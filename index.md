--- 
title: "Analitica de Datos Industriales Segunda Edición"
author: "Dr. Ing. Ricardo R. Palma"
date: "2025-10-22"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
# url: your book url like https://bookdown.org/yihui/bookdown
# cover-image: path to the social sharing image like images/cover.jpg
description: |
  This is a minimal example of using the bookdown package to write a book.
  The HTML output format for this example is bookdown::bs4_book,
  set in the _output.yml file.
biblio-style: apalike
csl: chicago-fullnote-bibliography.csl
---

# Acerca de este curso {-}

![Doctorado Interinstitucional en Ingeniería Industrial Di3](images/coverMZA_Di3.png)

## Requerimiento y competencias {-}

No se requieren conocimiento previos de programación para trabajar en este curso.
Es solamente necesario un repaso de algunos conceptos de estadística y algo de experiencia en gestión de la cadena de suministros

Este curso tendrá más valor agragado para ti si en logar de utilizar los datos que te entregamos utilizas tus propios datos. Esto es lo que llamaremos datasets. En general tus datos pueden venir de hojas de cálculo, pero la tecnología que utilizaremos puede manejar volúnemes de información cientos o miles de veces más extensas que tu hoja de excel más grande que puedas concebir.

## Software utilizado {-}

Utilizaremos R-Cran


![R-Cran site ](images/Rlogo.png)

Que puedes bajarlo de este sitio:

[Descargar R-Cran](https://cran.r-project.org/bin/windows/)
Hay versiones para Mac y Linux

Complementaremos el trabajo con R-Studio (hoy llamado Posit)

![ Posit https://posit.co/downloads/ ](images/posit.png)

Finalmente es conveniente (no absolutamente necesario) que sepas trabajar en github.

![GitHub](images/github.png)





```r
bookdown::render_book()
```

To render this example to PDF as a `bookdown::pdf_book`, you'll need to install XeLaTeX. You are recommended to install TinyTeX (which includes XeLaTeX): <https://yihui.org/tinytex/>.

## Preview book {-}

As you work, you may start a local server to live preview this HTML book. This preview will update as you edit the book when you save individual .Rmd files. You can start the server in a work session by using the RStudio add-in "Preview book", or from the R console:


```r
bookdown::serve_book()
```



