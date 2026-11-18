# 100 DÍAS — CrossFit en casa (v3.5.4)

Aplicación web progresiva (PWA), minimalista en blanco y negro, para seguir un programa de CrossFit en casa de 100 días.

## Qué incluye

- Programa estructurado en cinco fases: adaptación (1–20), construcción de base (21–45), intensidad (46–70), pico de rendimiento (71–90) y consolidación/test (91–100).
- Primeros 20 días desarrollados individualmente, con calentamiento, fuerza/técnica, bloque metabólico y core/finalizador. El detalle también está en `PROGRAMA_100_DIAS.md`.
- Calendario completo de 100 días con sesión detallada cada día: descanso cada siete días y tests los días 95 y 100.
- Pantalla inicial a pantalla completa con el mensaje “EMPEZAMOS?”; se accede a la app deslizando hacia arriba.
- Navegación por páginas independientes: Inicio, Sesión, Calendario y Progreso.
- Entrenamiento por tarjetas: se muestra un solo ejercicio cada vez y cada serie completada lleva automáticamente al siguiente ejercicio.
- El calentamiento desaparece automáticamente al completar la primera serie del primer ejercicio y permanece oculto al volver a abrir la sesión.
- Series intercaladas por rondas: al acabar la lista se vuelve al primer ejercicio y se omiten las series ya completadas.
- Botón “Finalizar entreno” habilitado únicamente cuando todas las series están completadas.
- Historial de cargas y repeticiones.
- Temporizador de descanso ajustable.
- Estadísticas de sesiones completadas y avance por fase.
- Exportación y restauración de copias JSON.
- Guardado local en el navegador, sin cuenta ni servidor.
- PWA instalable y caché offline. No depende de CDN ni de conexión externa para mostrar estilos o lógica.

## Navegación

- **Inicio:** resumen del día y acceso a la sesión.
- **Sesión:** ejercicios, registro de series, temporizador y notas.
- **Calendario:** selección de día y fases.
- **Progreso:** estadísticas, historial y copias de seguridad.

## Publicar en GitHub Pages

1. Descomprime el ZIP.
2. Sube el contenido de la carpeta `ENTRENOS-main` a la raíz de un repositorio de GitHub (no es necesario subir la carpeta contenedora).
3. En el repositorio, abre **Settings → Pages**.
4. En **Build and deployment**, selecciona **Deploy from a branch**, rama `main` y carpeta `/(root)`.
5. Guarda y abre la URL publicada por GitHub Pages.

## Instalar en móvil

- iPhone: abre la web en Safari → Compartir → Añadir a pantalla de inicio.
- Android: abre la web en Chrome → menú → Instalar aplicación / Añadir a pantalla de inicio.

## Datos y privacidad

Los datos se guardan en `localStorage` del navegador y dispositivo actual. No se sincronizan entre dispositivos. Exporta una copia periódicamente desde **Progreso → Copia de seguridad**. La restauración sustituye los datos actuales, previa confirmación.

La versión anterior (`fullbody-home-100-v1`) no se borra del almacenamiento del navegador. La nueva versión utiliza una clave independiente para no sobrescribir registros antiguos.

## Contenido del programa

Los días 1–20 están escritos a mano. Los días 21–100 se generan automáticamente a partir de las seis sesiones-tipo de los días 15–20, multiplicando repeticiones, tiempos y duración de los bloques por 1,10 (fase 2), 1,21 (fase 3), 1,33 (fase 4) y 1,46 (fase 5): +10 % acumulado por fase. Los descansos siguen el rango de cada fase. Los días 95 y 100 son el mismo test (flexiones, sentadillas, plancha y burpees en 3 min) para poder compararlos.

## Novedades de la v3.2.0

- Temporizador: ±15 s ya no lo detiene, el descanso por defecto sigue a la fase/día y puede iniciarse automáticamente al marcar una serie (opcional).
- Los días de descanso y de test se pueden marcar como hechos, y cualquier día se puede reabrir; el progreso ya puede llegar al 100 %.
- Service worker: la página se descarga primero de la red, así las actualizaciones llegan sin borrar la caché.
- PWA: iconos PNG (192, 512, maskable y apple-touch-icon) y manifiesto completo para instalar correctamente en iOS y Android.
- Pantalla de bienvenida accesible también con toque/clic y teclado, con indicación visible.
- Política de seguridad de contenido (CSP) y validación más estricta al restaurar copias.
- Versiones sincronizadas en app, caché y documentación. Los datos existentes son compatibles (misma clave de almacenamiento).

## Novedades de la v3.4.0

- Sesiones completas para los días 21–100 con +10 % de volumen por fase.
- Test de los días 95 y 100 con registro de resultados.
- La pantalla se mantiene encendida durante la sesión y el temporizador avisa con sonido y vibración (según dispositivo).


## Cambios 3.4.0
- Entrenamiento en modo tarjeta: un ejercicio visible cada vez, con navegación anterior/siguiente.
- Se mantienen los registros individuales de series, repeticiones/tiempo y carga.
- Descanso automático de 30 segundos al marcar una serie, con opción de avanzar al siguiente ejercicio sin esperar.
- Navegación limitada a un máximo de cinco días por delante del último día completado.


## Versión 3.5.0 — Series intercaladas

Durante el entrenamiento se muestra una sola tarjeta de serie cada vez. Al confirmar una serie, la app avanza automáticamente al siguiente ejercicio. Al acabar el listado, comienza la siguiente ronda desde el primer ejercicio, omitiendo las series ya completadas. El botón **Finalizar entreno** solo se habilita cuando todas las series están registradas.
