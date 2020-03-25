# Inverta a Lista

-   assunto: Lista encadeada
-   categoria: Implementar funcionalidade
-   dificuldade: facil

## Problema

E fornecida a referência para a cabeça de uma lista encadeada.
Implemente uma função que inverte _in-place_ a lista recebida.
A referência inicial pode ser nula (`None`), implicando que a lista é vazia.

## Tarefa

Você deve completar a função `reverse(head)` que recebe um argumento - a cabeça da lista encadeada.

Não é necessario implementar qualquer lógica para ler entrada ou imprimir a saida.
As entradas e saidas do programa são procesadas automáticamente.

## Entrada

A entrada é uma lista de números que representa a lista encadeada. O primeiro número estará no ínicio da lista.

## Código

```python
class LinkedList:
    def __init__(self, data, next=None):
        self.data = data
        self.next = next

    def __str__(self):
        string = ''
        pointer = self
        while pointer is not None:
            string += f'{pointer.data}  '
            pointer = pointer.next
        return string


# complete a função reverse(head) abaixo
def reverse(head):
    # possivel solução
    reversed_list = None
    pointer = head
    while (pointer != None):
        next_pointer = pointer.next
        pointer.next = reversed_list
        reversed_list = pointer
        pointer = next_pointer
    return reversed_list
    #
    pass


if __name__ == '__main__':
    linked_list = None
    tail = linked_list
    try:
        for data in input().split():
            if not tail: tail = LinkedList(data)
            else:
                tail.next = LinkedList(data)
                tail = tail.next
            if not linked_list: linked_list = tail
    except: pass
    tail = None
    linked_list = reverse(linked_list)
    print(linked_list)
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
