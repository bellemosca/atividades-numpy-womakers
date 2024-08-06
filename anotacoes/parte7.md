## Operações com vetorização

Ao realizar a soma de elementos em um array utilizando o Numpy, a operação não ocorre de forma individual para cada elemento; em vez disso, ela é realizada de maneira simultânea para todos os elementos.

## Sintax Numpy

No Numpy, a sintaxe é otimizada: empregamos um sinal de adição e indicamos ao numpy o número único que desejamos adicionar a todos os elementos do array. Na linguagem matemática, esse único número é comumente denominado escalar. Podemos utilizar uma sintaxe semelhante para multiplicar um array por um escalar.

      arr = np.array([[1, 2], [4, 5]])
      arr += 3
      arr
      array([[4, 5],
             [7, 8]])
---
      arr2 = np.array([[1, 2],[4, 5]])
      arr2 * 5
      array([[5, 10],
             [20, 25]])

## Adicionando 2 array
O Numpy permite operações vetorizadas entre arrays do mesmo formato. Na adição de dois arrays com o mesmo formato, o Numpy realiza a operação elemento por elemento, somando cada elemento do primeiro array ao elemento correspondente no segundo array.
      
      a = np.array([[1, 2, 3], [4, 5, 6]])
      b = np.array([[2, 2, 2], [0, 0, 1]])
      a + b
      array([[3, 4, 5],
             [4, 5, 7]])

## Multiplicando 2 arrays
O mesmo conceito se aplica à multiplicação, subitração e divisão de dois arrays no Numpy. Nessas operações, os elementos nas posições correspondentes de cada array são multiplicados, subtraídos ou divididos entre si.

      a = np.array([[1, 2, 3], [4, 5, 6]])
      b = np.array([[2, 2, 2], [0, 0, 1]])
      a * b
      array([[2, 4, 6],
             [0, 0, 6]])

## Operações booleanas
Embora as operações vetorizadas se destacam em operações matemáticas, seu aproveitamento se estende por todo o Numpy. Anteriormente, exploramos o uso dessas operações para criar máscaras booleanas e filtrar arrays.

      a = np.array([[1, 2, 3], [4, 5, 6]])
      a > 3
      array([[False, False, False],
             [True, True, True]])

## Vetorizando código Python(np.vectorize)

np.vectorize transforma funções Python regulares em funções vetorizadas. Isso significa que podemos aplicar eficientemente uma função a cada elemento de um array Numpy sem nos preocuparmos com loops explícitos. É muito útil quando precisamos operar em arrays, mas temos funções projetadas para operar em valores únicos.

      arr = np.array(["Hello", "meninas", "coders"])
      len(arr) > 5
      False
---
      vetorizar_len = np.vectorize(len)
      vetorizar_len(arr) > 5
      array([False, True, True])
___
      def minha_funcao(x):
          return x**2 + 3*x + 1
      
      vetorizada_funcao = np.vectorize(minha_funcao)

      array_original = np.array([1, 2, 3, 4, 5])

      resultado = vetorizada_funcao(array_original)

      resultado

      array([5, 11, 19, 29, 41])

## Broadcasting (trasmissão)

Broadcasting(trasmissão) refere-se à capacidade do Numpy de lidar com operações entre arrays de diferentes formar e tamanhos durante operações aritiméticas. O Broadcasting permite que o Numpy execute essas operações mesmo quando as dimensões dos arrays não são as mesmas, seguindo um conjunto de regras específicas.

      arr2 = np.array([[1, 2], [4, 5]])
      arr2 * 5
      
      array([[5, 10],
             [20, 25]])
---
      arr_3x3 = np.array([[1, 2],
                          [4, 5],
                          [7, 8]])
      arr_3x3

      array([[1, 2],
             [4, 5],
             [7, 8]])
---
      arr_3x1 = np.array([1, 0, -1]).reshape((3, 1))
      arr_3x1

      array([[1],
             [0],
             [-1]])
---
      arr_3x3 + arr_3x1

      array([[2, 3],
             [4, 5],
             [6, 7]])

## Linhas

      arr10 = np.arange(10).reshape((2, 5))
      arr5 = np.array([0, 1, 2, 3, 4])
      arr10.shape, arr5.shape

      ((2, 5), (5,))
---
      arr10 + arr5
      
      array([[0, 2, 4, 6, 8],
             [5, 7, 9, 11, 13]])

## Colunas
      arr10 = np.arange(10).reshape((2, 5))
      arr2 = np.array([0, 1]).reshape(2, 1)
      arr10.shape, arr2.shape

      ((2, 5), (2, 1))
___
      arr10 + arr2

      array([[0, 1, 2, 3, 4]
             [6, 7, 8, 9, 10]])

## Outras operações

A aplicação das mesma lógica estende-se à multiplicação, subitração e divisão! AO multiplicar por uma coluna, cada elemento dessa coluna é multiplicado pelos elementos correspondentes em ambas as colunas do array maior. Da mesma forma, ao subitrair uma linha, cada elemento dessa linha é subitraido dos elementos correspondentes em ambas as linhas do array maior.

      arr10 = np.arange(10).reshape((2, 5))
      arr2 = np.array([2, 1]).reshape(2, 1)
      arr10.shape, arr2.shape

      ((2, 5), (2, 1))
      
      -
      arr10/arr2

      array([[0. , 0.5, 1.5, 2. ],
             [5. , 6. , 7. , 8. , 9. ]])
---
      arr10 = np.arange(10).reshape((2, 5))
      arr2 = np.array([2, 1]).reshape(2, 1)
      arr10.shape, arr2.shape

      ((2, 5), (2, 1))

      -

      arr10 * arr2

      array([[0, 2, 4, 6, 8],
             [5, 6, 7, 8, 9]])


# Salvando arquivos Numpy
### Por quê usar arquivos .npy?
Dados numpy podem ser salvos em diferentes formatos:

- .npy(NumPy Binary)
- .txt(Text/CSV)
- .h5(HDF5 - Hierarchial Data Format)
- .json(JSON)
- .csv(Comma-Separeted Values)
- .parquet(Apache Parquet)
---

#### 1. Eficiência de Aramazenamento: 
O formato binário utilizado é altamente eficiente em termos de armazenamento, sendo especialmente útil para grandes conjuntos de dados, reduzindo os requisitos de espaço e melhorando a velocidade de operações de leitura e escrita.

#### 2. Preservação de Informações:
Ao salvar um array como .npy, o formato inclui indformações cruciais sobre o tipo de dados e a forma do array. Isso garante que, ao carregá-lo posteriormente, a estrutura original seja recriada com precisão, evitando perda de informações.

#### 3. Carregamento Rápido:
O carregamento de dados a partir de um arquivo .npy é geralmente mais rápido do que em formatos de texto. Isso se deve à eficiente serialização e deserialização dos dados, resultando em tempos de carregamento mais curtos.

#### 4. Compatibilidade com NumPy:
O formato .npy é específico do Numpy, proporcionando compatibilidade sólida com outra ferramentas e bibliotecas baseadas em Numpy. Estabelece uma maneira padronizada e confiável de armazenar e compartilhar array de diferentes projetos e colaboradores.

#### Carregando

      arr = np.load('arr10.npy')
      arr

      array([[0, 1, 2, 3, 4],
             [5, 6, 7, 8, 9]])

#### Salvando

      arr10 = np.arange(10).reshape((2, 5))
      arr10

      array([[0, 1, 2, 3, 4],
             [5, 6, 7, 8, 9]])

      np.save('arr10.npy', arr10)
      


