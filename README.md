# 📚 Examen de Regularización - Simulación Electrónica y Tecnología y Taller

**Alumno:** Oscar
**Institución:** Bachillerato Tecnológico Salesiano Carlos Gómez
**Fecha de entrega:** Viernes 26 de junio de 2026
**Repositorio compartido con:** @erickmone

---

## 🎯 Objetivo del Proyecto
Analizar, calcular, simular y diseñar un convertidor de corriente continua tipo **Cúk**, cumpliendo con todos los requisitos de análisis teórico, validación por simulación, selección de componentes, diseño de placa de circuito impreso y documentación completa.

---

## ⚙️ Parámetros de Operación
El convertidor funciona bajo las siguientes condiciones asignadas:
- Tensión de entrada: 18 V
- Inductancia de entrada: 330 µH
- Inductancia de salida: 330 µH
- Condensador de transferencia: 100 µF
- Condensador de salida: 100 µF
- Resistencia de carga: 60 Ω
- Frecuencia de conmutación: 60 kHz
- Ciclo de trabajo: 0.65

---

## 📐 Desarrollo Analítico
En la carpeta `Calculos/` se encuentra el documento PDF con todos los procedimientos matemáticos, deducciones y resultados obtenidos. Los valores principales calculados son:

- Relación de conversión: -1.857
- Tensión de salida: -33.43 V (polaridad inversa respecto a la entrada)
- Corriente media de salida: 0.557 A
- Potencia media de salida: 18.62 W
- Corriente media de entrada: 1.034 A
- Periodo de conmutación: 16.67 µs
- Rizado de corriente en ambas inductancias: 0.591 A
- Corrientes máximas y mínimas en cada inductancia
- Rizado de tensión en condensadores
- Modo de operación: **Conducción Continua**, ya que la corriente en las inductancias nunca llega a cero durante el ciclo completo.

---

## 🧪 Simulación en Multisim
Dentro de la carpeta `Simulacion_Multisim/` se guarda el archivo del circuito y todas las capturas de pantalla. La configuración utilizada fue:

- Fuente de alimentación de 18 V
- Señal de control PWM con ciclo de trabajo de 0.65 y frecuencia de 60 kHz
- Componentes con los valores nominales indicados
- Instrumentos de medición: osciloscopio, multímetros y cursores para medir variaciones de tensión y corriente

Se obtuvieron y verificaron las siguientes señales:
- Tensión de salida
- Corrientes en ambas inductancias
- Tensiones en los condensadores
- Corrientes que circulan por el interruptor MOSFET y el diodo
- Valores de rizado de tensión y corriente

---

# 📋 Resultados del Convertidor Tipo Cúk

Comparación entre valores teóricos y resultados de simulación:

| Parámetro                          | Símbolo       | Valor Teórico | Valor Simulado | Unidad | Error (%) |
|------------------------------------|---------------|---------------|----------------|--------|-----------|
| Tensión de entrada                 | Vin           | 18.00         | 18.00          | V      | 0.00 %    |
| Tensión de salida                  | Vo            | -33.43        | -32.70         | V      | 2.18 %    |
| Resistencia de carga               | RL            | 60            | 60             | Ω      | 0.00 %    |
| Frecuencia de conmutación          | f             | 60            | 60             | kHz    | 0.00 %    |
| Ciclo de trabajo                   | D             | 0.65          | 0.65           | —      | 0.00 %    |
| Inductancia bobina 1               | L1            | 330           | 330            | µH     | 0.00 %    |
| Inductancia bobina 2               | L2            | 330           | 330            | µH     | 0.00 %    |
| Capacitor de transferencia         | C1            | 100           | 100            | µF     | 0.00 %    |
| Capacitor de salida                | C2            | 100           | 100            | µF     | 0.00 %    |
| Corriente media en L1              | IL1           | 1.035         | 1.030          | A      | 0.48 %    |
| Corriente media en L2 / salida     | IL2 = Io      | 0.557         | 0.545          | A      | 2.15 %    |
| Rizado de corriente en L1          | ΔiL1          | 0.591         | 0.590          | A      | 0.17 %    |
| Rizado de corriente en L2          | ΔiL2          | 0.591         | 0.590          | A      | 0.17 %    |
| Corriente máxima en L1             | IL1(máx)      | 1.330         | 1.325          | A      | 0.38 %    |
| Corriente mínima en L1             | IL1(mín)      | 0.740         | 0.734          | A      | 0.81 %    |
| Corriente máxima en L2             | IL2(máx)      | 0.853         | 0.840          | A      | 1.52 %    |
| Corriente mínima en L2             | IL2(mín)      | 0.262         | 0.250          | A      | 4.58 %    |
| Rizado de tensión en C1            | ΔVC1          | 60.3          | 59.5           | mV     | 1.33 %    |
| Rizado de tensión en C2 / salida   | ΔVo           | 12.3          | 12.0           | mV     | 2.44 %    |
| Porcentaje de rizado de salida     | % Rizado      | 0.037         | 0.037          | %      | 0.00 %    |
| Modo de operación                  | —             | MCC           | MCC            | —      | —         |

