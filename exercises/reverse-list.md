# Inverta a Lista

-   assunto: Lista encadeada
-   categoria: Implementar funcionalidade
-   dificuldade: fácil

## Problema

Uma lista encadeada simples permite que se navegue apenas a partir da cabeça em direção a calda da lista.
Algumas vezes é preciso navegar na direção contrária com frequência, e para que isso seja possivel, a direção da lista deve ser invertida.
Após a inversão da lista, a calda antiga se torna a cabeça nova, e a cabeça antiga se torna a calda nova.

Você deve completar a função `reverse(head)` que recebe um argumento:
- `head`: o nó cabeça de uma lista encadeada

A função deve **retornar** o nó da cabeça da lista após a sua inversão.

## Entrada

A entrada é composta de apenas uma linha, que são os números que representam a lista encadeada.
Haverá sempre ao menos um elemento na lista.

Múltiplas entradas podem ser aceitas de uma única vez, deve haver uma linha em branco entre cada entrada.

## Código

```python
# complete a função reverse(head) abaixo
def reverse(head):
    # solução
    pointer, reversed = head, None
    while pointer is not None:
        next_pointer = pointer.next
        pointer.next = reversed
        reversed = pointer
        pointer = next_pointer
    return reversed
    #
    return None # a cabeça da lista invertida

class ListNode:
    def __init__(self, v):
        self.v = v
        self.next = None


if __name__ == '__main__':
    while True:
        head, tail = None, None
        for v in (int(v) for v in input().split()):
            if not head: head = tail = ListNode(v)
            else:
                tail.next = ListNode(v  )
                tail = tail.next
        tail = None
        head = reverse(head)
        while head is not None:
            print(head.v, end=' ' if head.next is not None else '\n')
            head = head.next
        try:
            input()
        except EOFError:
            break
```

## Exemplos

Entrada:
```
4

10 20 30

0 2 3 4 5 8 9

9 8 5 4 3 2 0
```

Saída:
```
4
30 20 10
9 8 5 4 3 2 0
0 2 3 4 5 8 9
```
