---
title: Limiting Your Game Framerate
layout: page
nav_order: 11
parent: Special & Others
---

# Limiting your game's framerate.

While having the highest FPS can be seen as a good thing, it often comes with the side effect of not allowing shaders breathing room in ReShade.

This guide will take you down the various paths of how to limit your framerate, both globally and locally!

-----------------

## AMD Adrenalin Global (Driver Based, AMD GPU Only, All Games)
This guide will provide you with the basics to limit your framerate using AMD Adrenalin's `Frame rate target control` function.

Keep in mind that this works globally, so it will force the framerate to what you set for ALL games on your system.

### Step 1 - Opening AMD Adrenalin
Open AMD Adrenalin:
* __Easiest Method__ - Right click your desktop wallpaper, and click `AMD Software꞉ Adrenalin Edition`.
    <div class="figure">
    <img src="./images/limiting_game_fps/amd_desktop_context_menu.png" width="225px"/><br>
* Alternative Method - Search `Adrenalin` in the Windows Search Bar.
    <div class="figure">
    <img src="./images/limiting_game_fps/amd_start_search_software.png" width="500px"/><br>

-----------------

### Step 2 - Enabling "Frame rate target control"
1. Click `Gaming` on the top most bar of the `Adrenaline` software, and then click `Graphics` in the second bar that has now appeared.
    <div class="figure">
    <img src="./images/limiting_game_fps/amd_graphics_gaming_highlight.png" width="400px"/><br>
2. Scroll down to the `Advanced` portion of the `Graphics` tab and enable `Frame rate target control`.
    <div class="figure">
    <img src="./images/limiting_game_fps/amd_enable_frtc.png" width="500px"/><br>
4. Tune `Frame rate target control` to have the desired `Max FPS`.
    <div class="figure">
    <img src="./images/limiting_game_fps/amd_frtc_tune.png" width="500px"/><br>

-----------------

