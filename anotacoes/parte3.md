# Tipo de Dados em um Numpy Array

### Tipos em Numpy vs. tipo em Python:

#### Python
- Int 
- Float

#### Numpy
- np.int64
- np.int32
- np.float64
- np.float32

### Bits e bytes
##### - Bits são digitos binários. Ele é 0 e 1, é a menor unidade de dados de um computador.
##### - Um byte é uma sequência de 8bits 
EX: 2024 (0000011111101000)
np.int32 armaneza 4.294.967.296 em valor de inteiro = 2³²

## Atributo .dtype e tipo de default
##### Ele indica o tipo dos elementos que estão sendo guardados.

## String
np.array(["Hello","Coder","Girls"]).dtype

dtype('<U5')

## Conversão e coerção
#### dtype como argumento

arr_float32 = np.array([2.14,6.25,160.87], dtype=np.float32)

arr_float32
#### Conversão

arr_vf = np.array([[True, False], [True, True]], dtype=np.bool8)

arr_vf.astype(np.int32)

- Tudo que é Falso é 0 e tudo é True é 1
#### Coerção

nparray(["pedra", False, 42 42.42])

## Hierarquia de coerção
Adicionar um float a um array de int mudará todos os valores para float.

np.array ([0,10]).dtype

-> dtype('int64')

----
np.array([0,10,1.]).dtype

-> dtype('float64')

----

Adicionar um inteiro em um array de booleanos transformará todo o array em inteiro

np.array([True, False]).dtype

-> dtype('bool')

----
np.array([True, False, 12]).dtype

-> dtype('int64')
 


