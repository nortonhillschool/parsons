---
layout: default
title: Odd or even
---

Ask the user for a number and print whether it's even or odd.

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "num = input(&quot;Enter a number&quot;)\n" +
    "num = int(num)\n" +
    "if num MOD 2 == 0 then\n" +
    "    print(&quot;Even&quot;)\n" +
    "else\n" +
    "    print(&quot;Odd&quot;)\n" +
    "endif\n" +
    "if num DIV 2 == 0 then #distractor\n" +
    "if num / 2 == 0 then #distractor\n" +
    "if num // 2 == 0 then #distractor\n" +
    "end #distractor";
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
