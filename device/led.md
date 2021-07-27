LED点灯実験
===========

単純に LED を点灯させる実験

![](http://hara.jpn.com/images/_default/Topics/RaspPiZero/RaspPiZero.png)

3つのLEDを点灯させる GPIO は 17, 27,22 を使う

- 抵抗 510Ω

まず、3.3V VCC と GND で繋いで点灯を確認

python でLチカ実験

```python
import RPi.GPIO as GPIO
from time import sleep

GPIO.setmode(GPIO.BCM)
GPIO.setup(17, GPIO.OUT)
GPIO.setup(27, GPIO.OUT)
GPIO.setup(22, GPIO.OUT)

while True:
    GPIO.output(17, GPIO.HIGH)
    sleep(0.5)
    GPIO.output(17, GPIO.LOW)
    GPIO.output(27, GPIO.HIGH)
    sleep(0.5)
    GPIO.output(27, GPIO.LOW)
    GPIO.output(22, GPIO.HIGH)
    sleep(0.5)
    GPIO.output(22, GPIO.LOW)
```

- GPIO.setup で出力ポートとして指定し
- GPIO.output で設定すれば OK
