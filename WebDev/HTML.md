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
	- [ELEMENTS](#elements)
		- [Classification](#classification-2)
			- [Representation](#representation)
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

[Content attribute](https://developer.mozilla.org/en-US/docs/Glossary/Attribute "MDN Web Docs Glossary - Attribute")
	:	Your everyday key-value pair.

[Boolean attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#boolean_attributes "MDN Web Docs - HTML Attribute Reference / Boolean Attributes")
	:	Special case of content attribute.
	:	Will be interpreted as 'on' if the attribute's name is present in the tag, with- or without any associated value.
	:	Will be interpreted as 'off', only if absent.

[Event handler attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#event_handler_attributes "MDN Web Docs - HTML Attribute Reference / Event Handler Attributes")
	:	

#### By Scope

Global
	:	Associated with any element.

Specific
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

## TAGS

<nav>

| >                                               | [:fa-chevron-circle-up:Top](#top)         |                                            |
| ----------------------------------------------- | :---------------------------------------: | -----------------------------------------: |
| [:fa-chevron-circle-left:Previous](#attributes) |                                           | [:fa-chevron-circle-right:Next](#elements) |
| >                                               | [:fa-chevron-circle-down:Bottom](#bottom) |                                            |

</nav>

Tags indicate the beginning and/or end of an [element](#elements)'s description in the source code.

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

|
< name >
```

#### Container tag

```
 opening tag          nested value  closing tag
          |                   |            |
/---------^---------\ /-------^-------\ /--^--\
<name[ attribute[s]]> enclosed  content </name>
\-v-/\------v------/
  |         |
tag's name  0 or more attributes separated by space character
```

#### Empty tag

```
same as an opening tag
          |
/---------^---------\
<name[ attribute[s]]>
\-v-/\------v------/
  |         |
tag's name  0 or more attributes
```

#### Self-closing tag

```
<name[ attribute[s]] />
```

## ELEMENTS

<nav>

| >                                               | [:fa-chevron-circle-up:Top](#top)         |                                        |
| ----------------------------------------------- | :---------------------------------------: | -------------------------------------: |
| [:fa-chevron-circle-left:Previous](#attributes) |                                           | [:fa-chevron-circle-right:Next](#page) |
| >                                               | [:fa-chevron-circle-down:Bottom](#bottom) |                                        |

</nav>

### Classification

| Classification | Types        | Associated Class^*^ |
| -------------- | ------------ | ------------------- |
| Representation | container    | A-Container         |
| ^              | void         | A-Void              |
| Layout         | block        | L-Block             |
| ^              | inline       | L-Inline            |
| Semantics      | semantic     | S-Semantic          |
| ^              | non-semantic | S-NonSemantic       |

\* As it will appear in the upcoming demo page.

#### Representation

<!--TODO: IDK, not void?-->
	:	

Void
	:	

#### Layout

Block
	:	

Inline
	:	

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

```
<tag>???</tag>
```

### Content Types

<!--TODO: Diagram-->

#### (Nothing)



#### Metadata



#### Flow



#### Sectioning



#### Heading



#### Phrasing



#### Embedded



#### Interactive



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
	:	

Multi-page
	:	

### Anatomy

```
<!DOCTYPE html>

<html>

	<head>

	</head>

	<body>

	</body>

</html>
```

---

<nav id="bottom">

| [:fa-arrow-alt-circle-left:Theory](../Theory/Index.md) | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Utilities](../Utilities/Index.md) |
| ------------------------------------------------------ | :------------------------------------------: | ------------------------------------------------------------: |
| [:fa-arrow-circle-left:Web Dev](Index.md)              | [:fa-arrow-circle-up:Web Dev](Index.md)      | [:fa-arrow-circle-right:CSS](CSS.md)                          |
| >                                                      | [:fa-chevron-circle-up:Top](#top)            |                                                               |

</nav>