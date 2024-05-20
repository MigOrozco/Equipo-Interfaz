# Integrantes
 Programa: Control de Raspberry Pi Pico W con C#
 
  Autor: [Aguilar Orozco Jose Miguel]
  
Autor: [Álvarez Armenta Steve Jovanni]

Autor: [Agatón Gutiérrez Daniel]

Autor: [Inzunza Montaño Erick Geovany]

  
# Practica
En esta parte se conecta al Pi pico

Aqui se envía el mensaje “Hola mundo” con el botón Enviar

![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/c55eb4ea-1099-4c1b-839c-663ae615af5c)


En esta imagen se está desconectando  del Pi pico

![image](https://github.com/MigOrozco/Equipo-Interfaz/assets/158230692/a0ade724-2b26-4b1d-824d-2e11da5825a6)

# Codigo del c#
```
namespace InterfazProyect
{
    public partial class PicoWCSharp : Form
    {
        SerialPort puertoSerial;

        public PicoWCSharp()
        {
            InitializeComponent();
            // Llenar el ComboBox con los puertos seriales disponibles
            string[] puertosDisponibles = SerialPort.GetPortNames();
            CBPuertos.Items.AddRange(puertosDisponibles);
        }
        private void BtnConectar_Click_1(object sender, EventArgs e)
        {
            if (CBPuertos.SelectedItem != null)
            {
                try
                {
                    // Configurar y abrir el puerto serial seleccionado
                    puertoSerial = new SerialPort(CBPuertos.SelectedItem.ToString());
                    puertoSerial.Open();
                    MessageBox.Show("Conexión establecida correctamente", "Conexión exitosa", MessageBoxButtons.OK, MessageBoxIcon.Information);
                }
                catch (Exception ex)
                {
                    MessageBox.Show("Error al conectar al puerto serial: " + ex.Message, "Error de conexión", MessageBoxButtons.OK, MessageBoxIcon.Error);
                }
            }
            else
            {
                MessageBox.Show("Por favor, seleccione un puerto serial", "Puerto no seleccionado", MessageBoxButtons.OK, MessageBoxIcon.Warning);
            }
        }

        private void BtnDesconectar_Click_1(object sender, EventArgs e)
        {
            if (puertoSerial != null && puertoSerial.IsOpen)
            {
                puertoSerial.Close();
                MessageBox.Show("Conexión cerrada correctamente", "Desconexión exitosa", MessageBoxButtons.OK, MessageBoxIcon.Information);
                TxtMensaje.Clear();
            }
            else
            {
                MessageBox.Show("No hay una conexión activa para cerrar", "Sin conexión", MessageBoxButtons.OK, MessageBoxIcon.Warning);
                TxtMensaje.Clear();
            }
        }

        private void BtnReset_Click_1(object sender, EventArgs e)
        {
            TxtMensaje.Clear();
        }

        private void BtnEnviar_Click_1(object sender, EventArgs e)
        {
            if (puertoSerial != null && puertoSerial.IsOpen)
            {
                try
                {
                    // Enviar el mensaje del TextBox por el puerto serial
                    puertoSerial.Write(TxtMensaje.Text);
                    MessageBox.Show("Mensaje enviado correctamente", "Mensaje enviado", MessageBoxButtons.OK, MessageBoxIcon.Information);
                }
                catch (Exception ex)
                {
                    MessageBox.Show("Error al enviar el mensaje: " + ex.Message, "Error de envío", MessageBoxButtons.OK, MessageBoxIcon.Error);
                }
            }
            else
            {
                MessageBox.Show("No hay una conexión activa para enviar el mensaje", "Sin conexión", MessageBoxButtons.OK, MessageBoxIcon.Warning);
            }
        }

        private void PicoWCSharp_Load(object sender, EventArgs e)
        {

        }
    }
}
```

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

