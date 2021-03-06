
# Ubuntu 20.04へのDockerのインストールおよび使用方法

### ステップ1— Dockerをインストールする

1. 既存のパッケージのリストを更新
```bash
   sudo apt update
```

2. aptがHTTPS経由でパッケージを使用できるようにするいくつかの必要条件パッケージをインストール
```bash   
   sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

3. 公式DockerリポジトリのGPGキーをシステムに追加
```bash
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

4. DockerリポジトリをAPTソースに追加
```bash
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

5. 追加されたリポジトリからDockerパッケージでパッケージデータベースを更新
```bash
   sudo apt update
```

6. デフォルトのUbuntuリポジトリではなく、Dockerリポジトリからインストールしようとしていることを確認
```bash
   apt-cache policy docker-ce
```

7. 最後に、Dockerをインストール
```bash
   sudo apt install docker-ce
```

8. これでDockerはインストールされ、デーモンが起動し、プロセスがプート時に起動できるようになりました。実行されていることを確認
```bash
   sudo systemctl status docker
```

### ステップ2— SudoなしでDockerコマンドを実行する（オプション）

1. dockerコマンドを実行するたびに sudoを入力しないようにするには、ユーザー名をdockerグループに追加
```bash
sudo usermod -aG docker ${USER}
```

2. 次のように入力して、ユーザーがdockerグループに追加されたことを確認
```bash
id -nG
```
# ※うまくいかなかったら再起動！！！！


## 参考
[Ubuntu 20.04へのDockerのインストールおよび使用方法](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-ja)

