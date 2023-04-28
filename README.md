
# Filtros de Imagem

Este repositório contém implementações em Python alguns filtros de imagem, como: Filtro da Média, Filtro Gaussiano e Filtro Laplaciano.

## Filtro da Média

O Filtro da Média é um dos filtros mais simples que pode ser aplicado a uma imagem. Este filtro é usado para suavizar a imagem, reduzindo o ruído e os detalhes finos. A ideia é simples: para cada pixel na imagem, o valor deste pixel é substituído pela média dos valores dos pixels em sua vizinhança.

A implementação do Filtro da Média pode ser encontrada na função filter_mean().

## Filtro Gaussiano
O Filtro Gaussiano é outro filtro utilizado para suavizar a imagem. A diferença entre o Filtro da Média e o Filtro Gaussiano é que o Filtro Gaussiano leva em conta o desvio padrão dos valores dos pixels em sua vizinhança, enquanto o Filtro da Média não leva em conta esta informação. O Filtro Gaussiano é uma opção melhor do que o Filtro da Média quando há muitos detalhes finos na imagem.

A implementação do Filtro Gaussiano pode ser encontrada no arquivo gaussian_kernel().

## Filtro Laplaciano
O Filtro Laplaciano é um filtro utilizado para realçar as bordas de uma imagem. Este filtro calcula a diferença entre o valor do pixel central e a média dos valores dos pixels em sua vizinhança. O resultado é uma imagem onde as bordas ficam mais visíveis.

A implementação do Filtro Laplaciano pode ser encontrada no arquivo return_neighborhood().

## Dependências

As seguintes bibliotecas são necessárias para rodar os scripts:

- `numpy`
- `pandas`
- `cv2`
- `math`
- `matplotlib`

## Exemplo de uso

O código abaixo mostra um exemplo de como usar os filtros implementados:

```python
import numpy as np
import pandas as pd
import cv2
import math
import matplotlib.pyplot as plt

# Filtro da Média
def return_neighborhood_mean(image, x, y):
    ...

def filter_mean(image):
    ...

# Filtro Gaussiano
def return_neighborhood(image, x, y):
    ...

def gaussian_kernel(size, sigma):
    ...

def convolution_image(image, kernel):
    ...

# Filtro Laplaciano
def return_neighborhood(image, x, y):
    ...

image = cv2.imread("/kaggle/input/imagejpeg/images.jpeg")
img_gray = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)

image_mean = filter_mean(img_gray)
hist, bins = np.histogram(image.ravel(), 256, [0, 256])
fig, axis = plt.subplots(1, 2, figsize=(10, 5))

axis[0].imshow(img_gray, cmap='gray')
axis[0].axis('on')
axis[0].set_title('Imagem Original')

axis[1].imshow(image_mean, cmap='gray')
axis[1].axis('on')
axis[1].set_title('Após filtro média')

plt.show()

kernel = gaussian_kernel(3, 2)
image_gaussian = convolution_image(img_gray, kernel)

fig, axis = plt.subplots(1, 2, figsize=(10, 5))

axis[0].imshow(img_gray, cmap='gray')
axis[0].axis('on')

axis[1].imshow(image_gaussian, cmap='gray')
axis[1].axis('on')

plt.show()


```


## Autores

- [@igorbezerrar](https://www.github.com/igorbezerrar)

