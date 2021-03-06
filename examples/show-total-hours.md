---
layout: content
title:  Sum of total hours remaining
category: examples
---
Display a countdown calculating all remining hours to the final date.

<div class="example-base">
  Open till ...
  <span id="clock"></span>
</div>

<script type="text/javascript">
  var twoDaysFromNow = new Date().valueOf() + 2 * 24 * 60 * 60 * 1000;
  $('#clock').countdown(twoDaysFromNow, function(event) {
    var totalHours = event.offset.totalDays * 24 + event.offset.hours;
    $(this).html(event.strftime(totalHours + ' hr %M min %S sec'));
  });
</script>

##### HTML:
{% highlight html linenos %}
<div id="clock"></div>
{% endhighlight %}

##### JS:
{% highlight js linenos %}
$('#clock').countdown("2020/10/10", function(event) {
  var totalHours = event.offset.totalDays * 24 + event.offset.hours;
  $(this).html(event.strftime(totalHours + ' hr %M min %S sec'));
});
{% endhighlight %}
