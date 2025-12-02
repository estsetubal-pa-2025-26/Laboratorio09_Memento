# Programação Avançada | Lab9

:gb: [English version](README_EN.md)

## Objectivos
- Aplicação do padrão de software Memento

## 1 - Introdução

O padrão Memento permite guardar o estado atual de um objeto para que possa ser recuperado após alterações, i.e., undo.

Neste laboratório pretende-se oferecer suporte para a operação undo num carrinho de compras, de forma a que se possam adicionar produtos ao carrinho e fazer undo.

O padrão determina que existe um objeto **Originator** com um estado que será guardado através de um objeto **Memento**, gerido por um **CareTaker**. A responsabilidade do **CareTaker** é, simplesmente, guardar estados do **Originator**, de forma a que os possa recuperar.

Para promover o encapsulamento na utilização do padrão, propõe-se uma versão adaptada do padrão original **Memento** que define interfaces **Originator** e **Memento**, implementando o estado (**ShoppingCartMemento**) como classe privada interna à instância de **Originator** (ShoppingCart).

![Figura 1 - Diagrama UML do padrão Memento](images/fig01.png)

Figura 1 - Diagrama UML do padrão Memento

Nesta implementação do padrão teremos as seguintes correspondências:
- Concrete Originator -> ShoppingCart
- ConcreteMemento -> ShoppingCartMemento

# Exercícios

## 1. Exercício 1
   1. Comece por executar o programa, familiarizando-se com a GUI e com as funcionalidades disponibilizadas. Repare que o botão Undo não está a funcionar.
   2. Altere a classe **ShoppingCart** para que esta passe a implementar a interface **Originator**.
   3. Implemente a *inner class* **ShoppingCartMemento**, que implementa a interface Memento.
   4. Crie a classe **Caretaker**, com os seguintes atributos:
      - **Memento memento**
      - **Originator originator**
   5. Implemente o método Construtor.
   6. Implemente o método **void saveState()**, o qual deve obter e guardar o Memento atual.
   7. Implemente o método **void restoreState()**, que deverá reestabelecer o estado do **originator** com base no **Memento** guardado. Se não existir **Memento** guardado, deve lançar a exceção **NoMementoException**.
   
## 2. Exercício 2
   1. Adicione um atributo **Caretaker** ao **ShoppingCartManager**.
   2. Modifique os métodos **addProduct**, **reset** e **removeProduct** para que passe a guardar o estado anterior, a cada modificação do estado do carrinho de compras.
   3. Implemente o método **void undo()** que utiliza a instância **caretaker** para recuperar o estado anterior do carrinho de compras.
   4. Modifique a classe **ShoppingCartPanel** de forma a adicionar o comportamento ao botão **buttonUndo**, de forma a permitir **um undo** após inserção de um produto na lista de compras.

## 3. Exercício 3
   - Altere a classe Caretaker de forma a implementar um múltiplas operações de undo.

## 4. Exercício 4
   1. Adicione o botão **buttonReset** na classe **ShoppingCartPanel** e adicione-o ao lado do botão **Undo**.
   2. Adicione o comportamento do botão **buttonReset** de forma a fazer um reset à lista de compras.
   3. Verifique se a funcionalidade *undo* continua a funcionar como o esperado.

## 5. Exercício 5
   1. Adicione o botão **buttonRemove** na classe **ShoppingCartPanel** e adicione-o ao lado do botão **Add**.
   2. Adicione o comportamento do botão **buttonRemove** de forma a fremover o produto selecionado à lista de compras.
   3. Verifique se a funcionalidade *undo* continua a funcionar como o esperado.

(fim de enunciado)