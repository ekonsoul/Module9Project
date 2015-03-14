---
title       : Interactive Probability Distributions Gallery
subtitle    : An exploratory journey into the world of randomness... 
author      : Ilias Konsoulas
job         : Developing Data Products Project
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [shiny, interactive]  
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

### Description of Purpose

* The main purpose of this small app is an educational one:
  To help the user understand the influence of various probability
  distribution parameters on the appearance and behavior of their
  corresponding pdf/pmf and cdf functions.    

* Apart from that, it demonstrates the connection between a scaled
  histogram (which sums up to 1) and the corresponding pdf for every
  distribution of the Gallery. This proves to younger students the very 
  essence of any pdf as a probability density measure and it verifies
  the validity of R's random number generators.  
   
* Finally, this app features a numerical and a graphical probability calculator.
  Those extra components help the user to do some quick calculations and see 
  graphically the implied mathematical connections between the two functions (pdf and cdf).  

---

### User Interaction (1 of 3)

* On the sidebar Panel, the user may select one of the 12 probability
  distributions which comprise the Gallery. This is done using the 
  following selection Box:  

<div class="row-fluid" align="center">
  <div class="span4">
    <form class="well">
      <label class="control-label" for="selectedpdf">
        <h5>Select Distribution</h5>
      </label>
      <select id="selectedpdf"><option value="1" selected>Normal</option>
<option value="2">Beta</option>
<option value="3">Gamma</option>
<option value="4">Cauchy</option>
<option value="5">Binomial</option>
<option value="6">Exponential</option>
<option value="7">Poison</option>
<option value="8">Log-Normal</option>
<option value="9">Weibull</option>
<option value="10">Student's t</option>
<option value="11">Chi-Squared</option>
<option value="12">Uniform</option></select>
      <script type="application/json" data-for="selectedpdf" data-nonempty="">{}</script>
    </form>
  </div>
</div>
<br /> 
*  After the distribution of interest is selected, the user may alter the number
   of bins (cells) to be used for the histogram plot of an adjustable size population of 
   random numbers generated from the selected distribution. The histogram is scaled to 
   sum up to unity and agrees with the overlying pdf plot of the distribution in red color.
   This verifies the correctness of R's random number generators. Also, the accuracy of the
   histogram improves and almost coincides with the associated pdf as the number of
   generated random samples increases using the relevant slider.

<div class="row-fluid" align="center">
  <div class="span4">
    <form class="well">
      <div>
        <label class="control-label" for="N1">Number of Random Samples</label>
        <input id="N1" type="slider" name="N1" value="1000" class="jslider" data-from="100" data-to="1e+05" data-step="100" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
      </div>
    </form>
  </div>
</div>

<div class="row-fluid" align="center">
  <div class="span4">
    <form class="well">
      <div>
        <label class="control-label" for="Nbreaks1">Number of Scaled Histogram bins</label>
        <input id="Nbreaks1" type="slider" name="Nbreaks1" value="100" class="jslider" data-from="20" data-to="600" data-step="1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
      </div>
    </form>
  </div>
</div>


---

###  User Interaction (2 of 3)

* Next, a couple of slide bars are provided for the app visitor to play with each
  distribution's parameters. The shape and location of the associated pdf, cdf and
  histogram are instantly updated in a reactive manner. For the Normal (Gaussian)
  distribution the adjustable pdf parameters are the mean and standard deviation.
<div class="row-fluid" align="center">
  <div>
    <label class="control-label" for="mean">Mean</label>
    <input id="mean" type="slider" name="mean" value="0" class="jslider" data-from="-10" data-to="10" data-step="0.1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
  </div>
  <div>
    <label class="control-label" for="sd">Standard Deviation</label>
    <input id="sd" type="slider" name="sd" value="3" class="jslider" data-from="1e-10" data-to="20" data-step="0.1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
  </div>
</div>
  
  
* As an extra feature, this app includes a quick probability calculator. The user may select 
  the bounds of the interval where the probability is to be computed. The Lower Bound (x1) is
  adjusted with the top slider and is depicted on both graphs on the right with a cyan
  vertical line. The Upper Bound (x2) of the interval is adjusted with the bottom slider
  and is depicted on both graphs on the right with a magenta vertical line. Probability
  calculations are updated reactively when any of the pdf/cdf parameters or interval bounds
  change by the user.  

---  

### User Interaction (3 of 3)

* On the top of the Main Panel the pdf of the selected distribution is plotted along with the
  associated histogram which again is computed reactively after any user input is received.
  We plot a scaled version of the classic histogram in order to agree scale-wise with the pdf.
  As expected, both plots almost coincide for all possible distributions and parameter values.
  
* On the bottom of the Main Panel we plot the cdf of the selected distribution. On both
  plots the user can see and adjust the probability integration interval bounds using the
  sliders on the sidebar panel. 
  
* The mathematical properties of the cdf function are exploited in order to demonstrate
  geometrically the magnitude of the calculated probability as the length of the blue
  vertical line segment on the left portion of the cdf plot. Again, the size of the blue
  line segment is updated reactively to agree with the calculated probability value when
  the interval bounds or pdf/cdf parameters are altered by the user. 

### Enjoy your journey into the world of randomness using a non-random Shiny app !!!  

