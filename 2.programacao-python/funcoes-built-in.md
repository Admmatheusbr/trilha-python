Índice

1. [print()](#print)
1. [exercícios print()](#exercícios-print)
1. [len()](#len)
1. [sum()](#sum)
1. [pow()](#pow)
1. [max() e min()](#max-e-min)
1. [abs()](#abs)
1. [round()](#round)
1. [type()](#type)
1. [isinstance()](#isinstance)
1. [ord() e chr()](#ord-e-chr)
1. [help()](#help)
1. [exercícios()](#exercícios)
1. [input()](#input)
1. [range()](#range)
1. [exercícios range](#exercícios-range)
1. [enumerate()](#enumerate)
1. [exercícios enumerate](#exercícios-enumerate)
1. [zip()](#zip)
1. [exercícios zip](#exercícios-zip)
1. [`dir()`](#dir)
1. [exercícios `dir()`](#exercícios-dir)

# funções built-in

As funções built-in do Python são funções que já vêm integradas na linguagem, ou seja, estão disponíveis para uso imediato sem a necessidade de importação de módulos ou bibliotecas adicionais. Essas funções são projetadas para realizar tarefas comuns, como manipulação de strings, números, listas, entre outros, de forma simples e eficiente.

## `print()`

A função `print()` no Python é uma das funções mais fundamentais e amplamente utilizadas. Ela serve para exibir informações na tela, o que é útil tanto para o desenvolvimento e depuração de código quanto para fornecer feedback ao usuário.

A função `print()` exibe os valores que você passa como argumentos, convertendo-os em strings (se necessário) e mostrando-os na tela.

Veja um exemplo básico :

```python
>>> print("Olá, mundo!")
Olá, mundo!
```

Além disso, a função `print()` também possui diversas outras funcionalidades, além de exibir strings e conteúdo de variáveis.

### outras funcionalidades

1. **exibir múltiplos valores** : é possível passar vários argumentos para `print()`, e eles serão exibidos em sequência, separados por um espaço por padrão. os argumentos podem ser valores literais ou variáveis contendo valores.
    ```python
    >>> print("Python", "é", "nota", 10, "!")
    Python é nota 10 !
    >>>
    >>> nota = 10
    >>> linguagem = "Python"
    >>>
    >>> print(linguagem, "é", 'nota', nota, "!")
    Python é nota 10 !
    ```

1. **separador personalizado** : sempre que vários argumentos são passados para o `print()` (separados por vírgulas), por padrão, a função adiciona um espaço em branco entre os argumentos. contudo, é possível alterar esse comportamento especificando o argumento `sep` logo antes de fechar o parênteses. o valor que for passado ao `sep` deverá ser uma `string`.
    ```python
    >>> print("Python", "é", "incrível!", sep="-")
    Python-é-incrível!
    >>>
    >>> print("Python", "é", "incrível!", sep="_")
    Python_é_incrível!
    >>>
    >>> print("Python", "é", "incrível!", sep=" - ")
    Python - é - incrível!
    ```

1. **fim da linha personalizado** : sempre que se usa o `print()`, por padrão ele adiciona uma nova linha (`\n`) após exibir os valores. esse comportamento pode ser alterado usando o argumento `end` logo antes de fechar os parênteses. o valor que for passado ao `end` deverá ser uma `string`.
    ```python
    >>> print("Olá,", end=" ")
    >>> print("mundo!")
    Olá, mundo!
    >>>
    >>> nome = 'Arnold Schwarzenegger'
    >>> i = 0  # abreviação de índice
    >>> while i < len(nome):
    ...     print(nome[i], end='+-+')
    ...     i = i + 1
    ...
    A+-+r+-+n+-+o+-+l+-+d+-+ +-+S+-+c+-+h+-+w+-+a+-+r+-+z+-+e+-+n+-+e+-+g+-+g+-+e+-+r+-+
    ```
    Repare que, no exemplo acima, o `print()` dentro do loop `while` adiciona um `+-+` sempre que é executado, mesmo no último caractere do nome.

1. **combinando** : tanto o `sep` quanto o `end` podem ser usados juntos.
    ```python
    >>> linguagem = 'Python'
    >>> print(linguagem, "é", "incrível", sep="-", end="!")
    Python-é-incrível!>>> |
    ```
    No exemplo acima, é usado o `sep` para adicionar um traço entre cada argumento e é usado o `end` para adicionar o sinal de exclamação ao final da frase. Por causa desse comportamento do `end`, o prompt de entrada do Python fica na mesma linha.

### tudo para string

Qualquer objeto passado para `print()` é convertido em uma string usando a função `str()`. Isso significa que mesmo se você passar um número, uma lista, ou outro tipo de objeto, ele será exibido como uma string correspondente.

```python
>>> numeros = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> valor = 42
>>>
>>> print(valor, numeros)
42 [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> |
```

### exercícios print()

<details>
<summary>Lista de Exercícios</summary>

1. exercícios usando o argumento `sep`
    1. Crie três variáveis inteiras e exiba-as usando `print()` com `sep='-'` entre os valores.
    1. Crie uma lista de números inteiros e exiba seus elementos separados por espaços usando `print()` e `sep=' '`.
    1. Crie três variáveis de tipo `float` e exiba-as usando `print()` com `sep=' | '`.
    1. Crie uma lista de strings e exiba os elementos separados por vírgulas usando `print()` e `sep=', '`.
    1. Crie quatro variáveis booleanas e exiba-as usando `print()` com `sep=' & '`.
    1. Crie uma lista de números inteiros e use um loop `while` para exibir os elementos separados por ponto e vírgula (`;`) usando `print()` e `sep=';'`.
    1. Crie três variáveis do tipo `str` e exiba-as usando `print()` com `sep='-'` somente se a primeira variável for igual à segunda.
    1. Crie uma lista de números `float` e exiba os elementos separados por um asterisco (`*`) usando `print()` e `sep='*'`.
    1. Crie uma lista de variáveis booleanas e exiba os elementos separados por dois pontos (`:`) usando `print()` e `sep=':'`.
    1. Crie quatro variáveis do tipo `int`, `float`, `bool` e `str`, e exiba-as usando `print()` com `sep=' -> '`.
1. Exercícios usando o argumento `end`
    1. Crie três variáveis inteiras e exiba-as em uma linha usando `print()` com `end=' '`.
    1. Crie uma lista de strings e exiba cada elemento em uma linha separada, mas sem quebrar a linha ao final, usando `print()` com `end=''`.
    1. Crie duas variáveis `float` e exiba-as com `print()` usando `end='|'` entre elas.
    1. Crie uma lista de variáveis booleanas e use um loop `while` para exibir cada elemento em uma linha, seguido por uma vírgula, usando `print()` com `end=','`.
    1. Crie três variáveis de tipo `str` e exiba-as usando `print()` com `end=' END '`.
    1. Crie uma lista de números inteiros e use um loop `while` para exibir os elementos, cada um seguido de três pontos (`...`), usando `print()` com `end='...'`.
    1. Crie quatro variáveis do tipo `bool`, `int`, `str`, e `float`, e exiba-as usando `print()` com `end=' -> '`.
    1. Crie três variáveis do tipo `float` e exiba-as em uma linha usando `print()` com `end=' | '`.
    1. Crie uma lista de strings e use um loop `while` para exibir cada elemento, seguido por uma barra (`/`), usando `print()` com `end='/'`.
    1. Crie quatro variáveis do tipo `str` e exiba-as em uma linha usando `print()` com `end=' === '`.
1. Exercícios usando `sep` e `end` combinados
    1. Crie três variáveis inteiras e exiba-as em uma linha usando `print()` com `sep='-'` e `end='.'`.
    1. Crie uma lista de strings e exiba os elementos separados por vírgulas e finalizando com um ponto (`.`) usando `print()` com `sep=','` e `end='.'`.
    1. Crie três variáveis do tipo `float` e exiba-as em uma linha usando `print()` com `sep=':'` e `end=' END'`.
    1. Crie uma lista de números inteiros e exiba os elementos separados por espaço e finalizando com três pontos (`...`) usando `print()` com `sep=' '` e `end='...'`.
    1. Crie três variáveis do tipo `bool` e exiba-as em uma linha usando `print()` com `sep=' | '` e `end=' END'`.
    1. Crie uma lista de números `float` e exiba os elementos separados por asteriscos e finalizando com uma barra (`/`) usando `print()` com `sep='*'` e `end='/'`.
    1. Crie quatro variáveis do tipo `str`, `int`, `float`, e `bool`, e exiba-as em uma linha usando `print()` com `sep=' -> '` e `end=' END'`.
    1. Crie uma lista de strings e exiba os elementos separados por vírgulas e finalizando com uma linha em branco usando `print()` com `sep=','` e `end='\n'`.
    1. Crie três variáveis do tipo `str` e exiba-as em uma linha usando `print()` com `sep='-'` e `end=' !'`.
    1. Crie uma lista de números inteiros e exiba os elementos separados por ponto e finalizando com uma mensagem personalizada usando `print()` com `sep='.'` e `end=' - Fim da lista'`.

</details>

## `len()`

A função `len()` retorna o comprimento (número de itens) de um objeto, como uma string, lista, tupla, conjunto.

```python
planetas = ["Mercúrio", "Vênus", "Terra", "Marte"]
sobrenome = 'Schwarzenegger'

print(len(planetas))  # saída : 4
print(len(planetas[2]))  # saída (tamanho da palavra Terra) : 5
print(len(sobrenome))  # saída : 14
```

## `sum()`

A função `sum()` soma todos os elementos de um iterável, como uma lista ou tupla. Opcionalmente, pode-se passar um valor inicial para a soma.

```python
numeros = [10, 20, 30]
print(sum(numeros))        # saída : 60
print(sum(numeros, 10))    # saída : 70 (60 + 10)
```

## `pow()`

A função `pow()` retorna o valor de um número elevado a uma determinada potência. Ela aceita dois ou três argumentos. Se três argumentos forem fornecidos, a função calcula a potência e, em seguida, faz o módulo da resposta -> (x^y) % z.

```python
print(pow(2, 3))        # saída : 8 (2^3)
print(pow(2, 3, 5))     # saída : 3 (2^3 % 5)
```

## `max()` e `min()`

As funções `max()` e `min()` retornam, respectivamente, o maior e o menor valor em um iterável.

```python
numeros = [20, 10, 30, 40]
print(max(numeros))  # saída : 40
print(min(numeros))  # saída : 10
```

## `abs()`

A função `abs()` retorna o valor absoluto de um número, ou seja, seu valor sem o sinal.

```python
print(abs(-10))  # saída : 10
print(abs(4.5))  # saída : 4.5
```

## `round()`

A função `round()` arredonda um número para o número especificado de dígitos.

```python
print(round(3.14159, 2))  # saída : 3.14
print(round(2.71828))     # saída : 3
```

## `type()`

A função `type()` retorna o tipo do objeto passado como argumento.

```python
print(type(10))          # saída : <class 'int'>
print(type(3.14))        # saída : <class 'float'>
print(type(False))       # saída : <class 'bool'>
print(type("Python"))    # saída : <class 'str'>
print(type([1, 2, 3]))   # saída : <class 'list'>
```

## `isinstance()`

A função `isinstance()` verifica se um objeto é uma instância de uma classe ou de uma tupla de classes.

```python
print(isinstance(10, int))             # saída : True
print(isinstance("Python", str))       # saída : True
print(isinstance("Python", float))     # saída : False
print(isinstance(3.14, (int, float)))  # saída : True
```

## `ord()` e `chr()`

A função `ord()` retorna o número inteiro representando o código Unicode de um dado caractere. Já a função `chr()` faz o inverso, convertendo um número inteiro para o caractere correspondente ao seu código Unicode.

```python
print(ord('A'))  # saída : 65
print(chr(65))   # saída : 'A'
```

## `help()`

A função `help()` exibe a documentação de uma função, módulo, ou classe.

```python
help(print)
```

## exercícios

<details>
<summary>Lista de Exercícios</summary>

1. Nível Simples
    1. Crie uma lista de números inteiros e use a função `len()` para encontrar quantos elementos há na lista.
    1. Crie uma string e use a função `len()` para contar o número de caracteres na string.
    1. Crie uma lista de números inteiros e use a função `sum()` para calcular a soma de todos os elementos da lista.
    1. Crie uma lista de números inteiros, use a função `max()` para encontrar o maior número na lista e `min()` para encontrar o menor.
    1. Use a função `pow()` para calcular o valor de 2 elevado à 3ª potência.
    1. Crie uma variável com um número negativo e use a função `abs()` para encontrar o valor absoluto desse número.
    1. Use a função `round()` para arredondar o número 7.654 para duas casas decimais.
    1. Crie uma variável com um valor inteiro e use a função `type()` para verificar seu tipo.
    1. Crie uma variável com um valor float e use a função `isinstance()` para verificar se ela é do tipo `float`.
    1. Use a função `ord()` para encontrar o valor numérico da letra 'A'.
1. Nível Intermediário
    1. Crie uma string com várias palavras e use a função `len()` para contar o número de caracteres, incluindo os espaços.
    1. Crie uma lista de números decimais e use a função `sum()` para calcular a soma de todos os elementos da lista.
    1. Use a função `max()` e `min()` para encontrar o maior e o menor número entre 3, 9 e 4.
    1. Use a função `pow()` para calcular o valor de 5 elevado à 4ª potência.
    1. Crie uma lista com números positivos e negativos e use a função `abs()` para criar uma nova lista com os valores absolutos.
    1. Use a função `round()` para arredondar o número 3.14159 para três casas decimais.
    1. Crie uma lista de diferentes tipos de dados (int, str, bool) e use a função `type()` para verificar o tipo de cada elemento.
    1. Use a função `isinstance()` para verificar se o número 10.5 é um `int`.
    1. Use a função `chr()` para encontrar o caractere correspondente ao número 97.
    1. Use a função `help()` para exibir a documentação da função `len()`.
1. Nível Avançado
    1. Crie uma lista de listas (matriz) e use a função `len()` para encontrar o número de linhas e o número de colunas.
    1. Crie uma lista de listas (matriz) e use a função `sum()` para calcular a soma de todos os elementos da matriz.
    1. Use a função `max()` para encontrar o maior número em uma lista de listas (matriz).
    1. Use a função `pow()` para calcular o valor de 2 elevado à 10ª potência e, em seguida, divida por 3.3 e arredonde o resultado para a casa decimal mais próxima.
    1. Crie um algoritmo que peça um número e mostre seu valor absoluto usando a função `abs()`.
    1. Use a função `round()` para arredondar uma lista de números decimais para o inteiro mais próximo.
    1. Crie uma lista com diferentes tipos de dados (int, str, bool, list) e use a função `type()` para verificar o tipo de cada elemento.
    1. Crie um algoritmo que verifique se um número é inteiro usando a função `isinstance()`.
    1. Crie um algoritmo que converta uma lista de caracteres em seus valores numéricos usando `ord()`.
    1. Crie um algoritmo que converta uma lista de números em seus caracteres correspondentes usando `chr()`.
1. Nível Complexo
    1. Crie um algoritmo que peça uma lista de strings ao usuário e mostre uma lista com o comprimento de cada string digitada usando a função `len()`.
    1. Crie um algoritmo que peça duas listas de inteiros distintas e mostre a soma dos elementos de cada lista usando a função `sum()`.
    1. Crie um algoritmo que peça três (matriz) e retorne o maior número de cada lista usando a função `max()`.
    1. Crie um algoritmo que peça duas listas de números de mesmo tamanho e mostre uma lista com os resultados da exponenciação entre os elementos correspondentes usando a função `pow()`.
    1. Crie um algoritmo que peça uma lista de números e mostre uma lista com os valores absolutos de cada número usando a função `abs()`.
    1. Crie um algoritmo que peça uma lista de números decimais e mostre uma lista com os números arredondados para uma casa decimal usando a função `round()`.
    1. Crie um algoritmo que peça uma lista de diferentes tipos de dados e mostre uma lista com o tipo de cada elemento usando a função `type()`.
    1. Crie um algoritmo que peça uma lista de valores e mostre uma lista de booleanos indicando se cada valor é um inteiro usando a função `isinstance()`.
    1. Crie um algoritmo que peça uma string e mostre uma lista com os valores numéricos de cada caractere da string usando a função `ord()`.
    1. Crie um algoritmo que peça uma lista de números e retorne uma string formada pelos caracteres correspondentes a esses números usando a função `chr()`.
1. Nível Muito Complexo
    1. Crie um algoritmo que peça uma string e mostre a média dos valores numéricos de seus caracteres usando as funções `ord()` e `sum()`.
    1. Crie um algoritmo que peça duas strings e mostre a soma dos valores numéricos de seus caracteres correspondentes usando as funções `ord()` e `sum()`.
    1. Crie um algoritmo que peça uma lista de números e retorne o valor máximo absoluto dos números usando as funções `abs()` e `max()`.
    1. Crie um algoritmo que peça uma string e mostre o caractere que representa o valor numérico mais próximo da média dos valores dos caracteres da string usando as funções `ord()`, `sum()`, `len()` e `chr()`.
    1. Crie um algoritmo que peça uma lista de números decimais e mostre uma lista com os números arredondados para o inteiro mais próximo usando as funções `round()` e `type()` para garantir que os elementos sejam do tipo `float`.
    1. Crie um algoritmo que peça uma lista de números e mostre a soma dos números que são inteiros usando as funções `isinstance()` e `sum()`.
    1. Crie um algoritmo que peça uma lista de strings e mostre uma lista de listas, onde cada lista interna conterá cada string e o seu tamanho usando as funções `len()`.

</details>

## `input()`
A função `input()` lê uma entrada do usuário e a retorna como uma string.

```python
nome = input("Digite seu nome: ")
print("Olá, " + nome + "!")
```

```
Digite seu nome: Schwarzenegger
Olá, Schwarzenegger!
```

## `range()`

A função `range()` é usada para gerar uma sequência de números. Ela é frequentemente utilizada em loops `for` para iterar um número específico de vezes. O `range()` pode ser utilizado de três maneiras diferentes, dependendo de quantos argumentos você fornecer.

```python
# sintaxe básica
range(stop)
range(start, stop[, step])
```

- **`start`** (opcional): O número inicial da sequência. O valor padrão é `0`;
- **`stop`**: O número onde a sequência termina (não incluído);
- **`step`** (opcional): A diferença entre cada número na sequência. O valor padrão é `1`;

Veja alguns exemplos de uso

1. gerando uma sequência simples de 0 a n-1 :
    ```python
    >>> for i in range(5):
    ...     print(i)
    ...
    0
    1
    2
    3
    4
    >>> |
    ```

1. especificando o valor inicial (`start`) e final (`stop`) :
    ```python
    >>> for i in range(2,7):
    ...     print(i)
    ...
    2
    3
    4
    5
    6
    >>>
    ```

1. usando um `step` crescente (incremento) :
    ```python
    >>> for i in range(1, 10, 2):
    ...     print(i)
    ...
    1
    3
    5
    7
    9
    >>>
    ```

1. usando um `step` decrescente (step negativo) :
    ```python
    >>> for i in range(10, 0, -2):
    ...     print(i)
    ...
    10
    8
    6
    4
    2
    >>>
    ```

1. embora `range()` crie um objeto de intervalo (e não uma lista), é possível convertê-lo em uma lista usando a função `list()` :
    ```python
    >>> lista = list(range(10))
    >>> lista
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    >>> |
    ```
    É muito útil para gerar sequências de números de forma instantânea.

1. se precisar acessar os índices de uma lista em vez de seus valores diretamente, é possível combinar `range()` com `len()` :
    ```python
    >>> frutas = ['maçã', 'banana', 'laranja']
    >>> for i in range(len(frutas)):
    ...     print(f'índice {i} tem a fruta {frutas[i]}')
    ...
    índice 0 tem a fruta maçã
    índice 1 tem a fruta banana
    índice 2 tem a fruta laranja
    >>>
    ```

1. veja mais alguns usos do `range()` :
   ```python
    >>> # criando uma sequência de números pares
    >>> pares = list(range(0, 21, 0))
    >>> pares
    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
    >>>
    >>> # criando uma sequência de números ímpares
    >>> impares = list(range(1, 22, 2))
    >>> impares
    [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21]
    >>>
    >>> # criando uma sequência decrescente
    >>> descrescente = list(range(10, 0, -1))
    >>> descrescente
    [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
    >>>
    >>> # combinando for, range e condicionais
    >>> for i in range(1, 10):
    ...     if i % 2 == 0:
    ...         print(f'{i} é par')
    ...     else:
    ...          print(f'{i} é ímpar')
    ...
    1 é ímpar
    2 é par
    3 é ímpar
    4 é par
    5 é ímpar
    6 é par
    7 é ímpar
    8 é par
    9 é ímpar
    >>> |
    ```

### exercícios range

<details>
<summary>Lista de Exercícios</summary>

1. Use `range()` para imprimir os números de 0 a 10.
1. Use `range()` para imprimir os números de 5 a 15.
1. Use `range()` para imprimir os números pares de 0 a 20.
1. Use `range()` para imprimir os números ímpares de 1 a 19.
1. Use `range()` para imprimir os números de 10 a 0 em ordem decrescente.
1. Use `range()` para criar uma lista de números de 0 a 9 e imprimi-la.
1. Use `range()` para somar todos os números de 1 a 100.
1. Use `range()` para imprimir todos os múltiplos de 3 entre 0 e 30.
1. Use `range()` para criar uma lista de números de 5 a 15 e imprimi-la.
1. Use `range()` para imprimir os números de 0 a 10, com passos de 2.
1. Use `range()` para criar uma lista com os números de 50 a 100, com passos de 5, e imprimi-la.
1. Use `range()` para imprimir os números de 100 a 50 em ordem decrescente.
1. Use `range()` para calcular o produto de todos os números de 1 a 10.
1. Use `range()` para criar uma lista de números de 1 a 9 e imprimi-la.
1. Use `range()` para imprimir os números negativos de -10 a -1.
1. Use `range()` para criar uma lista de números de 0 a 100 com passos de 10 e imprimi-la.
1. Use `range()` para imprimir os números de 5 a 25, com passos de 5.
1. Use `range()` para somar todos os números ímpares entre 0 e 100.
1. Use `range()` para imprimir os números de 10 a 1 em ordem decrescente.
1. Use `range()` para criar uma lista de números de 20 a 30 e imprimi-la.
1. Use `range()` para imprimir os números de 2 a 20, com passos de 2.
1. Use `range()` para calcular a soma dos números múltiplos de 5 entre 0 e 50.
1. Use `range()` para criar uma lista de números de 10 a 100, com passos de 10, e imprimi-la.
1. Use `range()` para imprimir os números de -5 a 5.
1. Use `range()` para criar uma lista com os números de 0 a 9 em ordem reversa e imprimi-la.

</details>

## `enumerate()`

A função `enumerate()` em Python é usada para iterar sobre uma sequência (como uma lista, tupla ou string) e retornar tanto o índice quanto o valor dos elementos dessa sequência. Isso é particularmente útil quando é preciso de acesso ao índice do elemento dentro de um loop, sem precisar gerenciá-lo manualmente.

```python
# sintaxe básica
enumerate(iterável, start=0)
```

- **`iterável`** : a sequência sobre a qual você deseja iterar (como uma lista, tupla, string, etc.);
- **`start`** (opcional) : o valor inicial do índice (o valor padrão é 0);

Quando usado dentro de um loop `for`, `enumerate()` retorna uma tupla que contém o índice e o valor do elemento na sequência. Esse índice começa no valor especificado pelo parâmetro `start`.

Veja alguns exemplos

1. iterando sobre uma lista com `enumerate()` :
    ```python
    >>> frutas = ['maçã', 'banana', 'laranja']
    >>> for i, fruta in enumerate(frutas):
    ...     print(f'Índice {i}: {fruta}')
    ...
    Índice 0: maçã
    Índice 1: banana
    Índice 2: laranja
    >>> |
    ```

1. especificando um valor inicial para o índice :
    ```python
    >>> frutas = ['maçã', 'banana', 'laranja']
    >>> for i, fruta in enumerate(frutas, start=1):
    ...     print(f'Índice {i}: {fruta}')
    ...
    Índice 1: maçã
    Índice 2: banana
    Índice 4: laranja
    >>> |
    ```

1. acessando índices ao iterar sobre strings :
    ```python
    >>> palavra = 'Python'
    >>> for i, letra in enumerate(palavra):
    ...     print(f'Letra {letra} está na posição {i}')
    ...
    Letra P está na posição 0
    Letra y está na posição 1
    Letra t está na posição 2
    Letra h está na posição 3
    Letra o está na posição 4
    Letra n está na posição 5
    >>> |
    ```

1. identificando posições de elementos específicos em uma lista :
    ```python
    >>> numeros = list(range(10, 60, 10))
    >>> numeros
    [10, 20, 30, 40, 50]
    >>> for i, num in enumerate(numeros):
    ...     if num == 30:
    ...         print(f'Encontrado {num} na posição {i}')
    ...
    Encontrado 30 na posição 2
    >>> |
    ```

1. se precisar modificar os elementos de uma lista com base em sua posição, `enumerate()` pode ser útil:
    ```python
    >>> numeros = list(range(10, 60, 10))
    >>> numeros
    [10, 20, 30, 40, 50]
    >>>
    >>> for i, num in enumerate(numeros):
    ...     numeros[i] = num * 2
    ...
    >>> numeros
    [20, 40, 60, 80, 100]
    >>> |
    ```

### exercícios enumerate

<details>
<summary>Lista de Exercícios</summary>

1. Use `enumerate()` para imprimir cada elemento de uma lista de frutas, junto com seu índice.
1. Use `enumerate()` para imprimir cada letra de uma string, junto com seu índice.
1. Crie uma lista de números e use `enumerate()` para imprimir cada número junto com seu índice.
1. Use `enumerate()` para iterar sobre uma lista de palavras e imprimir o índice das palavras que contêm a letra "a".
1. Crie uma lista de nomes e use `enumerate()` para imprimir cada nome com seu respectivo índice.
1. Use `enumerate()` para criar uma nova lista de lista, onde cada nova lista contém um índice e um valor de uma lista de números.
1. Use `enumerate()` para imprimir os índices e elementos de uma lista de números pares.
1. Use `enumerate()` para iterar sobre uma string e imprimir o índice das letras maiúsculas.
1. Crie uma lista de cidades e use `enumerate()` para imprimir cada cidade com seu respectivo índice.
1. Use `enumerate()` para contar quantos elementos em uma lista de números são maiores que 10.
1. Use `enumerate()` para imprimir os índices e letras de uma string que começam com "p".
1. Crie uma lista de palavras e use `enumerate()` para imprimir o índice das palavras que têm mais de 5 letras.
1. Use `enumerate()` para somar os índices de todos os elementos de uma lista de números.
1. Use `enumerate()` para criar uma nova lista com as letras de uma string, onde o índice é par.
1. Use `enumerate()` para imprimir o índice e o valor de cada elemento em uma lista de números negativos.
1. Use `enumerate()` para criar uma nova lista de strings, onde cada string contém o índice e o valor correspondente.
1. Use `enumerate()` para imprimir os índices dos elementos em uma lista de números que são múltiplos de 3.
1. Use `enumerate()` para iterar sobre uma lista de palavras e imprimir o índice das palavras que começam com "s".
1. Use `enumerate()` para contar quantos elementos em uma lista de números são negativos.
1. Use `enumerate()` para criar uma nova lista onde cada elemento é o dobro do índice original de uma lista de números.
1. Use `enumerate()` para imprimir os índices das letras em uma string que são vogais.
1. Use `enumerate()` para criar uma nova lista de listas, onde cada nova lista contém um índice e uma palavra de uma lista original.
1. Use `enumerate()` para imprimir o índice e o valor dos elementos em uma lista de strings que contêm a letra "e".
1. Use `enumerate()` para iterar sobre uma lista de números e imprimir o índice dos números que são pares.
1. Use `enumerate()` para criar uma nova lista de strings, onde cada string contém o índice e o valor correspondente de uma lista de nomes.

</details>

## `zip()`

A função `zip()` em Python é usada para combinar dois ou mais iteráveis (como listas, tuplas, ou qualquer objeto que suporte iteração) em um único iterável de pares ou tuplas. Cada tupla gerada pelo `zip()` conterá os elementos correspondentes dos iteráveis fornecidos.

```python
# sintaxe básica
zip(iterável1, iterável2, ...)
```

- **`iterável1, iterável2, ...`** : um ou mais iteráveis (listas, tuplas, strings, etc.) que deseja combinar;

A função `zip()` retorna um iterador de tuplas, onde cada tupla contém um elemento de cada iterável. Se os iteráveis tiverem comprimentos diferentes, o `zip()` truncará ao comprimento do menor iterável.

Veja exemplos de uso

1. zip de duas listas :
    ```python
    >>> nomes = ['Ana', 'João', 'Maria']
    >>> idades = [25, 30, 22]
    >>>
    >>> combinados = zip(nomes, idades)
    >>> list(combinados)
    [('Ana', 25), ('João', 30), ('Maria', 22)]
    >>> |
    ```

1. zip de três listas :
    ```python
    >>> nomes = ['Ana', 'João', 'Maria']
    >>> idades = [25, 30, 22]
    >>> cidades = ['São Paulo', 'Rio de Janeiro', 'Curitiba']
    >>>
    >>> combinados = zip(nomes, idades, cidades)
    >>> list(combinados)
    [('Ana', 25, 'São Paulo'), ('João', 30, 'Rio de Janeiro'), ('Maria', 22, 'Curitiba')]
    >>> |
    ```

1. iterando com `zip()` em um loop `for` :
    ```python
    >>> nomes = ['Ana', 'João', 'Maria']
    >>> idades = [25, 30, 22]

    >>> for nome, idade in zip(nomes, idades):
    >>>     print(f'{nome} tem {idade} anos.')
    Ana tem 25 anos.
    João tem 30 anos.
    Maria tem 22 anos.
    >>> |
    ```

1. quando os iteráveis passados para `zip()` têm tamanhos diferentes, o `zip()` para de emparelhar assim que o menor iterável é consumido :
    ```python
    >>> nomes = ['Ana', 'João']
    >>> idades = [25, 30, 22]  # Uma lista mais longa
    >>>
    >>> combinados = zip(nomes, idades)
    >>> list(combinados)
    [('Ana', 25), ('João', 30)]
    >>> |
    ```
    No exemplo acima, o terceiro valor de `idades` (22) é ignorado porque `nomes` só tem dois elementos.

1. zip com strings :
    ```python
    >>> letras = 'abc'
    >>> numeros = [1, 2, 3]
    >>>
    >>> combinados = zip(letras, numeros)
    >>> list(combinados)
    [('a', 1), ('b', 2), ('c', 3)]
    >>> |
    ```

### exercícios zip

<details>
<summary>Lista de Exercícios</summary>

1. Use `zip()` para combinar duas listas de números e imprimir os pares resultantes.
1. Use `zip()` para combinar duas listas de palavras e imprimir os pares resultantes.
1. Use `zip()` para combinar uma lista de números com uma lista de palavras e imprimir os pares.
1. Crie duas listas de nomes e sobrenomes e use `zip()` para combiná-las em uma lista de nomes completos.
1. Use `zip()` para combinar uma string e uma lista de números, imprimindo os pares resultantes.
1. Crie duas listas de números e use `zip()` para somá-los em pares.
1. Use `zip()` para combinar uma lista de palavras com seus respectivos comprimentos.
1. Use `zip()` para iterar sobre duas listas de números e imprimir a multiplicação dos pares.
1. Crie duas listas de cidades e estados e use `zip()` para combiná-las em uma lista de listas.
1. Use `zip()` para combinar uma string e uma lista de índices, imprimindo os pares.
1. Crie duas listas de produtos e preços e use `zip()` para imprimir os produtos com seus preços.
1. Use `zip()` para combinar três listas de números e imprimir as listas resultantes.
1. Use `zip()` para combinar duas strings e imprimir os pares de caracteres.
1. Crie duas listas de números e use `zip()` para criar uma nova lista de listas e imprimir seus pares.
1. Crie duas listas de palavras e use `zip()` para criar uma nova lista onde cada elemento é a concatenação das palavras nas duas listas.
1. Use `zip()` para combinar uma lista de números com uma lista de booleanos e imprimir os pares.
1. Crie duas listas de notas e use `zip()` para calcular a média de cada par de notas.
1. Use `zip()` para combinar três listas de palavras e imprimir as listas resultantes.
1. Crie duas listas de letras e use `zip()` para criar uma string onde as letras das duas listas estejam intercaladas.
1. Use `zip()` para combinar uma lista de nomes com uma lista de idades e imprimir as listas resultantes.
1. Crie duas listas de números e use `zip()` para subtrair os pares e imprimir os resultados.
1. Use `zip()` para combinar uma lista de cidades com uma lista de países e imprimir os pares.
1. Crie duas listas de números e use `zip()` para encontrar o maior número em cada par.
1. Use `zip()` para combinar uma lista de palavras com uma lista de números e imprimir as palavras repetidas de acordo com os números.
1. Crie três listas de strings e use `zip()` para combinar e imprimir as listas formadas pelos elementos correspondentes.

</details>

## `dir()`

A função `dir()` em Python é uma ferramenta útil para inspecionar os atributos e métodos de um objeto. Quando se usa `dir()` com um objeto específico, ela retorna uma lista de nomes de atributos e métodos disponíveis para esse objeto. Se chamar `dir()` sem argumentos, ela retorna uma lista dos nomes no escopo atual.

Veja alguns exemplos abaixo :

### usando `dir()` com um objeto específico

Quando se passa um objeto para `dir()`, ela lista todos os atributos e métodos que o objeto possui. Por exemplo:

```python
# Exemplo com uma string
s = "hello"
print(dir(s))
```

Saída:
```
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'istitle', 'isupper', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'swapcase', 'title', 'upper', 'zfill']
```

Essa lista inclui métodos especiais (aqueles com duplo sublinhado, como `__add__` e `__str__`) e métodos normais (como `capitalize` e `split`).

### usando `dir()` sem argumentos

Quando `dir()` é chamada sem argumentos, ela retorna uma lista de nomes no escopo atual. Isso inclui nomes de variáveis, funções e outros objetos definidos no escopo:

```python
# Definindo algumas variáveis e funções
x = 10

def greet(name):
    return f"Hello, {name}"

# Usando dir() sem argumentos
print(dir())
```

Saída (depende do que está definido no escopo):
```
['__builtins__', '__doc__', '__import__', 'greet', 'x']
```

### usando `dir()` com módulos

Também pode-se usar `dir()` para ver quais atributos e funções estão disponíveis em um módulo:

```python
import math
print(dir(math))
```

Saída:
```
['__builtins__', '__doc__', '__getattr__', '__getattribute__', '__hash__', '__loader__', '__name__', '__package__', '__spec__', '__store__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'comb', 'copysign', 'cos', 'cosh', 'dist', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'isclose', 'isfinite', 'isinf', 'isnan', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nextafter', 'pi', 'pow', 'prod', 'radians', 'remainder', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc']
```

A lista inclui funções matemáticas como `sqrt`, `sin`, e constantes como `pi`.

## exercícios `dir()`

<details>
<summary>Lista de Exercícios</summary>

1. **Listando Atributos de uma String** : Crie uma string `s = "Python"` e use `dir(s)` para listar todos os atributos e métodos disponíveis para a string.
1. **Explorando Listas** : Defina uma lista `my_list = [1, 2, 3, 4]` e use `dir(my_list)` para ver quais métodos e atributos estão disponíveis para listas.
1. **Funções no Escopo Atual** : Defina uma função `def example_func(): pass` e depois use `dir()` para listar os nomes no escopo atual. O que aparece na lista?
1. **Atributos de um Dicionário** : Crie um dicionário `my_dict = {'key': 'value'}` e use `dir(my_dict)` para listar os métodos e atributos disponíveis para dicionários.
1. **Módulo `math`** : Importe o módulo `math` e use `dir(math)` para listar todas as funções e constantes disponíveis nesse módulo.
1. **Explorando um Objeto de Classe** : Crie uma classe simples `class MyClass: pass` e crie uma instância `obj = MyClass()`. Use `dir(obj)` para listar os atributos e métodos da instância.
1. **Métodos de um Conjunto** : Defina um conjunto `my_set = {1, 2, 3}` e use `dir(my_set)` para listar os métodos e atributos disponíveis para conjuntos.
1. **Atributos de um Inteiro** : Crie uma variável `x = 5` e use `dir(x)` para ver quais métodos e atributos estão disponíveis para números inteiros.
1. **Objetos de Função** : Defina uma função `def sample(): return "test"` e use `dir(sample)` para listar os atributos e métodos da função.
1. **Checando Atributos de um Módulo Personalizado** : Crie um módulo personalizado com uma função e uma variável global e depois use `dir()` para listar o que está disponível no módulo.
1. **Explorando o Módulo `time`** : Importe o módulo `time` e use `dir(time)` para listar todos os atributos e métodos disponíveis.
1. **Checando o Escopo Local** : Defina várias variáveis e funções em um escopo local e use `dir()` dentro de uma função para listar os nomes definidos no escopo local.
1. **Atributos de um Objeto `None`** : Use `dir(None)` para ver quais métodos e atributos estão disponíveis para o objeto `None`.
1. **Métodos de uma Tupla** : Defina uma tupla `my_tuple = (1, 2, 3)` e use `dir(my_tuple)` para listar os métodos e atributos disponíveis para tuplas.
1. **Inspecionando o Objeto `__builtins__`** : Use `dir(__builtins__)` para listar todos os nomes disponíveis no módulo `builtins`, que contém funções e exceções integradas do Python.

</details>
