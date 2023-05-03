Download Link: https://assignmentchef.com/product/solved-cs-510-software-engineering-project-1-version-1
<br>
IPlease download proj1-skeleton.tar.gz from Blackboard to get the necessary source code and test cases needed for finishing this project.

I expect each of you to do this project independently.

<strong>Submission Instructions:</strong>

Please read the following instructions carefully. <strong>If you do not follow the instructions, you may be penalized up to 5 points. </strong>Illegible answers receive no points.

Go to Blackboard → Project 1 to submit your answer. Submit only one file in .tar.gz format. Please name your file

<em>&lt;</em>FirstName<em>&gt;</em>–<em>&lt;</em>LastName<em>&gt;</em>–<em>&lt;</em>Username<em>&gt;</em>.tar.gz

For example, use John-Smith-jsmith.tar.gz if you are John Smith with username jsmith. The .tar.gz file should contain the following items:

<ul>

 <li>a single pdf file “proj1 sub.pdf”. The first page must include your full name, and your Purdue email address.</li>

 <li>a directory “q1” that contains your code (source code only; no binaries or object files) for Question 1</li>

 <li>“q2/sll fixed.c” for Question 2</li>

 <li>“q3/TestM.java” for Question 3, and</li>

 <li>“q4/CFGTest.java” and “q4/CFG.java” for Question 4.</li>

</ul>

You can submit multiple times. After submission, <strong>please view your submissions to make sure you have uploaded the right files/versions</strong>.

<h1>Question 1 (5 points)</h1>

Write one simple program that prints out the value of -5 modulo 2 (e.g., -5%2 in C) in each of the following 4 programming languages: C/C++, Java, Perl, and Python. You will write 4 programs in total. Report what you have found and the reason for this discrepancy. Discuss at least 2 different strategies to cope with such a problem. Hint: think about what can change: developers, compilers, standards, etc.

<h1>Question 2 (15 points)</h1>

Compile program <em>sll buggy.c </em>with the -O0 -g options<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>, execute it with Valgrind, and answer the following questions:

<ul>

 <li>Run Test Case 1 and report the memory problem you find.</li>

</ul>

<em>Paste the Valgrind outputs. </em>Briefly explain the problem. We’ve made a copy of <em>sll buggy.c</em>, renamed to “<em>sll fixed.c</em>”. Fix the bug in “<em>sll fixed.c</em>”, and use comments, e.g. “// Fix for Q2 (a)”, to mark the bug fixes in your program. Explain how you fix this bug in the report. (5 points)

<ul>

 <li>Run Test Case 2 and report the memory problem you find.</li>

</ul>

Briefly explain the problem. Fix the bug in “<em>sll fixed.c</em>”. Use comments, e.g. “// Fix for Q2 (b)”, to mark the bug fixes in your program. Explain how you fix this bug in the report. (5 points)

<ul>

 <li>Generate a test case that would cause a new bug, e.g., a buffer overflow bug.</li>

</ul>

Attach the test case, and briefly explain the problem. Fix the bug in “<em>sll fixed.c</em>”. Use comments, e.g. “// Fix for Q2 (c)”, to mark the bug fixes in your program. Explain how you fix this bug in the report. (5 points)

Note that you only submit <strong>one </strong><em>sll </em><em>fixed.c </em>file with all the fixes. For instructions on downloading Valgrind and installing it, please refer to the tutorial slides. You should do this exercise in Unix/Linux. You may find ‘gdb’ very useful. Our CS Linux machines (madoc.cs.purdue.edu) already have Valgrind installed.

Test Case 1

insert&gt;insert&gt;delete&gt;exit

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:i enter the tel:&gt;100 enter the name:&gt;Tom

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:i enter the tel:&gt;111 enter the name:&gt;Mary

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:d enter the tel:&gt;111

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:x

Test Case 2

insert&gt;insert&gt;insert&gt;edit&gt;delete all&gt;exit

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:i enter the tel:&gt;100 enter the name:&gt;Tom

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:i enter the tel:&gt;111 enter the name:&gt;Mary

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:i enter the tel:&gt;112 enter the name:&gt;John

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:e enter the old tel :&gt;111 enter the <strong>new </strong>tel :&gt;111 enter the <strong>new </strong>name:&gt;Mary

