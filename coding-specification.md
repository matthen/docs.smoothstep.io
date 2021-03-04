---
layout: page
title: Coding Specification
permalink: /coding-specification
nav_order: 5
description: "Specification of input uniforms and shader requirements."
---

# Coding Specification

Every {% include smoothstep.html %} animation must define a `mainImage` function with the following signature:

```glsl
void mainImage(out vec4 fragColor, in vec2 fragCoord) {
  fragColor.rgb = vec3(1., 0., 0.);
}
```

(This is the same as [Shadertoy](https://www.shadertoy.com/) shaders.)

## Input Uniforms

Animations may also use any of the following input variables (*uniforms*):

| variable | description |
|---|---|
| `int iFrame`  |  The index of the current frame. |
| `float iTime`  |  The time into the animation that the current frame is being rendered at. |
| `sampler2D iPrevFrame`  |  The contents of the previously rendered frame. |
| `vec2 iResolution`  |  The resolution of the frame being rendered in pixels. |
| `float iDuration`  |   The total duration of the animation in seconds. |
| `sampler2D iTexture0` etc.  | The contents of the textures.  |
| `float iFloat0` etc.  | The value of the animated parameters, controlled by the animation timeline.  |
