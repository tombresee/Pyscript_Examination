
### <font color='#00274C'>Background</font>

I want you to start by clicking [this link](https://pyscript.net/examples/panel_stream.html).  

It's going to take a bit to load, wait for it. 

What do you think of it ? 

It was built in a very unusual manner...

<p align="center"><img src='https://raw.githubusercontent.com/pyscript/pyscript/main/pyscriptjs/examples/logo.png' alt='py.png' width="100"></p>


<br><br>



### <font color='#00274C'>What is Pyscript ?</font>

You can now use Pyscript to run Python code IN the web browser.  PyScript does **not** require any development environment other than a web browser (Chrome is recommended for stability).  This has enormous potential for AI, ML, Data Scientists, and even regular Python developers. The possibility of writing both frontend and backend code in Python is intriguing...

Some reference links below:
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

Pyscript defines the tag `<py-env>` which defines the Python packages your program requires. IF you refer to a numpy command for instance without refering to it from py-env, it will not work, you will get a error similiar to something like this:  ```ModuleNotFoundError: No module named 'altair'```

<br>


**The Process:**

1. Import the appropriate pyscript files to your html page with: 
  - `<link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />`
  - `<script defer src="https://pyscript.net/alpha/pyscript.js"></script>`
   Now you can use PyScript components in your html page.  You will always include these two tags in the HTML head. 

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


Note:  You must correctly format the Python code just like a normal .py file. Indentation will matter !  I just left align the python code to keep it simple. 

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

<p>Don't want to write all your python code directly into the actual html file ? 
It's fine, just reference it like this:</p>

```<py-script> src="/toms_python_file.py"> </py-script>```

This loads python from that separate file...


<br>

<p>It turns out you can also do something like this for plotting matplotlib charts:</p>

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






### <font color='#00274C'>Bokeh</font>

Plotting charts is going to be a big thing to leverage, let's show how to do it... 

<br>


```
<html><head>
    <title>Bokeh Example</title>
    <meta charset="iso-8859-1">
    <link rel="icon" type="image/x-icon" href="./favicon.png">
    <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-2.4.2.min.js"></script>
    <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-gl-2.4.2.min.js"></script>
    <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-widgets-2.4.2.min.js"></script>
    <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-tables-2.4.2.min.js"></script>
    <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-mathjax-2.4.2.min.js"></script>

    <script type="text/javascript">
        Bokeh.set_log_level("info");
    </script>
    
    <link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />
    <script defer src="https://pyscript.net/alpha/pyscript.js"></script>

    </head>
    <body>
        <py-env>
         - bokeh
         - numpy
         - pandas 

        </py-env>
        <h1>Bokeh Example</h1>
        <div id="myplot"></div>

    <py-script id="main">
import json
import pyodide
import pandas as pd
from js import Bokeh, console, JSON

from bokeh.embed import json_item
from bokeh.resources import CDN
from bokeh.plotting import figure, show
from bokeh.sampledata.penguins import data
from bokeh.transform import factor_cmap, factor_mark

SPECIES = sorted(data.species.unique())

MARKERS = ['hex', 'circle_x', 'triangle']

p = figure(title = "Penguin size", background_fill_color="#fafafa")
p.xaxis.axis_label = 'Flipper Length (mm)'
p.yaxis.axis_label = 'Body Mass (g)'
p.scatter("flipper_length_mm", "body_mass_g", source=data,
          legend_group="species", fill_alpha=0.4, size=12,
          marker=factor_mark('species', MARKERS, SPECIES),
          color=factor_cmap('species', 'Category10_3', SPECIES))
p.legend.location = "top_left"
p.legend.title = "Species"

p_json = json.dumps(json_item(p, "myplot"))
Bokeh.embed.embed_item(JSON.parse(p_json))
    </py-script>

</body>
</html>
```


<p> This was a bit trickier. Bokeh can also supply JSON data that **BokehJS** can use to render a standalone Bokeh document in a specified `div`. 
The json_item() function accepts a Bokeh model (for example, a plot) and an optional ID of the target `<div>`.</p>
This [link](http://docs.bokeh.org/en/latest/docs/user_guide/embed.html) helped explain the details. 


```
item_text = json.dumps(json_item(p, "myplot"))

The embed_item() function can then use this output on a web page:
item = JSON.parse(item_text);
Bokeh.embed.embed_item(item);
This renders the plot in the <div> with the ID “myplot”.




#  You can also omit the target ID when calling json_item():
p = figure()
p.circle(x, y)
item_text = json.dumps(json_item(p)) # no target ID given

#  You can then specify the ID in JavaScript:
item = JSON.parse(item_text);
Bokeh.embed.embed_item(item, "myplot");
```







### <font color='#00274C'>Altair</font>

Plotting charts is going to be a big thing to leverage, let's show how to do it... 

<br>

```
    <py-env>
      - altair
      - pandas
      - vega_datasets
    </py-env>

    <body>
      <div id="altair-output" style="width: 100%; height: 100%"></div>
      

      <py-script output="altair-output">   <--- point output plot to the above div id 
      ...
      altair code 
      ...
      </py-script>

```



```
<html>
  <head>
    <link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />
    <script defer src="https://pyscript.net/alpha/pyscript.js"></script>
    <py-env>    <--- need altair, pandas, vega_datasets for this example... 
      - altair
      - pandas
      - vega_datasets
    </py-env>
    </head>
    
    <body>
      <div id="altair" style="width: 100%; height: 100%"></div>   <--- define a div 
      

      <py-script output="altair">      <--- note output is the altair div above... 

# Paste this example in line for line:
# https://altair-viz.github.io/gallery/trellis_area_sort_array.html
# i.e. the below: 
import altair as alt
from vega_datasets import data
source = data.stocks()
alt.Chart(source).transform_filter(
    alt.datum.symbol != 'GOOG'
).mark_area().encode(
    x='date:T',
    y='price:Q',
    color='symbol:N',
    row=alt.Row('symbol:N', sort=['MSFT', 'AAPL', 'IBM', 'AMZN'])
).properties(height=50, width=400)

      </py-script>

    </body>
</html>
```



<p> Altair behaves pretty well.  Make sure you have altair in the py-env html tag, build a div element with an id, and refer to that id as the output in the py-script tag... pretty simples. So in theory, you just go to [Altair gallery here](https://altair-viz.github.io/gallery/index.html), paste in some code, and it will work out of the box... 




<br>
<br>


### <font color='#00274C'>Current Limitations</font>
- At this time, Pyscript is in **alpha**.  Give it time! It will be improved, more will be added.  Get familiar with it... 
- If you try to load an external python file, it has to be running from html server ? 
- You can import altair and for instance vega_datasets, and thus you will have access to source example data. 
- from pyodide.http import pyfetch. (I use that import to provide a replacement for requests)
- 

<br>
<br>




#### <font color='#00274C'>CONTACT</font>
General questions should be directed to Tom Bresee at <tbresee@umich.edu>.

