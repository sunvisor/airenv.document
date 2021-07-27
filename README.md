AirEnv
======

- CO2 濃度を測定する
- 現在の CO2 濃度に応じて、赤・黄・緑の LED を点灯させる
- 一定間隔で web サーバーに測定値を送信する
- web サーバーにアクセスすると、最新の CO2 濃度や、濃度の推移が確認できる

使用する機器
----------

- Raspberry Pi Zero W
- CCS881 センサー搭載ボード
  - https://www.amazon.co.jp/gp/product/B09329T245/
  
回路
----

- [回路図と基盤レイアウト](circuit/circuit.md)

リポジトリ
----------

- サーバー: 計測値を保存・取得する Web API 
  - https://github.com/sunvisor/airenv.server
- デバイス: CO2 を計測する python プログラム
  - https://github.com/sunvisor/airenv.device

Raspberry PI の設定
----------

- [Raspberry PI のセットアップ](device/setup_pi.md)
- [CCS811 が使えるようにする](device/ccs811.md)
- [プログラムのインストールと Superviser](device/supervisor.md)

Web API

- CentOS サーバーを用意
- ansible playbook を実行

```
cd airenv.server/ansible
ansible-playbook site.yml
```
