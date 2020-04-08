<title>deepdocs</title>
<!-- <link rel="stylesheet" href="https://acdlite.github.io/jquery.sidenotes/css/main.css"> -->

<!-- https://tscanlin.github.io/tocbot/ -->
<!-- <link rel="stylesheet" href="https://tscanlin.github.io/tocbot/static/css/styles.css" class="next-head"> -->

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/tocbot/4.4.2/tocbot.css">

<link rel="stylesheet" href="lib/styles.css" class=next-head>

<link rel="stylesheet" href="styles/toolkit-styles.css" class="next-head">

<div class="mw7 center dark-gray lh-copy all-content">

<nav class="toc toc-right js-toc relative z-1 transition--300 absolute pa4 is-position-fixed">
</nav>

<script
  src="https://code.jquery.com/jquery-3.4.1.min.js"
    integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo="
	  crossorigin="anonymous"></script>

<!-- <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script> -->
<script src="lib/comments/inlineDisqussions.js"></script>
<link rel="stylesheet" type="text/css" href="lib/comments/inlineDisqussions.css" />

<div class="content js-toc-content pa4">

<!-- <script -->
<!--   src="https://code.jquery.com/jquery-3.4.1.min.js" -->
<!--     integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=" -->
<!-- 	  crossorigin="anonymous"></script> -->
<!-- <script src="lib/annotator-full.1.2.10/annotator-full.min.js"></script> -->
<!-- <link rel="stylesheet" href="lib/annotator-full.1.2.10/annotator.min.css"> -->
  
# DeepDocs: Toward a rich explanatory medium for deep learning models

## Proposal

It's critically important for people to understand how algorithms work, and in particular, how deep learning algorithms work. Not only is it important for technically-minded people like model developers and model users (e.g. data scientists and UI designers), it's important for general scientific literacy. As ML algorithms come to be embedded in more of the fabric of daily life, it's important to provide clear specifications and documentation of these models at a high level, from human to human. A policy expert, lawmaker, judge, activist, or member of the public should have the right to read the documentation of an machine learning algorithm deployed by the government that might make decisions concerning their daily lives, such as food stamp allocation or bail decisions. It is also particularly important to make it easier to document deep learning algorithms given their popular conception as "black boxes" or "AI magic."

The idea to document important algorithms is not novel; the NIST standards agency (part of the US government) has released human-readable specifications of high-assurance cryptography primitives, and the W3C (an international consortium) releases human-readable documentation of Web standards. However, the tool support for creating such rich documentation is lacking. To _explain_ an algorithm means centering all the modalities that people use: first, prose, examples, and pictures, and then mathematical notation and pseudocode; to understand a system, any technical person will read the code last. But centering prose and pictures, as in a conventional explanation, means losing the context of the algorithm; any technical person will bemoan the difficulty of figuring out what prose is referring to, the ambiguity of prose, and the irritation of having to read code in a "dead" document that has already gone out of sync with an implementation. 

Clearly, what is needed is a hybrid medium that centers all of these modalities of technical explanation. One promising start at such as medium is the emergent genre of computational notebooks, yet the notebook medium is well-known for its tension between exploration and explanation; most notebooks end up as a messy series of code-centric experiments where the author doesn't know what's going on, much less the reader. Toward creating this new medium for deep technical explanation, this project proposes several research hypotheses: 

*Hypothesis 1*: Providing a rich explanatory medium for deep learning models will make it easier for experts to author documentation of models. This documentation will be easier for technically-minded laypeople to understand and to verify.

*Hypothesis 2*: We can design an environment for authoring rich, executable, visual documentation linked directly to the math and code for a real machine learning model, running in the browser.

*Hypothesis 3*: Our particular design of this new medium will, in fact, both improve the authoring experience for authors and result in more helpful artifacts for readers.

Such a project has the potential to provide the basis for clear human-to-human communication and specification of deep learning algorithms, enabling these crucial algorithms to be more clearly understood, audited, and edited by domain experts and by an interested member of the public.

Such a medium would include first-class support for the following _explanatory, narrative_ modalities at a static, generic specification level:

- prose
- concrete examples, e.g. input-output pairs
- math notation
- pseudocode
- diagrams, e.g. pictures of model architectures
- plots, e.g. visualization of the loss function
- references and deeplinks to the model that link several representations (prose, math, picture, code)

It might include support for specific iterations:

- visualizing specific trained networks (with specific parameters) and specific datasets, and the performance or failures of these models
- running the loss function

It may include support for the following modalities at a dynamic level:

- the ability to run examples in the browser (e.g. code snippets or inference)
- the ability to visualize and document the training process (optimization)

