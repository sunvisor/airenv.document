Raspberry Pi W の初期設定
=========================

キーボードを USB で接続して実施した。
別のコンピューターからSD カードを事前に編集することで、
固定IP の設定などができるので
キーボードを繋がなくてもいいようにできるようだ。
次はそうしよう。

raspi-config コマンド
---------------------

- ホスト名の設定
- ロケールの設定
    - 4 Localisation Option
    - I1 Change Locale
    - `ja_JP.UTF-8`
- タイムゾーンの設定
    - 4 Localisation Option
    - I2 Change Timezone
- キーボードの設定
    - 4 Localisation Option
    - I2 Change Keyboard Layout
- SSH を有効に
    - 5 Interfacing Options
    - P2 SSH
- I2C を有効に (CO2センサーで使用する)
    - 5 Interfacing Options
    - P5 I2C

固定IP
------

ファイル: `/etc/dhcpcd.conf`

```
interface wlan0
static ip_address=192.168.0.230/24
static routers=192.168.0.254
static domain_name_servers=192.168.0.254
```

