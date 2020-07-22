# Lowest Common Ancestor

<!--english-->

In a binary search tree, the lowest common ancestor of two nodes `va` and `vb` is the common ancestor of these nodes which is the farthest from the tree root.
If `va` is a parent or ancestor of `vb` or vice-versa, then the parent is also the common ancestor.

You have to implemente thr function `lca(root, va, vb)` with takes three arguments:

-   `root`: the binary tree root node
-   `va` e `vb`: values of two tree nodes, such that `va <= vb`, of which we want to obtain the common ancestor.

The function must **return** the value of the lowest common ancestor of `va` e `vb`.

<!--english-->

<!--portuguese-->

Em uma árvore binária, o primeiro ancestral comum de dois nós `va` e `vb` é o parente em comum destes nós que é está mais longe da raiz da árvore.
Se `va` é parente ou ancestral de `vb` ou vice-versa, então o nó parente também é o ancestral comum.

Você deve completar a função `lca(root, va, vb)` que recebe três argumentos:

-   `root`: o nó raiz de uma árvore binária
-   `va` e `vb`: valores de nós na árvore, tal que `va <= vb`, dos quais se quer obter o ancestral comum

A função deve **retornar** o valor do primeiro ancestral comum de `va` e `vb`.

<!--portuguese-->

## Input

<!--english-->

The first line is a list of numbers to be inserted one at a time in a BST.
The seconds line contains the values `va` and `vb`.
`va` and `vb` are always contained in the BST.

Multiple inputs can be provided at once, ther must be an empty line between each input line.

<!--english-->

<!--portuguese-->

A primeira linha da entrada é uma lista de números que seram inseridos um a um em uma BST.
A segunda linha contem os valores `va` e `vb`.
`va` e `vb` estão sempre contidos na BST.

Múltiplas entradas podem ser aceitas de uma única vez, deve haver uma linha em branco entre cada entrada.

<!--portuguese-->

## Code

```python
# implement the function below
def lca(root, va, vb):
    # solution
    pointer = root
    while not va <= pointer.v <= vb:
        pointer = pointer.left if pointer.v > vb else pointer.right
    return pointer.v
    #


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

```java
import java.util.*;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Main {

    // implement the function below
    static int lca(BSTNode root, int va, int vb) {
        // solution
        var pointer = root;
        while (pointer.v < va || pointer.v > vb)
            pointer = pointer.v > vb ? pointer.left : pointer.right;
        return pointer.v;
        //
    }

    static class BSTNode {
        int v;
        BSTNode left;
        BSTNode right;
        BSTNode(int v) {
            this.v = v;
            left = null;
            right = null;
        }
    }

    public static void main (String[] args) throws IOException {
        var reader = new BufferedReader(new InputStreamReader(System.in));
        while(true) {
            BSTNode root = null;
            for (var v : reader.readLine().split(" ")) {
                var vint = Integer.parseInt(v);
                BSTNode parent = null;
                var node = root;
                while (node != null && vint != node.v) {
                    parent = node;
                    node = vint < node.v ? node.left : node.right;
                }
                if (node != null) continue;
                if (parent == null) root = new BSTNode(vint);
                else if (vint < parent.v) parent.left = new BSTNode(vint);
                else parent.right = new BSTNode(vint);
            }
            var vs = reader.readLine().split(" ");
            var va = Integer.parseInt(vs[0]);
            var vb = Integer.parseInt(vs[1]);
            vs = null;
            System.out.println(lca(root, va, vb));
            if (reader.readLine() == null) break;
        }
    }
}
```

## Examples

Input:

```
7 0 8 5 9
5 9

6 3 1 5 4 9 7
1 4
```

Output:

```
7
3
```
