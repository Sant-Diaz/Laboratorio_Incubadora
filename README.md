<h1 align="center"> Diseño y Construcción De Una Incubadora Neonatal a Escala</h1>

## PARTE A – Punto 1: Identificación de las Partes Principales de una Incubadora Neonatal

#### 1. Introducción

La incubadora neonatal es un dispositivo médico cuya finalidad principal es generar un microambiente controlado que emule las condiciones del vientre materno, asegurando la supervivencia y el desarrollo óptimo del neonato, en especial de aquellos nacidos de forma prematura [1][2]. Su funcionamiento está regido por la norma internacional **IEC 60601-2-19**, que establece los requisitos de seguridad básica y desempeño esencial para este tipo de equipos [3].
<p align="center">
  <img src="https://github.com/user-attachments/assets/b2a5009f-b3ad-487c-89be-199b771ec75e" width="400" height="400" alt="image">
</p>

>  *Los neonatos prematuros poseen una piel más delgada y un sistema nervioso inmaduro, lo que afecta severamente su capacidad de termorregulación [4]. Por ello, la incubadora se convierte en un elemento crítico para su supervivencia.*

---

#### 2. Componentes Principales y sus Funciones

A continuación se identifican y describen los componentes principales de una incubadora neonatal, con base en revisión bibliográfica de artículos científicos, manuales técnicos y la norma IEC 60601-2-19.



##### 2.1 Cámara o Capacete (Cubierta Transparente)
<div align="center">

| Parámetro | Descripción |
|-----------|-------------|
| **Material** | Acrílico simple o doble |
| **Función** | Aislar al neonato y generar un microclima controlado |
| **Característica clave** | Permite visibilidad continua sin perder contacto visual |

</div>

La cámara o capacete es la estructura principal que encierra al neonato. Está fabricada en acrílico transparente (simple o doble capa), lo que permite el monitoreo visual constante mientras mantiene el microclima en su interior [5]. Esta cubierta actúa como barrera contra corrientes de aire frío, bajas temperaturas externas y contaminantes del entorno [6].

La cubierta cuenta con **portillos de acceso laterales** que permiten la atención médica al neonato minimizando la pérdida de calor hacia el interior [7]. Según la norma IEC 60601-2-19, la cubierta debe garantizar que la temperatura en el compartimento del paciente se mantenga estable y uniforme [3].



##### 2.2  Sistema de Calefacción y Control Térmico
<div align="center">
  <table>
    <tr>
      <th>Parámetro</th>
      <th>Descripción</th>
    </tr>
    <tr>
      <td><b>Elemento calefactor</b></td>
      <td>Resistencia eléctrica (heater)</td>
    </tr>
    <tr>
      <td><b>Mecanismo</b></td>
      <td>Convección forzada</td>
    </tr>
    <tr>
      <td><b>Rango de temperatura</b></td>
      <td>36 °C – 37,5 °C</td>
    </tr>
    <tr>
      <td><b>Sensor asociado</b></td>
      <td>Termistor (NTC)</td>
    </tr>
  </table>
</div>
El calor se suministra al interior de la incubadora mediante **convección forzada**: un ventilador o turbina toma el aire del exterior y lo hace circular a través de un elemento resistivo calefactor hasta alcanzar la temperatura de referencia establecida por el personal médico [7][8].

El sistema puede operar en dos modos:
- **Modo de control de aire:** regula la temperatura del aire al interior de la cámara.
- **Modo de control de piel (Baby-Controlled):** regula la temperatura a partir de la lectura de un sensor cutáneo adherido al abdomen del neonato [3][8].

La temperatura del elemento calefactor se controla mediante una señal eléctrica proporcional al error entre la temperatura medida y el valor de referencia, implementando típicamente un controlador **PID** [9].

>  *Un mal funcionamiento en el sistema de calefacción puede producir hipotermia o hipertermia, ambas condiciones de alto riesgo para el neonato [4].*


##### 2.3  Ventilador o Turbina de Circulación de Aire
<div align="center">
  
| Parámetro | Descripción |
|-----------|-------------|
| **Tipo** | Ventilador DC de baja potencia |
| **Función** | Circulación forzada del aire caliente |
| **Nivel de ruido máximo** | 60 dB (según IEC 60601-2-19) |

</div>
El ventilador toma el aire del exterior, lo hace pasar por el elemento calefactor y lo distribuye uniformemente dentro de la cámara [7]. Este componente es fundamental para garantizar una distribución homogénea de la temperatura en toda la cabina. La norma IEC 60601-2-19 establece que el nivel máximo de ruido admisible dentro del habitáculo es de **60 dB**, ya que el exceso de ruido puede afectar negativamente el desarrollo neurológico del neonato [8].



