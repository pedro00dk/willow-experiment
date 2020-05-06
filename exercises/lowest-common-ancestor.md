# Primeiro Ancestral Comum

-   assunto: Árvore binária
-   categoria: Implementar funcionalidade
-   dificuldade: fácil

## Problema

Em uma árvore binária, o primeiro ancestral comum de dois nós `va` e `vb` é o parente em comum destes nós que é está longe da raiz da árvore.
Se `va` é parente de `vb` ou vice-versa, então o nó parente também é o ancestral comum.

Você deve completar a função `lca(root, va, vb)` que recebe três argumentos:

-   `root`: o nó raiz de uma árvore binária
-   `va` e `vb`: valores de nós na árvore, dos quais se quer obter o ancestral comum

A função deve **retornar** o valor do ancestral comum mais próximo de `va` e `vb`.

## Entrada

A primeira linha da entrada é uma lista de números que seram inseridos um a um na BST.
A segunda linha contem os valores `va` e `vb`.
`va` e `vb` sempre contidos na BST.

Múltiplas entradas podem ser aceitas de uma única vez, deve haver uma linha em branco entre cada entrada.

## Código

```python
# complete a função lca(root, va, vb) abaixo
def lca(root, va, vb):
    # solução
    va, vb = (va, vb) if va <= vb else (vb, va)
    pointer = root
    while not va <= pointer.v <= vb:
        pointer = pointer.left if pointer.v > vb else pointer.right
    return pointer.v
    #
    return 0 # o valor do primeiro ancestral comum entre va e vb


class BSTNode:
    def __init__(self, v):
        self.v = v
        self.left = None
        self.right = None


if __name__ == '__main__':
    while True:
        root = None
        for v in (int(v) for v in input().split()):
            parent, node = None, root
            while node is not None and v != node.v: node, parent = (node.left if v < node.v else node.right), node
            if node is not None: continue
            if parent is None: root = BSTNode(v)
            elif v < parent.v: parent.left = BSTNode(v)
            else: parent.right = BSTNode(v)
        va, vb = [int(v) for v in input().split()]
        print(lca(root, va, vb))
        try:
            input()
        except EOFError:
            break
```

## Exemplos

Entrada:

```
7 0 8 5 9
5 9

6 3 1 5 4 9 7
1 4
```

Saída:

```
7
3
```
