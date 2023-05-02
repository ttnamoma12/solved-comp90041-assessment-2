Download Link: https://assignmentchef.com/product/solved-comp90041-assessment-2
<br>
In this assignment, you will write a program named <strong>SimpleCompetitions </strong>that helps companies (e.g., retailers) create competitions to boost their sales. For instance, during Easter Sale, a retailer can use your software to create a lucky draw game. In the game, a customer is given entries equivalent to the size of its purchase after their single-purchase final balance, after discounts, reach a specific amount, say $50. Once the competition time ends, the retailer draws winners and the winning customers will get points added to their membership account; customers can use these points for future purchases if they wish. Please read the competition policy and application walk-through sections for more information. This assignment is designed in such a way that we can evaluate your knowledge on the following topics: 1) class design and implementation, 2) control flow structures (e.g., if-then-else &amp; switch-case statements, loops), 3) basic I/O (e.g., Scanner class, formatted printing), 4) arrays, and 5) inheritance &amp; polymorphism.

<ul>

 <li><strong>Your Task</strong></li>

</ul>

Go to <em>https://classroom.github.com/a/vUhbB-Zy </em>and accept the assignment. For details on how to check out the repository, make sure to consult the Lab 3 Materials<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>. Once you have cloned the repository, you will find four classes in it:

SimpleCompetitions.java

Competition.java

Entry.java

AutoEntry.java

SimpleCompetitions.java will be the main application containing your main() method. The classes come with some initial implementations that follow the design shown in Figure 1. You are asked to add constructors, instance variables, and methods to complete the program. See the competition policy and application walk-through sections to understand the required features of the program. <strong>Note that in the provided UML class diagram and the application skeleton on GitHub, we only suggest methods’ names; you can make any modifications to the methods’ return types and their argument lists if necessary to complete the task</strong>. You may add your own class(es) if you think it

Figure 1: UML Class Diagram for the SimpleCompetitions Application.

is necessary, but your program must contain the classes mentioned above.

<strong>For this assignment, all user inputs will be assumed to be of correct data types; such that if a String is expected then it is assumed a string will be entered, and the same for an integer or a decimal number. No error control for incorrectly entered data types are required <u>unless stated otherwise!</u></strong>.

<ul>

 <li><strong>Competition Policy</strong></li>

</ul>

In this assignment, you are asked to implement a specific competition type with the following policy. • Only customers who have valid membership accounts can enter a competition. Having said that, you do not need to check if a membership account exists in this assignment. As long as the membership identifier is in the correct format, it should be fine.

<ul>

 <li>There is no limit on the number of competitions that a customer can enter. However, for this assignment, there is only one active competition (whose result is not decided) at a specific point in time i.e. the system does not support concurrent competitions.</li>

 <li>In a specific competition, one customer can have an unlimited number of entries based on their paid bills.</li>

 <li>For each entry, the customer is asked to select 7 numbers in the range from 1 to 35. You can imagine that s/he is provided a card on which s/he can manually select numbers for some entries and/or ask the system to randomly generate entries. Completed cards must be returned to a staff member after purchases so that the information can be inputted into the system.</li>

 <li>Customers get one entry for each $50 in a single bill. For example, if a total bill is $245, it is eligible for getting four entries.</li>

 <li>Once the competition time ends, the organizer can draw winners by using the system to randomly generate a lucky entry. If an entry shares at least two numbers in common with the lucky entry, the owner of that entry would get some prize. The detailed prizes are listed on Table 1. <strong>Note that if a customer has several winning entries, only the first one with the highest prize will be awarded. By saying first winning entry, we mean the entry that has smallest entry identifier.</strong></li>

</ul>

<table width="321">

 <tbody>

  <tr>

   <td width="73">Division</td>

   <td width="166">Winning number required</td>

   <td width="82">Prize</td>

  </tr>

  <tr>

   <td width="73">1</td>

   <td width="166">7 numbers</td>

   <td width="82">50000 points</td>

  </tr>

  <tr>

   <td width="73">2</td>

   <td width="166">6 numbers</td>

   <td width="82">5000 points</td>

  </tr>

  <tr>

   <td width="73">3</td>

   <td width="166">5 numbers</td>

   <td width="82">1000 points</td>

  </tr>

  <tr>

   <td width="73">4</td>

   <td width="166">4 numbers</td>

   <td width="82">500 points</td>

  </tr>

  <tr>

   <td width="73">5</td>

   <td width="166">3 numbers</td>

   <td width="82">100 points</td>

  </tr>

  <tr>

   <td width="73">6</td>

   <td width="166">2 numbers</td>

   <td width="82">50 points</td>

  </tr>

 </tbody>