##### 2.4  Sistema de Humidificación
<div align="center">
  
| Parámetro | Descripción |
|-----------|-------------|
| **Componente** | Reservorio o depósito de agua destilada |
| **Variable controlada** | Humedad relativa del aire interior |
| **Sensor** | Sensor de humedad (e.g., SHT11) |

</div>

El sistema de humidificación consiste en un **depósito de agua** localizado en la parte inferior de la incubadora. El calor generado por el sistema de calefacción evapora parcialmente el agua, aumentando la humedad relativa del aire interior [7][8]. Controlar la humedad es esencial para reducir la pérdida de agua transcutánea (TEWL) en neonatos prematuros, cuya piel aún no ha madurado completamente [4].

Según el estándar IEC 60601-2-19, el sensor de humedad debe ubicarse en el punto central de medición **(Punto A)**, a 10 cm sobre el colchón, siguiendo el esquema de cinco puntos de medición definido por la norma [10].



##### 2.5 Módulo de Control y Panel de Alarmas
<div align="center">
  
| Parámetro | Descripción |
|-----------|-------------|
| **Tipo de control** | Microprocesador con algoritmos de control (PID) |
| **Alarmas** | Audibles y visuales |
| **Variables monitoreadas** | Temperatura, humedad, oxígeno |

</div>

El módulo de control es el "cerebro" de la incubadora. Integra los sensores, procesa las señales adquiridas y genera las señales de actuación para el calefactor, el ventilador y el humidificador [6][7]. Los sistemas modernos utilizan **microprocesadores** con algoritmos de control digital que permiten una regulación precisa de todas las variables del microambiente [9].

El panel de alarmas alerta al personal médico ante desviaciones fuera del rango seguro de operación. Las alarmas pueden ser:
- **Alarma de alta temperatura:** protege al neonato de hipertermia.
- **Alarma de baja temperatura:** alerta ante posible hipotermia.
- **Alarma de falla del sensor:** indica mal funcionamiento de los transductores [7][9].

##### 2.6 Sensores

Los sensores son los transductores que convierten las variables físicas del microambiente en señales eléctricas procesables por el módulo de control. Los principales sensores en una incubadora neonatal son:
<div align="center">
  
| Sensor | Variable medida | Tecnología típica |
|--------|----------------|-------------------|
| Sensor de temperatura del aire | Temperatura del aire interior | Termistor NTC |
| Sensor de temperatura cutánea | Temperatura superficial del neonato | Termistor de contacto (e.g., W0001A) |
| Sensor de humedad relativa | Humedad del aire interior | Capacitivo (e.g., SHT11) |
| Sensor de oxígeno | Concentración de O₂ | Electroquímico |

</div>

Según la norma IEC 60601-2-19, los sensores de temperatura y humedad deben posicionarse en **cinco puntos específicos** dentro del habitáculo (A, B, C, D, E), todos ubicados a 10 cm sobre la superficie del colchón, para verificar la uniformidad del microclima [10]. El sensor de temperatura del aire debe calibrarse periódicamente por personal autorizado [11].

>  *El termistor de control de temperatura del aire y el termistor de alarma por alta temperatura se encuentran encapsulados juntos en el módulo sensor, a través del cual circula el flujo de aire antes de entrar al habitáculo [7].*

##### 2.7 Colchón y Estructura de Soporte (Chasis)
<div align="center">
  
| Componente | Función |
|------------|---------|
| **Colchón** | Superficie donde reposa el neonato; debe ser de material poco poroso para facilitar limpieza y esterilización |
| **Portacolchón** | Plataforma que sostiene el colchón dentro del habitáculo |
| **Chasis / Gabinete** | Base metálica que integra la fuente de poder, sensores y permite movilización del equipo |

</div>

El **chasis** es la estructura metálica base sobre la cual reposa toda la incubadora. Contiene la fuente de alimentación eléctrica y los principales componentes electrónicos, y está diseñado para permitir la movilización del equipo [6]. Sobre el chasis se ubica el portacolchón, y encima de este, el colchón donde se deposita al neonato.


##### 2.8  Fuente de Alimentación

La fuente de alimentación convierte la tensión alterna de la red eléctrica (110/220 VAC) en los niveles de tensión continua necesarios para los distintos componentes electrónicos del sistema. En los prototipos académicos se emplean comúnmente circuitos basados en transformadores, puentes rectificadores y reguladores de voltaje como el **LM317** y **LM337** [9].

