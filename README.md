こちらはShibbolethをDocker環境で動かすためのDockerfileです。インストール方法、使い方などは以下のブログをご覧ください！！  
https://tech-lab.sios.jp/archives/19270

1. Docker file を作成
```
cd idp
docker run -it -v $(pwd):/ext-mount --rm noriyukitakei/dockerized-shibboleth-idp4 gen-idp-conf.sh
cd ..
```

2. 実行
```
docker-compose up -d
```

3. ホスト書き換え
OSのhostsファイルに以下のように設定して下さい。
```
127.0.0.1 idp.example.org
127.0.0.1 sp.example.org
```

4. テスト
以下にアクセスしてください
```
https://sp.example.org:10443/secure/testsp.php
```
認証情報は
```
id:test001
password:password
```
