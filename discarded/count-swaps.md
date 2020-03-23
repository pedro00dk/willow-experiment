# Conte os Swaps

-   assunto: Ordenação + Arvores
-   categoria: Implementar funcionalidade
-   dificuldade: dificil

## Problema

Insertion Sort é um algoritmo de ordenação simples, que desloca elementos um a um para a sessão do array já ordenada.
Queremos contar quantos swaps de elementos o insertion sort performa em um array.

Seja **s[i]** a quantidade de posições que o i-ésimo elmento do array tem que se mover.
A quantidade de swaps é então **s[0] + s[1] + ... + s[n - 1]**.
Por exemplo, considere o array `arr = [5, 3, 2, 1]`:

```
Array          Swaps por elemento
[5, 3, 2, 1]
[3, 5, 2, 1]   s[1] = 1
[2, 3, 5, 1]   s[1] = 2
[1, 2, 3, 5]   s[1] = 3

Total Swaps = s[1] + s[2] + s[3] = 6
```

No entanto arrays podem ser muito grandes para esperarmos o algoritmo terminar.
Há alguma outra forma que podemos usar para calcular a quantidade de swaps que o insertion sort executa ao ordenar um array?

## Tarefa

Você deve completar a função `swaps(arr)` o array cujo a quantide de swaps devem ser contadas.

Não é necessario implementar qualquer lógica para ler entrada ou imprimir a saida.
A entrada e saida do programa e procesada automáticamente.

## Código

```python

# complete a função count_swaps(arr) abaixo
def count_swaps(arr):
    swaps = 0
    # solução
    bit = []
    #
    return swaps

if __name__ == '__main__':
    arr = [int(x) for x in input().split()]
    swaps = count_swaps(arr)
    print(swaps)
```

## Examples

```
```
