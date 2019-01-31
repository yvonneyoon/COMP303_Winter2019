## Exercises

The following exercises are required. For maximum learning effectiveness, please check the [answers](../Answers/M2-Answers.md) only after giving the problems an honest try.

1. Starting with the code base provided in [Software Design Code](https://github.com/jin-guo/SoftwareDesignCode/tree/master/module02/ca/mcgill/cs/swdesign/m2), implement a well-encapsulated abstraction to represent a "hand" of cards in a player's hand as a Java class `Hand`. A `Hand` should be able to contain between 0 and `N` cards, where `N` is a a parameterizable upper bound that will depend on the card game being played (e.g., 5 for draw poker, 13 for bridge, etc.). Implement the following services on a `Hand`: `add(Card)`, `remove(Card)`, `contains(Card)`, `isEmpty()`, `size()`, and `isFull()`. Find a way to provide access to the cards in the hand. Ensure that all the rules of encapsulation seen in Module 1 are respected and use Design by Contract to clarify valid and invalid inputs.

2. Make is possible to compare two hands using the [Comparable](http://docs.oracle.com/javase/8/docs/api/java/lang/Comparable.html) interface. Sort hands by increasing number of cards in the hand. Write a small driver program to test your class. You do not need to handle the case where the argument is `null`. How to handle this case properly requires the material of later modules.
 
3. Make is possible to compare two hands using the [Comparator](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html) interface. Implement two different hand comparison strategies. Define *factory methods* in the `Hand` class to return anonymous instances of comparators for the different sorting strategies. You do not need to handle the case where the argument is `null`. How to handle this case properly requires the material of later modules.

4. Implement a `UniversalComparator` that stores the type of desired comparison as an enumerated type, and switches on that type.

5. Objects of class `Hand` aggregate exactly 10 objects of class `Card`. Implement the mechanism necessary to support sorting hands using the `Arrays.sort` functionality of the JDK. The required behavior for comparing hands is that hands should be ordered in terms of number of cards of a certain rank. Clients should be able to compare hands by number of aces, or number kings, or number of fours, etc. For example, if the client chooses to compare hands by number of aces, a hand with one ace should come before a hand with two aces. If two hands have the same number of aces, they should be considered equal and their order does not matter. The same logic applies to any rank. To answer this question, create the UML class diagram with all relevant elements, and write the code of the method or methods that implement the actual comparison. Your solution should include, among others, the Strategy design pattern and a method that acts as an object factory.

6. Create a UML Class Diagram that captures the main design decisions of JetUML class [SelectionList](https://github.com/prmr/JetUML/blob/v1.0/src/ca/mcgill/cs/stg/jetuml/framework/SelectionList.java) as an aggregator of graph elements. This class has been refactored as a more complex class named [SelectionModel](https://github.com/prmr/JetUML/blob/master/src/ca/mcgill/cs/jetuml/gui/SelectionModel.java). For the purpose of this exercise, please use the class before refactoring. Hint: you don't need to understand all the details of the class to be able to complete this exercise.

## Optional
The following exercises are are optional. The ones prefixed with :star: are more challenging questions aimed to provide you with additional design and programming experience. The ones prefixed with :spades: will incrementally guide you towards the ultimate completion of a complete Solitaire application.

1. :spades: Create a new Eclipse project named "Solitaire" (you can also remove all the java files from the your clone of the [Solotaire Repository](https://github.com/prmr/Solitaire) to get a fresh start). Add this project to a git repository and create a new package `comp303.solitaire.cards`. Copy the 3 files of the [Solitaire `cards` package](https://github.com/prmr/Solitaire/tree/v0.3/src/ca/mcgill/cs/stg/solitaire/cards) into your own package and adjust the package statements as required. You should now have a fully compilable version of the first three classes of the Solitaire application.

2. :spades: Design a well-encapsulated class to represent the "suit stacks". A "suit stack" is a stack where players accumulate finished sequences of cards of a same suit, with the Ace at the bottom and subsequent cards on top of it in strictly increasing order of rank. Call your class `SuitStack`. Try to anticipate the services this class will need, and implement them as methods of the class.

---
Note: this content is updated from exercises in [Introduction to Software Design with Java](https://github.com/prmr/SoftwareDesign/blob/master/modules/Module-02.md) by Martin P. Robillard