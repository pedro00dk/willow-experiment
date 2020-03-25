# Biscoitos de Jessie

-   assunto: Heap
-   categoria: Implementar funcionalidade
-   dificuldade: médio

## Problema

Jessie adora biscoitos.
Ele quer que a doçura de seus biscoitos seja maior que um valor `K`.
Para conseguir isso, Jesse repetidamente mistura seus dois biscoitos menos doces e cria um biscoito combinado.
O novo biscoito tem a doçura de `1 * (doçura do biscoito menos doce) + 2 * (doçura do 2º biscoito menos doce)`.

Ele repete esse procedimento até que todos os biscoitos restantes tenham doçura maior ou igual a `K`.

## Tarefa

Você deve completar a função `combinations(cookies, k)` que recebe uma lista com a doçura dos biscoitos e a doçura esperada.
Calcule a quantidade de misturas de biscoitos requeridos para que todos os biscoitos tenham a doçura desejada por Jessie.
Se a doçura não pode ser atingida, retorne `-1`.

## Entrada

A primeira linha da entrada é uma lista de números que representa a doçura de cada biscoito.
A segunda linha contem o valor `K`, a doçura requerida.

## Código

```python
# complete a função combinations(cookies, k) abaixo
def combinations(cookies, k):
    # possivel solução
    def heapify(i):
        left, right = i * 2 + 1, i * 2 + 2
        smaller = left if len(cookies) and cookies[i] < cookies[left] else
            right if right < len(cookies) and cookies[i] < cookies[right] else
            i
        if smaller != i:
            cookies[i], cookies[smaller] = coolies[smaller], cookies[i]
            heapify(smaller)

   # TODO 

    for i in range(len(cookies) // 2, 0): heapify(i)

    count = len(cookie)
    while count > 1 and cookies[0] < k:

    #
    pass


if __name__ == '__main__':
    cookies = [int(i) for i in input().split()]
    k = int(input())
    print(combinations(cookies, k))
```

## Exemplos

```
# 1
## Input
0 2 3 4 5 8 9

## Expected Output
9 8 5 4 3 2 0


# 2
## Input
10

## Output
10


# 3
## Input <empty>


## Output
None
```
