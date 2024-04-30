# Practica 1
##   Codigo

 Programa: Control de Raspberry Pi Pico W
 
  Autor: [Aguilar Orozco Jose Miguel]
  
Autor: [Álvarez Armenta Steve Jovanni]

Autor: [Agatón Gutiérrez Daniel]

Autor: [Inzunza Montaño Erick Geovanny]

  Fecha: [Fecha de creación]

  Descripción:
  Este programa imprime en la consola serial de arduino IDE la frase "Hello world"
  Licencia: [Tipo de licencia]

void setup() {
  // Inicializa la comunicación serial a 9600 baudios
  Serial.begin(9600);
}

void loop() {
  // Imprime "Hello, World!" en la consola serial
  Serial.println("Hello, World!");
  // Espera un momento para que puedas leer el mensaje
  delay(1000);
}
## Imagen del codigo en Arduino IDE
![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/be37c874-012c-49ce-93df-048ef9dca12d)

## Resultado en consola
![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/1484fc85-977e-4883-b26c-2a6cf87bb2c0)

