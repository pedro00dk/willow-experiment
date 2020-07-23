### Willow

Nas proximas sessões, dois problemas serão apresentados.
Você deve usar o ambiente Willow para resolver esses problemas.

#### Tutorial

Antes de avançar para os problemas, você deve acessar Willow e seguir os passos abaixo.
Os passos proverão um treinamento básico de como usar Willow.

Primeiro clique no link abaixo para acessar o site do Willow.

https://willow-beta.web.app/

Ao acessar o site, você deve logar com uma conta google através do botão no canto superior direito.
O login permitirá que você execute programas mais longos.

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step0-signin.png?raw=true)

#### Passo 1

Selecione a linguagem **Python** na barra de ferramentas, e então cole o código abaixo em `Editor`Nas proximas sessões, dois problemas serão apresentados..
Esse código é uma implementação de lista encadeada, e será usado para mostrar as funcionalidades de Willow.
```
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

Cole também as entradas do programa em `Input`, que são os valores que serão usados para criar os nós.
```
0
1
2
3
4
```

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step1-screen.png?raw=true)

#### Passo 2

Para executar o código, clique no botão play na barra de ferramentas.

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step2-play.png?raw=true)

Aguarde alguns segundos até que a visualização seja gerada.

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step2-screen.png?raw=true)

#### Passo 3

Use as setas para direita e esquerda para navegar até o fim do programa.
Você também pode clicar nos escopos do programa para pular para este ponto do programa.
Clique duplo pula para o fim de um escopo ao invés do início.

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step3-scopes.gif?raw=true)

#### Passo 4

Tente agora arrastar os objetos na heap.

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step4-move.gif?raw=true)

Você pode também ativar a disposição automática, basta clicar duas vezes em qualquer objeto interno da lista (nos da lista).

![](https://github.com/pedro00dk/willow-experiment/blob/master/images/step4-auto.gif?raw=true)

Ao ativar disposição automática, o contorno dos nós da lista estará levemente escureçido.
Se você mover qualquer nó, a disposição automática será desativada.

Com a disposição automática ativada, tente agora navegar pelo programa usando as setas do teclado e clicando nos escopos.

---

Em cada problema, será fornecido um código base que já lê entradas e imprime as saídas do programa.
Você deverá apenas implementar uma função apresentada no problema.
Após resolver, você deve **copiar todo o código** no campo de resposta.
Você ainda poderá submeter sua resposta se ultrapassar o tempo limite.

Caso precise parar, há uma sessão de espera entre os problemas, não é possivel parar o cronômetro durante a solução do problema.
