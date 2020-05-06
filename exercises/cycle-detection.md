# Detecção de Cíclo

-   assunto: Lista encadeada
-   categoria: Implementar funcionalidade
-   dificuldade: médio

## Problema

Diz-se que uma lista encadeada contém um ciclo se algum nó for visidado mais de uma vez quando se percorre a lista.

```
head
  |
  v
+---+    next     +---+    next     +---+
| 1 |---------->  | 2 |---------->  | 3 |---+
+---+             +---+             +---+   |
                    ^                       |
                    |          next         |
                    +-----------------------+
```

Você deve completar a função `has_cycle(head)` que recebe um argumento:
- `head`: o nó cabeça de uma lista encadeada

A função deve **retornar** o valor `True` se a lista contém um cíclo ou `false` caso contrário.

## Entrada

A entrada é composta de apenas uma linha, que são os números que representam a lista encadeada, caso haja um ciclo na lista, o elemento que inicia o cíclo é precedido de um `#`.
Para a ilustração acima, a entrada seria `1 # 2 3`.
Haverá sempre ao menos um elemento na lista.

Múltiplas entradas podem ser aceitas de uma única vez, deve haver uma linha em branco entre cada entrada.

## Código

```python
# complete a função has_cycle(head) abaixo
def has_cycle(head):
    # solução
    slow, fast = head, head
    while fast is not None and fast.next is not None:
        slow, fast = slow.next, fast.next.next
        if slow == fast:
            return True
    return False
    #
    return False # se a lista contém cíclos

class ListNode:
    def __init__(self, v):
        self.v = v
        self.next = None


if __name__ == '__main__':
    while True:
        head, tail, put_cycle, cycle = None, None, False, None
        for v in input().split():
            if v == '#':
                put_cycle = True
                continue
            v = int(v)
            if not head: head = tail = ListNode(v)
            else:
                tail.next = ListNode(v  )
                tail = tail.next
            if put_cycle and cycle is None:
                cycle = tail
        if cycle is not None:
            tail.next = cycle
        put_cycle, cycle, tail = False, None, None
        print(has_cycle(head))
        try:
            input()
        except EOFError:
            break
```

## Exemplos

Entrada:
```
0 0 # 0 0 0 0

0 1 2 3 4 # 5

# 0 1 2 3 4 5

0 1 2 3 4 5
```

Saída:
```
True
True
True
False
```
