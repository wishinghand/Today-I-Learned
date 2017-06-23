# Outline all Visible DOM Nodes

Input this into your dev console to see a random colored box around every DOM node on the page you're viewing.

`[].forEach.call(document.querySelectorAll("*"),function(a){a.style.outline="1px solid #"+(~~(Math.random()*(1<<24))).toString(16)})`