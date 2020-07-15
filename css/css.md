# Guide to css

### Index

1. Order in css
2.  Class vs Id
3.  Pseudo-class selectors
4.  Colors
5.  Making Sense of Units in CSS


----
## 1.Order in css
 This is because in CSS, the order in which you write your declarations matter. If a conflicting declaration is found further down the styles document, it is honored.

##### Specificty in CSS
The points are calculated off of the selectors in the CSS rule.
Consider the following
```
header h1 {
  color: red;
}
h1 {
  color: blue;
}
```

From the last lesson, you would expect the color of h1 to be blue. But, in this case that is wrong.
Red is the and. The selector header h1 has more points than h1 so its declaration, color: red wins over color: blue

![image](https://user-images.githubusercontent.com/43414928/87521221-b3fda400-c6a1-11ea-8a63-400050097362.png)

**How exactly does header h1 have a higher point than h1?**

header h1 contains 2 elements. header and h1. An element gets 1 point (see the graphic above). Thus, this results in 2 points.

h1 has just one element. This results in only 1 point.

header h1 is the obvious winner here, as 2 is greater than 1

#### Reference
1. [Understanding Order and Specificity in CSS](!https://www.educative.io/courses/the-complete-advanced-guide-to-css/NE06o49n7P2)

## 2. Class vs Id

![image](https://user-images.githubusercontent.com/43414928/87520118-253c5780-c6a0-11ea-8e70-707cd4fd9beb.png)

## 3. Pseudo-class selectors

> pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). For example :hover,  :first-child, :nth-child

The Pseudo-element selectors are very much like the Pseudo-class selectors in terms of how they are written. Except that the CSS3 specification states that they should be written with double colons.


----
#### Syntax
```
selector:pseudo-class {
  property: value;
}
```
```
selector::pseudo-element {
  property: value;
}
```

#### Example
```
a:link {
  color: #FF0000;
} 
a:visited {
  color: #00FF00;
}
a:hover {
  color: #FF00FF;
}
```

The order in which you define these link pseudo-selectors is important. It should follow the order **LVHA (kinda like LoVe HA!)** i.e :link, :visited, :hover, and finally :active


##### * Before and After Pseudo-element Selectors 
:before places the content before any child elements within the parent element, and :after places the content after every child element within the parent.

Content added using pseudo-elements is only visually displayed. It is not inserted into the DOM.



## 4.Colors
a. RGB Value

      - rgb(255,0,0) : red 
      - rgb(0,0,255) : blue
      - rgb(90, 56, 222) :purple

b. Hex value

The general format is #RRGGBBwhere R is Red, G is Green and B is Blue.
Unlike RGB values that span 0 - 255, hex values span 00 - FF where 00 is the lowest and FF the highest.

      - #FF0000 : red
      - #00FF00 : green


## 5. Making Sense of Units in CSS

Below are the units :

- Pixels (px) :This will ignore any preferences the user may have set in their own browsers.

- Points (pts) and Picas (PC) : Points (and Picas) are absolute length units, more like centimeters and millimeters.  What this means is that their units are fixed and a length expressed in any of these will apply exactly that size. Therefore they are not recommended for screen sizes because screen sizes vary so much.

        1 Pica = 12 Points

- Ems (em) : The em is a relative font measurement. In CSS, 1em is equal to the user’s default font size. This is usually the browsers default, 16px.

        1 em = 16px

 1em may also represent the font size of the parent element. Which is why it is loosely described as the “current font size”.
         
        font-size: 2em;  // This is equal to 16px * 2
 
[The problem with the EM unit.](!https://www.educative.io/courses/the-complete-advanced-guide-to-css/q28DnjLq8xy)


- Percentages (%) : Percentages, just like ems and rems are resizable by the user.

- Viewport height (vh) and width (vw): The vw and vh units are determined based on the viewport i.e the entire display screen.

 vw stands for viewport width, and vh stands for viewport height.
