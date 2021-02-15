# CSS Variables
## Font-Awesome Icons, Text-Shadow Box-Shadow, Browser Prefixes, Semantic Tags, Emmet Workflow


## 01. CSS Variables aka Custom Properties 

hold a value and reuse it
--varName::value 
property:var(--varName)
scope
:root{} === global
element === local
any property

Code Example
```
/* setting the color variable to assign color to the properties, prevent typo or repetitive work (copy/paste) */
:root {
    --primaryColor: #1313fa;
    --secondaryColor: #f15025;
    --mainTransition: all 0.4s linear;
}
.heading {
    color: var(--primaryColor)
}
.second-heading {
    color: var(--primaryColor);
    transition: var(--mainTransition);
}
.second-heading:hover {
    color: var(--secondaryColor)
}
div {
    --primaryRed:red;
}
.main-text {
    color: var(--primaryRed);
}
.third-heading {
    color: var(--primaryRed);
}
/* third-heading doesn't change the color to the variable --primaryRed, because it is inherited from html, not from div (can check in the Inspect/Styles) */
```

## 02. ICONS - Font-Awesome Icons
Free, easy to get up running, simple syntax

Code Example
```
HTML

<!-- icons CDN -->
    <script src="https://kit.fontawesome.com/0326323446.js" crossorigin="anonymous"></script> 

<!-- icons download -->
    <link rel="stylesheet" href="./fontawesome-free-5.15.2-web/css/all.css">
```
```
CSS

.fa-home {
    color: crimson;
}
.social-icon {
    font-size: 4rem;
    color:dodgerblue;
} 
```

## 03. Text-Shadow Box-Shadow

- Text-Shadow: X Y blur-radius color
- Box-Shadow: X Y blur-radius color 

There are many text- or box-shadow generators, you can choose one to copy the syntax.

Code Example
```
h1 {
    text-shadow: 1px 1px 3px red;
}
.box {
    width: 200px;
    height: 100px;
    background: royalblue;
    margin: 20px;
    box-shadow: 3px 5px 5px greenyellow;
    transition: all 0.5s linear;
}

/* 03-1. Browser Prefixes - according to the browser version, can use https://autoprefixer.github.io/ instead typing by yourself */

.box:hover {
    -webkit-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75); 
    -moz-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75); 
    box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
} 
```

## 04. Semantic Tags 

https://www.w3schools.com/html/html5_semantic_elements.asp

A semantic element clearly describes its meaning to both the browser and the developer.

- Examples of non-semantic elements: div and span - Tells nothing about its content.

- Examples of semantic elements: form, table, and article - Clearly defines its content.


## 05. Emmet Workflow 

If you use visual studio code, you can use emmet. It is the suggestion when you type the syntax. 

Code Example
```
Example 1: h1.main.secondary === <h1 class="main secondary"></h1> 

Example 2: h1#main === <h1 id="main"></h1>

Example 3: h3#third.third === <h3 id="third" class="third"></h3>

Example 4: #header.header-1.header-2 === <div id="header" class="header-1 header-2"></div>

Example 5: div>ul>li ===
<div>
    <ul>
        <li></li>
    </ul>
</div>

Example 6: div>ul>li*5
<div>
    <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</div>

Example 7: ul>li*6{$} ===
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li>6</li>
</ul>
```