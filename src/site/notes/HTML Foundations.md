---
{"dg-publish":true,"permalink":"/html-foundations/","title":"HTML Foundations"}
---


### PersonalNote:
- (##Ele) Makes more sense to.. rather than memorize html elements/tags, work alongside documentation and refer to it when the element you need is called for.. Like writing with a thesaurus. 
	- https://developer.mozilla.org/en-US/docs/Web/HTML/Element#inline_text_semantics
- (##HTM) probably better to start off with a boilerplate that acts as a template and revise accordingly vs. recreating from scratch. 
- (##Wor) Rehash of chapter (##Ele) ..reiterate the idea that time is probably better spent just using a [HTML validator](https://validator.w3.org/) to find the needed element rather then memorizing everything w/o context 
- difference between " vs ', former="interpolated str" vs 'given literal value' and do not perform interpolation 

---
##  Introduction To HTML And CSS
*html* - lang rponsible for information 
*css* - lang responsible for styling()

---
## Elements And Tags

--open/close tag
--TODO; fix table color inspect

| `<a>`   | a                |
| ------- | ---------------- |
| `<p>`   | paragraph        |
| `br`    | break            |
| `img`   | imageInsert      |
| `a`     | anchor/hyperlink |
| `i`     | italicized       |
| `body` | body |
| `b`    | bold |
|`center` | centeredText       |
| `svg`   | svg container    |
| `td`    | table-cell       |
| `th`    | cell-header      |
| `dir`   | directory        |

---
## HTML Boilerplate
Common Practice:.
	- always name the HTML file that will contain the homepage of our websites `index.html` as default
	- Every HTML page starts with a doctype declaration, purpose is to tell the browser what version of HTML it should use to render the document `<!DOCTYPE html>`
	- provide the root element of the document `<html>`, so that every other element afterwards is a descendant 
	- `lang` Always use a language attribute to declare default lang..  
```
<html lang="en"> 
<p>The title is "<span lang="fr">Le Bon Usage</span>".
```
..
	- `head` = put important meta-information
	-  declare  charset = `<meta charset="___">`
	- `title`  always include for navigation
ex.. (index.html)
```html
<!DOCTYPE html>

<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <title>My First Webpage</title>
	</head>
	<body>
	<!--insertCommentHere-- >
	</body>
	
</html>
```
---
## Working with Text
- KnowledgeCheck: How to.. (paragraphs,heading,bold,italicized,nested relationships,)-- 
-[Answers->DropDown]
		- `<p>`
		- `<h1>`
		- `<b>` or `<strong>`  denotes = important 
		- `<i>` or  `<em>` idnicates = emphasis 
		- Nested = refers of placement of one element inside another 
		- `<!--` = comment 

PN: reiterate the idea that time is probably better spent just using a [HTML validator](https://validator.w3.org/) to find the needed element rather then memorizing everything w/o context  

---
## Lists
- KnowledgeCheck: create(Unordered_List , Ordered_List )
-[Answers->DropDown]
	 -`<ul>` creates a bullet-point list, `<li>` to denote each item 
	 -  therefore, `<ol>` creates a numbered-list 

> Tangent: 
- TODO; unrelated.. eventually should address diff. types of categories which html elements flow through (Main-content/Form-related/Specifics)(block-levels vs Inline) [more here](https://developer.mozilla.org/en-US/docs/Web/HTML/Content_categories)
![[Pasted image 20230210172342.png \|300]]
---
## Links And Images
Prac: If req.. 
	1.  Create a new directory named `odin-links-and-images`.
	2.  Within that directory, create a new file named `index.html`.
	3.  Fill in the usual HTML boilerplate.
	4.  Finally, add the following h1 to the body:
Then.. 
```
CMD: 
	mkdir "odin-links-and-images"
	type nul > "G:\index.html"
			REM 'type nul > FILE' where 'FILE' = 'dir/path/to/file.txt'
			REM > vs >> .. write new vs append
- Copy>Paste "usual HTML boilerplate" using editor 
html:
	<h1>Homepage</h1>
```
Anchor Elements = `a` where `<a href="YOUR_PATH_HERE">` then wrap+close 
- regarding Absolute vs Related Paths, it's ok as long as in same dir. Pros/cons = comes to Stable vs Portable fulfillment. 
Image embed = `img` where `<img src="PATH">`
- regarding paths, "../" denotes relative when prepositioned before path