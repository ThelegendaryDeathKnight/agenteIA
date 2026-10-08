# Manual de LaTeX

**Autor:** Alfredo Sánchez Alberca (asalber@ceu.es)
**Sitio web:** https://aprendeconalf.es
**Páginas totales:** 63
**Idioma:** Español
**Licencia:** Creative Commons Reconocimiento – No comercial – Compartir bajo la misma licencia 3.0 España

---

## Resumen técnico

Este documento constituye un manual introductorio al lenguaje de composición de textos **LaTeX**, orientado específicamente a la creación de documentos científicos y técnicos con contenido matemático. A lo largo de sus 63 páginas, el autor presenta desde los fundamentos teóricos de TeX y LaTeX hasta la aplicación práctica de comandos y entornos para generar documentos profesionales.

El manual comienza explicando qué es TeX (creado por Donald Knuth en 1978) y qué es LaTeX (macros desarrolladas por Leslie Lamport), destacando la ventaja fundamental de separar el contenido y la estructura del formato, en contraste con los procesadores WYSIWYG como Microsoft Word. Se detallan las distintas distribuciones (TexLive, MiKTeX, MacTeX) y editores (TexMaker, TeXstudio, Vim, Emacs, Visual Studio Code, Overleaf).

El documento cubre la estructura básica de un documento LaTeX: clase de documento (`\documentclass`), preámbulo (paquetes `inputenc`, `babel`, `fontenc`), y cuerpo (entorno `document`). Se explican los comandos para secciones (`\section`, `\subsection`), párrafos, justificación (`flushleft`, `flushright`, `center`), y formateo básico (negrita, cursiva, subrayado, familias tipográficas, perfiles, tamaños).

Se detallan las listas (itemize, enumerate, description), tablas (entorno `tabular`, `\multicolumn`, `\cline`), e imágenes (paquete `graphicx`, comando `\includegraphics`). El capítulo de fórmulas matemáticas es particularmente extenso, cubriendo modo matemático (`$`, `$$`, `equation`), símbolos (letras griegas, operadores, relaciones, lógica, conjuntos, flechas), subíndices/superíndices, fracciones (`\frac`), sumatorios (`\sum`), productorios (`\prod`), integrales (`\int`), límites (`\lim`), sombreros (`\bar`, `\hat`, `\vec`), matrices (entorno `array`, paquete `amsmath`), y teoremas (paquete `amsthm`).

Finalmente, el manual aborda entornos flotantes (`figure`, `table`), referencias cruzadas (`\label`, `\ref`), notas al pie (`\footnote`), citas bibliográficas (BibTeX, biblatex), y diseño de página (paquete `geometry`, `fancyhdr`). Cada capítulo incluye ejemplos de código y su correspondiente salida compilada.

---

## Índice de contenidos

| Sección | Páginas |
|---|---|
| Prefacio | 4 |
| Licencia | 4 |
| 1. Introducción | 5 |
| 1.1. ¿Qué es TeX? | 5 |
| 1.2. ¿Qué es LaTeX? | 5 |
| 1.3. Instalación | 6 |
| 1.4. Hola LaTeX | 7 |
| 1.4.1. Compilación | 7 |
| 2. Estructura de un documento | 10 |
| 2.1. Esqueleto básico para pdflatex | 10 |
| 2.1.1. Clase de un documento | 11 |
| 2.1.2. Preámbulo | 12 |
| 2.1.3. Cuerpo | 12 |
| 2.2. Esqueleto básico para xelatex | 12 |
| 3. Secciones y párrafos | 14 |
| 3.1. Secciones y subsecciones | 14 |
| 3.2. Párrafos y cambios de línea | 15 |
| 3.3. Justificación | 16 |
| 4. Formateo básico | 19 |
| 4.1. Negrita, cursiva y subrayado | 19 |
| 4.2. Familias de tipos de letra | 20 |
| 4.3. Perfiles de letra | 21 |
| 4.4. Tamaños de letra | 22 |
| 5. Listas | 24 |
| 6. Tablas | 28 |
| 7. Imágenes | 31 |
| 8. Fórmulas matemáticas | 33 |
| 8.1. Símbolos matemáticos | 34 |
| 8.1.1. Letras griegas | 34 |
| 8.1.2. Operadores aritméticos | 35 |
| 8.1.3. Relaciones | 35 |
| 8.1.4. Operadores binarios | 35 |
| 8.1.5. Lógica | 35 |
| 8.1.6. Conjuntos | 35 |
| 8.1.7. Flechas | 35 |
| 8.1.8. Puntos suspensivos | 36 |
| 8.1.9. Otros símbolos | 36 |
| 8.1.10. Funciones | 36 |
| 8.2. Subíndices y superíndices | 36 |
| 8.3. Fracciones | 37 |
| 8.4. Sumatorios, productorios, integrales y límites | 38 |
| 8.5. Sombreros | 40 |
| 8.6. Matrices | 41 |
| 8.7. Teoremas | 43 |
| 9. Entornos flotantes | 45 |
| 9.1. Entorno flotante para figuras | 45 |
| 9.2. Entorno flotante para tablas | 46 |
| 10. Referencias cruzadas y notas a pie | 49 |
| 10.1. Referencias cruzadas | 49 |
| 10.2. Notas a pie de página | 50 |
| 11. Citas y referencias bibliográficas | 51 |
| 12. Diseño de página | 55 |
| 12.1. Dimensiones y márgenes | 55 |
| 12.2. Encabezados y pies de página | 59 |
| Bibliografía y recursos | 63 |
| Libros | 63 |
| Sitios Web | 63 |

---

## Prefacio

¡Bienvenida/os al manual de LaTeX!

