# Getting started

Material for MkDocs is a powerful documentation framework on top of [MkDocs],
a static site generator for project documentation.[^1] If you're familiar with
Python, you can install Material for MkDocs with [`pip`][pip], the Python
package manager. If not, we recommend using [`docker`][docker].

  [^1]:
    In 2016, Material for MkDocs started out as a simple theme for MkDocs, but
    over the course of several years, it's now much more than that – with the
    many built-in plugins, settings, and countless customization abilities,
    Material for MkDocs is now one of the simplest and most powerful frameworks
    for creating documentation for your project.

  [MkDocs]: https://www.mkdocs.org
  [pip]: #with-pip
  [docker]: #with-docker

## Installation

### with pip <small>recommended</small> { #with-pip data-toc-label="with pip" }

Material for MkDocs is published as a [Python package] and can be installed with
`pip`, ideally by using a [virtual environment]. Open up a terminal and install
Material for MkDocs with:

=== "Latest"

    ``` sh
    pip install mkdocs-material
    ```

=== "9.x"

    ``` sh
    pip install mkdocs-material=="9.*" # (1)!
    ```

    1.  Material for MkDocs uses [semantic versioning][^2], which is why it's a
        good idea to limit upgrades to the current major version.

        This will make sure that you don't accidentally [upgrade to the next
        major version], which may include breaking changes that silently corrupt
        your site. Additionally, you can use `pip freeze` to create a lockfile,
        so builds are reproducible at all times:

        ```
        pip freeze > requirements.txt
        ```

        Now, the lockfile can be used for installation:

        ```
        pip install -r requirements.txt
        ```

  [^2]:
    Note that improvements of existing features are sometimes released as
    patch releases, like for example improved rendering of content tabs, as
    they're not considered to be new features.

This will automatically install compatible versions of all dependencies:
[MkDocs], [Markdown], [Pygments] and [Python Markdown Extensions]. Material for
MkDocs always strives to support the latest versions, so there's no need to
install those packages separately.

---

:fontawesome-brands-youtube:{ style="color: #EE0F0F" }
__[How to set up Material for MkDocs]__ by @james-willett – :octicons-clock-24:
27m – Learn how to create and host a documentation site using Material for
MkDocs on GitHub Pages in a step-by-step guide.

  [How to set up Material for MkDocs]: https://www.youtube.com/watch?v=xlABhbnNrfI

---

!!! tip

    If you don't have prior experience with Python, we recommend reading
    [Using Python's pip to Manage Your Projects' Dependencies], which is a
    really good introduction on the mechanics of Python package management and
    helps you troubleshoot if you run into errors.

  [Python package]: https://pypi.org/project/mkdocs-material/
  [virtual environment]: https://realpython.com/what-is-pip/#using-pip-in-a-python-virtual-environment
  [semantic versioning]: https://semver.org/
  [upgrade to the next major version]: upgrade.md
  [Markdown]: https://python-markdown.github.io/
  [Pygments]: https://pygments.org/
  [Python Markdown Extensions]: https://facelessuser.github.io/pymdown-extensions/
  [Using Python's pip to Manage Your Projects' Dependencies]: https://realpython.com/what-is-pip/

### with docker

The official [Docker image] is a great way to get up and running in a few
minutes, as it comes with all dependencies pre-installed. Open up a terminal
and pull the image with:

=== "Latest"

    ```
    docker pull squidfunk/mkdocs-material
    ```

=== "9.x"

    ```
    docker pull squidfunk/mkdocs-material:9
    ```

The `mkdocs` executable is provided as an entry point and `serve` is the
default command. If you're not familiar with Docker don't worry, we have you
covered in the following sections.

The following plugins are bundled with the Docker image:

- [mkdocs-minify-plugin]
- [mkdocs-redirects]

  [Docker image]: https://hub.docker.com/r/squidfunk/mkdocs-material/
  [mkdocs-minify-plugin]: https://github.com/byrnereese/mkdocs-minify-plugin
  [mkdocs-redirects]: https://github.com/datarobot/mkdocs-redirects

??? question "How to add plugins to the Docker image?"

    Material for MkDocs only bundles selected plugins in order to keep the size
    of the official image small. If the plugin you want to use is not included,
    you can add them easily:

    === "Material for MkDocs"

        Create a `Dockerfile` and extend the official image:

        ``` Dockerfile title="Dockerfile"
        FROM squidfunk/mkdocs-material
        RUN pip install mkdocs-macros-plugin
        RUN pip install mkdocs-glightbox
        ```

    === "Insiders"

        Clone or fork the Insiders repository, and create a file called
        `user-requirements.txt` in the root of the repository. Then, add the
        plugins that should be installed to the file, e.g.:

        ``` txt title="user-requirements.txt"
        mkdocs-macros-plugin
        mkdocs-glightbox
        ```

    Next, build the image with the following command:

    ```
    docker build -t squidfunk/mkdocs-material .
    ```

    The new image will have additional packages installed and can be used
    exactly like the official image.

