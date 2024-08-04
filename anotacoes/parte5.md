## Indexação sofisticada (fancy) indexing e máscara (mask) em array 2D

     pessoas_id_idade = np.array([1, 22],[2, 21], [3, 27], [4, 26])
     pessoas_id_idade[:, 1] % 2 == 0
     array([True, False, False, True])

#### Boolean mask
- Retorna um array de verdadeiros e falsos

      arr1 = np.array([1, 2, 3, 4, 5])
      mask = arr1 % 2 == 0
      mask
      array([False, True, False, True, False])

#### Fancy indexing
- Retorna os valores do array quando passado a máscara

      arr1[mask]
      array([2, 4])

### Fancy indexing e np.where()
____
#### Fancy indexing
- Retorna os valores do array quando passado a máscara
        
      1  cartela_bingo
      array([[16, 10, 3, 15]
            [14, 23, 17, 27]
            [6, 19, 3, 1]
            [10, 4, 18, 19]])
      np.where(cartela_bingo % 3 == 0)

      1  (array([0, 0, 1, 2, 2, 3], array([2, 3, 3, 0, 2, 2])))
---
#### np.where()
- Retorna um array de indices
- Cria uma matriz com base em se os elementos correspondem ou não a uma condição

      pessoas_id_idade = np.array([[1, 22], [2, 21], [3, 27], 4, 26])
      np.where(pessoas_id_idade[:, 1] % 2 == 0)
      (array([0, 3]),)
---
#### Buscar e substituir

      np.where(cartela_bingo % 3 == 0, "", cartela_bingo)
      array([['16', '10','','']
            ['14', '23', '17','']
            ['', '19','','1']
            ['10','4','','19']], dtype='<U21')