Este libro presenta una introducción al lenguaje de composición de textos LaTeX con un enfoque orientado a la creación de documentos científicos y técnicos con contenido matemático.

### Licencia

Esta obra está bajo una licencia **Reconocimiento – No comercial – Compartir bajo la misma licencia 3.0 España de Creative Commons**. Para ver una copia de esta licencia, visite:
https://creativecommons.org/licenses/by-nc-sa/3.0/es/

Con esta licencia eres libre de:
- Copiar, distribuir y mostrar este trabajo.
- Realizar modificaciones de este trabajo.

Bajo las siguientes condiciones:
- **Reconocimiento.** Debe reconocer los créditos de la obra de la manera especificada por el autor o el licenciador (pero no de una manera que sugiera que tiene su apoyo o apoyan el uso que hace de su obra).
- **No comercial.** No puede utilizar esta obra para fines comerciales.
- **Compartir bajo la misma licencia.** Si altera o transforma esta obra, o genera una obra derivada, sólo puede distribuir la obra generada bajo una licencia idéntica a ésta.

Al reutilizar o distribuir la obra, tiene que dejar bien claro los términos de la licencia de esta obra.

Estas condiciones pueden no aplicarse si se obtiene el permiso del titular de los derechos de autor.

Nada en esta licencia menoscaba o restringe los derechos morales del autor.

---

## 1. Introducción

### 1.1. ¿Qué es TeX?

TeX es un sistema de composición de documentos de alta calidad, orientado especialmente a la creación de documentos científicos y técnicos que incluyen fórmulas matemáticas. Fue creado por **Donald Knuth en 1978**.

A diferencia de un procesador de textos como Microsoft Word, TeX no es una aplicación sino un **lenguaje de programación** que requiere compilar el código fuente para obtener el documento final. Esto permite separar fácilmente el contenido y la estructura de un documento, de su formato.

TeX incorpora un potente **lenguaje de marcado** para estructurar y formatear el texto. Por ejemplo, para poner una palabra en negrita en TeX se escribe `{\bf palabra}` y después se compila el código fuente.

La página principal con información sobre TeX es la del **TeX Users Group**.

### 1.2. ¿Qué es LaTeX?

```json
{
  "type": "image",
  "id": "image-01",
  "page": 5,
  "title": "The LaTeX Project",
  "caption": "Logotipo oficial del proyecto LaTeX",
  "description": "Logotipo con un colibrí verde y el texto 'The LaTeX Project'.",
  "source": "The LaTeX Project"
}
```

LaTeX es un conjunto de **macros para TeX** debido originalmente a **Leslie Lamport** para facilitar la composición de documentos científicos y técnicos.

Tanto TeX como LaTeX son programas de **código abierto**, liberados bajo la licencia LPPL.

Otra de las grandes ventajas de LaTeX es que existen multitud de **paquetes de código libre** para generar distintos tipos de documentos que pueden descargarse desde el repositorio CRAN.

La página principal sobre LaTeX es **The LaTeX project**.

### 1.3. Instalación

Existen distintas distribuciones de LaTeX, algunas multiplataforma:

| Distribución | Sistemas operativos |
|---|---|
| **TexLive** | Windows, Mac OSX, Linux |
| **MiKTeX** | Windows, Mac OSX, Linux |
| **MacTeX** | Mac OSX |

Editores de texto recomendados:

| Editor | Características |
|---|---|
| **TexMaker** | Editor libre, multiplataforma, previsualización en tiempo real |
| **TeXstudio** | Editor libre, multiplataforma, más asistentes |
| **Vim** | Editor simple, plugins para LaTeX, para terminal |
| **Emacs** | Editor similar a Vim, para terminal |
| **Visual Studio Code** | Entorno de desarrollo multipropósito con paquetes para LaTeX |

También se puede usar un editor **on-line** como **Overleaf** sin instalar nada.

### 1.4. Hola LaTeX

Ejemplo de documento mínimo:

```latex
\documentclass{article}
\usepackage[spanish]{babel}
\begin{document}
Hola LaTeX
\end{document}
```

**Importante:** El nombre del fichero puede ser cualquiera, pero la extensión debe ser `.tex`.

**Explicación del código:**
1. Primera línea: tipo de documento (`article`).
2. Segunda línea: idioma del documento (`spanish`).
3. Tercera línea: comienzo del documento.
4. Cuarta línea: texto del documento. `LaTeX` es un comando que produce la salida LaTeX.
5. Quinta línea: final del documento.

#### 1.4.1. Compilación

Cada distribución de LaTeX viene con varios compiladores:

| Compilador | Formato de salida | Características |
|---|---|---|
| **latex** | dvi | Más antiguo, formato independiente |
| **pdflatex** | pdf | El más usado |
| **xelatex** | pdf | Admite Unicode y tipografías modernas |

**Comandos de compilación:**
```bash
latex main.tex
pdflatex main.tex
xelatex main.tex
```

**Salida típica de pdflatex:**
```
This is pdfTeX, Version 3.141592653-2.6-1.40.22 (TeX Live 2021)
...
Output written on main.pdf (1 page, 20106 bytes).
Transcript written on main.log.
```

```json
{
  "type": "image",
  "id": "image-02",
  "page": 9,
  "title": "Creación de un documento en Overleaf",
  "caption": "Figura 1.1: Creación de un documento en Overleaf",
  "description": "Captura de pantalla del editor Overleaf mostrando el código fuente a la izquierda y la vista previa del PDF a la derecha.",
  "source": "Overleaf"
}
```

**Ejemplo de error:**
```
! Undefined control sequence.
l.6 Ejemplo de documento con un error. \error
```

