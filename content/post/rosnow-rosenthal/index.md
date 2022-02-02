---
title: What simple effects can't tell
subtitle: Often, people interpret an interaction based on simple effects. This post aims at showing that this kind of practice is to be avoided because simple effects also depend on main effects.

# Summary for listings and search engines
summary: Often, people interpret an interaction based on simple effects. This post aims at showing that this kind of practice is to be avoided because simple effects also depend on main effects.

# Link this post with a project
projects: []

# Date published
date: "2021-11-27T00:00:00Z"

# Date updated
lastmod: "2021-11-28T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**pixabay**](https://pixabay.com/fr/photos/garçon-la-paume-du-visage-enfant-666803/)'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- Yoann Julliard

tags:
- statistics
- r
- shiny

categories:
- shiny

links:
- icon: twitter
  icon_pack: fab
  name: Follow
  url: https://twitter.com/YoannJulliard
- name: R shiny app
  url: https://yoannjulliard.shinyapps.io/rosnow_rosenthal_app/
---

## Some context

<p style='font-size:15px; text-align: justify;'> 
The app below displays a plot based on various entries that you can manipulate. To give some context, the app is inspired by data we observe using approach/avoidance tasks. In these tasks, participants have to approach or to avoid positive or negative stimuli. Data typically reveals 'compatibility effects': Particicipants are faster in the compatible condition (in which they have to approach positive stimuli and to avoid negative ones), than in the incompatible condition (in which they have to approach negative stimuli and to avoid positive ones). 
<br>
This compatibility effect is often inferred from the interaction between movement and valence, but sometimes researchers draw conclusions based on the simple effects. As mentioned in the subtitle of this post, the app below aims at showing that this kind of practice is to be avoided (wink).
<br>
<br>
Even though the app below is designed to illustrate approach/avoidance data, you can apply the same reasoning to other effects, especially compatibility effects (e.g., stroop effects, imitation effects, priming effects...)
</p>

## Simple effects depend on main effects

<p style='font-size:15px; text-align: justify;'> 
As you can see with the app below, simple effects depend on the interaction, but also on the main effects. One way to see this is to vary the main effects using the sliders and to observe how it affects the simple effects.
<br><br>
You can see that various patterns of simple effects can be observed with the exact same interaction (see the t-value), because varying the main effects do not affect the interaction effect at all. Another consequence is that different visual pattern of mean plot can arise from the exact same interaction. 
<br><br>
Using this app, you can also see visually what an interaction effect really looks like. To do so, set the valence and movement main effects to 0, and increase the sample size to some 10,000 participants (in order to reduce random variability). Once you have done these manipulations you look at a 'real' interaction plot, and as you can see the pattern of an interaction is always crossed.
</p>

## Shiny app

<!-- the position absolute causes issues of positioning for the other elements of the website, try to find another solution -->
<div style= "position:absolute; left:10%; right:-10%;">
<iframe height="850px" width="80%" frameborder="no" src="https://yoannjulliard.shinyapps.io/rosnow_rosenthal_app/"> </iframe>
</div>

<!-- dirty hack to artificially add the height of the app in order that the other elements of the website appear -->
<div style= "height: 850px"></div>

## About the shiny app

<p style='font-size:15px; text-align: justify;'> 
This app is generated using R and the shiny library. Click <a href="https://yoannjulliard.shinyapps.io/rosnow_rosenthal_app/" target="_blank" title="https://yoannjulliard.shinyapps.io/rosnow_rosenthal_app/">here</a> to open the shiny app in a stand-alone web page.
<br>
Basically, the R script running under the hood simulates data based on the entries on the left (e.g., main and interaction  effects) that you can manipulate. Actually, participants data are drawn from a normal distribution of the intercept, the valence and movement main effects, and the interaction effect. Response times for each condition (i.e., approach-positive, approach-negative, avoidance-positive, avoidance-negative) are then computed based on these data and then plotted. The script also computes linear models to display the summary of the common statistical tests performed. 
<br>
In order to allow computational reproducibility, the random generation of data is defined using seeds. Because of these seeds, you can vary one entry without altering others.
<br><br>
Feedback on the post or the app is appreciated, do not hesitate to reach me via <a href="/#contact" target="_blank" title="/#contact">email</a> or <a href="https://twitter.com/YoannJulliard" target="_blank" title="https://twitter.com/YoannJulliard">Twitter</a>. 
</p>