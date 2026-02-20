# Investigacion: Flujo Markdown a LaTeX para CVs Profesionales

> Fecha: 2026-02-20

## Indice

1. [Que es un CV con formato profesional](#1-que-es-un-cv-con-formato-profesional)
2. [Templates LaTeX para CVs](#2-templates-latex-para-cvs)
3. [Compatibilidad con ATS](#3-compatibilidad-con-ats)
4. [Conversion de Markdown a LaTeX](#4-conversion-de-markdown-a-latex)
5. [Herramientas de conversion](#5-herramientas-de-conversion)
6. [Pipeline completo: MD a LaTeX a PDF](#6-pipeline-completo-md-a-latex-a-pdf)
7. [Overleaf: compilacion y flujo de trabajo](#7-overleaf-compilacion-y-flujo-de-trabajo)
8. [Alternativas a Overleaf](#8-alternativas-a-overleaf)
9. [Proyectos open-source de referencia](#9-proyectos-open-source-de-referencia)
10. [Recomendacion para este proyecto](#10-recomendacion-para-este-proyecto)

---

## 1. Que es un CV con formato profesional

### Estandares de la industria

Un CV profesionalmente formateado cumple estas convenciones:

- **Layout**: Una sola columna, orden cronologico inverso. Fechas alineadas a la derecha.
- **Fuentes**: Tipografias estandar (Arial, Calibri, Times New Roman, Helvetica, Lato) a 10-12pt.
- **Margenes**: Entre 0.5 y 1 pulgada en todos los lados.
- **Extension**: Una pagina (fuertemente preferido), maximo dos. El punto ideal es 475-600 palabras. Candidatos con CVs de una pagina reciben el doble de invitaciones a entrevistas.
- **Encabezados de seccion**: Labels convencionales que los ATS reconocen: "Professional Experience", "Skills", "Education", "Certifications".
- **Orden de secciones**: Informacion de contacto arriba, luego resumen profesional, experiencia, habilidades, educacion, certificaciones.
- **Contenido**: Cada bullet debe empezar con un verbo de accion (Led, Built, Automated, Improved) e incluir metricas cuantificadas (%, $, tiempo ahorrado, usuarios).

### Formato de archivo: PDF vs DOCX

El consenso en 2025-2026:

| Formato | Cuando usar |
|---------|-------------|
| **PDF** | Al enviar por email, cuando no se especifica formato, para consistencia visual. Opcion por defecto. |
| **DOCX** | Cuando el posting lo pide explicitamente, para maxima compatibilidad con ATS legacy. |

**Mejor practica**: Tener ambos formatos listos. Nombrar archivos como `Nombre-Apellido-Puesto-2026.pdf`.

### Por tipo de empresa

| Aspecto | FAANG / Tech | Consulting (MBB) | Corporativo general |
|---------|-------------|-------------------|---------------------|
| Paginas | 1 | 1 (estricto) | 1-2 |
| Layout | Columna unica, limpio | Columna unica, preciso | Columna unica |
| Creatividad | Ninguna | Ninguna (penalizada) | Minima |
| Contenido clave | Skills tecnicos, impacto | Liderazgo, pedigree | Logros relevantes |
| Metricas | Requeridas | Requeridas | Fuertemente preferidas |
| ATS optimizado | Esencial | Menos relevante | Esencial |

---

## 2. Templates LaTeX para CVs

### Templates principales

#### Jake's Resume (Recomendado para ATS)

- **Overleaf**: [overleaf.com/latex/templates/jakes-resume/syzfjbzwjncs](https://www.overleaf.com/latex/templates/jakes-resume/syzfjbzwjncs)
- **GitHub**: [github.com/jakegut/resume](https://github.com/jakegut/resume)
- **Compilador**: pdfLaTeX
- **Layout**: Columna unica, una pagina
- **ATS Score**: 98+ en tests de compatibilidad
- **Licencia**: MIT
- **Mejor para**: Roles tech/ingenieria. El template LaTeX mas usado.

#### moderncv

- **CTAN**: [ctan.org/pkg/moderncv](https://ctan.org/pkg/moderncv)
- **GitHub**: [github.com/xdanaux/moderncv](https://github.com/xdanaux/moderncv)
- **Version**: v2.4.1
- **Compilador**: pdfLaTeX, LuaLaTeX, XeLaTeX
- **5 estilos**: `casual`, `classic`, `banking`, `oldstyle`, `fancy`
- **8 colores**: `black`, `blue`, `burgundy`, `green`, `grey`, `orange`, `purple`, `red`
- **Comandos clave**:
  - `\cventry{years}{title}{employer}{location}{grade}{description}`
  - `\moderncvstyle{banking}`, `\moderncvcolor{blue}`
- **Mejor para**: CVs academicos, internacionales, multi-pagina.

#### Awesome-CV

- **GitHub**: [github.com/posquit0/Awesome-CV](https://github.com/posquit0/Awesome-CV) (12k+ stars)
- **Overleaf**: [overleaf.com/latex/templates/awesome-cv/dfnvtnhzhhbm](https://www.overleaf.com/latex/templates/awesome-cv/dfnvtnhzhhbm)
- **Compilador**: XeLaTeX (obligatorio)
- **Fuentes**: Roboto, Source Sans Pro, FontAwesome 6
- **Licencia**: CC BY-SA 4.0
- Incluye soporte Docker y Makefile
- **Mejor para**: Roles profesionales/tech, layout estilo LinkedIn.

#### AltaCV

- **GitHub**: [github.com/liantze/AltaCV](https://github.com/liantze/AltaCV)
- **Version**: v1.7.4 (2025)
- **Compilador**: pdfLaTeX, XeLaTeX, LuaLaTeX
- **Diseno**: Dos columnas (inspirado en el CV de Marissa Mayer)
- Usa el paquete `accsupp` para mejor compatibilidad ATS
- **Mejor para**: CVs visualmente atractivos cuando se envian directamente.

#### Deedy-Resume

- **GitHub**: [github.com/deedy/Deedy-Resume](https://github.com/deedy/Deedy-Resume)
- **Compilador**: XeTeX (obligatorio)
- **Layout**: Dos columnas asimetricas, una pagina
- **Variante OpenFonts**: Usa Lato Light y Raleway ExtraLight (fuentes libres)
- **Nota**: El layout de dos columnas NO es ATS-friendly. Existe una variante de columna unica.

#### europecv / europasscv

- **CTAN**: [ctan.org/pkg/europecv](https://ctan.org/pkg/europecv)
- Implementacion del Europass CV recomendado por la Comision Europea
- Localizado en 23+ idiomas de la UE
- **Mejor para**: Aplicaciones en la Union Europea.

### Tabla comparativa

| Template | Compilador | Columnas | ATS-friendly | Ideal para |
|----------|-----------|----------|:------------:|------------|
| Jake's Resume | pdfLaTeX | 1 | Si | Tech, maximo ATS |
| moderncv (banking) | pdfLaTeX | 1 | Si | Academico, internacional |
| Awesome-CV | XeLaTeX | 1 | Si | Profesional, visual |
| AltaCV | pdfLaTeX+ | 2 | Parcial | Visual, envio directo |
| Deedy | XeTeX | 2 | No | Estudiantes CS |
| europecv | pdfLaTeX | 1 | Si | Aplicaciones UE |

---

## 3. Compatibilidad con ATS

### El problema

**97.8% de las Fortune 500** usan ATS (2025), proyectado a 99.5% en 2026. El 99.7% de los reclutadores usan filtros de keywords.

Los PDFs generados con LaTeX pueden causar problemas si:
1. **Encoding**: Caracteres especiales rompen el parsing sin UTF-8 consistente
2. **Fuentes no embebidas**: Sin fuentes embebidas, el ATS no puede leer el texto
3. **Layouts complejos**: Dos columnas, graficos, headers no estandar confunden los parsers
4. **Mapeo Unicode faltante**: Sin glyph-to-Unicode mapping, el texto extraido sale corrupto

### Fixes criticos en LaTeX

**Lineas obligatorias en el preambulo**:
```latex
\input{glyphtounicode}
\pdfgentounicode=1
```
Estas dos lineas aseguran que el PDF sea completamente mapeado a Unicode y legible por maquinas. Es el fix mas importante para compatibilidad ATS.

**Fuentes para ATS**:
- Usar paquetes `lmodern`, `charter`, o `helvet`
- O fuentes del sistema via XeLaTeX/LuaLaTeX: Arial, Calibri, Times New Roman
- Siempre embeber fuentes en el PDF

**Reglas de layout**:
- Layout de columna unica (fuertemente preferido)
- Sin iconos o imagenes para transmitir informacion
- Titulos de seccion estandar: "Experience", "Skills", "Education"

### Como testear tu CV LaTeX

1. **Workday**: Subir el PDF a una aplicacion Workday y verificar que los campos se pre-llenan correctamente
2. **ATS parsers gratuitos**: Jobscan, ResumeWorded analizan tu PDF
3. **Test de copy-paste**: Abrir el PDF, seleccionar todo, pegar en texto plano. Si es coherente, el ATS lo parseara bien

---

## 4. Conversion de Markdown a LaTeX

### Pandoc (herramienta principal)

Pandoc lee un archivo Markdown, lo parsea a un AST interno, y lo escribe en el formato destino. Para LaTeX:

- `# Heading` se convierte en `\section{Heading}`
- `## Subheading` se convierte en `\subsection{Subheading}`
- `**bold**` se convierte en `\textbf{bold}`
- Listas bullet se convierten en `\begin{itemize}...\end{itemize}`
- Variables YAML del metadata se interpolan en el template

#### Comandos basicos

```bash
# Markdown a LaTeX standalone
pandoc resume.md -f markdown -t latex -s -o resume.tex

# Markdown directo a PDF (pandoc invoca pdflatex internamente)
pandoc resume.md -o resume.pdf

# Con template personalizado y XeLaTeX
pandoc resume.md \
  -f markdown+yaml_metadata_block \
  --template cv-template.tex \
  --pdf-engine=xelatex \
  -o resume.pdf
```

#### Opciones clave

| Opcion | Proposito |
|--------|-----------|
| `-f markdown+yaml_metadata_block` | Formato de entrada con soporte YAML |
| `-t latex` | Formato de salida (LaTeX) |
| `-s` / `--standalone` | Documento completo con preambulo |
| `--template=FILE` | Template `.tex` personalizado |
| `--pdf-engine=xelatex` | Motor LaTeX para salida PDF |
| `-V KEY=VAL` | Pasar variables al template |
| `--lua-filter=FILE` | Aplicar filtro Lua al AST |

#### Templates Pandoc para CVs

Un template pandoc es un archivo `.tex` normal con variables de pandoc delimitadas por `$...$`:

```latex
\documentclass[11pt]{article}
\usepackage[margin=1in]{geometry}
\usepackage{hyperref}

\begin{document}

$if(name)$
{\LARGE\bfseries $name$} \\
$endif$
$if(email)$
\href{mailto:$email$}{$email$}
$endif$

\vspace{1em}

$body$

\end{document}
```

Con el Markdown correspondiente:

```yaml
---
name: "Juan Perez"
email: "juan@example.com"
phone: "+1-555-0123"
---

# Experience

### Senior Software Engineer
#### Acme Corp | 2020 -- Present

- Built distributed systems
- Led team of 5 engineers
```

### El problema del mapeo MD a CV-class

Markdown estandar (`# heading`, bullets) no mapea directamente a comandos especializados de clases CV como `\cventry{}{}{}{}{}{}` o `\cvsection{}`. Soluciones:

#### Enfoque A: Filtro Lua

```lua
-- cv-filter.lua
function Header(el)
  if FORMAT:match 'latex' then
    local content = pandoc.utils.stringify(el)
    if el.level == 1 then
      return pandoc.RawBlock('latex', '\\cvsection{' .. content .. '}')
    elseif el.level == 2 then
      return pandoc.RawBlock('latex', '\\cvsubsection{' .. content .. '}')
    end
  end
end
```

```bash
pandoc resume.md --lua-filter cv-filter.lua --template awesome-cv.tex -o resume.pdf
```

#### Enfoque B: LaTeX crudo en Markdown

Embeber comandos LaTeX directamente en el Markdown. Pandoc pasa LaTeX crudo sin modificar a la salida.

#### Enfoque C: Script hibrido

Un script Python o shell que pre-procesa el Markdown a LaTeX mediante reemplazos de strings, luego compila con pdflatex.

### Limitaciones de Pandoc para CVs

1. No hay mapeo nativo a comandos de clases CV
2. Sin soporte de layouts multi-columna
3. Elementos visuales complejos (sidebars, barras de skills, iconos) requieren LaTeX crudo
4. Variables YAML son strings planos; datos estructurados requieren loops y YAML cuidadoso

---

## 5. Herramientas de conversion

### Paquetes Node.js

| Paquete | Descripcion | Nota |
|---------|-------------|------|
| [zmarkdown](https://www.npmjs.com/package/zmarkdown) | MD a LaTeX nativo via `rebber` (remark/MDAST) | Unica conversion nativa en Node.js |
| [pandocjs](https://www.npmjs.com/package/pandocjs) | Wrapper pandoc con descarga automatica del binario | No requiere pandoc pre-instalado |
| [node-pandoc](https://www.npmjs.com/package/node-pandoc) | Bridge entre pandoc CLI y Node.js | Requiere pandoc instalado |
| [pdc](https://github.com/pvorb/node-pdc) | Wrapper fino de pandoc para Node.js | Requiere pandoc instalado |

### Herramientas especializadas para CVs

| Herramienta | Lenguaje | Enfoque |
|-------------|----------|---------|
| [resume-latex](https://github.com/jfhack/resume-latex) | Python | Parsea MD, emite LaTeX con formato resume. Docker image incluye lualatex + pdflatex |
| [mderncv](https://github.com/manualbashing/mderncv) | Python (panflute) | Filtro pandoc que mapea MD a comandos moderncv |
| [pandoc-moderncv](https://github.com/barraq/pandoc-moderncv) | Pandoc | Theming completo de moderncv via YAML metadata |
| [awesome-cv-pandoc](https://github.com/florianschwanz/awesome-cv-pandoc) | Pandoc | Fork de Awesome-CV con soporte pandoc |

---

## 6. Pipeline completo: MD a LaTeX a PDF

### Motores LaTeX

| Motor | Soporte Unicode | Soporte Fuentes | Mejor para |
|-------|:--------------:|:---------------:|------------|
| **pdflatex** | Limitado (requiere `inputenc`/`fontenc`) | Solo Type1/bitmap | Documentos simples, ingles |
| **xelatex** | UTF-8 nativo | OpenType, TrueType, fuentes del sistema | CVs con acentos, nombres internacionales |
| **lualatex** | UTF-8 nativo | OpenType, TrueType, fuentes del sistema | Igual que xelatex + scripting Lua |

**Recomendacion para CVs con caracteres especiales (espanol, etc.)**: Usar **xelatex** o **lualatex**. Manejan Unicode nativamente, nombres como "Raul Esteban Burro Cespedes" funcionan directamente en UTF-8 sin secuencias de escape.

### Compilacion sin instalacion completa de LaTeX

#### Docker

| Imagen | Descripcion |
|--------|-------------|
| [`texlive/texlive`](https://hub.docker.com/r/texlive/texlive) | Imagen oficial, TeX Live completo, actualizada semanalmente |
| [`dante-ev/docker-texlive`](https://github.com/dante-ev/docker-texlive) | TeX Live completo + pandoc + Perl + Python pre-instalados |
| [`maxkratz/docker_texlive`](https://github.com/maxkratz/docker_texlive) | Multi-version, tags: `base`, `latest`, `2025` |

```bash
docker run --rm -v $(pwd):/data texlive/texlive pdflatex resume.tex
```

#### Tectonic (motor en Rust)

[Tectonic](https://github.com/tectonic-typesetting/tectonic) es un motor TeX autocontenido escrito en Rust:

- **No requiere instalacion de TeX Live** - descarga paquetes automaticamente al primer uso
- Basado en XeTeX, soporte nativo Unicode y OpenType
- Binario unico, instalable via `cargo install tectonic` o `brew install tectonic`
- Reduce tiempo de build en CI de 5+ minutos a 50 segundos

```bash
cargo install tectonic
tectonic resume.tex
```

#### GitHub Actions

```yaml
- uses: xu-cheng/latex-action@v4
  with:
    root_file: resume.tex
    # compiler: xelatex  # opcional
```

---

## 7. Overleaf: compilacion y flujo de trabajo

### Como funciona Overleaf

Overleaf usa TeX Live en sus servidores de compilacion. Cuando haces click en "Recompile", ejecuta el motor LaTeX (via `latexmk` internamente) multiples veces segun sea necesario para resolver referencias cruzadas y bibliografias.

### Motores soportados

| Compilador | Motor | Caracteristicas |
|-----------|-------|-----------------|
| **pdfLaTeX** | pdfTeX | Por defecto. Mejor para documentos estandar con script latino |
| **XeLaTeX** | XeTeX | UTF-8 nativo, soporte OpenType/TrueType. Para scripts no-latinos y fuentes custom |
| **LuaLaTeX** | LuaTeX | pdfTeX extendido con Lua. Para accesibilidad PDF/UA-1 |
| **LaTeX** | TeX clasico | Formato DVI (raramente usado hoy) |

### Importar archivos .tex a Overleaf

Tres metodos:

1. **Subir ZIP**: Crear un `.zip` con los archivos `.tex`, `.cls`, `.sty`, imagenes. Ir a New Project > Upload Project. Limite: 7 MB contenido editable, max 2000 archivos.
2. **Subir archivos individuales**: En un proyecto existente, boton "Upload" para agregar archivos.
3. **Abrir desde template**: Navegar la galeria de Overleaf y click "Open as Template".

### Integracion Git con Overleaf (clave para el flujo)

**Se puede hacer push de archivos `.tex` a un proyecto Overleaf via Git.** Este es el metodo de integracion mas potente:

1. Abrir proyecto Overleaf > Integrations > Git
2. Copiar la URL de `git clone`
3. Clonar localmente, hacer cambios, push de vuelta al remote de Overleaf

**Vincular un repo local existente a Overleaf:**

```bash
# 1. Crear proyecto en blanco en Overleaf (borrar main.tex)
# 2. Obtener la URL Git del proyecto
# 3. Agregar como remote
git remote add overleaf <URL>

# 4. Pull y merge
git pull overleaf master --allow-unrelated-histories

# 5. Push tu contenido
git push overleaf master
```

### GitHub Sync de Overleaf (feature premium)

- Vincula un proyecto Overleaf directamente a un repo GitHub
- Sync es **manual** (no automatico) - click en "Push" o "Pull" en la UI
- Conflictos de merge se resuelven creando un PR desde la branch `overleaf` en GitHub
- **Limitacion**: No se puede vincular un proyecto Overleaf existente a un repo GitHub existente

### Templates populares en Overleaf

| Template | URL | Compilador | ATS Score |
|----------|-----|-----------|-----------|
| Jake's Resume | [Link](https://www.overleaf.com/latex/templates/jakes-resume/syzfjbzwjncs) | pdfLaTeX | 98+ |
| Awesome CV | [Link](https://www.overleaf.com/latex/templates/awesome-cv/dfnvtnhzhhbm) | XeLaTeX | Alto |
| ModernCV | [Link](https://www.overleaf.com/latex/templates/moderncv-and-cover-letter-template/sttkgjcysttn) | pdfLaTeX+ | Alto |
| Deedy CV | [Link](https://www.overleaf.com/latex/templates/deedy-cv/bjryvfsjdyxz) | XeTeX | Bajo (2 cols) |
| ATS Friendly Technical | [Link](https://www.overleaf.com/latex/templates/ats-friendly-technical-resume/yrhtcnjyzgsf) | pdfLaTeX | Muy alto |

Galeria completa: [overleaf.com/gallery/tagged/cv](https://www.overleaf.com/gallery/tagged/cv)

---

## 8. Alternativas a Overleaf

### Instalaciones locales

| Distribucion | Plataforma | Notas |
|-------------|-----------|-------|
| **TeX Live** | Cross-platform | Completo, releases anuales, incluye `latexmk` y `tlmgr` |
| **MiKTeX** | Windows-first | Instalacion on-demand de paquetes, footprint inicial menor |
| **MacTeX** | macOS | TeX Live reempaquetado para macOS con GUI nativas |
| **TinyTeX** | Cross-platform | Subconjunto minimo de TeX Live, ideal para CI/CD |

### latexmk (herramienta de build)

`latexmk` es la herramienta estandar de automatizacion de builds para LaTeX (Overleaf lo usa internamente):

```bash
# Compilar a PDF
latexmk -pdf resume.tex

# Watch mode con preview continuo
latexmk -pvc -pdf resume.tex

# Limpiar archivos auxiliares
latexmk -c resume.tex
```

---

## 9. Proyectos open-source de referencia

### Pipeline completo (MD input a PDF output)

| Proyecto | Input | Pipeline | Template |
|----------|-------|----------|----------|
| [pandoc_resume](https://mszep.github.io/pandoc_resume/) | Markdown | Pandoc + ConTeXt/wkhtmltopdf | Limpio, minimal |
| [resume-pandoc](https://github.com/john-bokma/resume-pandoc) | Markdown + YAML | Pandoc + template `.latex` custom | Estilo Blevins |
| [pandoc-moderncv](https://github.com/barraq/pandoc-moderncv) | Markdown + YAML | Pandoc + moderncv | Temas moderncv |
| [awesome-cv-pandoc](https://github.com/florianschwanz/awesome-cv-pandoc) | Markdown | Pandoc + Awesome-CV | Awesome-CV |
| [resume-latex](https://github.com/jfhack/resume-latex) | Markdown | Python + lualatex/pdflatex | Custom, Docker |
| [mderncv](https://github.com/manualbashing/mderncv) | Markdown + YAML | Pandoc + panflute + moderncv | moderncv |

### Templates LaTeX puros (referencia)

| Proyecto | Notas |
|----------|-------|
| [Awesome-CV](https://github.com/posquit0/Awesome-CV) | 20k+ stars, el template mas popular |
| [Jake's Resume](https://github.com/jakegut/resume) | Maximo ATS, basado en sb2nov/resume |
| [rover-resume](https://github.com/subidit/rover-resume) | ATS-friendly, setup minimo |

---

## 10. Recomendacion para este proyecto

### Flujo propuesto

```
resume.md  ──(pandoc + template)──>  resume.tex  ──(compilacion)──>  resume.pdf
                                         │
                                         ├──> Compilar localmente (tectonic / latexmk)
                                         ├──> Push a Overleaf via Git para tweaks finales
                                         └──> Tambien generar .docx via pandoc (para ATS)
```

### Opcion A: Compilacion local (automatizada)

1. Escribir/mantener CV en `resume.md`
2. Convertir a `.tex` via pandoc con template LaTeX personalizado
3. Compilar localmente con `tectonic resume.tex` (rapido, autocontenido) o `latexmk -pdf resume.tex`
4. Automatizar en CI con `xu-cheng/latex-action@v4`

### Opcion B: Overleaf via Git (semi-automatizada)

1. Escribir/mantener CV en `resume.md`
2. Convertir a `.tex` via pandoc
3. Push del `.tex` a un proyecto Overleaf via Git (`git push overleaf master`)
4. Abrir Overleaf en el navegador para review final y compilacion

### Opcion C: Hibrida (recomendada)

1. Escribir/mantener CV en `resume.md`
2. Agregar script npm que convierte MD a LaTeX via pandoc:
   ```bash
   pandoc resume.md -f markdown+yaml_metadata_block \
     --template templates/cv-template.tex \
     --pdf-engine=xelatex \
     -o resume.tex
   ```
3. El usuario puede:
   - Compilar localmente con `tectonic` o Docker
   - Subir el `.tex` a Overleaf para tweaks y compilacion visual
   - Generar `.docx` para envio ATS: `pandoc resume.md -o resume.docx`
4. Agregar GitHub Action para compilacion automatica en push

### Template recomendado

**Jake's Resume** es la opcion mas solida:
- Usa pdfLaTeX (lo mas simple de configurar)
- Licencia MIT
- Score ATS de 98+
- Layout de columna unica que mapea limpiamente desde la estructura Markdown
- El template mas usado en la industria tech

Para necesidades internacionales/EU, considerar **moderncv** con estilo `banking`.

### Dependencias nuevas necesarias

- **pandoc**: Para la conversion MD a LaTeX (`brew install pandoc` / `apt install pandoc`)
- **tectonic** (opcional): Para compilacion local sin TeX Live completo (`cargo install tectonic`)
- **pandocjs** (opcional): Para integracion Node.js sin pandoc pre-instalado

---

## Fuentes

### Formatos profesionales y ATS
- [Resume.io - ATS Resume Templates (2026)](https://resume.io/resume-templates/ats)
- [Jobscan - ATS-Friendly Resume in 2026](https://www.jobscan.co/blog/20-ats-friendly-resume-templates/)
- [Novoresume - How to Write an ATS Resume](https://novoresume.com/career-blog/ats-resume)
- [Design Gurus - Best Resume Formats for FAANG](https://www.designgurus.io/blog/best-resume-formats-for-faang-and-top-tech-companies-2025)

### LaTeX templates
- [CTAN - moderncv](https://ctan.org/pkg/moderncv)
- [CTAN - europecv](https://ctan.org/pkg/europecv)
- [CTAN - CV Topic Page](https://ctan.org/topic/cv)
- [GitHub - posquit0/Awesome-CV](https://github.com/posquit0/Awesome-CV)
- [GitHub - liantze/AltaCV](https://github.com/liantze/AltaCV)
- [GitHub - deedy/Deedy-Resume](https://github.com/deedy/Deedy-Resume)
- [GitHub - jakegut/resume](https://github.com/jakegut/resume)

### Pandoc y conversion
- [Pandoc User's Guide](https://pandoc.org/MANUAL.html)
- [Pandoc Lua Filters](https://pandoc.org/lua-filters.html)
- [GitHub - pandoc-moderncv](https://github.com/barraq/pandoc-moderncv)
- [GitHub - mszep/pandoc_resume](https://mszep.github.io/pandoc_resume/)
- [How I manage my CV with Markdown, Pandoc, Python, and LaTeX](https://lucaf.eu/2022/08/18/cv-markdown-pandoc-python-latex.html)

### Overleaf
- [Overleaf - Choosing a LaTeX Compiler](https://www.overleaf.com/learn/latex/Choosing_a_LaTeX_Compiler)
- [Overleaf - Git Integration](https://docs.overleaf.com/integrations-and-add-ons/git-integration-and-github-synchronization/git-integration)
- [Overleaf - GitHub Synchronization](https://docs.overleaf.com/integrations-and-add-ons/git-integration-and-github-synchronization/github-synchronization)
- [Overleaf - CV Gallery](https://www.overleaf.com/gallery/tagged/cv)
- [Overleaf API](https://www.overleaf.com/devs)

### Compilacion LaTeX
- [Tectonic](https://github.com/tectonic-typesetting/tectonic)
- [xu-cheng/latex-action](https://github.com/marketplace/actions/github-action-for-latex)
- [texlive/texlive Docker](https://hub.docker.com/r/texlive/texlive)
- [CTAN - latexmk](https://ctan.org/pkg/latexmk)
