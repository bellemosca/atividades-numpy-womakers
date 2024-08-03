# Manipulando array

### Index em um array de 1 dimensão
---
arr = np.array([2,4,6,8])

arr[2]

-- A indexisação como sempre a partir do 0 

-- Para lhe dar com array de 2D a gente sempre indexa linha e coluna 

- cartela_bing[1, 3]
- 27

-- Se quiser selecionar uma linha inteira 

- cartela_bing[0]
- array([16, 10, 3, 15])

-- Se quiser escolher uma coluna tem usar o atributo da ','

-- Os ':' vai indicar a linha inteira 

- cartela_bing[:, 1]
- array([10, 23, 19, 4])

### Fatiar (slicing) um array de 1 dimensão
----

- arr = np.array([2,4,6,8,10])

- arr[2:4]

- --> array([6,8])

### Fatiar (slicing) um array de 2D
-----
- cartela_bingo[1:3, 0:2]   
         
         array([14, 23],

               [6, 19])
    
### Ordenar (sorting) um array
---
Ele vai fazer uma ordenação em relação a cada coluna
- np.sort(cartela_bingo)
  
        array([[3, 10, 15, 15],
               [14, 17, 23, 27]
               [1, 3, 6, 19]
               [4, 10, 18, 19]])

### Eixos (axis)
---
Temos o axis 0(linhas) e o axis 1(colunas)

np.sort(cartela_)


