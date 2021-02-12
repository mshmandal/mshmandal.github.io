---
title: Make beautiful maps in R 
output:
  md_document:
    preserve_yaml: TRUE
knit: (function(inputFile, encoding) {
  rmarkdown::render(inputFile, encoding = encoding, output_dir = "../_posts") })
author: "mshmandal"
date: '2021-02-12'
excerpt: R can be used to make beautiful maps programmatically. Today, I am just playing around with tmap and also setting up this blog. So, I will just keep it short. Let's make some. 
layout: post
categories:
  - spatial
  - gis
  - maps
---

I have been looking to write about making maps in R. But since, I am
using [jekyll](https://jekyllrb.com/) to publish this site using GitHub
it seems little bit tricky to write posts in RStudio and convert to
markdown. Specially connecting the R output graphics into the markdown
posts. Did some Google search and found some help from some blog posts.
More on that later.

Today, I will start a post about many possible ways to make beautiful
maps in R. I specially like the
[‘tmap’](https://cran.r-project.org/web/packages/tmap/vignettes/tmap-getstarted.html)
package. It is flexible and powerful. Read about the documentation and
install the package.

So, the basic syntax is pretty simple.

    # install.packages('tmap', dependencies = T)  
    library(tmap)

We load a world shapefile object already loaded inside the ‘tmap’
package

    # load data
    data(World)

Check the class of the object

    class(World)

    ## [1] "sf"         "data.frame"

Now we check the data typs and attributes inside

    # str(World) # run this line to check, removing first hash sign.
    names(World) # check attributes name

    ##  [1] "iso_a3"       "name"         "sovereignt"   "continent"    "area"        
    ##  [6] "pop_est"      "pop_est_dens" "economy"      "income_grp"   "gdp_cap_est" 
    ## [11] "life_exp"     "well_being"   "footprint"    "inequality"   "HPI"         
    ## [16] "geometry"

So, this is a [sf](https://r-spatial.github.io/sf/articles/sf1.html)
object which stands for ‘simple feature’. Kind of same like dataframe
but with geometry attributes.

Now we can tm\_shape function, here we specify the data to plot and next
we specify the type of plotting we want. Since, this is a polygon of
countries, we will specify as so using ‘tm\_polygons()’ with a + (plus)
just ahead of it. Finally, inside tm\_ploygons() we simply specify the
attribute to plot.

    tm_shape(World)+                 
    tm_polygons("HPI") 

![](/img/HPI-map-1.png)

Next, we can assign colors for the map, rather than random colors.

    tm_shape(World)+                 
    tm_polygons("life_exp", palette="RdYlBu") 

![](/img/life-exp-plot-1.png)

‘tamp’ have lot of options, which I love to play with when making maps.
So, have a look at their documentation and happy mapping.
