<nav id="top">

[NOTES](../Index.md) / [Web Dev](Index.md) / [HTML](HTML.md)
<!--FXME: I _REALLY_ shouldn't use tables for this:-->
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
<!--TODO: Mention HTML5-->
<!--TODO: Replace inline external links with footnotes to citations!-->

## TOC

<nav>

| >                                         | [:fa-chevron-circle-up:Top](#top)         |                                                |
| ----------------------------------------- | :---------------------------------------: | ---------------------------------------------: |
| [:fa-chevron-circle-left:Previous](#html) |                                           | [:fa-chevron-circle-right:Next](#introduction) |
| >                                         | [:fa-chevron-circle-down:Bottom](#bottom) |                                                |

</nav>

- [HTML](#html)
	- [TOC](#toc)
	- [INTRODUCTION](#introduction)
		- [Overview](#overview)
	- [CHARACTERS](#characters)
		- [Reserved Characters](#reserved-characters)
		- [Entities](#entities)
			- [Anatomy](#anatomy)
			- [Common Examples](#common-examples)
	- [ATTRIBUTES](#attributes)
		- [Anatomy](#anatomy-1)
			- [General](#general)
			- [Boolean](#boolean)
		- [Classification](#classification)
			- [By Type](#by-type)
			- [By Scope](#by-scope)
		- [Common Examples](#common-examples-1)
	- [TAGS](#tags)
		- [Anatomy](#anatomy-2)
			- [General](#general-1)
			- [Doctype](#doctype)
			- [Comment](#comment)
			- [Container tag](#container-tag)
			- [Empty tag](#empty-tag)
			- [Self-closing tag](#self-closing-tag)
		- [Classification](#classification-1)
		- [Common Examples](#common-examples-2)
	- [](#)
	- [ELEMENTS](#elements)
		- [Anatomy](#anatomy-3)
		- [Classification](#classification-2)
			- [WHATWG](#whatwg)
			- [Representation](#representation)
			- [Relationship](#relationship)
			- [Layout](#layout)
			- [Semantics](#semantics)
				- [Notable non-semantic tags:](#notable-non-semantic-tags)
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
		- [Grouping](#grouping)
	- [CONSTRUCTS](#constructs)
		- [Page](#page)
			- [Hierarchy](#hierarchy)
		- [Table](#table)
			- [Hierarchy](#hierarchy-1)
		- [Form](#form)
			- [Hierarchy](#hierarchy-2)
	- [REFERENCES](#references)

## INTRODUCTION

<nav>

| >                                        | [:fa-chevron-circle-up:Top](#top)         |                                              |
| ---------------------------------------- | :---------------------------------------: | -------------------------------------------: |
| [:fa-chevron-circle-left:Previous](#toc) |                                           | [:fa-chevron-circle-right:Next](#characters) |
| >                                        | [:fa-chevron-circle-down:Bottom](#bottom) |                                              |

</nav>


HTML is a markup language, which means it consists of two main components:

- The display text, that's going to be rendered in browser window (or read by a screen reader or other assistive software),
- And the markup, that gives contextual info to the browser (or assistive software) how to render the text.  
	<aside>This contextual info used to be largely overlooked and all that mattered was the visual representation. <!--TODO: But now search engines and AI beside assistive tech needs more context in a way that visual just don't cut it any more...--></aside>

In this document I discuss the syntax used to markup HTML documents. I will refer to the contents of such document as [*tags*](#tags), which can have [*attributes*](#attributes) and may have nested text (That may be markup text itself, or just plain text). The tags and their attributes have an abstract counterpart of a corresponding [*element*](#elements) and its *properties*. Their content (if any) is in general referred to as [objects](#). These objects in the context of HTML are called *nodes*. So a node can be plain text, another tag, etc..

<aside>

### Overview

A HTML [document](#page) consists of a hierarchical tree of [tags](#tags) nested into each-other: Thus these tags may contain 0 or more tags inside and/or text content, that is the visible part of the document.  
Every tag can have 0 or more [attributes](#attributes), that tune their behaviour. Some tags can reference external or internal content through their attributes.  
Display text may contain [entities](#entities), which are specific strings representing certain characters, that are otherwise would've been interpreted as parts of the markup or just difficult to type in.

</aside>

---

## CHARACTERS

<nav>

| >                                                 | [:fa-chevron-circle-up:Top](#top)         |                                              |
| ------------------------------------------------- | :---------------------------------------: | -------------------------------------------: |
| [:fa-chevron-circle-left:Previous](#introduction) |                                           | [:fa-chevron-circle-right:Next](#attributes) |
| >                                                 | [:fa-chevron-circle-down:Bottom](#bottom) |                                              |

</nav>

HTML parsers treat whitespace characters (space, tab, newline) equally:

- Whitespace is ignored on the beginning and end of a paragraph.
- Whitespace between words replaced with a single space character.
- Word wrap is taken care of by the renderer, so that the text would fit in its bounding box.

<aside>

:fa-info-circle: As a result, the two following paragraphs would render the exact same way:  

```
<p>Sphinx of black quartz, judge my vow!</p>
```
```
<p>
Sphinx     of 
	black	 
  quartz,
 judge		 my vow!

</p>
```

See?:
<p>Sphinx of black quartz, judge my vow!</p>
<p>
Sphinx     of 
	black	 
  quartz,
 judge		 my vow!

</p>
Can you tell which one's which?
</aside>

### Reserved Characters

In HTML the following characters have special meaning:

`<` :fa-exclamation-circle:
	:	beginning of a tag

`>` :fa-exclamation-circle:
	:	ending of tag

`&` :fa-exclamation-circle:
	:	beginning of an entity

`;`
	:	ending of an entity

`'`, `"` :fa-exclamation-circle:
	:	beginning and ending of attribute value
<dd><aside>

:fa-info-circle: Only have to escape / substitute them in an attribute's value.
</aside></dd>

`\`
	:	escape character
<dd><aside>

:fa-info-circle: Can be used to interpret literally the following character.
</aside></dd>

`/`
	:	part of closing sequence in closing tags and self-closing tags

:fa-info-circle: You only really need to worry about the ones marked with :fa-exclamation-circle:, the other's won't cause any trouble on their own.

### Entities

An entity is a string representation of a unicode character. Some characters have named entities but all have codes, although it depends on the renderer, which one can be displayed. (All the printable ASCII characters are supported, plus more!)

#### Anatomy

- The commonly used entities (and many more) have names, by which they can be referred to:

```
`&` - indicates beginning
 |
 | mnemonic name of the entity
 |  |
 |  |  `;` - indicates end
 |  |   |
 |/-^--\|
 &entity;
```

- Even though some don't have name, all of them can be referred to by they unicode code point.
	- Either in hexadecimal,

	```
	`&`
	 | `#` - indicates numeric form
	 |  |
	 |  | hexadecimal number
	 |  |  |
	  \ |  | `;`
	   ||/-^-\|
	   &#x001F;
	     |\/
	    /  \
	   |  optional 0-padding
	   |
	leading 'x' indicates hexadecimal base
	```

	- Or decimal form

	```
	`&`
	 |`#` - indicates numeric form
	 | |
	 | | decimal number
	 | | |
	 \ | |`;`
	  ||/^\|
	  &#190;
	   \/
	no base-indicator means it'll be interpreted as decimal number
	```


#### Common Examples

| Character            | Entity Name | Entity Code | Reason to Substitute                                 |
| -------------------: | ----------- | ----------- | ---------------------------------------------------- |
| &lt;                 | `&lt;`      | `&#x003C;`  | Reserved: beginning of a tag                         |
| &gt;^*^              | `&gt;`      | `&#x003E;`  | Reserved: ending of a tag                            |
| &                    | `&amp;`     | `&#x0026;`  | Reserved: beginning of an entity                     |
| ;                    | `&semi;`    | `&#x003B;`  | Interpreted: ending of an entity                     |
| '                    | `&apos;`    | `&#x0027;`  | Reserved: beginning and ending of an attribute value |
| "                    | `&quot;`    | `&#x0022;`  | Reserved: beginning and ending of an attribute value |
| `                    | `&grave;`   | `&#x0060;`  | Interpreted (markdown): code                         |
| /                    | `&sol;`     | `&#x002F;`  | Interpreted: part of self-closing sequence           |
| \                    | `&bsol;`    | `&#x005C;`  | Interpreted: escape character                        |
| &vert;               | `&vert;`    | `&#x007C;`  | Interpreted (markdown/table): cell separator         |
| [non-breaking space] | `&nbsp;`    | `&#x00A0;`  | May be interpreted: whitespace; Not on keyboard      |
| [tab]                | `&Tab;`     | `&#x0009;`  | May be interpreted: whitespace                       |
| [newline] (CR)       | `&NewLine;` | `&#x000D;`  | Interpreted: whitespace                              |
| [newline] (LF)       | `&NewLine;` | `&#x000A;`  | Interpreted: whitespace                              |
| &ndash;              | `&ndash;`   | `&#x2013;`  | Not on keyboard                                      |
| &mdash;              | `&mdash;`   | `&#x2014;`  | Not on keyboard                                      |
| ©                    | `&copy;`    | `&#x00A9;`  | Not on keyboard                                      |
| ®                    | `&reg;`     | `&#x00AE;`  | Not on keyboard                                      |
| ™                    | `&trade;`   | `&#x2122;`  | Not on keyboard                                      |
| ≈                    | `&asymp;`   | `&#x2248;`  | Not on keyboard                                      |
| ≠                    | `&ne;`      | `&#x2260;`  | Not on keyboard                                      |
| °                    | `&deg;`     | `&#x00B0;`  |                                                      |
| £                    | `&pound;`   | `&#x00A3;`  |                                                      |
| €                    | `&euro;`    | `&#x20AC;`  |                                                      |
| $                    | `&dollar;`  | `&#x0024;`  |                                                      |
| #                    | `&num;`     | `&#x0023;`  |                                                      |
| @                    | `&commat;`  | `&#x0040;`  |                                                      |
|                      | `&;`        | `&#x;`      |                                                      |

<aside>* A single > seems to break my markdown parser somehow, so I had to add something else that would render to make the &gt; visible.</aside>

Explanation:

Reserved
	:	These characters are reserved for a special purpose.
	:	:fa-exclamation-circle: Using them literally may break your code at worst, or at best they won't render.

Interpreted
	:	These character have special meaning.
	:	:fa-exclamation-circle: In certain cases they may behave similarly to reserved characters.

Not on keyboard
	:	These characters may be difficult to produce on some keyboards.
	:	:fa-info-circle: Keep in handy the ones you can't find on yours!

## ATTRIBUTES

<nav>

| >                                               | [:fa-chevron-circle-up:Top](#top)         |                                        |
| ----------------------------------------------- | :---------------------------------------: | -------------------------------------: |
| [:fa-chevron-circle-left:Previous](#characters) |                                           | [:fa-chevron-circle-right:Next](#tags) |
| >                                               | [:fa-chevron-circle-down:Bottom](#bottom) |                                        |

</nav>

Attributes in HTML (and XML*) are added to opening-[tags](#tags) to extend or modify the functionality of [elements](#elements).
These attributes describe (modify or set) properties of their corresponding objects (elements).

<aside>Some attributes are global: Any element can have them; Some are specific to certain elements.  
Some elements require certain attributes to be configured in order to function properly, others function just fine without any.</aside>

### Anatomy

#### General

```
attribute's name `=` it's associated value
             |    |   |
         /---^---\|/--^--\
         attribute="value"
                   |     |
                quotation marks
```

- Quoting the value of an attribute is only necessary, if {value} has special characters, including whitespace, but *it's a good practice to do it every time*.
- Quoted text can be *equivalently* represented by either single-quotes (`'`) *or* double-quotes (`"`), but *opening and closing marks have to be of the same type*.
	- It's common to use the other type of quotation mark, if one of them also appears in the text.
		- <aside>E.g.: <code>"I'm using this as an example."</code> or <code>'She said: "But why?"'</code></aside>
	- It's necessary to escape the reoccurring symbol if both are present in the quoted text.
		- <aside>E.g.: <code>'To quote Shakespeare: "Don\'t".'</code></aside>
	- > :fa-info-circle: In this document I use single quotes (`'`) for common keywords.  
	And double quotes (`"`) for specific terms, that don't have implied meaning beside their value.
		- <aside>E.g.: <code>'true'</code>, <code>target='_blank'</code>, <code>lang='en_GB'</code></aside>
		- <aside>E.g.: <code>id="arbitrary-string"</code>, <code>class="my-class"</code>, <code>alt="Image description goes here."</code></aside>
<!--- <TODO: IDK, what I wanted to add here:c-->

#### Boolean

Boolean attributes can have only 2 states: Either `true` or `false`. These states are implied by the presence or absence of the attribute itself, respectably. As such, they don't require defined values.
<aside>In fact, its associated value is completely ignored. This can create the rather misleading situation where `boolean='false'` is still interpreted as being set to 'true'.</aside>

| 'On'-states             | 'Off'-state |
| :---------------------: | :---------: |
| `boolean`               | `''`^*^     |
| `boolean = 'true'`      | ^           |
| `boolean = "any value"` | ^           |
| `boolean = 'false'`     | ^           |
\* 'Off' only when it's not present.

> :fa-info-circle: In above example `boolean` represents the name of a boolean attribute.

### Classification

#### By Type

[Boolean attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#boolean_attributes "MDN Web Docs - HTML Attribute Reference / Boolean Attributes")
	:	Special type of attribute: Can have only 2 states: 'on'/'true' of 'off'/'false'.
	:	Will be interpreted as 'on' if the attribute's name is present in the tag, with- or without any associated value.
	:	Will be interpreted as 'off', only if absent.
	:	Name
		:	The property to be toggled on.
	:	Value
		:	N/A (*none* necessary; *any* value accepted, but *ignored*).

[Enumerated attribute](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated "MDN Web Docs - Glossary / Enumerated")
	:	<aside>Somewhere in-between a boolean and a more general attribute.</aside>
	:	Has finite states, set via predefined keywords.
	:	<aside>E.g.: <code></code> | <code>hidden</code> | <code>hidden='until-found'</code> sets an element to be visible | hidden | or to be only revealed when referenced or searched for.</aside>
	:	Name
		:	Identifies the attribute and the property it represents.
		:	May determine a state on its own (like a boolean does).
	:	Value
		:	A specific identifier of one of its accepted states.

[General attribute](https://developer.mozilla.org/en-US/docs/Glossary/Attribute "MDN Web Docs Glossary - Attribute")
	:	Your everyday key-value pair. See: [anatomy](#general "General anatomy of an attribute").
	:	Name
		:	Serves only as an identifier for the attribute and the property it represents.
	:	Value
		:	Its associated value.
		:	Types of accepted values depend on the attribute.
			- Usually a keyword or a string / text, URL or even quoted CSS, JS.
			- Can be numeric, date and/or time, etc.

[Event handler attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#event_handler_attributes "MDN Web Docs - HTML Attribute Reference / Event Handler Attributes")
	:	Describe the *on*event behaviour of certain objects (that can have events).
	:	> :fa-exclamation-circle: This is a legacy way of handling events and should be avoided!  
		See: [Inline event handlers](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#other_event_listener_mechanisms "MDN Web Docs - Introduction to events / Inline event handlers - don't use these")
	:	Name
		:	Name of the specific event that supposed to trigger the action.
		:	Usually in the form of *on*event-name E.g.: `onclick`.
	:	Value
		:	The JS function to be triggered by the event.

#### By Scope

Global
	:	Associated with any element. => Every element can have attributes.

Non-global
	:	Can be used only in certain elements.

### [Common Examples](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes "MDN Web Docs - HTML Attribute Reference")

<!--FXME: Check if `enumerated` elements were miscategorised prior to the first one!-->
<!--FXME: Decide on the use of "Coupled" vs "Paired"!-->
<!--FXME: More conscious use of "Hints", "Indicates", "Declares", "Sets", "Dictates"-->

| Attribute           | Type       | Scope                                                                                                                 | Value Data Type                   |
| ------------------- | ---------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------- |
| **action**          | general    | `<form>`                                                                                                              | URI                               |
| ^                   | >          | The URI of the receiver that processes the information sent via the form's onsubmit event.                            |                                   |
| **alt**             | general    | `<area>` `<img>` `<input>`                                                                                            | string                            |
| ^                   | >          | Text to show if image can't be displayed.                                                                             |                                   |
| ^                   | >          | <aside>May help crawlers, AI to put the image in context.</aside>                                                     |                                   |
| **async**           | boolean    | `<script>`                                                                                                            | boolean                           |
| ^                   | >          | Dictates asynchronous script execution.                                                                               |                                   |
| **autocomplete**    | general    | `<form>` `<input>` `<select>` `<textarea>`                                                                            | keyword                           |
| ^                   | >          | Hints the browser that fields can be auto filled.                                                                     |                                   |
| ^                   | >          | May give info on the type of data requested.                                                                          |                                   |
| **autoplay**        | boolean    | `<audio>` `<video>`                                                                                                   | boolean                           |
| ^                   | >          | Indicates that the media should be played ASAP.                                                                       |                                   |
| **charset**         | general    | `<meta>`                                                                                                              | keyword                           |
| ^                   | >          | Declares character encoding for the object.                                                                           |                                   |
| **checked**         | boolean    | `<input>`                                                                                                             | boolean                           |
| ^                   | >          | Sets the input to be checked on page load.                                                                            |                                   |
| ^                   | >          | Valid for `checkbox` and `radio` types.                                                                               |                                   |
| **cite**            | general    | `<blockquote>` `<del>` `<ins>` `<q>`                                                                                  | URI                               |
| ^                   | >          | Source URI of the quote.                                                                                              |                                   |
| **class**           | general    | GLOBAL                                                                                                                | string                            |
| ^                   | >          | Provides option to arbitrarily group different elements together, by assigning them to the same class.                |                                   |
| ^                   | >          | Used for targeting such groups with CSS and/or JS.                                                                    |                                   |
| **colspan**         | general    | `<td>` `<th>`                                                                                                         | integer                           |
| ^                   | >          | The number of columns a cell should extend to.                                                                        |                                   |
| ^                   | >          | <aside>This number includes the cell's own column, so <code>colspan="1"</code> does nothing.</aside>                  |                                   |
| ^                   | >          | <aside>:fa-info-circle: Similar to `rowspan`.</aside>                                                                 |                                   |
| **content**         | general    | `<meta>`                                                                                                              | string                            |
| ^                   | >          | :fa-info-circle: Paired with *`name`* attribute.                                                                      |                                   |
| ^                   | >          | Represents the 'value' in a 'key-value' pair.                                                                         |                                   |
| ^                   | >          | Provides a way to associate non-canonical properties with the object, that's only meaningful for certain consumers.   |                                   |
| ^                   | >          | <aside>E.g.: web crawlers.</aside>                                                                                    |                                   |
| **contenteditable** | general    | GLOBAL                                                                                                                | keyword                           |
| ^                   | >          | Changes the element's content's editability.                                                                          |                                   |
| ^                   | ^          |                                                                                                                       |                                   |
| **controls**        | boolean    | `<audio>` `<video>`                                                                                                   | boolean                           |
| ^                   | >          | Adds controls to the media.                                                                                           |                                   |
| **crossorigin**     | general    | `<audio>` `<img>` `<link>` `<script>` `<video>`                                                                       | keyword                           |
| ^                   | >          | Defines how to handle cross-origin requests.                                                                          |                                   |
| **default**         | boolean    | `<track>`                                                                                                             | boolean                           |
| ^                   | >          | Hints which track should be enabled.                                                                                  |                                   |
| ^                   | >          | Overridden by user settings.                                                                                          |                                   |
| **defer**           | boolean    | `<script>`                                                                                                            | boolean                           |
| ^                   | >          | Indicates the script should be executed after the document is parsed, but before firing `DOMContentLoaded`.           |                                   |
| ^                   | >          | :fa-exclamation-circle: Has no effect on inline scripts.                                                              |                                   |
| **disabled**        | boolean    | `<button>` `<fieldset>` `<input>` `<optgroup>` `<option>` `<select>` `<textarea>`                                     | boolean                           |
| ^                   | >          | Sets the element non-interactable.                                                                                    |                                   |
| **download**        | ???        | `<a>` `<area>`                                                                                                        | ???                               |
| ^                   | >          | Indicates that the hyperlink is for downloading a resource.                                                           |                                   |
| **draggable**       | general    | GLOBAL                                                                                                                | keyword                           |
| ^                   | >          | Indicates whether the element can be dragged.                                                                         | 'true' *or* 'false'               |
| ^                   | >          | :fa-exclamation-circle: **Not ~~boolean~~, always should have an assigned value of either *'true'* or *'false'*!**    |                                   |
| **for**             | general    | `<label>` `<output>`                                                                                                  | string (id)                       |
| ^                   | >          | Indicates which element this one belongs to by adding the target element's `id`.                                      |                                   |
| **form**            | general    | `<button>` `<fieldset>` `<input>` `<label>` `<meter>` `<object>` `<output>` `<progress>` `<select>` `<textarea>`      | string                            |
| ^                   | >          | Indicates which form element this one belongs to.                                                                     |                                   |
| **hidden**          | enumerated | GLOBAL                                                                                                                | keyword                           |
| ^                   | >          | Indicates if the element should not be rendered.                                                                      | '', 'hidden', ='until-found'      |
| ^                   | >          | If absent, the element presented as normal.                                                                           |                                   |
| ^                   | >          | If present without assigned value, the element is hidden.                                                             |                                   |
| ^                   | >          | If it's `hidden='until-found'`, the element is only shown when referenced or searched for.                            |                                   |
| **href**            | general    | `<a>` `<area>` `<base>` `<link>`                                                                                      | URL                               |
| ^                   | >          | The URL of a linked resource.                                                                                         |                                   |
| ^                   | >          | <aside>:fa-info-circle: Similar to `src`, but for linked resources.</aside>                                           |                                   |
| **id**              | general    | GLOBAL                                                                                                                | string                            |
| ^                   | >          | Provides option to uniquely identify the element by assigning an id to it.                                            |                                   |
| ^                   | >          | Used for targeting such element with an other element's `for` attribute or CSS, JS.                                   |                                   |
| **inputmode**       | enumerated | `<textarea>` `contenteditable`                                                                                        | keyword                           |
| ^                   | >          | Hints the type of data, that may be entered by user.  <!--FXME: Move values to the next column-->                     |                                   |
| ^                   | >          | Values = 'none', 'text', 'decimal', 'numeric', 'tel', 'search', 'email', 'url'                                        |                                   |
| **label**           | general    | `<optgroup>` `<option>` `<track>`                                                                                     | string                            |
| ^                   | >          | Adds user-readable title to the element.                                                                              |                                   |
| **lang**            | general    | GLOBAL                                                                                                                | keyword                           |
| ^                   | >          | Hints the language used in the element.                                                                               |                                   |
| ~~language~~        | general    | `<script>`                                                                                                            | string                            |
| ^                   | >          | :fa-times-circle: Use `type` instead!                                                                                 |                                   |
| ^                   | >          | Supposed to identify the scripting language used, but was never standardised.                                         |                                   |
| **list**            | general    | `<input>`                                                                                                             | string                            |
| ^                   | >          | Points to predefined options for the input.                                                                           |                                   |
| ^                   | >          | Should be the id of a `<datalist>` element of the same document.                                                      |                                   |
| **loop**            | boolean    | `<audio>` `<marquee>` `<video>`                                                                                       | boolean                           |
| ^                   | >          | Indicates that the media should repeat indefinitely.                                                                  |                                   |
| **max**             | general    | `<input>` `<meter>` `<progress>`                                                                                      | number, date, time                |
| ^                   | >          | Sets the maximum allowed value.                                                                                       |                                   |
| ^                   | >          | :fa-info-circle: Coupled with `min` `step`.                                                                           |                                   |
| **maxlength**       | general    | `<input>` `<textarea>`                                                                                                | non-negative integer              |
| ^                   | >          | Sets the maximum length of an input string.                                                                           |                                   |
| ^                   | >          | :fa-info-circle: Coupled with `minlength`.                                                                            |                                   |
| **method**          | enumerated | `<form>`                                                                                                              | 'get' (default), 'post', 'dialog' |
| ^                   | >          | Defines the HTTP method used on submission.                                                                           |                                   |
| **min**             | general    | `<input>` `<meter>` `<progress>`                                                                                      | number, date, time                |
| ^                   | >          | Sets the minimum allowed value.                                                                                       |                                   |
| ^                   | >          | :fa-info-circle: Coupled with `max` `step`.                                                                           |                                   |
| **minlength**       | general    | `<input>` `<textarea>`                                                                                                | non-negative integer              |
| ^                   | >          | Sets the minimum length of an input string.                                                                           |                                   |
| ^                   | >          | :fa-info-circle: Coupled with `maxlength`.                                                                            |                                   |
| **muted**           | boolean    | `<audio>` `<video>`                                                                                                   | boolean                           |
| ^                   | >          | Sets the media to be initially silenced.                                                                              |                                   |
| **name**            | general    | `<meta>`                                                                                                              | string                            |
| ^                   | >          | :fa-info-circle: Paired with *`content`* attribute.                                                                   |                                   |
| ^                   | >          | Represents the 'key' in a 'key-value' pair.                                                                           |                                   |
| ^                   | >          | Provides a way to associate non-canonical properties with the object, that's only meaningful for certain consumers.   |                                   |
| ^                   | >          | <aside>E.g.: web crawlers.</aside>                                                                                    |                                   |
| **novalidate**      | boolean    | `<form>`                                                                                                              | boolean                           |
| ^                   | >          | Indicates that the form shouldn't be validated on submission.                                                         |                                   |
| **pattern**         | general    | `<input>`                                                                                                             | string (regexp expression)        |
| ^                   | >          | The inputted value will be checked against this expression.                                                           |                                   |
| **placeholder**     | general    | `<input>` `<textarea>`                                                                                                | string                            |
| ^                   | >          | Its value displayed in the empty field.                                                                               |                                   |
| ^                   | >          | <aside>Used for giving a hint to the user regarding what to enter in the field.</aside>                               |                                   |
| **poster**          | general    | `<video>`                                                                                                             | URL                               |
| ^                   | >          | URL to a frame to be displayed until the video is played or seeked.                                                   |                                   |
| **preload**         | enumerated | `<audio>` `<video>`                                                                                                   | keyword                           |
| ^                   | >          | Indicates what should be preloaded.                                                                                   | 'none', 'metadata', 'auto' = ''   |
| **readonly**        | boolean    | `<input>` `<textarea>`                                                                                                | boolean                           |
| ^                   | >          | Renders the input field non-editable by user.                                                                         |                                   |
| ^                   | >          | Only applies to text inputs.                                                                                          |                                   |
| ^                   | >          | :fa-info-circle: For other input types the *`disabled`* attribute gives equivalent functionality.                     |                                   |
| ^                   | >          | :fa-info-circle: `readonly` fields skipped during constraint validation.                                              |                                   |
| **rel**             | general    | `<a>` `<area>` `<link>` `<form>`?                                                                                     | keyword                           |
| ^                   | >          | Indicates relationship between the document and the linked resource.                                                  |                                   |
| ^                   | >          | Used by browsers and crawlers.                                                                                        |                                   |
| **required**        | boolean    | `<input>` `<select>` `<textarea>`                                                                                     | boolean                           |
| ^                   | >          | Doesn't let the form to be submitted, until the user specifies a value in its field.                                  |                                   |
| **reversed**        | boolean    | `<ol>`                                                                                                                | boolean                           |
| ^                   | >          | Indicates that the list should be displayed in an ascending order.                                                    |                                   |
| **role**            | general    | GLOBAL                                                                                                                | keyword                           |
| ^                   | >          | Explicitly sets the element's ARIA role.                                                                              |                                   |
| ^                   | >          | <aside>:fa-info-circle: Useful for elements without intrinsic roles or if used in a non-canonical manner.</aside>     |                                   |
| **rowspan**         | general    | `<td>` `<th>`                                                                                                         | integer                           |
| ^                   | >          | The number of rows a cell should extend to.                                                                           |                                   |
| ^                   | >          | <aside>This number includes the cell's own row, so <code>rowspan="1"</code> does nothing.</aside>                     |                                   |
| ^                   | >          | <aside>:fa-info-circle: Similar to `colspan`.</aside>                                                                 |                                   |
| **selected**        | boolean    | `<option>`                                                                                                            | boolean                           |
| ^                   | >          | Indicates that this option should be selected on page load.                                                           |                                   |
| **spellcheck**      | enumerated | GLOBAL                                                                                                                | keyword                           |
| ^                   | >          | Hints whether the element should be checked for spelling errors.                                                      | 'true' or 'false'                 |
| ^                   | >          | :fa-exclamation-circle: Should be set to 'false' for elements that may contain sensitive information!                 |                                   |
| **src**             | general    | `<audio>` `<embed>` `<iframe>` `<img>` `<input>` `<script>` `<source>` `<track>` `<video>`                            | URL                               |
| ^                   | >          | The URL of the embedded content.                                                                                      |                                   |
| ^                   | >          | <aside>:fa-info-circle: Similar to `href`, but for embedded content.</aside>                                          |                                   |
| **start**           | general    | `<ol>`                                                                                                                | integer                           |
| ^                   | >          | Sets the starting value for ordered list items.                                                                       |                                   |
| ^                   | >          | :fa-info-circle: Always numeric, even if the numbering `type` is alphabetic or roman.                                 |                                   |
| **step**            | general    | `<input>`                                                                                                             | number                            |
| ^                   | >          | Sets the stepping interval for numeric input types including date, time types and range besides number.               |                                   |
| ^                   | >          | :fa-info-circle: Coupled with `max` `min`, but only valid for `<input>`.                                              |                                   |
| ~~style~~           | general    | GLOBAL                                                                                                                | CSS declarations                  |
| ^                   | >          | Provides *inline* CSS style declarations for the element.                                                             |                                   |
| ^                   | >          | :fa-exclamation-circle: Inline CSS should be avoided. :fa-check-circle: Use external CSS instead!                     |                                   |
| ^                   | >          | :fa-exclamation-circle: Not to be confused with the ~~`<style>`~~ element.                                            |                                   |
| ~~summary~~         | general    | `<table>`                                                                                                             | string                            |
| ^                   | >          | Used to describe contents of the table.                                                                               |                                   |
| ^                   | >          | :fa-times-circle: Obsolete. :fa-check-circle: Use `<caption>` element instead!^*^                                     |                                   |
| **tabindex**        | general    | GLOBAL                                                                                                                | integer                           |
| ^                   | >          | Overrides the default tab order by specifying the element's position in the sequence.                                 |                                   |
| ^                   | >          | :fa-info-circle: Setting it to a positive value will force the element on top of the natural tab sequence.            |                                   |
| ^                   | >          | :fa-info-circle: Zero means that the element will be forced into the tab sequence, but will follow its natural order. |                                   |
| ^                   | >          | :fa-info-circle: A negative value means that the element will be excluded.                                            |                                   |
| ^                   | >          | :fa-info-circle: These settings can override the element's natural behaviour.                                         |                                   |
| **target**          | general    | `<a>` `<area>` `<base>` `<form>`                                                                                      | keyword or string                 |
| ^                   | >          | Specifies where to open linked documents.                                                                             |                                   |
| ^                   | >          | <aside>In case of forms, it's the response after submitting it.</aside>                                               |                                   |
| **title**           | general    | GLOBAL                                                                                                                | string                            |
| ^                   | >          | Tooltip to display when hovering over the element.                                                                    |                                   |
| ^                   | >          | :fa-exclamation-circle: Not to be confused with ~~`<title>`~~ element!                                                |                                   |
| **translate**       | enumerated | GLOBAL                                                                                                                | '' = 'yes', 'no'                  |
| ^                   | >          | Hints whether the element's text content should be subject to translation.                                            |                                   |
| ^                   | >          | <aside>:fa-info-circle: E.g.: to protect brand names from being translated.</aside>                                   |                                   |
| **type**            | general    | `<button>` `<input>` `<ol>` `<link>`                                                                                  | keyword                           |
| ^                   | >          | Sets the default behaviour or input type for the element. Each element has its own specific types.                    |                                   |
| **type**            | general    | `<embed>` `<object>` `<script>` `<source>` `<link>`                                                                   | keyword                           |
| ^                   | >          | Sets the MIME type for the element. Each element has its own specific types.                                          |                                   |
| ~~type~~            | general    | ~~`<style>`~~ `<menu>`                                                                                                | keyword                           |
| ^                   | >          | :fa-times-circle: `<style>`'s `type` attribute is deprecated, if present should be 'text/css'.                        |                                   |
| ^                   | >          | :fa-times-circle: `<menu>` is referenced, but doesn't list `type` as a valid attribute.                               |                                   |
| **value**           | general    | `<button>` `<data>` `<input>` `<li>` `<meter>` `<option>` `<progress>` `<param>`                                      | string                            |
| ^                   | >          | Sets default value to be displayed and submitted (if not changed by user).                                            |                                   |
| **wrap**            | enumerated | `<textarea>`                                                                                                          | keyword                           |
| ^                   | >          | Defines word wrap for the element's content.                                                                          |                                   |

<!--TODO: List acceptable keywords for each attribute, that require specific strings as input!--> <!--Ugh, ...somewhere.-->
\* See: https://html.spec.whatwg.org/multipage/tables.html#table-descriptions-techniques

## TAGS

<nav>

| >                                               | [:fa-chevron-circle-up:Top](#top)         |                                            |
| ----------------------------------------------- | :---------------------------------------: | -----------------------------------------: |
| [:fa-chevron-circle-left:Previous](#attributes) |                                           | [:fa-chevron-circle-right:Next](#elements) |
| >                                               | [:fa-chevron-circle-down:Bottom](#bottom) |                                            |

</nav>

Tags indicate the beginning and/or end of an [element](#elements)'s description in the source code.

### Anatomy

#### General

Every tag begins with an opening `<` character, followed by the tag's **name**, and ends with a whitespace separated list of optional attributes -in case of a self-closing tag the ` /` string- and finally the `>` character.

```
opening angle-bracket
|
| tag's name
| |
| | closing angle-bracket
|/^\|
<tag>
```

#### Doctype

Must be the first line of the document, that isn't a whitespace or a comment.
Hints that the document is supposed to be a correctly formed html file.

```
`<`
 | case-insensitive
 |      |     `>`
 |      |      |
 |/-----^-----\|
 <!DOCTYPE html>
  |\--v--/|\-v/
  |   |   |  |
 `!`  |  ` ` |
      |    'html'
  'doctype'
```
<aside>There really aren't many options for this, it's just that string, and that's it.</aside>

#### Comment

Comments are multi-line strings, that are ignored by the interpreter. They are a good way to leave notes for yourself and others for future reference.

```
opening sequence
 |
 | arbitrary text*
 |     |
 |     | closing sequence
 |     |    |
/^-\/--^--\/^\
<!--comment-->
```

\* Can't contain `-->` though.

#### Container tag

Container tags are which have an opening and closing counterparts. The enclosed value isn't part of the tag, but only part of the element they describe.

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

Empty tags describe objects, that don't have (*and can't have*) nested internal elements.

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

Self-closing tags are the same as empty tags, but in an XML-conforming notation.

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

### Classification

Container
	:	A pair of opening and closing tags.
	:	Represents an [element](#elements).

Empty
	:	Tags without a closing counterpart.
	:	Represents a [void-element](#representation) in HTML.

Self-closing
	:	Same as empty, but has a trailing `/`.
	:	The XML, XHTML, SVG compatible version of an empty tag.
	:	>	:fa-exclamation-circle: Doesn't exist in HTML, but parsers interpret them as empty tags, so to maintain compatibility with XML~ it is customary to use them instead of an empty tag.
	:	>	:fa-exclamation-circle: If a leading whitespace is missing and the last attribute's value isn't quoted, the parser will assume that it's part of the attribute's value.  <aside>E.g.: :fa-times-circle:`<tag attribute=value/>` will be interpreted as the attribute having the value of "value/". To avoid this, (besides always quoting attr. values) a leading space should be added: :fa-check-circle:`<tag attribute="value" />`.</aside>

### Common Examples

<!--TODO: Decide: Introduce tags here, and only group them in elements, maybe?-->

<!--TODO-->

---
<aside>So far these were mostly structural components in the source code of a given document. Now let's see how a page emerges from these microstructures!</aside>

---

## <!--TODO: Chapter name - IDK, CONTENT TYPES?-->

<!--TODO-->
- Doctype
- Comment
- Text
- Entity
- Element
- CDATA section

## ELEMENTS

<nav>

| >                                         | [:fa-chevron-circle-up:Top](#top)         |                                              |
| ----------------------------------------- | :---------------------------------------: | -------------------------------------------: |
| [:fa-chevron-circle-left:Previous](#tags) |                                           | [:fa-chevron-circle-right:Next](#constructs) |
| >                                         | [:fa-chevron-circle-down:Bottom](#bottom) |                                              |

</nav>

An element is represented by its corresponding tag in HTML.

### Anatomy

<!--TODO: Mention inner/outer~text/html!-->

```
     outer text / html
            |
/-----------^-----------\
<tag>Nested content</tag>
\-v-/\------v-----/\--v-/
  |         |         |
opening tag |         |
            |         |
   inner text / html  |
                      |
              closing tag
```

### Classification

https://html.spec.whatwg.org/multipage/syntax.html#elements-2 <!--TODO: Move it footnote!-->

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

#### WHATWG

https://whatwg.org/ <!--TODO: Move it footnote!-->

The template element
	:	The template element isn't rendered, as it represents *nothing*.
	:	Instead, it stores a document fragment, that can be accessed by scripts to clone and insert into the document body.
	:	The element itself doesn't contain this fragment as a child.
	:	> `<template>`

Void elements
	:	Void elements don't have and must not have closing tags.
	:	As a result, they can't have any content.
	:	> `<area>`, `<base>`, `<br>`, `<col>`, `<embed>`, `<hr>`, `<img>`, `<input>`, `<link>`, `<meta>`, `<source>`, `<track>`, `<wbr>`


Raw text elements
	:	Must have both opening and closing tags.
	:	Can have text content, with some restrictions.
	:	> `<script>`,`<style>`

Escapable raw text elements
	:	Must have both opening and closing tags.
	:	Can have text content including entities, with some restrictions (e.g.: no ambiguous ampersand).
	:	> `<textarea>`, `<title>`

Normal elements
	:	Generally have both opening and closing tags.
	:	Certain element's opening and/or closing tags may be omitted, but it's a bad practice, so don't do it!
	:	Allowed children:
		- Comment
		- Text
		- Entity
		- Element
	:	> Rest of the tags.

Foreign elements
	:	Whose opening tag is self-closing, must not have a closing tag, and can't have children.
	:	Whose opening tag isn't self-closing, must have a closing tag, and can have any of the following children:
		- Comment
		- Text
		- Entity
		- CDATA section
		- Element
	:	> Elements from the MathML and SVG namespace.

#### Representation

<!--TODO: IDK, not void? - see: https://html.spec.whatwg.org/multipage/syntax.html#elements-2 -->
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

- Has semantic meaning (most of them have)
- Doesn't have semantic meaning

##### Notable non-semantic tags:

- Block:
	- `<div></div>`
- Inline:
	- `<span></span>`
	- `<b></b>`
	- `<i></i>`
	- `<u></u>`

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

### Grouping

https://developer.mozilla.org/en-US/docs/Web/HTML/Element

- Main root
- Document metadata
- Sectioning root
- Content sectioning
- Text content
- Inline text semantics
- Image & multimedia
- Embedded content
- SVG & MathML
- Scripting
- Demarcating edits
- Table content
- Forms
- Interactive elements
- Web components
- Obsolete & deprecated elements

## CONSTRUCTS
<!--FXME: Navigation-->
<nav>

| >                                             | [:fa-chevron-circle-up:Top](#top)         |                                              |
| --------------------------------------------- | :---------------------------------------: | -------------------------------------------: |
| [:fa-chevron-circle-left:Previous](#elements) |                                           | [:fa-chevron-circle-right:Next](#references) |
| >                                             | [:fa-chevron-circle-down:Bottom](#bottom) |                                              |

</nav>

<aside>
Most elements are useless on their own: they need to be placed in a hierarchical tree. While there's a degree of freedom, as to their parent-child relationship, there are certain complex structures, that require more rigorous element placement. The most obvious of these is the html document itself.
</aside>

### Page

Properly formatted html consists of the following parts, in the following order:

1. \[Byte Order Mark]
2. \[Comments &| whitespace]
3. [DOCTYPE](#doctype)
4. \[Comments &| whitespace]
5. Document element (`<html>`\[...]`</html>`)
6. \[Comments &| whitespace]

#### Hierarchy

1. `<!DOCTYPE html>`
2. `<html>`
	1. `<head>`
		- \[`<base />`]
		- \[`<link />`]
		- \[`<meta />`]
		- \[`<script>`]
		- \[`<style>`]
	2. `<body>`
		- elements of the page <!--TODO-->

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

### Table

<!--TODO-->

#### Hierarchy

1. `<table>`
	- `<tr>`
		- \[`<th>`]
		- `<td>`

<!--TODO-->

### Form

<!--TODO-->

#### Hierarchy

<!--TODO-->

---

## REFERENCES

<nav>

| >                                               | [:fa-chevron-circle-up:Top](#top)         |                               |
| ----------------------------------------------- | :---------------------------------------: | ----------------------------: |
| [:fa-chevron-circle-left:Previous](#constructs) |                                           | :fa-chevron-circle-right:Next |
| >                                               | [:fa-chevron-circle-down:Bottom](#bottom) |                               |

</nav>

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
*[WHATWG]:		Web Hypertext Application Technology Working Group https://whatwg.org/
*[XHTML]:		XML compatible HTML
*[XML]:			eXtensible Markup Language

---

<nav id="bottom">

| [:fa-arrow-alt-circle-left:Theory](../Theory/Index.md) | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Utilities](../Utilities/Index.md) |
| ------------------------------------------------------ | :------------------------------------------: | ------------------------------------------------------------: |
| [:fa-arrow-circle-left:Web Dev](Index.md)              | [:fa-arrow-circle-up:Web Dev](Index.md)      | [:fa-arrow-circle-right:CSS](CSS.md)                          |
| >                                                      | [:fa-chevron-circle-up:Top](#top)            |                                                               |

</nav>
