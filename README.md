# 📡 Indy Open LoRa

### APRS VHF + LoRa 433 MHz + APRS-IS

![Indy Open LoRa Concept](./indy-open-lora-concept.png)

**Indy Open LoRa** es un proyecto abierto de la familia **Indy Open** pensado para unir dos mundos de la radioafición en un mismo sistema:

- 📻 **APRS tradicional en VHF 144.390 MHz**
- 📡 **LoRa en 433 MHz**
- 🌐 **Conectividad con APRS-IS mediante Wi-Fi**

La idea es desarrollar una plataforma híbrida basada en una **TNC Indy Open** y una placa **LILYGO ESP32 LoRa**, capaz de recibir, procesar, visualizar y compartir información tanto desde APRS convencional como desde nodos LoRa.

> [!IMPORTANT]
> ## 🚧 PROYECTO EN DESARROLLO
>
> **Indy Open LoRa se encuentra actualmente en desarrollo activo.**
>
> Las características, funciones, hardware, pantallas, modos de operación y especificaciones descritas en este repositorio representan la visión actual del proyecto.
>
> ⚠️ **Las funcionalidades pueden cambiar, añadirse, modificarse o eliminarse durante el proceso de desarrollo y pruebas.**
>
> Algunas funciones mostradas en imágenes, diagramas o material promocional son conceptos previstos y **pueden no estar implementadas todavía**.

---

## 💡 La idea

Queremos crear un equipo que permita trabajar al mismo tiempo con APRS convencional y LoRa.

De forma sencilla:

```text
Radio VHF 144.390 MHz
        │
        ▼
   Indy Open TNC
        │
        ▼
 LILYGO ESP32 LoRa
     │         │
     │         └──── LoRa 433 MHz
     │
     └────────────── APRS-IS
                     por Wi-Fi
```

La TNC se encargará del mundo APRS / AX.25 en VHF, mientras que la LILYGO ESP32 gestionará LoRa 433 MHz, la conexión a Internet, la interfaz, los registros y el intercambio de información con APRS-IS.

---

## 🔧 Hardware previsto

El proyecto contempla una pequeña PCB propia que podrá integrar:

- Indy Open TNC
- Audio de entrada y salida hacia el radio
- PTT
- Conectores hacia el equipo VHF
- Potenciómetro digital para ajuste de nivel
- Conexión UART hacia la LILYGO ESP32
- Alimentación y protecciones
- Conectores modulares para facilitar pruebas y futuras versiones

La intención es que esta placa pueda utilizarse con diferentes modelos compatibles de **LILYGO ESP32 LoRa**, evitando depender de una sola versión de hardware.

---

## 📻 APRS VHF

La parte APRS utilizará un radio VHF convencional trabajando en **144.390 MHz**, conectado a la Indy Open TNC.

El objetivo es poder:

- Recibir tramas APRS
- Procesar AX.25
- Enviar información hacia APRS-IS
- Mostrar actividad y estado
- Registrar eventos y estadísticas
- Aprovechar futuras funciones de ajuste automático de audio

---

## 📡 LoRa 433 MHz

La LILYGO añadirá un segundo enlace de radio mediante **LoRa 433 MHz**.

Esto permitirá explorar funciones como:

- Comunicación entre nodos Indy Open
- Mensajería entre radioaficionados
- Telemetría
- Trackers
- Balizas
- Información de sensores
- RSSI y SNR
- Enlaces de experimentación de largo alcance y bajo consumo

---

## 🌐 APRS-IS

El ESP32 podrá utilizar Wi-Fi para conectarse a APRS-IS.

Uno de los objetivos principales es que el sistema pueda actuar como puente entre:

```text
APRS VHF
   ↕
Indy Open LoRa
   ↕
APRS-IS
```

y también:

```text
LoRa 433 MHz
   ↕
Indy Open LoRa
   ↕
APRS-IS
```

El comportamiento final del gateway y las reglas de encaminamiento se definirán durante el desarrollo y las pruebas.

---

## 🚀 Modos que queremos explorar

### 🛰️ Gateway

Equipo fijo capaz de trabajar con:

**APRS VHF + LoRa 433 MHz + APRS-IS**

### 📍 Tracker

Nodo LoRa capaz de enviar posición, telemetría y otros datos.