>  *La fuente debe cumplir con los requisitos de corriente de fuga establecidos por IEC 60601-1 para equipos de tipo BF (Body Floating), limitando las corrientes de fuga al paciente a valores menores de 100 µA en condición normal [11].*

##### 2.9  Portillos de Acceso

Los portillos son aberturas en las paredes laterales y frontales de la cámara, equipadas con sellos de goma o material flexible, que permiten el acceso de las manos del personal médico o el paso de equipos (catéteres, cables de monitoreo, sondas de oxígeno) sin comprometer significativamente el microambiente interior [5][6].

---

#### 3. Resumen de Componentes
<div align="center">
  
| N° | Componente | Función Principal |
|----|------------|-------------------|
| 1 | Cámara / Capacete transparente | Aislar al neonato y generar microclima controlado |
| 2 | Sistema de calefacción (resistencia) | Elevar y mantener la temperatura interior |
| 3 | Ventilador / Turbina | Circular el aire caliente uniformemente |
| 4 | Humidificador (reservorio) | Controlar la humedad relativa interior |
| 5 | Módulo de control (microprocesador) | Procesar señales y ejecutar algoritmos de control |
| 6 | Panel de alarmas | Alertar sobre condiciones fuera del rango seguro |
| 7 | Termistor (sensor de temperatura) | Medir temperatura del aire y de la piel del neonato |
| 8 | Sensor de humedad | Medir humedad relativa del aire interior |
| 9 | Colchón y portacolchón | Soporte y posicionamiento del neonato |
| 10 | Chasis / Gabinete | Base estructural y alojamiento de componentes |
| 11 | Fuente de alimentación | Conversión y regulación de tensión eléctrica |
| 12 | Portillos de acceso | Acceso del personal médico al paciente |

</div>

#### Diseño y Simulación de Control de Temperatura y Peso
Se aborda el diseño y la simulación de un sistema de control de temperatura, considerando tanto el modelado del proceso térmico como la implementación de estrategias de control que permitan regular la variable de interés de manera eficiente. A través del uso de herramientas de simulación, se analizan las respuestas del sistema ante diferentes condiciones de operación, evaluando su estabilidad, precisión y capacidad de respuesta.
El control de peso constituye una variable clave en sistemas de medición y monitoreo, especialmente en aplicaciones donde la precisión y la estabilidad son fundamentales para la toma de decisiones. En este apartado se desarrolla el diseño y la simulación de un sistema de control de peso, considerando el comportamiento dinámico del proceso de medición y la integración de sensores adecuados para la adquisición de datos confiables.

<p align="center">
  <img 
    src="https://github.com/user-attachments/assets/86f4ba14-9a1f-4f7c-ac53-5d582a083df9" 
    alt="Imagen del proyecto" 
    width="700"
  />
</p>

## PARTE B – Contrucción del Modelo Neonatal 
### 1. Estructura Física 
Las imágenes a continuación muestran el diseño tanto estructural como circuital del modelo de incubadora realizado, que contaba con medidas espaciales de 40 × 20 × 22.

<div align="center">
  <table>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/e9bf6f14-52ff-42f0-b59b-6cf461582e23" width="300"></td>
      <td><img src="https://github.com/user-attachments/assets/876b9351-fe12-47e6-9a96-4036b9abd929" width="300"></td>
    </tr>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/621267e1-ddfb-4b27-bf87-61c98f231865" width="300"></td>
      <td><img src="https://github.com/user-attachments/assets/6c8f3219-ed4e-478f-8b3c-8eb1fa7c7011" width="300"></td>
    </tr>
  </table>
</div>

### 2. Código 
## PARTE B – Funcionamiento del Sistema de Control de la Incubadora (Código ESP32)

El siguiente código implementa un sistema de monitoreo y control para una incubadora neonatal a escala utilizando un microcontrolador **ESP32**, integrando sensores biomédicos y actuadores para garantizar condiciones térmicas adecuadas.  
El sistema permite medir temperatura, humedad y peso del neonato, además de controlar automáticamente un sistema de calefacción (bombillo), ventilación (ventilador) y señalización mediante LEDs, proporcionando retroalimentación visual en una pantalla OLED.


#### 2. Librerías utilizadas
Estas librerías permiten la comunicación con los diferentes dispositivos del sistema, incluyendo la pantalla OLED, el sensor de temperatura y humedad, y la celda de carga para medición de peso.
```
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>
#include <DHT.h>
#include "HX711.h"
```
#### 3. Configuración de pines del sistema
En esta sección se definen los pines del ESP32 a los cuales están conectados los sensores y actuadores, permitiendo la correcta comunicación entre hardware y software.

