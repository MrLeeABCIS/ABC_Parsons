<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "highest_salary = &quot;X&quot;\n" +
    "salary = &quot;X&quot;\n" +
    "index = 1\n" +
    "num_employees = 4  # Number of employees\n" +
    "while index &lt;= num_employees:\n" +
    "    print(&quot;Enter salary for employee&quot;, index, &quot;:&quot;)\n" +
    "    salary = float(input())  # Get salary input\n" +
    "    if highest_salary == &quot;X&quot;:  # Initialize highest_salary\n" +
    "        highest_salary = salary\n" +
    "    else:\n" +
    "        if salary &gt; highest_salary:  # Update if new salary is higher\n" +
    "            highest_salary = salary\n" +
    "    index = index + 1  # Move to the next entry\n" +
    "print(&quot;The highest salary entered was:&quot;, highest_salary)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 0,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
