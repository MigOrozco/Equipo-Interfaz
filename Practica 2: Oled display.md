# Practica 2: Oled display
# Integrantes
 Programa: Despliegue en Oled display
 
  Autor: [Aguilar Orozco Jose Miguel]
  
Autor: [Álvarez Armenta Steve Jovanni]

Autor: [Agatón Gutiérrez Daniel]

Autor: [Inzunza Montaño Erick Geovanny]

# Comando código para desplegar un mensaje en Display OLED
![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/1fd8ad80-bf97-484a-bb53-13440447f69c)

# Codigo en arduino IDE
```
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128 // Ancho del OLED
#define SCREEN_HEIGHT 64 // Alto del OLED
#define OLED_RESET -1    // Sin pin de reset
#define SCREEN_ADDRESS 0x3C // Dirección I2C del OLED, ajustar si es necesario

Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

void setup() {
  Serial.begin(9600);

  if (!display.begin(SSD1306_SWITCHCAPVCC, SCREEN_ADDRESS)) {
    Serial.println(F("SSD1306 allocation failed"));
    for (;;); // Bucle infinito
  }
  display.clearDisplay();
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0, 0);
  display.println("Practica 4.2");
  display.println("OLED Display");
  display.println("");
  display.println("Equipo");
  display.println("Team KSM");
  display.display();
}

void loop() {
  // No hay necesidad de hacer nada en el loop para este ejemplo
}

```

# Imagen de ejecucion
![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/2d5c8510-992a-4c83-be8b-271aa3c71665)