> **Advertencia:** Si el documento contiene referencias cruzadas, citaciones bibliográficas, tabla de contenidos o índices, es necesario compilar el documento **dos o tres veces** para que se generen automáticamente esas partes.

---

## 2. Estructura de un documento

### 2.1. Esqueleto básico para pdflatex

```latex
% CLASE
\documentclass[a4paper,10pt]{article}

% PREÁMBULO
% Paquetes
\usepackage[utf8]{inputenc}
\usepackage[spanish]{babel}
\usepackage[T1]{fontenc}

% Título, autor y fecha
\title{Título}
\author{Autor}
\date{Fecha}

% CUERPO
\begin{document}

\maketitle

% Resumen
\begin{abstract}
Resumen
\end{abstract}

% Tabla de contenidos
\tableofcontents

Contenido del documento

\end{document}
```

**Sintaxis de elementos básicos:**

| Elemento | Descripción |
|---|---|
| **Comandos** | Comienzan por `\`. Argumentos obligatorios entre `{}`, opcionales entre `[]` |
| **Entornos** | Bloques delimitados por `\begin{entorno}` y `\end{entorno}` |
| **Comentarios** | Comienzan con `%` |
| **Símbolos reservados** | `\`, `$`, `{`, `}`, `#`, `%`, `&`, `~`, `_`, `^` |

**Símbolos reservados y su escritura:**

| Símbolo | Escritura |
|---|---|
| `\` | `\backslash` |
| `{` | `\{` |
| `}` | `\}` |
| `#` | `\#` |
| `$` | `\$` |
| `%` | `\%` |
| `&` | `\&` |
| `~` | `\~` |
| `_` | `\_` |
| `^` | `\^` |

#### 2.1.1. Clase de un documento

El comando `\documentclass` indica la clase de documento:

| Clase | Tipo de documento |
|---|---|
| `article` | Artículo |
| `report` | Informe |
| `book` | Libro |
| `letter` | Carta |

**Argumentos opcionales:**
- `a4paper` — tamaño de hoja A4
- `10pt`, `11pt`, `12pt` — tamaño base de fuente

#### 2.1.2. Preámbulo

Parte entre la clase y el cuerpo del documento. Se usa para:
- Cargar paquetes (`\usepackage`)
- Configurar el documento
- Definir nuevos comandos

**Paquetes del ejemplo:**
- `inputenc` — codificación de caracteres (`utf8`)
- `babel` — idioma del documento (`spanish`)
- `fontenc` — codificación de fuentes (`T1`)

#### 2.1.3. Cuerpo

Contiene el texto del documento dentro del entorno `document`. Suele empezar con:
- `\maketitle` — título, autor y fecha
- `\tableofcontents` — tabla de contenidos
- Texto del documento

### 2.2. Esqueleto básico para xelatex

```latex
% Paquetes
\usepackage{fontspec}
\setmainfont{Times New Roman}
\usepackage{polyglossia}
\setdefaultlanguage{spanish}
```

- **fontspec** — define las fuentes tipográficas (deben estar instaladas)
- **polyglossia** — define el idioma del documento

```json
{
  "type": "image",
  "id": "image-03",
  "page": 13,
  "title": "Estructura básica de un documento",
  "caption": "Figura 2.1: Estructura básica de un documento",
  "description": "Captura de Overleaf mostrando el esqueleto básico de un documento LaTeX con clase, preámbulo y cuerpo.",
  "source": "Overleaf"
}
```

---

## 3. Secciones y párrafos

### 3.1. Secciones y subsecciones

| Comando | Descripción |
|---|---|
| `\chapter{Título}` | Capítulo (solo clase `book`) |
| `\section{Título}` | Sección |
| `\subsection{Título}` | Subsección |
| `\subsubsection{Título}` | Subsubsección |

**Versiones sin numerar:** `\chapter*`, `\section*`, `\subsection*`, `\subsubsection*` (no aparecen en la tabla de contenidos).

**Ejemplo 3.1:**
```latex
\documentclass[a4paper, 10pt]{article}
\begin{document}
\tableofcontents

\section{Sección primera}
Texto de la sección.

\subsection{Subsección primera}
Texto de la subsección.

\subsection*{Subsección segunda}
Texto de la subsección.

\subsection{Subsección tercera}
Texto de la subsección.

\section{Sección segunda}
Texto de la sección.
\end{document}
```

**Salida:**
```
Índice general
1 Sección primera 1
  1.1 Subsección primera . . . . . . . . . . . . . . . . . . . . 1
  1.2 Subsección tercera . . . . . . . . . . . . . . . . . . . . 1
2 Sección segunda 1

1 Sección primera
Texto de la sección.
1.1 Subsección primera
Texto de la subsección.
*Subsección segunda
Texto de la subsección.
1.2 Subsección tercera
Texto de la subsección.
2 Sección segunda
Texto de la sección.
```

### 3.2. Párrafos y cambios de línea

- **Párrafo nuevo:** dejar una o más líneas en blanco
- **Cambio de línea:** `\newline` o `\\`
- **Sangría:** automática al comenzar un párrafo

**Ejemplo 3.2:**
```latex
\begin{document}
Este es el primer párrafo del documento, con un \\ cambio de linea.

Este es el segundo párrafo del documento. Obsérvese que cada vez que se comienza un párrafo la primera línea de desplaza un poco hacia la derecha. Esto se conoce como \emph{sangria}.
\end{document}
```

### 3.3. Justificación

| Entorno | Justificación |
|---|---|
| `flushleft` | Izquierda |
| `flushright` | Derecha |
| `center` | Centrado |

