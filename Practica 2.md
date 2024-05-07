# Codigo del simulador

import ssd1306
import utime


Configuración del display OLED
i2c = I2C(0, scl=Pin(9), sda=Pin(8))
oled_width = 128
oled_height = 64
oled = ssd1306.SSD1306_I2C(oled_width, oled_height, i2c)


Función para mostrar texto en el display OLED
def show_text(text):
    oled.fill(0)
    oled.text(text, 0, 0)
    oled.show()


Mostrar "Hola Mundo" en el display OLED
show_text("Hola mundo")
