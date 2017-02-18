---
layout:      post
title:       Python cheatsheet
description: This is a cheatsheet created during my endaevor to learn scientific python computing
date:        2017-02-15 16:16:01 -0600
categories:  python scientific
---

# {{ page.title }}

[back]({{ site.baseurl }}/)

python_cheatsheet.html

<div id="includedContent"></div>
<script>
  $.ajax({
    url: "{{ site.url }}{{ site.baseurl }}/resources/evernote/python_cheatsheet.html",
    cache: false,
    dataType: "html",
    success: function(data) {
      $("#includedContent").html(data);
    }
  });
</script>
