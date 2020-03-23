# Primeiro Ancestral Comum

-   assunto: Aŕvores Binárias
-   categoria: Implementar funcionalidade
-   dificuldade: facil

## Problema

E fornecida a raiz da árvore de busca binária `root` e dois valores `va` e `vb`.
Você deve encontrar o ancestral comum mais proximo de `va` e `vb`.

## Tarefa

Você deve completar a função `lowest_common_ancestor(root, va, vb)` que recebe três argumentos - a cabeça da lista encadeada, e os valores cujo ancestral deve ser encontrado.

Não é necessario implementar qualquer lógica para ler entrada ou imprimir a saida.
As entradas e saidas do programa são procesadas automáticamente.

## Código

```python
class Node:
    def __init__(self, v, left=None, right=None):
        self.v = v
        self.left = left
        self.right = right

class BST:
    def __init__(self):
        self.root = None

    def insert(self, v, pointer=None):
        # TODO
        


# complete a função lowest_common_ancestor(head) abaixo
def lowest_common_ancestor(root, va, vb):
    # possivel solução
    #
    pass


if __name__ == '__main__':
    bst = BST()
    for v in input().split():
        bst.insert(int(v))
    va, vb = [int(v) for v in input().split()]
    print(lowest_common_ancestor(bst, va, vb))
```

## Examples

```
```
