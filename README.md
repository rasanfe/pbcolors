# pbcolors 🎨

![PowerBuilder](https://img.shields.io/badge/PowerBuilder-2025-orange?style=flat-square&logo=appveyor&logoColor=white)
![Tipo](https://img.shields.io/badge/utilidad-selector%20de%20color-blueviolet?style=flat-square)
![Plataforma](https://img.shields.io/badge/Windows-10%2F11-0078D6?style=flat-square&logo=windows&logoColor=white)
![Blog](https://img.shields.io/badge/blog-rsrsystem-FF5722?style=flat-square&logo=blogger&logoColor=white)

> Un selector de colores hecho en PowerBuilder para tener mis tonos favoritos a mano y convertirlos al vuelo entre RGB, HTML y número `long`.

---

## 📋 ¿Qué es esto?

Esta es una de esas utilidades pequeñas que, sin hacer mucho ruido, acabas usando un montón. La monté para resolver un problema muy tonto pero muy real: cada vez que quería aplicar un color en una aplicación PowerBuilder tenía que pelearme con la conversión entre las distintas anotaciones.

Y es que en PowerBuilder el color se maneja como un número **`long`**, pero el diseño web (y casi todo el mundo) habla en **RGB** o en **hexadecimal HTML** (`#RRGGBB`). **pbcolors** os deja:

- **Elegir** cualquier color con el selector.
- **Convertirlo al instante** entre las tres notaciones: `RGB(r,g,b)`, HTML (`#RRGGBB`) y número `long`.
- **Copiar al portapapeles** el valor que necesitéis para pegarlo directamente en vuestro código.

Nada de matar moscas a cañonazos: una ventanita, sin dependencias externas, y a trabajar.

## ✨ Cómo funciona

La gracia didáctica de este ejemplo no es solo la app, sino **cómo está construida**. Está repartida en tres librerías para que veáis una arquitectura reutilizable de verdad:

- **`pbcolors.pbl`** → la aplicación en sí (`pbcolors.sra`) y la ventana principal `w_seleccionar_color`, donde vive toda la lógica de conversión. Aquí está el "cómo paso de `long` a RGB y a hexadecimal y vuelta".
- **`ancestors.pbl`** → objetos **ancestro** visuales reutilizables (`vs_cb_master`, `vs_em_master`, `vs_st_master`, `vs_htb_master`, la ventana base `w_ancestor`/`w_popup`…). La idea es que heredéis de ellos en vuestras propias apps.
- **`myobjects.pbl`** → objetos de usuario concretos que heredan de los ancestros (botones `vuo_cb_aceptar`/`vuo_cb_cancelar`, editmasks `vuo_em_number`/`vuo_em_rgb_number`/`vuo_em_string`, etiquetas `vuo_st_color`…).

Fijaos en el patrón: **ancestro genérico → objeto concreto**. Esa es la forma "de libro" de organizar componentes en PowerBuilder, y aquí lo tenéis en un ejemplo chiquitito y fácil de leer.

## 🛠️ Requisitos

- **PowerBuilder 2025** (compilado con el Runtime `25.0.0.3711`).
- **Windows 10/11**.
- Sin librerías de terceros ni instalaciones raras: clonáis y compila.

## ▶️ Cómo probarlo

1. Clona el repositorio (viene **en modo solución**: el workspace completo).
2. Abre `pbcolors.pbsln` (o el target `pbcolors.pbproj`) desde el IDE de PowerBuilder.
3. Compila y ejecuta. También tienes el `pbcolors.exe` ya generado para probarlo directamente.
4. Elige un color, juega con las conversiones y copia el formato que te interese.

## 🔗 Repo PowerBuilder

Tenéis el ejemplo publicado en modo solución aquí:
👉 <https://github.com/rasanfe/pbcolors>

---

> ¡Nos vemos en el próximo artículo! Y recuerda: en PowerBuilder, los límites solo están en nuestra imaginación. 🚀

📨 **Blog:** <https://rsrsystem.blogspot.com/>
