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

  <img width="918" height="591" alt="image" src="https://github.com/user-attachments/assets/86f4ba14-9a1f-4f7c-ac53-5d582a083df9" />height="400" alt="image">

</p>


### 5. Referencias

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

---

*Elaborado por: [Nombre del estudiante] | Laboratorio de Instrumentación Biomédica y Biosensores | UMNG 2025*
