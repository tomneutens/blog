---
layout: post
title:  "Defining Computational thinking (CT)"
date:   2022-01-19 15:16:47 +0100
categories: jekyll update
---
For my PhD dissertation, I defined Computational thinking (CT) in the context of Flemish education. Since it is hard to find clear definitions and examples of the concepts that are often considered part of CT, I thought it would be useful to share my definition with a broader audience. This definition is based on literature as well as my own experience in the field of computing education. It is by no means an absolute truth, however, it should provide sufficient insight into what CT is and how it can be part education as well as our day-to-day lives.


# Computational thinking
 
For this work, the most relevant definition of **computational thinking** comes from the Flemish government {% cite vl-decreet-594-2020-2021 %}. They define computational thinking for all learners in a primary and secondary school as the process by which the following techniques are used to generate output: (1) pattern recognition and generalization, (2) decomposition, (3) abstraction, (4) modeling and 5) algorithms. The Flemish government refrains from giving detailed definitions of these five concepts. Below I formulate definitions for these concepts based on definitions found in literature and my own experience. These definitions stem from the philosophy that computer science (CS) is for everyone, implying that computational thinking skills can be applied to computing and non-computing related problems. In the following sections, we define the concepts of computational thinking and provide both computing and non-computing related examples.
 
## Pattern recognition
 
Donald Knuth {% cite knuth1985algorithmic %} defines **pattern recognition** as:
> The ability to spot certain kinds of orders.

There are many different ways in which data can respect some type of order: Similar objects can have a set of identical properties like how all cars have wheels, headlights, and a windshield; A series of events can repeat predictably like the way the traffic lights change at a crossroad, Or the data you are observing can follow a certain trend like how the amount of $CO_2$ in the atmosphere has been rising over the last century {% cite hsu2018learn %}.
 
During programming, **pattern recognition** is used frequently to recognize pieces of code with similar structure or functionality. Having the ability to spot these similarities is essential when writing clean, compact, and reusable code.
 
## Decomposition
 
_**Decomposition**_ is often bluntly defined as breaking a problem down into smaller parts that are easier to understand. {% cite rose2018pirate %}. However, using this definition risks concealing the actual skill required. Just splitting a problem into smaller parts does not necessarily help one to solve the problem in an efficient way {% cite stegeman2016designing %}.
 
Imagine your partner sends you to the store with a shopping list. It’s a long list so you want to categorize it to make it easier to check if you forgot anything. You could group the items by color so, first getting all the red items, then the green items,... It is clear that this is a bad way of decomposing the problem. You have to walk around the supermarket multiple times to get the items by color, lose time, get stressed, and forget half of the items on the list.
 
The key with **decomposition** is not only splitting the problem into parts but also selecting the right way of doing so. For example, in one of our course's projects, students have to write an application that reads accelerometer input and uses it to manipulate a virtual ball they draw on an LCD screen. Figure 1 shows two possible decompositions for the problem. Some students decompose the problem into the parts: 1) Read the input values from the accelerometer. 2) Use these values to calculate the new position of the ball in a Cartesian coordinate system. 3) Map the coordinates to a position on the screen. 4) Draw the ball in that position. While other students decompose it as 1) Read the input values of the accelerometer. 2) Use this information to shift the pixels on the screen to move the ball. These two solutions lead to a similar result. However, in the second group, the physics and display logic are tightly coupled. This leads to problems later in the project when they have to add other elements to the screen. The first way of decomposing the problem proves to be more effective because it results in a better decoupling of responsibilities.
 
Taking into account the importance of the way a problem is decomposed, **decomposition** can be defined as:
> Effectively split up a problem into parts facilitating the solution process.
 
<caption><strong>Figure 1</strong>: Possible decompositions of an application that reads accelerometer input and uses it to manipulate a virtual ball they draw on an lcd-screen.</caption>
 ![Figure 1a: Decoupled physics and display logic.](/assets/images/defining-ct/decomposition_example1.png)
 <caption><strong>Figure 1a</strong>: Decoupled physics and display logic</caption>
 ![Figure 1b: Tightly coupled physics and display.](/assets/images/defining-ct/decomposition_example2.png)
 <caption><strong>Figure 1b</strong>: Tightly coupled physics and display.</caption>
 


 
## Abstraction
 
_**Abstraction**_ is the ability to remove the information you don't need allowing you to focus on the information that is essential to solving the problem} {% cite rose2018pirate %}.
Only keeping information essential to the problem facilitates the creation of a mental schema which in turn aids reasoning about the problem {% cite van1992strategies %}. This schema can be seen as mental categorization of information together with the relations between those categories. Both the removal of information and the creation of a mental schema are an essential part of the **abstraction** process. This importance is illustrated by the examples in the paragraph below.
 
