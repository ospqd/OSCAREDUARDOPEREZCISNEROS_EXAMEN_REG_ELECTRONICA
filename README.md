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

## 📊 Comparación: Teoría vs Simulación
Se elaboró una tabla comparativa para verificar la coincidencia entre los resultados teóricos y los valores medidos en la simulación, calculando el porcentaje de error para cada magnitud:

| Variable               | Valor Teórico | Valor Simulado | Error (%) |
|------------------------|---------------|----------------|-----------|
| Tensión de salida      | -33.43 V      | -33.26 V       | 0.51 %    |
| Corriente de salida    | 0.557 A       | 0.554 A        | 0.54 %    |
| Corriente de entrada   | 1.034 A       | 1.027 A        | 0.68 %    |
| Rizado en L1           | 0.591 A       | 0.590 A        | 0.17 %    |
| Rizado en L2           | 0.591 A       | 0.590 A        | 0.17 %    |
| Rizado en C1           | 0.060 V       | 0.058 V        | 3.33 %    |
| Rizado en C2           | 0.032 V       | 0.031 V        | 3.13 %    |
| Porcentaje de rizado   | 0.096 %       | 0.093 %        | 3.13 %    |

Todos los errores son menores al 5%, valor aceptable. Las pequeñas diferencias se explican por pérdidas en los componentes, parásitos del circuito y redondeo de valores.

---

## 📄 Selección de Componentes
Se consultaron y analizaron las hojas técnicas de todos los elementos utilizados, disponibles en la carpeta `Datasheets/`. La selección se justifica así:

- **MOSFET RFD3055LE:** Soporta tensión y corriente suficientes, con baja resistencia de encendido, adecuado para la frecuencia de trabajo.
- **Driver NCP81253:** Diseñado para manejar señales de control de compuerta con alimentación de 5 V, ideal para conmutar el MOSFET correctamente.
- **Diodo:** Tipo Schottky, con tensión y corriente nominales superiores a los valores máximos de operación.
- **Inductancias:** Valor de 330 µH, con corriente nominal superior a la máxima que circula en el circuito.
- **Condensadores:** Valor de 100 µF y tensión nominal mayor a la máxima que se presenta en el circuito.



