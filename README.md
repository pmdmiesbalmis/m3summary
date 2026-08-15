# Catálogo Material 3 Compose (m3summary)

Un catálogo interactivo web y guía de referencia rápida para componentes de **Material Design 3 (M3)** en **Android Jetpack Compose**, con simulaciones visuales web en tiempo real y código Kotlin listo para copiar.

---

## 📋 Descripción del Proyecto

**Catálogo Material 3 Compose** es una aplicación web *offline-first* diseñada como chuleta y visualizador interactivo de componentes de la librería Material 3 para desarrollo Android con Jetpack Compose.

Para cada componente incluido, la aplicación ofrece:
1. **Agrupación y Clasificación por Uso**: Navegación organizada en 6 categorías temáticas con filtros rápidos por *pills*, botón para colapsar/expandir todas las secciones y buscador integrado por teclado (`Ctrl+K` / `/`).
2. **Consejos de Accesibilidad (A11y)**: Directrices prácticas para Jetpack Compose (gestión de `contentDescription`, `Modifier.semantics`, objetivos táctiles de 48dp, TalkBack y navegación por teclado).
3. **Previsualización Web Interactiva (Preview)**: Simulación visual en HTML/CSS con estilos, elevaciones, paleta de colores y efectos visuales de Material 3.
4. **Código Jetpack Compose (Kotlin)**: Implementación idiomática en Kotlin con resaltado de sintaxis, buenas prácticas de estado (`remember`, `rememberSaveable`, `animateItem`, etc.) y botón de copiado accesible con notificación Toast en región viva (`aria-live`).

---

## 🚀 Tecnologías Utilizadas

El proyecto está construido como una Single Page Application (SPA) ligera, modular y totalmente funcional sin conexión a internet (*offline*):

| Tecnología / Recurso | Versión / Detalle | Propósito |
|---|---|---|
| **HTML5 & Vanilla JavaScript** | Estándar ES6+ | Estructura de la aplicación, gestión de estado y renderizado dinámico del catálogo. |
| **Tailwind CSS** | Standalone Script (Local) | Framework utilitario para el diseño responsivo, interfaz minimalista con paleta de 4 valores de escala de grises y tipografía. |
| **PrismJS** | `prism.min.js` + `prism-kotlin.min.js` | Motor de resaltado de sintaxis para bloques de código Kotlin. |
| **Prism GHColors Theme** | `prism-ghcolors.css` | Tema claro inspirado en GitHub para la visualización del código fuente. |
| **Material Symbols Rounded** | Fuentes locales (`.ttf` + `.css`) | Iconografía oficial de Material Design 3. |
| **Google Fonts** | Roboto & Roboto Mono (Local) | Tipografías sans-serif y monoespaciadas para la interfaz y el código. |
| **CSS3 Custom Effects** | CSS nativo | Simulación de *Ripple Effect*, elevaciones y sombras M3, estilos personalizados de *Switch* y *Slider*, y barras de desplazamiento estilizadas. |

---

## 📦 Contenido y Componentes Incluidos

El catálogo cuenta con **39 componentes y patrones de diseño** clasificados en diversas categorías:

### 1. Estructura y Navegación
- **Scaffold**: Estructura base de pantalla (TopBar, BottomBar, FAB, Content con `innerPadding`).
- **Navigation Drawer**: Menú lateral deslizable (`ModalNavigationDrawer`, `ModalDrawerSheet`, `NavigationDrawerItem`).
- **Navigation Rail**: Barra vertical de navegación para pantallas medianas/expandidas (`NavigationRail`, `NavigationRailItem`).
- **App Bars**: Barras de aplicación superiores e inferiores (`TopAppBar`, `BottomAppBar`, `NavigationBar`).
- **Tabs**: Pestañas de navegación e indicadores activos (`TabRow`, `Tab`, `LeadingIconTab`).

### 2. Listas y Contenedores
- **Lazy Column (List)**: Lista vertical eficiente con soporte de claves (`key`) y animaciones (`animateItem`).
- **Lazy Grid**: Cuadrículas adaptativas (`LazyVerticalGrid`, `GridCells.Adaptive`).
- **List Item (M3)**: Elemento estándar de lista con ranuras para titular, subtítulo, avatar y acciones (`ListItem`).
- **Cards**: Tarjetas con elevación, bordes y variantes de color (`ElevatedCard`, `OutlinedCard`, `Card`).
- **Carousel**: Carruseles horizontales con máscaras dinámicas y tamaños variables (`HorizontalMultiBrowseCarousel`).
- **Horizontal Pager**: Carruseles y paginación horizontal con indicadores de página (`rememberPagerState`).
- **Swipe To Dismiss**: Deslizamiento de elementos para acciones rápidas o borrado (`SwipeToDismissBox`).
- **Bottom Sheet**: Hojas inferiores modales (`ModalBottomSheet`, `rememberModalBottomSheetState`).
- **Side Sheet**: Panel complementario lateral para pantallas grandes (`Surface`, `AnimatedVisibility`).
- **Dialog**: Ventanas modales y cuadros de diálogo de alerta (`AlertDialog`).

