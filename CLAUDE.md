# Resúmenes de Física Electrónica

Apuntes en LaTeX, uno por unidad, a partir del libro (Pierret, *Semiconductor Device
Fundamentals*) y de las diapositivas de clase (PDFs en la raíz).

## Estructura
- `comun/preambulo.tex`: paquetes, colores, cajas (`definicion`, `clave`, `ejemplo`,
  `ojo`, `intuicion`), macros (`\diapo{n}`, `\EG`, `\lG`, `\Resp`, ...) y estilos TikZ
  (`bandac`, `bandav`, `elec`, `hueco`, `foton`). Reutilizarlo en todas las unidades.
- `unidades/NN-nombre/nombre.tex`: documento principal; hace
  `\input{../../comun/preambulo.tex}` y `\input{secciones/...}`.
- Se versionan el `.tex` y el `.pdf` compilado; los auxiliares están en `.gitignore`.

## Compilar
    cd unidades/06-optoelectronica && latexmk -pdf optoelectronica.tex

## Criterios de contenido
- Apunte completo (~20–30 págs.): derivaciones, figuras TikZ/pgfplots propias, ejemplos
  numéricos verificados, formulario y preguntas de repaso al final.
- No copiar las convenciones de las diapositivas al pie de la letra; corregir errores en
  cajas `ojo` citando `\diapo{n}` y listarlos en la tabla final de correcciones.
- Ojo con babel-spanish: no usar `\%` dentro de modo matemático (usar `\SI{..}{\percent}`);
  dentro de `axis` de pgfplots no usar `\foreach` con `axis cs:\x`.
