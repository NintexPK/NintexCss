## Clases para el Formulario (Nintex Designer)

Para organizar visualmente el formulario, añade las siguientes clases en el apartado **Styling → CSS class** de cada control dentro del diseñador de Nintex.

### Estructura y Grupos

| Clase CSS | Descripción y Uso |
| :--- | :--- |
| **`pk-header`** | Grupo de cabecera principal. Contiene la imagen corporativa, el nombre de la lista/biblioteca y el título del formulario. Fondo con el degradado corporativo y cuerpo blanco. |
| **`pk-g1` a `pk-g10`** | Grupos principales. Asignan automáticamente un círculo numerado (del 01 al 10) al lado del título del grupo. |
| **`pk-subgroup`** | Grupo anidado. Aplica un diseño secundario (título más pequeño, sin numeración y fondo transparente) a los grupos que están dentro de un grupo principal. |

### Clases Especiales

Se utilizan para aplicar características muy específicas a campos determinados.

| Clase CSS | Descripción y Uso |
| :--- | :--- |
| **`pk-title`** | Se asigna al label del título del formulario para aplicar el tamaño y el color corporativo correspondiente. |
| **`pk-logo`** | Centra y dimensiona la imagen del logo dentro de la cabecera. |
| **`pk-label-tabla`** | Modifica color, fuente y tamaño de las letras. Pensada exclusivamente para los labels que se utilizan para asemejar tablas. |
| **`pk-notF`** | Destaca un campo como error o aviso. En **inputs** pinta fondo y borde en el color principal. En **labels** muestra un aviso con fondo suave y barra lateral, sin bloquear el envío. Normalmente se aplica mediante una **regla de formulario** (acción *CSS class*). |
| **`pk-req`** | Destaca un **desplegable** según tenga o no valor: borde en el color principal si está vacío y en verde suave (`--pk-ok`) cuando tiene valor. Funciona solo, sin reglas, y también en modo lectura. |

---

## Aspectos a Personalizar en el CSS

Todos los valores personalizables se gestionan mediante variables CSS en el **Apartado 1** (`:root`) del archivo. Para adaptar el formulario a otra marca basta con cambiar estas variables y la imagen de la marca de agua.

### Paleta de Colores

| Variable CSS | Elementos a los que afecta |
| :--- | :--- |
| **`--pk-primary`** | Color principal (iconos, líneas de títulos, numeración, foco de campos, opciones seleccionadas, etc.). |
| **`--pk-primary-dark`** | Color principal oscuro (título del formulario, subgrupos, cabeceras de secciones repetibles). |
| **`--pk-primary-light`** | Color principal claro. Se usa como final del degradado corporativo. |
| **`--pk-primary-soft`** | Tono muy suave del color principal: anillo de foco, fondos *hover* del botón secundario, calendario, opciones y avisos `pk-notF`. |
| **`--pk-shadow-tint`** | Color de las sombras corporativas, en formato `R,G,B` (sin `rgb()`). |
| **`--pk-ok`** / **`--pk-ok-soft`** | Verde suave para campos completados (clase `pk-req`): borde y halo. |
| **`--pk-ink`** | Color de la gran mayoría del texto (cabeceras, labels, checkboxes). |
| **`--pk-muted`** | Color del texto del botón secundario (Cancelar). |
| **`--pk-line`** | Color muy suave para líneas y bordes secundarios. |
| **`--pk-line-strong`** | Borde por defecto de los campos, botones secundarios y campos deshabilitados. |
| **`--pk-line-hover`** | Borde de los campos al pasar el ratón. |
| **`--pk-surface-tint`** | Tono casi blanco usado en el degradado de los campos y en la tabla editable. |
| **`--pk-disabled-bg`** | Color de fondo para los campos deshabilitados o en modo lectura. |
| **`--pk-disabled-fg`** | Color de texto para los campos deshabilitados o en modo lectura. |
| **`--pk-white`** | Color blanco puro utilizado en numerosos fondos. |

### Degradados y Sombras

| Variable CSS | Elementos a los que afecta |
| :--- | :--- |
| **`--pk-grad-hero`** | Degradado corporativo: fondo de la cabecera y botón principal (Enviar). |
| **`--pk-grad-surface`** | Degradado sutil del fondo de los campos. |
| **`--pk-grad-title-line`** | Línea degradada bajo los títulos de grupos y secciones repetibles. |
| **`--pk-btn-shadow-1`** / **`--pk-btn-shadow-2`** | Sombra del botón principal (Enviar) en reposo y al pasar el ratón. |
| **`--pk-shadow-*`** | Resto de sombras (formulario, tarjetas, popups, calendario, campos). |
| **`--pk-focus-ring`** | Halo que aparece alrededor de un campo al seleccionarlo. |

