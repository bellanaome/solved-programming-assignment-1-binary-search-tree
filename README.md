Download Link: https://assignmentchef.com/product/solved-programming-assignment-1-binary-search-tree
<br>
In this programming assignment, you are supposed to implement a Binary Search Tree (BST). Each node of the BST will be a string. The directions are on Stepik.

Link to Stepik (Links to an external site.)Links to an external site.

You are required to submit the code in C++ on the Stepik platform and also upload it on canvas as a .cpp file. Three test cases will be provided to you to test your output on Stepik but you will be graded on 16 test cases including the three that are available to you. Each test case you pass, earns you 5 points. Therefore, 80 points are for implementation.

You are also required to submit a commentary in a docx or txt file explaining:

<ol start="4">

 <li>The complexity of your code (each function)</li>

 <li>Why did you choose the implementation you did?</li>

 <li>What challenges you encountered for this project?</li>

 <li>How do you see this project connecting to your prior course experience?</li>

</ol>

This carries 20 points (5 points each for the four topics). I expect that you will write anywhere between 1~2 pages.

Notes:

<ol start="3">

 <li>The fourth test case is fake and is deliberately programmed to avoid access to other students’ code. So if you pass first three and get a score of 0.75, that is equal to 100%</li>

 <li>Another pro-tip: Instead of using the submit button, use the Run button next to submit to test your own test cases. This is strongly encouraged and it is a good practice to create your own test cases. Anyone who creates them and needs help on verification, feel free to contact me or use slack to verify test cases with your peers.</li>

 <li>The assignment is new and you will be the first batch to work on it. So if you find bugs or issues in input/output, message me on slack and I will update the details.</li>

</ol>

TreePlay

In this programming assignment, you are supposed to implement a Binary Search Tree (BST). Each node of the BST will be a string. This data structure should implement the following methods:

class TreePlay

{

private:

//Tree data structure here or create another class to implement it




public:

1. void insert(string s);         //inserts a new node to the tree

2. void inOrder( );               //prints the in order traversal with each node separated by a space

3. void levelOrder( );            //prints the level order traversal with each node separated by a

space

4. void postOrderPalindrome( );   //prints the post order traversal with each node separated by a

space printing only string palindromes

5. int height( );                 //returns the height of the tree – if one root node – height is 1

6. int search(string s);          //search string s in the tree, return 1 if found and 0 if not found.

7. void deleteNode(string s);     //deletes the string s from the tree replacing s with successor node

if it has two children. If s is not present, don’t do anything.

8. void skipLevelOrder(int l);    //prints the level order traversal excluding the elements at level l

Root’s level is 0 and if level is more than existing levels, don’t

do anything.

};







You are expected to write code for each of the functions as well as implement the BST. A sample int main() function that invokes your BST is provided and you can test it on three test cases. Make sure you do not change any code in the main() function.




Composition of main() Method (How I will Test your code):




Input:

9                  – Line 1 indicates the number of operations you will be performing or the number of lines that follow

1 Cat           – Each line’s first integer indicates operation; 1 here means insert() and this follows input to the operation – “Cat”

1 DoD          – insert(DoD)

2                   – 2 is inOrder. Therefore, operation is inorder()

3                   – 3 is levelOrder. Therefore, operation is levelOrder ()

4                   – 4 is postOrderPalindrome. Therefore, operation is postOrderPalindrome()

5                   – 5 is height. Therefore, operation is height()

6 Cat            – 6 is search. Therefore, operation is search(Cat)

7 Cat            – 7 is deleteNode. Therefore, operation is deleteNode(Cat)

8 1                – 8 is skipLevelOrder . Therefore, operation is skipLevelOrder(1)




Output (for above input):

Functions 1, 5, 6 and 7 do not print anything.

Cat DoD

Cat DoD

DoD

2

1

DoD




Rubric:

Commentary: 20 points

Test Cases: 80 points




There will be 16 Test cases including three visible test cases. Each test case will be worth 5 points and last test case is fake.




Test case 1-3 are now available. The other test cases 4-16 will be available Jan 30. They won’t be visible but you can test if they pass or not.

Sample Input 1:




6

1 Cat

1 Dog

1 Elephant

1 Ape

1 Bugs

2

Sample Output 1:




Ape Bugs Cat Dog Elephant

Sample Input 2:




7

1 Cat

1 DoD

4

5

6 Cat

7 Cat

2

Sample Output 2:




DoD

2

1

DoD

Sample Input 3:




6

1 Cat

1 Dog

1 Elephant

1 Ape

1 Bugs

8 1

Sample Output 3:




Cat Bugs Elephant

Code Challenge — Write a program, test using stdin → stdout




#include&lt;iostream&gt;

#include&lt;string&gt;

#include&lt;sstream&gt;

using namespace std;




class TreePlay

{

private:

// Tree data structure here

public:

void insert(string s);

void inOrder();

void levelOrder( );

void postOrderPalindrome( );

int height( );

int search(string s);

void deleteNode(string s);

void skipLevelOrder(int l);

};




int main()

{

//DO NOT CHANGE THIS FUNCTION. CHANGE YOUR IMPLEMENTATION CODE TO MAKE IT WORK

int noOfLines, operation, inputInt, h;

string input;

cin&gt;&gt;noOfLines;

TreePlay obj;

for(int i=0;i&lt;noOfLines;i++)

{

cin&gt;&gt;operation;

switch(operation)

{

case 1:

cin&gt;&gt;input;

obj.insert(input);

break;

case 2:

obj.inOrder();

cout&lt;&lt;“
”;

break;

case 3:

obj.levelOrder();

cout&lt;&lt;“
”;

break;

case 4:

obj.postOrderPalindrome();

cout&lt;&lt;“
”;

break;

case 5:

h=obj.height();

cout&lt;&lt;h&lt;&lt;“
”;

break;

case 6:

cin&gt;&gt;input;

h=obj.search(input);

cout&lt;&lt;h&lt;&lt;“
”;

break;

case 7:

cin&gt;&gt;input;

obj.deleteNode(input);

break;

case 8:

cin&gt;&gt;inputInt;

obj.skipLevelOrder(inputInt);

cout&lt;&lt;“
”;

break;

}

}

return 0;

}