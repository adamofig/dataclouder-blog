# 🍥 Control Markets Blog & Guías (PoC)

Este es el sub-proyecto de blog estático y guías técnicas para **Control Markets**. Sirve como documentación de usuario y de plataforma, y a la vez como prueba de concepto para demostrar cómo los agentes de IA pueden escribir, actualizar y publicar contenidos en un flujo GitOps.

---

## 🚀 Base del Proyecto

Este blog está construido sobre la plantilla **[Fuwari](https://github.com/saicaca/fuwari)**, un tema de blog estático premium y de alto rendimiento diseñado con **Astro v5** y **Tailwind CSS**. 

### Características de la Base:
*   Transiciones de página fluidas mediante Swup.
*   Búsqueda estática instantánea integrada con Pagefind.
*   Diseño responsive y soporte para temas claro/oscuro.
*   Resaltado de sintaxis enriquecido para bloques de código mediante Expressive Code.

---

## ⚡ Comandos y Cómo Ejecutar el Blog

Todos los comandos se ejecutan desde la carpeta raíz del sub-proyecto `control-markets-blog`:

| Comando | Acción |
| :--- | :--- |
| `npm install` | Instala todas las dependencias del proyecto. |
| `npm run dev` | Inicia el servidor de desarrollo local en `http://localhost:4321`. |
| `npm run build` | Compila el sitio estático final en `./dist/` e indexa el contenido para Pagefind. |
| `npm run preview` | Previsualiza localmente el build de producción antes del despliegue. |
| `npm run format` | Da formato al código usando Biome. |

---

## 🛠️ Adaptaciones y Cambios para Control Markets

Para adaptar este blog genérico al ecosistema de **Control Markets**, realizamos los siguientes cambios de diseño y funcionalidad:

### 1. Personalización de Marca y Branding
*   **Esquema de Color**: Ajustamos el tono de color de acento (`hue: 75` en la escala OKLCH) en `src/config.ts` para reflejar el color ámbar/sunset característico de Control Markets.
*   **Identidad**: Cargamos el avatar corporativo `control-markets-logo.png` y modificamos los campos de perfil (`name`, `bio`, links de GitHub) para representar el proyecto.

### 2. Eliminación de Licencia Creative Commons por Defecto
*   Desactivamos la visualización obligatoria de la tarjeta de licencias Creative Commons (`CC BY-NC-SA 4.0`) cambiando `licenseConfig.enable: false` en `src/config.ts`. Esto quita el recuadro con el logotipo de CC al final de cada post para dar una imagen más limpia y profesional.

### 3. Integración de Call-To-Action (CTA) de Control Markets
*   Creamos un componente custom en `src/components/misc/PostFooterCTA.astro` que reemplaza el espacio de la licencia.
*   Este bloque ofrece enlaces útiles al final de cada artículo: un enlace directo para abrir el repositorio en **GitHub** y otro para iniciar/entrar a la aplicación web local de Control Markets (`http://localhost:8120`).

### 4. Limpieza del Pie de Página (Footer)
*   Modificamos `src/components/Footer.astro` para remover la firma de créditos *"Powered by Astro & Fuwari"*.
*   Tradujimos el texto de copyright del pie de página a español (*"Todos los derechos reservados"*).

### 5. Botón de Copiado de Documentación en Markdown
*   Agregamos un botón de **"Copiar Markdown"** junto a la cabecera (conteo de palabras y tiempo de lectura) en `src/pages/posts/[...slug].astro`.
*   Al compilar, Astro reconstruye dinámicamente el bloque de metadatos YAML original (Frontmatter) y lo concatena con el cuerpo de Markdown. El script del cliente decodifica de forma segura el texto en base64 para evitar errores con caracteres UTF-8 y saltos de línea, permitiendo al usuario copiar el archivo completo al portapapeles con un solo clic para usarlo en otras wikis o agentes.

### 6. Depuración de Contenidos Iniciales
*   Eliminamos los posts de ejemplo y placeholders del template original (`draft.md`, `markdown.md`, `markdown-extended.md`, `video.md`, `expressive-code.md`, y el directorio `guide/`) para conservar únicamente artículos y guías de valor reales del proyecto.
