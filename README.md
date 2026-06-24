# 📚 Examen de Regularización - Simulación Electrónica y Tecnología y Taller
**Alumno:** Oscar
**Institución:** Bachillerato Tecnológico Salesiano Carlos Gómez
**Fecha de entrega:** Viernes 26 de junio de 2026
**Repositorio compartido con:** @erickmone

---

## 🎯 Objetivo del Proyecto
Analizar, calcular, simular y diseñar un convertidor CC-CC tipo Cúk bajo condiciones de funcionamiento definidas, cumpliendo con los requisitos de análisis teórico, validación por simulación, selección de componentes, diseño de placa de circuito impreso (PCB) y documentación completa.

---

## ⚙️ Parámetros de Operación
El convertidor trabaja con los siguientes valores:
- Tensión de entrada: \( V_G = 18\ \text{V} \)
- Inductancias: \( L_1 = 330\ \mu\text{H} \), \( L_2 = 330\ \mu\text{H} \)
- Condensadores: \( C_1 = 100\ \mu\text{F} \), \( C_2 = 100\ \mu\text{F} \)
- Resistencia de carga: \( R = 60\ \Omega \)
- Frecuencia de conmutación: \( f_s = 60\ \text{kHz} \)
- Ciclo de trabajo: \( D = 0.65 \)

---

## 📐 Desarrollo Analítico
Todos los cálculos algebraicos y resultados se detallan en la carpeta `Calculos/` en formato PDF. A continuación se resumen los resultados principales:

### 1. Relación de conversión
\[
\frac{V_O}{V_G} = -\frac{D}{1-D} = -\frac{0.65}{1-0.65} = -1.857
\]

### 2. Tensión de salida
\[
V_O = V_G \cdot \left(-\frac{D}{1-D}\right) = 18 \cdot (-1.857) = -33.43\ \text{V}
\]
*Polaridad: Inversa respecto a la entrada*

### 3. Corriente media de salida
\[
I_O = \frac{|V_O|}{R} = \frac{33.43}{60} = 0.557\ \text{A}
\]

### 4. Potencia media de salida
\[
P_O = |V_O| \cdot I_O = 33.43 \cdot 0.557 = 18.62\ \text{W}
\]

### 5. Corriente media de entrada
\[
I_{in} = \frac{P_O}{V_G} = \frac{18.62}{18} = 1.034\ \text{A}
\]

### 6. Periodo de conmutación
\[
T_s = \frac{1}{f_s} = \frac{1}{60000} = 16.67\ \mu\text{s}
\]

### 7. Rizado de corriente en inductancias
\[
\Delta i_{L1} = \frac{V_G \cdot D}{L_1 \cdot f_s} = \frac{18 \cdot 0.65}{330\times10^{-6} \cdot 60000} = 0.591\ \text{A}
\]
\[
\Delta i_{L2} = \frac{|V_O| \cdot (1-D)}{L_2 \cdot f_s} = \frac{33.43 \cdot 0.35}{330\times10^{-6} \cdot 60000} = 0.591\ \text{A}
\]

### 8. Corrientes máximas y mínimas
- **Inductancia \( L_1 \):**
  \[
  i_{L1,\text{max}} = I_{in} + \frac{\Delta i_{L1}}{2} = 1.034 + 0.295 = 1.329\ \text{A}
  \]
  \[
  i_{L1,\text{min}} = I_{in} - \frac{\Delta i_{L1}}{2} = 1.034 - 0.295 = 0.739\ \text{A}
  \]
- **Inductancia \( L_2 \):**
  \[
  i_{L2,\text{max}} = I_O + \frac{\Delta i_{L2}}{2} = 0.557 + 0.295 = 0.852\ \text{A}
  \]
  \[
  i_{L2,\text{min}} = I_O - \frac{\Delta i_{L2}}{2} = 0.557 - 0.295 = 0.262\ \text{A}
  \]

✅ **Modo de operación:** Ambas inductancias mantienen corriente positiva en todo el ciclo → **Conducción Continua (MCC)**

### 9. Rizado de tensión en condensadores
\[
\Delta V_{C1} = \frac{I_O \cdot D}{C_1 \cdot f_s} = \frac{0.557 \cdot 0.65}{100\times10^{-6} \cdot 60000} = 0.060\ \text{V}
\]
\[
\Delta V_{C2} = \frac{I_O \cdot (1-D)}{C_2 \cdot f_s} = \frac{0.557 \cdot 0.35}{100\times10^{-6} \cdot 60000} = 0.032\ \text{V}
\]
\[
\text{Rizado relativo de salida} = \frac{\Delta V_O}{|V_O|} \times 100 = \frac{0.032}{33.43} \times 100 = 0.096\%
\]

---

## 🧪 Simulación en Multisim
El circuito completo se encuentra en la carpeta `Simulacion_Multisim/`. Se configuró con:
- Fuente de 18 V
- Generador PWM: \( D=0.65 \), \( f_s=60\ \text{kHz} \)
- Componentes con los valores nominales indicados
- Instrumentos: osciloscopio, multímetros y cursores de medición

### Señales validadas:
- Tensión de salida \( v_O(t) \)
- Corrientes en \( L_1 \) y \( L_2 \)
- Tensiones en \( C_1 \) y \( C_2 \)
- Corrientes por MOSFET y diodo
- Medición directa de rizados de corriente y tensión

---

## 📊 Comparación Teoría vs Simulación
| Variable       | Valor Teórico | Valor Simulado | Error (%) |
|----------------|---------------|----------------|-----------|
| \( V_O \)      | -33.43 V      | -33.26 V       | 0.51%     |
| \( I_O \)      | 0.557 A       | 0.554 A        | 0.54%     |
| \( \Delta i_{L1} \) | 0.591 A | 0.590 A | 0.17% |
| \( \Delta i_{L2} \) | 0.591 A | 0.590 A | 0.17% |
| \( \Delta V_{C1} \) | 0.060 V | 0.058 V | 3.33% |
| \( \Delta V_{C2} \) | 0.032 V | 0.031 V | 3.12% |
| Rizado (%)     | 0.096%        | 0.093%         | 3.12%     |

✅ Los resultados coinciden con desviaciones menores al 5%, debidas a pérdidas parásitas y redondeo numérico.

---

## 📄 Selección de Componentes
Se consultaron las hojas técnicas de todos los elementos, disponibles en la carpeta `Datasheets/`:
- **MOSFET:** RFD3055LE → 60 V, 12 A, baja resistencia de encendido, adecuado para 60 kHz
- **Driver:** NCP81253 → 5 V de alimentación, salida suficiente para conmutar el MOSFET
- **Diodo:** Schottky 45 V / 5 A → baja caída de tensión directa
- **Inductancias:** 330 µH, corriente nominal ≥ 2 A → soportan la corriente máxima con margen
- **Condensadores:** Electrolíticos 100 µF / 50 V → tensión nominal mayor a la máxima de operación