---

✅ Conclusión: Los errores obtenidos son menores al 5 %, lo que confirma una buena coincidencia entre el modelo teórico y la simulación. El convertidor opera en **Modo de Conducción Continua (MCC)**.

---

## 🛠️ Selección y Justificación de Componentes

### 🔹 Transistor MOSFET
**Componente solicitado:** RFD3055LE
- Características: Canal N, Vds = 60 V, Id = 11 A, Rds(on) = 107 mΩ, nivel lógico (enciende con ≥4.5 V), Pd = 40 W.
- **Limitación:** No existe un modelo nativo en las librerías estándar de Multisim.

**Componente base usado en simulación:** IRL540
- Se utilizó como punto de partida por estar disponible y también ser de nivel lógico.
- **Modificación de parámetros:** Para reproducir el comportamiento exacto del RFD3055LE, se ajustaron sus valores en la pestaña *Electronic parameters*:

| Parámetro | Valor original IRL540 | Nuevo valor RFD3055LE |
|-----------|------------------------|-------------------------|
| Vdss      | 100 V                  | **60 V**                |
| Id        | 28 A                   | **11 A**                |
| Rds       | 0.077 Ω                | **0.107 Ω**             |
| Pd        | 150 W                  | **40 W**                |
| gFS       | 12 S                   | **6.5 S**               |

✅ **Razón:** Con estos cambios, el modelo refleja los límites eléctricos y características reales del componente solicitado.

---

### 🔹 Driver de Compuerta
**Componente:** Circuito de excitación mediante generador de funciones PWM
- **Señal de control:** Amplitud de 5 V, frecuencia de 60 kHz, ciclo de trabajo 65 %.
- **Justificación:** El RFD3055LE y el modelo ajustado operan con **nivel lógico**, por lo que 5 V son suficientes para encenderlo completamente sin necesidad de amplificación adicional.
- Si se usara un MOSFET de nivel estándar (como el IRF540N), se requeriría un driver externo para elevar la tensión de compuerta a 10–12 V. En este diseño no es necesario, lo que simplifica el circuito.

---

### 🔹 Diodo
**Componente:** MUR460G
- Características: Diodo de recuperación ultrarrápida, 4 A, 600 V.
- ✅ **Razón:** Soporta la tensión y corriente del circuito con amplio margen; su tiempo de conmutación reducido minimiza pérdidas a 60 kHz.

---

### 🔹 Inductancias
**Valor calculado:** 330 µH
**Usado en simulación:** L1 = 330 µH, L2 = 330 µH
- ✅ **Razón:** Es mayor que la inductancia crítica calculada (214.4 µH), garantizando operación en **Modo de Conducción Continua** y manteniendo el rizado de corriente en Δi = 0.59 A.

---

### 🔹 Capacitores
- **C1 = 100 µF:** Capacitor de transferencia de energía. Limita el rizado de tensión a ~60.3 mV.
- **C2 = 100 µF:** Capacitor de salida. Obtiene un rizado de tensión de solo 12.3 mV (0.037 % del valor nominal).
- ✅ **Razón:** Cumplen con los requisitos de filtrado y estabilidad calculados.

---

### 🔹 Resistencia de Carga
**Valor:** R1 = 60 Ω
- ✅ **Razón:** Permite obtener la corriente de salida deseada según Ley de Ohm: Io = |Vo| / R = 33.43 V / 60 Ω = 0.557 A.




