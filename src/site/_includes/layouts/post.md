---
layout: layouts/base.njk
pageClass: posts
templateEngineOverride: njk, md
---

<!-- <h1>{{ title }}</h1>
<p class="date">
  Posted as an example, on <time datetime="{{ date }}">{{ date | dateDisplay }}</time>
</p>
<main>
  {{ content | safe }}
  <div class="footnote">
    <p>
      This page is part of the posts section.
    </p>
  </div>
</main> -->


<!doctype html>
<html>
<head>
<script type="text/javascript" src="http://code.jquery.com/jquery-1.7.1.min.js"></script>
<script type="text/javascript" src="../../turn.min.js"></script>

<style type="text/css">
body{
	background:#ccc;
}
#magazine{
	width:1152px;
	height:752px;
}
#magazine .turn-page{
	background-color:#ccc;
	background-size:100% 100%;
}
</style>
</head>
<body>

<div id="magazine">
	<div style="background-image:url(pages/01.jpg);"></div>
	<div style="background-image:url(pages/02.jpg);"></div>
	<div style="background-image:url(pages/03.jpg);"></div>
	<div style="background-image:url(pages/04.jpg);"></div>
	<div style="background-image:url(pages/05.jpg);"></div>
	<div style="background-image:url(pages/06.jpg);"></div>
</div>


<script type="text/javascript">

	$(window).ready(function() {
		$('#magazine').turn({
							display: 'double',
							acceleration: true,
							gradients: !$.isTouch,
							elevation:50,
							when: {
								turned: function(e, page) {
									/*console.log('Current view: ', $(this).turn('view'));*/
								}
							}
						});
	});
	
	
	$(window).bind('keydown', function(e){
		
		if (e.keyCode==37)
			$('#magazine').turn('previous');
		else if (e.keyCode==39)
			$('#magazine').turn('next');
			
	});

</script>

</body>
</html>
