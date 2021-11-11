# docker-install-memo-for-ubuntu

## Ubuntu 20.04へのDockerのインストールおよび使用方法

### ステップ1— Dockerをインストールする

1. 既存のパッケージのリストを更新

```ubntu
   $sudo apt update
```

2. aptがHTTPS経由でパッケージを使用できるようにするいくつかの必要条件パッケージをインストール
3
   $sudo apt install apt-transport-https ca-certificates curl software-properties-common


3. 公式DockerリポジトリのGPGキーをシステムに追加

   $curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -


4.DockerリポジトリをAPTソースに追加
$sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"


5.追加されたリポジトリからDockerパッケージでパッケージデータベースを更新
$sudo apt update


6.デフォルトのUbuntuリポジトリではなく、Dockerリポジトリからインストールしようとしていることを確認
$apt-cache policy docker-ce


7.最後に、Dockerをインストール
$sudo apt install docker-ce


8.これでDockerはインストールされ、デーモンが起動し、プロセスがプート時に起動できるようになりました。実行されていることを確認
$sudo systemctl status docker


ステップ2— SudoなしでDockerコマンドを実行する（オプション）

1.dockerコマンドを実行するたびに sudoを入力しないようにするには、ユーザー名をdockerグループに追加
sudo usermod -aG docker ${USER}


2.次のように入力して、ユーザーがdockerグループに追加されたことを確認
id -nG

※うまくいかなかったら再起動！！！！
