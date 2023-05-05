Download Link: https://assignmentchef.com/product/solved-cse241-programming-assignment-4
<br>
<strong>Description</strong>

<ul>

 <li>This is an individual assignment. Please do not collaborate</li>

 <li>If you think that this document does not clearly describes the assignment, ask questions before its too late.</li>

</ul>

This assignment is about implementing and testing classes for a logic circuit simulator.

<ul>

 <li>Your program reads two files:

  <ul>

   <li>txt</li>

   <li>txt</li>

  </ul></li>

 <li>According to content in <sub>txt</sub>, the program <strong><sub>dynamically </sub></strong>creates necessary objects for a logic circuit and evaluates the states listed in <sub>input.txt</sub>.</li>

 <li>Your program prints the output to <sub>stdout</sub>. Each line in <sub>txt </sub>is a state. For each state, there should be</li>

</ul>

a line of output printed.

<h1>circuit.txt</h1>

<ul>

 <li>Each line starts with a <sub>keyword</sub>. Possible <sub>keyword</sub>s:</li>

</ul>

INPUT

OUTPUT

AND

OR

NOT

FLIPFLOP

DECODER

<ul>

 <li>The first line specifies input labels. Labels are separated by spaces. Example:</li>

</ul>

INPUT a input2 c3 k

<ul>

 <li>Here there are <sub>4 </sub>inputs are defined. Each has an identifier. <sub>a</sub>, <sub>input2</sub>, <sub>c3</sub>, <sub>k</sub>.</li>

 <li>The second line specifies output labels. Labels are separated by spaces. Example:</li>

</ul>

OUTPUT d1 d2 d3 d4

<ul>

 <li>Here there are <sub>4 </sub>outputs are defined. Each has an identifier. <sub>d1</sub>, <sub>d2</sub>, <sub>d3</sub>, <sub>d4</sub>.</li>

 <li><sub>AND </sub>keyword specifies that there is an <sub>and </sub>gate defined. <sub>AND </sub>keyword follows the identifier for its output and two other identifiers for the inputs. Example:</li>

</ul>

AND gate_A c3 another_id

<ul>

 <li>Here the <sub>and </sub>gate has an output identified by the string <sub>gate_A</sub>. Its inputs are identified <sub>c3 </sub>and <sub>another_id</sub>. These identifiers can be input identifiers or identifiers for other gates.</li>

 <li><sub>OR </sub>keyword specifies that there is an <sub>or </sub>gate defined. <sub>OR </sub>keyword follows the identifier for its output and two other identifiers for the inputs. Example:</li>

</ul>

OR gate_B ck id3

<ul>

 <li>Here the <sub>or </sub>gate has an output identified by the string <sub>gate_B</sub>. Its inputs are identified <sub>ck </sub>and <sub>id3</sub>. These identifiers can be input identifiers or identifiers for other gates.</li>

 <li><sub>NOT </sub>keyword specifies that there is a <sub>not </sub>gate defined. <sub>NOT </sub>keyword follows the identifier for its output and one other identifier for its input. Example:</li>

</ul>

NOT gate_C c5

<ul>

 <li>Here the <sub>not </sub>gate has an output identified by the string <sub>gate_C</sub>. It has only one input an it is identified by the string <sub>c5</sub>.</li>

 <li><sub>FLIPFLOP </sub>keyword specifies that there is a <sub>flip-flop </sub>gate defined. <sub>FLIPFLOP </sub>keyword follows the identifier</li>

</ul>

for its output and one other identifier for its input. Example:

FLIPFLOP gate_F c6

<ul>

 <li>Here the <sub>flip-flop </sub>gate has an output identified by the string <sub>gate_F</sub>. Its input is identified by <sub>c6</sub>.</li>

 <li><sub>DECODER </sub>keyword specifies that there is a <sub>decoder </sub>gate defined. <sub>DECODER </sub>keyword follows the identifiers for</li>

</ul>

its outputs(o1, o2, o3, o4) and identifiers for its inputs(a1, a2). Example:

DECODER d1 d2 d3 d4 g1 another_identifier

<ul>

 <li>Here the <sub>decoder </sub>gate has outputs identified by strings <sub>o1</sub>, <sub>o2</sub>, <sub>o3</sub>, <sub>o4</sub>. Its inputs are identified by <sub>g1 </sub>and another_identifier.</li>

</ul>

<h1>input.txt</h1>

<ul>

 <li>Each line is a list of <sub>1 </sub>and <sub>0</sub>. Example:</li>

</ul>

1 0 1 1

0 1 1 1

<ul>

 <li>0 1 0</li>

 <li>0 0 1</li>

</ul>

<strong>Example:</strong>

<ul>

 <li>Suppose that <sub>txt </sub>is has the following content:</li>

</ul>

INPUT a b c d

OUTPUT d1 d2 d3 d4

AND and1 a b

OR or1 and1 c

NOT n1 d

FLIPFLOP f1 n1

AND a2 or1 f1

DECODER d1 d2 d3 d4 a2 f1

<ul>

 <li><sub>txt </sub>has the following content:

  <ul>

   <li>1 0 1</li>

  </ul></li>

</ul>

1 0 1 0

1 1 1 0

