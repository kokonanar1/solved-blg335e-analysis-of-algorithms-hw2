Download Link: https://assignmentchef.com/product/solved-blg335e-analysis-of-algorithms-hw2
<br>
<strong>Homework Policy </strong>

<ul>

 <li>Use comments whenever necessary to explain your code. Also, <strong>write your name on top of each file you are sending in comment!</strong></li>

</ul>




<ul>

 <li>Do not forget to handle exceptions and print error messages!</li>

</ul>




<ul>

 <li>Your code must be written in C++, and should be able to be compiled and run using g++ compiler. ITU servers provide g++ compiler, you can test your program by connecting to the servers using ssh (if you don’t know how to do it, <a href="http://www.eskibidb.itu.edu.tr/?d=165">click here</a><a href="http://www.eskibidb.itu.edu.tr/?d=165">)</a>.</li>

</ul>




<ul>

 <li>Your program must take the name of the file that contains events (<strong>see homework description for events file format</strong>) from the <strong>command line</strong>. Therefore, it must be executed as follows:</li>

</ul>




<h1><strong>./your_executable_file  events_file_name </strong></h1>

<strong> </strong>

<ul>

 <li>Your program must produce <strong>output exactly same as defined in the homework description below</strong>. <strong> </strong></li>

</ul>

<strong> </strong>




<strong>Problem Description </strong>

<strong> </strong>

In this homework, you are asked to implement an event-scheduler as a MIN-HEAP. A file keeps a list of events with the following format:




<h1>EVENT-NAME START-TIME END-TIME</h1>




where EVENT-NAME is the name of the event, START-TIME is the scheduling time of the event and END-TIME is the finishing time of the event. Following is an example <strong>events.txt</strong> file which consists of three events: EVENT-A which starts at time 2 and ends at time 4, EVENT-B which starts at time 5 and ends at time 7, and EVENT-C which starts at time 4 and ends at time 5.

events.txt

<table width="174">

 <tbody>

  <tr>

   <td width="107">EVENT-A</td>

   <td width="36">2</td>

   <td width="31">4</td>

  </tr>

  <tr>

   <td width="107">EVENT-B</td>

   <td width="36">5</td>

   <td width="31">7</td>

  </tr>

  <tr>

   <td width="107">EVENT-C</td>

   <td width="36">4</td>

   <td width="31">5</td>

  </tr>

 </tbody>

</table>

The event scheduler starts by reading the list of events from an event file <strong>whose name is supplied as a command line parameter, as mentioned in homework policy section</strong>. Event scheduler creates an event MIN-HEAP using the firing times of the events as keys. Note that, each listed event in the events file produces two events: (1) an event at the start time and (2) an event at the end time. Therefore, the heap nodes must store event type, either start or end, as well as the event name. An event MIN-HEAP for the given example file is as follows:







There is a virtual clock in the system which starts from 0 and ticks by 1 time unit. At each clock tick, event scheduler checks the top event in MIN-HEAP to see whether there is a scheduled event at that time or not:




<ul>

 <li>If there is no scheduled event for that time, the program prints out:</li>

</ul>




<h1>TIME <strong>T</strong>: NO EVENT</h1>

where <strong>T</strong> is the current time.




<ul>

 <li>If there is a START event for the scheduled time, then the program prints out:</li>

</ul>




<h1>TIME <strong>T</strong>: <strong>EVENT-NAME</strong> STARTED</h1>

where <strong>T</strong> is the current time and <strong>EVENT-NAME</strong> is the name of the event. Afterwards, the event is removed from the event MIN-HEAP.




<ul>

 <li>If there is an END event for the scheduled time, then the program prints out:</li>

</ul>




<h2>TIME T: EVENT-NAME ENDED</h2>




where <strong>T</strong> is the current time and <strong>EVENT-NAME</strong> is the name of the event. Afterwards, the event is removed from the event MIN-HEAP.




Please note that, there may be more than one events scheduled for the same time (e.g., both EVENT-A END and EVENT-C START events are scheduled for time 4 in the example above). Therefore, you have to check heap till the scheduling time on top of the event MIN-HEAP becomes larger than the current time.







<strong>Program Run and Output for The Given Example</strong>




At time T = 1, there is no scheduled event. Therefore, the program prints out:




<h1>TIME 1: NO EVENT</h1>




The clock ticks and at time T=2, there is a scheduled START event on the top of the event MIN-HEAP. Therefore, the program prints out:




<h1>TIME 2: EVENT-A STARTED</h1>




Then, the node is removed from the heap and heap becomes:




The top element has a scheduled time 4, which is larger than the current time T=2. Therefore, the clock ticks to the next time, i.e., T=3.




At time T=3, there is no scheduled event. Therefore, the program prints out:




<h1>TIME 3: NO EVENT</h1>




The clock ticks and at time T=4, there is a scheduled END event on the top of the MIN-HEAP. Therefore, the program prints out:




<h1>TIME 4: EVENT-A ENDED</h1>




Then, the node is removed from the heap and heap becomes:







The top element has a scheduled time 4, which is equal to the current time T=4. Therefore, the program prints out:

<h1>TIME 4: EVENT-C STARTED</h1>




Then, the node is removed from the heap and heap becomes:




The top element has a scheduled time 5, which is larger than the current time T=4. Therefore, the clock ticks to the next time, i.e., T=5.




At time T=5, the top element has a scheduled time 5, which is equal to the current time. Therefore, the program prints out:




<h1>TIME 5: EVENT-C ENDED</h1>




Then, the node is removed from the heap and heap becomes:







The top element has a scheduled time 5, which is equal to the current time T=5. Therefore, the program prints out:

<h1>TIME 5: EVENT-B STARTED</h1>




Then, the node is removed from the heap and heap becomes:




7

EVENT-B

END




The top element has a scheduled time 7, which is larger than the current time T=5. Therefore, the clock ticks to the next time, i.e., T=6.




At time T=6, there is no scheduled event. Therefore, the program prints out:




<h1>TIME 6: NO EVENT</h1>




The clock ticks and at time T=7, there is a scheduled END event on the top of the MIN-HEAP.

Therefore, the program prints out:




<h1>TIME 7: EVENT-B ENDED</h1>




Then, the node is removed from the heap and heap becomes empty.




Since the MIN-HEAP is empty, all the events are scheduled. The program prints out:




TIME 7: NO MORE EVENTS, SCHEDULER EXITS




Afterwards, the program exits gracefully since there is no more events and the user is informed!

























<h1><strong>Submission </strong></h1>

<strong> </strong>

Submit your homework files through Ninova. Please zip and upload all your files. You are going to submit the following files:




<ul>

 <li>All your .h (if any) and .cpp files</li>

</ul>




<ul>

 <li>A .pdf file as your report. Your report should be clear and detailed. Otherwise, it may result in a grade loss for you.</li>

</ul>




<ul>

 <li>A .txt file explaining how to compile and run your code (in a 1 or 2 line)</li>

</ul>




Use your student ID as file names. That is, <strong>your_student_id.zip</strong> for the .zip file,<strong> your_student_id.cpp</strong> for the main C++ source file and <strong>your_student_id.pdf</strong> for the report.