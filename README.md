# Funciones-Estadistica-III

Funciones de apoyo para el curso Estadística III (series de tiempo), Universidad Nacional de Colombia, sede Medellín.

## Test HEGY: `Funcion-HEGY.test.R`

La función `HEGY.test()`, usada en el Capítulo 11 de las notas de clase para el test HEGY de raíces unitarias estacionales, venía en el paquete `pdR`. La versión actual de `pdR` en CRAN (1.9.4) ya no la incluye. Este archivo contiene la función tal como estaba en `pdR` 1.9.3, sin modificaciones, para que pueda usarse con R y todos los paquetes en su versión actual.

No requiere instalar `pdR` ni ningún otro paquete. Basta con cargarla así:

```r
source("https://raw.githubusercontent.com/patiaeh/Funciones-Estadistica-III/main/Funcion-HEGY.test.R")
```

y usarla igual que en las notas de clase:

```r
suppressWarnings(HEGY.test(wts=yt, itsd=c(0,0,c(0)), selectlags=list(mode="aic", Pmax=12))$stats)
```

Los valores p que reporta la función están acotados a 0.10: un valor p de 0.10 significa "mayor o igual que 0.10".

Si con `mode="aic"` aparece el error "subíndice fuera de los límites" (un fallo del código original en algunas series), use `selectlags=list(mode="signf", Pmax=12)`.

## Créditos y licencia

El código de `HEGY.test()` y de sus funciones auxiliares es de Ho Tsung-wu, autor del paquete `pdR` (versión 1.9.3, 2024, <https://cran.r-project.org/src/contrib/Archive/pdR/>), y se redistribuye bajo la misma licencia, GPL (>= 2). Ver el archivo `LICENSE`.
