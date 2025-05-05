---
layout: default
title: Drinks calculator
---

A juice bar sells drinks for £2. Write an algorithm that asks the user how many drinks they want and calculates the total cost.


<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "price = 2\n" +
    "quantity = input(&quot;How many drinks?&quot;)\n" +
    "quantity = int(quantity)\n" +
    "total = price * quantity\n" +
    "print(&quot;Your total is £&quot; + str(total))\n" +
    "price = input(&quot;Enter price per drink&quot;) #distractor\n" +
    "quantity = &quot;How many drinks?&quot; #distractor\n" +
    "total = price ^ quantity #distractor\n" +
    "price = &quot;£2&quot; #distractor\n" +
    "price = &quot;2&quot; #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "sortableTrash"
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
