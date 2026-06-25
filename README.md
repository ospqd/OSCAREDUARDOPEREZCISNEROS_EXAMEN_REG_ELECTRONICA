# 📚 Examen de Regularización - Simulación Electrónica
# 📁 OSCAR_PEREZ_EXAMEN_REG_ELECTRONICA
-**Examen de Regularización**
-**Materia:** Simulación Electrónica 
-**Institución:** Bachillerato Tecnológico Salesiano Carlos Gómez
-**Alumno:** Oscar Eduardo Pérez Cisneros
-**Fecha de elaboración:** 24 de junio de 2026
-**Fecha de entrega:** Viernes 26 de junio de 2026
-**Repositorio compartido con:** @erickmone

---

## 🎯 Objetivo del Proyecto
Realizar el análisis teórico, simulación, validación de resultados, selección de componentes y documentación completa de un convertidor CC-CC tipo Cúk,

---
## Problema asignado

**Diseñar y analizar un convertidor Ćuk con los siguientes parámetros:**

El convertidor funciona bajo las siguientes condiciones:
- Tensión de entrada: 18 V
- Inductancias: 330 µH
- Condensadores: 100 µF
- Resistencia de carga: 60 Ω
- Frecuencia de conmutación: 60 kHz
- Ciclo de trabajo: 0.65

---
## Metodología utilizada

## 1. Desarrollo Analítico
✅ Obtener la relación de conversión, calcular tensiones, corrientes, rizados, valores máximos y mínimos, y determinar el modo de operación.

✅ **Pasos realizados:**
1. Se obtuvo la relación de conversión del convertidor, comprobando que entrega una tensión de salida con polaridad inversa respecto a la tensión de entrada.
2. Se calculó el valor promedio de la tensión de salida y se indicó claramente su polaridad negativa.
3. Se determinó la corriente promedio que circula por la carga y la potencia que entrega el circuito.
4. Se calculó la corriente promedio que consume el convertidor desde la fuente de alimentación.
5. Se halló el periodo de conmutación correspondiente a la frecuencia de trabajo definida.
6. Se calculó la variación de corriente (rizado) en cada una de las dos inductancias.
7. Se obtuvieron los valores máximos y mínimos de corriente que circulan en cada inductancia durante un ciclo completo.
8. Se verificó que en todo momento la corriente se mantiene positiva → funcionamiento en Modo de Conducción Continua (MCC).
9. Se calculó la variación de tensión (rizado) en el condensador de transferencia y en el condensador de salida.
10. Se determinó el porcentaje de rizado total en la tensión de salida.

#Calculos
-[PDF](https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/c5e9364d775b1ad501865425b37fe17e9e66a2be/Calculos.pdf)



---
## 2. Simulación en Multisim
✅ Construir el circuito, configurar parámetros, medir todas las magnitudes y guardar capturas de señales e instrumentos.

✅ **Pasos realizados:**
1. Se dibujó el esquema completo del convertidor: fuente de 18 V, interruptor MOSFET, diodo, dos inductancias, dos condensadores y resistencia de carga.
2. Se configuró la señal de control: ciclo de trabajo de 0.65 y frecuencia de conmutación de 60 kHz.
3. Se conectaron los instrumentos de medición: osciloscopio, multímetros y cursores para medir variaciones de tensión y corriente.
4. Se ejecutó la simulación hasta alcanzar el estado de funcionamiento estable.
5. Se midieron y registraron todos los valores: tensión de salida, corrientes en inductancias, tensiones en condensadores, corrientes por el MOSFET y el diodo, así como los valores de rizado.
6. Se capturaron todas las pantallas: esquema del circuito, señales de control, formas de onda de tensión y corriente, y mediciones realizadas con los instrumentos.
   
📋 **Descripción de Componentes Usados**
### MOSFET de potencia
- **Modelo utilizado en simulación:** IRF540

### Diodo de conmutación
- **Modelo:** MUR460G
- **Características:** Diodo de recuperación rápida, soporta 600 V de tensión inversa y 4 A de corriente máxima.

### Inductancias
- **Valor:** 330 µH
- **Justificación:** Es el valor asignado, suficiente para mantener el modo de conducción continua y limitar el rizado de corriente.

