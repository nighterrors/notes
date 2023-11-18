<nav id="top">

[NOTES](../Index.md) / [Theory](Index.md) / [Data Structures](DataStructures.md)

| [:fa-arrow-alt-circle-left:INDEX](../Index.md)            | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Web Dev](../WebDev/Index.md) |
| --------------------------------------------------------- | :------------------------------------------: | -------------------------------------------------------: |
| [:fa-arrow-circle-left:Bitwise Ops](BitwiseOperations.md) | [:fa-arrow-circle-up:Theory](Index.md)       | [:fa-arrow-circle-right:Algorithms](Algorithms.md)       |

</nav>

# DATA STRUCTURES

<nav>

| >                                | [:fa-chevron-circle-up:Top](#top)         |                                       |
| -------------------------------- | :---------------------------------------: | ------------------------------------: |
| :fa-chevron-circle-left:Previous |                                           | [:fa-chevron-circle-right:Next](#toc) |
| >                                | [:fa-chevron-circle-down:Bottom](#bottom) |                                       |

</nav>



## TOC

<nav>

| >                                                    | [:fa-chevron-circle-up:Top](#top)         |                                    |
| ---------------------------------------------------- | :---------------------------------------: | ---------------------------------: |
| [:fa-chevron-circle-left:Previous](#data-structures) |                                           | [:fa-chevron-circle-right:Next](#) |
| >                                                    | [:fa-chevron-circle-down:Bottom](#bottom) |                                    |

</nav>

- [DATA STRUCTURES](#data-structures)
	- [TOC](#toc)
	- [OVERVIEW](#overview)
	- [PRIMITIVE DATA TYPES](#primitive-data-types)
	- [LINEAR](#linear)
		- [Arrays](#arrays)
			- [Strings](#strings)
			- [Matrices](#matrices)
		- [Linked Lists](#linked-lists)
		- [Stacks](#stacks)
		- [Queues](#queues)
		- [Dequeues](#dequeues)
	- [NON-LINEAR](#non-linear)
		- [Trees](#trees)
			- [Binary Trees](#binary-trees)
			- [Binary Search Trees](#binary-search-trees)
			- [Self-Balancing Binary Search Trees](#self-balancing-binary-search-trees)
				- [Red-Black Tree](#red-black-tree)
			- [AVL Trees](#avl-trees)
			- [B-Trees](#b-trees)
		- [Graphs](#graphs)
			- [Directed Graphs](#directed-graphs)
			- [Undirected Graphs](#undirected-graphs)
			- [Cyclic Graphs](#cyclic-graphs)
			- [Acyclic Graphs](#acyclic-graphs)
	- [HASHED](#hashed)
		- [Hash Tables](#hash-tables)
		- [Hash Maps](#hash-maps)
		- [Hash Sets](#hash-sets)
	- [ADVANCED](#advanced)
		- [Heaps](#heaps)
		- [Tries](#tries)
		- [Skip Lists](#skip-lists)
	- [COMPOSITE](#composite)
		- [Graphs of Lists](#graphs-of-lists)
		- [Trees of Arrays](#trees-of-arrays)
		- [Hybrid Structures](#hybrid-structures)
	- [SPECIALISED](#specialised)
		- [Bloom Filters](#bloom-filters)
		- [Bitsets](#bitsets)
		- [Interval Trees](#interval-trees)
		- [Fenwick Trees](#fenwick-trees)
	- [DYNAMIC](#dynamic)
		- [Dynamic Arrays](#dynamic-arrays)
		- [Linked Structures with Dynamic Memory Allocation](#linked-structures-with-dynamic-memory-allocation)
	- [SPATIAL](#spatial)
		- [Quad Trees](#quad-trees)
		- [Octrees](#octrees)
	- [TEXT-SPECIFIC](#text-specific)
		- [Gap Buffers](#gap-buffers)
		- [Suffix Trees](#suffix-trees)
		- [Ternary Search Trees](#ternary-search-trees)
	- [ABSTRACT](#abstract)
		- [Dictionary](#dictionary)
		- [Colour Models](#colour-models)
		- [Decision Tree](#decision-tree)

---

## OVERVIEW

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=0s

## PRIMITIVE DATA TYPES

The building blocks of data structures.

> Their utilisation and size varies between programming languages. <!--TODO: Following are the typical / common values of these-->

-	Void Type

	Void
		:	Indicates no received or returned value
		:	>	 E.g.: `int main(void)` receives no arguments (but returns an integer).
		:	>	 E.g.: `void function(float)` takes a floating-point argument, but returns nothing.

-	Boolean Type

	Boolean
		:	Represents `true` or `false` values.

-	Integer Types

	Byte
		:	8 bit signed integer
		:	>	 -128 to 127
	
	Short
		:	16 bit signed integer
		:	>	 -(2^15^) to 2^15^-1

	Int
		:	32 bit signed integer
		:	>	 -(2^31^) to 2^31^-1
	
	Long
		:	64 bit signed integer
		:	>	 -(2^63^) to 2^63^-1

-	Floating-Pint Types

	Float
		:	32 bit floating-point number
			>	-	1 b sign
			>	-	8 b exponent
			>	-	23 b fraction
	
	Double
		:	64 bit floating-point number
			>	-	1 b sign
			>	-	11 b exponent
			>	-	52 b fraction

-	Character Types

	Char
		:	Single ASCII character
			>	 7 b unsigned ASCII code point
			>	 or sometimes stored as a
			>	 8 b signed integer, where negative values should be avoided

	Unicode Character
		:	It's exact name varies by language
		:	Stores a Unicode character
		:	>	Size depends on encoding (UTF-8 | UTF-16 | UTF-32) and the position of the character itself.
			>	-	UTF-32: Always 32 b
			>	-	UTF-16: 16 b or 32 b
			>	-	UTF-8: 8 b, 16 b, 24 b or 32 b

---

## LINEAR

a.k.a. Sequential Data Structures.

### Arrays

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=843s

#### Strings



#### Matrices



### Linked Lists

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=2304s

### Stacks

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=159s

### Queues

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=159s

### Dequeues

a.k.a. Double-Ended Queue




## NON-LINEAR



### Trees

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=5448s

#### Binary Trees



#### Binary Search Trees



#### Self-Balancing Binary Search Trees



##### Red-Black Tree



#### AVL Trees



#### B-Trees



### Graphs



#### Directed Graphs



#### Undirected Graphs



#### Cyclic Graphs



#### Acyclic Graphs



## HASHED



### Hash Tables

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=6574s

### Hash Maps



### Hash Sets



## ADVANCED



### Heaps

a.k.a. Priority Queues



### Tries

a.k.a. Prefix Trees

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=7457s

### Skip Lists


## COMPOSITE



### Graphs of Lists



### Trees of Arrays



### Hybrid Structures



## SPECIALISED



### Bloom Filters



### Bitsets



### Interval Trees



### Fenwick Trees

a.k.a. Binary Indexed Trees

## DYNAMIC



### Dynamic Arrays



### Linked Structures with Dynamic Memory Allocation



## SPATIAL



### Quad Trees



### Octrees



## TEXT-SPECIFIC



### Gap Buffers



### Suffix Trees



### Ternary Search Trees



---

## ABSTRACT

These data structures can be represented in multiple ways and are commonly used for various tasks in different contexts.<!--FXME: Clarify-->

### Dictionary

https://www.youtube.com/watch?v=X8h4dq9Hzq8&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4&index=6&t=6377s


### Colour Models



### Decision Tree


<nav>

| >                                        | [:fa-chevron-circle-up:Top](#top)         |                                    |
| ---------------------------------------- | :---------------------------------------: | ---------------------------------: |
| [:fa-chevron-circle-left:Previous](#toc) |                                           | [:fa-chevron-circle-right:Next](#) |
| >                                        | [:fa-chevron-circle-down:Bottom](#bottom) |                                    |

</nav>



---

<nav id="bottom">

| [:fa-arrow-alt-circle-left:INDEX](../Index.md)            | [:fa-arrow-alt-circle-up:INDEX](../Index.md) | [:fa-arrow-alt-circle-right:Web Dev](../WebDev/Index.md) |
| --------------------------------------------------------- | :------------------------------------------: | -------------------------------------------------------: |
| [:fa-arrow-circle-left:Bitwise Ops](BitwiseOperations.md) | [:fa-arrow-circle-up:Theory](Index.md)       | [:fa-arrow-circle-right:Algorithms](Algorithms.md)       |
| >                                                         | [:fa-chevron-circle-up:Top](#top)            |                                                          |

</nav>