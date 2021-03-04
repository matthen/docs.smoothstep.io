---
layout: page
title: Tutorial
permalink: /tutorial/
nav_order: 2
has_children: true
description: "A guide tutorial for getting started with smoothstep.io."
---

# Tutorial

This guide will teach you the basics of creating animations with {% include smoothstep.html %}.


## Shaders

Animations in  {% include smoothstep.html %} are actually *fragment shaders*, written in the WebGL2 shader language (*GLSL*). A shader computes the color of every pixel of each frame in parallel, using the location of the pixel, and variables like `iTime` that encode the frame timing. Your computer may run the code on its GPU, making the animations run fast. (But you can always export your animations at any frame rate, even if they do not run in real time.)

As you learn to code in GLSL, you can click on functions like `smoothstep` and input variables like `iTime` within the editor to see their definitions:

![smoothstep definition](/images/tutorial/definition.png)


## Shadertoy

{% include smoothstep.html %} is partly modeled after [Shadertoy](https://www.shadertoy.com/), but with features specifically for building and sharing animations. This means that you can use a lot of the resources for learning [Shadertoy](https://www.shadertoy.com/). In fact, a lot of code from [Shadertoy](https://www.shadertoy.com/) will also run on {% include smoothstep.html %}.

One excellent tutorial series is [TheArtofCode's Shadertoy tutorial](https://www.youtube.com/watch?v=u5HAYVHsasc&list=PLGmrMu-IwbguU_nY2egTFmlg691DN7uE5&ab_channel=TheArtofCode) on YouTube.

[Start tutorial](/tutorial/simple-shader){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
