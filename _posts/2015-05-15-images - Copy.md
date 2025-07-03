---
layout: post
title: are unions good (visually)?
date: 2025-07-01 12:00:00
description: using real data to visualize unionization, productivity, and capital intensity
tags: Politics Tech R Plotly Economics Visualization Data images
categories: social-sciences
---

this all started because people online were arguing about unions again — some saying they tank productivity, others claiming they’re the key to a better workforce. i figured i'd just pull some numbers and see what the data actually looks like, instead of getting into another circular debate.

i combined three main datasets, all from 2019 to keep things consistent:

- unionization rates by country (from the OECD),
- labor productivity measured as output per hour worked (from the Penn World Table),
- and national GDP (from the World Bank), just for context and sizing.

i also added capital intensity, which is basically how much equipment or physical capital workers have access to in a given country.

the first html embed (below) has two bubble plots side-by-side. the first one shows union rate vs labor productivity, and there's a clear downward curve; countries with very low or very high union membership seem to have lower productivity, while the ones in the middle tend to do best. it’s a classic parabola shape, and i threw on a smooth fit line to help make that clearer. does this mean anything? probably not — you tend to get that with a sample size of 15.

the second plot compares capital intensity vs productivity, and that one is just a straight-up positive linear trend. more machines and infrastructure per worker tends to mean higher productivity — no surprise there.

each dot is a country, and its size and color are based on GDP. bigger economies are more visually prominent. you can hover over each point to see which country it is and the actual numbers.

<iframe src="/assets/stats/2dscatterplotforecon.html" width="100%" height="500"></iframe>

then i decided to build a 3d scatterplot that combines all three variables: union rate (x), capital intensity (y), and labor productivity (z). it’s a bit harder to read at first glance, but you can rotate it and zoom in, which helps you spot different clusters or patterns.

what’s neat here is that you can see how different countries take different “paths” to high productivity. some rely more on capital investment, others have more balanced union coverage and capital intensity. and some just kinda hover in the middle of everything.

<iframe src="/assets/stats/3dscatterplotforecon.html" width="100%" height="600"></iframe>

### quick note on how this was built

i made all the plots in R using Plotly, which lets you build interactive charts and export them as self-contained HTML files. most of the complexity is just cleaning the datasets and lining up the country codes across all sources. i might make a cleaner version of the script later if people are interested — though look forward to a very cool FRC-related library for R coming out sometime in the next… decade?

<p style="font-size: 12px; color: #888;">Posted on 2025-07-01</p>
