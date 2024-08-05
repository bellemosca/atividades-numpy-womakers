## Adicionando e removendo dados do array

#### Concatenando linhas:
      arrv1 = np.random.randint(10, size=(3,2))
      arrv1
      array([[7, 6],
            [4, 1],
            [1, 1]])

      arrv2 = np.array([["Peras","Morangos"]])
      arrv2
      array([['Peras', 'MOrango']], dtype='<U7')

      np.concatenate((arrv1, arrv2))
      array([['7', '6'],
            ['4', '1'],
            ['1', '1'],
            ['Pera', 'Morango']], dtype='<U21')
___
#### Concatenando colunas:
      arrv1
      array([[7, 6]
             [4, 1]
             [1, 1]])
      
      arro1 = np.array(["Uva","Abacaxi", "Laranja"]).reshape((3, 1))
      arro1
      array([['Uva','Abacaxi', 'Laranja']], dtype='<U7')

      np.concatenate((arrv1, arro1), axis=1)
      array([['7','6','Uva'],
             ['4','1','Abacaxi'],
             ['1','1','Laranja']], dtype='<U21')

- É possível adicionar arrays para criar novas dimensões
- Mas o método np.concatenate não permite
- É compatível apenas para dimensões já existentes no array

---
#### Deletanto com np.delete():

Deletando com axis = 0
      
      sala_espera
      array([['5','30','1','Alice'],
             ['6','29','1','Bob'],
             ['7','35','3','Cristina']
             ['8','34','3','Luiz']], dtype='<U8')

      np.delete(sala_espera, 2, axis=0)
      array([['5','30','1','Alice'],
             ['6','29','1','Bob']
             ['8','34','3','Luiz']], dtype='<U8')

Deletando com axis = 1

      sala_espera
      array([['5','30','1','Alice'],
             ['6','29','1','Bob'],
             ['7','35','3','Cristina']
             ['8','34','3','Luiz']], dtype='<U8')

      np.delete(sala_espera, 1, axis=1)
      array([['5','1','Alice'],
             ['6','1','Bob']
             ['7','3','Cristina']
             ['8','3','Luiz']], dtype='<U8')

## Cálculos com array

### Métodos de agregação de dados:
#### Python
- .sum()
- .min()
- .max()
- .mean()
- .cumsum()

      acidendentes
      array([[1, 3, 2]
             [0, 1, 0]
             [2, 1, 4]
             [0, 0, 0]
             [1, 1, 0]])
O código a cima é sobre segurode carro, sobre quanto acidente cada um dos três clientes fez ao longo dos ano.
As colunas são os clientes e as linas os anos.

      acitendes.sum()

Esa função soma o array inteiro

Somar linas

      acidentes.sum(axis=0)
      array([4, 6, 6])

Somar colunas

      acidentes.sum(axis=1)
      array([6, 1, 7, 0, 2])

Mínimos e máximos

      acidentes.min()
      0


---
      acidentes.max()
      4

---
      acidentes.max(axis=0)
      arry([2, 3, 4]) 

Média

      acidentes.mean()
      1.0666666666666667

---
      acidentes.mean(axis=0)
      array([0.8, 1.2, 1.2])

---
      acidentes.mean(axis=1)
      array([2.        , 0.33333333, 2.33333333, 0.        , 0.66666667])

Soma cumulativa - cumsum

      acidentes.cumsum(axis=0)
      array([[1, 3, 2],
             [1, 4, 2],
             [3, 5, 6],
             [3, 5, 6],
             [4, 6, 6]])
---
      acidentes.cumsum(axis=1)
      array([[1, 4, 6],
             [0, 1, 1],
             [2, 3, 7],
             [0, 0, 0],
             [1, 2, 2]])



