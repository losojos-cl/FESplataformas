# Imágenes de fondo aleatorias para index_flotante.html

## Especificaciones
- **Formato**: WebP (recomendado) o JPG
- **Peso objetivo**: < 200 KB cada una
- **Dimensiones**: 1920x1080 mínimo (cover)
- **Tema**: Trabajo en plataformas, repartidores, ciudades latinoamericanas, texturas urbanas
- **Cantidad**: 6-10 imágenes

## Nombrado sugerido
```
bg01.webp
bg02.webp
bg03.webp
bg04.webp
bg05.webp
bg06.webp
...
```

## Implementación en index_flotante.html

```javascript
const bgImages = [
  'bg01.webp', 'bg02.webp', 'bg03.webp', 'bg04.webp', 'bg05.webp', 'bg06.webp'
];

// Persistencia por sesión (cambia al recargar)
const selected = bgImages[Math.floor(Math.random() * bgImages.length)];
document.getElementById('bg-layer').style.backgroundImage = `url(assets/bg/${selected})`;

// O persistencia diaria (localStorage)
// const today = new Date().toDateString();
// const stored = localStorage.getItem('bg-image');
// if (stored && stored.date === today) {
//   document.getElementById('bg-layer').style.backgroundImage = `url(assets/bg/${stored.image})`;
// } else {
//   const selected = bgImages[Math.floor(Math.random() * bgImages.length)];
//   localStorage.setItem('bg-image', JSON.stringify({ date: today, image: selected }));
//   document.getElementById('bg-layer').style.backgroundImage = `url(assets/bg/${selected})`;
// }
```

## Notas
- El elemento `#bg-layer` ya existe en index_flotante.html (línea 295)
- Tiene `z-index: -1` y `filter: grayscale(100%) brightness(0.075)` para legibilidad del mapa
- Las imágenes deben ser lo suficientemente oscuras o el filtro CSS las oscurecerá