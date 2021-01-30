(content_v2)=
# Add content to the book v2

```{warning}
This book is still being actively developed and this version of should be considered a rough draft. [Follow me on GitHub](https://docs.github.com/en/github/getting-started-with-github/following-people#:~:text=If%20someone%20you%20follow%20stars,Unfollow%20under%20their%20profile%20image.) to receive notifications when updates are made.  
```

This section covers how to add content to your book. To utilize jupyter-book you will have to ultimately become very familiar with the [official jupyter-book documentation](https://jupyterbook.org). However for the purposes of kicking the tires this section will take you through the features that are either critical to use, or just cool. Many details will be skipped for the purposes of illustrating what authoring a book with jupyter-book might be like in practice. Consider this chapter a minimum subset of the available functionality needed for authoring content.

In an effort to make leanring syntax more exciting this section will take you through a narrative of adding content to the [book you cloned](clone) while installing jupyter-book. After getting a feel for how everything works in this section you will probably graduate to just using the [jupyter-book cheat sheet](https://jupyterbook.org/reference/cheatsheet.html) to rapidly find the syntax details you need. 

Your mission, if you choose to accept it, is to write a (very brief and totally fictitious) book about dinosaurs using the sample book you cloned earlier as a template. Don't worry if your paleontology skills are rusty, the focus of this activity is on writing the described syntax. You can expect to accomplish the following tasks while reading this chapter.

1. [Outline your book chapters](new-chapter)
1. [Write some basic content using Markdown and MyST](mark-vs-myst)
    - [Headings](headings)
    - [Regular text](regular-text)
    - [Lists](num-bullet-lists)
    - [Code blocks](code-blocks)
    - [Notes](doc-notes)
      - [Footnotes](footnotes)
      - [Margin notes](margin-notes)
    - [Links and section references](ref)
    - [Admonitions](admonition)
    - [Equations](math-formula)
    - [Tables](tables)
1. [Embed (glue) results from your analysis in a jupyter notebook into your text content](glue-results)
    - [Glue numbers](glue-number)
    - [Glue figures](glue-figure)
1. [Reference numbered content](numbered-ref): [figures](numbered-figure), [tables](numbered-table), [equations](numbered-eq), 
1. [Create Citations/Bibliography](citations)
1. [Enable Annotations](annotations)
1. [Enable Reader comments](comments)

## File structure
If you look at the `sample-book` that you cloned during the install you will see the following structure and files.

- `sample-book`: this is your top level working directory
    - `book`: this directory contains the content of your book
        - `_build`: this directory is generated for you when you build the book
            - `html`: the html version of your book (if you chose this option)
            - `pdf`: the pdf version of your book (if you chose this option)
        `.md` files: these are markdown files that contain mostly text
        `.ipynb` files: these are notebook files that contain mostly computations and analysis 
        `_toc.yml`: This file controls your table of contents
        `_config.yml`: This file controls the configuration that determines the look and feel of your book 
    - `environment.yml`: file anaconda uses to automatically setup your environment if you are using anaconda
    - `requirements.txt`: file used to create a python virtual environment if you are not using anaconda
    - `README.md`: describes the contents of this repository
    - `.gitignore`: a file that tells git to ignore the _build directory among other things that don't need to be in version control

We will mainly be editing the files inside the `book` directory to show what the content creation process is like with jupyter-book.

(new-chapter)=
## Setting up your book chapters

Organization is key to the writing process, imagine you have outlined the following chapters for your book:

- Abstract
- Introduction
- Literature review
- Methods
- References

To create your book you would start by creating an empty markdown (`.md`) file for each of your chapters. You can name the files anything you want, but consider using similar names. The sample-book already contains the following files for you:

- Abstract: `abstract.md`
- Introduction: `intro.md`
- Literature review: `lit-review.md`
- Methods: `methods.md`
- References: `references.md`

```{note}
Writing your content in a markdown (`.md`) file is one of two ways to author content. The other is to write the same syntax described here into a jupyter notebook (`.ipynb`). Both methods work equally well, but I chose to focus on markdown because I personally feel it a more appropriate method for long form works. This is purely my opinion, and as they say, your mileage may vary.
```

An abstract is traditionally part of a journal paper, not a book. Because print and web are not equivalent mediums there are times when you have to make accommodations for the differences. In this case your abstract will act as a landing page for your website.

```{margin}
You can build your book from your working directory using `jupyter-book build book` to see the changes you are making.
```

If you build the book you will notice that you can only see the introduction. We need to tell jupyter-book which files are in your table of contents and therefore should be rendered to the reader. Update the `_toc.yml` file to include all of your chapters.


```yaml
# _toc.yml

- file: abstract
  numbered: true

- file: intro
- file: lit-review
- file: methods
- file: references
```

```{note}
Notice how the `.md` extension is not included in the `_toc.yml` file. Both markdown (`.md`) and jupyter notebook (`.ipynb`) files can be designated chapters in your jupyter-book. Using notebooks directly as content is not covered in this mini-book, see the [official docs](https://jupyterbook.org) for full details.
```

After saving your changes to `_toc.yml`, build your book again, and then refresh your browser, to see your new chapters.

```{tip}
After every prompt to add something, rebuild the book, and refresh your browser to view the changes. If the changes do not appear first check to see if you actually saved the file you were updating. You can also scroll up in the terminal and look for errors/warnings.

Because you will need to issue the `build` command repeatedly while authoring your book it may be useful to know how to access your command line history. In most terminals simply press the up key once to see the last command that you typed. Press the up key twice to see what you typed two commands ago, and so on. Most of the time you can simply press the up key once and then press enter to build your book. 
```

## Headings

Presumably a real outline for a book will describe more than just the chapter titles. Headings are used to define sub-sections in your book. Headings are created by using a series of ampersands:

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    # Heading level 1
    ## Heading level 2
    ### Heading level 3
    #### Heading level 4
    ##### Heading level 5
    ###### Heading level 6
    ```
  - ```md
    # Did dinosaurs have feathers?
    ```
  - Level 1-6 headings, denoted by number of `#`. Each chapter can only have one top level header. Avoid skipping levels (e.g. heading level 5 directly under a level 1 heading)
``````

Add some additional headings to your introduction (`intro.md`):

```md
<!-- intro.md -->
# Introduction

Achillesaurus Diceratops Malarguesaurus Sellacoxa Zhejiangosaurus...

## Fossil record supporing the existance of feathers
There is evidence of feathers in the fossil record...

### China
These locations in China have fossils that show feathers...

### Australia
These locations in Australia have fossils that show feathers...
```
(regular-text)=
## Regular text
Regular (body) text is simply typed into your content file without any special syntax. Add a new section with some body text at the bottom of your introduction.

```md
<!-- intro.md -->
## Other supporting evidence for feathered dinosaurs
This is body text.

A carriage return is required to make a line break. 
These two lines will be part of the same paragraph.

This line will be part of the next paragraph.
```
(num-bullet-lists)=
## Numbered and bulleted lists
Lists are often a way to summarize key points that you hope a reader skimming your book will pay attention to, or provide step by step instructions.

### Ordered lists

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    1. First item
    1. Second item
        1. First sub-item
    ```
  - 1. First item
    1. Second item
        1. First sub-item
  - Assign every item in the list a '1.' and let the compiler properly number the list. This is crucial if you later have to add an item in the middle of the list and don't want to manually renumber.
``````
### Unordered list

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Example
  - Result
  - Note
* - ```md
    * First item
    * Second item
      * First subitem
    ```
  - * First item
    * Second item
      * First subitem 
  - An asterisk (*) or dash (-) can be used to denote an unordered list.
``````

Add a list of locations where dinosaurs are found to the introduction:

```md
<!-- intro.md -->
## Fossil record supporting the existence of feathers
There is evidence of feathers in the fossil record...

Dinosaurs with feathers have been found in:

- Asia
- Australia
- North America
- The Atlantic ocean 
```




## Cross references

Cross references are essential in a technical document to help you refer to past chapters and otherwise direct the readers attention to other parts of your book. There are two ways accomplish a cross reference in jupyter-book depending on what you are referencing.

- Numbered references point to numbered quantities (figures, equations, tables)
- Link references internally point to headings, or can point to an external website or document

## Markdown vs MyST

## Add content

### Headings

### Regular text

## Glue results from your notebooks

## Reader/reviewer feedback

### Annotations

### Comments