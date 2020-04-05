# Cirlce CSS
## Everything is up to you
Circle CSS **keeps evolving**. there is no end.

* Anyone can easily do markup and refactor of markup.
* This is close to something like a FrameWork.
* This has a kind of Markup Patterns, inspired by Bootrap, FLOCSS, BEM, Atomic-Design, Scopded CSS and Object-Oriented Programing.

## Three Concepts

1. ***Readablity***
* Circle CSS remodels Rule of BEM in order to resolve complexity of nest-element patterns.
* This has Simple Naming Rules realting to each of layers.
2. ***Flexibility***
* This is able to tolerate other CSS FWs, for expamles Boostrap, Material UI and etc.
* You can edit, delete, and add Break Points.
* You can change priority of min and max for media query.

3. ***Easy of Imporvement***
* This offers simple patterns of Improvement.

---

## What merits does Circe CSS have?

* Ovbiously, Circle CSS lets you to be conscious on relation among Naming Rule, Layer, CSS and Proparty when you are coding or refactoring. Then, it becomes easier to guess what styles a class has, as soon as you see the class.

* As more you are coding by Circel CSS, as more the number of utility css is increasing **systematically**. Of course, at the same time, your skill will be getting better.

* It is easy that you move CSS from a previous project to new project.


## What demerits does Circe CSS have?
* You need to get accustomed to Rules of Circle CSS.&nbsp;&nbsp;&nbsp;Circle CSS has some operating rules when your coding, chosing one of layers, styling, refactoring and moving. But, please take it easy Beacause the rules are simple. If you are only cousious on relation among Naming Rule, Layer, CSS and Proparty, you can find operating theory of Circle CSS. If you are mature to markup, you understand that the theory is much close to your markup theory.

---

## Directory
  * SCSS
    * store&nbsp;:&nbsp; **Shared Script** which are first imported in the others.
      * function&nbsp;:&nbsp;function, mixin.
      * valuabales&nbsp;:&nbsp; color assets, break points and etc.
    * common&nbsp;:&nbsp;**Common styles** which All projects can use.
      * foundation
      * utility&nbsp;:&nbsp; common utility in all projects.
    * project&nbsp;:&nbsp; project.
      * objects
      * pages
    * other&nbsp;:&nbsp; other styles
      * animation
      * js
    * common.scss
    * project.scss
    * other.scss

**Store** is the most important. This must be first importend in common.scss, project.scss and other.scss.
Each of common.scss, project.scss and other.scss are use functions and valueblse which *store* has.

Next to **store**, you should import scss in abstract order.
For Eample,  object/other, project/page in project.scss.

Head of Html shoulde have links in the following order.

\<link href="/css/common.css" rel="stylesheet">

\<link href="/css/project.css" rel="stylesheet">

\<link href="/css/other.css" rel="stylesheet">

---

## Layers
Each of Layer have assign prefix.

* ***Layout***
  * l-
  * header, main, footer
  * contains moudles or the others.
* ***Module***
  * m-
  * contains components or dose components and atomics
  * mainly has arranging styles of margin, padding, float for layers Directly below.
* ***Components***
  * c-
  * contains atomics or dose component and atomics
  * mainly has arranging styles of margin, padding, float for layers Directly below, Atomic or Nest Component.
* ***Atomic***
  * a-
  * only contains Elementary particle. no elements.
* ***Elementary particle***
  * ep-
  * inside Atomic, parts for exmaple, logo, text and etc.
  * You should not use this layer if you can.
---
## Skeleton Patterns

**Simple Pattern**

No. 1 recommended

Nest Block of BEM is tolerated because you can make reuselful css.

* l-Header
  * a-Logo
  * a-Txt

* l-Header
  * a-Logo
  * c-Nav
    * a-Txt1
    * a-Txt2
    * a-Txt3

* l-Main
  * m-Section
    * c-Card
      * a-Txt1
      * a-Txt2
      * a-Txt3
    * c-Card
      * a-Txt1
      * a-Txt2
      * a-Txt3

**Nest Element Pattern**

compromise.
This is not reusefull.

* c-Card
  * a-Img
  * a-Ttile
  * a-Sub
  * c-Card__inner-list
    * a-Txt
    * a-Txt


**Mediate Element Pattern**

Mediate Element is a coined word in Cirlce CSS.
This bridges the gap between blocks.
But you don't use, This can make infinit nesting.

* c-Card
  * a-Img
  * a-Ttile
  * a-Sub
  * c-Card__Inner&nbsp;:&nbsp; This is Mediate Element.
    * c-Card-Iner
      * a-Txt
      * a-Txt

---
## How to Operate

### Basically Step
1. **Start Styling**
  * make scss file in  project/page/.
  * It is recomendale that file name is as same as body id.

2. **Scoped SCSS**
  * wrapp all css by #body-id in each of scss file.
  * It realizes Scopde CSS. Finally, You can find that you just need to write css of differance among each of scss file in  project/page/.

Afterwards, as usual, write css in the scss file.

### Refactoring Step
1. **find Reusable CSSs**
* chage prefix to **u-** and put together them in the scss file  When you find reusable CSSs.


2. **Common CSSs in Project Scss Files**
* in a similar way chage prefix to **u-** and put together When you find reusable CSSs in the other scss file in project/page/. If you find Common CSSs in reusable CSSs, move the Common CSSs into scss file in /project/object/other. If you want to make scss file, you can do. It is up to you.

If you find reusable design component in a production project, in a similar, you can do refactor.

### Final Refactoring Step

**move to Common Directory**

move the Common CSSs in Project Scss Files into *Common Directory*
if you find that you can repeatedly use the Common CSSs in some production projects.
If you want to make scss file, you can do. It is up to you.

---

## Chips of using Default Utility of Circle CSS.

1. **set Display Width**
* set value with v_container_width.

2. **set Margin-Top and Margin-Bottom between Content**
* set value with v_wrapper.

2. **use Utility**

* main.l-main
  * header.c-Hero
  * article.u-Above3
    * section.m-Content1
      * div.u-container2
        * div.u-Above2
          * h2.a-Title
          * p.a-Sub
          * ul.c-List.u-Adove1
            * li.a-txt
            * li.a-txt
            * li.a-txt

    * section.m-Content2
    * section.m-Content3

---

## offer for respnsive css

* ***Whitch min or max should be used***
  * Mainly, Circle CSS adopts Min when starting with PC Style.
    Conversely, Circle CSS does Max if starting with SP Style.

* **Why?**
  * You can less waste for overwriting css when Adapting Responsivity.
  * When Starting with PC Style, I recommend to write css with using *u-media-sm*.
  * Check responsivity and applicable range.
  * If you make sure responsivity for all display, get the css out the media query.
