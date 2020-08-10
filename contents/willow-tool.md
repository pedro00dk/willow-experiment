# Willow

<!--english-->

In the following sections, two problems will be presented.
You must use Willow to help visualizing and solving the problems.

<!--english-->

<!--portuguese-->

Nas proximas sessões, dois problemas serão apresentados.
Você deve usar o ambiente Willow para resolver esses problemas.

<!--portuguese-->

## Tutorial

<!--english-->

You **must follow this tutorial slowly and paying close attention to the text** before advancing to the next problems.
The estimated time to finish this tutorial ranges from **6 to 10 minutes**.

Before proceeding to the problems, you must access Willow and follow the steps below.
The steps will provide basic training on how to use Willow.
Read the instructions, look at the images and clips, and then, do the same.

First click on the link below to access the Willow website.

<!--english-->

<!--portuguese-->

Você **deve seguir esse tutorial pausadamente e prestando bastante atenção ao texto** antes de avançar para os próximos problemas.
O tempo extimado para completar esse tutorial varia de **6 a 10 minutos**

Antes de avançar para os problemas, você deve acessar Willow e seguir os passos abaixo.
Os passos proverão um treinamento básico de como usar Willow.
Leia as instruções, veja as images e clips, e então, faça o mesmo.

Primeiro clique no link abaixo para acessar o site do Willow.

<!--portuguese-->

https://willow-beta.web.app/

<!--english-->

After accessing the site, you must log-in with a google account through the button in the right upper corner.
The log-in will allow you to run longer programs.

<!--english-->

<!--portuguese-->

Ao acessar o site, você deve logar com uma conta google através do botão no canto superior direito.
O login permitirá que você execute programas mais longos.

<!--portuguese-->

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step0-signin.png?raw=true)

## Step 1

<!--english-->

Select the **Python** language in the toolbar, and then paste the code below into `Editor`.
This code is a linked list implementation, and it will be used to show features of Willow.

<!--english-->

<!--portuguese-->

Selecione a linguagem **Python** na barra de ferramentas, e então cole o código abaixo em `Editor`.
Esse código é uma implementação de lista encadeada, e será usado para mostrar as funcionalidades de Willow.

<!--portuguese-->

```python
class Node:
    def __init__(self, v):
        self.next = None
        self.v = v
        self.prev = None

class LinkedList:
    def __init__(self):
        self.head = self.tail = None
        self.size = 0

    def append(self, v):
        new = Node(v)
        if self.size == 0:
            self.head = self.tail = new
        else:
            self.tail.next = new
            new.prev = self.tail
            self.tail = new
        self.size += 1

ll = LinkedList()
ll.append(input())
ll.append(input())
ll.append(input())
ll.append(input())
ll.append(input())
```

<!--english-->

Paste also the program inputs into `Input`, which are the values ​​that will be used to create the list nodes.

<!--english-->

<!--portuguese-->

Cole também as entradas do programa em `Input`, que são os valores que serão usados para criar os nós da lista.

<!--portuguese-->

```
0
1
2
3
4
```

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step1-screen.png?raw=true)

## Step 2

<!--english-->

To run the code, click the play button on the toolbar.
Wait a few seconds for the visualization is generated.

<!--english-->

<!--portuguese-->

Para executar o código, clique no botão play na barra de ferramentas.
Aguarde alguns segundos até que a visualização seja gerada.

<!--portuguese-->

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step2-play.png?raw=true)
![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step2-screen.png?raw=true)

## Step 3

<!--english-->

Use the **right and left arrows** to navigate to the end of the program.
**You can also click on a call tree scope to jump to this point in the program.**
Double-clicking jumps to the end of a scope instead of the beginning.

<!--english-->

<!--portuguese-->

Use as **setas para direita e esquerda** para navegar até o fim do programa.
**Você também pode clicar nos escopos do programa para pular para este ponto do programa.**
Clique duplo pula para o fim de um escopo ao invés do início.

<!--portuguese-->

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step3-scopes.gif?raw=true)

## Step 4

<!--english-->

Now, try to drag the heap objects around.

<!--english-->

<!--portuguese-->

Tente agora arrastar os objetos na heap.

<!--portuguese-->

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step4-move.gif?raw=true)

<!--english-->

You can also activate automatic layout, just double-click on any internal object in the list.
It also works with other linked data structures, such as binary trees.

<!--english-->

<!--portuguese-->

Você pode também ativar a disposição automática, basta clicar duas vezes em qualquer objeto interno da lista (nos da lista).
Isso também funciona com outras estruturas encadeadas, como árvores binárias.

<!--portuguese-->

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step4-auto.gif?raw=true)

<!--english-->

When activating automatic layout, the outline of the nodes will be slightly darkened.
If you move any node, the automatic arrangement will be disabled.

With automatic layout enabled, try to navigate through the program using the arrow keys and clicking on the scopes.

<!--english-->

<!--portuguese-->

Ao ativar disposição automática, o contorno dos nós da lista estará levemente escureçido.
Se você mover qualquer nó, a disposição automática será desativada.

Com a disposição automática ativada, tente agora navegar pelo programa usando as setas do teclado e clicando nos escopos.

<!--portuguese-->

---

<!--english-->

In each problem, a base code that already reads inputs and prints the outputs of the program will be provided.
You should only implement a function presented in the problem.
After solving the problem, you must **copy all the code** in the answer field.

## Important

**You CAN still submit your response if the time limit is exceeded.**
**There is no problem if your answers are not be completely correct.**

If you need to stop, there is a waiting session between the problems, it is not possible to stop the timer while solving a problem.

<!--english-->

<!--portuguese-->

Em cada problema, será fornecido um código base que já lê entradas e imprime as saídas do programa.
Você deverá apenas implementar uma função apresentada no problema.
Após resolver, você deve **copiar todo o código** no campo de resposta.
Você ainda poderá submeter sua resposta se ultrapassar o tempo limite.

Caso precise parar, há uma sessão de espera entre os problemas, não é possivel parar o cronômetro durante a solução do problema.

<!--portuguese-->
