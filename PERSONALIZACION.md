# 🎯 Guía Rápida de Personalización

## 📝 Datos que DEBES Personalizar

### 1. Información del Evento (src/App.vue)

Busca el objeto `eventData` y modifica:

```javascript
date: 'Sábado 15 de Marzo, 2025',           // ← Tu fecha
time: '18:00 hrs',                          // ← Tu hora
location: 'Santiago del Estero, Argentina', // ← Tu ubicación
locationUrl: 'https://maps.google.com/?q=', // ← URL de Google Maps completa
```

### 2. Mensaje de Bienvenida

```javascript
title: '¡Nos complace invitarte!',
message: 'Tu mensaje personalizado aquí...',
```

### 3. Información de Contacto

```javascript
confirmation: {
  whatsapp: '+5493858123456',              // ← Tu número de WhatsApp (con código de país)
  email: 'eventos@todomadera.com',         // ← Tu email
  deadline: '10 de Marzo, 2025',           // ← Fecha límite de confirmación
}
```

### 4. Mesa de Regalos

```javascript
gifts: {
  options: [
    {
      name: 'Transferencia',
      description: 'Alias: TODOMADERA.EVENTOS',  // ← Tu alias o CBU
    },
    {
      name: 'Mesa de Regalos',
      link: 'https://tu-tienda.com'              // ← URL de tu tienda
    }
  ]
}
```

### 5. Dress Code

```javascript
dressCode: {
  style: 'Elegante Casual',                      // ← Tu dress code
  description: 'Tu descripción...',
  colors: ['#2c1810', '#8b6f47', '#d4a574']     // ← Tus colores (formato HEX)
}
```

## 🎨 Personalización Visual

### Cambiar Colores Principales

Edita `src/style.css`:

```css
:root {
  --color-primary: #2c1810;    /* Marrón oscuro */
  --color-secondary: #8b6f47;  /* Marrón medio */
  --color-accent: #d4a574;     /* Dorado/Beige */
  --color-light: #f5f1ed;      /* Crema claro */
}
```

### Cambiar Fuentes

Edita `index.html` para usar otras fuentes de Google Fonts:

```html
<link href="https://fonts.googleapis.com/css2?family=TU_FUENTE&display=swap" rel="stylesheet">
```

Luego actualiza en `src/style.css`:

```css
:root {
  --font-heading: 'Tu Fuente', serif;
  --font-body: 'Tu Fuente', sans-serif;
}
```

## 🗺️ Configurar Ubicación en Google Maps

1. Ve a Google Maps
2. Busca tu ubicación exacta
3. Haz clic en "Compartir"
4. Copia el enlace
5. Pégalo en `locationUrl`

Ejemplo:
```javascript
locationUrl: 'https://maps.google.com/?q=-27.7833,-64.2667'
```

## 📱 Configurar WhatsApp

El número debe incluir:
- Código de país (ej: +54 para Argentina)
- Código de área
- Número sin espacios ni guiones

Ejemplo:
```javascript
whatsapp: '+5493858123456'  // ✅ Correcto
whatsapp: '+54 385 8123456' // ❌ Incorrecto (con espacios)
```

## 🚀 Deploy Rápido

### Opción 1: Vercel (Recomendado)

1. Sube tu proyecto a GitHub
2. Ve a [vercel.com](https://vercel.com)
3. Conecta tu repositorio
4. Deploy automático ✨

### Opción 2: Netlify

1. Arrastra la carpeta `dist/` a [netlify.com/drop](https://app.netlify.com/drop)
2. ¡Listo!

## ✅ Checklist Pre-Deploy

- [ ] Fecha y hora del evento actualizadas
- [ ] Ubicación y URL de mapa configuradas
- [ ] WhatsApp y Email correctos
- [ ] Mesa de regalos personalizada
- [ ] Dress code definido
- [ ] Mensaje de bienvenida personalizado
- [ ] Colores ajustados (opcional)
- [ ] Fecha límite de confirmación establecida
- [ ] Probado en móvil y desktop

## 🆘 Problemas Comunes

### El mapa no abre
- Verifica que la URL tenga `https://`
- Asegúrate de usar la URL completa de Google Maps

### WhatsApp no funciona
- Revisa que el número incluya el código de país
- No uses espacios ni caracteres especiales

### Los colores no se ven
- Usa formato HEX: `#RRGGBB`
- Asegúrate de tener 6 dígitos después del `#`

## 💡 Tips

- **Responsive**: La invitación es 100% mobile-friendly
- **Animaciones**: Scroll suave automático entre secciones
- **Accesibilidad**: Contraste de colores optimizado
- **Performance**: Carga rápida en cualquier dispositivo

---

¿Necesitas ayuda? Consulta el README.md completo
