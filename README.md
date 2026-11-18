# Reconocimiento de manos y gestos

## Requisitos
- Teléfono Android con navegador actualizado (Chrome recomendado).
- Conexión a Internet.
- Cámara frontal o trasera.
- Permiso de cámara concedido al navegador.

## Tecnología
- JavaScript (módulos ES).
- MediaPipe Tasks Vision 0.10.14.
- Modelo preentrenado Gesture Recognizer de MediaPipe.
- HTML5 video y canvas.

## Cómo ejecutar desde Android
1. El archivo `index.html` debe publicarse en un sitio HTTPS estático (la cámara del navegador normalmente requiere un contexto seguro).
2. Abre la dirección HTTPS en Chrome.
3. Pulsa **Iniciar cámara** y concede permiso.
4. Coloca la mano completa frente a la cámara, con iluminación suficiente.
5. Prueba palma abierta, puño, V y pulgar arriba.
6. Registra capturas de pantalla para cada gesto.
7. Pulsa **Detener cámara** y verifica que se libere.

El proyecto importa MediaPipe desde jsDelivr y descarga el modelo oficial desde Google Cloud Storage. Por eso necesita Internet al iniciar.

## Gestos y acciones
- Open_Palm: saludo.
- Closed_Fist: pausa de demostración.
- Victory: confirmación.
- Thumb_Up: suma un punto.

La clasificación se realiza con el clasificador preentrenado de MediaPipe. La interfaz muestra la confianza devuelta por el modelo y dibuja los 21 puntos de referencia y sus conexiones.

## Solución de problemas
- Si no abre la cámara: confirma HTTPS, permisos del navegador y que ninguna otra aplicación esté usando la cámara.
- Si el modelo no carga: revisa Internet y vuelve a cargar la página.
- Si no reconoce un gesto: ilumina mejor la mano, aléjala un poco y muestra la palma completa.
- Al terminar, usa Detener cámara para cerrar las pistas de video.

## Limitaciones
El modelo incluye un conjunto limitado de gestos predefinidos. El rendimiento puede variar según iluminación, orientación, distancia, cámara y dispositivo. El proyecto debe probarse en el teléfono donde se presentará.
