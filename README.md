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

## 📄 Selección de Componentes
Se consultaron y analizaron las hojas técnicas de todos los elementos utilizados, disponibles en la carpeta `Datasheets/`. La selección se justifica así:

- **MOSFET RFD3055LE:** Soporta tensión y corriente suficientes, con baja resistencia de encendido, adecuado para la frecuencia de trabajo.
- **Driver NCP81253:** Diseñado para manejar señales de control de compuerta con alimentación de 5 V, ideal para conmutar el MOSFET correctamente.
- **Diodo:** Tipo Schottky, con tensión y corriente nominales superiores a los valores máximos de operación.
- **Inductancias:** Valor de 330 µH, con corriente nominal superior a la máxima que circula en el circuito.
- **Condensadores:** Valor de 100 µF y tensión nominal mayor a la máxima que se presenta en el circuito.



