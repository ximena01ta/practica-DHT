# REPORTE DEL SENSOR DHT22 CON TARJETA ESP32
## Introducción
En esta práctica se usará el sensor 


## Materiales
Simulador WOKWI (https://wokwi.com) :
- Tarjeta ESP32
- Sensor DHT22

## Procedimiento 
1. En el buscador ingresar la página https://wokwi.com

![]()

3. Seleccionar la opción ``ESP32`` en ambos casos

![]()
![]()

Nos llevará a la siguiente página:

![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-05%20010757.png)

4. En la parte de ``sketch.ino`` nos muestra el código anterior que debemos borrar para colocar el nuevo a continuación:
````#include "DHTesp.h" 

const int DHT_PIN = 15;
DHTesp dhtSensor;

void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  
  Serial.println("---");
  
  delay(1000);
}
````
4. En ``Library Manager`` vamos a buscar en la opción de ``+`` la siguiente biblioteca:
- DHT sensor library for ESPx

![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-04%20230418.png) 

5. Para colocar el sensor nos iremos a la parte de ``Simulation`` en la opción de ``+`` y buscar:
- DHT22

![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-04%20230350.png) 
![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-04%20231406.png) 

6. Se hace la conexión del ESP32 con el DHT22 (pines con la tarjeta)

![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-04%20202932.png)

8. Iniciamos la simulación con el botón ``play (|>)`` y empezará a darnos los lectores del sensor. 

![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-04%20230350.png) 
![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-04%20202856.png)

## Resultados
Obtenemos los resultados de humedad y temperatura.
![](https://github.com/ximena01ta/practica-DHT/blob/main/Captura%20de%20pantalla%202025-12-04%20202856.png)
