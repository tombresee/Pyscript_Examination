

<py-script src="/python_example.py"> </py-script>



#### <font color='#00274C'> Author:  &ensp; Tom Bresee </font>

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

PyScript does **not** require any development environment other than a web browser (be safe and use Chrome). It allows writing websites in python.  

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


| HTML Tag Element | Purpose |
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



```
<html>
  <head>
    <meta charset="utf-8" />

    <link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />   <--- insert this 
    <script defer src="https://pyscript.net/alpha/pyscript.js"></script>       <--- insert this 

  </head>

  <body>
    <p><br>Welcome. This is a simple pyscript example. We will print out some time values.<br><br></p>


    <py-script>         <--- write your python code here !  

from datetime import date, datetime
now = datetime.now()
current_time = now.strftime("%H:%M:%S")
print("\nThe current time:", current_time)

today = date.today()
print("\nToday's current date:", today)
    
    </py-script>       <--- end of python code  
  

  </body>
</html>
```

<br>

Here is what the HTML output will look like:
<p align="center"><img src='https://raw.githubusercontent.com/tombresee/Pyscript_Examination/main/examples/time.png' alt='py.png' width="600"></p>

as hosted as an example at this live [website](https://www.tombresee.com/Pyscript_Examination/examples/time). 

<br>
<br>




### <font color='#00274C'>A more complicated example</font>


Plotting charts is going to be a big thing to leverage, let's show how to do it... 

<br>


```
<html>
  <head>
    <title>Matplotlib</title>
    <meta charset="utf-8" />

    <link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />
    <script defer src="https://pyscript.net/alpha/pyscript.js"></script>

    
    <py-env>         <--- insert python libraries needed...
      - numpy
      - matplotlib
    </py-env>

  </head>

  <body>
    <p><br>Welcome. This is a simple Matplotlib chart.<br><br></p>
      
    <div id="mpl"></div>

    <py-script output='mpl'>
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
t = np.arange(0.0, 2.0, 0.01)
s = 1 + np.sin(2 * np.pi * t)
fig, ax = plt.subplots()
ax.plot(t, s)
ax.set(xlabel='time (s)', ylabel='voltage (mV)',
       title='About as simple as it gets, folks')
ax.grid()
fig 
    </py-script>
  
  </body>
</html>
```


<br>

Here is what the HTML output will look like:
<p align="center"><img src='https://raw.githubusercontent.com/tombresee/Pyscript_Examination/main/examples/matplotlib.png' alt='py.png' width="600"></p>

as hosted as an example at this live [website](https://www.tombresee.com/Pyscript_Examination/examples/simple_plot). 


<p> The py-env tag is used to define our Python environment. Example of loading python packages into our environment: </p>


```
 <py-env>    < - - - 
  - numpy   
  - pandas 
  - matplotlib
  - scikit-learn
 </py-env>
```

<p>Don't want to write all your python code directly into the html file ? 
It's fine, just reference it:</p>


```<py-script> src="/toms_python_file.py"> </py-script>```


<p>It turns out you can also do something like this:</p>

```
  <div class="container-md" id="test-plot"></div>
  
  <py-script>
  ... 
  pyscript.write('test-plot',fig)

  </py-script>
```

<br>
<br>




### <font color='#00274C'>How do I know if my particular python library is supported ???</font>

If you make the [list](https://github.com/pyodide/pyodide/tree/main/packages), you are supported. 

All those hours you spent learning numpy, pandas, matplotlib, seaborn, altair, bokeh, scipy, **networkx**, etc are about to pay off...Even the mighty **scikit-learn is supported**. 

The link is technically the folder that contains the list of packages built in **pyodide**. 

<br>
<br>




### <font color='#00274C'>Enhanced Visualization Expectations:</font>
 Final presentation will include a fully interactive view of all NFL players by weight, height, offense/defense, college attended, BMI, football position, including deeper views of the players via html link to their official NFL profile. This visualization will also allow a deeper view into player positional coordinates. 
   - Position coordinates is a relatively new technology, and an exciting element to analyze
   - Examples:  [Viz1](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/tampa_bay_passes_all_season.svg), [Viz2](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/avg_passing_yds_per_game_by_team.svg), [Viz3](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/player_weight_distribution.svg), [Viz4](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/orangeonblue2_b.svg), [Viz5](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/spheroid_prolate.svg), [Viz6](https://raw.githubusercontent.com/tombresee/NFL-Big-Data-Bowl-2021/main/ENTER/images/frontend.png)

<br>
<br>




#### <font color='#00274C'>CONTACT</font>
General questions should be directed to Tom Bresee at <tbresee@umich.edu>.

