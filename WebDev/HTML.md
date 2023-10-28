<nav id="top">

[NOTES](../Index.md) / [Web Dev](Index.md) / [HTML](HTML.md)

| [:fa-arrow-alt-circle-left:Theory](../Theory/Index.md) | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Utilities](../Utilities/Index.md) |
| ------------------------------------------------------ | :------------------------------------------: | ------------------------------------------------------------: |
| [:fa-arrow-circle-left:Web Dev](Index.md)              | [:fa-arrow-circle-up:Web Dev](Index.md)      | [:fa-arrow-circle-right:CSS](CSS.md)                          |

</nav>

# HTML

<nav>

| >                                | [:fa-chevron-circle-up:Top](#top)         |                                       |
| -------------------------------- | :---------------------------------------: | ------------------------------------: |
| :fa-chevron-circle-left:Previous |                                           | [:fa-chevron-circle-right:Next](#toc) |
| >                                | [:fa-chevron-circle-down:Bottom](#bottom) |                                       |

</nav>

HyperText Markup Language

## TOC

<nav>

| >                                         | [:fa-chevron-circle-up:Top](#top)         |                                              |
| ----------------------------------------- | :---------------------------------------: | -------------------------------------------: |
| [:fa-chevron-circle-left:Previous](#html) |                                           | [:fa-chevron-circle-right:Next](#attributes) |
| >                                         | [:fa-chevron-circle-down:Bottom](#bottom) |                                              |

</nav>

- [HTML](#html)
	- [TOC](#toc)
	- [ATTRIBUTES](#attributes)
		- [Classification](#classification)
			- [By Type](#by-type)
			- [By Scope](#by-scope)
		- [Anatomy](#anatomy)
			- [General](#general)
			- [Boolean](#boolean)
	- [TAGS](#tags)
		- [Classification](#classification-1)
		- [Anatomy](#anatomy-1)
			- [General](#general-1)
			- [Container tag](#container-tag)
			- [Empty tag](#empty-tag)
			- [Self-closing tag](#self-closing-tag)
		- [Special "tag-level" components](#special-tag-level-components)
	- [ELEMENTS](#elements)
		- [Classification](#classification-2)
			- [Representation](#representation)
			- [Relationship](#relationship)
			- [Layout](#layout)
			- [Semantics](#semantics)
				- [Notable non-semantic tags:](#notable-non-semantic-tags)
		- [Anatomy](#anatomy-2)
		- [Content Types](#content-types)
			- [(Nothing)](#nothing)
			- [Metadata](#metadata)
			- [Flow](#flow)
			- [Sectioning](#sectioning)
			- [Heading](#heading)
			- [Phrasing](#phrasing)
			- [Embedded](#embedded)
			- [Interactive](#interactive)
			- [(Palpable)](#palpable)
	- [PAGE](#page)
		- [Classification](#classification-3)
		- [Anatomy](#anatomy-3)

---

## ATTRIBUTES

<nav>

| >                                        | [:fa-chevron-circle-up:Top](#top)         |                                        |
| ---------------------------------------- | :---------------------------------------: | -------------------------------------: |
| [:fa-chevron-circle-left:Previous](#toc) |                                           | [:fa-chevron-circle-right:Next](#tags) |
| >                                        | [:fa-chevron-circle-down:Bottom](#bottom) |                                        |

</nav>

Attributes in HTML (and XML*) are added to opening-[tags](#tags) to extend or modify the functionality of [elements](#elements).  
Some attributes are global: Any element can have them; Some are specific to certain elements.  
Some elements require certain attributes to be configured in order to function properly, other's function just fine without any.

### Classification

#### By Type

[Content attribute](https://developer.mozilla.org/en-US/docs/Glossary/Attribute "MDN Web Docs Glossary - Attribute")<!--FXME: Find name for general attribute-->
	:	Your everyday key-value pair.

[Boolean attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#boolean_attributes "MDN Web Docs - HTML Attribute Reference / Boolean Attributes")
	:	Special case of content attribute.
	:	Will be interpreted as 'on' if the attribute's name is present in the tag, with- or without any associated value.
	:	Will be interpreted as 'off', only if absent.

[Event handler attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#event_handler_attributes "MDN Web Docs - HTML Attribute Reference / Event Handler Attributes")
	:	<!--TODO-->

#### By Scope

Global
	:	Associated with any element.

Specific<!--FXME: Find name for non-global attributes-->
	:	Can be used only in certain elements.

### Anatomy

#### General

```
attribute  it's associated value
      |     |
    /-^-\/--^--\
    name="value"
```

#### Boolean

`boolean-attribute` = `boolean-attribute="any value, including 'false'"`
<!--TODO: Add explanation-->

## TAGS

<nav>

| >                                               | [:fa-chevron-circle-up:Top](#top)         |                                            |
| ----------------------------------------------- | :---------------------------------------: | -----------------------------------------: |
| [:fa-chevron-circle-left:Previous](#attributes) |                                           | [:fa-chevron-circle-right:Next](#elements) |
| >                                               | [:fa-chevron-circle-down:Bottom](#bottom) |                                            |

</nav>

Tags indicate the beginning and/or end of an [element](#elements)'s description in the source code.
<!--TODO: Elaborate further?-->

### Classification

Container
	:	A pair of opening and closing tags.
	:	Represents an [element](#elements).

Empty
	:	Tags without a closing counterpart.
	:	Represents a [void-element](#void-element) in HTML.

Self-closing
	:	Same as empty, but has a trailing `/`.
	:	The XML, XHTML, SVG compatible version of an empty tag.
	:	>	:fa-exclamation: Doesn't exist in HTML, but parsers interpret them as empty tags, so to maintain compatibility with XML* it is customary to use them instead of an empty tag.
	:	>	:fa-exclamation: If a leading whitespace is missing and the last attribute's value isn't quoted, the parser will assume that it's part of the attribute's value.  
	E.g.: `<tag attribute=value/>` will be interpreted as the attribute having the value of "value/". To avoid this, (besides always quoting attr. values) a leading space should be added:  
	`<tag attribute="value" />`.

### Anatomy

#### General

```
opening angle-bracket
|
| tag's name
| |
| | closing angle-bracket
|/^\|
<tag>
```

#### Container tag

```
  opening tag      nested value  closing tag
           |                 |           |
 /---------^--------\/-------^-------\/--^-\
 <tag[ attribute[s]]>enclosed  content</tag>
 |\v/\------v------/|                 |\-v/|
 | |        |       |                 |  | |
`<`|        |      `>`               `<` |`>`
   |        |                            |
 tag's name |          tag's name preceded by `/`
            |
0 or more attributes separated by space character
```

#### Empty tag

```
 same as an opening tag
           |
 /---------^--------\
 <tag[ attribute[s]]>
 |\v/\------v------/|
 | |        |       |
`<`|        |      `>`
   |        |
 tag's name |
            |
  0 or more attributes
```

#### Self-closing tag

```
 single tag only
            |
 /----------^---------\
 <tag[ attribute[s]] />
 |\v/\------v------/\v/
 | |        |        |
`<`|        |        |
   |        |        |
tag's name  |        |
            |        |
0 or more attributes |
                     |
whitespace + forward slash + closing angle-bracket
```

### Special "tag-level" components<!--FXME: Better title/name-->

Technically aren't tags, but just as important parts of the document.

Comment
	:	`<!--comment-->`
	:	<!--TODO-->
	
Doctype
	:	`<!DOCTYPE html>`
	:	Must be the first line of the document, that isn't a whitespace or a comment

## ELEMENTS

<nav>

| >                                               | [:fa-chevron-circle-up:Top](#top)         |                                        |
| ----------------------------------------------- | :---------------------------------------: | -------------------------------------: |
| [:fa-chevron-circle-left:Previous](#attributes) |                                           | [:fa-chevron-circle-right:Next](#page) |
| >                                               | [:fa-chevron-circle-down:Bottom](#bottom) |                                        |

</nav>

An element is represented by its corresponding tag in HTML.

### Classification

| Classification | Types        | Associated Class^*^             |
| -------------- | ------------ | ------------------------------- |
| Representation | container    | A-Container                     |
| ^              | void         | A-Void                          |
| Relationship   | root         | R-Root                          |
| ^              | parent       | none - it's a relative property |
| ^              | child        | ^                               |
| Layout         | block        | L-Block                         |
| ^              | inline       | L-Inline                        |
| Semantics      | semantic     | S-Semantic                      |
| ^              | non-semantic | S-NonSemantic                   |

\* As it will appear in the upcoming demo page.

#### Representation

<!--TODO: IDK, not void?-->
	:	

Void
	:	<!--TODO-->

#### Relationship

Root
	:	<!--TODO-->

Parent
	:	<!--TODO-->

Child
	:	<!--TODO-->

#### Layout

Block
	:	<!--TODO-->

Inline
	:	<!--TODO-->

#### Semantics

- Has semantic meaning (most of them)
- Doesn't have semantic meaning

##### Notable non-semantic tags:

- Block:
	- `<div></div>`
- Inline:
	- `<span></span>`
	- `<b></b>`
	- `<i></i>`
	- `<u></u>`

### Anatomy

```<!--TODO-->
<tag>???</tag>
```

### Content Types

<!--TODO: Diagram-->

#### (Nothing)

<!--TODO-->

#### Metadata

<!--TODO-->

#### Flow

<!--TODO-->

#### Sectioning

<!--TODO-->

#### Heading

<!--TODO-->

#### Phrasing

<!--TODO-->

#### Embedded

<!--TODO-->

#### Interactive

<!--TODO-->

#### (Palpable)

## PAGE

<nav>

| >                                             | [:fa-chevron-circle-up:Top](#top)         |                               |
| --------------------------------------------- | :---------------------------------------: | ----------------------------: |
| [:fa-chevron-circle-left:Previous](#elements) |                                           | :fa-chevron-circle-right:Next |
| >                                             | [:fa-chevron-circle-down:Bottom](#bottom) |                               |

</nav>

### Classification

Single-page
	:	<!--TODO-->

Multi-page
	:	<!--TODO-->

### Anatomy

Properly formatted html consists of the following parts, in the following order:

0. \[Byte Order Mark]
1. \[Comments &| whitespace]
2. [DOCTYPE](#special-tag-level-components)
3. \[Comments &| whitespace]
4. Document element (`<html>`\[...]`</html>`)
5. \[Comments &| whitespace]

<!--TODO-->
```
<!DOCTYPE html>

<html>

	<head>

	</head>

	<body>

	</body>

</html>
```

<!--TODO-->

---

<nav id="bottom">

| [:fa-arrow-alt-circle-left:Theory](../Theory/Index.md) | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Utilities](../Utilities/Index.md) |
| ------------------------------------------------------ | :------------------------------------------: | ------------------------------------------------------------: |
| [:fa-arrow-circle-left:Web Dev](Index.md)              | [:fa-arrow-circle-up:Web Dev](Index.md)      | [:fa-arrow-circle-right:CSS](CSS.md)                          |
| >                                                      | [:fa-chevron-circle-up:Top](#top)            |                                                               |

</nav>