```
#define DHTPIN     4
#define DHTTYPE    DHT22

#define OLED_SDA   21
#define OLED_SCL   22

#define LED_OK     32
#define LED_LOW    18
#define LED_HIGH   25

#define FAN_PIN    33
#define RELAY_PIN  13

#define HX_DT      26
#define HX_SCK     27
```

#### 4. Definición de umbrales térmicos
Estos valores establecen los límites de temperatura para el control del sistema:

Temperatura baja: menor a 36°C
Temperatura normal: entre 36°C y 38°C
Temperatura alta: mayor a 38°C

````
const float TEMP_LOW  = 36.0;
const float TEMP_HIGH = 38.0;
````
#### 5. Variables del sistema
Estas variables almacenan las mediciones de los sensores y el estado actual de los actuadores.

  ````
float temperature = NAN;
float humidity    = NAN;
float weight_kg   = 0.0;

bool fanState    = true;
bool heaterState = false;
````
#### 6. Control de LEDs indicadores
Esta función permite visualizar el estado térmico del sistema mediante LEDs:

 - LED_LOW → temperatura baja
 - LED_HIGH → temperatura alta
 - LED_OK → temperatura normal
````
void actualizarLEDs(float t) {
  if (isnan(t))           setLEDs(false, false, false);
  else if (t < TEMP_LOW)  setLEDs(false, true,  false);
  else if (t > TEMP_HIGH) setLEDs(false, false, true);
  else                    setLEDs(true,  false, false);
}
````
#### 7. Control del sistema de calefacción (relé)
El relé controla el bombillo que actúa como fuente de calor:

- Se activa cuando la temperatura es inferior al límite superior
- Se desactiva cuando la temperatura supera dicho límite

````
void actualizarBombillo(float t) {
  if (isnan(t)) {
    setRelay(false);
    return;
  }
  if (t < TEMP_HIGH) setRelay(true);
  else               setRelay(false);
}
````
#### 8. Control del sistema de ventilación
El ventilador permanece encendido constantemente, garantizando circulación de aire dentro de la incubadora.

````
void actualizarVentilador() {
  fanState = true;
  digitalWrite(FAN_PIN, HIGH);
}
````
#### 9. Lectura del sensor de temperatura y humedad
Se obtienen las mediciones del sensor DHT22, validando que los datos no sean inválidos (NaN).

````
void leerDHT() {
  float t = dht.readTemperature();
  float h = dht.readHumidity();
  if (!isnan(t)) temperature = t;
  if (!isnan(h)) humidity    = h;
}
````
#### 10. Lectura del sensor de peso (HX711)
Se realiza la medición del peso del neonato:

- Se promedian múltiples lecturas
- Se filtra el ruido
- Se eliminan valores negativos

````
void leerPeso() {
  if (scale.is_ready()) {
    float w = scale.get_units(5);

    if (w > -0.03 && w < 0.03) w = 0.0;
    if (w < 0) w = 0.0;

    weight_kg = w;
  } else {
    Serial.println("HX711 no listo");
  }
}
````
Calibración:
````
scale.set_scale(calibration_factor);
````
#### 11. Visualización en pantalla OLED

La pantalla OLED permite visualizar en tiempo real los parámetros del sistema.
````
void mostrarOLED() {
  display.clearDisplay();
  display.setCursor(0, 0);

  display.println("Incubadora neonatal");

  display.print("Temp: ");
  display.println(temperature);

  display.print("Hum: ");
  display.println(humidity);

  display.print("Peso: ");
  display.println(weight_kg);

  display.display();
}
````
#### 12. Monitor serial
Se envían los datos al monitor serial para fines de depuración y validación.
````
void mostrarSerial() {
  Serial.print("Temp: ");
  Serial.println(temperature);

  Serial.print("Hum: ");
  Serial.println(humidity);

  Serial.print("Peso: ");
  Serial.println(weight_kg);
}
````
#### 13. Inicialización del sistema (setup)
En esta etapa se inicializan todos los dispositivos del sistema.
````
void setup() {
  Serial.begin(115200);

  pinMode(FAN_PIN, OUTPUT);
  pinMode(RELAY_PIN, OUTPUT);

  dht.begin();

  scale.begin(HX_DT, HX_SCK);
  scale.tare(20);
  scale.set_scale(calibration_factor);
}
````
#### 14. Ciclo principal de ejecución (loop)
El sistema opera de forma continua realizando:

