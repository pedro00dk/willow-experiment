# Primeiro Ancestral Comum

-   assunto: Árvore binária
-   categoria: Implementar funcionalidade
-   dificuldade: facil

## Problema

E fornecida a raiz da árvore de busca binária `root` e dois valores `va` e `vb`.
Você deve encontrar o ancestral comum mais proximo de `va` e `vb`.

## Tarefa

Você deve completar a função `lowest_common_ancestor(root, va, vb)` que recebe três argumentos - a cabeça da lista encadeada, e os valores cujo ancestral deve ser encontrado.

Não é necessario implementar qualquer lógica para ler entrada ou imprimir a saida.
As entradas e saidas do programa são procesadas automáticamente.

## Entrada

A entrada provida é uma lista de números que seram inseridos um a um na BST.
Se números são repetidos, apenas o primeiro é adicionado.
`va` e `vb` são providos na práxima linha, `va` <= `vb`, `va` e `vb` sempre contidos na BST.

```
## Input
6 3 5 1 5 4 9 7 8
1 4

# Produced Tree
#        6
#     /     \
#    3       9
#  /   \   /
# 1     5 7
#      /   \
#     4     8
#
# va = 1, vb = 4
```

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
        if not self.root:
            self.root = Node(v)
            return
        pointer = self.root
        while True:
            if pointer.v > v:
                if not pointer.left: pointer.left = Node(v)
                pointer = pointer.left
            elif pointer.v < v:
                if not pointer.right: pointer.right = Node(v)
                pointer = pointer.right
            else: break




# complete a função lowest_common_ancestor(head) abaixo
# parametro root é do tipo Node, não BST, va <= vb
def lowest_common_ancestor(root, va, vb):
    # possivel solução
    pointer = root
    while True:
        if va < pointer.v > vb: pointer = pointer.left
        elif va > pointer.v < vb: pointer = pointer.right
        elif va <= pointer.v <= vb: return pointer.v
    #
    pass


if __name__ == '__main__':
    bst = BST()
    for v in input().split():
        bst.insert(int(v))
    va, vb = [int(v) for v in input().split()]
    print(lowest_common_ancestor(bst, va, vb))
```

## Exemplos

```
# 1
## Input
7 0 9 8 5 9
5 9

## Output
7

# 2
## Input 
6 3 5 1 5 4 9 7
1 4

## Output
3
```
