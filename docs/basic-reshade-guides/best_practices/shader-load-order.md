---
title: Shader Load Order
layout: page
nav_order: 1
parent: Best Practices
grand_parent: Basic ReShade Guides
---

# Shader Load Order

Shader load order refers to the order in which shaders within ReShade are loaded from top to bottom. Having a great load order will give you the best results. Especially when carefully taken into consideration.

![Alt text](<Cemu 2023-09-05 18-40-46 overlay.jpg>)

Here is the ideal load order as shown in the image above:

1. Motion vector shaders such as iMMERSE Launchpad. This is required to process all of the normals, opticalflow and depth calculations for RTGI or even MXAO. Doing this allows for the cleanest possible presentation.
1. Lighting shaders such as iMMERSE Pro RTGI or an ambient occlusion shader such as MXAO.
1. Shaders that adjust color balance, brightness and contrast such as iMMERSE Pro ReGrade.

Why is this important? The reason is because you don't want to make your color adjustments to the depth buffer first. Lets say that you do put a color shader at the top before RTGI. What you'd effectively be doing is adjusting the color of the entire depth buffer beforehand. This would directly affect how the lighting adjustments are being made by RTGI which would then create innaccurate results to the overall image and lighting. Same goes for any AO shader. Here are a few examples of good and bad practices shown below.

Color shader on top:
![Alt text](<Cemu 2023-09-05 19-02-35 overlay.jpg>)
Color shader underneath:
![Alt text](<Cemu 2023-09-05 19-02-42 overlay.jpg>)

This is an extreme example **(I will redo these comparisons later)**. Let's continue down the ideal load order list.

![Alt text](<Cemu 2023-09-05 18-40-46 overlay.jpg>)

4. Any AA shader such as iMMERSE Anti Aliaising.
1. Shaders that enhance texture sharpness such as iMMERSE Pro Clarity.

Why is this important to place shaders that affect sharpness after anti aliasing? It's so that you're not edge detecting the sharpening effect. Doing so would cause the anti aliasing to be inaccurate and provide undesireable results.

6. Any additional post-processing effects such as iMMERSE Pro Solaris which affects bloom. Or even gaussian blur of some sort.
1. Last but not least, any depth based effects such as depth of field or adaptive fog. You could even throw in film grain at the very bottom of the load order if that floats your boat.

Keep in mind that this type of load order is recommended for gameplay presets mostly. You don't have to follow this order as closely if you're only taking screenshots. But some of this is still important to keep in mind to avoid any funky results such as AO on top of DOF.