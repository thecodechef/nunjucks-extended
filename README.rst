Nunjucks Extended
======

A Better Nunjucks Syntax Highlighter for Sublime Text


.. image:: https://img.shields.io/github/tag/thecodechef/nunjucks-extended.svg?style=flat-square
    :target: https://github.com/thecodechef/nunjucks-extended
    :align: right

.. image:: https://img.shields.io/github/downloads/thecodechef/nunjucks-extended/latest/total.svg?style=flat-square
    :target: https://github.com/thecodechef/nunjucks-extended
    :align: right

.. image:: https://img.shields.io/packagecontrol/dt/Nunjucks%20Extended.svg?style=flat-square
    :target: https://packagecontrol.io/packages/Nunjucks%20Extended
    :align: right

Table of Contents
-----------------
- Installation_
- Contributing_
- Authors_
- Examples_


.. Installation:
Installation
------------

Package Control:
++++++++++++++++

- Open up Sublime Text
- Press ``shift+ctrl+p`` and type in ``Package Controll:``
- Then Type in ``Install Package`` and Press Enter
- Search for ``Nunjucks Extended`` and Press Enter
- Restart Sublime Text And Enjoy!

Manually:
+++++++++
- Change directories into your Packages Directory
    - **Windows** ``$env:appdata\Sublime Text 3\Packages\``
    - **Mac**  ``~/Library/Application\ Support/Sublime\ Text\ 3/Packages/``
    - **Linux** ``cd .config/sublime-text-3/Packages/``
- ``git clone http://github.com/thecodechef/nunjucks-extended.git``
- Restart Sublime Text and Enjoy!


.. Contributing:
Contributing
------------

Adding Features
+++++++++++++++

- First off create a fork of this repo
- then in your terminal type ``cd git clone http://github.com/[your-username]/nunjucks-extended.git [path-to-place-repo]``
- to create a feature branch: ``git checkout -b my-feature-branch`` 



.. Authors:
Authors
-------

- **Jeremy Bolding**
   - Github_
   - Twitter_


.. _Github: http://github.com/thecodechef
.. _Twitter: http://twitter.com/thecodechef

.. Examples:
Examples
--------

Tag Blocks
++++++


AsyncAll Tag Example
####################
    .. code:: jinja
      
      {% set links = [
        "../css/bootstrap.min.css",
        "../css/font-awesome.min.css",
        "..css/main.min.css"
      ] %}
      
      {% asyncAll link in links %}
        <link rel="stylesheet" href=link />
      {% endasyncAll %}

      //=> <link rel"stylesheet" href="../css/bootstrap.min.css"/>
      //=> <link rel"stylesheet" href="../css/font-awesome.min.css"/>
      //=> <link rel"stylesheet" href="../css/main.min.css"/>


AsyncEach Tag Example
#####################
    .. code:: jinja
      
      {% set links = [
        "../css/bootstrap.min.css",
        "../css/font-awesome.min.css",
        "..css/main.min.css"
      ] %}
      
      {% asyncEach link in links %}
        <link rel="stylesheet" href=link />
      {% endasyncEach %}

      //=> <link rel"stylesheet" href="../css/bootstrap.min.css"/>
      //=> <link rel"stylesheet" href="../css/font-awesome.min.css"/>
      //=> <link rel"stylesheet" href="../css/main.min.css"/>


Block Tag Example
#################
    .. code:: jinja

      {% set name = "Jeremy" %}

      {% block content %}
        Hello, {{ name }}
      {% endblock %}

      //=> Hello, Jeremy


Call Tag Example
#################
    .. code:: jinja

      {% call add(1, 2) -%}
      The result is
      {%- endcall %}

      //=> The result is: 3


Filter Tag Example
#################
    .. code:: jinja
      
      {% filter replace("force","forth") %}
      may the force be with you
      {% endfilter %}

      //=> may the forth be with you


For Tag Example
#################
    .. code:: jinja
      
      {% set items = ["Nunjucks is Awesome"] %}

      <h1>Posts</h1>
      <ul>
      {% for item in items %}
        <li>{{ item.title }}</li>
      {% else %}
        <li>Nothing to Show</li>
      {% endfor %}
      </ul>

     //=> <h1>Posts</h1>
     //=>  <ul>
     //=>   <li>Nunjucks is Awesome<li>
     //=>  </ul>


If Tag Example
################
    .. code:: jinja

      {% set isActive = true %}

      {% if isActive %}
        <li class="active">Link</li>
      {% elif isActive !== true or false %}
        <li>Undefined</li>
      {% else %}
        <li>Link<li>
      {% endif %}

      //=> <li class="active">Link</>

Macro Tag Example
####################
    .. code:: jinja

      {% macro add(x,y) %}
      <p>{{ caller() }}: {{ x + y }}</p>
      {% endmacro %}


Raw Tag Example
##################
    .. code:: jinja

      {% raw %}
        {{ name }}
      {% endraw %}


      //=>  {{ name }}




Inline Tags
++++++


Extends Tag Example
#####################
    .. code:: jinja

      {% extends "_layouts/default.njk" %}


      {% block content %}
      {% endblock %}


Import Tag Example
#####################
    .. code:: jinja

      {% import "_macros/navbar.njk" %}

      {% import "_macros/navbar.njk" as navbar %}

      {% from "_macros/navbar.njk" import navItem %}

      {% from "_macros/navbar.njk" import navItem,activeNavItem as activeItem %}


Include Tag Example
######################
    .. code:: jinja

      {% include "_partials/modal.njk" %}

      {% include "_partials/modal.njk" ignore missing %}


Set Tag Example
###################
.. code:: jinja
  :number-lines:

  {% set name = "Jeremy Bolding" %}

  {% set name %}
      Jeremy Bolding
  {% endset %}
       
  {{ name }}
