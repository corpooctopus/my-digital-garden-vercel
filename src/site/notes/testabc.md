---
{"dg-publish":true,"permalink":"/testabc/"}
---

### PersonalNote: 
- avoid complications. Keep it simple and clean. avoid name collisions. 
	- apply 90/10 rule and attempt to keep everything decluttered. Use unique selectors for edge cases, and if you do use them.. leave comments and pointers 
- (##Typ) good practice to include a list of values when playing -> font; your ideal-intended font and a generic fallback. 
- (##Spe) Be mindful of the weight behind the css stylings you employ.. and how they weigh against the values of other selectors. ex. Instead of using `!important`, consider using cascade layers and using low weight specificity throughout your CSS so that styles are easily overridden with slightly more specific rules.
- (##Inh) The Inheritance chapter is probably the most eye-opening behind how CSS works.. required read. 

## CSS Foundations
Basic Syntax:.

*Selectors* - refer to the HTML elements to which CSS rules apply
	- Universal - global application ``"*"``
	- Type - apply xxx whenever `<element>` is called upon, 
	- Class - most-used case. select all elements with the given class, which is just an attribute you place on an HTML element (See picture)
