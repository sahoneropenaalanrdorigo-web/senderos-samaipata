# Informe de calidad — Senderos Samaipata (solución de referencia)

Herramientas: Lighthouse 12.8 (móvil, servido por HTTP), html-validate 11 (reglas recomendadas + a11y), jigsaw.w3.org
(CSS), Playwright/Chrome (anchos 320-1280 px), DevTools.

## 1. Lighthouse (móvil)
| Página | Tema | Rendimiento | Accesibilidad | Buenas prácticas | SEO | LCP | CLS | Peso |
|---|---|---|---|---|---|---|---|---|
| index (antes) | oscuro | 99 | 95 | 100 | 100 | 2,0 s | 0 | 151 KiB |
| contacto (antes) | oscuro | 94 | 96 | 100 | 100 | 2,3 s | 0 | 458 KiB |
| index (después) | claro | 99 | 100 | 100 | 100 | 2,0 s | 0 | 152 KiB |
| index (después) | oscuro | 99 | 100 | 100 | 100 | 2,0 s | 0 | 152 KiB |
| contacto (después) | claro | 98 | 100 | 100 | 100 | 1,4 s | 0 | 475 KiB |
| nosotros | claro | 97 | 100 | 100 | 100 | 0,9 s | 0 | 25 KiB |
| tours | claro | 100 | 100 | 100 | 100 | 1,4 s | 0 | 28 KiB |
| version-bootstrap | claro | 92 | 100 | 100 | 100 | 3,0 s | 0 | 363 KiB |
| practica-auditoria (antes) | claro | 98 | 68 | 96 | 82 | 1,2 s | 0 | 31 KiB |
| practica-auditoria (después) | claro/oscuro | 100 | 100 | 100 | 100 | 0,9 s | 0 | 31 KiB |

(Los valores de rendimiento varían unos puntos entre ejecuciones; se reporta una ejecución representativa.)

## 2. Hallazgos y correcciones
| # | Hallazgo (herramienta) | Criterio | Corrección | Verificación |
|---|---|---|---|---|
| 1 | Botón dorado ilegible en modo oscuro: texto #e6ede8 sobre #f2c14e = 1,4:1 (Lighthouse, color-contrast) | WCAG 1.4.3 (4,5:1) | Token fijo --color-texto-sobre-sol (#1f2933) | Lighthouse accesibilidad 95 → 100 en oscuro |
| 2 | Insignia y hover de WhatsApp: blanco sobre #f4a582 = 1,99:1 en oscuro | WCAG 1.4.3 | Token fijo --color-acento-fondo (#9a3412, 6,9:1) | Idem |
| 3 | El mapa de contacto pesa ~300 KiB aunque tiene loading="lazy" (está a menos de la distancia de carga diferida) | Rendimiento | Aceptado (el mapa aporta valor); reto: fachada estática que cargue el iframe al tocarla | Peso de contacto documentado |
| 4 | Faltaban canonical, robots.txt, sitemap.xml y datos estructurados | SEO técnico | Agregados; gracias.html con noindex | Rich Results Test / validación del XML |
| 5 | practica-auditoria.html: 9 problemas (título vago, sin description, colores sin contraste, h1 → h4, img sin alt ni dimensiones, 'clic aquí', botón sin nombre, sin favicon → error 404 en consola) | WCAG 1.1.1, 1.3.1, 1.4.3, 2.4.4, 4.1.2; SEO; CLS | Comentarios numerados en el archivo | Lighthouse 68/96/82 → 100/100/100 |

Lección: la revisión manual de contraste de la clase 9 revisó el TEXTO sobre fondos, pero no los fondos de marca con
texto encima en modo oscuro. La auditoría automática lo encontró en segundos. Las dos cosas son necesarias.

## 3. Validación W3C
- HTML (9 páginas con 404.html): 0 errores (html-validate, recommended + a11y).
- CSS (estilos.css): 0 errores y 5 advertencias en jigsaw (propiedades modernas y variables, que el validador aún no evalúa).

## 4. Pruebas manuales
| Prueba | Resultado |
|---|---|
| Teclado: menú, formulario, FAQ (details), modal Bootstrap | ✔ foco visible en todo |
| Reflow 320 px (WCAG 1.4.10) en las 8 páginas | ✔ sin desplazamiento horizontal |
| Modo oscuro y movimiento reducido | ✔ contraste AA y sin animación |

## 5. SEO técnico
canonical ✔ · robots.txt ✔ · sitemap.xml ✔ · JSON-LD TravelAgency ✔ · 404.html ✔ · gracias.html noindex ✔

## 6. Conclusión
El sitio alcanza 100 en accesibilidad, buenas prácticas y SEO y 97-100 en rendimiento (móvil) en las páginas propias.
La versión Bootstrap es más pesada (363 KiB) y su LCP es 1 s mayor. Queda como mejora la fachada del mapa.
