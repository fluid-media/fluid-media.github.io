
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

## The idea

Literate deep learning

no results for “literate deep learning” “literate machine learning”

Toward a rich explanatory medium for deep learning models

but hear me out—executable documentation explaining visually how machine learning models work, with references to the real model running in the browser. 

This has input-output examples, math notation, prose, and pictures — for ~people~ — and linking that to the runnable code

Like, can we make something as good as the mathigon environment but for machine learning models (or hi-assurance models) (running in the browser) https://mathigon.org/course/fractals/introduction

IDEAL DEMO: TODO

## Motivation and applications

I’m actually thinking something like these NIST high-assurance specs, or other documents that vendors provide. People HAVE TO WRITE IT
https://csrc.nist.gov/publications/detail/sp/800-90a/archive/2012-01-23 

how do people do algorithmic accountability stuff, like, now, how does the government audit

this could be good for hi-assurance executable specs for legislation, etc? the point is that the domain has its own domain-specific language of biases, weights, layers, inputs, outputs, etc. that can be modeled in a DSL?

strong positive signal from angela — seems super necessary, etc.

## Related work

This is not for figuring out why your model isn’t doing the thing it was supposed to do. 
This is not for debugging or making models or transparency, this is for explaining and referring to an existing model. 

This is not a computational notebook (e.g. colab or jupyter), which is for really running and building the thing. 

- distill colab nb https://colab.research.google.com/github/tensorflow/lucid/blob/master/notebooks/activation-atlas/activation-atlas-simple.ipynb
- See in this notebook, they still put in pictures and notation. Also Q&A format?
http://d2l.ai/chapter_multilayer-perceptrons/mlp-scratch.html#the-loss-function
- https://colab.research.google.com/github/d2l-ai/d2l-en-colab/blob/master/chapter_convolutional-neural-networks/pooling.ipynb#scrollTo=Ql_gtyIxNkJO

This is not Dan Amelang's thing, which is great but is for really modeling industrial-strength NNs.

- of course, dan amelang’s work is the closest https://app.reduct.video/e/the-dynamic-media-dream-e4ed367417-4d5acec7aeed995cf021/

This is not a visual environment for making ML models, like Runway or Lobe.

- https://runwayml.com/
- sony NN console https://dl.sony.com/console/#/project
https://support.dl.sony.com/docs/tutorial-training-using-a-sample-project/

This is not a neural network playground.

- Obviously super related https://playground.tensorflow.org/#activation=tanh&batchSize=10&dataset=circle&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=4,2&seed=0.05915&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false

This is not model cards or datasheets for datasets!

- Model cards (fat* ’19) https://arxiv.org/pdf/1810.03993.pdf
- Datasheets for datasets (workshop on FATML, ’18) https://www.microsoft.com/en-us/research/uploads/prod/2019/01/1803.09010.pdf

This is not an architecture visualization library

- People still can’t draw diagrams https://datascience.stackexchange.com/questions/14899/how-to-draw-deep-learning-network-architecture-diagrams
https://github.com/ashishpatel26/Tools-to-Design-or-Visualize-Architecture-of-Neural-Network

This is not a neural network textbook or journal article.
obviously distill does it well (like the conv net windows)—but those aren’t explainers to technical people? more like research papers?

- idyll has some nice work on explainers: https://idyll-lang.org/gallery/the-beginner-s-guide-to-dimensionality-reduction

## Research questions and challenges

Questions

- TODO

Challenges

- TODO

## Technical next steps

can we explain tf.js demos? https://www.tensorflow.org/js/demos

https://github.com/tensorflow/tfjs-models/blob/master/posenet/src/posenet_model.ts

https://github.com/tensorflow/tfjs-models/blob/master/knn-classifier/demo/index.js

Are there already specs for high-assurance algos https://ainowinstitute.org/aap-toolkit.pdf

does tf.js have a tensorboard equivalent? 

I mean, at this point, you need to really be able to understand and explain the models yourself? 

Who has done this by hand, but really well?

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