*Hypothesis 2* (that designing this environment is a tractable problem) is likely to be true because the domain of deep learning has its own very domain-specific language of biases, weights, layers, inputs, outputs, etc. that can be modeled in a domain-specific language or annotations. (Also, we have expertise in domain-specific language design, making diagrams, interface design, data science, explaining machine learning models, etc.)

The ideal demo (or teaser figure) for such a medium looks like this:

- A video showing the authoring experience for documenting an existing realistic tensorflow.js model (e.g. for computer vision): the environment puts all the parts of the model into a "visual vocabulary" that the author can draw from, and the author, as they write, can seamlessly make references to the code and link it to the mathematics of the model and a diagram of the model
    - A user study on authors asking them to document the model with inline code comments, vs. a colab notebook, vs. a separate page (PDF or web), vs. this environment, asking them which experience they preferred. Plus, results from the authors, saying that this authoring experience was (ideally) faster, easier, and produced better results
    - A video showing the editing experience for the model, where any edit to the model is automatically propagated to the documentation OR is flagged if it breaks some invariant in the documentation
- The final document, compared side-by-side to 1. the other docs that authors made in-environment and out-of-environment, showing that the final doc written in this env is clearly richer and linked directly to the code, and 2. other docs that people have made by hand (not in this study) are clearly ad-hoc and worse. 
    - A reader study asking technically-proficient laypeople which documentation they preferred, and possibly a test to see which documentation they learned more from reading, ideally showing that these docs are better.

(TODO: Make a mockup of the authoring experience, reading experience, and sample documentation for real ML models.)

The idea is a combination of a couple of main pieces of related work:

