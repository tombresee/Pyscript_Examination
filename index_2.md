I want you to start by clicking [this link](https://pyscript.net/examples/panel_stream.html).  

Wait a few seconds.  

What do you think of it ? 

It was built in a very unusual manner...


#### <font color='#00274C'> Author:  Tom Bresee </font>
#### Category:  Examining something new to the industry


<br>
<br>


### <font color='#00274C'>Background</font>

I want you to start by clicking [this link](https://pyscript.net/examples/panel_stream.html).  

Wait a few seconds.  

What do you think of it ? 

It was built in a very unusual manner...

<p align="center"><img src='https://raw.githubusercontent.com/pyscript/pyscript/main/pyscriptjs/examples/logo.png' alt='py.png' width="100"></p>


<br>
<br>



### <font color='#00274C'>What is Pyscript ?</font>

PyScript does **not** require any development environment other than a web browser (be safe and use Chrome). It allows writing webesites in python.  

* <https://pyscript.net/>
* <https://github.com/pyscript>
* <https://github.com/pyscript/pyscript/blob/main/GETTING-STARTED.md>
* [Original Anaconda Blog](https://www.anaconda.com/blog/pyscript-python-in-the-browser)



<br>
<br>



### <font color='#00274C'>Cut to the chase and get to it...</font>


Ok, it's very simple. 

`<p>This is normal text - <b>and this is bold text</b>.</p>`

HTML tags.  Yes, we are going way back.  Like the [simple stuff](https://www.w3schools.com/tags/tag_comment.asp). 

An HTML tag is a piece of markup language used to indicate the beginning and end of an HTML element in an HTML document.  Yes, got it.  

> <u>The new PyScript project lets you embed Python programs *directly* in HTML pages and execute them within the browser without any server-based requirements.</u>


<br>


**Your new HTML tag building blocks:**


| HTML Tag | Purpose |
|:-|:-|
| `<py-script>`   | Indicates to HTML to to execute the python code  | 
| `<py-env>` | Indicates to HTML what your python library dependencies are (if you don't need any python libraries, it's blank). This component defines the Python packages needed to run your Python code...  |


<br>



**The Process:**

1. Import the appropriate pyscript files to your html page with: 
  - `<link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />`
  - `<script defer src="https://pyscript.net/alpha/pyscript.js"></script>`
   Now you can use PyScript components in your html page

2. Just write your code as if you were in any other IDE, making sure it is between the `<py-script>` tags.  These tags defined the python code that is executable within the web page. 


<br>


```python
<html>
  <head>

    <link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css"/>
  
    <script defer src="https://pyscript.net/alpha/pyscript.js"></script>
  
  </head>
  <body> 
  
  <py-script>  

# Tom is inserting his standard python code within these new <py-script> html TAGs: 
print('Tom is cool.') 
print('If you see this output, it means you did everything right...')
# Tom is done pasting in his python code...
 
   </py-script> 

</body>
</html>
```


You see how I left-aligned all the python code ?  It's the safe way of making sure it all works correctly...





<br>
<br>



### <font color='#00274C'>A more complicated example</font>


Ok, it's very simple. 



Plotting charts is going to be a big thing to leverage, let's show how to do it... 

<br>


```python
<html>
    <head>
      <link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />
      <script defer src="https://pyscript.net/alpha/pyscript.js"></script>

      <py-env>  
        - numpy  
        - pandas 
        - matplotlib
        - scikit-learn 
      </py-env>
    
    </head>

  <body>
    
    <p> Plotting random numbers </p>

    <div id="plot"></div>
    
    <py-script output="plot">   

# importing my libraries 
import matplotlib.pyplot as plt
import numpy as np

# defining some random variables 
x = np.random.randn(1000)
y = np.random.randn(1000)

fig, ax = plt.subplots()

ax.scatter(x, y)

fig

    </py-script>


  </body>
</html>
```

<p> The py-env tag is used to define our Python environment. Example of loading python packages into our environment: </p>

```
<py-env> 
  - numpy   
  - pandas 
  - matplotlib
  - scikit-learn
 </py-env>
```

<p>Don't want to write all your python code directly into the html file ? 
It's fine, just reference it:</p>

```<py-script> src="/toms_python_file.py"> </py-script>```












<br>
<br>

### <font color='#00274C'>How do I know if my particular python library is supported ???</font>

If you make the [list](https://github.com/pyodide/pyodide/tree/main/packages), you are supported. 

All those hours you spent learning numpy, pandas, matplotlib, seaborn, altair, bokeh, scipy, **networkx**, etc are about to pay off...Even the mighty **scikit-learn is supported**. 

The link is technically the folder that contains the list of packages built in **pyodide**. 















<br>

<hr>






 - [Kaggle NFL Repo](https://www.kaggle.com/c/nfl-big-data-bowl-2021/data)
   - **Description:** Online resource of 2018/2019 football season raw data, including GPS-like positional information for every single player for every single play (offense and defense). 
   - 20 separate .csv files (including one with 18M samples), and 363 feature columns
   - Total Set Size:  2.17 GB
   - Accessible via kaggle web API

 - [NFL Kaggle 2020 Repo](https://www.kaggle.com/c/nfl-big-data-bowl-2020/data)
   - Total Set Size:  276.47 MB
   - Accessible via kaggle web API 

 - [NFL Next Gen Stats](https://nextgenstats.nfl.com/)
   - Multiple insightful data sub-sources accessible via web scraping of raw HTML

 - [NFL Play by Play Vault](https://www.dolthub.com/repositories/Liquidata/nfl-play-by-play)
   - This data sourced from original nflfastR package scrape of [this](https://github.com/guga31bb/nflfastR-data)
   - Original poll python [scripts](https://github.com/dolthub/dolthub-etl-jobs/tree/master/adhoc/nfl-play-by-play)
   - Assumption is via Dolpy, a python API [wrapper](https://www.dolthub.com/docs/tutorials/installation/#doltpy)

 - NFLsavant.com
   - http://nflsavant.com/pbp_data.php?year=2018
   - 45,000+ play breakout samples 

 - Potentially public access to [Shield](https://api.nfl.com/docs/getting-started/index.html)
   - Shield represents the client-facing API that will serve the needs of internal projects, external contributors, and third-party partners. It is the primary way to read and write content to the NFL. It will allow users to find content, submit content for use in client applications and websites.
   - [API Endpoints](https://api.nfl.com/docs/global/endpoints/index.html) - This is a full list of the available Shield API root nodes.


<br>
<br>


### <font color='#00274C'>Expected Data Manipulation:</font>
 - Initial Processing:
   - Expectation is removing appropriate null values, interpolating some null values, and cleaning dataset for characters.  Part of the dataset may also be unusually, outlier, or corrupted in text form.
 - Merging/Combining:
   - Joining of all datasets will be contingent on a few elements:
     - In some cases, unique gameID key will be used to merge dataframes (which can also be broken out by NFL week)
     - In some cases, unique playID key will be used to merge dataframes
     - In some cases, unique playerID key will be used to merge dataframes
     - The outputs of the combinations and merges of the raw datasets will be dataframes that contain valuable meshed data forms that will allow correlation of features and examination of factors leading to victories (or football game losses).
 - New information resulted from combining them:
   - If we do this correctly, we will have a complete view of every single play, for every single player, for every single game in an entire NFL season.  This information will also include Next Gen Stats positional data for correlation.



<br>
<br>




### <font color='#00274C'>Enhanced Visualization Expectations:</font>
 Final presentation will include a fully interactive view of all NFL players by weight, height, offense/defense, college attended, BMI, football position, including deeper views of the players via html link to their official NFL profile. This visualization will also allow a deeper view into player positional coordinates. 
   - Position coordinates is a relatively new technology, and an exciting element to analyze
   - Examples:  [Viz1](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/tampa_bay_passes_all_season.svg), [Viz2](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/avg_passing_yds_per_game_by_team.svg), [Viz3](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/player_weight_distribution.svg), [Viz4](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/orangeonblue2_b.svg), [Viz5](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/spheroid_prolate.svg), [Viz6](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/frontend.png)

<br>
<br>




### <font color='#00274C'>Expected Visualization Tool Approaches:</font>
- Interactive Vizualization: 
   - Bokeh
   - Holoviews
   - Altair 
- Static Visualization:
   - Seaborn
   - Matplotlib
   - Altair 
   - ggplot 



<br>
<br>



### <font color='#00274C'>Core Technical Tools:</font>
 - Jupyter Notebooks
 - Apache Spark tie-in
 - Databricks Apache Spark platform (which I will have a link to the public notebook for spark python api commands)
 - Heroku [prototype](https://immense-eyrie-75566.herokuapp.com/).  This will store an additional bokeh server for truly interactive visualization of various information. 
 - Google Cloud Platform (GCP) as host to Heroku front-end
 - NetworkX / Gephi
 


<br>
<br>



### <font color='#00274C'>Reproducibility:</font>
- In order for the core project to be as reproducible as possible, I have a set of github pages as well as the core project within Kaggle (so that the notebook can be downloaded and executed locally, with minimal effort). 
- Note:  A portion of the project will also be hosted on Databricks, with a public URL, which is convenient given that Databricks offers the ability to efficiently *import* any public URL to the user's account, allowing execution of the notebook immediately on the local cluster object. 



<br>
<br>




#### <font color='#00274C'>CONTACT</font>
General questions should be directed to Tom Bresee at <tbresee@umich.edu>.



**Source:** [Michigan Milestone](https://tombresee.github.io/NFL/Milestone/)

