# 🌊 Océano 3D

Simulación interactiva de un océano en 3D, autocontenida en un solo `index.html`
(Three.js + shaders GLSL propios, sin build ni dependencias locales).

## Cómo ejecutarlo

```bash
python3 -m http.server 8765
# y abre http://localhost:8765
```

(O cualquier otro servidor estático. Necesita conexión a internet la primera vez
para descargar Three.js y lil-gui desde CDN.)

## Controles

| Acción | Efecto |
| --- | --- |
| Arrastrar | Orbitar la cámara |
| Rueda del ratón | Zoom (baja hasta sumergirte: hay modo submarino) |
| Clic en el agua | Genera una onda expansiva con espuma |
| Tecla `H` | Mostrar / ocultar el panel |
| Tecla `C` | Mostrar / ocultar el catálogo de fauna |

## Características

- **Olas de Gerstner** calculadas en la GPU (5 ondas superpuestas) con normales
  analíticas, espuma en las crestas, fresnel, reflejo del cielo, destellos
  especulares de sol y luna, y micro-detalle procedural de la superficie.
- **Ciclo día/noche** completo: cielo físico (Preetham), sol, luna, estrellas,
  niebla y luces que se sincronizan; modo automático con velocidad ajustable.
- **Clima**: nubes a la deriva con viento, lluvia, relámpagos y niebla.
- **Velero detallado**: casco curvo tallado en V con quilla y bulbo, velas
  triangulares hinchadas por el viento, jarcia, caseta, banderín y farol
  nocturno; navega solo y cabecea/balancea según la pendiente real de las olas.
- **Fauna variada (16 especies)** con un sistema de aparición/desaparición y
  rarezas, para que sea entretenido salir a buscar animales:
  - *Aves*: gaviota, pelícano y albatros (planeador).
  - *En la superficie*: delfines, orcas y ballenas que saltan y rompen el agua
    (la ballena lanza su soplido).
  - *Bajo el agua*: bancos de sardinas, pez payaso, pez cirujano, atún, pez
    globo, tortuga marina, mantarraya, tiburón, medusa y pulpo.
  - Cada especie tiene su rareza (de *común* a *legendario ⭐⭐⭐*); las raras
    aparecen de vez en cuando y se marchan, así que hay que estar atento.
- **Catálogo de fauna avistada**: panel que registra qué especies has visto
  (y cuántas veces) y cuáles te faltan por descubrir, con aviso al avistar una
  nueva. Bucea y orbita la cámara para encontrarlas todas.
- **Burbujas** al sumergirse.
- **Modo submarino**: tinte, niebla densa y fondo oceánico al bajar la cámara
  bajo la superficie.
- **Sonido del mar** generado proceduralmente con WebAudio (sin archivos).
- **Panel de personalización** (lil-gui) con 5 preestablecidos: Mediodía
  tropical, Atardecer dorado, Tormenta, Noche estrellada y Amanecer sereno;
  más ~30 parámetros de olas, agua, cielo, ambiente, vida y rendimiento.
