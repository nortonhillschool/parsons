---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: EcoGames chatbot
---
Re-arrange the blocks to build your chatbot. Think carefully about what order the blocks should be executed in.

Click <b>Get Feedback</b> when you want to test your answer.

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "print(&quot;Welcome to the EcoGames Chatbot!&quot;)\n" +
    "device = input(&quot;What type of device are you using? (laptop, desktop, phone, tablet&quot;)\n" +
    "if device in (&quot;laptop&quot;, &quot;desktop&quot;):\n" +
    "	print(&quot;Great news! This game is compatible with laptops and desktops&quot;)\n" +
    "elif device in (&quot;phone&quot;, &quot;tablet&quot;):\n" +
    "	print(&quot;Unfortunately, this game is not compatible with phones and tablets&quot;)\n" +
    "else:\n" +
    "	print(&quot;I did not understand. Please type &#039;laptop&#039;, &#039;desktop&#039;, &#039;phone&#039; or &#039;tablet&#039;&quot;)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
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
