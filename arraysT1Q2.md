---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Arrays lesson task one question two
---

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "array months[12]\n" +
    "months =  [&quot;January&quot;, &quot;February&quot;, &quot;March&quot;, &quot;April&quot;, &quot;May&quot;, &quot;June&quot;, &quot;July&quot;, &quot;August&quot;, &quot;September&quot;, &quot;October&quot;, &quot;November&quot;, &quot;December&quot;]\n" +
    "array rainfall[12]\n" +
    "annualRainfall = 0\n" +
    "for i = 0 to month.length\n" +
    "    	rainfall[i] = int(input(&quot;Please input rainfall  for month &quot;, 				                  months[i]))\n" +
    "    	annualRainfall = annualRainfall + rainfall[i]\n" +
    "next i\n" +
    "averageRainfall = annualRainfall / 12\n" +
    "monthsAboveAverage = 0\n" +
    "for i = 0 to month.length\n" +
    "	if rainfall[i] &gt; averageRainfall\n" +
    "		monthsAboveAverage = monthsAboveAverage + 1 \n" +
    "	endif  \n" +
    "    print(months[i] + &quot;: &quot; + str(rainfall[i]))\n" +
    "next i\n" +
    "print(annualRainfall)\n" +
    "print(monthsAboveAverage)";
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
