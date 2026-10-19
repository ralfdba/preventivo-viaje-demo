# 🚀 Quick Start

## ⚡ Ejecutar localmente (30 segundos)

### Opción 1: Python (más fácil)
```bash
cd /home/ralf/Development/code/gomind/preventivo-mvp-bono
python3 -m http.server 8000
```
Luego abre: **http://localhost:8000**

### Opción 2: Node.js
```bash
npx http-server -p 8000 -c-1
```

### Opción 3: Directamente
```bash
# En Mac
open /home/ralf/Development/code/gomind/preventivo-mvp-bono/index.html

# En Linux
firefox /home/ralf/Development/code/gomind/preventivo-mvp-bono/index.html
```

---

## 🌐 Publicar en Vercel (2 minutos)

### Paso 1: Instalar Vercel CLI
```bash
npm install -g vercel
```

### Paso 2: Deploy
```bash
cd /home/ralf/Development/code/gomind/preventivo-mvp-bono
vercel
```

Vercel te preguntará:
- **Project name**: `preventivo-mvp-bono` (Enter)
- **Project root**: `./` (Enter)
- **Build command**: (Enter - ya no necesita)
- **Output directory**: `./` (Enter)

**Resultado**: Tu demo está en vivo en `https://preventivo-mvp-bono.vercel.app` ✨

---

## 📋 Qué funciona

| Funcionalidad | Estado |
|---|---|
| 3 pestañas (Viaje, TI, Competencia) | ✅ |
| 11 pasos interactivos | ✅ |
| Cambiar entre perfiles | ✅ |
| localStorage automático | ✅ |
| Paleta GoMind | ✅ |
| Mobile-first responsive | ✅ |
| WCAG 2.1 AA | ✅ |
| Cero dependencias externas | ✅ |

---

## 🎨 Personalizar colores GoMind

Abre `index.html` y busca (línea ~27):

```css
:root {
  --gradient-start: #c471f5;  /* Morado GoMind */
  --gradient-end: #00c6ff;    /* Azul GoMind */
  --night: #28255b;           /* Morado oscuro */
  --gold: #877df6;            /* Lila headers */
  /* ... */
}
```

Cambia y guarda. El navegador se refresca automáticamente.

---

## 🔧 Cambiar perfiles

En `index.html`, busca `PRESETS` (línea ~288) y modifica:

```javascript
const PRESETS = [
  {
    profile: { nombre: 'TU NOMBRE', rut: 'TU RUT', sexo: 'F', edad: 35, ... },
    ans: { tabaco: 'no', actividad: 'ok', ... }
  }
];
```

---

## 💾 Limpiar localStorage

En Developer Tools (F12 → Console):
```javascript
localStorage.removeItem('bianca_demo_state');
location.reload();
```

---

## 📊 Analytics

La demo está lista para agregar:
- Google Analytics
- Hotjar
- Mixpanel
- O lo que uses en GoMind

Solo añade el script antes del `</body>`.

---

## ❓ Soporte

Cualquier duda:
- Lee `README.md` para más detalles
- Abre Developer Tools (F12) para debugging
- Ve el `console.log` de `STATE` para debugging de estado

---

**Listo para producción** ✅
