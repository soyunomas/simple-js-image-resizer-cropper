# Simple JS Image Resizer & Cropper

[![GitHub User](https://img.shields.io/badge/Autor-soyunomas-blue?style=flat-square)](https://github.com/soyunomas)
[![Repo URL](https://img.shields.io/badge/Repositorio-simple--js--image--resizer--cropper-lightgrey?style=flat-square)](https://github.com/soyunomas/simple-js-image-resizer-cropper)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

Una aplicación web sencilla y autónoma (**frontend puro**) para **redimensionar** y **recortar** imágenes directamente en el navegador. Permite cargar múltiples imágenes, redimensionarlas por píxeles o porcentaje (con opciones de aspecto y no-ampliación) y recortar imágenes individuales de forma interactiva.

Construida con **HTML**, **Bootstrap 5**, **JavaScript** y la librería **Cropper.js**.

---

**[➡️ Ver Demo en Vivo](https://soyunomas.github.io/simple-js-image-resizer-cropper/index.html)**

---

## 📸 Capturas de Pantalla (Ejemplos)

![Screenshot de la interfaz principal](docs/screenshot-main.png) <!-- ¡Reemplaza con tu captura! Puedes crear una carpeta 'docs' o 'assets' en tu repo -->
*Interfaz principal mostrando la carga de imágenes y las pestañas de opciones.*

![Screenshot del recorte](docs/screenshot-crop.png) <!-- ¡Reemplaza con tu captura! -->
*Ejemplo de la herramienta de recorte interactiva con Cropper.js.*

---

## ✨ Características Principales

*   ✅ **Carga Múltiple:** Arrastra y suelta o selecciona varios archivos de imagen (`jpg`, `png`, `gif`, `webp`, etc.).
*   🖼️ **Previsualización Instantánea:** Miniaturas de las imágenes cargadas con su nombre y dimensiones originales.
*   ❌ **Eliminación Fácil:** Quita imágenes individualmente de la lista.
*   📐 **Redimensionamiento Flexible:**
    *   Modo **Píxeles**: Define ancho y/o alto exactos.
    *   Modo **Porcentaje**: Escala la imagen según un porcentaje.
    *   Opción para **Mantener Relación de Aspecto**.
    *   Opción para **No Ampliar** (evita *upscaling* si la dimensión deseada es mayor que la original).
*   ✂️ **Recorte Interactivo:**
    *   Selecciona una imagen específica para recortar desde las previsualizaciones.
    *   Interfaz visual e intuitiva con [Cropper.js](https://github.com/fengyuanchen/cropperjs).
    *   Visualización en tiempo real de coordenadas (X, Y) y tamaño (ancho, alto) del recorte.
*   🚀 **Procesamiento 100% en el Cliente:** Toda la manipulación se realiza en tu navegador. No se suben imágenes a ningún servidor. ¡Rápido y privado!
*   💾 **Descarga Directa:** Guarda las imágenes procesadas (redimensionadas o recortadas) en tu dispositivo.
*   📑 **Interfaz Organizada:** Pestañas claras (Bootstrap Tabs) para separar las funciones de Redimensionar y Recortar.
*   ⏳ **Feedback Visual:** Indicadores de carga (spinners) en los botones durante el procesamiento y alertas para mostrar resultados o errores.
*   📱 **Diseño Responsivo:** Interfaz adaptable a diferentes tamaños de pantalla gracias a Bootstrap.

---

## 🛠️ Tecnologías Utilizadas

*   **HTML5:** Estructura semántica del contenido.
*   **CSS3:** Estilos personalizados (incrustados en el HTML).
*   **JavaScript (ES6+):** Lógica de la aplicación, manipulación del DOM, manejo de eventos y procesamiento de imágenes (Vanilla JS).
*   **[Bootstrap 5.3.2](https://getbootstrap.com/):** Framework CSS para el layout, componentes (pestañas, botones, formularios, alertas, grid) y utilidades.
*   **[Cropper.js 1.6.1](https://github.com/fengyuanchen/cropperjs):** Librería JavaScript para el recorte interactivo de imágenes.
*   **[Bootstrap Icons 1.11.1](https://icons.getbootstrap.com/):** Iconos para mejorar la interfaz de usuario.
*   **APIs del Navegador:**
    *   File API / FileReader API: Para leer los archivos seleccionados por el usuario.
    *   Canvas API: Para realizar el redimensionamiento y generar las imágenes recortadas.
    *   Drag and Drop API: Para la funcionalidad de arrastrar y soltar.

---

## 🚀 Cómo Usar

Como es una aplicación puramente de lado del cliente, no necesitas instalación compleja ni dependencias externas (más allá de las CDNs incluidas):

1.  **Clona el repositorio:**
    ```bash
    git clone https://github.com/soyunomas/simple-js-image-resizer-cropper.git
    ```
2.  **Navega a la carpeta:**
    ```bash
    cd simple-js-image-resizer-cropper
    ```
3.  **Abre el archivo `index.html`** directamente en tu navegador web preferido (Firefox, Chrome, Edge, Safari, etc.).

¡Y listo! Ya puedes empezar a cargar y editar tus imágenes.

---

## ⚙️ Cómo Funciona (Brevemente)

1.  **Carga y Lectura:** Se usa la File API para acceder a los archivos seleccionados o soltados. `FileReader` lee cada archivo como un `DataURL`.
2.  **Previsualización:** Se crea un elemento `<img>` para cada archivo leído. Al cargar la imagen en memoria, se obtienen sus dimensiones naturales y se muestra la miniatura junto con los detalles.
3.  **Redimensionamiento:**
    *   Se calcula el tamaño final basándose en la entrada del usuario (píxeles/porcentaje) y las opciones seleccionadas (aspecto, no ampliar).
    *   Se crea un elemento `<canvas>` con las dimensiones finales.
    *   Se dibuja la imagen original en el canvas usando `drawImage()` con las nuevas dimensiones.
    *   Se exporta el contenido del canvas como un `DataURL` usando `toDataURL()`.
4.  **Recorte:**
    *   Al seleccionar una imagen, se inicializa `Cropper.js` sobre ella.
    *   `Cropper.js` maneja la interfaz de selección y proporciona los datos del área recortada.
    *   Al pulsar "Recortar", se usa el método `getCroppedCanvas()` de `Cropper.js` para obtener un nuevo `<canvas>` que contiene solo el área seleccionada.
    *   Se exporta este canvas como `DataURL`.
5.  **Descarga:** Se crea un enlace (`<a>`) temporal con el `DataURL` de la imagen procesada y el atributo `download`, y se simula un clic para iniciar la descarga.

---

## 📜 Licencia

Distribuido bajo la Licencia MIT. Ver `LICENSE` para más información.


---

Hecho con ❤️ por **soyunomas**