### 💬 Messenger

Mensajería directa entre dispositivos Indy Open mediante LoRa.

La intención es que **Indy Open LoRa Messenger** pueda comunicarse también con **Indy Open HamWatch** utilizando un protocolo común.

### 🦊 Fox Hunt

Experimentación con balizas LoRa, RSSI/SNR y búsqueda de transmisores.

---

## 💬 Indy Open Messenger

Queremos desarrollar un protocolo abierto de mensajería para que distintos dispositivos de la familia Indy Open puedan comunicarse.

Ejemplo:

```text
Indy Open LoRa
      │
      │ LoRa 433 MHz
      ▼
Indy Open HamWatch
```

También:

```text
LILYGO LoRa
      │
      ▼
Gateway Indy Open
      │
      ▼
Otro nodo LoRa
```

El protocolo podrá evolucionar para transportar:

- Indicativo
- Mensajes
- Posición
- Telemetría
- Batería
- RSSI
- SNR
- Estado del nodo

---

## 🖥️ Firmware

Además del hardware, desarrollaremos un firmware específico para la LILYGO ESP32.

Entre las funciones previstas:

- Configuración Wi-Fi
- APRS-IS
- Control y comunicación con la TNC
- LoRa 433 MHz
- Messenger
- Monitor de estaciones
- Registro de actividad
- Pantalla OLED
- Tarjeta SD, cuando el hardware lo permita
- Actualización de firmware
- Interfaz web
- Estadísticas
- Herramientas de diagnóstico

---

## 🌎 Parte de la familia Indy Open

Indy Open LoRa forma parte de:

- 📡 **Indy Open APRS**
- 🔧 **Indy Open TNC**
- 📻 **Indy Open LoRa**
- ⌚ **Indy Open HamWatch**

Todos comparten la misma idea:

**crear herramientas abiertas para experimentar, aprender, modificar y aportar nuevas ideas a la comunidad radioaficionada.**

---

## 🧪 Estado del proyecto

🚧 **EN DESARROLLO ACTIVO**

Actualmente estamos trabajando en la definición de:

- Arquitectura general
- PCB para TNC e interfaz con radio
- Integración con LILYGO ESP32
- Comunicación entre TNC y ESP32
- LoRa 433 MHz
- Protocolo Indy Open LoRa
- Messenger
- Integración APRS-IS
- Interfaz web
- Pantallas y experiencia de usuario

### ⚠️ Importante

**Las funcionalidades finales pueden variar conforme avance el desarrollo.**

Durante las pruebas algunas características pueden ser modificadas, sustituidas, ampliadas o descartadas.

Las imágenes y diagramas publicados deben considerarse **conceptos de diseño** y no necesariamente representan el hardware o firmware final.

---

## ⭐ Sigue el proyecto

Si te interesa Indy Open LoRa:

- ⭐ Dale una **Star** al repositorio
- 👀 Usa **Watch** para recibir actualizaciones
- 🍴 Haz **Fork** si quieres experimentar
- 💡 Comparte ideas y sugerencias
- 🐛 Reporta errores
- 🤝 Colabora con código, pruebas o documentación

Cada aportación ayuda a que el proyecto siga creciendo.

---

## ☕ Apoya el proyecto

Indy Open es un proyecto comunitario desarrollado por interés en la radioafición, la experimentación y el hardware/software abierto.

Si quieres ayudar a continuar desarrollando placas, probando hardware y creando nuevas funciones, podrás apoyar voluntariamente el proyecto.

❤️ **Las donaciones son completamente opcionales.**

**Próximamente añadiremos aquí las opciones disponibles para apoyar el desarrollo.**

---

## ⚠️ Aviso

Este proyecto tiene fines educativos y experimentales relacionados con la radioafición.

El usuario es responsable de operar cualquier transmisor respetando la legislación aplicable, las frecuencias autorizadas, los límites de potencia y las condiciones correspondientes a su licencia.

---

## 📜 Open Source

Indy Open LoRa nace con la intención de ser un proyecto abierto.

Queremos que cualquier radioaficionado pueda:

**aprender → experimentar → modificar → mejorar → compartir**

---

## 📡 Indy Open

### Innovación abierta para la comunidad radioaficionada.

**Tu radio. Tu red. Tu proyecto.**
