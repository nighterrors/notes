# CSS

Cascading Style-Sheets

## TOC

- [CSS](#css)
	- [TOC](#toc)
	- [INTRODUCTION](#introduction)
		- [Overview](#overview)
	- [COMMENTS](#comments)
		- [Anatomy](#anatomy)
	- [RULES](#rules)
		- [Anatomy](#anatomy-1)
		- [Classification](#classification)
	- [SELECTORS](#selectors)
		- [Anatomy](#anatomy-2)
		- [Classification](#classification-1)
	- [RULE SETS](#rule-sets)
		- [Anatomy](#anatomy-3)
	- [REPRESENTATION](#representation)
	- [REFERENCES](#references)

## INTRODUCTION



<aside>

### Overview

<!--TODO: Add bird's-eye view-->

</aside>

---

## COMMENTS



### Anatomy

```
/* multi-line comment */
```

## RULES



### Anatomy

```
name: value
```

### Classification



## SELECTORS

- element	`tag`
- class		`.class`
- id		`#id`

- attribute	`?attribute`<!--FXME-->
- pseudo	`?event attribute`<!--FXME-->

### Anatomy

- and
- or
- relationship

```
<!--TODO-->
```

### Classification



## RULE SETS



### Anatomy

```
selector {rule set;}
```
```
selector {
	rule 1;
	rule ...;
	rule n;
}
```

---

## REPRESENTATION

Inline
	:	Placed in an opening or self-closing tag as the `style` attribute.
	:	The rules are given as the attribute's value. (They are quoted.)
	:	They act on the element and its children (no need for selectors).
	:	:fa-times-circle: Not recommended; *=> use **external CSS**:fa-check-circle: instead!*
	:	```
		
		```

Internal
	:	Must be placed inside the `<head>.`
	:	The rules are nested between the tags as pure CSS. (No quoting needed.)
	:	Applies to the contents of the whole document. :fa-info-circle: (If multiple tags add internal and/or linked CSS, they're applied consecutively - so rules may override previous ones.)
	:	:fa-times-circle: Not recommended; *=> use **external CSS**:fa-check-circle: instead!*
	:	```
		
		```

External
	:	Should be placed inside the `<head>.`
	:	The rules are linked from an external *.css file.
	:	Applies to the contents of the whole document. :fa-info-circle: (If multiple tags add internal and/or linked CSS, they're applied consecutively - so rules may override previous ones.)
	:	:fa-check-circle: Recommended way of applying CSS.
	:	```
		
		```

---

## REFERENCES

<!--Abbreviations-->

*[ARIA]:		Accessible Rich Internet Applications
*[CSS]:			Cascading Style Sheets
*[HTML]:		Hyper Text Markup Language
*[HTTP]:		HyperText Transfer Protocol
*[JS]:			Java Script
*[MDN]:			Mozilla Developer Network
*[MIME]:		Multi-purpose Internet Mail Extensions
*[SVG]:			Scalable Vector Graphics
*[TOC]:			Table of Content
*[URI]:			Uniform Resource Identifier
*[URL]:			Uniform Resource Locator
*[WAI]:			Works As Intended
*[WAI-ARIA]:	Web Accessibility Initiative - Accessible Rich Internet Applications
*[XHTML]:		XML compatible HTML
*[XML]:			eXtensible Markup Language

---