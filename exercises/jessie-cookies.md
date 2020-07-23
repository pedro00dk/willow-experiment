# Jessie Cookies

<!--english-->

Jessie loves cookies.
He wants the sweetness of his cookies to be greater then a value `k`.
To archieve that, Jessie repeatedly mixes his two less sweet cookies `c0` and `c1`, and creates a new combined cookie `c`.

Let the cookie `c0` less or as swwet as `c1`, the new cookie will have the sweeteness `c = c0 + 2 * c1`.

He repeats the proceduer until all of his remaining cookies have the sweetness greater than or equal `k`.

You have to complete the function `combinations(cookies, k)`, which takes two arguments:

-   `cookies`: a list containing thw cookies sweetness
-   `k`: the minimum expected sweetness

The function must **return** how many cookie mixes are necessary for all cookies to have at least `k` sweetness.
If the sweetness can not be archieved, the function must **return** `-1`.

<!--english-->

<!--portuguese-->

Jessie adora biscoitos.
Ele quer que a doçura de seus biscoitos seja maior que um valor `k`.
Para conseguir isso, Jessie repetidamente mistura seus dois biscoitos menos doces `c0` e `c1`, e cria um biscoito combinado `c`.

Dado que o biscoito `c0` é menos ou igualmente doce a `c1`, o novo biscoito terá doçura `c = c0 + 2 * c1`.

Ele repete esse procedimento até que todos os biscoitos restantes tenham doçura maior ou igual a `k`.

Você deve completar a função `combinations(cookies, k)` que recebe dois argumentos:

-   `cookies`: uma lista contendo as doçuras dos biscoitos
-   `k`: a doçura mínima esperada

A função deve **retornar** quantas misturas de biscoitos são nescessárias para que todos os biscoitos tenham ao menos a doçura `k`.
Se a doçura não pode ser atingida, a função deve **retornar** `-1`.

<!--portuguese-->

## Input

<!--english-->

The first input line contains a list of numbers when represent the sweetness of each cookie.
The second line contains `k`.

<!--english-->

<!--portuguese-->

A primeira linha da entrada contém uma lista de números que representam a doçura de cada biscoito.
A segunda linha contem `k`.

<!--portuguese-->

## Code

```python
# implement the function below
def combinations(cookies, k):
    # <!--solution-->
    def heapify(i):
        l, r = i * 2 + 1, i * 2 + 2
        smaller = i
        smaller = l if l < len(cookies) and cookies[l] < cookies[smaller] else smaller
        smaller = r if r < len(cookies) and cookies[r] < cookies[smaller] else smaller
        if smaller != i:
            cookies[i], cookies[smaller] = cookies[smaller], cookies[i]
            heapify(smaller)

    for i in range(len(cookies) // 2 - 1, -1, -1):
        heapify(i)

    merges = 0
    while len(cookies) >= 2 and cookies[0] < k:
        cookie_a = cookies[0]
        cookies[0] = cookies.pop()
        heapify(0)
        cookie_b = cookies[0]
        new_cookie = cookie_a + cookie_b * 2
        cookies[0] = new_cookie
        heapify(0)
        merges += 1

    return merges if cookies[0] >= k else -1
    # <!--solution-->
    return -1


if __name__ == '__main__':
    cookies = [int(i) for i in input().split()]
    k = int(input())
    print(combinations(cookies, k))
```

```java
import java.util.*;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Main {

    // implement the function below
    static int combinations(int[] cookies, int k) {
        // <!--solution-->
        for (var i = cookies.length / 2 - 1; i >= 0; i--)
            heapify(cookies, i, cookies.length);
        var merges = 0;
        var length = cookies.length;
        while (length >= 2 && cookies[0] < k) {
            var cookieA = cookies[0];
            cookies[0] = cookies[length - 1];
            length -= 1;
            heapify(cookies, 0, length);
            var cookieB = cookies[0];
            var newCookie = cookieA + cookieB * 2;
            cookies[0] = newCookie;
            heapify(cookies, 0, length);
            merges += 1;
        }
        return merges;
        // <!--solution-->
        return -1;
    }

    // <!--solution-->
    static void heapify(int[] cookies, int i, int length) {
        var l = i * 2 + 1;
        var r = i * 2 + 2;
        var smaller = i;
        smaller = l < length && cookies[l] < cookies[smaller] ? l : smaller;
        smaller = r < length && cookies[r] < cookies[smaller] ? r : smaller;
        if (smaller != i) {
            var aux = cookies[i];
            cookies[i] = cookies[smaller];
            cookies[smaller] = aux;
            heapify(cookies, smaller, length);
        }
    }
    // <!--solution-->

    public static void main (String[] args) throws IOException {
        var reader = new BufferedReader(new InputStreamReader(System.in));
        var stringCookies = reader.readLine().split(" ");
        var cookies = new int[stringCookies.length];
        for (var i = 0; i < stringCookies.length; i++) cookies[i] = Integer.parseInt(stringCookies[i]);
        stringCookies = null;
        var k = Integer.parseInt(reader.readLine());
        System.out.println(combinations(cookies, k));
    }
}
```

## Examples

Input:

```
7 1 9 8 5 9
50

7 2 5 1 3 2 6 7
70

2 2 5 3 1 1
45
```

Output:

```
5
7
-1
```
