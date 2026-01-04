[⬅️ Volver a "Conceptos de Ladder"](https://github.com/SantiagoBaeza/Conceptos-importantes-de-Ladder/tree/main)

# Uso de funciones SET y RESET en PLC – Enclavamiento de motores

Este proyecto muestra cómo utilizar las funciones **SET (S)** y **RESET (R)** en programación de PLCs para controlar salidas de manera más intuitiva.  
A diferencia de las bobinas normales, las bobinas de tipo SET mantienen la salida activada incluso cuando la condición inicial desaparece, y las bobinas de tipo RESET permiten desactivar esa misma salida cuando se cumple la condición de apagado.

---

## Contexto

En el [repositorio anterior](https://github.com/SantiagoBaeza/Repeticion-de-se-ales-en-PLC/tree/main) a este se trabajó con un error típico: la repetición de bobinas de salida en distintos segmentos.  
En este nuevo ejercicio se retoma ese mismo esquema, pero se reemplaza la lógica por bobinas de tipo **SET** y **RESET**, lo que permite repetir la misma salida en distintos segmentos sin que el PLC genere conflictos.  
Se añadieron dos nuevas variables (`set button - M0.2` y `reset button - M0.3`) para controlar el motor mediante las instrucciones de SET y RESET.

---

## Capturas

- **Captura 01**: Inicio de la simulación, con el circuito original y la bobina `motor3` en su forma normal.  
  ![Inicio de la simulación](https://github.com/SantiagoBaeza/Uso-de-funciones-SET-y-RESET-en-PLC/blob/main/01%20inicio%20de%20la%20simulacion.jpg)

- **Captura 02**: Forzado de enclavamiento usando instrucciones SET y RESET.  
  ![Forzado de enclavamiento](https://github.com/SantiagoBaeza/Uso-de-funciones-SET-y-RESET-en-PLC/blob/main/02%20forzado%20de%20enclavamiento%20usando%20set%20y%20reset.jpg)

- **Captura 03**: Circuito con botón Start presionado, `motor3` encendido en ambos segmentos.  
  ![Botón Start presionado](https://github.com/SantiagoBaeza/Uso-de-funciones-SET-y-RESET-en-PLC/blob/main/03%20circuito%20con%20boton%20start%20presionado%20.jpg)

- **Captura 04**: Botón Start sin presionar (forzado a cero), `motor3` permanece enclavado.  
  ![Motor3 enclavado](https://github.com/SantiagoBaeza/Uso-de-funciones-SET-y-RESET-en-PLC/blob/main/04%20boton%20start%20sin%20presionar%20(forzado%20a%20cero)%2C%20motor3%20enclavado%20en%20ambos%20segmentos%20(2%20y%203).jpg)

- **Captura 05**: Pulso al botón Stop para apagar `motor3` en ambos segmentos.  
  ![Pulso botón Stop](https://github.com/SantiagoBaeza/Uso-de-funciones-SET-y-RESET-en-PLC/blob/main/05%20pulso%20boton%20stop%20para%20apagar%20motor3%20en%20ambos%20segmentos%20.jpg)

- **Captura 06**: `motor3` apagado, fin del ciclo de control.  
  ![Motor3 apagado](https://github.com/SantiagoBaeza/Uso-de-funciones-SET-y-RESET-en-PLC/blob/main/06%20motor3%20apagado%20.jpg)
  
---

## Funcionalidad clave

- **SET (S):** activa la salida y la mantiene energizada hasta que se ejecute un RESET.  
- **RESET (R):** desactiva la salida cuando se cumple la condición de apagado.  
- Permite repetir la misma salida en distintos segmentos sin errores de programación.  
- Simplifica el enclavamiento de motores en simulaciones cortas, aunque puede complejizar el análisis en proyectos grandes.  
- Se recomienda estructurar bien las condiciones de SET y RESET para evitar que las salidas queden encendidas de forma incorrecta.

---

## Simulación realizada en

- Siemens S7-1200 (TIA Portal)  
- Lógica en escalera (LAD)

---

## Comentarios finales

Este ejercicio demuestra cómo las funciones SET y RESET pueden reemplazar el enclavamiento clásico con bobinas normales, ofreciendo una alternativa más directa para mantener y liberar salidas.  
Sin embargo, en proyectos más complejos puede resultar menos claro y generar dificultades de mantenimiento, por lo que muchos programadores prefieren seguir utilizando bobinas normales con lógica de enclavamiento.  

El archivo del proyecto está incluido en este repositorio para que cualquier persona con acceso a **TIA Portal V16** pueda abrirlo y realizar la simulación.  
Este ejercicio tiene como objetivo servir de práctica y dejar registro de mis avances en programación de PLC.

---

> 🧩 Estos espacios están en construcción y se actualizan de forma frecuente.