[(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:a [(i)nsert,(d)elete,delete (a)ll,d(u)plicate,(e)dit,(p)rint,e(x)it]:x

<h1>Question 3 (20 points)</h1>

Consider the following (contrived) program:

<strong>class </strong>M { <strong>public static void </strong>main(String [] argv){ M obj = <strong>new </strong>M(); <strong>if </strong>(argv.length &gt; 0) obj.m(argv[0], argv.length);

}

<strong>public void </strong>m(String arg, <strong>int </strong>i) { <strong>int </strong>q = 1; A o = <strong>null</strong>;

Impossible nothing = <strong>new </strong>Impossible(); <strong>if </strong>(i == 0) q = 4; q++; <strong>switch </strong>(arg.length()) { <strong>case </strong>0: q /= 2; <strong>break</strong>; <strong>case </strong>1: o = <strong>new </strong>A(); <strong>new </strong>B(); q = 25; <strong>break</strong>; <strong>case </strong>2: o = <strong>new </strong>A(); q = q * 100; <em>// no break </em><strong>default</strong>: o = <strong>new </strong>B(); <strong>break</strong>;

} <strong>if </strong>(arg.length() &gt; 0) {

o.m();

} <strong>else </strong>{

System.out.println(“zero”); }

nothing.happened();

}

}

<strong>class </strong>A { <strong>public void </strong>m() {

System.out.println(“a”);

}

}

<strong>class </strong>B <strong>extends </strong>A { <strong>public void </strong>m() {

System.out.println(“b”);

} }

<strong>class </strong>Impossible{ <strong>public void </strong>happened() {

<em>// “2b||!2b?”, whatever the answer nothing happens here</em>

}

}

<ul>

 <li>Using the minimal number of nodes (hint: 11), draw a Control Flow Graph (CFG) for method m() and include it in your proj1 sub.pdf. The CFG should be at the level of basic blocks. See the lecture notes on <em>Structural Coverage </em>and <em>CFG </em>for examples.</li>

 <li>List the sets of Test Requirements (TRs) with respect to the CFG you drew in part (a) for each of the following coverages: node coverage; edge coverage; edge-pair coverage; and prime path coverage. In other words, write four sets:</li>

</ul>

<em>TR<sub>NC</sub></em>, <em>TR<sub>EC</sub></em>, <em>TR<sub>EPC</sub></em>, and <em>TR<sub>PPC</sub></em>. If there are infeasible test requirements, list them separately and explain why they are infeasible.

<ul>

 <li>Using q3/TestM-skeleton.java as a starting point, write one JUnit Test Class that achieves, for method m(), each of the following coverages: (1) node coverage but not edge coverage; (2) edge coverage but not edge-pair coverage; (3) edge-pair coverage but not prime path coverage; and (4) prime path coverage. In other words, you will write four test sets (groups of JUnit test functions) in total. One test set satisfies (1), one satisfies (2), one satisfies (3), and the last satisfies (4), if possible. If it is not possible to write a test set to satisfy (1), (2), (3), or (4), explain why. For each test written, provide a simple documentation in the form of a few comment lines above the test function, listing which TRs are satisfied by that test. Consider feasible test requirements only for this part.</li>

</ul>

Our CS Linux machines have JUnit installed (in /homes/cs510/jars/). If you use your own machine, you can get the JUnit jar file here: <a href="https://github.com/junit-team/junit4/wiki/Download-and-Install">https://github.com/junit-team/junit4/wiki/Download-and-Install</a><a href="https://github.com/junit-team/junit4/wiki/Download-and-Install">.</a> JUnit is included in standard Java code development environments such as Eclipse.

<h1>Question 4 (30 points)</h1>

You are to implement and test a class that will construct a partial<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> control-flow graph from the bytecode<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a> of a given Java class using the ASM framework, version 5.2 (<a href="http://asm.ow2.org/">http://asm.ow2.org</a><a href="http://asm.ow2.org/">)</a>. You can download from <a href="https://repository.ow2.org/nexus/content/repositories/releases/org/ow2/asm/asm-all/5.2/asm-all-5.2.jar">https://repository. </a><a href="https://repository.ow2.org/nexus/content/repositories/releases/org/ow2/asm/asm-all/5.2/asm-all-5.2.jar">ow2.org/nexus/content/repositories/releases/org/ow2/asm/asm-all/5.2/asm-all-5.2.jar</a> . If you use CS Linux machines, the jar file is in directory /homes/cs510/jars/. You will also need JUnit for this question.

To illustrate the CFG functionality, consider the following class C:

<strong>public class </strong>C { <strong>int </strong>max(<strong>int </strong>x, <strong>int </strong>y) { <strong>if </strong>(x &lt; y) {

<strong>return </strong>y;

} <strong>else return </strong>x;

}

}

which can be represented in bytecode as (e.g. the output of java -cp path/to/asm/asm-all-5.2.jar org.objectweb.asm.util.Textifier C.class, modified for readability):

<strong>class </strong>C {

Code: max(II)I 0: ILOAD 1

1: ILOAD 2

2: IF_ICMPGE L0

3: ILOAD 2

4: IRETURN

5: L0

6: FRAME SAME

7: ILOAD 1

8: IRETURN }

You can easily draw the corresponding control-flow graph.

<strong>Graph representation of control-flow. </strong>Implement the class CFG to model control-flow in a Java bytecode program. A CFG object has a set of nodes that represent bytecode statements and a set of edges that represent the flow of control (branches) among statements. Each node contains:

<ul>

 <li>an integer that represents the position (bytecode line number) of the statement in the method.</li>

 <li>a reference to the method (an object of objectweb.asm.tree.MethodNode) containing the bytecode statement; and</li>

 <li>a reference to the class (an object of class objectweb.asm.tree.ClassNode) that defines the method.</li>

</ul>

Represent the set of nodes using a java.util.HashSet object, and the set of edges using a java.util.HashMap object, which maps a node to the set of its neighbors. Ensure the sets of nodes and edges have values that are consistent, i.e., for any edge, say from node <em>a </em>to node <em>b</em>, both <em>a </em>and <em>b </em>are in the set of nodes. Moreover, ensure that for any node, say, <em>n</em>, the map maps <em>n </em>to a non-null set, which is empty if the node has no neighbours.

You can find a partial implementation of the CFG class in CFG-skeleton.java. You’ll need to rename it to CFG.java to continue. Your first task is to fill in the implementation of this class. Then you will write JUnit test cases to achieve some coverage criterion.

<ul>

 <li><strong>Adding a node (2 points). </strong>Implement the method addNode such that it creates a new node with the given values and adds it to nodes as well as initializes edges to map the node to an empty set. If the graph already contains a node that is equivalent (under .equals()) to the new node, addNode does not modify the graph.</li>

 <li><strong>Adding an edge (2 points). </strong>Implement the method addEdge such that it adds an edge from the node (p1, m1, c1) to the node (p2, m2, c2). Your implementation should update nodes to maintain its consistency with edges as needed. If the node does not exist in the graph, add the node.</li>

 <li><strong>Deleting a node (4 points). </strong>Implement the method deleteNode such that it deletes a node with the given values, and all edges connected to the node, if any. If the graph does not contain a node that is .equals to the new node, deleteNode does not modify the graph. Your implementation should update nodes to maintain its consistency with edges as needed.</li>

 <li><strong>Deleting an edge (4 points). </strong>Implement the method deleteEdge such that it deletes an edge from the node (p1, m1, c1) to the node (p2, m2, c2).</li>

 <li><strong>Reachability (6 points). </strong>Implement the method isReachable such that it traverses the control-flow graph starting at the node represented by (p1, m1, c1) and ending at the node represented by (p2, m2, c2) to determine if there exists any path from the given start node to the given end node. If the start node or the end node are not in the graph, the method returns false. You must not use recursion for this question.</li>

 <li><strong>Testing (12 points). </strong>I have also provided a class CFGTest in java, which exercises your CFG class. Examine this test class. Does it satisfy NC and EC for each of the method you write? Justify your answer. If it does not satisfy either coverage criterion, write additional JUnit test cases to satisfy one of them. Recall that to run JUnit tests in Junit 4.x, run java org.junit.runner.JUnitCore CFGTest, with the necessary jar and class files on your classpath.</li>

</ul>

<a href="#_ftnref1" name="_ftn1">[1]</a> According to Valgrind’s documentation, “Compile your program with -g to include debugging information so that Memcheck’s error messages include exact line numbers. Using -O0 is also a good idea, if you can tolerate the slowdown. With -O1 line numbers in error messages can be inaccurate, although generally speaking running Memcheck on code compiled at -O1 works fairly well, and the speed improvement compared to running -O0 is quite significant. Use of -O2 and above is not recommended as Memcheck occasionally reports uninitialised-value errors which don’t really exist.”

<a href="#_ftnref2" name="_ftn2">[2]</a> This assignment ignores the labels that are traditionally annotated on nodes and edges, as well as the edges that correspond to method invocations or jsr[ w] bytecodes.

<a href="#_ftnref3" name="_ftn3">[3]</a> <a href="https://docs.oracle.com/javase/specs/jvms/se6/html/VMSpecTOC.doc.html">https://docs.oracle.com/javase/specs/jvms/se6/html/VMSpecTOC.doc.html</a>