<ul>

 <li>Assume that initially former-out of any FLIPFLOP is 0.</li>

 <li>Any <sub>FLIPFLOP</sub>s should preserve the state throughout the evaluation of the whole <sub>txt</sub>.</li>

 <li>Each line in <sub>txt </sub>is assigned to identifiers <sub>a</sub>, <sub>b</sub>, <sub>c</sub>, <sub>d</sub>, defined in <sub>circuit.txt</sub>. According to the truth tables, outputs of gates are calculated.</li>

 <li>For the input.txt given, the output of your program should be:

  <ul>

   <li>0 0 0</li>

   <li>0 0 1</li>

   <li>0 0 0</li>

  </ul></li>

</ul>

Figure 1: Example Logic Circuit

<strong>Remarks</strong>

<ul>

 <li>Each identifier is unique. You can assume that their length is limited to 15 characters. You can use std::string.</li>

 <li>There won’t be any errors in the files.</li>

 <li>You have to use <sub>dynamic memory allocation </sub>and C++ classes.</li>

 <li>You have use inheritance and polymorphism. Find a class hierarchy and try to use abstraction.</li>

 <li>You are not allowed to used <sub>std::vectors</sub>.</li>

 <li>You cannot use components which are not covered in class. (such as templates etc..)</li>

 <li>In order to learn about file I/O operations, you can go through the related book chapter(not covered in class). Or you can read the section presented in <sub>assignment 3</sub>.</li>

</ul>

<strong>Turn in:</strong>

<ul>

 <li>Source code of a complete C++ program and a suitable makefile. You should use c++11 standard. Your code will be tested in a linux-gcc environment.</li>

 <li>A script will be used in order to check the correctness of your results. So, be careful not to violate the expected output format.</li>

 <li>Provide comments unless you are not interested in partial credit. (If I cannot easily understand your design, you may loose points.)</li>

 <li>You cannot get full credit if your implementation contradicts with the statements in this document.</li>

</ul>

<strong>Truth Tables:</strong>

<ul>

 <li>AND</li>

</ul>

<table width="65">

 <tbody>

  <tr>

   <td width="23">a</td>

   <td width="23">b</td>

   <td width="19">out</td>

  </tr>

  <tr>

   <td width="23">0</td>

   <td width="23">0</td>

   <td width="19">0</td>

  </tr>

  <tr>

   <td width="23">0</td>

   <td width="23">1</td>

   <td width="19">0</td>

  </tr>

  <tr>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="19">0</td>

  </tr>

  <tr>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="19">1</td>

  </tr>

  <tr>

   <td width="23"> </td>

   <td width="23"> </td>

   <td width="19"> </td>

  </tr>

  <tr>

   <td width="23">a</td>

   <td width="23">b</td>

   <td width="19">out</td>

  </tr>

  <tr>

   <td width="23">0</td>

   <td width="23">0</td>

   <td width="19">0</td>

  </tr>

  <tr>

   <td width="23">0</td>

   <td width="23">1</td>

   <td width="19">1</td>

  </tr>

  <tr>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="19">1</td>

  </tr>

  <tr>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="19">1</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>OR</li>

 <li>NOT</li>

</ul>

<table width="42">

 <tbody>

  <tr>

   <td width="23">a</td>

   <td width="19">out</td>

  </tr>

  <tr>

   <td width="23">0</td>

   <td width="19">1</td>

  </tr>

  <tr>

   <td width="23">1</td>

   <td width="19">0</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>FLIPFLOP</li>

</ul>

<table width="125">

 <tbody>

  <tr>

   <td width="23">a</td>

   <td width="83">former_out</td>

   <td width="19">out</td>

  </tr>

  <tr>

   <td width="23">0</td>

   <td width="83">0</td>

   <td width="19">0</td>

  </tr>

  <tr>

   <td width="23">0</td>

   <td width="83">1</td>

   <td width="19">1</td>

  </tr>

  <tr>

   <td width="23">1</td>

   <td width="83">0</td>

   <td width="19">1</td>

  </tr>

  <tr>

   <td width="23">1</td>

   <td width="83">1</td>

   <td width="19">0</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>DECODER</li>

</ul>

<table width="162">

 <tbody>

  <tr>

   <td width="29">a1</td>

   <td width="29">a2</td>

   <td width="30">d1</td>

   <td width="30">d2</td>

   <td width="30">d3</td>

   <td width="14">d4</td>

  </tr>

  <tr>

   <td width="29">0</td>

   <td width="29">0</td>

   <td width="30">1</td>

   <td width="30">0</td>

   <td width="30">0</td>

   <td width="14">0</td>

  </tr>

  <tr>

   <td width="29">0</td>

   <td width="29">1</td>

   <td width="30">0</td>

   <td width="30">1</td>

   <td width="30">0</td>

   <td width="14">0</td>

  </tr>

  <tr>

   <td width="29">1</td>

   <td width="29">0</td>

   <td width="30">0</td>

   <td width="30">0</td>

   <td width="30">1</td>

   <td width="14">0</td>

  </tr>

  <tr>

   <td width="29">1</td>

   <td width="29">1</td>

   <td width="30">0</td>

   <td width="30">0</td>

   <td width="30">0</td>

   <td width="14">1</td>

  </tr>

 </tbody>

</table>


