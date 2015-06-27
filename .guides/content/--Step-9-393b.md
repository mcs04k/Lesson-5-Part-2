<h1>Step 9 - Add a function to populate the calendar dates with the opposing team names using a for statement</h1>

<ol>
<li>Return to the <b>seminole.js</b> file.</li>

<li>Below the <code>addCalendarDates()</code> function, enter the following code to add a comment and create the structure of a new function named <code>addGameInfo()</code>:
<pre>// function to place day of month value in first p element 
// within each table data cell that has an id 
function addGameInfo() {

}//end of function</pre>
</li>

<li>Within the <code>addGameInfo()</code> function, enter the following statement:
<pre>
var paragraphs = "";
</pre>
This statement creates a variable named <code>paragraphs</code> and sets its value to an empty string.
</li>

<li>
Below the variable declaration, enter the following code:

<pre>
for (var i = 0; i < 31; i++) {</pre> 
This code starts a <code>for</code> loop.  It creates a counter variable named <i> and sets its value to 0.</i>  It specifies the condition <code>i < 31;</code> as long as this condition is satisfied, the <code>for</code> command block will repeat.  Finally, the code i++ increments the <code>i</code> counter variable with each iteration.
</li>

<li>
Within the code block for the <code>for</code> statement, enter the following statement:
<pre>var date = i+1;</pre>
This statement creates a variable called date and assigns a value to it equal to the value of the counter variable, <code>i</code>, plus 1.
</li>

<li>
Below the statement you created in the previous step, enter the following statement:
<pre>var tableCell = document.getElementById("08-" + date);</pre>
This statement creates a variable called <code>tableCell</code> and uses the <code>getElementById()</code> method to set its value to the element with an <code>id</code> value that starts with 08- followed by the value of <code>i</code>.
</li>
<li>
Below the statement you created in the previous step, enter the following statement:
<pre> paragraphs = tableCell.getElementsByTagName("p");</pre>
This statement uses the <code>getElementByTagName</code> method to look up all <code>p</code> elements within the current cell and stores the values as an array in the <code>paragraphs</code> variable.
</li>

<li>
Below the statement you created in the previous step, enter the following statement:
<pre> paragraphs[1].innerHTML += opponents[i];</pre>
This statement fetches the value in the <code>opponents</code> array whose index matches the current value of the counter variable <code>i</code>, and assigns its value as the content of the second paragraph (numbered 1) in the current cell. 
</li>

The following shows the <b>completed</b> code for the <code>addGameInfo()</code> function:
<pre>
function addGameInfo() {
   var paragraphs = "";
   for (var i = 0; i < 31; i++) {
      var date = i+1;
      var tableCell = document.getElementById("08-" + date);
      paragraphs = tableCell.getElementsByTagName("p");
      paragraphs[1].innerHTML += opponents[i];
   }
}
</pre>
</li>
<li>
Within the <code>setUpPage()</code> function, before the closing <code>}</code>, add the statement <b>addGameInfo();</b> so your <code>setUpPage()</code> function matches the following:
<pre>
// function to populate calendar 
function setUpPage() {
   addColumnHeaders();
   addCalendarDates();
   addGameInfo();
}
</pre>
Calling the <code>addGameInfo()</code> function ensures that the calendar is populated with opponent information when the page is loaded</li>
<li>Reload the <b>calender.htm</b> and view the web page.  As you can see, the table cells should now contain the name of each day's opponent, or "(off)" if no opponent is scheduled.</li>


<center><img src=".guides/img/SeminoleTrojan_Opponents.png" alt="Seminole Trojans" /></center>

<center><h1>Congratulations you have completed PART 1 of Assignment 5!</h1></center>