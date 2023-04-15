# docker-ssh

## composition
- Docker
- SSH Server
  - amazonlinux
  - openssh-server
- SSH Client
  - centOS
  - openssh-clients

## install and Usage
1. コンテナ起動
```shell
docker compose build
docker compose up -d
```

2. コンテナ確認
```shell
docker ps
docker compose ps
```

3. コンテナホストからの接続
```shell
$ ssh root@localhost
Are you sure you want to continue connecting (yes/no)? yes
root@ssh-server's password: (root)
-bash-4.2#
```

4. dokcerコンテナからの接続
```shell
$ docker compose exec ssh-client bash
root@12345 app]# ssh root@ssh-server
Are you sure you want to continue connecting (yes/no)? yes
-bash-4.2#
```

5. 要点
#### `/etc/ssh/sshd_config`の設定について
- ポート公開
```
#Port 22 -> Port 22
```
- DNS無効化(有効だとコンテナホストからの接続時にホスト解決できないためにタイムアウトまで待ってしまう)
```
#UseDNS yes -> UseDNS no
```
