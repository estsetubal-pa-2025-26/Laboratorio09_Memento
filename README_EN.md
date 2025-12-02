# Advanced Programming | Lab9

## Objectives
- Application of the Memento software standard

## 1 - Introduction

The Memento pattern allows you to save the current state of an object so that it can be recovered after changes, i.e. undo.

In this laboratory we intend to offer support for the undo operation in a shopping cart, so that products can be added to the cart and undo.

The pattern dictates that there is an **Originator** object with a state that will be saved through a **Memento** object, managed by a **CareTaker**. **CareTaker**'s responsibility is simply to save **Originator** states so that it can recover them.

To promote encapsulation in the use of the pattern, an adapted version of the original **Memento** pattern is proposed, which defines **Originator** and **Memento** interfaces, implementing the state (**ShoppingCartMemento**) as a class internal to the **Originator** (ShoppingCart) instance.

![Figure 1 - UML diagram of the Memento pattern](images/fig01.png)

Figure 1 - UML diagram of the Memento pattern

In this implementation of the pattern we will have the following correspondences:
- Concrete Originator -> ShoppingCart
- ConcreteMemento -> ShoppingCartMemento

Here is the full text translated into UK English and formatted in Markdown:

---
#Exercicies

## 1. Exercise 1

1. Start by running the programme to familiarise yourself with the GUI and the available features. Note that the **Undo** button is not working.
2. Modify the **ShoppingCart** class so that it implements the **Originator** interface.
3. Implement the **inner class** **ShoppingCartMemento**, which must implement the **Memento** interface.
4. Create the **Caretaker** class with the following attributes:

   * **Memento memento**
   * **Originator originator**
5. Implement the constructor.
6. Implement the method **void saveState()**, which must retrieve and store the current Memento.
7. Implement the method **void restoreState()**, which must restore the state of the **originator** based on the stored **Memento**. If no **Memento** exists, the method must throw the exception **NoMementoException**.

---

## 2. Exercise 2

1. Add a **Caretaker** attribute to **ShoppingCartManager**.
2. Modify the methods **addProduct**, **reset**, and **removeProduct** so that the previous state is stored whenever the shopping cart is modified.
3. Implement the method **void undo()**, which uses the **caretaker** instance to retrieve the previous state of the shopping cart.
4. Modify the **ShoppingCartPanel** class to add behaviour to the **buttonUndo**, enabling **one undo** after inserting a product into the shopping list.

---

## 3. Exercise 3

* Modify the **Caretaker** class so that it supports multiple undo operations.

---

## 4. Exercise 4

1. Add the **buttonReset** to the **ShoppingCartPanel** class, placing it next to the **Undo** button.
2. Add the behaviour for **buttonReset** so that it resets the shopping list.
3. Confirm that the *undo* functionality continues to work as expected.

---

## 5. Exercise 5

1. Add the **buttonRemove** to the **ShoppingCartPanel** class, placing it next to the **Add** button.
2. Add the behaviour for **buttonRemove** so that it removes the selected product from the shopping list.
3. Confirm that the *undo* functionality continues to work as expected.

---

*(end of instructions)*
