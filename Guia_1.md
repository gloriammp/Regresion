---
title: "Ejercicios Regresión"
author: "Gloria"
date: '2025-04-07'
output:
  html_document:
    keep_md: true
    toc: yes
    code_folding: show
    toc_float: yes
    df_print: paged
    theme: flatly
    code_download: yes
  pdf_document:
    toc: yes
---


<br>
<br>

## Capítulo 1

<br>

### <span style="color:#18bc9c">Correlación</span>

<br>

Ejercicio 1.1. \
<br>
En el archivo grasacerdos.xlsx se encuentran los datos del peso
vivo (PV, en Kg) y al espesor de grasa dorsal (EGD, en mm) de 30 lechones
elegidos al azar de una población de porcinos Duroc Jersey del Oeste de la
provincia de Buenos Aires. Se pide: \
<br>
(a) Dibujar el diagrama de dispersión e interpretarlo.\
<br>
(b) Calcular el coeficiente de correlación muestral y explíquelo.\
<br>
(c) ¿Hay suficiente evidencia para admitir asociación entre el peso y el espesor de grasa? (α = 0,05). Verifique los supuestos para decidir el indicador
que va a utilizar.\



```
## # A tibble: 5 × 3
##     Obs PV    EGD  
##   <dbl> <chr> <chr>
## 1     1 56,81 16,19
## 2     2 70,40 22,00
## 3     3 71,73 19,52
## 4     4 75,10 31,00
## 5     5 79,65 23,58
```
Cambiamos las "," por "." y visualizamos cuantos nulos hay  por columna. Convertimos las columnas de PV y EGD a numéricas. Pedimos el summary del dataframe. 


```
## tibble [30 × 3] (S3: tbl_df/tbl/data.frame)
##  $ Obs: num [1:30] 1 2 3 4 5 6 7 8 9 10 ...
##  $ PV : chr [1:30] "56.81" "70.40" "71.73" "75.10" ...
##  $ EGD: chr [1:30] "16.19" "22.00" "19.52" "31.00" ...
## NULL
```

```
## Obs  PV EGD 
##   0   0   0
```

```
##        PV             EGD       
##  Min.   :27.51   Min.   : 7.29  
##  1st Qu.:55.47   1st Qu.:16.47  
##  Median :64.94   Median :21.55  
##  Mean   :63.07   Mean   :21.60  
##  3rd Qu.:70.15   3rd Qu.:25.92  
##  Max.   :93.00   Max.   :40.90
```
<br>
(a) 


![](Guia_1_files/figure-html/unnamed-chunk-3-1.png)<!-- -->
![](Guia_1_files/figure-html/unnamed-chunk-4-1.png)<!-- -->
En los datos visualizados  no pareciera haber asociación entre las variables. 

(b)
<br>
En primer lugar analizo la normalidad de las variables mediante los gráficos de los histogramas, los qqplots y la prueba de Shapiro.
![](Guia_1_files/figure-html/unnamed-chunk-5-1.png)<!-- -->
![](Guia_1_files/figure-html/unnamed-chunk-6-1.png)<!-- -->

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  PV
## W = 0.97533, p-value = 0.6925
```



```
## 
## 	Shapiro-Wilk normality test
## 
## data:  EGD
## W = 0.98514, p-value = 0.9395
```
Por el test de Shapiro Wilk no se puede rechazar la normalidad de los datos en ninguno de los dos casos. 
<br>
Análisis de la normalidad multivariada - Test de Henze Zirkler
