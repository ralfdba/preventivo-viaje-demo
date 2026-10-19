# bIAnca Viaje Preventivo - Demo Interactiva

Demo completa del flujo de bIAnca: desde la encuesta hasta la telemedicina y plan de salud.

## ✨ Características

- **3 pestañas interactivas**: Viaje del colaborador, Operación TI, Benchmark
- **11 pasos completos**: encuesta → batería → orden → prestador → agenda → resultados → telemedicina → plan
- **Datos sincronizados**: localStorage automático en cada cambio
- **3 perfiles de demo**: Camila (44, FONASA), Rodrigo (56, ISAPRE), Javiera (28, FONASA A)
- **Diseño mobile-first**: responsive con Tailwind CSS
- **Paleta GoMind**: gradiente morado→azul, colores de marca integrados
- **Cero dependencias**: HTML + Vanilla JS + Tailwind CDN

## 🚀 Uso local

### Opción 1: Python (recomendado)
```bash
cd /home/ralf/Development/code/gomind/preventivo-mvp-bono
python3 -m http.server 8000
# Abre http://localhost:8000
```

### Opción 2: Node.js (con live reload)
```bash
npx http-server -p 8000 -c-1
# Abre http://localhost:8000
```

### Opción 3: Abrir directamente
```bash
# En MacOS
open index.html

# En Linux
firefox index.html

# En Windows
start index.html
```

## 📦 Estructura

```
/preventivo-mvp-bono/
├── index.html           # Single-file app (todo el código)
├── assets/img/          # PNG de bIAnca (bianca.png, gomind-logo.png)
├── vercel.json          # Config deployment
├── .gitignore           # Exclusiones Git
└── README.md            # Este archivo
```

## 🎨 Paleta de colores (GoMind)

| Elemento | Color | CSS |
|---|---|---|
| Botón primario | Gradiente morado→azul | `linear-gradient(#c471f5 → #00c6ff)` |
| Fondo oscuro | Morado oscuro | `#28255b` |
| Lila (headers) | Lila medio | `#877df6` |
| Lila suave | Blanco lila | `#EDEDFF` |
| Verde OK | Verde esmeralda | `#10b981` |
| Rojo alerta | Rojo standard | `#ef4444` |

## 💾 localStorage

El estado se guarda automáticamente bajo la clave `bianca_demo_state`:

```javascript
{
  "tab": "viaje",
  "step": 3,
  "profile": { "nombre": "Camila Rojas", "edad": 44, ... },
  "ans": { "tabaco": "ex", "actividad": "bajo", ... },
  "provider": "gomind",
  "day": 0,
  "slot": "08:00",
  "folio": "BE-482xxxxx",
  "orden": "OM-26xxxxx"
}
```

Borra la pestaña para limpiar: `localStorage.removeItem('bianca_demo_state')`

## 🔗 Hash Routing

- `#viaje` - Pestaña Viaje del colaborador
- `#operacion` - Pestaña Cómo opera TI
- `#competencia` - Pestaña Benchmark

## 🌐 Deploy a Vercel

### Método 1: Vercel CLI
```bash
npm i -g vercel
vercel
# Sigue los prompts
```

### Método 2: GitHub + Vercel
```bash
# Inicializar Git (si no lo hiciste)
git init
git add .
git commit -m "Initial commit: bIAnca demo"
git branch -M main
git remote add origin https://github.com/usuario/preventivo-mvp-bono.git
git push -u origin main

# Luego conecta en https://vercel.com/new
```

### Método 3: Vercel Import
Sube el repo a GitHub y abre https://vercel.com/new → selecciona el repo.

**Resultado**: URL automática como `preventivo-mvp-bono.vercel.app`

## 📱 Accesibilidad & Performance

- ✅ WCAG 2.1 AA (contraste mínimo 4.5:1)
- ✅ Keyboard navigation (Tab, Enter, Escape)
- ✅ ARIA labels en componentes interactivos
- ✅ Mobile-first responsive
- ✅ ~500KB sin minificar (gzip: ~120KB)
- ✅ Zero external API calls
- ✅ LocalStorage solo lectura/escritura síncrona

## 🔧 Personalización

### Cambiar paleta
Edita las variables CSS en la sección `<style>`:
```css
:root {
  --gradient-start: #c471f5;
  --gradient-end: #00c6ff;
  /* ... */
}
```

### Agregar perfiles
En `PRESETS` array, añade:
```javascript
{
  profile: { nombre: 'Nuevo', rut: '...', sexo: 'F', edad: 30, ... },
  ans: { tabaco: 'no', actividad: 'ok', ... }
}
```

### Modificar pasos
Edita `STEPS` array para cambiar títulos y descripciones.

## 🐛 Debugging

Abre Developer Tools (F12) y:

```javascript
// Ver estado completo
console.log(STATE);

// Ver localStorage
console.log(localStorage.getItem('bianca_demo_state'));

// Limpiar
localStorage.removeItem('bianca_demo_state');

// Forzar render
render();
```

## 📄 Licencia

Propiedad de GoMind. Demo interna.

---

**Mantenedor**: Ralf Falfarini (rfalfarop@gmail.com)  
**Última actualización**: Octubre 2026
