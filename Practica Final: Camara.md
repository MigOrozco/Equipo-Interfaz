# Practica Final: Camara

 Programa: Proyecto con camara 
 
  Autor: [Aguilar Orozco Jose Miguel]
  
Autor: [Álvarez Armenta Steve Jovanni]

Autor: [Agatón Gutiérrez Daniel]

Autor: [Inzunza Montaño Erick Geovanny]

# Codigo de Arduino IDE
```
include <Wire.h>
include <OV7670.h>

OV7670 cam;

void setup() {
  Serial.begin(115200);
  
  Wire.begin();
  
  // Inicia la cámara
  if (!cam.init()) {
    Serial.println("No se pudo inicializar la cámara");
    while (1);
  }

  // Configura la cámara
  cam.setQVGA(); // QVGA Mode
  cam.setRGB565(); // RGB565 Mode
  
  // Inicia la captura
  cam.startCapture();
}

void loop() {
  if (cam.isFrameComplete()) {
    // Lectura del frame completo
    for (int i = 0; i < cam.getFrameBufferSize(); i++) {
      Serial.write(cam.getFrameBuffer()[i]);
    }

```
    
    // Reinicia la captura
    cam.startCapture();
  }
}

