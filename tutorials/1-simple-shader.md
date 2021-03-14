---
layout: page
title: Simple Shader
permalink: /tutorial/simple-shader
nav_order: 1
parent: Tutorial
---

# Creating a simple shader

[Create a new {% include smoothstep.html no_link=true%} animation](https://smoothstep.io/new){:target="_blank"}, and enter the following code into the editor:

```glsl
void mainImage(out vec4 fragColor, in vec2 fragCoord) {
  fragColor.rgb = vec3(1., 0., 0.);
}
```

Click the *build* button, or press shift+enter to recompile the code. The animation should now be a red square.

This is a very simple shader. It sets the output color to red: `fragColor.rgb = vec3(1., 0., 0.);` (this is an RGB color where each value can be from 0 to 1).

Every shader must define a function `void mainImage(out vec4 fragColor, in vec2 fragCoord)`. This function is run in parallel at every pixel, located at coordinate `fragCoord`, and outputs the pixel colour to `fragColor`.

## Animating

This shader outputs a constant red color, so pressing play on the animation will appear to do nothing. We can animate the shader by using the `iTime` variable, which contains the time in seconds into the animation as it is played.

Replace the code with the following:

```glsl
void mainImage(out vec4 fragColor, in vec2 fragCoord) {
  fragColor.rgb = mix(
    vec3(1., 0., 0.),
    vec3(0., 0., 1.),
    iTime
  );
}
```

Press play - in the first second of the animation the colour will animate from red to blue. Experiment with the code:

1. bring up a color picker by clicking inside the `vec3` statements. Select different start and end colors
2. click on `mix` and `iTime` to see their definitions

## Animation timeline

The Animation timeline is a visual way of controlling parameters of an animation. It controls input variables `iFloat0`, `iFloat1` etc. that we can use inside the code.

Replace the code with:

```glsl
void mainImage(out vec4 fragColor, in vec2 fragCoord) {
  fragColor.rgb = mix(
    vec3(1., 0., 0.),
    vec3(0., 0., 1.),
    iFloat0  // control the blend with an animation parameter
  );
}
```

the blend from red to blue is now controlled by the animation parameter `iFloat0`.

In the *Animation* tab, click and drag in the first row to create a transition for `iFloat0`:

![Animation timeline](/images/tutorial/transition.png)

The `smoothstep` transition uses a sigmoidal curve to smoothly interpolate the variable, `linear` interpolates the value linearly, and `step` makes the value jump half-way through the transition.

Note you can change the total duration of the animation, either by editing the value next to the play bar under the canvas, or by dragging the end of the timeline in the *Animation* tab.

## Video resolution

You can change the aspect ratio of the animation by mousing over the animation, and selecting a different value in the top left. When you export the animation, you are able to set the width of the export in pixels to any value. While you edit the code, the animation automatically scales to fit your screen size. Try minimizing the tabs at the bottom to give more screen space to the editor and animation canvas.

[Next](/tutorial/drawing-a-circle){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
