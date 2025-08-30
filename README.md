# 📝 Tablero Minimalista

Un CMS simple y elegante con estética terminal para compartir enlaces y notas.

## ✨ Características

- **Diseño minimalista** con fuente monospace
- **Sistema de calificación** con estrellas (1-5 ⭐)
- **Enlaces personalizables** con texto opcional
- **Autenticación segura** vía Firebase
- **Tiempo real** - actualizaciones instantáneas
- **Responsive** - funciona en móvil y desktop
- **Sin servidor** - hosting gratuito con GitHub Pages

## 🚀 Demo

```
[Viernes 30/08/2025  10:30:15 p.m.] Esta es una nota de ejemplo [enlace] ⭐⭐⭐⭐
[Jueves 29/08/2025   09:15:42 a.m.] Otra entrada con enlace personalizado [ver más] ⭐⭐
```

## 🛠️ Crear tu propia versión

### 1. Configurar Firebase
1. Ve a [Firebase Console](https://console.firebase.google.com)
2. Crea un nuevo proyecto
3. Activa **Authentication** → Email/Password
4. Activa **Firestore Database** en modo de prueba
5. Copia tu configuración Firebase

### 2. Configurar código
1. Clona este repositorio
2. Edita `index.html` y `edit.html`
3. Reemplaza la configuración Firebase:
```javascript
const firebaseConfig = {
    apiKey: "tu-api-key",
    authDomain: "tu-proyecto.firebaseapp.com",
    projectId: "tu-project-id",
    // ... resto de tu configuración
};
```

### 3. Configurar reglas Firestore
En Firebase Console → Firestore → Reglas:
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /notas/{document} {
      allow read: if true;
      allow write: if request.auth != null;
    }
  }
}
```

### 4. Deploy en GitHub Pages
1. Crea un repositorio público en GitHub
2. Sube `index.html` y `edit.html`
3. Activa GitHub Pages en Settings → Pages
4. ¡Listo! Tu tablero estará en `https://tu-usuario.github.io/tu-repo`

## 📁 Estructura del proyecto

```
├── index.html          # Frontend público
├── edit.html           # Panel de administración  
└── README.md           # Este archivo
```

## 🎨 Personalización

### Cambiar título
```html
<title>Tu título aquí</title>
<h1>Tu título aquí</h1>
```

### Modificar colores
```css
:root { 
    --background-color: #ffffff; 
    --text-color: #000000; 
}
.timestamp { color: #a11d1d; }  /* Color de fechas */
.enlace { color: #0066cc; }      /* Color de enlaces */
```

### Ajustar fuente
```css
font-family: 'Roboto Mono', monospace;
```

## 🔐 Primer uso

1. Ve a `/edit.html` en tu sitio
2. Crea tu primera cuenta de admin
3. Empieza a agregar notas

## 💡 Características técnicas

- **Frontend**: HTML5 + CSS3 + JavaScript ES6
- **Backend**: Firebase (Auth + Firestore)
- **Hosting**: GitHub Pages (gratuito)
- **Sin dependencias** externas
- **Compatible** con todos los navegadores modernos

## 🤝 Contribuir

Si encuentras un bug o tienes una mejora:
1. Abre un Issue
2. Haz un Fork del proyecto
3. Crea tu propia versión

## 📄 Licencia

Este proyecto está bajo licencia MIT - puedes usarlo libremente para tus propios proyectos.

---

**¿Te gusta este proyecto?** Dale una ⭐ en GitHub
