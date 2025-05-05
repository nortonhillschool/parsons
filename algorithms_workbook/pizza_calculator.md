---
layout: default
title: Pizza calculator
---

A group of friends have a pizza that has been cut into 8 slices. Create a program that takes as an input the number of friends in the group and calculates how many whole slices they can each have.

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "group_size = input(&quot;How many people are in the group?&quot;)\n" +
    "group_size = int(group_size)\n" +
    "slices = 8 DIV group_size\n" +
    "slices = str(slices)\n" +
    "print(&quot;Each person can have &quot; + slices)\n" +
    "slices = group_size DIV 8 #distractor\n" +
    "group_size = &quot;How many people are in the group?&quot; #distractor\n" +
    "input(&quot;How many people are in the group?&quot;) #distractor\n" +
    "slices = 8 / group_size #distractor\n" +
    "slices = group_size / 8 #distractor\n" +
    "slices = 8 MOD group_size #distractor\n" +
    "slices = group_size MOD 8 #distractor";
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