1. Lectura de sensores
2. Procesamiento de datos
3. Control de actuadores
4. Visualización de resultados

````
void loop() {
  leerDHT();
  leerPeso();

  actualizarLEDs(temperature);
  actualizarVentilador();
  actualizarBombillo(temperature);

  mostrarOLED();
  mostrarSerial();

  delay(800);
}
````
#### 15. Funcionamiento general del sistema

El sistema implementa un control térmico básico en lazo cerrado:

- Si la temperatura disminuye → se activa el calefactor
- Si la temperatura aumenta → se desactiva el calefactor
- El ventilador mantiene circulación constante
- Se monitorean continuamente las condiciones internas

Este comportamiento permite mantener un ambiente estable y adecuado para el neonato, cumpliendo con el objetivo principal de una incubadora neonatal.
#### 16. Sistema de señalización mediante LEDs

Las imágenes presentadas corresponden al funcionamiento del sistema de indicadores luminosos (LEDs), los cuales permiten visualizar de manera rápida el estado térmico de la incubadora.

<div align="center">
  <table>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/baace015-da05-4da6-934f-afd345a6c57d" width="250"></td>
      <td><img src="https://github.com/user-attachments/assets/ea176424-b3f8-419b-afc3-6a3c27c4088e" width="250"></td>
      <td><img src="https://github.com/user-attachments/assets/59c2e623-b493-4582-ac39-d3565bcd428c" width="250"></td>
    </tr>
  </table>
</div>

El sistema utiliza tres LEDs:

- LED LOW → Indica temperatura baja  
- LED OK → Indica temperatura normal  
- LED HIGH → Indica temperatura alta  

## PARTE C – Preguntas para la Discusión

### Pregunta 1: ¿Qué otras variables (y por qué) además de las aquí mencionadas son críticas en el monitoreo neonatal?
Además de la temperatura y la humedad, las siguientes variables son críticas en el monitoreo neonatal:

#### 1.1 Concentración de Oxígeno (FiO₂)
El control de la fracción inspirada de oxígeno es una de las variables más delicadas en neonatología. Una concentración insuficiente de O₂ puede provocar **hipoxia**, daño cerebral o incluso la muerte del neonato. Sin embargo, una concentración excesiva sostenida puede causar **retinopatía del prematuro (ROP)**, una patología que puede llevar a la ceguera permanente [11][12]. Por esta razón, la norma IEC 60601-2-19 contempla el control de oxígeno como una variable de seguridad esencial en las incubadoras neonatales [13].

#### 1.2 Frecuencia Cardíaca

La frecuencia cardíaca es un indicador directo del estado hemodinámico del neonato. Los valores normales en un recién nacido oscilan entre 120 y 160 latidos por minuto (lpm). Alteraciones como la **bradicardia** (FC < 100 lpm) o la **taquicardia** (FC > 180 lpm) pueden ser señales de hipoxia, infección o fallo cardíaco, y requieren intervención médica inmediata [14]. Su monitoreo se realiza mediante electrodos de ECG adaptados para neonatos.

#### 1.3 Frecuencia Respiratoria y Saturación de Oxígeno (SpO₂)

La frecuencia respiratoria normal en un neonato es de 40 a 60 respiraciones por minuto. La **apnea neonatal** (pausas respiratorias mayores a 20 segundos) es frecuente en prematuros y puede generar hipoxia severa si no se detecta a tiempo [14]. La SpO₂ se monitorea de forma no invasiva mediante pulsioximetría y debe mantenerse entre el 91% y el 95% en prematuros para evitar tanto hipoxia como hiperóxia [11].

#### 1.4 Presión Arterial

La hipotensión neonatal puede ser indicativa de sepsis, hemorragia o disfunción cardíaca. Su monitoreo permite al equipo médico intervenir oportunamente con soporte hemodinámico. Se mide de forma no invasiva mediante manguitos de presión miniaturizados o de forma invasiva mediante catéter arterial [4].

#### 1.5 Nivel de Bilirrubina (Ictericia Neonatal)

La hiperbilirrubinemia es una condición muy frecuente en neonatos, especialmente prematuros. Niveles elevados de bilirrubina en sangre pueden causar **kernicterus**, una forma de daño cerebral irreversible. Por esta razón, muchas incubadoras modernas integran o se complementan con sistemas de **fototerapia** (lámparas de rayos UVA) que degradan la bilirrubina en la piel del neonato [15].

#### 1.6 Peso Corporal

