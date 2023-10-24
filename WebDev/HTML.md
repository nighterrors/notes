[NOTES](../Index.md) / [Web Dev](Index.md) / [HTML](HTML.md)

| [:fa-arrow-alt-circle-left:Theory](../Theory/Index.md) | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Utilities](../Utilities/Index.md) |
| ------------------------------------------------------ | :------------------------------------------: | ------------------------------------------------------------: |
| [:fa-arrow-circle-left:Web Dev](Index.md)              | [:fa-arrow-circle-up:Web Dev](Index.md)      | [:fa-arrow-circle-right:CSS](CSS.md)                          |

</nav>

# HTML

HyperText Markup Language

## TOC

<nav>

| >                                         | [:fa-chevron-circle-up:Top](#top)         |                                            |
| ----------------------------------------- | :---------------------------------------: | -----------------------------------------: |
| [:fa-chevron-circle-left:Previous](#html) |                                           | [:fa-chevron-circle-right:Next](#elements) |
| >                                         | [:fa-chevron-circle-down:Bottom](#bottom) |                                            |

</nav>

- [HTML](#html)
	- [TOC](#toc)
	- [ELEMENTS](#elements)
		- [Classification](#classification)
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

---


## ATTRIBUTES

Attributes in HTML (and XML*) are added to opening-[tags](#tags) to extend or modify the functionality of [elements](#elements).  
Some attributes are global: Any element can have them; Some are specific to certain elements.  
Some elements require certain attributes to be configured in order to function properly, other's function just fine without any.

### Classification

By Type:

[Content attribute](https://developer.mozilla.org/en-US/docs/Glossary/Attribute "MDN Web Docs Glossary - Attribute")
	:	Your everyday key-value pair.

[Boolean attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#boolean_attributes "MDN Web Docs - HTML Attribute Reference / Boolean Attributes")
	:	Special case of content attribute.
	:	Will be interpreted as 'on' if the attribute's name is present in the tag, with- or without any associated value.
	:	Will be interpreted as 'off', only if absent.

[Event handler attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#event_handler_attributes "MDN Web Docs - HTML Attribute Reference / Event Handler Attributes")
	:	

By Scope:

Global
	:	Associated with any element.

Specific
	:	Can be used only in certain elements.

### Anatomy

General:

```
attribute  it's associated value
	  |		|
	/-^-\/--^--\
	name="value"
```

Boolean:

`boolean-attribute` = `boolean-attribute="any value, including 'false'"`

## ELEMENTS

<nav>

| >                                        | [:fa-chevron-circle-up:Top](#top)         |                                    |
| ---------------------------------------- | :---------------------------------------: | ---------------------------------: |
| [:fa-chevron-circle-left:Previous](#toc) |                                           | [:fa-chevron-circle-right:Next](#) |
| >                                        | [:fa-chevron-circle-down:Bottom](#bottom) |                                    |

</nav>

### Classification

| Classification | Types        | Associated Class |
| -------------- | ------------ | ---------------- |
| annotation     | container    | A-Container      |
| ^              | empty        | A-Empty          |
| Layout         | block        | L-Block          |
| ^              | inline       | L-Inline         |
| Semantics      | semantic     | S-Semantic       |
| ^              | non-semantic | S-NonSemantic    |

### Content Types

#### (Nothing)

Diagram

#### Metadata



#### Flow



#### Sectioning



#### Heading



#### Phrasing



#### Embedded



#### Interactive



#### (Palpable)<nav id="top">

---

<nav id="bottom">

| [:fa-arrow-alt-circle-left:Theory](../Theory/Index.md) | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Utilities](../Utilities/Index.md) |
| ------------------------------------------------------ | :------------------------------------------: | ------------------------------------------------------------: |
| [:fa-arrow-circle-left:Web Dev](Index.md)              | [:fa-arrow-circle-up:Web Dev](Index.md)      | [:fa-arrow-circle-right:CSS](CSS.md)                          |
| >                                                      | [:fa-chevron-circle-up:Top](#top)            |                                                               |

</nav>