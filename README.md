# An EchoLab Machine Learning Quest

> Name: Eyrin Kim (`eyrinkim`)

## Question 1: We live in the terminal

1. Fork this repo on your personal Github account. To make life easier, you should consider setting up an [SSH authentication on Gtihub][1].
2. `git clone` your fork to your local computer
3. Change the name on this README file above on your machine. Please get used to work on the terminal, try to use `nano`, `vim`, or `emacs` as a lot of the times VSCode won't be available to you.
4. Push your changes and verify your fork is correctly cloned on your machine.

Now, repeat this process in [Farmshare][2]. You can login using SSH: `<sunetid>@rice.stanford.edu`. You can see more help about Farmshare [here][2].


## Question 2: Image embeddings

Please folow the instructions in the LaTeX document and answer to the question in this Markdown file. Please create a Jupyter notebook for the visualizations/code. You can chose between separate things in modules in your code or add everything to the notebook. We prefer the latter.

Q: Why you think a model performs better than the other one? What is each embedding
capturing?

A: Although there weren't significant differences in perforamce, based on the evaluation, the simpler Image Stats and MOSAIKS models slightly outperform the complex ResNet-SSL4EO model on this task. This suggests that the EuroSAT land cover classes are strongly separable by basic features, which these simpler models capture effectively. The abstract features from the pre-trained ResNet may be too complex to be decoded by a simple linear classifier, especially given that the visualizations display worse delination between image classes for the ResNet model. A key limitation is that I only used 250 images from each class instead of the full dataset due to compute constraints.

Based on the visualizations, which show how well the embeddings cluster by class (each color represent an image class):

1. The Image Stats embedding captures the image's color distribution (mean, std, min, max), more or less separating classes based on their dominant colors.
2. The MOSAIKS embedding captures the image's overall texture by summarizing its response to a bank of random local feature detectors.
3. The ResNet-SSL4EO embedding captures abstract features (e.g., "a building," "a crop field"), which are not easily separable by a linear model, resulting in the poor clustering seen in the visualization.

[1]: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh
[2]: https://docs.farmshare.stanford.edu/