The concept of **abstraction** is often illustrated using animals. Imagine you have a collection of cats you want to draw. These cats have different properties like tail size, fur color, purring sound, name, and breed. Since some properties like purring sound and name are irrelevant when drawing the cat, you can remove this information. This leaves tail size, fur color, and breed. These properties can be seen as a (more) abstract representation of our cat. Even though this type of example is common when explaining **abstraction**, I believe it fails to elucidate part of the essence of **abstraction**, the creation of a mental schema that facilitates reasoning. The following example should clarify why this mental schema is important.
Imagine you work in a shipping warehouse. On one side of the warehouse, items enter in their original packaging. Your task is to load the items onto delivery trucks as efficiently as possible. To make your life easier, you decide to put the items into boxes. On these boxes, you write the width, height, depth, and weight of the box. Putting the items into boxes can be seen as an **abstraction** step, you remove information about the item and reduce it to four parameters. For now, the **abstraction** seems similar to the one in the cat example, however, the new representation of the items (width, height, depth, and weight) can be used to reason about the problem of filling the delivery trucks. We can formulate rules like: boxes can never be stacked on top of boxes with a smaller size or, boxes that weigh over 25kg can never be stacked. Unlike in the cat example, it is clear that the **abstraction** we made in the warehouse example allows us to create a mental schema that facilitates reasoning.
 
These examples clearly illustrate the importance of the creation of a mental schema. Consequently, we can define **abstraction** as:
 
> Remove information you don't need allowing you to create a mental schema that facilitates reasoning.
 
 
A more CS-related example of **abstraction** is sorting algorithms. There are many different sorting algorithms like QuickSort, MergeSort, TimSort, HeapSort, and bubble sort. A programmer doesn't necessarily have to know how these algorithms work, however, if the programmer knows the best, average, and worst time complexity as well as the memory complexity of the algorithm they can reason about which algorithm is most effective in each specific situation. Table 1 illustrates the time complexity of some sorting algorithms.
 
<table>
   \label{tab:performance_sorting_algorithms}
    <tr>
        <td></td>
        <td colspan=3><strong>Time complexity</strong></td>
        <td colspan=2><strong>Memory complexity ($\mathcal{O}$)</strong></td>
    </tr>
    <tr>
        <td><strong>Algorithm</strong></td>
        <td><strong>Best ($\Omega$)</strong></td>
        <td><strong>Average ($\Theta$)</strong></td>
        <td><strong>Worst ($\mathcal{O}$)</strong></td>
        <td></td>
    </tr>
    <tr>
        <td><strong>Quicksort</strong></td>
        <td>$n\log(n)$</td>
        <td>$n\log(n)$</td>
        <td>$n^2$</td>
        <td>$\log(n)$</td>
    </tr>
    <tr>
        <td><strong>MergeSort</strong></td>
        <td>$n\log(n)$</td>
        <td>$n\log(n)$</td>
        <td>$n\log(n)$</td>
        <td>$n$</td>
    </tr>
    <tr>
        <td><strong>TimSort</strong></td>
        <td>$n$</td>
        <td>$n\log(n)$</td>
        <td>$n\log(n)$</td>
        <td>$n$</td>
    </tr>
    <tr>
        <td><strong>HeapSort</strong></td>
        <td>$n\log(n)$</td>
        <td>$n\log(n)$</td>
        <td>$n\log(n)$</td>
        <td>$1$</td>
    </tr>
    <tr>
        <td><strong>Bubble sort</strong></td>
        <td>$n$</td>
        <td>$n^2$</td>
        <td>$n^2$</td>
        <td>$1$</td>
    </tr>
    <caption>Table 1: Abstraction of sorting algorithms</caption>
</table>

 
 
## Generalization
 
In this book, pattern recognition and **generalization** are defined separately to clarify their distinction. **Generalization** is often defined as an extension of pattern recognition {% cite lowe2017operationalized %}. __It is seen as a way of "generalizing" patterns by identifying common elements_. Moreover, Paul Curzon defines **generalization** as a way of quickly solving a problem based on previous problems we have solved. These definitions are broad and sometimes hard to interpret. Moreover, they can be confusing because they fail to clarify the difference between concepts like abstraction and pattern recognition.
In this work, pattern recognition is defined as the act of spotting structure while pattern **generalization** is defined as:

> Making analogies between elements, concepts, or problems.
 
Generalizing is the ability to apply knowledge from your current mental model to a new problem. The power of this definition of **generalization** is that it can be aligned with the other aspects of computational thinking without being confusing. The ability to generalize (find analogies) can be applied to more concrete and more abstract patterns. Imagine a dancer learning a new routine, the routine contains a sequence of movements the dancer has practiced before in other routines. They recognize the set of movements and can instantly perform them in the new routine. The dancer uses information from their mental model to help solve the problem of learning the new routine. This can be seen as a **generalization** of more concrete knowledge. When that same dancer gains more and more experience with that sequence of moves, they might attribute some abstract properties to it (abstraction). For example, the sequence starts and ends on the left foot, it takes eight beats, and you and up in the same position as you started. Now the mental model of the dancer contains an abstract representation of the sequence of moves. Imagine the same dancer is designing a choreography. Somewhere in the choreography they need a sequence of moves to fill a gap of eight beats. Since the rest of the choreography is fixed, after the eight beats, they want to be in the same spot. By making an analogy with the abstract representation of the dance moves in their mental model, the dancer can easily find a fitting move for the choreography. In conclusion, applying **generalization** to a problem can be interpreted as the ability to find analogies. In order to find these analogies, an abstraction step might be needed. Like with the dancing example, the gap in the choreography, as well as the moves the dancer mastered before, had to be abstracted in the same way before an analogy could be made between them.
The same reasoning applies to programming. When a programmer sees repeated code, they can make a concrete **generalization** of that piece of code by creating a function, pasting the code in that function, and calling that function everywhere they removed the duplicate code. However, it might also be the case that there are multiple pieces of code with similar functionality but subtle differences like different values, a different initialization step, and a different way of returning the result. In this case, the programmer has to recognize the similarities in functionality, create an accurate abstraction that captures the functional similarities, and create a function capturing this abstract functionality. This example should illustrate that **generalization** may or may not require an abstraction step.
 
