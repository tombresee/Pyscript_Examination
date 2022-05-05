


I want you to start by clicking [this link](https://pyscript.net/examples/panel_stream.html).  

Wait a few seconds.  

What do you think of it ? 

It was built in a very unusual manner...


<p align="center"><img src='https://raw.githubusercontent.com/pyscript/pyscript/main/pyscriptjs/examples/logo.png' alt='py.png' width="200"></p>



<br>

### 1. &ensp; What is Pyscript ? 

abc

* <https://pyscript.net/>
* <https://github.com/pyscript>
* <https://github.com/pyscript/pyscript/blob/main/GETTING-STARTED.md>
* [Original Anaconda Blog](https://www.anaconda.com/blog/pyscript-python-in-the-browser)





<br>

### 2. &ensp;  Cut to the chase and get to it...

Ok, it's very simple. 

`<p>This is normal text - <b>and this is bold text</b>.</p>`

HTML tags.  Yes, we are going way back.  Like the [simple stuff](https://www.w3schools.com/tags/tag_comment.asp). 

An HTML tag is a piece of markup language used to indicate the beginning and end of an HTML element in an HTML document.  Yes, got it.  

> <u>The new PyScript project lets you embed Python programs *directly* in HTML pages and execute them within the browser without any server-based requirements.</u>


<br>


**Your HTML building blocks:**
- `<py-script>` - indicated to HTML to to execute the python commands 


<br>


**The Process:**

1. Add the exact css stylesheet href link below
2. Add the exact script .js reference below 
3. Just write your code as if you were in any other IDE, making sure it is between the `<py-script>` tags...


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







<br>

### 3. &ensp; 


















<br>

### 5. &ensp;  How do I know if my particular python library is supported ???

If you make the [list](https://github.com/pyodide/pyodide/tree/main/packages), you are supported. 

All those hours you spent learning numpy, pandas, matplotlib, seaborn, altair, bokeh, scipy, **networkx**, etc are about to pay off...Even the mighty **scikit-learn is supported**. 




<br>
<br>
<br>