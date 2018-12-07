# my-docker

my-dockerは、よく使用する開発環境をDockerで実現したものになります。  
現在実現できる環境は以下になります。  

- web service (Rails)  

## web service (Rails)
web/apコンテナとdbコンテナを建てることができます。  

**web/apコンテナ**  
HTTPS(443ポート)でNginxまで通信を行い、HTTP(localhost:80)でリバースプロキシを使用して後方のPuma(Rails APサーバ)に連携します。  
クライアントからNginxまでの通信で使用するSSL証明書は、自己証明書を想定しています。構築する場合は、`./rails/web-ap/nginx/sslcert`配下に自己証明書と秘密鍵を準備して下さい。  
> RailsのAPサーバはDockerfileでは用意していません。個人で準備して下さい。

**dbコンテナ**  
postgres:10.6のイメージを使用しています。また、データ領域を永続化させるためにローカルの`./rails/db`ディレクトリをマウントしています。  


### How to run
下記を実行し、コンテナを起動して下さい。  
```
$ cd ./rails
$ docker-compose run -d

起動後、http://localhost:8888/にアクセスする
```

# Author
[Katsuya Yamaguchi](https://github.com/katsuya-yamaguchi)