El peso es un indicador fundamental del estado nutricional y el desarrollo del neonato. Pérdidas de peso superiores al 10% del peso al nacer pueden indicar deshidratación o problemas de absorción. Por ello, algunas incubadoras incluyen **balanzas integradas** que permiten el pesaje sin necesidad de retirar al neonato, reduciendo el estrés térmico y físico del procedimiento [15][16].

#### 1.7 Nivel de Ruido

Aunque no es una variable fisiológica del neonato, el nivel de ruido en el interior de la incubadora impacta directamente en su desarrollo neurológico y en la calidad del sueño. La norma IEC 60601-2-19 establece un límite máximo de **60 dB** dentro del habitáculo [13][16].

---

### Pregunta 2: ¿Qué haría falta para convertir el sistema desarrollado en una incubadora neonatal real?

Convertir el prototipo académico en un dispositivo médico real implica superar barreras técnicas, normativas, clínicas y económicas. A continuación se describen los principales aspectos a considerar:

#### 2.1 Cumplimiento Normativo (Certificación IEC 60601-2-19)

El requisito más exigente es la certificación bajo la norma **IEC 60601-2-19:2020**, que establece los requisitos de seguridad básica y desempeño esencial para incubadoras neonatales [3]. Esto implica:

- Verificación de uniformidad de temperatura en cinco puntos del habitáculo (A, B, C, D, E) a 10 cm sobre el colchón.
- Control de la temperatura con una precisión de ±0,5 °C respecto al valor de referencia.
- Tiempo de calentamiento definido y sobrepaso de temperatura (overshoot) no mayor a 2 °C.
- Corrientes de fuga al paciente menores a 100 µA en condición normal (tipo BF) [17].
- Nivel de ruido interior menor a 60 dB.

#### 2.2 Incorporación de Sensores Clínicos Adicionales

El prototipo desarrollado en el laboratorio solo controla temperatura y estima peso. Una incubadora real requiere monitoreo de:

- Saturación de oxígeno (SpO₂) mediante pulsioximetría neonatal.
- Concentración de O₂ interior mediante sensor electroquímico.
- Frecuencia cardíaca mediante electrodos de ECG neonatales.
- Frecuencia respiratoria.
- Temperatura cutánea del neonato (sensor adhesivo tipo W0001A) [18].

#### 2.3 Sistema de Control Más Robusto

El control implementado con componentes analíticos discretos (termistor + LM317) es funcional a nivel de prototipo, pero una incubadora real requiere:

- Un controlador **PID digital** implementado en microprocesador o microcontrolador de alta confiabilidad.
- Redundancia en sensores: al menos dos termistores independientes (control y alarma) para prevenir fallas silenciosas [8].
- Un sistema de alarmas audibles y visuales certificado, con alarma de falla de energía y batería de respaldo.

#### 2.4 Materiales Biocompatibles y Esterilizables

Todos los materiales en contacto con el neonato o con el aire interior deben ser:

- **Biocompatibles** (no tóxicos, no alergénicos).
- **Esterilizables** o de fácil desinfección (superficies lisas, pocas hendiduras).
- El colchón debe ser de material poco poroso para facilitar la limpieza [16].
- La cubierta debe ser de acrílico de grado médico, con resistencia mecánica suficiente para evitar fracturas que puedan dañar al neonato.

#### 2.5 Registro y Aprobación Sanitaria

En Colombia, el dispositivo debería registrarse ante el **INVIMA** (Instituto Nacional de Vigilancia de Medicamentos y Alimentos) como dispositivo médico de alto riesgo (Clase III), lo que implica ensayos de seguridad, eficacia y estudios clínicos controlados antes de su comercialización [19].

#### 2.6 Validación Clínica

Antes de su uso en pacientes reales, el dispositivo debe ser validado en estudios clínicos que demuestren su equivalencia o superioridad frente a incubadoras comerciales certificadas en términos de control térmico, estabilidad hemodinámica del neonato y ausencia de efectos adversos.

#### 2.7 Aspectos de Diseño Industrial

- **Dimensiones y ergonomía** adecuadas para el personal de enfermería y neonatología.
- **Portillos de acceso** con sellos herméticos que no generen corrientes de aire al abrirse.
- **Ruedas con freno** para movilización segura.
- **Diseño eléctrico** con protecciones contra sobretensiones, cortocircuitos y fallas a tierra.

---

### Pregunta 3: ¿Qué semejanzas hay entre una incubadora neonatal y una servo-cuna?

#### 3.1 Definición de Servo-Cuna

Una **servo-cuna** (también llamada cuna de calor radiante o *radiant warmer*) es un dispositivo médico de cama abierta equipado con una fuente de calor radiante ubicada sobre el neonato, que permite un acceso completo al paciente para procedimientos médicos y reanimación [3][10].

