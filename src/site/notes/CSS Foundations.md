---
{"dg-publish":true,"permalink":"/css-foundations/","title":"CSS Foundations"}
---


### PersonalNote: 
- avoid complications. Keep it simple and clean. avoid name collisions. 
	- apply 90/10 rule and attempt to keep everything decluttered. Use unique selectors for edge cases, and if you do use them.. leave comments and pointers 
- (##Typ) good practice to include a list of values when playing -> font; your ideal-intended font and a generic fallback. 
- (##Spe) Be mindful of the weight behind the css stylings you employ.. and how they weigh against the values of other selectors. ex. Instead of using `!important`, consider using cascade layers and using low weight specificity throughout your CSS so that styles are easily overridden with slightly more specific rules.
- (##Inh) The Inheritance chapter is probably the most eye-opening behind how CSS works.. required read. 

---
## CSS Foundations
Basic Syntax:.
pngpzza
![Drawing   18.03.46  2023-02-10.excalidraw.png](/img/user/Excalidraw/Drawing%20%20%2018.03.46%20%202023-02-10.excalidraw.png)
*Selectors* - refer to the HTML elements to which CSS rules apply
	- Universal - global application ``"*"``
	- Type - apply xxx whenever `<element>` is called upon, 
	- Class - most-used case. select all elements with the given class, which is just an attribute you place on an HTML element (See picture)

- ID Selectors - employment of special-use cases.. If `html` = `<div id="title">` , and `css` = 
``` css
#title {
  background-color: red;
}
```
	- An ID cannot be repeated on a single page, use sparingly when class will suffice 

- Grouping Selectors - To consolidate/clean up when repeating.. 
```css
.random1,
.random2,
.ThirdOptionSelector {
  color: white;
  background-color: black;
}
```

> [Forewarning](https://www.reddit.com/r/webdev/comments/vz1vqo/css_when_to_use_class_vs_chaining_selectors/ig7yszj/): "Default to _not_ increasing specificity where ever possible, because as the code grows it won't be lexically cogent i.e. you can't just read it from top to bottom anymore (you'll find yourself doing mental goto's).

>Chaining selectors increase specificity, therefore don't use them, or if you must, be frugal in their use and _always_ put their definition after the base class."

-  Chaining Selectors -  Tool to get more specific in scope.. This syntax basically works for chaining any combination of selectors except for type+type. 
		- Do note that, when "xxxx.xxxx", where the "." is present with no spaces, the css engine will read from right to left.. while "xxxx xxxx" goes left to right ..
		- In general, you can’t chain more than one type selector since an element can’t be two different types at once.  (Think upon the idea of )

!! PN: Imo, just skip this and learn to just simplify your coding to where class selectors can catch majority of elements, and look to specific-id solutions for those edge cases rather than reaching for chains. 
https://drafts.csswg.org/selectors-3/#selector


> [Another testament against chaining](https://www.reddit.com/r/learnprogramming/comments/wjwq00/what_is_the_point_point_of_chaining_a_class_and/ijk3pnu/): I don't buy the "readability" argument - just call do `id="subsection-preview"` if that's the goal, it also has the benefit of reducing the risk of naming collisions.

---
## Combinators 
	If...

A **[simple selector](https://drafts.csswg.org/selectors-3/#simple-selectors)*** is either a [type selector](https://drafts.csswg.org/selectors-3/#type-selectors), [universal selector](https://drafts.csswg.org/selectors-3/#universal-selector), [attribute selector](https://drafts.csswg.org/selectors-3/#attribute-selectors), [class selector](https://drafts.csswg.org/selectors-3/#class-html), [ID selector](https://drafts.csswg.org/selectors-3/#id-selectors), or [pseudo-class](https://drafts.csswg.org/selectors-3/#pseudo-classes).

	Then.. 

A *sequence of simple selectors* is a chain of [simple selectors](https://drafts.csswg.org/selectors-3/#simple-selectors-dfn) that are not separated by a [combinator](https://drafts.csswg.org/selectors-3/#combinators).

		and.. 
		
A *selector* is a chain of one or more [sequences of simple selectors](https://drafts.csswg.org/selectors-3/#sequence) separated by [combinators](https://drafts.csswg.org/selectors-3/#combinators). One [pseudo-element](https://drafts.csswg.org/selectors-3/#pseudo-elements) may be appended to the last sequence of simple selectors in a selector.
...

 A *combinator* is something that explains the relationship between the selectors
	 There are four different combinators in CSS:
			-   descendant selector (space)
			-   child selector (>)
			-   adjacent sibling selector (+)
			-   general sibling selector (~)		 
https://www.w3schools.com/css/css_combinators.asp

- A *Descendant Selector* (space).. 
	- selects all descending `<p>` elements inside the specified `<div>` elements
- A  *Child Selector* (>).. 
	- selects all elements that are the children `<p>` of a specified element `<div>`
- An *Adjacent Sibling Selector* (+).. 
	- selects the first `<p>` element that is directly after another specific element `<div>`
- A *General Sibling Selector* (~).. 
	- selects all `<p>` elements that are next siblings of `<div>` elements
![chrome_xyMyDzypNf.gif](/img/user/Media/chrome_xyMyDzypNf.gif)

---
## Typography Basics and Text-Align
- Each font will fall into one of two categories, either a “font family name"(InsertUniqueFontNameHere) or a “generic family name”(serif/sans-serif)
- If a browser cannot find or does not support the first font in a list, it will use the next one, then the next one and so on until it finds a supported and valid font.
	- This is why it’s best practice to include a list of values for this property, starting with the font you want to be used most and ending with a generic font family as a fallback, e.g. `font-family: "DejaVu Sans", sans-serif;`
- A [list of font-attributes to refer to](https://www.w3schools.com/cssref/pr_font_font.php)

---
## Specificity
- A CSS declaration that is more specific will take precedence over less specific ones. Specificity will only be taken into account when an element has multiple, conflicting declarations targeting it, sort of like a tie-breaker.
**reference**: - https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity
---
## Inheritance 
CSS properties can be categorized in two types:
	- inherited properties, which by default are set to the computed value of the parent element
	- non-inherited properties, which by default are set to initial value of the property

===

- Every property of CSS has an initial value. This initial value has no connection to the type of HTML element it’s applied to.
- HTML elements do not have initial style values! The basic styles of an HTML element, such as the `<h1>` tag for example, comes from the browser user agent stylesheet, and not from the `initial` value of the properties of CSS.
===
**@@@
> Every CSS property has an initial value. This value doesn’t depend on the HTML element that it applies to. A property’s initial value applies to all the HTML elements the same way.

>[!NOTE]
>- "**Have you ever asked yourself what the default values of the CSS Positions properties are?**
>- Many web developers will fail to answer this simple question. The answer is that the `position` property’s initial value is `static`.  
The other direction properties of CSS positions, `top`/`bottom`/`left`/`right` — their initial value is `auto`.

**Remember** — the basic styles of those CSS properties exist before you write a single style." <<<

===

- The best way to find each of the CSS properties’ initial value is by looking it up on the [MDN website](https://developer.mozilla.org/en-US/docs/Web/CSS/position#formal_definition) in the “Formal Definition” section.
https://elad.medium.com/how-does-css-work-92fe7116916d

---
**How can we know if styles are “inherited properties” or “non-inherited properties” when debugging in the browser?**
The formal way is by looking it up on the [MDN website](https://developer.mozilla.org/en-US/docs/Web/CSS/position#formal_definition) under the “**Formal Definition**” section.
Informal way is color based while inspecting HTML elements.. 

----
## **Summarizing the Four Basic CSS Levels**
(Good Read) by Elad Shechter
https://elad.medium.com/how-does-css-work-92fe7116916d

The default **CSS levels that we have in our browsers:**

png
![Drawing   16.22.14  2023-02-12.excalidraw.png](/img/user/Excalidraw/Drawing%20%20%2016.22.14%20%202023-02-12.excalidraw.png)


-   **“CSS Properties Default Styles” (Level-1)** — this is in charge of creating all the default values of all the properties we have in CSS.
-   **“User-Agent-Stylesheet” (Level-2)** — this is in charge of adding different default styles for some of the HTML elements.

Then, we learned how to **control the CSS with your own CSS basic layers:**

-   **“Normalize CSS” (Level-3)** — is in charge of keeping the default HTML styles, “User-Agent-Stylesheet” (Level 2), the same way across all browsers.
-   **“CSS Reset” (Level-4)** — overrides almost all the default “User-Agent-Stylesheet” (Level-2) styles whose effect we want to eliminate right from the beginning of our projects.
(EricMeyer Tool for CSS Reset)
https://meyerweb.com/eric/tools/css/reset/
png
![Drawing   16.59.04  2023-02-12.excalidraw.png](/img/user/Excalidraw/Drawing%20%20%2016.59.04%20%202023-02-12.excalidraw.png)

https://www.reddit.com/r/webdev/comments/q25nv9/building_mobile_first_vs_desktop_first/hfp4ftq/

---
### Adding CSS to HTML

*External CSS* is the most common method you will come across, and it involves creating a separate file for the CSS and linking it inside of an HTML’s opening and closing `<head>` tags with a self-closing `<link>` element:

```html
<!-- index.html -->

<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

```css
/* styles.css */

div {
  color: white;
  background-color: black;
}

p {
  color: red;
}
```
	(+): 
	1.  It keeps our HTML and CSS separated, which results in the HTML file being smaller and making things look cleaner.
	2.  We only need to edit the CSS in _one_ place, which is especially handy for websites with many pages that all share similar styles.
==
*Internal CSS* involves embedding the CSS within the HTML file itself instead of creating a completely separate file. With the internal method, you place all the rules inside of a pair of opening and closing `<style>` tags, which are then placed inside of the opening and closing `<head>` tags of your HTML file.

```html
<!-- index.html -->


<head>
  <style>
    div {
      color: white;
      background-color: black;
    }

    p {
      color: red;
    }
  </style>
</head>
<body>...</body>
```

(+):
	- useful for adding unique styles to a _single page_ of a website, but it doesn’t keep things separate like the external method

*Inline CSS* makes it possible to add styles directly to HTML elements, BUT.. not recommended as it's probably not good practice  to over-clutter your page with individualistic stylings. Just note that it is possible for those extreme cases.. 