### Condensadores
- **Valor:** 100 µF
- **Justificación:** Permiten transferir energía entre entrada y salida, además de filtrar la tensión final para obtener un rizado muy bajo.

---

## Esquemático completo
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Esquematico%20completo%20con%20parametros%20de%20simulacion.png?raw=true" alt="Esquemático completo" width="600">

✅ **Explicación:** Se observa la configuración típica del convertidor Cúk, con el MOSFET IRF540 como elemento de conmutación, el diodo MUR460G, las dos inductancias de 330 µH, los condensadores de 100 µF y la resistencia de carga de 60 Ω.

---

## Señal PWM aplicada al MOSFET
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Se%C3%B1al%20PWM%20aplicada%20al%20MOSFET.png?raw=true" alt="Señal PWM" width="550">

✅ **Explicación:** Onda cuadrada de 60 kHz y ciclo de trabajo del 65 %, encargada de activar y desactivar el IRF540 para regular la tensión de salida.

---

## Tensión de Salida
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Tension%20de%20Salida.png?raw=true" alt="Tensión de salida Vo" width="550">

✅ **Explicación:** Valor medio estable de aproximadamente -32.6 V, con polaridad inversa respecto a la entrada, tal como se espera en este tipo de convertidor.

---

## Corriente en L1
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20en%20L1.png?raw=true" alt="Forma de onda corriente L1" width="520">
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20en%20L1%20Amperimetro.png?raw=true" alt="Medición amperímetro L1" width="520">

✅ **Explicación:** Corriente continua con pequeña variación, siempre positiva → confirma operación en modo continuo.

---

## Corriente en L2
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20en%20L2.png?raw=true" alt="Forma de onda corriente L2" width="520">
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20en%20L2%20Amperimetro.png?raw=true" alt="Medición amperímetro L2" width="520">

✅ **Explicación:** Comportamiento similar a L1, manteniéndose siempre por encima de cero.

---

## Tensión en C1
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Tension%20delC1%20tecktronix.png?raw=true" alt="Tensión en capacitor C1" width="520">

✅ **Explicación:** Capacitor encargado de transferir la energía entre la entrada y la salida del circuito.

---

## Tensión en C2
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Tension%20del%20C2%20Tectronix.png?raw=true" alt="Forma de onda tensión C2" width="520">
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Tension%20del%20C2%20multimetro.png?raw=true" alt="Medición multímetro C2" width="520">

✅ **Explicación:** Filtra la tensión final, reduciendo su variación a valores muy bajos.

---

## Corriente en el MOSFET IRF540
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20en%20el%20MOSFET.png?raw=true" alt="Forma de onda corriente MOSFET" width="520">
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20del%20MOSFET%20Amperimetro.png?raw=true" alt="Medición amperímetro MOSFET" width="520">

✅ **Explicación:** Circula únicamente durante el tiempo en que el transistor está activado, con valores muy por debajo de su límite máximo.

---

## Corriente en el diodo
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20del%20diodo.png?raw=true" alt="Forma de onda corriente diodo" width="520">
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Corriente%20del%20diodo%20Amperimetro.png?raw=true" alt="Medición amperímetro diodo" width="520">

✅ **Explicación:** Conduce cuando el MOSFET está apagado, completando el ciclo de transferencia de energía.

---

## Rizado de tensión usando cursores
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Rizado%20de%20tension%20usando%20cursores.png?raw=true" alt="Medición rizado de tensión" width="520">

✅ **Explicación:** Variación de solo 12 mV, lo que representa menos del 0.04 % respecto al valor medio.

---

## Rizado de corriente usando cursores
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/main/Evidencias/Rizado%20de%20corriente%20usando%20cursores.png?raw=true" alt="Medición rizado de corriente" width="520">

✅ **Explicación:** Confirma que la corriente no se anula en ningún momento, manteniendo el modo de conducción continua.

---






---

## 3. Comparación: Teoría vs Simulación
✅ Elaborar tabla comparativa, calcular el porcentaje de error y justificar las diferencias entre valores teóricos y simulados.

✅ **Tabla de resultados:**

