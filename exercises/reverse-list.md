# Reverse List

<!--english-->

A singly linked list is allows the navigation only from the head towards the tail of the list.
Sometimes we need to navigate in the opposite direction frequently, and for the to be possible, the list direction must be reversed.
After the list reverse, the previos tail becomes the new head, and the previous head the new tail.

You have to complete the function `reverse(head)` which takes one argument:

-   `head`: the head node of a singly linked list

The function must **return** the new list head after the reverse operation.

<!--english-->

<!--portuguese-->

Uma lista encadeada simples permite que se navegue apenas a partir da cabeça em direção a calda da lista.
Algumas vezes é preciso navegar na direção contrária com frequência, e para que isso seja possivel, a direção da lista deve ser invertida.
Após a inversão da lista, a calda antiga se torna a cabeça nova, e a cabeça antiga se torna a calda nova.

Você deve completar a função `reverse(head)` que recebe um argumento:

-   `head`: o nó cabeça de uma lista encadeada

A função deve **retornar** o nó da cabeça da lista após a sua inversão.

<!--portuguese-->

## Input

<!--english-->

The input is composed of only one line, which contains numbers that compose the linked list.
There will be always at least one element in the list.

Multiple inputs can be provided at once, ther must be an empty line between each input line.

<!--english-->

<!--portuguese-->

A entrada é composta de apenas uma linha, que contêm números que compoẽm a lista encadeada.
Haverá sempre ao menos um elemento na lista.

Múltiplas entradas podem ser aceitas de uma única vez, deve haver uma linha em branco entre cada entrada.

<!--portuguese-->

## Code

```python
# implement the function below
def reverse(head):
    # <!--solution-->
    pointer, reversed = head, None
    while pointer is not None:
        next_pointer = pointer.next
        pointer.next = reversed
        reversed = pointer
        pointer = next_pointer
    return reversed
    # <!--solution-->
    return head

class ListNode:
    def __init__(self, v):
        self.v = v
        self.next = None


if __name__ == '__main__':
    head, tail = None, None
    for v in (int(v) for v in input().split()):
        if not head: head = tail = ListNode(v)
        else:
            tail.next = ListNode(v)
            tail = tail.next
    head = reverse(head)
    while head is not None:
        print(head.v, end=' ' if head.next is not None else '\n')
        head = head.next
```

```java
import java.util.*;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Main {

    // implement the function below
    static ListNode reverse(ListNode head) {
        // <!--solution-->
        var pointer = head;
        ListNode reversed = null;
        while (pointer != null) {
            var nextPointer = pointer.next;
            pointer.next = reversed;
            reversed = pointer;
            pointer = nextPointer;
        }
        return reversed;
        // <!--solution-->
        return head;
    }

    static class ListNode {
        int v;
        ListNode next;
        ListNode(int v) {
            this.v = v;
            next = null;
        }
    }

    public static void main (String[] args) throws IOException {
        var reader = new BufferedReader(new InputStreamReader(System.in));
        ListNode head = null, tail = null;
        for (var v : reader.readLine().split(" ")) {
            var vint = Integer.parseInt(v);
            if (head == null) head = tail = new ListNode(vint);
            else {
                tail.next = new ListNode(vint);
                tail = tail.next;
            }
        }
        head = reverse(head);
        while (head != null) {
            System.out.print(head.v + " ");
            head = head.next;
        }
    }
}
```

## Examples

Input:

```
4

10 20 30

0 2 3 4 5 8 9

9 8 5 4 3 2 0
```

Output:

```
4
30 20 10
9 8 5 4 3 2 0
0 2 3 4 5 8 9
```