**Ejemplo 3.3:**
```latex
\begin{document}
Este es el primer párrafo del documento, y aparece justificado a ambos lados (márgenes izquierdo y derecho) por defecto.

\begin{flushleft}
Este es el segundo párrafo del documento y aparece justificado a la izquierda, es decir alineado con el margen izquierdo del documento.
\end{flushleft}

\begin{flushright}
Este es el tercer párrafo del documento y aparece justificado a la derecha, es decir alineado con el margen derecho del documento.
\end{flushright}

\begin{center}
Este es el último párrafo del documento y aparece justificado en el centro entre los márgenes del documento.
\end{center}
\end{document}
```

> **Advertencia:** Si el algoritmo de partición de palabras divide mal una palabra, se puede indicar por dónde partir con el comando `\-` (ejemplo: `si\-la\-ba`).

---

## 4. Formateo básico

### 4.1. Negrita, cursiva y subrayado

| Comando | Efecto |
|---|---|
| `\textbf{...}` | Negrita |
| `\textit{...}` | Cursiva o itálica |
| `\emph{...}` | Énfasis (cambia de estilo) |
| `\underline{...}` | Subrayado |

**Ejemplo 4.1:**
```latex
\begin{document}
Este texto está en \textbf{negrita}, este en \textit{cursiva} y este \underline{subrayado}.

\textit{Este texto está \emph{enfatizado}}.
\end{document}
```

**Salida:**
> Este texto está en **negrita**, este en *cursiva* y este <u>subrayado</u>.
> *Este texto está enfatizado.*

### 4.2. Familias de tipos de letra

| Comando | Tipo de letra |
|---|---|
| `\textrm{...}` | Normal (con serif) — por defecto |
| `\textsf{...}` | Sin adornos (sin serif) |
| `\texttt{...}` | Máquina de escribir (monoespaciado) |

**Selección de fuentes (con fontspec para xelatex):**
```latex
\setromanfont{Times New Roman}
\setsansfont{Arial}
\setmonofont{Courier New}
```

> **Precaución:** Las fuentes deben estar instaladas en el sistema operativo donde se compile el documento.

**Ejemplo 4.3:**
```latex
% PREÁMBULO
\usepackage{fontspec}
\setromanfont{Times New Roman}
\setsansfont{Arial}
\setmonofont{Courier New}

% CUERPO
\begin{document}
Este texto es normal, \textsf{este es sin adornos}, \texttt{y este de máquina de escribir}.
\end{document}
```

### 4.3. Perfiles de letra

| Comando | Perfil |
|---|---|
| `\textup{...}` | Recto (por defecto) |
| `\textit{...}` | Itálica |
| `\textsl{...}` | Inclinado |
| `\textsc{...}` | Versalita (mayúsculas pequeñas) |

**Ejemplo 4.4:**
```latex
\begin{document}
Texto normal con perfil recto, \textit{itálica}, \textsl{inclinado} y \textsc{versalita}.

\textsf{Texto sin adorno con perfil recto, \textit{itálica}, \textsl{inclinado} y \textsc{versalita}.}

\texttt{Texto monoespaciado con perfil recto, \textit{itálica}, \textsl{inclinado} y \textsc{versalita}.}
\end{document}
```

### 4.4. Tamaños de letra

Tamaños predefinidos (de menor a mayor):

```
\tiny
\scriptsize
\footnotesize
\small
\normalsize
\large
\Large
\LARGE
\huge
\Huge
```

---

## 5. Listas

| Entorno | Tipo de lista |
|---|---|
| `itemize` | Sin numerar |
| `enumerate` | Enumerada |
| `description` | Descriptiva |

**Ejemplo 5.1: Lista no ordenada**
```latex
\begin{document}
\begin{itemize}
  \item Este es un item.
  \item Este es otro item.
  \item Y otro item más.
\end{itemize}
\end{document}
```

**Salida:**
- Este es un item.
- Este es otro item.
- Y otro item más.

**Ejemplo 5.2: Lista ordenada**
```latex
\begin{document}
\begin{enumerate}
  \item Primer item.
  \item Segundo item.
  \item Tercer item.
\end{enumerate}
\end{document}
```

**Salida:**
1. Primer item.
2. Segundo item.
3. Tercer item.

**Ejemplo 5.3: Lista descriptiva**
```latex
\begin{document}
\begin{description}
  \item{\textit{latex}} Genera documentos en formato dvi.
  \item{\textit{pdflatex}} Genera documentos en formato pdf.
  \item{\textit{xelatex}} Genera documentos en formato pdf que admiten codificación Unicode.
\end{description}
\end{document}
```

**Salida:**
- ***latex*** — Genera documentos en formato dvi.
- ***pdflatex*** — Genera documentos en formato pdf.
- ***xelatex*** — Genera documentos en formato pdf que admiten codificación Unicode.

**Ejemplo 5.4: Listas anidadas**
```latex
\begin{document}
\begin{enumerate}
  \item Primer item.
  \begin{enumerate}
    \item Primer subitem.
    \item Segundo subitem.
  \end{enumerate}
  \item Segundo item.
  \begin{itemize}
    \item Un item.
    \item Otro item.
  \end{itemize}
\end{enumerate}
\end{document}
```

**Salida:**
1. Primer item.
   (a) Primer subitem.
   (b) Segundo subitem.
2. Segundo item.
   - Un item.
   - Otro item.

---

## 6. Tablas

### Entorno tabular

Argumento obligatorio: número de columnas y justificación (`l` izquierda, `r` derecha, `c` centrada).

| Comando | Efecto |
|---|---|
| `\\` | Cambio de fila |
| `&` | Separador de celdas |
| `\hline` | Línea horizontal |
| `|` | Línea vertical entre columnas |
| `\multicolumn{num}{col}{texto}` | Celda que ocupa varias columnas |
| `\cline{n-m}` | Línea horizontal parcial |

