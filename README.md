# OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA
Repositorio con el desarrollo, cálculos teóricos y simulación de un convertidor Cuk, realizado para la asignatura de Simulacion Electronica del Bachillerato Tecnologico Salesiano Carlos Gomez
# Examen de Regularizacion-Simulacion Electronica

# Alumno
Oscar Eduardo Pérez

# Objetivo del Proyecto

Analizar, simular y diseñar un convertidor Ćuk, verificando experimentalmente mediante simulación en Multisim los resultados obtenidos de forma analítica.

# Problema Asignado

Diseñar y analizar un convertidor Ćuk con los siguientes parámetros:

| Parámetro | Valor |

| Voltaje de entrada (Vg) | 18 V |
| Inductancia L1 | 330 µH |
| Inductancia L2 | 330 µH |
| Capacitor C1 | 100 µF |
| Capacitor C2 | 100 µF |
| Resistencia de carga | 60 Ω |
| Frecuencia de conmutación | 60 kHz |
| Ciclo de trabajo (D) | 0.65 |

# 1. Desarrollo Analítico

Se realizó el análisis matemático completo del convertidor Ćuk ideal:

- Obtención de la relación de conversión.
- Cálculo del voltaje promedio de salida.
- Cálculo de la corriente promedio de salida.
- Cálculo de potencia de salida.
- Cálculo de corriente promedio de entrada.
- Determinación del período de conmutación.
- Cálculo del rizado de corriente en L1 y L2.
- Cálculo de corrientes máximas y mínimas.
- Verificación de operación en modo de conducción continua (MCC).
- Cálculo de voltaje promedio y rizado en los capacitores.
- Cálculo del porcentaje de rizado de salida.

# 2. Simulación en Multisim

Se implementó el convertidor Ćuk utilizando:

- Fuente DC de 18 V.
- MOSFET controlado por PWM.
- Frecuencia de conmutación de 60 kHz.
- Ciclo de trabajo de 65%.
- L1 = 330 µH.
- L2 = 330 µH.
- C1 = 100 µF.
- C2 = 100 µF.
- Resistencia de carga de 60 Ω.

Durante la simulación se verificaron:

- Voltaje de salida.
- Corriente de salida.
- Corriente en L1.
- Corriente en L2.
- Corriente en el MOSFET.
- Corriente en el diodo.
- Voltaje en C1.
- Voltaje en C2.
- Rizado de tensión.
- Rizado de corriente.

Las mediciones se realizaron mediante osciloscopio y cursores.

# 3. Comparación Teoría vs Simulación

Se compararon los resultados teóricos y simulados para determinar el porcentaje de error mediante:

Error (%) = ((Valor Simulado - Valor Teórico) / Valor Teórico) × 100

# Resultados del Convertidor Ćuk — Teoría vs Simulación

| Variable | Símbolo | Teórico | Simulado | Error % |

| Ciclo de trabajo | D | 0.65 | 0.65 | 0.00 % |
| Voltaje de salida | Vo | -33.43 V | -32.6 V | 2.48 % |
| Corriente de salida | Io | 0.557 A | 0.544 A | 2.33 % |
| Potencia de salida | Po | 18.63 W | 17.7 W | 4.99 % |
| Corriente de entrada | Iin | 1.035 A | 1.03 A | 0.48 % |
| Rizo de corriente L1 | ΔiL1 | 0.591 A | 0.590 A | 0.17% |
| Rizo de corriente L2 | ΔiL2 | 0.591 A | 0.590 A | 0.17 % |
| Corriente L1 máxima | iL1,max | 1.330 A | 1.32 A | 0.75 % |
| Corriente L1 mínima | iL1,min | 0.739 A | 0.731 A | 1.08 % |
| Corriente L2 máxima | iL2,max | 0.853 A | 0.839 A | 1.64% |
| Corriente L2 mínima | iL2,min | 0.262 A | 0.249 A | 4.96% |
| Rizo de voltaje C1 | ΔVC1 | 0.060 V | 0.059 V | 1.67 % |
| Rizo de voltaje de salida | ΔVo | 12.3 mV | 12 mV | 2.44% |
| Rizado de salida | %rizo | 0.037 % | 0.37 % | 0.00% |






