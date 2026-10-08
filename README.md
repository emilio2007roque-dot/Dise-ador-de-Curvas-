# Curva · Diseño geométrico

PWA en español para diseño preliminar de curvas horizontales circulares, con cálculo de transición, vista en planta y exportación de entregables. No necesita librerías ni servicios externos.

## Abrir y usar

La PWA necesita un origen `localhost` o HTTPS para que el navegador pueda instalarla y activar el modo sin conexión. Desde esta carpeta, inicia un servidor estático, por ejemplo:

```powershell
python -m http.server 8000
```

Abre `http://localhost:8000` en el navegador. En un teléfono, publícala en un hosting con HTTPS y usa **Instalar** o **Agregar a pantalla de inicio**. Tras la primera carga, los archivos de la interfaz quedan disponibles sin conexión.

## Funciones

- Radio o grado de curvatura, velocidad SCT, deflexión, sentido, coordenadas X/Y del PI, azimut de entrada, cadenamiento, tangente disponible y ancho de calzada.
- Elementos geométricos, sugerencias de transición, sobreelevación/ampliación y estaciones PC, PT, con verificación Gc ≤ Gmáx.
- Vista en planta ajustada al trazo, desplazable y con zoom; el PI puede ubicarse con coordenadas y azimut para orientar el diseño en cualquier dirección.
- División del arco en hasta 200 partes, con ángulo central, radio O–Pi, arco PC–Pi, cuerda y cadenamiento por punto.
- Apartados de resultados ordenados como el Excel y pestaña con las tablas 003-1, 004-1, 004-4 y 004-5 integradas.
- Descarga de la geometría en DXF (unidades en metros), memoria de cálculo en PDF o Markdown, y tabla de puntos en CSV.

## Alcance y fuentes

El libro Excel adjunto transcribe las tablas SCT 003-1, 004-1, 004-4 y los renglones principales de 004-5 para E/D (V=30–70 km/h). Los valores aplicables se sugieren al cambiar velocidad y Gc; Gmáx y Dp se interpolan para velocidades entre renglones. Los valores de 004-6/7/8 para carreteras C, B y A no aparecen transcritos en el libro adjunto, por lo que se capturan manualmente en los campos Sc, Ac y Le. El trazo de planta y DXF incluye la geometría de transición espiral aproximada cuando se adopta ese tipo; coteja los datos de diseño con las tablas SCT aplicables.

La longitud del arco simple se calcula como `Lc = π Rc Δ / 180`; el cadenamiento `PT = PC + Lc`, siguiendo el criterio de replanteo del material B19. En la tabla de puntos, `PC–Pi arco` es longitud sobre la curva; se incluye además la cuerda directa desde PC. El azimut se mide desde el Norte en sentido horario y las coordenadas del PI se exportan como origen de la geometría DXF.

Fuentes de referencia adjuntas: SCT, *Normas de Servicios Técnicos, Libro 2, Título 2.01.01 Carreteras* (1984); SCT, *Manual de Proyecto Geométrico de Carreteras* (2018); *Bitácora de clase 19 — Carreteras* (2026); Excel `Calculadora_Curva_Horizontal_SCT.xlsx`.
