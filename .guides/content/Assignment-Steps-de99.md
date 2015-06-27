<center><h1>"Seminole Cafe' Order Form"</h1></center>
<ol>
<li>At the bottom of the document, before the closing <code>&lt;/body></code> tag, enter <code>&lt;script></code>, insert a blank line, and then enter <code>&lt;/script></code> to create a new script section.  See below:
<pre>&lt;script>

&lt;/script></pre>
</li>
<li>
Within the script section you created in the previous step, enter the following function:
<pre>// function to add values of selected check boxes and display total
function calcTotal() {
 
}//end of function</pre>
</li>
<li>
Within the function braces, define the following global variables:
<pre>
var itemTotal = 0;
var items = document.getElementsByTagName("input");
</pre>
</li>
<li>
Below the global variables, enter the following <code>for</code> statement:
<pre>
//for loop used to iterate through the checkbox items and if it is checked add all items to find the item total
for (var i = 0; i < 5; i++) {
    if (items[i].checked) {
       itemTotal += (items[i].value * 1);
    }//end of if statement
}//end of for loop
</pre>
</li>

<b><h1>NOTE:</h1></b> ( <code>items[i].value</code>) is multiplied by 1 to ensure that it is treated as a number rather than a string.

<li>
Below the closing <code>}</code> for the <code>for</code> statement, enter the following statement to write the result to the web document:
<pre> document.getElementById("total").innerHTML = "Your order total is $" + itemTotal +".00";</pre>
</li>
<li>
Below the closing <code>}</code> for the function, enter the following code to create an event listner that's compatible with older versions browsers.
<pre>
var submitButton = document.getElementById("sButton");
if (submitButton.addEventListener) {
   submitButton.addEventListener("click", calcTotal, false); 
} 
else if (submitButton.attachEvent)  {
   submitButton.attachEvent("onclick", calcTotal);
}
</pre>
The above code checks if the <code>addEventListener</code> method exists for the button.  If it does, the standard code using the <code>addEventListener</code> method is executed.  If not, the program checks if the <code>attachEvent</code> method exists for the button.  If it does, the older IE-specific <code>attachEvent</code>syntax is used to add an event listener.  If neither of these conditions evaluates to true, then neither is executed.

<b><h1>NOTE:</h1></b> <code>if/else if</code> control statements are commonly used to enhance event listeners so the event listeners are backward-compatible with older browsers.  Although modern browsers have all standardized on the <code>addEventListener</code> method for creating event listeners, Internet Explorer version 8 and earlier used the <code>attachEvent</code> method instead.  You can use an <code>else if</code>  statement to create code that checks if either method is supported in the current browser, and if so, adds an event listener using the correct syntax. 


</li>

<li>Reload the <b>index.htm</b> and view the web page.  Check the <b>Side Salad</b> and <b>Grilled Salmon</b> check boxes, and then click <b>Submit</b>.  The text <b>"Your order total is $19.00"</b> should be displayed on the right side of the page as shown below:</li>
<center><img src=".guides/img/OrderForm_Ex.png" alt="Seminole Cafe" /></center>

<li>Fix any errors in your code until it works as expected!  Use the Browser Developer Tool to troubleshoot.</li>

<center><h1>Congratulations you have completed <br><b>PART 2</b> of Assignment 5!</h1></center>

</ol>