### Forma, Capas y Otros

| Variable CSS | Elementos a los que afecta |
| :--- | :--- |
| **`--pk-radius`** / **`--pk-radius-lg`** / **`--pk-radius-sm`** | Redondeo de esquinas (general, cabecera y elementos pequeños). |
| **`--pk-font`** | Tipografía del formulario (Open Sans, importada desde Google Fonts). |
| **`--pk-glass-1/2/3`** | Transparencias blancas de las tarjetas, cuerpos de grupo y adjuntos. |
| **`--pk-row-divider`** | Línea discontinua entre filas de las secciones repetibles. |
| **`--pk-row-alt`** | Fondo gris suave de las filas alternas de las secciones repetibles. |
| **`--pk-dropdown-max`** | Altura máxima de las listas desplegables (con scroll a partir de ahí). |
| **`--pk-z-top`** | Capa superior para desplegables, calendarios y popups. No suele ser necesario cambiarla. |

### Ancho del Formulario (versión ancha)

Configurado en el **Apartado 17**. Pensado para formularios que deben ocupar gran parte de la pantalla.

| Variable CSS | Descripción |
| :--- | :--- |
| **`--pk-form-width`** | Porcentaje del espacio disponible que ocupa el formulario (ej. `85%`). Controla el ancho en pantallas pequeñas y portátiles. |
| **`--pk-form-max`** | Ancho máximo en píxeles (ej. `1120px`). Evita que el formulario se estire de más en monitores grandes. Con `none` no hay tope. |

> En monitores grandes manda `--pk-form-max`. En pantallas pequeñas manda `--pk-form-width`.

### Marca de Agua

Se configura en el **Apartado 2** del archivo CSS, en las propiedades `background-image` y `background-size`.

- La imagen es un **mosaico ya girado** (PNG transparente) generado a partir del logo. El giro está hecho en la propia imagen, no por CSS, para que la marca de agua quede dentro del formulario y los desplegables y calendarios puedan salirse por debajo sin cortarse.
- El valor de `background-size` debe coincidir con el tamaño real de la imagen, o mantener su proporción si se quiere reducir. Si no se respeta la proporción, los logos se deforman.
- La intensidad se controla con **`--pk-watermark-opacity`**, y el velo blanco superior con **`--pk-watermark-veil`**.

| Marca | Imagen | `background-size` |
| :--- | :--- | :--- |
| Pikolin | `__bg__Logo_Pikolin_group.png` | `3498px 3498px` |
| Pardo | `logo-pardo-marca-agua-v2.png` | `1802px 901px` |
| Dunlopillo | `logo-dunlopillo-marca-agua-v2.png` | `2120px 2120px` |

> **Nota importante:** La URL tiene que apuntar a una imagen `.png` subida dentro de SharePoint **al nivel más alto del Site** (SiteAssets). Esto es vital para garantizar que la imagen se pueda visualizar correctamente en los formularios del resto de Sites.

> **Nota:** la variable `--pk-watermark-size` ya no se utiliza en el código actual. Se puede eliminar.

---

## Comportamientos Automáticos

Estas funcionalidades no requieren ninguna clase. Se aplican solas a todo el formulario.

| Elemento | Comportamiento |
| :--- | :--- |
| **Secciones repetibles** | Estilo de tarjeta igual que los grupos, filas alternas en gris suave (`--pk-row-alt`) y separador discontinuo entre filas. |
| **Desplegables y calendarios** | Se muestran por encima del resto del formulario y pueden salirse por la parte inferior, también dentro de secciones repetibles. |
| **Campos en modo lectura** | Fondo y texto grises (`--pk-disabled-*`). Se ocultan los iconos de fecha y persona. |
| **Adjuntos** | Caja de tarjeta con efecto al arrastrar. En modo lectura sin archivos muestra *"No files attached"*. |
| **Firmas** | Caja de firma y popup con los colores corporativos. |
| **Tabla editable (plugin)** | Los plugins `andys-table-v2` y `andys-table-v3` heredan los colores corporativos mediante sus variables `--nac-*` (Apartado 18). |
| **Animación** | Los grupos y campos aparecen con un ligero desplazamiento al cargar el formulario. |