#### 3.2 Semejanzas

<div align="center">
  <table>
    <tr>
      <th>Característica</th>
      <th>Incubadora Neonatal</th>
      <th>Servo-Cuna</th>
    </tr>
    <tr>
      <td><b>Objetivo principal</b></td>
      <td>Termorregulación del neonato</td>
      <td>Termorregulación del neonato</td>
    </tr>
    <tr>
      <td><b>Población objetivo</b></td>
      <td>Neonatos prematuros y de bajo peso</td>
      <td>Neonatos en reanimación o procedimientos</td>
    </tr>
    <tr>
      <td><b>Sensor de temperatura cutánea</b></td>
      <td>Sí, termistor adhesivo abdominal</td>
      <td>Sí, termistor adhesivo abdominal</td>
    </tr>
    <tr>
      <td><b>Modo servo-control</b></td>
      <td>Control por temperatura de piel</td>
      <td>Control por temperatura de piel</td>
    </tr>
    <tr>
      <td><b>Modo de control de aire/ambiente</b></td>
      <td>Sí</td>
      <td>No aplica (sistema abierto)</td>
    </tr>
    <tr>
      <td><b>Panel de alarmas</b></td>
      <td>Audibles y visuales</td>
      <td>Audibles y visuales</td>
    </tr>
    <tr>
      <td><b>Monitoreo de signos vitales</b></td>
      <td>Compatible con equipos externos</td>
      <td>Compatible con equipos externos</td>
    </tr>
    <tr>
      <td><b>Norma aplicable</b></td>
      <td>IEC 60601-2-19</td>
      <td>IEC 60601-2-21</td>
    </tr>
    <tr>
      <td><b>Fuente de alimentación</b></td>
      <td>Red eléctrica AC</td>
      <td>Red eléctrica AC</td>
    </tr>
  </table>
</div>

####  3.3 Diferencias Clave

La diferencia fundamental radica en el **mecanismo de transferencia de calor** y en el **tipo de acceso al paciente**:

- La **incubadora** transfiere calor por **convección forzada** (aire caliente circulante), creando un ambiente cerrado que también controla humedad y concentración de gases. Esto la hace más adecuada para el cuidado prolongado de prematuros estables [3][6].

- La **servo-cuna** transfiere calor por **radiación infrarroja** desde una lámpara ubicada encima del neonato. Al ser un sistema abierto, facilita el acceso inmediato para procedimientos de emergencia como intubación, colocación de vías venosas o reanimación cardiopulmonar, pero no controla humedad ni oxígeno de forma efectiva [10].

Algunos fabricantes han desarrollado dispositivos **híbridos** que combinan ambas tecnologías, permitiendo operar tanto en modo incubadora (ambiente cerrado, convección) como en modo servo-cuna (ambiente abierto, radiación), con conversión automática entre configuraciones sin necesidad de trasladar al paciente [2][10].

#### 3.4 Elección Clínica

<div align="center">
  <table>
    <tr>
      <th>Situación clínica</th>
      <th>Dispositivo recomendado</th>
    </tr>
    <tr>
      <td>Neonato prematuro estable en UCIN</td>
      <td>Incubadora neonatal</td>
    </tr>
    <tr>
      <td>Reanimación en sala de partos</td>
      <td>Servo-cuna</td>
    </tr>
    <tr>
      <td>Procedimientos quirúrgicos neonatales</td>
      <td>Servo-cuna</td>
    </tr>
    <tr>
      <td>Transporte intrahospitalario</td>
      <td>Incubadora de traslado (IEC 60601-2-20)</td>
    </tr>
    <tr>
      <td>Cuidado prolongado con acceso frecuente</td>
      <td>Dispositivo híbrido</td>
    </tr>
  </table>
</div>

---



## 5. Referencias

[1] C. G. K. Tran et al., "Designing a low-cost multifunctional infant incubator," *J. Lab. Autom.*, vol. 19, no. 3, pp. 332–337, Jun. 2014. https://doi.org/10.1177/2211068214530391

[2] L. Restrepo-Pérez et al., "Prototipo de incubadora neonatal," *Revista Ingeniería Biomédica*, vol. 1, no. 1, pp. 55–59, 2007. Disponible en: http://www.scielo.org.co/pdf/rinbi/v1n1/v1n1a12.pdf

[3] IEC 60601-2-19:2020, *Medical electrical equipment – Part 2-19: Particular requirements for the basic safety and essential performance of infant incubators*, International Electrotechnical Commission, 2020. Disponible en: https://webstore.iec.ch/en/publication/64023

