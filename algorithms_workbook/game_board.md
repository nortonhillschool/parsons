---
layout: default
title: Game board
---

You are making a simple game board. Fill the board with "O" in every cell of a 3×3 array and then print the whole board. Not all blocks are used!

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "array board[3,3]\n" +
    "for row = 0 to 2\n" +
    "    for col = 0 to 2\n" +
    "        board[row, col] = &quot;O&quot;\n" +
    "    next col\n" +
    "next row\n" +
    "print(board[row, col]) #distractor\n" +
    "for i = 0 to 2 #distractor\n" +
    "for i = 0 to 2 #distractor\n" +
    "next i #distractor\n" +
    "next i #distractor\n" +
    "board[col, row] = &quot;O&quot; #distractor\n" +
    "print(board[col, row]) #distractor\n" +
    "board = [3,3] #distractor\n" +
    "board[3,3] #distractor";
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
