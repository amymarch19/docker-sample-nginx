# docker-sample-nginx

A sample nginx container for training

以下のコマンドでウェブサーバーを起動してみる(Dockerの動作確認)

```
$ docker run --rm -d -p 8080:80 --name web nginx
```

ブラウザーで　http://localhost:8080 にアクセスして動作確認

動作を停止

```
$ docker stop web
```

Githubびログイン後以下のアドレスにアクセス、レポジトリーをFork

参考：　https://github.com/IBMDeveloperTokyo/DojoBasicLab/tree/master/Lab3_GitHub/Lab3-1_GitHub

```
https://github.com/osonoi/docker-sample-nginx.git
```

このレポジトリーをClone

```
$ git clone https://github.com/(ご自分のアカウント名)/docker-sample-nginx.git
```

Dockerfileを参照、index.htmlを編集
イメージを作成

```
$ docker build -t webserver .
```

イメージを起動

```
$ docker run --rm -d -p 8080:80 --name web webserver
```

動作を停止

```
$ docker stop web
```

イメージをDockerHubにアップロード

```
$ docker login
$ docker tag webserver yosonoi/webserver
$ docker push yosonoi/webserver:latest
** yosonoiのところはご自分のアカウント名にしてください。
```

dockerHubでイメージを確認

https://hub.docker.com/

DockerHubのイメージで起動(できれば他のメンバーのアカウントのイメージを使って）

```
docker run --rm -d -p 8080:80 --name web yosonoi/webserver
```

