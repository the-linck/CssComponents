# Contents
* [The Project](#the-project)
  * [Structure](#structure)
  * [Conventions](#conventions)
  * [Release](#release)
* [Documentation](#documentation)

# The Project

Firstly, **CSS Components, is a PURE CSS library for front-end development.**

The reason this project started was it developer (yeah, me) being tired of seeing how websites are unnecessarily heavyweight and with slow loading due the use of Javacript and JS libraries on their apperence - wich leads to poor performance and bad programming pratices.

Thinking on the problem of excessive JS use and the lack of several (normally most) useful things in existing pure CSS libraries that do exist in JS powered ones, i've got to one simple conclusion:
*maybe I sould make my own library, using only CSS*.
And   . why not do it?

Initially, it would be a simple copy of major front-end libraries and frameworks, remade with only CSS. But after some redesigns and two years learning more of web programming with pratice, I've decided to go back at the begining and redo the project with the following focuses:

1. **Simplicity**  
It must be easy to use and at the same time make developers job easier;
2. **Performance**  
It must be lightweight and use the miniimum ammount of code needed;
3. **Accessibility**  
It should help to make the web more accessible to everyone;
4. **Standardization**  
It should help to make the websites structure close to common standarts (wich helps with SEO);
5. **Visual**  
Of couse, the library must provide a good visual to sites who use it.

Given that big objetives, the project has 3 long term goals:

1. Be a really useful library to front-end development
2. Implement all accessibility (ARIA) rules and standarts
3. Implement all schema.org standart types

Of couse that's very, very hard to do. So any help is very welcome. ;)


## Structure

The design rules applied here are quite simple:

1. **Every file directly in the project's CSS folder act as a module**  
Except for *complete.css*, that's a shorcut to import all the modules;
2. **The modules are independent from all others (except the core)**  
The Core Module defines basic rules that all modules will follow and use and some utilitary CSS styles that can be used everywhere on front-end.  
Everything that doesn't fit that criteria must have it's own module;
3. **Modules (other than Core) serve to implement components**  
Being a button, a dialog or even a whole article (like this), every kind of thing that can be used in a web page and is supported by the library is treated as a component.  
If we use some OOP concepts, a component would be equivalento to a Class: a standart model of something;
4. **When possible, components must be groupped** 
If two or more components share most of their functionality (like *dialog* and *alertdialog* do), they must be implemented in the same module. That helps to keep the project simple and lightweight;
5. **Material Design color palletes are used for every color on this project, in all modules** 
The library's user is free to use them as weel if wish so.  
We already define our own primary color palette in Core Module (Grey) using CSS Propreties.  
To use other pallete as primary, just import it on the page after the library and the "color variables" will be overriden.  
*Remember that we choose no default accent color.*

The project's file struture is the following:

* **CSS {folder}**  
Where the magic happens
  * **pallete {folder}**  
  The color palettes avaliable on the project
      * **accent {folder}**  
      CSS files that register every pallete of the accent colors variables
      * **primary {folder}**  
      CSS files that register every pallete of the primary colors variables
  * **core.css {file}**  
  Where universal rules and styles are defined
  * **compllete.css {file}**  
  Shortcut to import all modules at once
  * Other modules ".css" files  .


## Conventions

Like said above, everything may be a component. Like a class in OOP, a compoent may be a link, a standart data document strucuture (like a blog post), a tooltip, almost anything.
Here are the "ground rules" we use to develop the components:

* A given component, a button for example, will have it's own unique properties, but at the same time may have properties shared with other components - like buttons and articles may share the same default font color;
* The most basic and/or universal properties that can be shared by most (or even all) components will be declared directly on the Core Module, making them universal.  
When components shared most of their properties, they will be both implemented in the same
module for simplicity;
* Components that group other components (like a radiogroup) follow the previous rule;
* We use attributes for styling to give a more semantic and declarative syntax on the HTML;
* All our custom attributes use the **data-css-** prefix, to avoid name collision with another libraries and/or your code.
* By default, all components use the primary colors.  
To use the accent pallete on a component (or part of it), you must use the **data-css-accent** attribute.


## Release

Beign a project currently kept by a single developer, wich works on this in his free time, its undoable to mantain a stricly regular release scheme.
But, I do plan to release updates in a role releasing like model: as soon as its done and tested, it will be released.

# Documentation

This project is made through it's documentaion, in other words: everything in the project is used to make the documentation.
At the same time it's difficult to have a component not documented, and our documentation is made using the same project it explains.
Check it out:

[CSS Components documentation](http://the-linck.github.io/CssComponents/)