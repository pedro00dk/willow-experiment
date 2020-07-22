# Cycle Detection

<!--english-->

A linked list contains a cycle if any of its nodes is visited more than once when you go through the list.

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

You have to complete the function `has_cycle(head)` that receives one argument:

-   `head`: the head of a linked list

The function must **return** `True` if the list contains a cycle or `False` otherwise.

<!--english-->

<!--portuguese-->

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

-   `head`: o nó cabeça de uma lista encadeada

A função deve **retornar** o valor `True` se a lista contém um cíclo ou `False` caso contrário.

<!--portuguese-->

## Input

<!--english-->

The input is composed of only one line, which contains numbers that compose the linked list, if there is a cycle in the list, the element that starts the cycle is preceded by a `#`.
For the diagram above, the input is `1 # 2 3`.
There will be always at least one element in the list.

Multiple inputs can be provided at once, ther must be an empty line between each input line.

<!--english-->

<!--portuguese-->

A entrada é composta de apenas uma linha, que contêm números que compoẽm a lista encadeada, caso haja um ciclo na lista, o elemento que inicia o cíclo é precedido de um `#`.
Para o diagrama acima, a entrada é `1 # 2 3`.
Haverá sempre ao menos um elemento na lista.

Múltiplas entradas podem ser aceitas de uma única vez, deve haver uma linha em branco entre cada entrada.

<!--portuguese-->

## Code

```python
# implement the function below
def has_cycle(head):
    # solution
    slow, fast = head, head
    while fast is not None and fast.next is not None:
        slow, fast = slow.next, fast.next.next
        if slow == fast:
            return True
    return False
    #

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

```java
import java.util.*;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Main {

    // implement the function below
    static boolean hasCycle(ListNode head) {
        // solution
        var slow = head;
        var fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
        //
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
        while(true) {
            ListNode head = null, tail = null, cycle = null;
            var putCycle = false;
            for (var v : reader.readLine().split(" ")) {
                if (v.equals("#")) {
                    putCycle = true;
                    continue;
                }
                var vint = Integer.parseInt(v);
                if (head == null) head = tail = new ListNode(vint);
                else {
                    tail.next = new ListNode(vint);
                    tail = tail.next;
                }
                if (putCycle && cycle == null) cycle = tail;
            }
            if (cycle != null) tail.next = cycle;
            System.out.println(hasCycle(head));
            if (reader.readLine() == null) break;
        }
    }
}
```

## Examples

Input:

```
0 0 # 0 0 0 0

0 1 2 3 # 4 5

# 0 1 2 3 4 5

0 1 2 3 4 5
```

Output:

```
True
True
True
False
```
