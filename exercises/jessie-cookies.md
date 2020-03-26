# Biscoitos de Jessie

-   assunto: Heap
-   categoria: Implementar funcionalidade
-   dificuldade: fácil (longo)

## Problema

Jessie adora biscoitos.
Ele quer que a doçura de seus biscoitos seja maior que um valor `K`.
Para conseguir isso, Jesse repetidamente mistura seus dois biscoitos menos doces e cria um biscoito combinado.
O novo biscoito tem a doçura de `1 * (doçura do biscoito menos doce) + 2 * (doçura do 2º biscoito menos doce)`.

Ele repete esse procedimento até que todos os biscoitos restantes tenham doçura maior ou igual a `K`.

## Tarefa

Você deve completar a função `combinations(cookies, k)` que recebe uma lista com a doçura dos biscoitos e a doçura mínima `K`.
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
        l, r = i * 2 + 1, i * 2 + 2
        smaller = i
        smaller = l if l < len(cookies) and cookies[l] < cookies[smaller] else smaller
        smaller = r if r < len(cookies) and cookies[r] < cookies[smaller] else smaller
        if smaller != i:
            cookies[i], cookies[smaller] = cookies[smaller], cookies[i]
            heapify(smaller)

    for i in range(len(cookies) // 2 - 1, -1, -1):
        heapify(i)

    merges = 0
    while len(cookies) >= 2 and cookies[0] < k:
        cookie_a = cookies[0]
        cookies[0] = cookies.pop()
        heapify(0)
        cookie_b = cookies[0]
        new_cookie = cookie_a + cookie_b * 2
        cookies[0] = new_cookie
        heapify(0)
        merges += 1

    return merges if cookies[0] >= k else -1
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
7 1 9 8 5 9
50

## Output
5

# 2
## Input 
7 2 5 1 3 2 6 7
70

## Output
7

# 3
## Input 
2 2 5 3 1 1
45

## Output
-1
```
