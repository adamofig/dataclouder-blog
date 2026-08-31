---
title: "Despliegue Continuo con Cloudflare Pages y GitHub: Prueba en Vivo"
published: 2026-08-30
description: "Probando el flujo de CI/CD automatizado entre GitHub y Cloudflare Pages. Cada commit se compila y publica en el Edge global."
image: "assets/images/dataclouder-banner.png"
tags: ["Cloudflare", "GitHub", "CI/CD", "Astro"]
category: "Infraestructura"
draft: false
---

# Despliegue Continuo en el Edge con Cloudflare Pages ⚡☁️

Este artículo es una **prueba en vivo** del pipeline automatizado de integración y despliegue continuo (CI/CD) de **Dataclouder**.

## ¿Cómo funciona este flujo?

1. **Escritura y Edición:** Un redactor humano o un agente autónomo de IA (como Pristina) genera una nueva publicación en formato Markdown.
2. **Push a GitHub:** El contenido se envía al repositorio [adamofig/dataclouder-blog](https://github.com/adamofig/dataclouder-blog).
3. **Detección Automática:** Cloudflare Pages escucha el webhook de GitHub ante cada commit en la rama `main`.
4. **Compilación en el Edge:** Cloudflare ejecuta `pnpm build`, generando el HTML estático, el motor de búsqueda Pagefind y las optimizaciones de imagen en segundos.
5. **Distribución Global:** Los assets se propagan a cientos de centros de datos en todo el mundo sin intervención manual.

---

> [!TIP]
> Todo este pipeline fue aprovisionado 100% mediante API por **Anubis** 🐺⚖️ en el Starter Kit Día Cero de Control Markets.
