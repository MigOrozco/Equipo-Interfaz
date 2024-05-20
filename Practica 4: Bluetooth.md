# Practica 4: Bluetooth
 Programa: Control a travez de Bluetooth
 
  Autor: [Aguilar Orozco Jose Miguel]
  
Autor: [Álvarez Armenta Steve Jovanni]

Autor: [Gutiérrez Agaton Daniel]

Autor: [Inzunza Montaño Erick Geovany]

# Codigo 1
```
from machine import UART, Pin

blue = UART (1,9600)
led =  Pin(25, Pin.OUT)

while True:
    msg = blue.readline()
    if "on" in msg:
        led.value(1)
        blue.write("led on\r\n")
    elif "off" in msg:
        led.value(0)
        blue.write("led off\r\n")
    else:
        blue.write("Sin FUNCIONAR\r\n")
```
# Codigo 2
```
import serial
import struct

# Configura la conexión serial
ser = serial.Serial('COM6', 115200)  
while True:
    file_size_bytes = ser.read(4)
    file_size = struct.unpack('<I', file_size_bytes)[0]

    # Lee los datos de la fotografía
    image_data = ser.read(file_size)

    # Guarda los datos en un archivo
    file_name = f"photo_{len([f for f in os.listdir('.') if f.startswith('photo_')])}.jpg"
    with open(file_name, 'wb') as f:
        f.write(image_data)

    print(f"Fotografía guardada como {file_name}")
```
