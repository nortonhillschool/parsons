---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Arrays lesson task one question one
---
Not all blocks of code are used!

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "for i = 0 to month.length\n" +
    "	temperature[i] = input(&quot;Please enter temperature for &quot; + month[i])\n" +
    "next i\n" +
    "for i = 0 to month.length\n" +
    "	print(month[i] + &quot;: &quot; + temperature[i])\n" +
    "next i\n" +
    "i = i + 1 #distractor\n" +
    "i = i + 1 #distractor\n" +
    "for month in months #distractor\n" +
    "for month in months #distractor\n" +
    "print(temperature[i] + &quot;: &quot; + month[i]) #distractor\n" +
    "temperature = input(&quot;Enter average temperature: &quot;) #distractor";
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
