# Calculadora de Metabolismo Basal

Calculadora web de metabolismo basal (BMR) y gasto calórico total (TDEE), pensada para gente sin conocimientos de nutrición o entrenamiento. Además del número, da contexto: ejercicios, nutrición, plan de comidas e información de salud personalizados según edad, nivel de actividad y condiciones médicas — y una hoja exportable en PDF para llevar a una consulta con un nutricionista.

**Demo en vivo:** https://calculadora-metabolismo-basal.vercel.app

## Qué hace

- Calcula BMR (fórmula de Harris-Benedict) y TDEE a partir de peso, altura, edad, sexo y nivel de actividad.
- Muestra objetivos de calorías para déficit, mantenimiento y superávit, con el desglose de macronutrientes (proteína / carbohidratos / grasas) de cada uno.
- Indicador visual de IMC con categoría (bajo peso / normal / sobrepeso / obesidad).
- Recomendaciones de ejercicio (cardio + fuerza), nutrición y un plan de comidas de ejemplo, **personalizados dinámicamente** según grupo etario y nivel de actividad — no es el mismo contenido para todos.
- Selector de 18 condiciones de salud/discapacidad (diabetes, hipertensión, embarazo, movilidad reducida, etc.) con información general no diagnóstica para cada una, filtrado según el sexo seleccionado.
- Glosario de términos y preguntas sugeridas para hacerle a un nutricionista.
- Exportación a PDF de una hoja compacta (una sola página) con los datos, resultados y preguntas, lista para imprimir o llevar a una consulta.
- Tarjeta de resultados descargable como imagen para compartir.
- Modo claro/oscuro con persistencia en `localStorage`.
- Totalmente responsive, con una tipografía y layout que aprovechan el espacio en pantallas grandes sin dejar de funcionar bien en celular.

## Stack

HTML, CSS y JavaScript vanilla — sin frameworks ni paso de build. Un solo archivo (`index.html`) desplegado como sitio estático en [Vercel](https://vercel.com).

Algunas técnicas usadas:
- CSS Grid con la técnica de `grid-template-rows: 0fr → 1fr` para los acordeones animados, sin JavaScript midiendo alturas.
- Canvas 2D para generar la tarjeta de resultados descargable.
- `@media print` con un layout propio (no es una captura del sitio) para el PDF exportable.
- Un fondo de video en el hero con loop manual (fade in/out con `requestAnimationFrame`) en vez de depender del loop nativo del navegador.

## Correr el proyecto localmente

No hace falta build ni dependencias. Cloná el repo y abrí `index.html` en el navegador, o serví la carpeta con cualquier servidor estático:

```bash
git clone https://github.com/GermanGiorgis/calculadora-metabolismo-basal.git
cd calculadora-metabolismo-basal
npx serve .
```

## Nota

Los cálculos y recomendaciones son estimaciones orientativas basadas en fórmulas estándar; no reemplazan una consulta con un profesional de la salud.