- Rich, dynamic environments for learning mathematics: can we make something as good as the [Mathigon environment for learning about fractals](https://mathigon.org/course/fractals/introduction) but for machine learning models? Note the deeplinking, interactivity, etc. 
- Linking many representations of deep learning models as in [Dan Amelang's work on executable neural network visual representations](https://app.reduct.video/e/the-dynamic-media-dream-e4ed367417-4d5acec7aeed995cf021/)
- [Model cards](https://arxiv.org/pdf/1810.03993.pdf) that document a model's details, purpose, intended use, evaluation factors, success metrics, training and evaluation data, ethical considerations, caveats and recommendations, and dataviz of errors (false positives, negatives, etc.)
- [Government specifications for high-assurance algorithms](https://csrc.nist.gov/publications/detail/sp/800-90a/archive/2012-01-23 ) as in cryptography, which provide a high-level spec comprising math, pseudocode, input-output examples, diagrams, properties the model should satisfy, invariants, etc. but in a very loose and ad-hoc manner that has caused implementation bugs in the past 
- Existing rich documentation for models, such as technical explainer articles (e.g. in _Distill_) or computational notebooks (which support some level of prose and interactivity, but are notoriously terrible for explanation)

The idea is to make a real environment for creating "model cards" to make models more easily understandable and auditable to a lay technical audience, keeping this documentation tightly linked to the code, so it's easier to understand and doesn't go out of sync. (Another idea is to just let people write the specification and synthesize the model from that--but that seems hard.)

The things that are out of scope for this project are the things that are out of scope for any piece of technical documentation, including:

- The ability to develop new model architectures, as in a computational notebook or dev environment.
- The ability to perform training, inference, or evaluation.
- The ability to debug models or debug datasets, as in a model development environment.
- Any research technique for ensuring "fairness, accountability, and transparency," especially those that are specialized to models for particular purposes or with specific architectures.

## Research points to consider

Questions

- Pain points: How can we make an authoring environment for explaining deep learning models that is most useful for authors; e.g. what are they trying to say or do that existing tools don't support well? 
- Pain points: How can we design an explanatory medium for deep learning models that is most useful for readers; e.g. what are they trying to learn or do that existing artifacts don't support well?
- What are the right authoring primitives for a computational medium for _explanation_? 
- What are the right domain primitives to provide for the domain of deep learning, and at what level of abstraction?
- Should we do a formative study, and if so, who can we interview? Who should we recruit for an evaluation study?
- What affordances might we provide for automatically documenting a model, or else taking as much of the burden as possible off the author?

Challenges

- Is the approach interesting to the wider ML community? e.g. Are questions of design, training/evaluation/inference, data, or FATML just more important to the community? Do they care about specification/explanation/documentation? Is that demo going to blow people away?
- Is the approach interesting to the wider HCI or PL community? e.g. Are questions of model deployment or verification more interesting to them?
- Engineering: Can we build this medium in the browser on tensorflow.js?
- How does tf.js model deep learning models, and is it the right level of abstraction for us (as designers/implementers)?
- What models would we be documenting as examples? Are those compelling and at the right level of difficulty to convince people that this is not a toy?

Contributions

- TODO: To come. (The contributions would be answers to the research questions above.)

Opportunities

- It would be really cool to integrate this project as documentation of real production models at MS or somewhere in the public sector.
- If the project works, there are many interesting opportunities to extend it from "static" documentation to "dynamic" documentation, e.g. it lives with the model and changes with it; it documents the running model and not just the program.

## Related work

The idea for this project is *not* to provide what any of the projects below provide, but they are all certainly related.

### Making models

Tensorflow, etc.

### Model debugging

Projects for debugging models, figuring out why your model isn’t doing the thing it was supposed to do, model transparency.

- GANvis, etc.
- Transparency techniques

### Computational notebooks

Notebooks are well-known for being caught between exploration and explanation. 

Some notebook software is Colab, Jupyter, Observable, etc. Some specific examples of notebooks:

- Distill colab notebook for [activation atlas article](https://colab.research.google.com/github/tensorflow/lucid/blob/master/notebooks/activation-atlas/activation-atlas-simple.ipynb)
- [Notebook from d2l.ai textbook on MLP](http://d2l.ai/chapter_multilayer-perceptrons/mlp-scratch.html#the-loss-function). In this notebook, they still put in pictures and notation to explain the model.
- [Notebook from d2l.ai textbook on pooling](https://colab.research.google.com/github/d2l-ai/d2l-en-colab/blob/master/chapter_convolutional-neural-networks/pooling.ipynb#scrollTo=Ql_gtyIxNkJO)

### Visual environments for creating models

- [Dan Amelang's work on executable neural network visual representations](https://app.reduct.video/e/the-dynamic-media-dream-e4ed367417-4d5acec7aeed995cf021/) (very related)
- [Runway](https://runwayml.com/)
- [Lobe](http://lobe.ai/)
- [Sony neural network console](https://dl.sony.com/console/#/project)
    - [docs](https://support.dl.sony.com/docs/tutorial-training-using-a-sample-project/)

### Neural network playgrounds

- [tensorflow playground](https://playground.tensorflow.org/#activation=tanh&batchSize=10&dataset=circle&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=4,2&seed=0.05915&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false)

### Model documentation

- [Model cards](https://arxiv.org/pdf/1810.03993.pdf) (FAT* '19) (very related)
- [Datasheets for datasets](https://www.microsoft.com/en-us/research/uploads/prod/2019/01/1803.09010.pdf) (workshop on FATML ’18) 

### Neural network architecture visualization libraries

- Tensorboard
- [stackexchange question](https://datascience.stackexchange.com/questions/14899/how-to-draw-deep-learning-network-architecture-diagrams)
- [GitHub repo of examples](https://github.com/ashishpatel26/Tools-to-Design-or-Visualize-Architecture-of-Neural-Network)

### Neural network textbook chapters, journal articles, explainers

- Distill
- Apple Machine Learning Journal
- Deep Learning Book
- d2l.ai
- [Idyll, Beginner's guide to PCA](https://idyll-lang.org/gallery/the-beginner-s-guide-to-dimensionality-reduction)

## Next steps

Is someone already working on this?

- Maybe at MSR?
- friend with domain expertise seems very excited about the idea and it doesn't seem to exist yet

Look into pain points and formative studies?

Are there already specs for high-assurance algos? 

- [maybe the algorithmic accountability people know of some](https://ainowinstitute.org/aap-toolkit.pdf)
- friend says "nyc is notoriously cagey about their automated decision systems to a suppression extent, so no depending on the agency"

Who has done this by hand, but really well or poorly?

- model zoo has some [example model docs](https://modelzoo.co/model/yolo-tensorflow)

Can we explain tensorflow.js demos? 

- [tf.js demos](https://www.tensorflow.org/js/demos)
- [posenet ts code](https://github.com/tensorflow/tfjs-models/blob/master/posenet/src/posenet_model.ts)
- [knn-classifier ts code](https://github.com/tensorflow/tfjs-models/blob/master/knn-classifier/demo/index.js)
- [tf.js tensorboard](https://js.tensorflow.org/api_node/1.1.0/#node.tensorBoard)

Is there some way to scope this down, or stage the work?

</div>

</div>

<script>
disqus_shortname = 'fluid-media';
jQuery(document).ready(function() {
jQuery("p").inlineDisqussions({
identifier: 'disqussion',
displayCount: true,
highlighted: false,
position: 'right',
background: 'white',
maxWidth: 9999
});
});
</script>
	<!-- jQuery("p").inlineDisqussions(); -->

<!-- <div id="commento"></div> -->
<!-- <script defer src="https://cdn.commento.io/js/commento.js"></script> -->


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