</table>

Table 1: Prize table

<ul>

 <li><strong>Application Walk-through</strong></li>

</ul>

For this application, you are asked to support two different modes: 1) the normal mode (i.e. release mode), and 2) the testing mode. The testing mode is designed in such a way that you can test your program in a deterministic manner. The markers will also use that mode for running automated tests. The mode is required because this application is supposed to generate random numbers for both customers’ entries and the lucky entries and it is hard to test its correctness without controlling the randomness. More details about how to implement the testing mode are explained below.

<ol>

 <li>Your program will start by displaying a welcome message. You will need to choose one mode (normal or testing mode) to start the program. The options are case insensitive and there is a simple check for invalid options. <strong>Note that the program outputs (e.g., menus and output messages) look the same in both the normal and testing mode. The two modes are different only in the ways entry numbers are generated.</strong></li>

</ol>

—-WELCOME TO SIMPLE COMPETITIONS APP—-

Which mode would you like to run? (Type T for Testing, and N for Normal mode):

A

Invalid mode! Please choose again.

Which mode would you like to run? (Type T for Testing, and N for Normal mode):

N

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

</ol>

<h1>2.    Add new entries</h1>

<ol start="3">

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

 <li>The main menu has five options for 1) creating a new competition, 2) adding new entries, bothmanually and automatically, into the current active competition, 3) drawing to find winners, 4) viewing a summary report of all competitions, and 5) exiting the program. Note that the user <strong>should not </strong>be able to 1) create a new competition if there is already an active one, or 2) add new entries or draw winners if there is no active competition. Error messages should be displayed if users try to do so. Following are some sample error messages. See all error messages in the provided test cases.</li>

</ol>

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

</ol>

<ol start="3">

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

2

There is no active competition. Please create one!

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

3

There is no active competition. Please create one!

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

 <li>If the first option (“Create a new competition”) is selected, by typing “1” and then pressing Enter,the program should call the addNewCompetition method of the SimpleCompetitions class to add a new competition with a given name. After creating a new competition, the program should goes back to the main menu. The newly created competition becomes active so that the user cannot create another competition. If s/he tries to do so, an error message should be displayed.</li>

</ol>

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

1

Competition name:

Easter Holidays

A new competition has been created!

Competition ID: 1, Competition Name: Easter Holidays Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit1</li>

</ol>

There is an active competition. SimpleCompetitions does not support concurrent competitions!

<ol start="4">

 <li>Now the user can choose the second option to add entries. The program should first ask for information such as membership ID, bill ID (i.e. receipt number), and the total amount of the bill. Both membership ID and billID need to follow the same format – these must be 6-digit numbers and the numbers can start with zero(es). For example, both 001234 and 123456 are valid identifiers but 123abc is not. The total bill should be used to calculate how many entries the customer can get for this bill.</li>

</ol>

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

2

Member ID:

1234

Invalid member id! It must be a 6-digit number. Please try again.

Member ID:

123abc

Invalid member id! It must be a 6-digit number. Please try again.

Member ID:

123456

Bill ID:

111aaa

Invalid bill id! It must be a 6-digit number. Please try again. Bill ID:

112233

Total amount: 102.5

This bill is eligible for 2 entries. How many manual entries did the customer fill up?:

<ol start="5">

 <li>Once correct information is provided and the number of given entries are decided, your program should ask for the number of manual entries for this bill. In the above example, the customer is eligible to get two entries for their bill. Suppose that s/he manually filled up one entry, by selecting 7 numbers in the range from 1 to 35, and asked for another one to be automatically generated. The program output should looks like the following. <strong>You will observe that manual entries should be added first and entries’ indices start from 1.</strong></li>

</ol>

<h1>This bill is eligible for 2 entries. How many manual entries did the customer fill up?:</h1>

1

Please enter 7 different numbers (from the range 1 to 35) separated by whitespace.

1 2 3 4 5 6 7

<h1>The following entries have been added:</h1>

