### デバイスのプログラムを clone

```
git clone https://github.com/sunvisor/airenv.device.git ./airenv
```

コンソールから実行する場合は以下のように

```
cd airenv
python3 main.py
```

### Supervisor でデーモン化

Supervisor を使うと、デーモン化できて落ちたときに自動再起動などもしてくれる。

```
# root ユーザーで
apt-get install supervisor
# 起動
service supervisor start
# 確認
service supervisor start
```

**/etc/supervisor/conf.d/airenv.conf** を作成

```
[program:AirEnv]
command=python3 /home/pi/airenv/main.py
process_name=airenv.py
directory=/home/pi/airenv/
numprocs=1
autostart=true
autorestart=true
user=pi
redirect_stderr=true
stdout_logfile=/home/pi/airenv/log/airenv.log
```

conf を読み込んでデーモンを追加

```
# conf 読み込み
supervisorctl reread
# 追加
supervisorctl add AirEnv
# 確認
supervisorctl status
```