### 3. Botones y Acciones
- **Buttons**: Variantes completas (`Button`, `ElevatedButton`, `FilledTonalButton`, `OutlinedButton`, `TextButton`).
- **Floating Action Button (FAB)**: Botones de acción flotante estándar, pequeños y extendidos (`FloatingActionButton`, `ExtendedFloatingActionButton`).
- **FAB Menu (Speed Dial)**: Menú de acciones flotantes desplegables desde el FAB (`FloatingActionButtonMenu`, `SmallFloatingActionButton`).
- **Icon Buttons**: Botones de icono estándar, rellenos y tonales (`IconButton`, `FilledIconButton`, `FilledTonalIconButton`).
- **Split Button**: Botón compuesto con acción principal directa y menú desplegable (`Button`, `DropdownMenu`).
- **Segmented Button**: Botones segmentados continuos para selección única o múltiple (`SingleChoiceSegmentedButtonRow`, `MultiChoiceSegmentedButtonRow`, `SegmentedButton`).

### 4. Entradas de Texto y Selección
- **Text Fields**: Campos de texto con soporte de estados, validaciones, contraseñas y estilos (`TextField`, `OutlinedTextField`).
- **Custom Text Fields**: Campos de texto con formato personalizado, límites y transformaciones visuales.
- **Search Bar**: Barras de búsqueda interactivas con historial y sugerencias (`SearchBar`, `DockedSearchBar`).
- **Selection Controls**: Interruptores, casillas de verificación y botones de opción (`Switch`, `Checkbox`, `TriStateCheckbox`, `RadioButton`).
- **Slider**: Deslizadores continuos y discretos para selección de rangos y valores (`Slider`, `RangeSlider`).
- **Exposed Dropdown Menu**: Menús desplegables integrados en campos de texto (`ExposedDropdownMenuBox`).
- **Date & Time Pickers**: Selectores modales de fecha y hora (`DatePickerDialog`, `TimePicker`).

### 5. Feedback, Estado y Utilidades
- **Progress Indicators**: Indicadores de carga lineales y circulares determinados e indeterminados (`CircularProgressIndicator`, `LinearProgressIndicator`).
- **Pull To Refresh**: Gesto de arrastrar para recargar (`PullToRefreshBox`, `rememberPullToRefreshState`).
- **Badge**: Insignias numéricas y de notificación sobre iconos y elementos (`BadgedBox`, `Badge`).
- **Tooltip**: Mensajes informativos emergentes de texto simple o enriquecido con acciones (`TooltipBox`, `PlainTooltip`, `RichTooltip`).
- **Snackbar**: Mensajes emergentes temporales con soporte para acciones (`SnackbarHost`, `rememberSnackbarHostState`).
- **Menus & Dropdowns**: Menús contextuales y desplegables flotantes (`DropdownMenu`, `DropdownMenuItem`).
- **Chips**: Etiquetas de filtro, sugerencia, asistencia y entrada (`FilterChip`, `AssistChip`, `InputChip`, `SuggestionChip`).
- **Horizontal Divider**: Separadores horizontales de contenido (`HorizontalDivider`).
- **Vertical Divider**: Separadores verticales para columnas y barras de herramientas (`VerticalDivider`).
- **AsyncImage (Coil)**: Carga asíncrona de imágenes remotas mediante la librería Coil en Compose.

---

## 📁 Estructura del Directorio

```plaintext
m3summary/
├── index.html                  # Aplicación principal SPA (interfaz, estilos y datos)
├── README.md                   # Documentación del proyecto
├── AGENTS.md                   # Directivas y notas de desarrollo
└── assets/                     # Recursos locales (Offline)
    ├── css/
    │   └── prism-ghcolors.css      # Tema de resaltado de código (GitHub Colors)
    ├── fonts/
    │   ├── fonts-local.css         # Importación de fuentes locales Roboto
    │   ├── material-symbols-local.css # Iconos Material Symbols locales
    │   ├── MaterialSymbolsRounded.ttf
    │   ├── Roboto-*.ttf
    │   └── RobotoMono-*.ttf
    ├── images/
    │   └── sample-image.svg        # Recursos gráficos vectoriales locales
    └── js/
        ├── prism.min.js            # Motor de sintaxis Prism
        ├── prism-kotlin.min.js     # Gramática de Kotlin para Prism
        └── tailwind.js             # Tailwind CSS Standalone
```

---

## 💻 Modo de Uso

1. **Abrir localmente**:
   Basta con abrir el archivo [index.html](file:///D:/Git/m3summary/index.html) directamente en cualquier navegador web moderno (doble clic o mediante la extensión Live Server de VS Code / IDE).
2. **Navegación**:
   - Utiliza la barra lateral para buscar y seleccionar cualquier componente.
   - En dispositivos móviles, utiliza el botón de menú superior para desplegar el panel de componentes.
3. **Copiar código**:
   - Pulsa el botón **"Copiar"** en la esquina superior derecha del bloque de código para transferir el fragmento de Kotlin directamente a tu portapapeles.