Entry ID: 1                                   Numbers: 1 2 3 4 5 6 7

Entry ID: 2                               Numbers: 2 5 13 17 25 30 35 [Auto]

<h1>Add more entries (Y/N)?</h1>

<ol start="6">

 <li>You can see that the numbers in the second entry in the above example were randomly generated by the program. You can do so using different ways. However, in this assignment we leverage the shuffle method of the Collections class<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a>. We provide the implementation for the createNumbers method in the AutoEntry class. <strong>The randomness is controlled by the seed argument. In the testing mode, you should use the competition identifier as seed for generating the lucky entry and the number of entries in the currently active competition to generate automated customers’ entries.</strong></li>

</ol>

public int[] createNumbers (int seed) {

ArrayList&lt;Integer&gt; validList = new ArrayList&lt;Integer&gt;(); int[] tempNumbers = new int[7]; for (int i = 1; i &lt;= 35; i++) { validList.add(i);

}

Collections.shuffle(validList, new Random(seed));

for (int i = 0; i &lt; 7; i++) {

tempNumbers[i] = validList.get(i);

} Arrays.sort(tempNumbers); return tempNumbers;

}

<strong>Note that there are checks for a valid entry</strong>. Error messages should be reported if the given numbers do not adhere to the format.

This bill is eligible for 2 entries. How many manual entries did the customer fill up?: 1

Please enter 7 different numbers (from the range 1 to 35) separated by whitespace.

1 2 3 4

Invalid input! Fewer than 7 numbers are provided. Please try again!

Please enter 7 different numbers (from the range 1 to 35) separated by whitespace.

1 2 3 4 4 5 6

Invalid input! All numbers must be different!

Please enter 7 different numbers (from the range 1 to 35) separated by whitespace.

1 2 3 4 5 6 7 8

Invalid input! More than 7 numbers are provided. Please try again!

Please enter 7 different numbers (from the range 1 to 35) separated by whitespace.

The user can then add more entries into the current competition and use the 3rd option from the main menu to draw and find winners. As shown below, the program should display the information of the lucky numbers and all the winning entries with their prizes. The entries are sorted by their identifiers. As stated in the competition policy, if a customer has several winning entries, only the first one with the highest prize will be awarded. By saying first winning entry, we mean the entry that has smallest entry identifier.

Add more entries (Y/N)?

Y

<h1>Member ID:</h1>

111222

Bill ID:

125678

Total amount: 305.8

This bill is eligible for 6 entries. How many manual entries did the customer fill up?:

0

The following entries have been added:

<table width="370">

 <tbody>

  <tr>

   <td width="119">Entry ID: 3</td>

   <td width="251">Numbers: 9 12 13 18 20 23 28 [Auto]</td>

  </tr>

  <tr>

   <td width="119">Entry ID: 4</td>

   <td width="251">Numbers: 1 2 9 10 11 17 35 [Auto]</td>

  </tr>

  <tr>

   <td width="119">Entry ID: 5</td>

   <td width="251">Numbers: 6 9 14 15 20 23 30 [Auto]</td>

  </tr>

  <tr>

   <td width="119">Entry ID: 6</td>

   <td width="251">Numbers: 5 13 14 17 23 27 33 [Auto]</td>

  </tr>

  <tr>

   <td width="119">Entry ID: 7</td>

   <td width="251">Numbers: 6 9 13 16 18 24 29 [Auto]</td>

  </tr>

  <tr>

   <td width="119">Entry ID: 8</td>

   <td width="251">Numbers: 1 2 5 16 17 21 30 [Auto]</td>

  </tr>

 </tbody>

</table>

Add more entries (Y/N)?

N

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

3

Lucky entry for Competition ID: 1, Competition Name: Easter Holidays

Numbers: 3 4 17 18 24 29 30 [Auto]

Winning entries:

Member ID: 123456, Entry ID: 1 , Prize: 50 , Numbers: 1 2 3 4 5 6 7 Member ID: 111222, Entry ID: 7 , Prize: 100 , Numbers: 6 9 13 16 18 24 29 [Auto] Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

Now the user can follow similar steps to create other competitions, or s/he can use the 4th option to display a summary report, or the 5th option to terminate the program.

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

1

Competition name:

Anzac Day

A new competition has been created! Competition ID: 2, Competition Name: Anzac Day Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

