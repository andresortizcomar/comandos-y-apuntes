# PDFs

## Comprimir un pdf mediante PS
Se realiza en 2 pasos

### 1. Se crea un archivo ps

> pdf2ps archivo-grande.pdf archivo-grande.ps

### 2. Se crea un pdf

> ps2pdf archivo-grande.ps archivo-chico.pdf

-----

## Con PDFTK

> gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -dNOPAUSE -dQUIET -dBATCH -sOutputFile=optimizado.pdf original.pdf

Hay /printer, /ebook, /screen, etc.