| Variable               | Valor teórico | Valor simulado | Error (%) |
|------------------------|---------------|----------------|-----------|
| Ciclo de trabajo D     | 0.65          | 0.65           | 0.00 %    |
| Tensión de salida Vo   | -33.43 V      | -32.6 V        | 2.48 %    |
| Corriente de salida Io | 0.557 A       | 0.544 A        | 2.33 %    |
| Potencia de salida Po  | 18.63 W       | 17.7 W         | 4.99 %    |
| Corriente de entrada Iin | 1.035 A    | 1.03 A         | 0.48 %    |
| Rizado de corriente L1 ΔiL1 | 0.591 A | 0.590 A | 0.17 % |
| Rizado de corriente L2 ΔiL2 | 0.591 A | 0.590 A | 0.17 % |
| Corriente máxima L1 iL1,máx | 1.330 A | 1.32 A | 0.75 % |
| Corriente mínima L1 iL1,mín | 0.739 A | 0.731 A | 1.08 % |
| Corriente máxima L2 iL2,máx | 0.853 A | 0.839 A | 1.64 % |
| Corriente mínima L2 iL2,mín | 0.262 A | 0.249 A | 4.96 % |
| Rizado de tensión C1 ΔVC1 | 0.060 V | 0.059 V | 1.67 % |
| Rizado de tensión de salida ΔVo | 12.3 mV | 12.0 mV | 2.44 % |
| Porcentaje de rizado de salida | 0.037 % | 0.036 % | 2.70 % |

✅ Todos los errores son menores al 5%, por lo que se consideran aceptables. Las pequeñas diferencias se explican porque el modelo teórico no considera pérdidas ni efectos parásitos, mientras que en la simulación se incluyen estos factores. Se confirma que los cálculos y el diseño son correctos.

---

## 4. Consulta de Hojas de Datos
✅ Revisé las especificaciones técnicas de cada componente, comparé lo que usé en la simulación con los modelos reales seleccionados y justifiqué cada elección.

✅ **Componentes seleccionados y justificación:**
- **MOSFET RFD3055LE**
  Soporta hasta 60 V y 12 A de corriente continua, valores superiores a los máximos que se presentan en el circuito. Cuenta con baja resistencia de encendido, lo que reduce pérdidas, y funciona de forma eficiente a la frecuencia de trabajo de 60 kHz.

- **Driver NCP81253**
  Diseñado para operar con alimentación de 5 V, entrega la corriente necesaria para activar y desactivar el MOSFET rápidamente, garantizando una conmutación estable y evitando sobrecalentamiento.

- **Diodo MUR460**
  Es un diodo de recuperación rápida que soporta 600 V de tensión inversa y 4 A de corriente máxima. Supera las condiciones de operación del circuito, reduce pérdidas al conmutar y se adapta perfectamente a la frecuencia de trabajo.

- **Inductancia 7447471331**
  Tiene un valor exacto de 330 µH, soporta una corriente continua de 2.1 A y no se satura en ningún momento. Mantiene sus características eléctricas en todo el rango de funcionamiento.

- **Condensador ABA0000C1018**
  Cuenta con un valor de 100 µF, tensión nominal de 50 V y baja resistencia interna. Soporta la tensión máxima del circuito y ayuda a reducir el rizado de tensión en la salida.

---

