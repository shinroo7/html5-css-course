# CSS Transform
## translate(), scale(), rotate(), skew()

### translate(): move objects around

Code Example
```
div {
    width: 150px;
    height: 150px;
    display: inline-block;
}
.one {
    background: tomato;
    transform: translateX(50%); 
}
/* 50% is related to the width and height setting */
.two {
    background: lawngreen;
    transform: translateY(30px);
}
.three {
    background: blueviolet;
    transform: translate(20px, 50px);
}
```

### scale(): change the size of objects

Code Example
```
div {
    width: 150px;
    height: 150px;
    display: inline-block;
}
.one {
    background: tomato;
    transform: scaleX(0.5);
}
.two {
    background: lawngreen;
    transform: scaleY(2);
}
.three {
    background: blueviolet;
    transform: scale(0.5, 0.5);
}
```

### rotate(): change the direction of objects

X/Y is hard to see the direction change, Z is the often use one

Code Example
```
div {
    width: 150px;
    height: 150px;
    display: inline-block;
}
.one {
    background: tomato;
    transform: rotateX(95deg);
}
.two {
    background: lawngreen;
    transform: rotateZ(45deg);
}
.three {
    background: blueviolet;
    transform: rotateY(95deg);  
}
```

### skew(): change the objects to trapezium

Code Example
```
div {
    width: 150px;
    height: 150px;
    display: inline-block;
}
.one {
    background: tomato;
    transform: skewX(40deg);
}
.two {
    background: lawngreen;
    transform: skewY(-20deg);
}
.three {
    background: blueviolet;
    transform: skew(40deg, -20deg);
}
```


# CSS Transition
## transition-property:, transition-duration:

Code Example
```
div {
    width: 150px;
    height: 150px;
    display: inline-block;
}
div:hover {
    background: cyan;
}
.one {
    background: tomato;
}
.two {
    background: lawngreen;
}
.three {
    background: blueviolet; 
    transition-property: background, border-radius;
    transition-duration: 3s, 1s;
}
.three:hover {
    border-radius: 50%;
}
```

## transition delay, shorthand

elements: objects, change over time, delay time

Code Example
```
div {
    width: 150px;
    height: 150px;
    display: inline-block;
}
.one {
    background: tomato;
}
.two {
    background: lawngreen;
}
.three {
    background: blueviolet; 
    transition-property: background, border-radius;
    transition-duration: 3s, 1s;
    transition-delay: 1.5s;
    /* shorter text*/
    transition: background 3s 2s, border-radius 4s 1.5s;
    /* even shorter text*/
    transition: all 4s 2s;
}
.three:hover {
    border-radius: 50%;
    background: cyan;
}
```

## How the transition takes place

transition-time-function: (here)
transition:all 3s here 5s;
ease = default
ease = slow start, fast, slow end
linear = same speed start to end
ease-in = slow start
ease-out = slow end
ease-in-out = slow start, fast, slow end

Code Example
```
div {
    width: 100px;
    height: 100px;
    background: blue;
    color: white;
    margin: 15px;
    transition: all 1s;
}
div:hover {
    transform:translateX(100px) ;
}
/* We can write transition: all 1s ease;, but since there is transition in all div, here we can use timing-function */
.ease {
    transition-timing-function: ease;
}
.linear {
    transition-timing-function: linear;
}
.ease-in {
    transition-timing-function: ease-in;
}
.ease-out {
    transition-timing-function: ease-out;
}
.ease-in-out {
    transition-timing-function: ease-in-out;
}
```

## Transition 0 = 100%, Animation 0 1% 2%...100%

Code Example
```
div {
    width: 200px;
    height: 100px;
    color: white;
    margin: 10px;
}
.transition {
    background: tomato;
    transition: all 2s linear;
}
.transition:hover {
    background: yellowgreen;
    transform: translateX(100px);
}
.animation {
    background: turquoise;
    animation-name: move;
    animation-duration: 10s;
    animation-iteration-count: 2;
    animation: move 5s infinite;
} 

/* the percentage is related to the duration setting */

@keyframes move {
    0% {
        transform: translateX(20px);
    }
    50% {
        transform: translateX(50px);
        background: violet;
    }
    75% {
        transform: translateX(-100px);
        background: yellow;
    }
    100% {
        transform: translateX(20px);
        background: blue;
    }
}
```

## Animation-fill-mode

What values are applied by the animation outside the time it is executing

Code Example
```
div {
    width: 200px;
    height: 100px;
    color: white;
    margin: 10px;
}
.animation {
    background: turquoise;
    animation: move 5s 2;
    animation-fill-mode: forwards;
}
/* instead of staying at original opacity 1, when setting of fill-mode is forward, the ending will stay at the last setting which the opacity is 0.5 */

@keyframes move {
    0% {
        opacity: 0;
    }
    25% {
        transform: translateX(200px);
        opacity: 0.25;
    }
     50% {
        transform: translateX(-100px);
        opacity: 1;
    }
     100% {
        transform: translateX(0);
        opacity: 0.5;
    }
}
```