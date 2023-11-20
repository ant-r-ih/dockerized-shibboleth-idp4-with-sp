こちらはShibbolethをDocker環境で動かすためのDockerfileです。インストール方法、使い方などは以下のブログをご覧ください！！  
https://tech-lab.sios.jp/archives/19270

1. Docker file を作成
'''
cd idp
docker run -it -v $(pwd):/ext-mount --rm noriyukitakei/dockerized-shibboleth-idp4 gen-idp-conf.sh
cd ..
'''

2. 実行
'''
docker-compose up -d
'''

id:test001
password:password