### 📋 Tabla comparativa: Lo que usé en la simulación vs Componente real final
| Elemento                  | Modelo que utilicé en Multisim | Modificación o ajuste que realicé                          | Componente real definitivo | Archivo de hoja de datos correspondiente      |
|---------------------------|----------------------------------|------------------------------------------------------------|----------------------------|-----------------------------------------------|
| MOSFET de potencia        | **IRF540** (disponible en la biblioteca del programa) | Modifiqué sus parámetros internos para que coincidieran en tensión, corriente y resistencia con el modelo solicitado | **RFD3055LE**              | [`RFD3055LE-Datasheets.pdf` ](https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/3ddbc9a3d452e10e2fe51050b6a0b197af670d47/Datasheets/RFD3055LE-Datasheets.pdf)                   |
| Diodo de conmutación      | **MUR460G**                      | Lo usé directamente, ya que tiene las mismas características eléctricas que el modelo real | **MUR460**                 | [`MUR460-Datasheet.pdf`](https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/a05f7f982aabfbe98dbc9a7e61040604f2476e8e/Datasheets/MUR460-Datasheet.PDF)                        |
| Driver de compuerta       | Señal PWM generada con el generador de funciones XFG1 | En la simulación no es necesario colocar el circuito físico; para el diseño final lo agregué para asegurar el control correcto del MOSFET | **NCP81253**               | [`NCP81253-Datasheets.pdf`](https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/a05f7f982aabfbe98dbc9a7e61040604f2476e8e/Datasheets/NCP81253-Datasheets.pdf )                  |
| Inductancias L1 y L2      | **330 µH** (modelo estándar)     | Configuré el valor exacto y una resistencia interna muy baja para simular un comportamiento real | **7447471331**             | [`Inductor7447471331-Datasheet.pdf`  ](https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/a05f7f982aabfbe98dbc9a7e61040604f2476e8e/Datasheets/Inductor7447471331-Datasheet.pdf)          |
| Condensadores C1 y C2     | **100 µF** (modelo electrolítico) | Ajusté su valor y tensión de trabajo a 50 V para coincidir con el componente real | **ABA0000C1018**           | [`CapacitorABA0000C1018-Datasheet.pdf`   ](https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/a05f7f982aabfbe98dbc9a7e61040604f2476e8e/Datasheets/CapacitorABA0000C1018-Datasheet.pdf)      |

---

#### 🔧 Procedimiento que seguí para ajustar el MOSFET
Como el modelo **RFD3055LE** no viene incluido de forma nativa en Multisim, yo realicé lo siguiente:
1. Seleccioné el componente **IRF540** de la lista de semiconductores, por tener características muy parecidas.
2. Entré en sus propiedades eléctricas para modificar los valores: tensión máxima de trabajo, corriente soportada y resistencia de encendido.
3. Ajusté todos estos parámetros para que coincidieran exactamente con lo que indica la hoja de datos del RFD3055LE.
4. Verifiqué que con estos cambios el circuito funcionara igual que si usara el modelo solicitado.

## Cambio de parametros del Mosfet IRF540
<img src="https://github.com/ospqd/OSCAREDUARDOPEREZCISNEROS_EXAMEN_REG_ELECTRONICA/blob/5ad3a76de48f763c8e1c234c7f189130c5392e57/Evidencias/Cambio%20de%20Parametros%20en%20el%20Mosfet.png" alt="Tensión de salida Vo" width="550">

#### ⚙️ Ajustes en el resto de componentes
- **Diodo:** El modelo **MUR460G** que usé en la simulación es idéntico al **MUR460** elegido para la placa; solo cambia la terminación de la referencia, pero sus especificaciones son exactamente las mismas.
- **Driver:** En la simulación solo necesité generar la señal de control, pero para el diseño físico incluí el NCP81253 para garantizar que la señal de 5 V tenga la potencia suficiente para mover la compuerta del MOSFET.
- **Inductancias:** Usé el valor de 330 µH en la simulación, y para el diseño final elegí el modelo 7447471331, que mantiene ese valor y soporta mayor corriente sin saturarse.
- **Condensadores:** Configuré en el programa 100 µF y 50 V de tensión, igual que el componente real ABA0000C1018, que además tiene baja resistencia interna para reducir el rizado.

---

### Descripción de carpetas

- **Calculos:** Desarrollo analítico y procedimientos matemáticos.
- **Simulacion_Multisim:** Archivos de simulación y capturas de resultados.
- **Datasheets:** Hojas de datos de los componentes principales.
- **Evidencias:** Capturas de pantalla y documentación del proyecto.

---

## Conclusiones

- Se diseñó y analizó correctamente un convertidor Ćuk capaz de convertir 18 V en aproximadamente -33.43 V.
- El análisis matemático permitió determinar un ciclo de trabajo de 65 %.
- La simulación en Multisim confirmó el comportamiento esperado del convertidor.
- El rizado de salida obtenido fue muy bajo, aproximadamente 12 mV (0.036 %).
- Los resultados teóricos y simulados presentan una alta concordancia, validando el diseño realizado.
- El diseño PCB desarrollado en KiCad permite la futura implementación física del convertidor.

---

## 📁 Estructura del repositorio


/
README.md
Calculos/
Simulacion_Multisim/
Datasheets/
Evidencias/

**Repositorio compartido con:** @erickmone
**Fecha de entrega:** 26 de junio de 2026
