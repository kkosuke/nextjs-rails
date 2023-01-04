# 環境
- ruby 3.0.0
- node 18.7.0

# DB環境
- docker-compose.yml

# 環境構築参考
- https://zenn.dev/kei178/articles/43172ba33eece4

## 入り方
```
$ docker ps
CONTAINER ID   IMAGE
XXXX           mysql:8.0.20

$ docker exec -it XXXX mysql -u root -p
Enter password:
# docker-compose.ymlの、DB_PASSWORD の値を入力
```

# 起動方法
## 1
```
$ ngrok http 8080
```
その値を以下のfileに記載する。

- project-backend/.env
- project-frontend/.env.local

※ ngrok をリスタートするたびに変えてください。
※ .env.sample、.env.local.sampleを参考に

## 2
```
$ docker-compose up
```
で、それぞれの Dockerfile の CMD のコードが叩かれる。

その後、以下のURLで、NEXT.JSや、Rails API、Sidekiqの管理画面が表示されることを確認できる。
- http://localhost:3000/
- http://localhost:8080/
- http://localhost:8080/sidekiq
