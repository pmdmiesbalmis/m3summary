# AGENTS.md — Guía y Directivas de Desarrollo para Agentes

Este documento contiene las directrices, reglas de arquitectura y estándares de desarrollo que todo agente de IA o desarrollador debe seguir al trabajar en este repositorio.

---

## 📌 1. Filosofía del Proyecto y Arquitectura

- **Tipo de Proyecto**: Catálogo interactivo web (Single Page Application - SPA) de componentes de **Material Design 3 (M3)** para **Android Jetpack Compose**.
- **Propósito**: Servir de referencia visual y chuleta de código con previsualizaciones interactivas en HTML/CSS y fragmentos de código Kotlin listos para copiar.
- **Sin paso de compilación (Zero-Build)**: La aplicación funciona directamente abriendo `index.html` en el navegador, sin necesidad de empaquetadores (Vite, Webpack, etc.) ni servidores de compilación obligatorios.

---

## 🛑 2. Regla Fundamental: Aplicación Offline-First

> [!IMPORTANT]
> **ESTA APLICACIÓN ES ESTRICTAMENTE OFFLINE-FIRST.**
> Está terminantemente prohibido incluir enlaces a CDNs externos (`https://cdn...`, `https://fonts.googleapis.com...`, `https://cdnjs.cloudflare.com...`, etc.) en el código fuente.

### Directrices de Dependencias y Recursos:
1. **Librerías y Scripts (`assets/js/`)**:
   - Si se necesita una nueva librería JavaScript (o actualizar una existente), debe descargarse o guardarse localmente en la carpeta [`assets/js/`](file:///D:/Git/m3summary/assets/js).
   - Se debe enlazar siempre mediante ruta relativa (ej. `<script src="assets/js/mi-libreria.js"></script>`).

2. **Estilos y Temas (`assets/css/`)**:
   - Todos los archivos CSS de terceros o temas deben residir en [`assets/css/`](file:///D:/Git/m3summary/assets/css).

3. **Fuentes e Iconos (`assets/fonts/`)**:
   - Las tipografías y fuentes de iconos (como Material Symbols o Roboto) deben servirse desde [`assets/fonts/`](file:///D:/Git/m3summary/assets/fonts) con sus correspondientes archivos `@font-face` locales (`fonts-local.css`, `material-symbols-local.css`).

4. **Imágenes y Multimedia (`assets/images/` u otros)**:
   - Cualquier imagen, ilustración o recurso multimedia necesario debe generarse o descargarse en una carpeta local bajo [`assets/`](file:///D:/Git/m3summary/assets).
   - No usar URLs de imágenes remotas (excepto en los ejemplos de código Kotlin como cadenas de texto demostrativas para `AsyncImage`).

---

## 🧱 3. Estructura de Componentes en `index.html`

Todos los componentes del catálogo se definen dentro del array `components` en [`index.html`](file:///D:/Git/m3summary/index.html). Al agregar o modificar un componente, se debe respetar la siguiente estructura:

```javascript
{
    id: 'identificador_unico',            // ID en minúsculas y sin espacios
    name: 'Nombre del Componente',         // Nombre legible para el menú y título
    icon: 'nombre_icono_material',         // Nombre del icono en Material Symbols Rounded
    description: 'Descripción concisa...',  // Resumen del propósito y uso en Material 3
    webPreview: `
        <!-- HTML + Tailwind para simular visualmente el componente -->
        <div class="..."> ... </div>
    `,
    kotlinCode: `// Código Jetpack Compose en Kotlin (idiomático y limpio)
@Composable
fun MiComponente() {
    // ...
}`
}
```

---

## 🎨 4. Estándares de Diseño y Previsualización Web (`webPreview`)

- **Fidelidad Material 3**: Utilizar los tokens de color configurados en Tailwind (`bg-m3-primary`, `text-m3-onPrimaryContainer`, `border-m3-outline`, etc.) y las clases de sombras y efectos (`.m3-card`, `.ripple`, `.m3-switch`, etc.).
- **Responsividad**: Las simulaciones deben ser contenidas, autocontenidas y verse correctamente en cualquier resolución de pantalla.
- **Interacciones**: En la medida de lo posible, simular estados (hover, active, cambios simples de estado en inputs o switches).

---

## 📱 5. Estándares de Código Kotlin (`kotlinCode`)

- **APIs Oficiales de Material 3**: Usar siempre las APIs modernas de `androidx.compose.material3` (por ejemplo, `HorizontalDivider` en lugar de `Divider`, `Scaffold` con `innerPadding`, `TopAppBar`, etc.).
- **Gestión de Estado Idiomática**: Incluir `remember`, `rememberSaveable`, `derivedStateOf` o estados de scroll/pager según corresponda para que el código sea directamente utilizable en proyectos reales.
- **Formato y Limpieza**: Mantener una indentación clara a 4 espacios y comentarios concisos que expliquen partes clave.

---

## 🛠️ 6. Flujo de Trabajo para Nuevas Funcionalidades o Cambios

1. **Adición de nuevos componentes**:
   - Añadir el objeto correspondiente en el array `components` de [`index.html`](file:///D:/Git/m3summary/index.html).
   - Asegurarse de invocar `Prism.highlightAll()` tras cualquier actualización del DOM para mantener el coloreado de sintaxis.
2. **Actualización de Documentación**:
   - Cuando se agreguen nuevos componentes o se modifique la arquitectura, actualizar siempre [`README.md`](file:///D:/Git/m3summary/README.md) reflejando los cambios.
3. **Comprobación**:
   - Verificar la navegación tanto en vista de escritorio como en móvil (botón de menú y drawer lateral).
   - Comprobar que la función de copiado al portapapeles (`copyCode`) y el Toast sigan operativos.

---

## 🔗 Fuentes de Información y Referencias Oficiales

El agente debe consultar estas fuentes para verificar firmas de funciones, parámetros vigentes y nuevas APIs de Material 3:

- **AndroidX Compose Material 3 Package Summary**: https://developer.android.com/reference/kotlin/androidx/compose/material3/package-summary
- **Adaptive Material 3 Layouts**: https://developer.android.com/develop/ui/compose/layouts/adaptive/get-started-with-adaptive-apps
- **Exmanples de Material 3 en Jetpack Compose**: https://cs.android.com/androidx/platform/frameworks/support/+/androidx-main:compose/material3/material3/samples/src/main/java/androidx/compose/material3/samples/
- **Material Design 3 Components**: https://developer.android.com/develop/ui/compose/components
