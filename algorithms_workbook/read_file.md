---
layout: default
title: Reading all lines
---

Write an algorithm to open a file called "data.txt", read every line in the file, and print each line to the screen. Then close the file.

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "myFile = open(&quot;data.txt&quot;)\n" +
    "while NOT myFile.endOfFile()\n" +
    "    line = myFile.readLine()\n" +
    "    print(line)\n" +
    "endwhile\n" +
    "myFile.close()\n" +
    "myFile = newFile(&quot;data.txt&quot;) #distractor\n" +
    "line = input(&quot;Enter a line&quot;) #distractor\n" +
    "myFile.close #distractor\n" +
    "if myFile.endOfFile() == False then #distractor\n" +
    "endif #distractor";
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
