# Practica 0
# Código de Arduino
/*
  Programa: Control de Raspberry Pi Pico W
  Autor: [Aguilar Orozco Jose Miguel]
  
Autor: [Álvarez Armenta Steve Jovanni]

Autor: [ Gutiérrez Agatón  Daniel]

Autor: [Inzunza Montaño Erick Geovany]

  Fecha: [Fecha de creación]

  Descripción:
  Este programa inicializa un parpadeo del let interno de la Raspberry Pi Pico W por medio de arduino IDE
  Licencia: [Tipo de licencia]
*/

#include <Arduino.h>

// Definir el número de pin al que está conectado el LED interno
const int pinLed = LED_BUILTIN;

void setup() {
  // Inicializar el pin del LED interno como salida
  pinMode(pinLed, OUTPUT);
}

void loop() {
  // Encender el LED interno
  digitalWrite(pinLed, HIGH);
  delay(500); // Esperar 500 milisegundos (0.5 segundos)

  // Apagar el LED interno
  digitalWrite(pinLed, LOW);
  delay(500); // Esperar 500 milisegundos (0.5 segundos)


## Imagen de codigo en ArduinoIDE
![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/6e4bac39-86b1-485c-9c7d-a320a83faf02)

## Funcionamiento de la Raspberry Pi Pico W
![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/c67b0aa0-73e0-4a30-af9d-11c394758280)