### with git

Material for MkDocs can be directly used from [GitHub] by cloning the
repository into a subfolder of your project root which might be useful if you
want to use the very latest version:

```
git clone https://github.com/squidfunk/mkdocs-material.git
```

Next, install the theme and its dependencies with:

```
pip install -e mkdocs-material
```

  [GitHub]: https://github.com/squidfunk/mkdocs-material

NucampLet's review all the main concepts we've covered so far in this course:
●	Variables and Data Types: We learned about the different types of data that JavaScript can handle such as strings, numbers, booleans, null, undefined, and objects. We also covered how to declare and use variables.
●	Operators and Expressions: We discussed the different types of operators (arithmetic, assignment, comparison, logical, etc.) and how they can be used in expressions.
●	Functions: We dove into how to define and call functions, which allow us to encapsulate reusable code.
●	Control Flow: We talked about conditional statements like if and switch, and how they allow us to control the flow of our programs based on certain conditions.
●	While Loops: A control flow statement that allows code to be executed repeatedly based on a given Boolean condition.
●	For Loops: Another type of loop which lets us specify the initializer, condition, and increment/decrement in one line.
●	Arrays: A data structure that can store multiple values in a single variable.
●	Array Methods: We practiced using some built-in JavaScript functions that allow us to manipulate and interact with arrays.
●	Strings and Arrays: We learned how JavaScript treats strings similarly to arrays.
●	Data Handling: Working with and manipulating data in a JavaScript environment.
●	Random Numbers: We learned how to generate and work with random numbers in JavaScript.
●	Scope: We explored the concepts of local vs. global scope, block scope, and function scope, and why this matters.
●	Arrow Functions and Function Expressions: We practiced different ways to write functions for greater control over your code execution.
●	JavaScript Objects: We explored the only non-primitive data type in JavaScript, which is a way to structure a collection of data.
●	Template Literals: We learned a quicker way to combine variables with strings.
●	JavaScript's "this" keyword: We learned about the "this" keyword, which that refers to the object that a method is associated with
●	JavaScript Classes: In programming languages, "classes" are templates for objects, allowing you to create multiple instances of an object easily.
●	Constructors: We learned how to create new instances of objects using a template constructor.
●	Class Inheritance: We learned to extend the properties of a parent class to child classes.
●	Default Function Parameters: We explored ways to define default values for parameters so that a function will work even when data is missing or left out.
●	JSON (JavaScript Object Notation): We learned a lightweight data structure that is easy for humans to read and write, and for machines to parse and generate.
●	Error Handling: We learned how to use Try, Catch, Throw, and Finally to gracefully handle errors in your code or your data stream without crashing your application.


New Concepts and Vocabulary this Week


•	Document Object Model (DOM): a platform and interface that allows programs and scripts to dynamically access and update the content, structure, and style of an HTML document
•	DOM Tree: a visual way to represent the data structure of the DOM and how different nodes and branches relate to each other and the root document
•	Nodes: individual elements in the DOM that can be targeted, read, modified, created, or removed
•	Traversing the DOM: a way to move through the document to select nodes that are adjacent to other nodes
•	Cloning: making a copy of a node or its entire branch
•	Events: user actions that can trigger certain behaviors or functions
•	Event Objects: the way an event is structured in JavaScript, and the methods that are available to use on an event
•	Handlers and Listeners: code that "listens" for an event to happen, and then invokes a function to respond to that event


 


Learning Objectives
By the end of this week, you should be able to:
•	Understand the DOM Structure: Students will grasp the hierarchical structure of the DOM and how it represents the content of a web page, allowing them to interact with HTML elements through JavaScript.
•	Manipulate the DOM: Students will learn to select, modify, add, and remove HTML elements, attributes, and content using various DOM methods, enhancing their ability to dynamically manipulate web pages.
•	Work with Event Listeners: Students will understand different types of browser events and how to use event listeners to handle user interactions such as clicks, keyboard inputs, and mouse movements.
•	Create Interactive Web Pages: By connecting DOM manipulations and event handling, students will gain the skills to create highly interactive and responsive web pages that respond to user actions in real time.
•	Integrate JavaScript with Bootstrap: Building on a previous project, students will learn how to update Bootstrap components with custom JavaScript, tailoring the behavior to specific project needs.
•	Develop a Shopping List Application: As part of this week's code challenge, students will apply their knowledge of the DOM and event handling to create a functional shopping list application, demonstrating their ability to create real-world web applications.
•	Build an Interactive Game: This week's workshop assignment will involve creating a simple yet engaging interactive game, allowing students to explore more complex event handling and DOM manipulation techniques.
•	
