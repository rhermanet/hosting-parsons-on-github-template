---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

## Parsons 1 (Line Based Grader)
Re-arrange the blocks below so they print out "Hello World!"

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "public static void main(String[]args){\n" +
    "	System.out.println(&quot;Hello World!&quot;);\n" +
    "}\n" +
    "print(&quot;Hello World!&quot;);\n" +
    "System.out.println(Hello World!&quot;);";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en"
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


## Parsons 2 (Variable Check Grader)


### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)