Since generalization is a broad term in CS, some readers might find that the definition of generalization given above does not match with their idea of generalization. One specific domain where the term generalization is used often is machine learning. Machine learning is the science of creating algorithms that can learn complex functions. The goal of these functions is to have predictive power in specific contexts. These functions are usually _trained_ using examples of input-output pairs. These examples are usually called the _training set_. Within this context, **generalization** is defined as the ability of the function to correctly categorize new examples that differ from those in the training set {% cite bishop2014bishop %}. At first, this definition might seem different from the one defined above. However, the machine learning model (=the learned function) can be seen as an analog of the mental model a human constructs when learning. As with generalization in the context of computational thinking, generalization in the context of machine learning can be seen as the ability of the algorithm to make analogies between the representations in the model and the new unseen examples.  
 
 
## Modeling
 
**Modeling** can be defined as:
 
> Synthesizing all the information acquired by abstraction, decomposition, pattern recognition and generalization creating a representation that is easier to understand {% cite lowe2017operationalized %}.
 
The goal of **modeling** is to create representations that are easier to understand and reason with.
**Modeling** is an essential part of science in general, for example, biologists use physical models of animals made from materials like wood or plastic to better understand their anatomy {% cite burnham1992data%}.
In a computing context, the goal of **modeling** is to create representations that can be easily stored and processed by a computer {% cite wing2011research %}. Using this definition, a wide range of representations is possible. For example, a database diagram can be seen as a model for the data used by a company while a graph can be used as a model for representing the railroad connections between cities (Figure 2).
 
  ![Figure 2: An example of a model representing the travel between the major Femish cities by train.](/assets/images/defining-ct/rail_net_model.png)
 <caption><strong>Figure 2</strong>: An example of a model representing the travel between the major Femish cities by train.</caption>

 
## Algorithms
 
**Algorithms** are defined as:

> Step-by-step unambiguous instructions specifying a solution to a problem.

Any plan, like a recipe in a cookbook, can be seen as an algorithm if the instructions are not open for interpretation (unambiguous). However, in the context of computational thinking, the plan has to be formulated in a way that is interpretable by a computer. When specifying these step-by-step instructions, taking into account the way a computer processes information is essential. For example, when writing a program to transmit an image over the internet, you could try to transmit the raw image data pixel by pixel. However, this might not be the best strategy when you know the connection is slow and you have a lot of local processing power. With this in mind, a better strategy might be to compress the image locally, send the compressed data over the connection, and uncompress the data on the other side.
 
## Computational thinking in practice
 
It is important to note that, in practice, these concepts are strongly intertwined. Decomposition can lead to pattern recognition which can lead to abstraction which can lead to pattern recognition, which can lead to the creation of a model, which aids in the formulation of an algorithm, which has some results informing a new abstraction step, helping to update the model,... {% cite lowe2017operationalized}. In the examples above, we provide both computing and non-computing related examples to illustrate that computational thinking is a broadly applicable skill. Arguably, mastering these concepts in everyday life does not imply you mastered computational thinking. Computational thinking requires the extra step of applying these concepts in a computing context, all with the goal of solving the problem using a computer. One might say that mastering these concepts outside a computing context is a necessary but not sufficient condition for mastering computational thinking.
 
The definition of computational thinking above matches with the idea that computational thinking can be usefull for everyone and is necessary for many. It supports the decisions of the Flemish gouvernment to mandate the integration of computational thinking in all fields of study in the first two years of secondary school as well as all non-vocational fields of study in the last four years of secondary school. Moreover, a broad range of fields of study have to take the extra step and have to apply CT in a computing context.
 
The list of computational thinking concepts defined above is by no means exhaustive. Concepts like parallelism, automation, data analysis, and simulation are are often considered to be a part of computational thinking {% cite lowe2017operationalized %}. However, these concepts are not explicitly defined as a part of computational thinking in the Flemish educational framework, consequently, they are less relevant for this thesis. There are some concepts like debugging that are sometimes seen a part of computational thinking that play a significant role in some of the research presented in this work. These concepts will be defined later at the place where they are relevant. 


## References

{% bibliography --cited %}








