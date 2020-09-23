# django-labeller

#### A light-weight image labelling tool for Python designed for creating segmentation data sets.

- compatible with Django and Flask
- polygon, box, point and oriented ellipse annotations supported
- polygonal labels can have disjoint regions and can be editing using paintng and boolean operations; provided by
  [polybooljs](https://github.com/voidqk/polybooljs)
- can use the [DEXTR](http://people.ee.ethz.ch/~cvlsegmentation/dextr/) algorithm to automatically generate
  polygonal outlines of objects identified by the user with a few clicks; provided by the
  [dextr](https://github.com/Britefury/dextr) library
  
Django Labeller in action:
![Django labeller movie](doc/dextr_boolean_cleanup_v1_small.gif "Django Labeller in action")


## Biggie Instructions

We will be using the Flask version of "Django-Labeller". This should already be installed on the server. Follow instructions under "For Flask Web App".


## Installation

In case you need to git clone the Biggie Version Locally: 

```shell script
> git clone https://github.com/biggie-inc/django-labeller.git
> python setup.py install
````

To use it as a library, either with Flask or Django, install from PyPI:

```shell script
> pip install django-labeller
```

### For Flask Web App

*1. Before running the program, ensure all photos that need to have outlines drawn are located in ../django-labeller/images/

*2. An example Flask-based web app is provided that displays the labelling tool within a web page. To start it:

*3. cd into the same directory into which you cloned the repo. Example: 
```shell script
> cd django-labeller/
```

*4. Run the following script:
 
```shell script
> python -m image_labelling_tool.flask_labeller_mod 
```

*5. Now open `127.0.0.1:5000` within a browser. This is a local server where the app will run in a browser window.

<!-- This function is currently not working. If you want to load images from a different directory, or if you installed from PyPI, tell `flask_labeller`
where to look:

```shell script
> python -m image_labelling_tool.flask_labeller --images_pat=<images_directory>/*.<jpg|png>
```
--!>

<!-- DEXTR does not seem to work at this moment
#### Flask app with DEXTR assisted labelling

<!--First, install the [dextr](https://github.com/Britefury/dextr) library:

```shell script
> pip install dextr
```

<!--Now tell the Flask app to enable DEXTR using the `--enable_dextr` option:

```shell script
> python -m image_labelling_tool.flask_labeller --enable_dextr
````
 
<!--The above will use the ResNet-101 based DEXTR model trained on Pascal VOC 2012 that is provided by
the dextr library. 
If you want to use a custom DEXTR model that you trained for your purposes, use the `--dextr_weights` option:

```shell script
> python -m image_labelling_tool.flask_labeller --dextr_weights=path/to/model.pth
````
--!>


## Libraries, Credits and License

Incorporates the public domain [json2.js](https://github.com/douglascrockford/JSON-js) library.
Uses [d3.js](http://d3js.org/), [jQuery](https://jquery.com/), [popper.js](https://popper.js.org/),
[PolyK](http://polyk.ivank.net/), [polybooljs](https://github.com/voidqk/polybooljs) and
[Bootstrap 4](https://getbootstrap.com/docs/4.0/getting-started/introduction/).

This software was developed by Geoffrey French in collaboration with Dr. M. Fisher and
Dr. M. Mackiewicz at the [School of Computing Sciences](http://www.uea.ac.uk/computing)
at the [University of East Anglia](http://www.uea.ac.uk) as part of a project funded by
[Marine Scotland](http://www.gov.scot/Topics/marine).

It is licensed under the MIT license.
