Download Link: https://assignmentchef.com/product/solved-lab-10-strings-and-text-files
<br>
<strong><em>Objectives:</em> </strong>

<ol>

 <li>To do some string processing.</li>

 <li>To learn how to read text files. You will find this useful for Assignment 4.</li>

 <li>To learn how to parse a line of text. You will find this useful for Assignment 4 also.</li>

</ol>

<strong><em> </em></strong>

<strong><em>Preparation:</em> </strong>

<ol>

 <li>Go over the Lecture Notes Topic 12</li>

 <li>Textbook reading (optional): Chapter 12 Section 12.2</li>

</ol>

<strong> </strong>

<strong> </strong>

<h1>Exercise 1: Using some String methods</h1>

<ol>

 <li>Type the following sequence of Java statements in the Interactions Pane:</li>

</ol>

String firstName = “harry”;

System.out.println(firstName.toUpperCase());

System.out.println(firstName);




Does the toUpperCase method change the string on which it is invoked? Strings are called <strong><em>immutable</em></strong> because once they are created, they are not changed; a new string is created and returned when a string manipulation method is invoked on a String object.

<ol>

 <li>Enter the following sequence of Java statements in the Interactions Pane:</li>

</ol>

String test = “hello”;

System.out.println(test.charAt(0));

System.out.println(test.charAt(3));

System.out.println(test.charAt(4));




What are the results?  What would you type to print out the letter e from the test string?




<ol>

 <li>The method length() of the String class returns the number of characters in a string. (Note that this is different from the length that we used with arrays.). Complete the simple program below that prints all the characters of a test string, using the charAt() method and the length() (Hint: see Topic 12). Compile and run it.</li>

</ol>




public class PlayWithStrings

{

public static void main (String[] args)

{

String test = “This is a test.”;

/* insert your code here */




}

}




<ol>

 <li>Add code to the program of part c) so that it will also print all the characters of the test string <em>backwards</em>, again using the charAt() method and the</li>

</ol>

length()method. (Hint: start your for loop at the last character in the string)

<strong>  </strong>

<strong> </strong>

<h1>Exercise 2:  String equality</h1>




The String method equals determines whether two strings are the same, and returns the boolean value true if they are the same and false if they are not.




<ol>

 <li>Type the following variable declarations in the Interactions pane:</li>

</ol>




String str1 =”Hello”;

String str2 =”Goodbye”;

String str3 =”Goodbye”;

System.out.println(str1.equals(str2));




<ol>

 <li>Then complete and type in the following if-else statement such that the correct message is printed when comparing str1 to str2:</li>

</ol>




