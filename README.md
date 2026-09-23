## Clases para el Formulario (Nintex Designer)

Para organizar visualmente el formulario, añade las siguientes clases en el apartado **Styling** (Clases CSS) dentro del diseñador de Nintex.

### Estructura y Grupos

| Clase CSS | Descripción y Uso |
| :--- | :--- |
| **`pk-header`** | Grupo de cabecera principal. Contiene la imagen corporativa, el nombre de la lista/biblioteca y el título del formulario. |
| **`pk-g1` a `pk-g10`** | Grupos principales. Asignan automáticamente un círculo numerado (del 01 al 10) al lado del título del grupo. |
| **`pk-subgroup`** | Grupo anidado. Aplica características de diseño secundarias a los grupos que están dentro de un grupo principal. |

### Clases Especiales

Se utilizan para aplicar características muy específicas a campos determinados.

| Clase CSS | Descripción y Uso |
| :--- | :--- |
| **`pk-label-tabla`** | Modifica color, fuente y tamaño de las letras. Pensada exclusivamente para los labels que se utilizan para asemejar tablas. |
| **`pk-title`** | Se asigna al label del nombre del título del formulario para aplicar el color corporativo correspondiente. |
| **`pk-logo`** | Configuración para la imagen del título. |
| **`pk-notF`** | Configuración para destacar inputs como error. |

---

## Aspectos a Personalizar en el CSS

### Paleta de Colores

Todos los colores del formulario se gestionan mediante variables CSS en la raíz del archivo para facilitar su edición.

| Variable CSS | Elementos a los que afecta |
| :--- | :--- |
| **`--pk-primary`** | Color principal (iconos, líneas horizontales, etc.). |
| **`--pk-primary-dark`** | Color principal oscuro (usado principalmente en el título). |
| **`--pk-primary-soft`** | Sombras, fondos y estado 'hover' del botón secundario, calendario y opciones. |
| **`--pk-btn-shadow-1`** | Sombreado del botón principal (Enviar). |
| **`--pk-btn-shadow-2`** | Sombreado del botón secundario (Cancelar). |
| **`--pk-ink`** | Color de la gran mayoría del texto (cabeceras, labels, checkboxes). |
| **`--pk-muted`** | Color de las letras del botón secundario (Cancelar). |
| **`--pk-line`** | Color muy suave para los bordes de algunos campos desplegables e iconos. |
| **`--pk-line-strong`** | Color suave pero más intenso para bordes de botones secundarios y campos deshabilitados. |
| **`--pk-disabled-bg`** | Color de fondo para los campos de edición deshabilitados. |
| **`--pk-disabled-fg`** | Color de texto para los campos de edición deshabilitados. |
| **`--pk-white`** | Color blanco puro utilizado en numerosos fondos. |
| **`--pk-grad-hero`** | Degradado corporativo utilizado en el fondo del título y el botón de enviar. |

### Configuración de la Imagen (Marca de Agua y Logo)

Se utiliza la misma imagen tanto para el título como para el fondo. Esta URL se configura en el **Apartado 2 (Marca de agua)** del archivo CSS, específicamente en la propiedad `background-image`.

> **Nota importante:** La URL tiene que apuntar a una imagen `.png` subida dentro de SharePoint **al nivel más alto del Site**. Esto es vital para garantizar que la imagen se pueda visualizar correctamente en los formularios del resto de Sites.