4

—-SUMMARY REPORT—-

+Number of completed competitions: 1

+Number of active competitions: 1

Competition ID: 1, name: Easter Holidays, active: no

Number of entries: 8

Number of winning entries: 2

Total awarded prizes: 150

Competition ID: 2, name: Anzac Day, active: yes

Number of entries: 0

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

5 Goodbye!

<ul>

 <li><strong>Example Executions</strong></li>

</ul>

In this section, we show two example executions for both the normal mode and the testing mode. You may observe that the program logic is the same and the outputs look similar. As stated above, the two modes are only different in the ways random numbers are generated. Specifically, for the testing mode, since the randomness is controlled by using seeds, if you provide the same input, the program should produce the same output. <strong>Note that in the example executions, we show both the input and output of the program. In the given test cases, the input and output are stored in different files. See Section 7 (Testing Before Submission) for more details.</strong>

<strong>5.1        Example Execution in Normal Mode</strong>

—-WELCOME TO SIMPLE COMPETITIONS APP—-

Which mode would you like to run? (Type T for Testing, and N for Normal mode):

N

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

1

Competition name:

Easter Holidays

A new competition has been created!

Competition ID: 1, Competition Name: Easter Holidays Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

2

Member ID:

123456

Bill ID:

112233

Total amount: 102.5

This bill is eligible for 2 entries. How many manual entries did the customer fill up?:

1

Please enter 7 different numbers (from the range 1 to 35) separated by whitespace.

1 2 3 4 5 6 7

The following entries have been added:

Entry ID: 1 Numbers: 1 2 3 4 5 6 7 Entry ID: 2 Numbers: 2 4 6 11 12 23 34 [Auto]

Add more entries (Y/N)?

Y

Member ID:

111222

Bill ID:

125678

Total amount: 305.8

This bill is eligible for 6 entries. How many manual entries did the customer fill up?:

0

The following entries have been added:

Entry ID: 3                                   Numbers: 1 2 12 13 16 17 34 [Auto]

Entry ID: 4                                 Numbers: 1 10 21 30 31 32 35 [Auto]

Entry ID: 5                                    Numbers: 3 7 9 10 13 19 35 [Auto]

Entry ID: 6                                   Numbers: 5 9 15 19 28 31 32 [Auto]

Entry ID: 7                                 Numbers: 1 10 12 18 22 27 32 [Auto]

Entry ID: 8                                   Numbers: 3 4 11 13 17 24 30 [Auto]

Add more entries (Y/N)?

N

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

3

Lucky entry for Competition ID: 1, Competition Name: Easter Holidays

Numbers: 1 3 8 13 24 25 31 [Auto]

Winning entries:

Member ID: 123456, Entry ID: 1 , Prize: 50 , Numbers: 1 2 3 4 5 6 7 Member ID: 111222, Entry ID: 8 , Prize: 100 , Numbers: 3 4 11 13 17 24 30 [Auto] Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

1

Competition name:

Anzac Day

A new competition has been created! Competition ID: 2, Competition Name: Anzac Day Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

4

—-SUMMARY REPORT—-

+Number of completed competitions: 1

+Number of active competitions: 1

Competition ID: 1, name: Easter Holidays, active: no

Number of entries: 8

Number of winning entries: 2

Total awarded prizes: 150

Competition ID: 2, name: Anzac Day, active: yes

Number of entries: 0

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

<ul>

 <li>Goodbye!</li>

</ul>

<strong>5.2        Example Execution in Testing Mode</strong>

—-WELCOME TO SIMPLE COMPETITIONS APP—-

Which mode would you like to run? (Type T for Testing, and N for Normal mode):

T

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

1

Competition name:

Easter Holidays

A new competition has been created!

Competition ID: 1, Competition Name: Easter Holidays Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

2

Member ID:

123456

Bill ID:

112233

Total amount: 102.5

This bill is eligible for 2 entries. How many manual entries did the customer fill up?:

1

Please enter 7 different numbers (from the range 1 to 35) separated by whitespace.

1 2 3 4 5 6 7

The following entries have been added:

Entry ID: 1                                       Numbers: 1 2 3 4 5 6 7

Entry ID: 2                                   Numbers: 3 4 17 18 24 29 30 [Auto]

Add more entries (Y/N)?

Y

Member ID:

111222

Bill ID:

