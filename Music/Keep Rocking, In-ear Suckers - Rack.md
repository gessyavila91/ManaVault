
### 1. **KRIS**
**K**riSys **R**ack for **I**nfinite **S**tages
### 2. **KRIS**
**K**riSys **R**ig of **I**llogical **S**olutions
### 3. **KRIS**
**K**riSys **R**ack for **I**nfinite **S**ound
### 4. **KRIS**
**K**riSys **R**ack for **I**ntegrated **S**onics
### 5. **KRIS**
**K**riSys **R**ack for **I**ntelligent **S**treaming
### 6. **KRIS**
**K**riSys **R**ockin’ with **I**ll-advised **S**cience 


# 🎚 Patch List y Stage Plot - Banda

Documento técnico para administrar las **entradas y salidas** de audio de la banda, organizado por músicos y con esquema de colores y TAGS para facilitar el cableado, etiquetado y monitoreo.

---

## 📑 Índice de TAGS

- **V** → Vocal
- **G** → Guitarra
- **B** → Bajo
- **D** → Drum (Batería)
    - **DK** → Kick
    - **DS** → Snare
    - **DOHL** → Overhead Left
    - **DOHR** → Overhead Right
- **K** → Keyboard (auxiliar / futuro músico adicional)
- **IEM** → In Ear Monitor (salida personal)
    
---

## 🎨 Colores por Persona

- 🟥 **Guicho** → Voz (V1) + G2
- 🟩 **Kevin** → Lead Guitar (G1)
- 🟦 **Getse** → Bass (B1)
- 🟨 **Pako** → Drums (DK, DS, DOHL, DOHR)
- 🟪 **Auxiliar** → Keyboard (K1, K2)

---

## 🎚 Asignación de Canales y TAGS (Inputs)

|Canal|TAG|Músico / Instrumento|Fuente / Salida|Color|Observaciones|
|---|---|---|---|---|---|
|1|V1|Guicho (Voz Principal)|Micrófono XLR|🟥|Vocal principal|
|2|G1|Kevin (Lead Guitar)|Pedalera XLR / DI|🟩|Lead|
|3|G2|Guicho (Rythm Guitar)|Pedalera XLR / DI|🟥|Rythm|
|4|B1|Getse (Bass)|Pedalera XLR / DI|🟦|Bajo directo|
|5|DK|Pako (Kick)|Mic dinámico XLR|🟨|Bombo|
|6|DS|Pako (Snare)|Mic dinámico XLR|🟨|Tarola|
|7|DOHL|Pako (Overhead L)|Mic condensador XLR|🟨|Overhead Izquierdo|
|8|DOHR|Pako (Overhead R)|Mic condensador XLR|🟨|Overhead Derecho|
|9|K1|Aux (Keyboard L)|Línea ¼”/XLR|🟪|Opcional|
|10|K2|Aux (Keyboard R)|Línea ¼”/XLR|🟪|Opcional|

---

## 🎧 Asignación de Salidas IEM (OUTs)

Cada salida de la mixer va a un **IEM Transmitter o Amp**.

|Out|TAG|Músico|Mixer Out|Amp/Transmisor|Color|
|---|---|---|---|---|---|
|O1|IEM1|🟥 Guicho (Voz+G2)|Aux Out 1|IEM TX Guicho|🟥|
|O2|IEM2|🟩 Kevin (G1)|Aux Out 2|IEM TX Kevin|🟩|
|O3|IEM3|🟦 Getse (Bajo)|Aux Out 3|IEM TX Getse|🟦|
|O4|IEM4|🟨 Pako (Drums)|Aux Out 4|IEM TX Pako|🟨|
|O5|IEM5|🟪 Aux (Keyboard)|Aux Out 5|IEM TX Aux|🟪|

---

## 🏷 Lista de Cables IEM (Etiquetas en ambas puntas)

Cada cable de salida tiene dos etiquetas:
- **Mixer Side** → Canal de salida.    
- **Amp Side** → IEM correspondiente.

|Cable|Mixer Side (OUT)|Amp Side (IEM)|TAG|Color|
|---|---|---|---|---|
|C11|🟥 Aux Out 1 (Guicho)|🟥 IEM Amp Guicho (TX)|IEM1|🟥|
|C12|🟩 Aux Out 2 (Kevin)|🟩 IEM Amp Kevin (TX)|IEM2|🟩|
|C13|🟦 Aux Out 3 (Getse)|🟦 IEM Amp Getse (TX)|IEM3|🟦|
|C14|🟨 Aux Out 4 (Pako)|🟨 IEM Amp Pako (TX)|IEM4|🟨|
|C15|🟪 Aux Out 5 (Aux)|🟪 IEM Amp Aux Keyboard|IEM5|🟪|

👉 Ejemplo Cable C11:
- Lado Mixer → `🟥 OUT1 - Guicho`
- Lado Amp → `🟥 IEM Guicho`

---

## 🏷 Etiquetas para Puertos de Mixer (OUTs)

|Puerto|Etiqueta sugerida|Color|
|---|---|---|
|Out 1|`🟥 OUT1 - IEM Guicho`|🟥|
|Out 2|`🟩 OUT2 - IEM Kevin`|🟩|
|Out 3|`🟦 OUT3 - IEM Getse`|🟦|
|Out 4|`🟨 OUT4 - IEM Pako`|🟨|
|Out 5|`🟪 OUT5 - IEM Aux Keyboard`|🟪|

---

## 🏷 Etiquetas para Amp/Transmisor IEM

Cada **amp o transmisor** debe tener etiqueta fija con nombre y color.

- 🟥 `IEM GUICHO (Voz+G2)`
- 🟩 `IEM KEVIN (Lead G1)`
- 🟦 `IEM GETSE (Bass)`
- 🟨 `IEM PAKO (Drums)`
- 🟪 `IEM AUX (Keyboard)`
    

---

## 📦 Buenas Prácticas de Etiquetado

- **Inputs**: TAG + color en ambos extremos.
- **Outputs IEM**: Etiquetas iguales (Mixer OUT ↔ IEM Amp).
- **Puertos fijos** (mixer/snake) → Etiquetas permanentes.
- **Transmisores/Amp IEM** → Etiqueta grande visible (nombre + color).
- **Backups**: tener al menos 1 cable spare para OUT IEM y 1 DI Box extra.
    

---

## 📂 Histórico de Cambios

- **v1.0** → Primera versión con TAGS, colores y stage plot.
- **v1.1** → Adición de Keyboard auxiliar (🟪).
- **v1.2** → Expansión Drum con sub-TAGs (DK, DS, DOHL, DOHR).
- **v1.3** → Inclusión de lista completa de **cables IN/OUT y puertos mixer**.
- **v1.4** → Inclusión de **salidas IEM, cables OUT y branding en amps/transmisores**.