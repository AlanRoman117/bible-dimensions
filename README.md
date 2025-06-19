# Bible Dimensions

Bible Dimensions is a web application designed to provide easy, programmatic access to the scriptures, allowing users to fetch and display Bible verses and chapters from different versions with a user-friendly interface. It's built for developers and anyone who needs a quick and structured way to interact with Bible texts.

## Features

* **Multi-Version Support**: Easily switch between different Bible versions, including:
    * King James Version (KJV)
    * Reina Valera 1960 (RV1960)
* **Dynamic Verse Retrieval**: Specify single verses, ranges of verses within a chapter, or even across multiple chapters.
* **Multiple Verse Selections**: Add multiple input fields to fetch various passages simultaneously.
* **Language Selection**: Toggle the application's interface between English and Spanish.
* **Theme Customization**: Choose between Light, Sepia, and Dark themes for a personalized reading experience.
* **Copy to Clipboard**: Conveniently copy the fetched verses to your clipboard.
* **Structured Data Output**: Verses are presented clearly with their book, chapter, and verse references.

## How to Use

The project includes an `Bible-dimensions.html` file which contains the full web application. You can open this HTML file directly in a web browser to use the tool.

### Navigating the Application:

1.  **Select Bible Version**: Use the "Select Bible Version" dropdown to choose between "King James Version" or "Reina Valera 1960".
2.  **Select Language**: Use the language toggle buttons (English / Español) to change the UI language.
3.  **Select Theme**: Use the theme toggle buttons (Light / Sepia / Dark) to change the application's visual theme.
4.  **Input Verses**:
    * Select the **Book**, **Start Chapter**, and **Start Verse**.
    * Optionally, specify an **End Chapter** and **End Verse** to retrieve a range.
    * Click "Add More Verses" to add additional input fields for multiple passages.
5.  **Generate Document**: Click "Generate Document" to fetch and display the selected verses in the output area.
6.  **Copy Verses**: Use the "Copy Verses to Clipboard" button to copy the displayed text.

## Data Structure (for RV1960 and KJV)

The Bible text is organized into structured JSON files for easy access. The data structure is modeled after the popular `aruljohn/Bible-kjv` project.

The data is typically organized as follows within version-specific `data/` directories (e.g., `rv1960_output/` or `kjv_output/`):

1.  **Individual Book Files (66 files)**: Each book of the Bible has its own JSON file (e.g., `Genesis.json`, `Apocalipsis.json`).
    * **Structure**:
        ```json
        {
          "book": "Génesis",
          "chapters": [
            {
              "chapter": 1,
              "verses": [
                {
                  "verse": 1,
                  "text": "En el principio creó Dios los cielos y la tierra."
                },
                // ...
              ]
            }
          ]
        }
        ```
    * **Filename Convention**:
        * **Reina Valera 1960**: Multi-word book names use underscores (e.g., `1_Corintios.json`), while single words are direct (e.g., `Genesis.json`). Accented characters in book names are normalized for filenames (e.g., "Génesis" becomes "Genesis").
        * **King James Version**: Multi-word book names are concatenated (e.g., `1Corinthians.json`), and single words are direct (e.g., `Genesis.json`).

2.  **`books.json`**: A simple JSON array containing the names of all 66 books in their canonical order. This file is used to populate the book selection dropdowns.
    * **Example**:
        ```json
        [
            "1 Crónicas",
            "1 Corintios",
            // ...
        ]
        ```

3.  **`book_chapter_counts.json`**: A JSON object mapping each book's name to its total number of chapters. (This file might not be directly used in the current `ible-dimensions.html` but is part of the data structure description).
    * **Example**:
        ```json
        {
          "Génesis": 50,
          "Éxodo": 40,
          // ...
        }
        ```

## Credits and Source

* **Source Text Data**:
    * **Reina Valera 1960**: The original plain text data was sourced from the `josevladimir/bible-json` repository.
    * **King James Version**: Data source typically from similar public domain Bible text projects.
* **JSON Structure Model**: This project's output format is based on the structure of the `aruljohn/Bible-kjv` repository.

## License

This project is released under the **MIT License**. See the `LICENSE` file for more details.

---

# Bible Dimensions

Bible Dimensions es una aplicación web diseñada para proporcionar acceso fácil y programático a las escrituras, permitiendo a los usuarios buscar y mostrar versículos y capítulos de la Biblia de diferentes versiones a través de una interfaz amigable. Está pensada para desarrolladores y cualquier persona que necesite una forma rápida y estructurada de interactuar con textos bíblicos.

## Características

* **Soporte Multi-versión**: Cambia fácilmente entre diferentes versiones de la Biblia, incluyendo:
    * King James Version (KJV)
    * Reina Valera 1960 (RV1960)
