# Cálculo Mental

Aplicación móvil desarrollada en **React Native** para practicar cálculo mental bajo presión de tiempo. El juego genera operaciones matemáticas aleatorias y registra el desempeño del usuario según precisión, velocidad de respuesta, puntaje e historial de partidas.

Proyecto realizado para la materia **Desarrollo de Aplicaciones I**.

---

## Funcionalidades principales

- Generación aleatoria de operaciones matemáticas.
- Selección de dificultad:
  - Fácil
  - Medio
  - Difícil
- Configuración de cantidad de preguntas por ronda, entre 1 y 20.
- Múltiples modos de juego:
  - Clásico
  - Verdadero / Falso
  - Multiple Choice
  - Contra reloj
- Timer por pregunta según dificultad.
- Puntaje basado en precisión y velocidad.
- Registro de:
  - Respuestas correctas
  - Respuestas incorrectas
  - Preguntas sin responder
  - Puntaje total
  - Tiempo promedio de respuesta
- Pantalla de resultado final de la partida.
- Historial de partidas con persistencia local.
- Leaderboard de mejores puntajes.
- Filtro de leaderboard por modo de juego y dificultad.
- Visualización de los 3 mejores puntajes por categoría.
- Pantalla de estadísticas generales.
- Estadísticas acumuladas por modo de juego.
- Gráficos visuales de rendimiento.
- Borrado de historial.
- Dificultad dinámica mediante reducción progresiva del tiempo.
- Animaciones simples para mejorar la experiencia de usuario.
- Diseño visual con paleta azul y oro.

---

## Modos de juego

### Modo Clásico

El usuario debe ingresar manualmente el resultado de una operación matemática.

Ejemplo:

```text
8 + 5 = ?
```

---

### Modo Verdadero / Falso

Se muestra una operación con un resultado propuesto. El usuario debe indicar si es verdadero o falso.

Ejemplo:

```text
7 × 4 = 29
```

---

### Modo Multiple Choice

Se muestra una operación matemática y cuatro posibles respuestas. El usuario debe seleccionar la opción correcta.

Ejemplo:

```text
12 - 5 = ?

[6] [7] [8] [9]
```

---

### Modo Contra Reloj

El usuario tiene un tiempo total de partida para responder la mayor cantidad posible de operaciones.

La partida termina cuando:

- El usuario responde incorrectamente.
- Se agota el tiempo total.

---

## Dificultades

### Fácil

- Números entre 1 y 10.
- Operaciones de suma y resta.
- Mayor tiempo por pregunta.

### Medio

- Números entre 1 y 50.
- Operaciones de suma, resta y multiplicación.
- Tiempo intermedio por pregunta.

### Difícil

- Números más altos.
- Operaciones de suma, resta, multiplicación y división exacta.
- Menor tiempo por pregunta.

En las divisiones se generan resultados enteros para mantener el foco en cálculo mental ágil.

---

## Sistema de puntaje

El puntaje se calcula teniendo en cuenta si la respuesta fue correcta y cuánto tardó el usuario en responder.

| Situación                    | Puntaje |
| ---------------------------- | ------: |
| Respuesta correcta rápida    |    +100 |
| Respuesta correcta en tiempo |     +70 |
| Respuesta incorrecta         |     -30 |
| Sin respuesta                |     -50 |

Una respuesta se considera rápida si fue respondida antes del 75% del tiempo disponible.

Durante la partida se muestra feedback visual del resultado de cada respuesta.

---

## Pantalla de resultado final

Al terminar una partida, la aplicación muestra una pantalla de resultado final con los datos principales de esa ronda:

- Modo de juego.
- Dificultad.
- Preguntas totales o preguntas alcanzadas.
- Correctas.
- Incorrectas.
- Sin responder.
- Puntaje final.
- Precisión.
- Tiempo promedio de respuesta.

Las estadísticas acumuladas no se muestran en esta pantalla, sino en una pantalla separada de estadísticas para mantener más clara la experiencia.

---

## Persistencia local

La aplicación no se conecta a internet. Los datos se guardan localmente utilizando **AsyncStorage**.

Se guarda información como:

- Fecha de la partida.
- Modo de juego.
- Dificultad.
- Cantidad de preguntas.
- Correctas.
- Incorrectas.
- Sin responder.
- Puntaje.
- Tiempo promedio.

---

## Historial

La pantalla de historial permite consultar las partidas guardadas localmente.

Cada partida muestra información como:

- Modo de juego.
- Dificultad.
- Puntaje.
- Cantidad de respuestas correctas.
- Cantidad de respuestas incorrectas.
- Cantidad de preguntas sin responder.
- Fecha de la partida.

Desde historial se puede acceder a:

- Leaderboard.
- Estadísticas.
- Borrado del historial local.

---

## Leaderboard

La aplicación cuenta con una pantalla de mejores puntajes organizada por modo de juego y dificultad.

El usuario puede filtrar por:

- Modo clásico.
- Verdadero / Falso.
- Multiple Choice.
- Contra reloj.

Y también por dificultad:

- Fácil.
- Medio.
- Difícil.