if  ( // fill in the condition here)

System.out.println(“The strings are the same”) else

System.out.println(“The strings are different”);




<ol>

 <li>Now complete and type in the following if-else statement such that the correct message is printed when comparing str2 to str3:</li>

</ol>




if  ( // fill in the condition here)

System.out.println(“The strings are different”) else

System.out.println(“The strings are the same”);




<h1>Exercise 3:  Reading text from a file</h1>

<strong> </strong>

In this exercise, you will learn how to read lines of text (i.e. strings) from a file into memory. You will use a class SimpleReader which we have developed, that provides methods for reading text from a file. (You will find this useful for Assignment 4.)




<ol>

 <li>Download the file <em>java</em> from the Lab 10 section of the Labs folder on the course website. Also download the file <em>test.txt</em>,which is the file you will be reading. It is a text file, so you can look at its contents using Notepad.</li>

</ol>




<ol>

 <li>To read from a file, you first need to create a SimpleReader The constructor for the SimpleReader class takes a parameter that is the name of the file to be read. In the Interactions pane, type the following statement:</li>

</ol>

SimpleReader reader = new SimpleReader(“test.txt”);




<ol>

 <li>The SimpleReader class has two methods that we will use: readFile() and getFileLength(). The readFile() method is used to read all the lines in the file and store them in memory. It creates a String array, where each element of the array contains a line of text from the file. It <strong>returns a reference to that String array.</strong> The method getFileLength() returns the number of lines in the file. In the Interactions pane enter the statements below:</li>

</ol>




String []lineArray = reader.readFile();




The variable lineArray now references the String array that contains the lines of text read from the file.




System.out.println(“The number of lines in the file is ” + reader.getFileLength());

System.out.println(lineArray[0]);

<ol>

 <li>Type the Java statement that prints the third line of text.</li>

</ol>




<ol>

 <li>Type the following Java statement. What happens?</li>

</ol>

reader = new SimpleReader(“blahblah”);

<h1>Exercise 4:  A program to read text from a file</h1>

In this exercise, you will complete a Java program that uses the methods provided by the SimpleReader class to print all the lines of the file <em>test.txt</em>. Type this program into the Definitions pane, filling in the blank spaces, and then compile and run your program.

import java.io.*;




public class ReadandPrintFromFile

{

public static void main(String[] args)

{

String fileName = “test.txt”;




SimpleReader reader = new _____________________________;       String [] lineArray = reader. ____________________;




for (int i = 0; i &lt; reader.__________________; i++)




System.out.println(lineArray[i] +  “
”);

}

}

<strong> </strong>

<h1>Exercise 5: How to parse a line of text</h1>




In this exercise, you will learn how to <strong><em>parse</em></strong> a line of text, i.e. to break it up into individual components (words). (You will find this useful for Assignment 4.)

Our file <em>test.txt</em> contains the following lines of text:

Homer Simpson hsimpson

Lisa Simpson  lsimpson

Bart Simpson  bsimpson

Marge Simpson msimpson




Using the class SimpleReader as in Exercises 3 and 4 results in the String array lineArray with these values:




lineArray[0] = “Homer Simpson hsimpson”  lineArray[1] = “Lisa Simpson  lsimpson”  lineArray[2] = “Bart Simpson  bsimpson”  lineArray[3] = “Marge Simpson msimpson”

Suppose we need to access the components in each line individually, i.e. first name, last name, username. Java provides a class called StringTokenizer that allows us to separate a string into <strong><em>tokens </em></strong>(i.e. individual components or words).  For example, the

string “Homer Simpson hsimpson” has three tokens: “Homer”, “Simpson” and  “hsimpson”. The tokens are separated by one or more blank spaces in a line.




<ol>

 <li>We will start by reading the lines from the file <em>txt</em> into lineArray, as in Exercise</li>

</ol>

3, and then creating a StringTokenizer object.The constructor for the StringTokenizer class takes a parameter that is the string to be tokenized. Reset the Interactions Pane and then type the following statements:

import java.util.StringTokenizer;

SimpleReader reader = new SimpleReader(“test.txt”);

String []lineArray = reader.readFile();

StringTokenizer tokenizer = new

StringTokenizer(lineArray[0]);

<ol>

 <li>The StringTokenizer class has a method nextToken() that returns the next token in the line. Note that a token is a <em>substring </em>of the line. The first call to nextToken() will return the first token: the substring up to the first space in the</li>

</ol>

line. Type the following statements:




String firstName = tokenizer.nextToken(); System.out.println(firstName);

<ol>

 <li>Type the following statements, filling in the blanks, to return and print the second token in the line (the person’s last name):</li>

</ol>




String lastName = _________________________; System.out.println(lastName);

<ol>

 <li>The next call to nextToken()will return the third token (the person’s username)<em>. </em>Type the statements to return and print the person’s username.</li>

 <li>Now type statements to print the person’s name in the form <strong>Simpson, Homer</strong> followed by his username.</li>

 <li>Type the statements needed to the print the information for Lisa Simpson as you did in part e) for Homer Simpson. What statements from parts a) to e) will you need to repeat?</li>

</ol>

<h1>Optional Exercise 6:  A program to read a file and tokenize the lines</h1>

If you have time, write a complete Java program that reads the file <em>test.txt</em> and prints the information from each line of the file in the form you used in Exercise 5 part e). Hint: use a for loop.


