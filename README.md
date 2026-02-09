# Invitación Interactiva - Es... TODOMADERA

Invitación web interactiva creada con Vue 3 para eventos de Es... TODOMADERA.

## 🚀 Características

- ✨ Diseño elegante y responsivo
- 📱 100% Mobile-friendly
- 🎨 Animaciones suaves
- 📍 Integración con Google Maps
- 💌 Confirmación de asistencia
- 🎁 Mesa de regalos
- 📧 Contacto por WhatsApp y Email
- 👔 Dress code visual

## 📋 Requisitos Previos

- Node.js (versión 16 o superior)
- npm o yarn

## 🛠️ Instalación

1. Navega a la carpeta del proyecto:
```bash
cd invitacion-todomadera
```

2. Instala las dependencias:
```bash
npm install
```

## 🏃‍♂️ Desarrollo

Ejecuta el servidor de desarrollo:
```bash
npm run dev
```

La aplicación estará disponible en `http://localhost:5173`

## 📦 Build para Producción

```bash
npm run build
```

Los archivos optimizados se generarán en la carpeta `dist/`

## 🚀 Despliegue en Vercel

### Opción 1: Desde la CLI de Vercel

1. Instala Vercel CLI:
```bash
npm install -g vercel
```

2. Ejecuta en la carpeta del proyecto:
```bash
vercel
```

3. Sigue las instrucciones en pantalla

### Opción 2: Desde GitHub

1. Sube el proyecto a un repositorio de GitHub
2. Ve a [vercel.com](https://vercel.com)
3. Haz clic en "New Project"
4. Importa tu repositorio
5. Vercel detectará automáticamente que es un proyecto Vite
6. Haz clic en "Deploy"

### Configuración de Vercel (vercel.json)

El proyecto ya incluye un archivo `vercel.json` con la configuración necesaria.

## ⚙️ Personalización

### Datos del Evento

Edita el archivo `src/App.vue` y modifica el objeto `eventData`:

```javascript
const eventData = ref({
  title: 'Tu título',
  message: 'Tu mensaje',
  date: 'Tu fecha',
  time: 'Tu hora',
  location: 'Tu ubicación',
  locationUrl: 'URL de Google Maps',
  // ... más configuraciones
})
```

### Colores y Estilos

Los colores principales están definidos en `src/style.css`:

```css
:root {
  --color-primary: #2c1810;
  --color-secondary: #8b6f47;
  --color-accent: #d4a574;
  --color-light: #f5f1ed;
}
```

### Fuentes

El proyecto usa Google Fonts:
- **Playfair Display** (títulos)
- **Montserrat** (cuerpo de texto)

Puedes cambiarlas editando el `index.html`

## 📱 Contacto

- **WhatsApp**: Edita el número en `eventData.confirmation.whatsapp`
- **Email**: Edita la dirección en `eventData.confirmation.email`

## 🎨 Secciones Incluidas

1. **Hero** - Portada principal con logo circular
2. **Mensaje** - Mensaje de bienvenida
3. **Detalles** - Fecha, hora y ubicación
4. **Dress Code** - Código de vestimenta con paleta de colores
5. **Regalos** - Mesa de regalos y opciones
6. **Confirmación** - Formulario de RSVP
7. **Footer** - Información de contacto

## 📄 Estructura del Proyecto

```
invitacion-todomadera/
├── src/
│   ├── App.vue          # Componente principal
│   ├── main.js          # Punto de entrada
│   └── style.css        # Estilos globales
├── public/              # Archivos estáticos
├── index.html           # HTML principal
├── vite.config.js       # Configuración de Vite
├── package.json         # Dependencias
├── vercel.json          # Configuración de Vercel
└── README.md           # Este archivo
```

## 🌐 Demo

Una vez desplegado en Vercel, tu invitación estará disponible en:
`https://tu-proyecto.vercel.app`

## 📝 Licencia

Este proyecto es de uso libre para Es... TODOMADERA

## 🤝 Soporte

Para soporte o consultas sobre la invitación, contacta al desarrollador.

---

Desarrollado con ❤️ para **Es... TODOMADERA**
