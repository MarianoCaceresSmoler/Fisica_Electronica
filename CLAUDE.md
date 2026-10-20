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
    cd unidades/<NN-unidad> && latexmk -pdf <unidad>.tex

## Referencias oficiales de la materia
- `Hojas de fórmulas.pdf`: hoja que se lleva al examen. Su notación es la canónica (p. ej. BJT en PNP,
  `I_F0`, `α_F`, `γ`, `α_T`). Marcar con `\enhoja` (en el título de una caja) o `\enhojatexto` los
  resultados que figuran en ella.
- `Tabla de constantes.pdf`: valores oficiales, cargados como macros en `comun/constantes.tex`
  (`\niSi`, `\munSi`, `\qval`, `\tablaconstantes`, ...). Usarlos en todos los ejemplos numéricos.

## Criterios de contenido
- Apunte completo (~20–30 págs.): derivaciones, figuras TikZ/pgfplots propias, ejemplos
  numéricos verificados, formulario y preguntas de repaso al final.
- No copiar las convenciones de las diapositivas al pie de la letra; corregir errores en
  cajas `ojo` citando `\diapo{n}` y listarlos en la tabla final de correcciones.
- Ojo con babel-spanish: no usar `\%` dentro de modo matemático (usar `\SI{..}{\percent}`);
  dentro de `axis` de pgfplots no usar `\foreach` con `axis cs:\x`.
- Cada unidad terminada y compilada se commitea (tex + pdf).
