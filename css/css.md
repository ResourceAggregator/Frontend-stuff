# Guide to css

### Index
 A. Specificity in css 
     
     1. Order in css
     2.  Class vs Id (ID has a higher priority than class)
     
3.  CSS Selectors
4.  Colors
5.  Making Sense of Units in CSS
6.  Understanding CSS Display : none, inline , block, inline-block
    
        a. Display: None   vs.  Visibility: Hidden 
        b. inline vs block (div vs span) 
7. CSS Flex
8. Css Clip Path
----
## 1.Order in css
 This is because in CSS, the order in which you write your declarations matter. **If a conflicting declaration is found further down the styles document, it is honored.**

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

## 3. CSS Selectors

```
- Simple selectors (select elements based on name, id, class)
- Combinator selectors (select elements based on a specific relationship between them)
- Pseudo-class selectors (select elements based on a certain state)
- Pseudo-elements selectors (select and style a part of an element)
- Attribute selectors (select elements based on an attribute or attribute value)
```


2. Combinator selectors

A CSS selector can contain more than one simple selector. Between the simple selectors, we can include a combinator. There are four different combinators in CSS:

- descendant selector (space)
- child selector (>)
- adjacent sibling selector (+)
- general sibling selector (~)

https://www.w3schools.com/Css/css_combinators.asp

difference between descedant and child selector

- The child combinator selector (>) targets an element that is a child of its parent. It does not target descendants beyond the children.

- The descendant selector targets the child and other descendants of the parent/ancestor.


![Screenshot](https://user-images.githubusercontent.com/43414928/89120761-6e7d0b80-d4d6-11ea-8ae8-5af23bc860ee.png)

3. Pseudo-class selectors

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

4. Attribute selectors

Selects all elements that have the given attribute.

Syntax: [attr] [attr=value] [attr~=value] [attr|=value] [attr^=value] [attr$=value] [attr*=value]

https://www.w3schools.com/css/css_attribute_selectors.asp


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
 
 
 
 6. ## Understanding CSS Display
 
#### a. Display: None   vs.  Visibility: Hidden 

![image](https://user-images.githubusercontent.com/43414928/87634529-11096080-c75b-11ea-9063-5bde3fd88a2e.png)
![image](https://user-images.githubusercontent.com/43414928/87634552-1e264f80-c75b-11ea-99d2-62f971f3a77e.png)
![image](https://user-images.githubusercontent.com/43414928/87634565-27172100-c75b-11ea-9bd6-30180f8118e7.png)

 Visibility: hidden hides the tag, but it still takes up space and affects the page. In contrast, display: none removes the tag and its effects for all intents and purposes, but the tag remains visible in the source code. 

<br/> 
#### b. inline vs block (div vs span) 
 
- div is a block element
- span is an inline element

![image](https://user-images.githubusercontent.com/43414928/87633648-59278380-c759-11ea-8b0b-fc543d85a590.png)
![image](https://user-images.githubusercontent.com/43414928/87633668-63e21880-c759-11ea-94fd-4801f4b01803.png)


![image](https://user-images.githubusercontent.com/43414928/87634071-33e74500-c75a-11ea-801f-6f7fe6dd2a4b.png)

```
Inline elements don’t accept width or height properties, and top-bottom margin
 **display: inline-block** declaration shows both the characteristics of inline and block-level elements.
```
![image](https://user-images.githubusercontent.com/43414928/87634920-d653f800-c75b-11ea-9f4d-cca687ad8392.png)



## 7. CSS Flex

- http://flexbox.malven.co/

- https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- https://yoksel.github.io/flex-cheatsheet/#section-justify-content



## Css Clip Path

Tool: https://bennettfeely.com/clippy/
https://css-playground.com/view/65/clipping-paths-with-clip-path

https://getwaves.io/

