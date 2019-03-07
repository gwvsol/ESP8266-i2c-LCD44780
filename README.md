## ESP8266 i2c LCD44780

[![micropython](https://user-images.githubusercontent.com/13176091/53680744-4dfcc080-3ce8-11e9-94e1-c7985181d6a5.png)](https://micropython.org/)

Библиотека для работы микроконтроллера ESP8266 с LCD44780 через интерфейс i2c и преобразователь PCF8574.

***
#### Схема включения преобразователь PCF8574 и LCD44780

![esp8266-i2c-lcd44780](https://user-images.githubusercontent.com/13176091/53985630-d33b0780-4124-11e9-9762-d804b64032c1.png)

#### Пример использования
```python
from machine import I2C, Pin
from i2c_lcd_api import I2cLcd

#### Вывод информации на LCD HD44780 по шине i2c через PCF8574
i2c = I2C(scl=Pin(5), sda=Pin(4), freq=400000)     #Настройка шины i2c
lcd = I2cLcd(self.i2c, 0x27, 4, 20) # Настройка экрана 4 строки 20 символов
lcd.backlight_on()
lcd.display_on()
lcd.move_to(0, 0)
self.lcd.putstr('Test')
self.lcd.display_off()
self.lcd.backlight_off()
```









