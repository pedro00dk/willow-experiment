# Pilhas de cilindros

-   assunto: Pilha
-   categoria: Implementar funcionalidade
-   dificuldade: facil

## Problema

Você tem três pilhas de cilindros, todos os cilindros possuem o mesmo diametro, mas eles suas alturas podem variar.
Você precisa empacotar essas pilhas, mas para isso todas as pilhas precisam ter a mesma altura.

## Tarefa

Você deve implementar a função `maximum_common_height(stacks)` onde `stacks` é uma lista contendo três pilhas (estas pilhas são listas, mas só a operação `pop()` pode ser usada).
Encontre a maior altura das pilhas de forma que todas as pilhas tenham a exatamente a mesma altura.
Você pode mudar a altura de qualquer pilha ao remover e descartar cilindros quantas vezes quiser, até que as pilhas tenham a mesma altura.
Retorne a altura resultante das pilhas.

Nota: Uma pilha vazia ainda é uma pilha.

## Entrada

A entrada são três linhas, que representam as pilhas.
Cada linha contem uma sequência de números que são as alturas dos cilindros da base para o topo da pilha.

```
## Input
2 1 2 4 2 2 1 
1 2 2 1 2 5 2
1 3 1 3 1 3 2
```


## Código

```python
from functools import reduce

# complete a função maximum_common_height(stacks) abaixo
def maximum_common_height(stacks):
    # possivel solução
    heights = [reduce(lambda acc, cylinder: acc + cylinder, stack, 0) for stack in stacks]
    while heights[0] != heights[1] != heights[2]:
        higher = max(heights)
        stacks[hi]

    #
    pass


if __name__ == '__main__':
    stack_a = [int(i) for i in input().split()]
    stack_b = [int(i) for i in input().split()]
    stack_c = [int(i) for i in input().split()]
    print(maximum_common_height([stack_a, stack_b, stack_c]))
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