**Ejemplo 6.1:**
```latex
\begin{document}
\begin{tabular}{lcr}
Nombre & Ciudad & Edad \\
María & Valencia & 22 \\
Juan & Madrid & 50 \\
Carmen & Barcelona & 35 \\
\end{tabular}
\end{document}
```

**Salida:**

| Nombre | Ciudad | Edad |
|---|---|---|
| María | Valencia | 22 |
| Juan | Madrid | 50 |
| Carmen | Barcelona | 35 |

**Ejemplo 6.2: Con líneas divisorias**
```latex
\begin{tabular}{llclrl}
\hline
Nombre & Ciudad & Edad \\
\hline \hline
María & Valencia & 22 \\
\hline
Juan & Madrid & 50 \\
\hline
Carmen & Barcelona & 35 \\
\hline
\end{tabular}
```

**Ejemplo 6.3: Con multicolumn y cline**
```latex
\begin{document}
\begin{tabular}{lrrccrr}
\hline
 & \multicolumn{2}{c}{Enero} & & \multicolumn{2}{c}{Febrero}\\
\cline{2-3}\cline{5-6}
Ciudad & Ingresos & Gastos & & Ingresos & Gastos\\
\hline
Madrid & 2500 & 1750 & & 2600 & 1800\\
Barcelona & 2250 & 1500 & & 2400 & 1650\\
\hline
\end{tabular}
\end{document}
```

**Salida:**

| Ciudad | Enero Ingresos | Enero Gastos | | Febrero Ingresos | Febrero Gastos |
|---|---|---|---|---|---|
| Madrid | 2500 | 1750 | | 2600 | 1800 |
| Barcelona | 2250 | 1500 | | 2400 | 1650 |

---

## 7. Imágenes

**Requisito previo:** Cargar el paquete `graphicx` en el preámbulo.

**Formatos soportados:** jpg, png, tiff, eps, pdf.

**Comando:** `\includegraphics[opciones]{fichero}`

| Opción | Descripción |
|---|---|
| `height` | Altura de la imagen |
| `width` | Anchura de la imagen |
| `scale` | Factor de escalado (0 a 1) |
| `angle` | Ángulo de rotación (sentido horario) |

**Ejemplo 7.1:**
```latex
% PREÁMBULO
\usepackage{graphicx}

% CUERPO
\begin{document}
Ejemplo de imagen en línea \includegraphics{img/logo-aprendeconalf.png}, escalada \includegraphics[height=1cm]{img/logo-aprendeconalf.png}, y rotada \includegraphics[angle=90]{img/logo-aprendeconalf.png}

Ejemplo de imagen centrada:
\begin{center}
\includegraphics{img/logo-aprendeconalf.png}
\end{center}
\end{document}
```

---

## 8. Fórmulas matemáticas

### Modos matemáticos

| Modo | Activación | Descripción |
|---|---|---|
| En línea | `$ ... $` | Fórmula en la misma línea que el texto |
| Desplegado | `$$ ... $$` | Fórmula en línea aparte |
| Ecuación numerada | `\begin{equation} ... \end{equation}` | Fórmula con número |

**Ejemplo 8.1:**
```latex
\begin{document}
Ejemplo de fórmula en linea $ x+y=0 $.

Ejemplo de fórmula desplegada
$$
x+y=0
$$

Ejemplo de fórmula con el entorno \texttt{equation}
\begin{equation}
x+y=0
\end{equation}
\end{document}
```

### 8.1. Símbolos matemáticos

#### 8.1.1. Letras griegas

**Minúsculas:**

| Comando | Símbolo | Comando | Símbolo |
|---|---|---|---|
| `\alpha` | α | `\theta` | θ |
| `\beta` | β | `\vartheta` | ϑ |
| `\gamma` | γ | `\iota` | ι |
| `\delta` | δ | `\kappa` | κ |
| `\epsilon` | ε | `\lambda` | λ |
| `\zeta` | ζ | `\mu` | μ |
| `\eta` | η | `\nu` | ν |
| `\xi` | ξ | `\pi` | π |
| `\rho` | ρ | `\varpi` | ϖ |
| `\sigma` | σ | `\tau` | τ |
| `\upsilon` | υ | `\phi` | φ |
| `\chi` | χ | `\psi` | ψ |
| `\omega` | ω | | |

**Mayúsculas:**

| Comando | Símbolo |
|---|---|
| `\Gamma` | Γ |
| `\Delta` | Δ |
| `\Theta` | Θ |
| `\Lambda` | Λ |
| `\Xi` | Ξ |
| `\Pi` | Π |
| `\Sigma` | Σ |
| `\Upsilon` | Υ |
| `\Phi` | Φ |
| `\Psi` | Ψ |
| `\Omega` | Ω |

#### 8.1.2. Operadores aritméticos

| Comando | Símbolo |
|---|---|
| `+` | + |
| `-` | − |
| `\times` | × |
| `\cdot` | · |
| `/` | / |
| `\div` | ÷ |
| `\sqrt{...}` | √ |

#### 8.1.3. Relaciones

| Comando | Símbolo | Comando | Símbolo |
|---|---|---|---|
| `=` | = | `\neq` | ≠ |
| `<` | < | `\leq` | ≤ |
| `>` | > | `\geq` | ≥ |
| `\approx` | ≈ | `\sim` | ∼ |
| `\equiv` | ≡ | `\in` | ∈ |
| `\notin` | ∉ | `\subset` | ⊂ |
| `\not\equiv` | ≢ | `\subsetneq` | ⊊ |

#### 8.1.4. Operadores binarios

| Comando | Símbolo |
|---|---|
| `\cup` | ∪ |
| `\cap` | ∩ |
| `\setminus` | \ |
| `\circ` | ∘ |