125678

Total amount: 305.8

This bill is eligible for 6 entries. How many manual entries did the customer fill up?:

0

The following entries have been added:

Entry ID: 3                                   Numbers: 2 7 14 18 22 25 35 [Auto]

Entry ID: 4                                     Numbers: 1 5 6 8 31 32 35 [Auto]

Entry ID: 5                                   Numbers: 2 5 11 12 23 24 34 [Auto]

Entry ID: 6                                   Numbers: 1 2 13 24 25 31 34 [Auto]

Entry ID: 7                                   Numbers: 2 3 15 18 26 27 31 [Auto]

Entry ID: 8                                   Numbers: 4 6 14 16 17 18 20 [Auto]

Add more entries (Y/N)?

N

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

3

Lucky entry for Competition ID: 1, Competition Name: Easter Holidays

Numbers: 3 4 17 18 24 29 30 [Auto]

Winning entries:

Member ID: 123456, Entry ID: 2                                             , Prize: 50000, Numbers: 3 4 17 18 24 29 30 [Auto]

Member ID: 111222, Entry ID: 8        , Prize: 100 , Numbers: 4 6 14 16 17 18 20 [Auto] Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

1

Competition name:

Anzac Day

A new competition has been created! Competition ID: 2, Competition Name: Anzac Day Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

4

—-SUMMARY REPORT—-

+Number of completed competitions: 1

+Number of active competitions: 1

Competition ID: 1, name: Easter Holidays, active: no

Number of entries: 8

Number of winning entries: 2

Total awarded prizes: 50100

Competition ID: 2, name: Anzac Day, active: yes

Number of entries: 0

Please select an option. Type 5 to exit.

<ol>

 <li>Create a new competition</li>

 <li>Add new entries</li>

 <li>Draw winners</li>

 <li>Get a summary report</li>

 <li>Exit</li>

</ol>

<ul>

 <li>Goodbye!</li>

 <li><strong>Assessment &amp; Important Notes</strong></li>

</ul>

This project is worth 15% of the total marks for the subject.

Your Java program will be assessed based on correctness of the output as well as quality of code implementation.

Automatic tests will be conducted on your program by compiling, running, and comparing your outputs for several test cases with generated expected outputs. The automatic test will deem your output wrong if your output does not match the expected output, even if the difference is just having an <strong>extra space or missing a colon</strong>. Therefore, it is crucial that <strong>your output follows exactly the same format</strong>

<strong>shown in the examples above.</strong>

Also, use <strong>ONLY ONE </strong>Scanner object throughout your program. Otherwise the automatic tests may cause your program to generate exceptions and terminate. The reason is that in the automatic test, multiple lines of test inputs are sent all together to the program. As the program receives the inputs, it will pass them all to the currently active Scanner object, leaving the rest of the Scanner objects nothing to read and hence cause a run-time exception. Therefore, it is important that <strong>your program has only one Scanner object. </strong>Arguments such as “It runs correctly when I do the manual test, but fails under the automatic test” will not be accepted.

<ul>

 <li><strong>Testing Before Submission</strong></li>

</ul>

You will find all input files and the expected output files in the Projects page on Canvas for you to use on your own. <strong>In this assignment, the markers will use the same set of test data for marking</strong>. You should use them to test your code carefully and then submit your code on GitHub. Note that each commit you make is recorded in your GitHub repository. Details of how the submission works can be found in Section 8.

To test your code by yourself:

<ol>

 <li>Check your source code files, and make sure you have the test input data files ready (e.g.,“txt”).</li>

 <li>Open a console, navigate to your project directory (where your .java classes reside), and compileyour program: javac *.java (this command will compile all your java files in the current folder).</li>

 <li>Run command: java SimpleCompetitions &lt; input1.txt &gt; my-output1.txt (it runs the program using contents in “txt” as input and write the output to my-output1.txt).</li>

 <li>Inspect the file my-output1.txt as it contains any errors your program execution may have encountered.</li>

 <li>Compare your result with the provided output file txt. Fix your code if they are different.</li>

 <li>Repeat steps 3-5 for all given input and output pairs. When you are satisfied with your project,commit your changes to GitHub.</li>

</ol>

<strong>Please follow the instructions in Lab-3 documentation if you want to use IDEs like</strong>

<strong>Eclipse.</strong>