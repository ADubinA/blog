---
layout: post
title: "WGANs and sheep"
date: 2017-12-11 10:10:13 -0700
comments: true
---

<a href = "https://en.wikipedia.org/wiki/Generative_adversarial_network" > GAN</a> or generative adversarial network, is a concept by Ian Goodfellow discussed in his article in 2014. The algorithm involve two neural networks in playing a <a href = "https://en.wikipedia.org/wiki/Non-cooperative_game_theory"> non- cooperative game</a>, untill a <a href = "https://en.wikipedia.org/wiki/Nash_equilibrium" >a Nash equilibrium</a> is achieved. the two neuron networks are named <i> generator</i> and <i>discriminator</i>.
GANs are increasing in popularity nowadays. We have seen GANs <a href = "https://arxiv.org/abs/1708.08227" >Creating new drugs</a> , <a href = "https://arxiv.org/abs/1709.06298" > generating new music</a> and more. For an updating list, one should refereed to <a href="https://github.com/nightrome/really-awesome-gan" > nightrome's Github </a>.

Today I implemented myself a variation of GAN, with a <a href = "https://en.wikipedia.org/wiki/Convolutional_neural_network">convolution architecture</a>. The goal is to recreate art from a very small data set. I acquired from Google 150 images of painting by <a href = "https://en.wikipedia.org/wiki/Menashe_Kadishman" >Menashe Kadishman</a> with the goal to recreate his famous sheep paintings. Doing so with Tensorflow is a trivial task. With only 200 lines of code, that took 2 hours of work I achieved results. When I executed the code on the GPU, I discovered the main issue with GAN. GAN are notorious hard to train, and the loss function of both NN had no clear convergence.

To eliminate to some degree this, we use WGAN. That is, using the <a href= "https://en.wikipedia.org/wiki/Wasserstein_metric"> Wasserstein metric </a> as the loss function. This improved the convergence traumatically. After 5000 epoch, using my hyper-parameters from <a href = "https://julianzaidi.wordpress.com/2017/04/24/deep-convolution-gan-dcgan-architecture-and-training/" >Julianzaidi's blog</a> I achieved results.

[picture is removed due to copyright claims]. 

After showing my results, a fiend proposed that showing the result of my work could be copyright infringement. I'm currently in contact with Kadishman copyrighter, and when I will get the permission, I will re-upload my results. Although I can't upload my work, I can upload my code and the learned structure. It will be available on my Github.
I believe that I should research more on the field, I as a human can still easily differentiate between the generator's creation, and Kadishman's real work. Tomorrow I will try to implement a variation of WGAN named <i>WGAN-GP</i>, more on that in the next post.  