* **Recuperación Dinámica de Versículos**: Especifica versículos individuales, rangos de versículos dentro de un capítulo, o incluso a través de múltiples capítulos.
* **Selección de Múltiples Versículos**: Añade varios campos de entrada para buscar diversos pasajes simultáneamente.
* **Selección de Idioma**: Alterna la interfaz de la aplicación entre inglés y español.
* **Personalización de Tema**: Elige entre temas Claro, Sepia y Oscuro para una experiencia de lectura personalizada.
* **Copiar al Portapapeles**: Copia convenientemente los versículos obtenidos al portapapeles.
* **Salida de Datos Estructurada**: Los versículos se presentan claramente con sus referencias de libro, capítulo y versículo.

## Cómo Usar

El proyecto incluye un archivo `Bible-dimensions.html` que contiene la aplicación web completa. Puedes abrir este archivo HTML directamente en un navegador web para usar la herramienta.

### Navegando la Aplicación:

1.  **Seleccionar Versión de la Biblia**: Utiliza el menú desplegable "Select Bible Version" para elegir entre "King James Version" o "Reina Valera 1960".
2.  **Seleccionar Idioma**: Usa los botones de alternancia de idioma (English / Español) para cambiar el idioma de la interfaz.
3.  **Seleccionar Tema**: Usa los botones de alternancia de tema (Light / Sepia / Dark) para cambiar el estilo visual de la aplicación.
4.  **Ingresar Versículos**:
    * Selecciona el **Libro**, **Capítulo de Inicio** y **Versículo de Inicio**.
    * Opcionalmente, especifica un **Capítulo Final** y **Versículo Final** para obtener un rango.
    * Haz clic en "Añadir Más Versículos" para agregar campos de entrada adicionales para múltiples pasajes.
5.  **Generar Documento**: Haz clic en "Generar Documento" para buscar y mostrar los versículos seleccionados en el área de resultados.
6.  **Copiar Versículos**: Usa el botón "Copiar Versículos al Portapapeles" para copiar el texto mostrado.

## Estructura de Datos (para RV1960 y KJV)

El texto bíblico está organizado en archivos JSON estructurados para un acceso fácil. La estructura de datos está modelada a partir del popular proyecto `aruljohn/Bible-kjv`.

Los datos suelen estar organizados de la siguiente manera dentro de los directorios `data/` específicos de cada versión (ej., `rv1960_output/` o `kjv_output/`):

1.  **Archivos de Libros Individuales (66 archivos)**: Cada libro de la Biblia tiene su propio archivo JSON (ej., `Genesis.json`, `Apocalipsis.json`).
    * **Estructura**:
        ```json
        {
          "book": "Génesis",
          "chapters": [
            {
              "chapter": 1,
              "verses": [
                {
                  "verse": 1,
                  "text": "En el principio creó Dios los cielos y la tierra."
                },
                // ...
              ]
            }
          ]
        }
        ```
    * **Convención de Nombres de Archivo**:
        * **Reina Valera 1960**: Los nombres de libros con varias palabras usan guiones bajos (ej., `1_Corintios.json`), mientras que las palabras individuales son directas (ej., `Genesis.json`). Los caracteres acentuados en los nombres de libros se normalizan para los nombres de archivo (ej., "Génesis" se convierte en "Genesis").
        * **King James Version**: Los nombres de libros con varias palabras se concatenan (ej., `1Corinthians.json`), y las palabras individuales son directas (ej., `Genesis.json`).

2.  **`books.json`**: Un simple array JSON que contiene los nombres de los 66 libros en su orden canónico. Este archivo se utiliza para llenar los menús desplegables de selección de libros.
    * **Ejemplo**:
        ```json
        [
            "1 Crónicas",
            "1 Corintios",
            // ...
        ]
        ```

3.  **`book_chapter_counts.json`**: Un objeto JSON que mapea el nombre de cada libro con su número total de capítulos. (Este archivo podría no usarse directamente en el actual `ible-dimensions.html`, pero forma parte de la descripción de la estructura de datos).
    * **Ejemplo**:
        ```json
        {
          "Génesis": 50,
          "Éxodo": 40,
          // ...
        }
        ```

## Créditos y Fuente

* **Datos del Texto Fuente**:
    * **Reina Valera 1960**: Los datos originales en texto plano se obtuvieron del repositorio `josevladimir/bible-json`.
    * **King James Version**: Los datos provienen generalmente de proyectos similares de textos bíblicos de dominio público.
* **Modelo de Estructura JSON**: El formato de salida de este proyecto se basa en la estructura del repositorio `aruljohn/Bible-kjv`.

## Licencia

Este proyecto se publica bajo la **Licencia MIT**. Consulta el archivo `LICENSE` para más detalles.

---