El leaderboard muestra solamente los **3 mejores puntajes** para la combinación seleccionada de modo y dificultad.

---

## Estadísticas

La aplicación incluye una pantalla específica de estadísticas acumuladas.

A diferencia del leaderboard, esta pantalla no muestra rankings ni partidas individuales, sino un resumen general del rendimiento del usuario.

Las estadísticas se pueden consultar por modo de juego:

- Clásico.
- Verdadero / Falso.
- Multiple Choice.
- Contra reloj.

La pantalla de estadísticas muestra:

- Partidas jugadas.
- Mejor puntaje.
- Puntaje promedio.
- Precisión promedio.
- Tiempo promedio de respuesta.
- Preguntas totales.
- Correctas totales.
- Incorrectas totales.
- Sin responder totales.
- Rendimiento por dificultad.

También se incorporaron gráficos visuales realizados con componentes nativos de React Native:

- Gráfico visual de precisión promedio.
- Barras de distribución de respuestas.
- Barras de precisión por dificultad.
- Gráfico de mejor puntaje por dificultad.
- Gráfico de partidas jugadas por dificultad.

Estos gráficos no requieren librerías externas.

---

## Tecnologías utilizadas

- React Native
- TypeScript
- AsyncStorage
- React Native Animated API
- Android Studio
- Gradle
- Android SDK

---

## Estructura del proyecto

```text
src/
  screens/
    homeScreen.tsx
    gameScreen.tsx
    resultScreen.tsx
    historyScreen.tsx
    leaderboardScreen.tsx
    statsScreen.tsx

  theme/
    colors.ts

  utils/
    generateOperation.ts
    calculateScore.ts
    dynamicDifficulty.ts
    gameModes.ts
    storage.ts
```

---

## Instalación

Clonar el proyecto y entrar a la carpeta:

```bash
cd calculosmentales
```

Instalar dependencias:

```bash
npm install
```

Ejecutar Metro:

```bash
npx react-native start
```

En otra terminal, ejecutar la app en Android:

```bash
npx react-native run-android
```

---

## Configuración Android

Para ejecutar el proyecto es necesario tener configurado:

- Android Studio
- Android SDK
- Emulador Android o dispositivo físico
- Variable de entorno o archivo `android/local.properties` apuntando al SDK

Ejemplo de `android/local.properties`:

```properties
sdk.dir=C:\\Users\\TU_USUARIO\\AppData\\Local\\Android\\Sdk
```

---

## Capturas sugeridas para la entrega

Se recomienda incluir capturas de:

1. Pantalla de inicio/configuración.
2. Modo clásico.
3. Modo verdadero/falso.
4. Modo multiple choice.
5. Modo contra reloj.
6. Resultado final.
7. Historial.
8. Leaderboard filtrado por modo y dificultad.
9. Pantalla de estadísticas.
10. Gráficos de estadísticas.

---

## Decisiones de diseño

Se eligió una paleta **azul y oro** para dar una identidad visual clara y consistente.

La lógica del proyecto se separó en archivos independientes para mejorar la organización:

- Las pantallas están en `src/screens`.
- Los colores están centralizados en `src/theme/colors.ts`.
- La lógica del juego está en `src/utils`.
- La persistencia local está centralizada en `storage.ts`.

El sistema de puntaje fue separado en una función propia para facilitar su mantenimiento y reutilización.

La persistencia local se implementó con AsyncStorage para cumplir con la restricción de que la aplicación no se conecte a internet.

El leaderboard se separó del historial para mostrar únicamente los mejores resultados.

La pantalla de estadísticas se separó del resultado final para distinguir entre:

- Estadísticas de una partida individual.
- Estadísticas acumuladas del usuario.

Los gráficos de estadísticas fueron implementados con componentes nativos de React Native para evitar agregar dependencias externas innecesarias.

---

## Estado del proyecto

Funcionalidades implementadas:

- [x] Configuración de dificultad
- [x] Generación aleatoria de operaciones
- [x] Modo clásico
- [x] Modo verdadero/falso
- [x] Modo multiple choice
- [x] Modo contra reloj
- [x] Cantidad de preguntas configurable
- [x] Timer por pregunta
- [x] Sistema de puntaje
- [x] Resultado final por partida
- [x] Persistencia local
- [x] Historial
- [x] Leaderboard
- [x] Leaderboard top 3
- [x] Filtro de leaderboard por modo
- [x] Filtro de leaderboard por dificultad
- [x] Pantalla de estadísticas acumuladas
- [x] Estadísticas por modo de juego
- [x] Gráficos de estadísticas
- [x] Reinicio/borrado de historial
- [x] Dificultad dinámica
- [x] Animaciones simples

---

## Conclusión

La aplicación cumple con el objetivo de evaluar cálculo mental bajo presión de tiempo. Permite configurar dificultad, modo de juego y cantidad de preguntas cuando corresponde; registra precisión, velocidad, puntaje e historial; e incorpora funcionalidades adicionales como leaderboard filtrado, estadísticas acumuladas, gráficos visuales, dificultad dinámica, animaciones y persistencia local.

La solución funciona offline y utiliza almacenamiento local, respetando las restricciones del proyecto.
