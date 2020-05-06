# Biscoitos de Jessie

-   assunto: Heap
-   categoria: Implementar funcionalidade
-   dificuldade: médio

## Problema

Jessie adora biscoitos.
Ele quer que a doçura de seus biscoitos seja maior que um valor `k`.
Para conseguir isso, Jessie repetidamente mistura seus dois biscoitos menos doces `c0` e `c1`, e cria um biscoito combinado `c`.

Dado que o biscoito `c0` é menos ou igualmente doce a `c1`, o novo biscoito tem a doçura `c = c0 + 2 * c1`.

Ele repete esse procedimento até que todos os biscoitos restantes tenham doçura maior ou igual a `k`.

Você deve completar a função `combinations(cookies, k)` que recebe dois argumentos:

-   `cookies`: uma lista contendo as doçuras dos biscoitos
-   `k`: a doçura mínima esperada

A função deve **retornar** quantas misturas de biscoitos são nescessárias para que todos os biscoitos tenham ao menos a doçura `k`.
Se a doçura não pode ser atingida, a função deve **retornar** `-1`.

## Entrada

A primeira linha da entrada é uma lista de números que representam a doçura de cada biscoito.
A segunda linha contem o valor `k`, a doçura requerida.

Múltiplas entradas podem ser aceitas de uma única vez, deve haver uma linha em branco entre cada entrada.

## Código

```python
# complete a função combinations(cookies, k) abaixo
def combinations(cookies, k):
    # solução
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
    return 0 # a quantidade de combinações de biscoitos


if __name__ == '__main__':
    while True:
        cookies = [int(i) for i in input().split()]
        k = int(input())
        print(combinations(cookies, k))
        try:
            input()
        except EOFError:
            pass
```

## Exemplos

Entrada:

```
7 1 9 8 5 9
50

7 2 5 1 3 2 6 7
70

2 2 5 3 1 1
45
```

Saída:

```
5
7
-1
```