#### 8.1.5. Lógica

| Comando | Símbolo |
|---|---|
| `\exists` | ∃ |
| `\forall` | ∀ |
| `\neg` | ¬ |
| `\lor` | ∨ |
| `\land` | ∧ |

#### 8.1.6. Conjuntos

| Comando | Símbolo |
|---|---|
| `\emptyset` | ∅ |
| `\mathbb{N}` | ℕ |
| `\mathbb{Z}` | ℤ |
| `\mathbb{Q}` | ℚ |
| `\mathbb{R}` | ℝ |
| `\mathbb{C}` | ℂ |

#### 8.1.7. Flechas

| Comando | Símbolo |
|---|---|
| `\rightarrow` | → |
| `\longrightarrow` | ⟶ |
| `\leftarrow` | ← |
| `\Leftarrow` | ⇐ |
| `\longleftarrow` | ⟵ |
| `\uparrow` | ↑ |
| `\Uparrow` | ⇑ |
| `\downarrow` | ↓ |

#### 8.1.8. Puntos suspensivos

| Comando | Símbolo |
|---|---|
| `\ldots` | … |
| `\cdots` | ⋯ |
| `\vdots` | ⋮ |
| `\ddots` | ⋱ |

#### 8.1.9. Otros símbolos

| Comando | Símbolo |
|---|---|
| `\infty` | ∞ |
| `\partial` | ∂ |
| `\nabla` | ∇ |

#### 8.1.10. Funciones

| Comando | Función |
|---|---|
| `\sin` | sin |
| `\cos` | cos |
| `\tan` | tan |
| `\arcsin` | arcsin |
| `\arccos` | arccos |
| `\arctan` | arctan |
| `\exp` | exp |
| `\log` | log |
| `\ln` | ln |
| `\csc` | csc |
| `\sec` | sec |
| `\cot` | cot |

**Declaración de nuevos operadores:**
```latex
\usepackage{amsmath}
\DeclareMathOperator{\sen}{sen}
```

> **Tip:** Cargar los paquetes `amsmath`, `amssymb` y `amsthm` para documentos extensos o con muchas fórmulas matemáticas.

### 8.2. Subíndices y superíndices

| Comando | Efecto |
|---|---|
| `_` | Subíndice |
| `^` | Superíndice |

Si afectan a más de un carácter, usar llaves: `x_{i+1}`, `y^{2n}`.

**Ejemplo 8.2:**
```latex
\begin{document}
Ejemplo de fórmula con subíndices
$$ x_i+y_j=0 $$

Ejemplo de fórmula con superíndices
$$ x^2+y^2=0 $$

Ejemplo de fórmula con subíndices y superíndices
$$ x_i^2+y_j^2=0 $$
\end{document}
```

### 8.3. Fracciones

**Comando:** `\frac{numerador}{denominador}`

**Ejemplo 8.3:**
```latex
\begin{document}
Ejemplo de fracción en línea $\frac{x+2}{x^2-2x+1}$.

Ejemplo de fracción en modo desplegado
$$
\frac{\frac{x}{2}+\frac{y}{2}}{\frac{x}{2}-\frac{y}{2}}
$$
\end{document}
```

### 8.4. Sumatorios, productorios, integrales y límites

| Comando | Símbolo |
|---|---|
| `\sum_{sub}^{sup}` | ∑ |
| `\prod_{sub}^{sup}` | ∏ |
| `\int_{sub}^{sup}` | ∫ |
| `\lim_{sub}` | lim |

**Ejemplo 8.4:**
```latex
\begin{document}
Ejemplo de sumatorio
$$
\sum_{i=1}^{\infty} x^i
$$

Ejemplo de productorio
$$
\prod_{i=1}^n i
$$
\end{document}
```

**Ejemplo 8.5:**
```latex
\begin{document}
Ejemplo de integral definida
$$
\int_a^b f(x)\,dx
$$

Ejemplo de integral indefinida
$$
\int f(x)\,dx
$$
\end{document}
```

**Ejemplo 8.6:**
```latex
\begin{document}
Ejemplo de límite
$$
\lim_{h\to 0} \frac{f(a+h)-f(a)}{h}
$$
\end{document}
```

### 8.5. Sombreros

| Comando | Efecto |
|---|---|
| `\bar{...}` | Línea horizontal (1 carácter) |
| `\overline{...}` | Línea horizontal (varios) |
| `\hat` | Ángulo (1 carácter) |
| `\widehat` | Ángulo (varios) |
| `\vec{...}` | Flecha (1 carácter) |
| `\overrightarrow{...}` | Flecha (varios) |

**Ejemplo 8.7:**
```latex
\begin{document}
Ejemplos de sombreros: $ \overline{xy}$, $ \hat{a}$, $ \widehat{abc}$, $ \vec{u}$.
\end{document}
```

### 8.6. Matrices

**Entorno `array`** (similar a `tabular`):

```latex
\begin{document}
Ejemplo de matriz
$$
\left(
\begin{array}{rrr}
1 & 2 & 3 \\
x & y & z \\
\end{array}
\right)
$$
\end{document}
```

**Entornos del paquete amsmath:**

| Entorno | Delimitadores |
|---|---|
| `matrix` | Sin delimitadores |
| `pmatrix` | Paréntesis |
| `vmatrix` | Barras verticales |
| `Vmatrix` | Dobles barras verticales |
| `bmatrix` | Corchetes |
| `Bmatrix` | Llaves |

**Ejemplo 8.9:**
```latex
% PREÁMBULO
\usepackage{amsmath}

% CUERPO
\begin{document}
Ejemplo de determinante
$$
\begin{vmatrix}
1 & x & \alpha \\
2 & y & \beta \\
3 & z & \gamma
\end{vmatrix}
$$
\end{document}
```

