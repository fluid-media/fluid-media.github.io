
<title>notes</title>
<!-- <link rel="stylesheet" href="https://acdlite.github.io/jquery.sidenotes/css/main.css"> -->

<!-- https://tscanlin.github.io/tocbot/ -->
<!-- <link rel="stylesheet" href="https://tscanlin.github.io/tocbot/static/css/styles.css" class="next-head"> -->

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/tocbot/4.4.2/tocbot.css">

<link rel="stylesheet" href="lib/styles.css" class=next-head>

<link rel="stylesheet" href="styles/toolkit-styles.css" class="next-head">

<div class="mw7 center dark-gray lh-copy all-content">

<nav class="toc toc-right js-toc relative z-1 transition--300 absolute pa4 is-position-fixed">
</nav>

<div class="content js-toc-content pa4">

<!-- <script -->
<!--   src="https://code.jquery.com/jquery-3.4.1.min.js" -->
<!--     integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=" -->
<!-- 	  crossorigin="anonymous"></script> -->
<!-- <script src="lib/annotator-full.1.2.10/annotator-full.min.js"></script> -->
<!-- <link rel="stylesheet" href="lib/annotator-full.1.2.10/annotator.min.css"> -->
  
# Toward a rich explanatory medium for deep learning models

## TODO

TODO

<!-- <script> -->
<!-- var ann = new Annotator(document.body);  -->
<!-- ann.setupPlugins() -->
<!-- </script> -->

</div>

</div>

<div id="commento"></div>
<script defer src="https://cdn.commento.io/js/commento.js"></script>


<script
  src="https://code.jquery.com/jquery-3.4.1.min.js"
    integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo="
	  crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/tocbot/4.4.2/tocbot.min.js"></script>
<script src="lib/jquery.sidenotes.js"></script>

<script>
 $(() => {
     console.log("ready");

     tocbot.init({
	 // Where to render the table of contents.
	 tocSelector: '.js-toc',
	 // Where to grab the headings to build the table of contents.
	 contentSelector: '.js-toc-content',
	 // Which headings to grab inside of the contentSelector element.
	 headingSelector: 'h1, h2, h3',
	 // For headings inside relative or absolute positioned containers within content.
	 hasInnerContainers: true,
     });

     $(".footnotes").appendTo(".all-content");

     /*      $('.all-content').sidenotes();*/
 });
</script>
