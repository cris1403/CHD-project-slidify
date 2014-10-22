---
title       : Prevent Heart Disease
subtitle    : Assess the probability of having a Coronary Heart Disease
author      : Cristian Mastrofrancesco
job         : statistician
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: [libraries/nvd3]}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## CHD

* We have built a risk assessment tool for estimating
a person 10-year risk of having a heart attack

* Heart disease has been the leading cause of death
worldwide

* Risk factors are variables that increase the chances of a
disease

* Key to successful prediction of CHD: identifying the most
important risk factors


---

## Risk factors

We took into account different features:
+ demographic
+ behavioral
+ medical history
+ last blood test results

---

## Gender and CHD



<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    800,
"height":    400,
"x": "Gender",
"y": "Frequency",
"group": "CHD",
"type": "multiBarChart",
"id": "chart1" 
},
        data = [
 {
 "CHD": "No",
"Gender": "Female",
"Frequency": 0.8756198347107 
},
{
 "CHD": "Yes",
"Gender": "Female",
"Frequency": 0.1243801652893 
},
{
 "CHD": "No",
"Gender": "Male",
"Frequency": 0.8115384615385 
},
{
 "CHD": "Yes",
"Gender": "Male",
"Frequency": 0.1884615384615 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

Gender seems to be an important risk factor!

---

## Cholesterol and CHD



<div id = 'chart2' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart2()
    });
    function drawchart2(){  
      var opts = {
 "dom": "chart2",
"width":    800,
"height":    400,
"x": "Cholesterol",
"y": "Frequency",
"group": "CHD",
"type": "multiBarChart",
"id": "chart2" 
},
        data = [
 {
 "CHD": "No",
"Cholesterol": "Desiderable",
"Frequency": 0.8951521984216 
},
{
 "CHD": "Yes",
"Cholesterol": "Desiderable",
"Frequency": 0.1048478015784 
},
{
 "CHD": "No",
"Cholesterol": "High",
"Frequency": 0.8540145985401 
},
{
 "CHD": "Yes",
"Cholesterol": "High",
"Frequency": 0.1459854014599 
},
{
 "CHD": "No",
"Cholesterol": "Very High",
"Frequency": 0.8207126948775 
},
{
 "CHD": "Yes",
"Cholesterol": "Very High",
"Frequency": 0.1792873051225 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

Cholesterol is a dangerous risk factor!


---

## Smoking behavior and CHD


<div id = 'chart3' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart3()
    });
    function drawchart3(){  
      var opts = {
 "dom": "chart3",
"width":    800,
"height":    400,
"x": "Smoker",
"y": "Frequency",
"group": "CHD",
"type": "multiBarChart",
"id": "chart3" 
},
        data = [
 {
 "CHD": "No",
"Smoker": "No smoking",
"Frequency": 0.8550116550117 
},
{
 "CHD": "Yes",
"Smoker": "No smoking",
"Frequency": 0.1449883449883 
},
{
 "CHD": "No",
"Smoker": "Light smoker",
"Frequency": 0.8714285714286 
},
{
 "CHD": "Yes",
"Smoker": "Light smoker",
"Frequency": 0.1285714285714 
},
{
 "CHD": "No",
"Smoker": "Smoker",
"Frequency": 0.835175879397 
},
{
 "CHD": "Yes",
"Smoker": "Smoker",
"Frequency": 0.164824120603 
},
{
 "CHD": "No",
"Smoker": "Heavy smoker",
"Frequency": 0.8373983739837 
},
{
 "CHD": "Yes",
"Smoker": "Heavy smoker",
"Frequency": 0.1626016260163 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

Smoking doesn't seem to be so dangerous regarding CHD

---

## Glucose levels and CHD


<div id = 'chart4' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart4()
    });
    function drawchart4(){  
      var opts = {
 "dom": "chart4",
"width":    800,
"height":    400,
"x": "Glucose",
"y": "Frequency",
"group": "CHD",
"type": "multiBarChart",
"id": "chart4" 
},
        data = [
 {
 "CHD": "No",
"Glucose": "Desiderable",
"Frequency": 0.8539100544257 
},
{
 "CHD": "Yes",
"Glucose": "Desiderable",
"Frequency": 0.1460899455743 
},
{
 "CHD": "No",
"Glucose": "Pre-diabetes",
"Frequency": 0.8363636363636 
},
{
 "CHD": "Yes",
"Glucose": "Pre-diabetes",
"Frequency": 0.1636363636364 
},
{
 "CHD": "No",
"Glucose": "Diabetes",
"Frequency": 0.546511627907 
},
{
 "CHD": "Yes",
"Glucose": "Diabetes",
"Frequency": 0.453488372093 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

Glucose levels have an high impact on the probability a person has a CHD!!!


--- .smallcode


## Modeling CHD using logistic regression

We use logistic regression to predict
whether or not a patient experienced CHD within 10
years of first examination.

The model can differentiate low-risk from high-risk
patients.


```
## 
## Call:
## glm(formula = TenYearCHD ~ male + age + cigsPerDay + totChol + 
##     sysBP + glucose + prevalentStroke, family = binomial, data = framingham)
## 
## Deviance Residuals: 
##     Min       1Q   Median       3Q      Max  
## -2.0247  -0.5991  -0.4326  -0.2849   2.8774  
## 
## Coefficients:
##                   Estimate Std. Error z value Pr(>|z|)    
## (Intercept)      -9.130088   0.462612 -19.736  < 2e-16 ***
## maleMale          0.549033   0.104014   5.278 1.30e-07 ***
## age               0.066351   0.006260  10.600  < 2e-16 ***
## cigsPerDay        0.020158   0.004072   4.951 7.39e-07 ***
## totChol           0.002515   0.001060   2.371   0.0177 *  
## sysBP             0.016747   0.002099   7.977 1.50e-15 ***
## glucose           0.007591   0.001646   4.611 4.00e-06 ***
## prevalentStroke1  1.064541   0.442437   2.406   0.0161 *  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 1)
## 
##     Null deviance: 3290.3  on 3816  degrees of freedom
## Residual deviance: 2903.1  on 3809  degrees of freedom
##   (423 observations deleted due to missingness)
## AIC: 2919.1
## 
## Number of Fisher Scoring iterations: 5
```