### 8.7. Teoremas

**Paquete:** `amsthm`

**Declaración:**
```latex
\newtheorem{entorno}{texto}
```

**Ejemplo 8.10:**
```latex
% PREÁMBULO
\usepackage{amsthm}
\newtheorem{midef}{Definición}
\newtheorem{teo}{Teorema}

% CUERPO
\begin{document}
\begin{midef}
Dado un triángulo rectángulo de catetos \(a\), \(b\) e hipotenusa \(c\), se define el seno del ángulo \(\alpha\) opuesto al cateto \(b\) como
$$
\sen{\alpha}= \frac{b}{c}.
$$
\end{midef}

\begin{teo}
Para cualquier ángulo \(\alpha\) se cumple \(\sen{\alpha}^2 + \cos{\alpha}^2 = 1\).
\end{teo}

\begin{proof}
Es una consecuencia directa del teorema de Pitágoras.
\end{proof}
\end{document}
```

**Salida:**
> **Definición 1.** Dado un triángulo rectángulo de catetos *a*, *b* e hipotenusa *c*, se define el seno del ángulo α opuesto al cateto *b* como
> sen α = b/c.
>
> **Teorema 1.** Para cualquier ángulo α se cumple sen(α)² + cos(α)² = 1.
>
> **Demostración.** Es una consecuencia directa del teorema de Pitágoras.

---

## 9. Entornos flotantes

Los entornos flotantes ubican automáticamente figuras y tablas sin dejar espacios vacíos.

### 9.1. Entorno flotante para figuras

```latex
\begin{figure}[posición]
  Código de las imágenes
  \caption{leyenda}
  \label{etiqueta}
\end{figure}
```

**Posiciones:** `h` (aquí), `t` (arriba), `b` (abajo).

**Ejemplo 9.1:**
```latex
% PREÁMBULO
\usepackage{graphicx}

% CUERPO
\begin{document}
Ejemplo de imagen flotante. Como se puede apreciar la imagen aparece al principio de la página aunque va después de este párrafo en el código fuente.

\begin{figure}[t]
\begin{center}
\includegraphics{img/logo-aprendeconalf.png}
\end{center}
\caption{Logotipo del sitio web AprendeconAlf.}
\label{img-1}
\end{figure}
\end{document}
```

**Listado de figuras:** `\listoffigures`

### 9.2. Entorno flotante para tablas

```latex
\begin{table}[posición]
  \caption{leyenda}
  \label{etiqueta}
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

**Ejemplo 9.2:**
```latex
\begin{document}
\begin{table}[t]
\begin{center}
\begin{tabular}{lcr}
Nombre & Ciudad & Edad \\
María & Valencia & 22 \\
Juan & Madrid & 50 \\
Carmen & Barcelona & 35 \\
\end{tabular}
\end{center}
\caption{Tabla de clientes de una empresa.}
\label{tabla-1}
\end{table}
\end{document}
```

**Listado de tablas:** `\listoftables`

---

## 10. Referencias cruzadas y notas a pie

### 10.1. Referencias cruzadas

| Comando | Efecto |
|---|---|
| `\label{etiqueta}` | Asigna una etiqueta |
| `\ref{etiqueta}` | Referencia al elemento |

**Ejemplo 10.1:**
```latex
% PREÁMBULO
\usepackage{amsmath}
\DeclareMathOperator{\sen}{sen}
\usepackage{amsthm}
\newtheorem{teo}{Teorema}

% CUERPO
\begin{document}
\begin{teo}\label{teo-trigo}
Para cualquier ángulo $\alpha$ se cumple
\begin{equation}\label{eq-trigo}
\sen(\alpha)^2 + \cos(\alpha)^2 = 1.
\end{equation}
\end{teo}

Ejemplo de referencia cruzada. La ecuación \ref{eq-trigo} del teorema \ref{teo-trigo} es una ecuación básica en trigonometría.
\end{document}
```

### 10.2. Notas a pie de página

**Comando:** `\footnote{...}`

**Ejemplo 10.2:**
```latex
\begin{document}
El logotipo de latex es LaTeX.\footnote{Fue creado por Leslie Lamport.}
\end{document}
```

---

## 11. Citas y referencias bibliográficas

**Herramientas:** BibTeX (incluido en LaTeX) o biber (soporta Unicode).

**Formato de fichero:** `.bib`

**Ejemplo 11.1: Fichero bibliografia.bib**
```bibtex
@book{lamport_latex_1994,
  edition = {2nd},
  title = {{LaTeX}: {A} {Document} {Preparation} {System}, 2nd {Edition}},
  isbn = {978-0-201-52983-8},
  publisher = {Addison-Wesley Professional.},
  author = {Lamport, Leslie},
  month = jun,
  year = {1994}
}

@article{borbon_latex_2022,
  title = {{LaTeX}: {Primeros} pasos},
  journal = {Revista digital Matemática, Educación e Internet.},
  author = {{Borbón, Alexandér} and {Mora, Walter}},
  year = {2022},
  pages = {2--7},
}
```

**Ejemplo 11.2:**
```latex
% PREÁMBULO
\usepackage{biblatex}
\addbibresource{bibliografia.bib}

% CUERPO
\begin{document}
El principal libro sobre latex es \cite{lamport_latex_1994}, aunque también es muy interesante el artículo \cite{borbon_latex_2022}

