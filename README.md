# Practica 0
# Codigo de Arduino
/*
  Programa: Control de Raspberry Pi Pico W
  Autor: [Aguilar Orozco Jose Miguel]
  
Autor: [Álvarez Armenta Steve Jovanni]

Autor: [Agatón Gutiérrez Daniel]

Autor: [Inzunza Montaño Erick Geovanny]

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
