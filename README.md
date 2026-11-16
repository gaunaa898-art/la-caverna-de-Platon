# 🕳️ Alegoría de la Caverna – Experiencia WebAR Educativa

Aplicación de **Realidad Aumentada** sin marcadores para la asignatura de **Filosofía / Formación Ética y Ciudadana**.

Los estudiantes apuntan con el celular a una superficie real (mesa o piso), colocan la escena 3D de la caverna de Platón y tocan los objetos para descubrir su significado filosófico.

---

## 1. Información del proyecto

| Campo | Valor |
|-------|-------|
| **Nombre de la aplicación** | Alegoría de la Caverna (WebAR) |
| **Asignatura** | Filosofía / Formación Ética y Ciudadana |
| **Tema** | La Alegoría de la Caverna (Platón, *República*, Libro VII) |
| **Destinatarios** | 4.º / 5.º año de secundaria |
| **Objetivo de aprendizaje** | Comprender los niveles de conocimiento (eikasia, pistis, dianoia, noesis) y el sentido educativo de la liberación del prisionero a través de una experiencia espacial e interactiva. |
| **Conceptos principales** | Apariencia vs. realidad, sombras, mundo sensible, mundo de las Ideas, Idea del Bien, educación como liberación, dialéctica. |

---

## 2. Experiencia de Realidad Aumentada

### Escenario representado
Una caverna con:
- Prisioneros encadenados mirando la pared
- Fuego que proyecta sombras
- Sombras en la pared
- Estatuas / objetos que pasan detrás del muro
- Camino de salida hacia la luz
- El Sol (Idea del Bien) fuera de la caverna

### Objetos tridimensionales (creados con geometrías de Three.js)
1. **Prisioneros** – figuras sentadas con cadenas
2. **Fuego** – troncos + llamas con luz puntual
3. **Sombras** – siluetas oscuras en la pared
4. **Estatuas** – objetos que proyectan las sombras
5. **Salida** – escalones + flecha hacia la luz
6. **Sol** – esfera brillante con halo (Idea del Bien)

### Interacciones
Al tocar cualquier objeto aparece un panel con:
- Nombre del elemento
- Explicación filosófica clara y adaptada a secundaria

El estudiante puede rotar, acercar y alejar la escena (controles táctiles nativos de WebXR / OrbitControls en el modo fallback).

---

## 3. Requisitos técnicos cumplidos

- ✅ HTML + CSS + JavaScript puro
- ✅ Three.js (r170) + WebXR Device API
- ✅ Hit-test para detectar superficies (sin marcadores, sin QR, sin imágenes impresas)
- ✅ Indicador visual (retículo circular) que muestra dónde se colocará la escena
- ✅ Controles táctiles: colocar, rotar, explorar, tocar objetos
- ✅ Interfaz adaptable a pantallas de teléfonos Android
- ✅ Bibliotecas gratuitas (CDN de jsDelivr) – sin API keys ni registros
- ✅ Todas las geometrías generadas por código (sin modelos externos pagos)
- ✅ Listo para publicar en **GitHub Pages** (HTTPS automático)
- ✅ Comprobación de compatibilidad antes de iniciar
- ✅ Versión alternativa 3D interactiva (OrbitControls) cuando el dispositivo no soporta WebAR

### Requisitos del dispositivo
- Conexión **HTTPS** (obligatorio para WebXR)
- Navegador compatible: **Chrome** o **Edge** en Android (recomendado)
- Dispositivo con **ARCore** (la mayoría de los Android medianos/altos de los últimos años)
- Permiso de cámara

---

## 4. Cómo publicar en GitHub Pages (gratis)

1. Creá un repositorio nuevo en GitHub (público).
2. Subí todos los archivos de esta carpeta (`index.html`, `css/`, `js/`, `README.md`).
3. Andá a **Settings → Pages**.
4. En *Source* elegí la rama `main` (o `master`) y la carpeta `/ (root)`.
5. Guardá. En uno o dos minutos tendrás una URL del tipo:
   ```
   https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/
   ```
6. Abrí esa URL **desde el celular Android** con Chrome.

> **Importante:** GitHub Pages ya entrega el sitio por HTTPS, que es requisito de WebXR.

---

## 5. Cómo probar en local (desarrollo)

```bash
# Desde la carpeta del proyecto
npx serve .
# o
python -m http.server 8080
```

Luego abrí `http://localhost:8080` en el celular (misma red Wi-Fi) o usá un túnel HTTPS (ngrok, localtunnel, etc.) porque WebXR exige contexto seguro.

---

## 6. Cómo adaptar a otro tema de Filosofía / Ética

Todo el contenido pedagógico está centralizado en el objeto `SCENE_CONFIG` dentro de `js/main.js`:

```js
const SCENE_CONFIG = {
  title: "...",
  objectsInfo: {
    prisioneros: { title: "...", text: "..." },
    fuego: { title: "...", text: "..." },
    // etc.
  }
};
```

Podés:
1. Cambiar los textos de `objectsInfo`.
2. Reemplazar las funciones `createPrisoners()`, `createFire()`, etc. por nuevas geometrías.
3. Mantener la misma lógica de hit-test, colocación e interacción.

Ejemplos de otros escenarios posibles:
- Balanza de la Justicia + figuras de derechos humanos
- Árbol de las virtudes aristotélicas
- Mapa conceptual 3D de corrientes éticas
- Escena del “anillo de Giges”

---

## 7. Estructura del proyecto

```
web-ar-filosofia/
├── index.html          ← Página principal
├── css/
│   └── styles.css      ← Estilos responsive + UI
├── js/
│   └── main.js         ← Lógica Three.js + WebXR + fallback
└── README.md           ← Este archivo
```

---

## 8. Licencia y recursos

- Three.js → licencia MIT
- Todo el código de este proyecto se entrega como material educativo libre para uso en el aula.
- No utiliza ningún servicio pago ni requiere registro.

---

**Desarrollado para el aula · Realidad Aumentada educativa sin barreras técnicas.**