\printbibliography
\end{document}
```

**Salida:**
> El principal libro sobre latex es [2], aunque también es muy interesante el artículo [1].
>
> **Referencias**
> [1] Borbón, Alexander y Mora, Walter. "LaTeX: Primeros pasos". En: Revista digital Matemática, Educación e Internet. (2022), págs. 2-7.
> [2] Leslie Lamport. LaTeX: A Document Preparation System, 2nd Edition. 2nd. Addison-Wesley Professional., jun. de 1994. isbn: 978-0-201-52983-8.

**Estilos de citación:**
```latex
\usepackage[backend=biber, style=alphabetic]{biblatex}
```

**Salida con estilo alphabetic:**
> El principal libro sobre latex es [Lam94], aunque también es muy interesante el artículo [BM22].

---

## 12. Diseño de página

### 12.1. Dimensiones y márgenes

**Paquete:** `geometry`

| Opción | Descripción |
|---|---|
| `a4paper`, `a5paper`, `b1paper`, `letterpaper` | Tamaños predefinidos |
| `paperheight=x` | Longitud vertical |
| `paperwidth=x` | Longitud horizontal |
| `landscape` | Orientación horizontal |
| `margin=x` | Los cuatro márgenes |
| `left=x`, `right=x`, `top=x`, `bottom=x` | Márgenes individuales |

**Ejemplo 12.1:**
```latex
% PREÁMBULO
\usepackage[a5paper, landscape]{geometry}
\usepackage{blindtext}

% CUERPO
\begin{document}
\section{Introducción}
Esta es una página de tamaño A5 apaisada.

\subsection{Texto de relleno}
\blindtext
\end{document}
```

**Ejemplo 12.2:**
```latex
% PREÁMBULO
\usepackage[a4paper, left=2.5cm, right=3.5cm, top=45mm, bottom=20mm]{geometry}
\usepackage{blindtext}
```

### 12.2. Encabezados y pies de página

**Paquete:** `fancyhdr`

**Configuración:**
```latex
\pagestyle{fancy}
\fancyhead{} % Borra el encabezado por defecto
\fancyfoot{} % Borra el pie por defecto
```

**Áreas:** `L` (izquierda), `C` (centro), `R` (derecha). Para doble cara: `E` (pares), `O` (impares).

| Comando | Efecto |
|---|---|
| `\fancyhead[opcion]{texto}` | Añade texto al encabezado |
| `\fancyfoot[opcion]{texto}` | Añade texto al pie |
| `\headrulewidth` | Grosor de línea del encabezado |
| `\footrulewidth` | Grosor de línea del pie |
| `\headsep=x` | Separación encabezado-cuerpo |
| `\footskip=x` | Separación pie-cuerpo |

**Ejemplo 12.4:**
```latex
% PREÁMBULO
\usepackage{blindtext}
\usepackage[top=4cm, headsep=2cm]{geometry}
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhead{} % Borra el encabezado por defecto
\fancyhead[R]{\textbf{Mi encabezado}}
\fancyhead[C]{Alfredo Sánchez}
\fancyfoot{} % Borra el pie por defecto
\fancyfoot[R]{\thepage}
\fancyfoot[L]{\texttt{http://aprendeconalf.es}}
\renewcommand{\headrulewidth}{0pt}

% CUERPO
\begin{document}
\section{Introducción}
Este es una página con encabezado y pie personalizado.

\subsection{Texto de relleno}
\blindtext[9]
\end{document}
```

---

## Bibliografía y recursos

### Libros

- Cascales, B. y otros (2003). *El libro de LaTeX*. Pearson Educación.
- Cascales, B. y otros (2000). *LaTeX: una imprenta en sus manos*. Aula Documental de Investigación.
- Lamport, Leslie (1994). *LaTeX: A Document Preparation System, 2nd Edition*. 2nd ed. Addison-Wesley Professional.
- Mittelbach, F. et al. (2004). *LaTeX Companion, The, 2nd Edition*. 2nd ed. Addison-Wesley Professional.
- Oetiker, T et al (2021). *The not so short introduction to LaTeX 2e*.

### Sitios Web

- **The LaTeX project** — Sitio web principal del proyecto LaTeX.
- **Comprehensive TeX Archive Network** — Principal repositorio de paquetes para TeX y LaTeX.
- **CervanTeX** — Grupos de usuarios de TeX hispanohablantes.
- **Awesome LaTeX** — Sitio web con multitud de recursos curados para escribir documentos con LaTeX.
- **Chuleta de LaTeX** — Resumen de los principales comandos y entornos de LaTeX.

---

## Plantilla LaTeX

```latex
\documentclass[11pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[spanish]{babel}
\usepackage[T1]{fontenc}
\usepackage{geometry}
\geometry{margin=2.5cm}
\usepackage{hyperref}
\usepackage{graphicx}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{amsthm}
\usepackage{booktabs}
\usepackage{float}

\title{Manual de LaTeX}
\author{Alfredo Sánchez Alberca}
\date{\today}

\begin{document}

\maketitle

\begin{abstract}
Manual introductorio al lenguaje de composición de textos LaTeX
orientado a la creación de documentos científicos y técnicos
con contenido matemático.
\end{abstract}

\tableofcontents
\newpage

\section{Introducción}
% completar

\section{Estructura de un documento}
% completar

\section{Secciones y párrafos}
% completar

\section{Formateo básico}
% completar

\section{Listas}
% completar

\section{Tablas}
% completar

\section{Imágenes}
% completar

\section{Fórmulas matemáticas}
% completar

\section{Entornos flotantes}
% completar

\section{Referencias cruzadas y notas a pie}
% completar

\section{Citas y referencias bibliográficas}
% completar

\section{Diseño de página}
% completar

\end{document}
```

---

**Fin del documento estructurado.**
**Páginas cubiertas:** 1–63
**Identificadores JSON únicos:** image-01 a image-03
**Total de palabras:** ~9,500
