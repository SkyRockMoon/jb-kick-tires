(content_v2)=
# Add content to the book v2

```{warning}
This book is still being actively developed and this version of should be considered a rough draft. [Follow me on GitHub](https://docs.github.com/en/github/getting-started-with-github/following-people#:~:text=If%20someone%20you%20follow%20stars,Unfollow%20under%20their%20profile%20image.) to receive notifications when updates are made.  
```

This section covers how to add content to your book. To utilize jupyter-book you will have to ultimately become very familiar with the [official jupyter-book documentation](https://jupyterbook.org). However for the purposes of kicking the tires this section will take you through the features that are either critical to use, or just cool. Many details will be skipped for the purposes of illustrating what authoring a book with jupyter-book might be like in practice. Consider this chapter a minimum subset of the available functionality needed for authoring content.

In an effort to make leanring syntax more exciting this section will take you through a narrative of adding content to the [book you cloned](clone) while installing jupyter-book. After getting a feel for how everything works in this section you will probably graduate to just using the [jupyter-book cheat sheet](https://jupyterbook.org/reference/cheatsheet.html) to rapidly find the syntax details you need. 

Your mission, if you choose to accept it, is to write a (very brief and totally fictitious) book about dinosaurs using the sample book you cloned earlier as a template. Don't worry if your paleontology skills are rusty, the focus of this activity is on writing the described syntax. You can expect to accomplish the following tasks while reading this chapter.

1. [Create a new chapter about dinosaurs](new-chapter)
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

- sample-book: this is your top level working directory
    - book: this directory contains the content of your book
        - _build: this directory is generated for you when you build the book
            - html: the html version of your book (if you chose this option)
            - pdf: the pdf version of your book (if you chose this option)
        .md files: these are markdown files that contain mostly text
        .ipynb files: these are notebook files that contain mostly computations and analysis 
        _toc.yml: This file controls your table of contents
        _config.yml: This file controls the configuration that determines the look and feel of your book 
    - environment.yml: file anaconda uses to automatically  setup your environment if you are using anaconda
    - requirements.txt: file used to create a python virtual environment if you are not using anaconda
    - README.md: describes the contents of this repository
    - .gitignore: a file that tells git to ignore some directories



## Setting up your book chapters

```yaml
- file: intro
  numbered: true

- file: lit-review
- file: methods
- file: references
```

## Target references

- numbered references
- link references

## Markdown vs MyST

## Add content

### Headings

### Regular text

## Glue results from your notebooks

## Reader/reviewer feedback

### Annotations

### Comments