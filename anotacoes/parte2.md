# Por que usar numpy e não listas?

#### - Arrays numpay aceita que todos o elementos sejam de diferentes tipos de dados, contudo o array sempre terá apenas um tipo de dados. Contudo a normal dentro da análise de dados que usamos apenas um tipo de dados dentro de um array
#### - Um único tipo de dados também resulta em arrays numpy ocupando menos espaço na memória em comparação com listas.
#### - Quando precisamos de uma estrutura multidimensional para armazenar os dados, optamos por arrays em vez de listas, pois as listas podem ser unidimensionais apenas.
#### - Se precisarmos de um comprimento fixo e alocação estática, usamos arrays em vez de listas.
#### - Quando é nescessária um processamento de dados mais rápido, preferimos arrays em vez de listas.
#### - Tipos de dados primitivos podem ser armazenados diretamente em arrays, mas não em listas.

## Arrays e mais dimensões

#### Array 3D
- arr1_2d = np.array([[1,2],[3,4]])
- arr2_2d = np.array([[5,6],[7,8]])
- arr3_2d = np.array([[9,2],[3,4]])

- arr_3d = np.array([arr1_2d, arr2_2d, arr3_2d])

##### Alguns programadores e a documentação do numpay as vezes vão se referir ao array como vetores, matrizes ou tensores. Esses termos são mais matemáticos. 
##### Um vetor se refere a um array com uma dimensão só.
##### Na matemática nos conseguimos enxergar coisas bidimensionais como matriz e tridimensionais como tensores.

## Dimensões do array (atributos e métodos)

#### Atributo:
- .shape
#### Método:
- .flatter()
- .reshape()

## Linhas e colunas em arrays 2D
- Linhas(rows) são a primeira dimensão (horizontal)
- Colunas (columns) são a segunda dimensão (vertical)

## "Achatando" um array
#### Coloca a array em apenas uma dimensão
.fltter()

## Reshaping- mudando as dimensões
arr = np.array([3,2,4], [8,11,5])

arr.reshape((3,2))


