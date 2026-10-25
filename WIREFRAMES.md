# Wireframes — Página "Nosotros" (Senderos Samaipata)

## 1. Arquitectura de información (mapa del sitio)
```
Inicio ─┬─ Tours ──── (anclas por tour) ─── Tarifas
        ├─ Galería
        ├─ Nosotros   ← NUEVA
        ├─ Contacto ─── Formulario de reserva ─── Gracias
        └─ (pie) Políticas de reserva
```

## 2. Wireframe de baja fidelidad — celular (390 px), primero
```
┌───────────────────────────┐
│ Senderos Samaipata        │  cabecera (no fija)
│ Inicio Tours Galería      │
│ Nosotros Contacto         │
├───────────────────────────┤
│ NOSOTROS (h1)             │
│ Texto de entrada (2-3     │
│ líneas: quiénes somos)    │
│                           │
│ Nuestra historia (h2)     │
│ ┃ ● 2014 …                │  línea de tiempo
│ ┃ ● 2017 …                │
│ ┃ ● 2020 …                │
│                           │
│ El equipo (h2)            │
│ ┌───────────────────────┐ │
│ │  (RM)  Rosa Méndez    │ │  tarjeta por persona
│ │  Fundadora…           │ │  (1 columna)
│ └───────────────────────┘ │
│ …                         │
│ Nuestro impacto (h2)      │
│ [ +4.000 viajeros ]       │  cifras apiladas
│ [ 1.200 árboles   ]       │
│                           │
│ Preguntas frecuentes (h2) │
│ ▸ ¿Necesito experiencia?  │  <details>
│ ▸ ¿Qué debo llevar?       │
│                           │
│ ( Reserva tu tour )       │  botón → contacto
│                   [WA]    │
└───────────────────────────┘
```

## 3. Wireframe — escritorio (1280 px)
```
┌────────────────────────────────────────────────────────────┐
│ Senderos Samaipata                Inicio Tours … Contacto  │ fija
├────────────────────────────────────────────────────────────┤
│ NOSOTROS                                                   │
│ Texto de entrada (máx. 65 caracteres por línea)            │
│                                                            │
│ Nuestra historia                                           │
│ ┃ ● 2014 …   ┃ ● 2017 …   (sigue siendo vertical)          │
│                                                            │
│ El equipo                                                  │
│ ┌──────┐ ┌──────┐ ┌──────┐ ┌──────┐   4 tarjetas en fila   │
│ │ (RM) │ │ (JM) │ │ (LM) │ │ (AV) │                        │
│ └──────┘ └──────┘ └──────┘ └──────┘                        │
│ Nuestro impacto                                            │
│ [ +4.000 ]   [ 1.200 ]   [ 8 ]          3 cifras en fila   │
│ Preguntas frecuentes (acordeón a todo el ancho)            │
└────────────────────────────────────────────────────────────┘
```

## 4. Decisiones (justifica cada una)
- Contenido primero: la historia antes que el equipo porque genera confianza.
- Avatares con iniciales: no tenemos fotos con permiso de uso; se reemplazarán por fotos reales.
- Preguntas frecuentes con `<details>`: accesibles con teclado sin JavaScript.