[4] R. B. Knobel-Dail, "Role of effective thermoregulation in premature neonates," *Research and Reports in Neonatology*, vol. 4, pp. 147–156, 2014. https://doi.org/10.2147/RRN.S52377

[5] EOS Meds, "Incubadora Neonatal," 2021. Disponible en: https://eosmeds.mx/incubadora-neonatal/

[6] Kalstein, "¿Qué es una incubadora neonatal?," 2021. Disponible en: https://kalstein.net/es/que-es-una-incubadora-neonatal/

[7] Apuntes de Electromedicina – Pardell, "Incubadora Neonatal," s.f. Disponible en: https://www.pardell.es/incubadora-neonatal.html

[8] Apuntes de Electromedicina – Pardell, "Curso Incubadoras," s.f. Disponible en: https://www.pardell.es/curso-incubadoras.html

[9] R. Castrillón B. et al., "Diseño e implementación de un prototipo de incubadora neonatal," *Tesis de Grado*, Universidad Politécnica Salesiana, Ecuador, 2012. Disponible en: https://dspace.ups.edu.ec/bitstream/123456789/5091/1/UPS-CT002691.pdf

[10] L. Coelho et al., "Assessment and Certification of Neonatal Incubator Sensors through an Inferential Neural Network," *Sensors*, vol. 13, no. 11, pp. 15613–15632, Nov. 2013. https://doi.org/10.3390/s131115613

[11] RTM Medical, *Digital Infant Incubator – User Manual*, RTM Baby Incubator Products. Disponible en: https://www.scribd.com/document/683022581/Manual-book-Incubator-ENG

[12] Fluke Biomedical, "10 Best Practices for Infant Incubator and Radiant Warmer Testing," Fluke Biomedical Application Note. Disponible en: https://a.flukebiomedical.com/Infant_Incubator_and_Radiant_Warmer_Testing

[13] M. van Leeuwen et al., *European Standards of Care for Newborn Health: Temperature management in newborn infants*, European Foundation for the Care of Newborn Infants (EFCNI), Nov. 2018. Disponible en: https://newborn-health-standards.org/standards/standards-english/care-procedures/temperature-management-in-newborn-infants/
[14] M. van Leeuwen et al., *European Standards of Care for Newborn Health: Temperature management in newborn infants*, EFCNI, Nov. 2018. Disponible en: https://newborn-health-standards.org/standards/standards-english/care-procedures/temperature-management-in-newborn-infants/

[15] L. Restrepo-Pérez et al., "Prototipo de incubadora neonatal," *Revista Ingeniería Biomédica*, vol. 1, no. 1, pp. 55–59, 2007. Disponible en: http://www.scielo.org.co/pdf/rinbi/v1n1/v1n1a12.pdf

[16] IEC 60601-2-19:2020, *Medical electrical equipment – Part 2-19: Particular requirements for the basic safety and essential performance of infant incubators*, IEC, 2020. Disponible en: https://webstore.iec.ch/en/publication/64023

[17] EOS Meds, "Incubadora Neonatal," 2021. Disponible en: https://eosmeds.mx/incubadora-neonatal/

[18] Apuntes de Electromedicina – Pardell, "Incubadora Neonatal," s.f. Disponible en: https://www.pardell.es/incubadora-neonatal.html

[19] Apuntes de Electromedicina – Pardell, "Curso Incubadoras," s.f. Disponible en: https://www.pardell.es/curso-incubadoras.html

[20] RTM Medical, *Digital Infant Incubator – User Manual*. Disponible en: https://www.scribd.com/document/683022581/Manual-book-Incubator-ENG

[21] R. Castrillón B. et al., "Diseño e implementación de un prototipo de incubadora neonatal," *Tesis de Grado*, Universidad Politécnica Salesiana, Ecuador, 2012. Disponible en: https://dspace.ups.edu.ec/bitstream/123456789/5091/1/UPS-CT002691.pdf

[22] INVIMA, "Clasificación de dispositivos médicos," Instituto Nacional de Vigilancia de Medicamentos y Alimentos, Colombia. Disponible en: https://www.invima.gov.co/dispositivos-medicos

[23] Fluke Biomedical, "10 Best Practices for Infant Incubator and Radiant Warmer Testing." Disponible en: https://a.flukebiomedical.com/Infant_Incubator_and_Radiant_Warmer_Testing
---

*Elaborado por: [Salome Ortega Moreno y Santiago Diaz] | Laboratorio de Instrumentación Biomédica y Biosensores | UMNG 2025*
