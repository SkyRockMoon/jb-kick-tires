(content)=
# Add content to the book

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

(new-chapter)=
## Create a new chapter
In your `book` directory that you [cloned earlier](clone), create a new file markdown file named `05_dino.md`. Place the following content into this file and save the file:

*05_dino.md*

    (dino)=
    # Did dinosaurs have feathers?

    Write your content here...

```{note}
Writing your content in a markdown (`.md`) file is one of two ways to author content. The other is to write the same syntax described here into a jupyter notebook (`.ipynb`). Both methods work equally well, but I chose to focus on markdown because I personally feel it a more appropriate method for long form works. This is purely my opinion, and as they say, your mileage may vary.
```

Next, open `_toc.yml` and add an entry for your new chapter. The file should look like this:

*_toc.yml_*

    - file: 01_intro
    - file: 02_setup
    - file: 03_build-pub
    - file: 04_content
    - file: 05_dino

```{note}
Notice how the `.md` extension is not included in the `_toc.yml` file. Both markdown (`.md`) and jupyter notebook (`.ipynb`) files can be designated chapters in your jupyter-book. Using notebooks directly as content is not covered in this mini-book, see the [official docs](https://jupyterbook.org) for full details.
```

Save everything and then rebuild the book with `jupyter-book build book`. If all goes well you should now see your new book chapter in the left hand navigation bar. 

```{tip}
After every prompt to add something to `05_dino.md` rebuild the book and refresh your browser to view the changes. If the changes do not appear first check to see if you actually saved the file you were updating. You can also scroll up in the terminal and look for errors/warnings.

Because you will need to issue the `build` command repeatedly while authoring your book it may be useful to know how to access your command line history. In most terminals simply press the up key once to see the last command that you typed. Press the up key twice to see what you typed two commands ago, and so on. Most of the time you can simply press the up key once and then press enter to build your book. 
```
(headings)=
## Headings
Headings are created by using a series of ampersands:

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
When writing it is often convenient to reference previous chapters or sections in your book. The `(dino)=` syntax represents a [target header](https://jupyterbook.org/reference/cheatsheet.html#target-headers). Regular headers can and do change, target headers are not visible to readers and therefore should not be changed once they are established to avoid breaking links. Don't put any spaces in your target headers.

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    (target_header)=
    ```
  - ```md
    (dino)=
    # Did dinosaurs have feathers?
    ```
  - See [below](ref) for instructions on how to reference target headers.
``````

(mark-vs-myst)=
## Markdown vs MyST
You will hear two different names for the syntax being thrown around in this chapter. Markdown and Markedly Structured Text (MyST). While there are important differences in the two, none of those differences will matter to a content creator. Just use the syntax described here in your document and thank the creators/maintainers of jupyter-book for saving you from worry about the details because 'it just works (TM)'.

(regular-text)=
## Regular text
Regular (body) text is simply typed into your content file without any special syntax. Edit `05_dino.md` to include additional text:

```{margin}
The gyberish at the end of the paragraph is [dinosaur filler text](https://dinoipsum.herokuapp.com/).
```

*05_dino.md*

```md
(dino)=
# Did dinosaurs have feathers?

There is now evidence that dinosaurs may have all had feathers. Part of the controversy of this statement is defining exactly what a feather is...Achillesaurus Diceratops Malarguesaurus Sellacoxa Zhejiangosaurus Incisivosaurus Colonosaurus Albertaceratops Eupodosaurus Lapparentosaurus Siamosaurus Sauraechinodon Frenguellisaurus Chasmosaurus Rapator Brasileosaurus Riojasaurus Ruehleia Qinlingosaurus Anchisaurus Pantydraco Rebbachisaurus Appalachiosaurus Lapampasaurus Cryolophosaurus Gryphoceratops Strenusaurus Nectosaurus Squalodon Anatotitan Hallopus Velociraptor Pinacosaurus Archaeornithomimus Yueosaurus Vulcanodon Szechuanosaurus Hallopus Pleuropeltus.
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

Add a list of locations where dinosaurs are found to `05_dino.md`:

    Dinosaurs with feathers have been found in:
        - Asia
        - Australia
        - North America
        - The Atlantic ocean 

(code-blocks)=
## Code blocks
There are a couple of ways to draw attention to code or commands that a user following your book should use.


### Commands
Any text placed inside of back ticks will be highlighted.

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    `command`
    ```
  - Run this `command` to achieve greatness
  - 
``````

### Preformatted text
Any text that is indented with a single tab will be considered preformatted text. This can be useful for drawing attention to commands that a reader should execute by breaking the flow of the text.

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    Execute this command:
        $ sudo apt update
    ```
  - Execute this command:
    ```
    $ sudo apt update
    ```
  - Note the copy button in the upper right hand corner
``````

### Code blocks
Snippets of code with syntax highlighting can be included in your document as well.  

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    ```python
    import numpy as np
    print(f'This is index {ii}')
    ```
    ``````
  - ```python
    import numpy as np
    print(f'This is index {ii}')
    ```
  - Python is one of many languages that syntax highlighting is supported for.
``````
Add some instructions for installing a fictional software tool to `05_dino.md`:

*05_dino.md*

``````md
You can install the feather identification toolbox via pip:
    pip instal -U featherid

Then modify your script to locate feathers on pictures of dinosaur bones. This uses computer vision in a way that is beyond the scope of this document to explain, and your ability to understand.

```python
import featherid as fid

for i, X in enumerate(files):
    Y[i] = fid.find(X)
```
``````

(doc-notes)=
## Notes
```{margin}
Best practices for using margin notes, and many other elements, are described in [Edward Tufte's](https://www.edwardtufte.com/tufte/books_vdqi) books, and online at [Tufte CSS](https://edwardtufte.github.io/tufte-css/) 
```

Adding notes to your content can help readers who wish to learn more investigate further without breaking the flow of your text. In jupyter-book there are two kinds of notes that can be used. Traditional footnotes and Tufte style margin notes. 

```{warning}
Margin notes are not fully supported when generating a PDF.
```
(footnotes)=
### Footnotes
Footnotes can be used to add an interesting comment to text that is not directly relevant to the argument of the text.

``````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    This is body text [^footnote-label].
    [^footnote-label]: This is my footnote.
    ```
  - Dinosaurs may have had feathers [^footnote-label]. 
  - Click to follow the footnote which is located at the bottom of the page.
``````
[^footnote-label]: This is my footnote which wil be placed at the bottom of the page. Conveniently you can click on the footnote number to return to the text that contains the note.

(margin-notes)=
### Margin notes
```{margin} 
This is a margin note
```

Margin notes, or sidenotes as they were originally called, are located in the margin.

> Sidenotes are like footnotes, except they don’t force the reader to jump their eye to the bottom of the page, but instead display off to the side in the margin. Perhaps you have noticed their use in this document already. You are very astute.
> --- [Tufte CSS](https://edwardtufte.github.io/tufte-css/)

```{margin} Optional title
Margin note text goes here
```

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    ```{margin} Optional title
    Margin note text goes here
    ```
    ``````
  - See margin
  - Margin notes are a great example of the web not being like print.
`````````
(ref)=
## Links/References

There are many ways to generate a link/reference in jupyter-book. Here are the two simplest methods. See [numbered references](numbered-ref) for more advanced use cases.

### Markdown links
To link to a target header that you created with the `(target-header)=` syntax simply 

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    Body text [link text](target-header)
    ``````
  - See the [references section](ref) for more details.
  - Markdown links can also direct a reader to an external website, or just another markdown header. However using target headers is considered a best practice.
`````````
(doc-links)=
### Document links
If you want to link to another document outside the current document you are writing in, then use a document link.

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    Body text {doc}`document`
    ``````
  - See the {doc}`setup` page for more details.
  - There are multiple ways to style this link, check the [official docs](https://jupyterbook.org/reference/cheatsheet.html#reference-documents) for a complete description.
`````````
Add some [notes](doc-notes) [references](ref), and [links](doc-links) to `05_dino.md` to help backup your assertions about feathers.

*05_dino.md*

``````md

```{margin}
The filler text is generated from actual dinosaur names. Placing the margin note above the paragraph it is associated with usually results in proper placement of the note.
```
There is now evidence that dinosaurs may have all had feathers. Part of the controversy of this statement is defining exactly what a feather is [^feather]...Achillesaurus Diceratops Malarguesaurus Sellacoxa Zhejiangosaurus Incisivosaurus Colonosaurus Albertaceratops Eupodosaurus Lapparentosaurus...See the next section for more [dinosaur names](more). 

[^feather]:To be a true feather, there are characteristics that need to be fulfilled. The structures must be made from a protein called beta-keratin, they must be branched, and finally they must originate from a follicle. For details see: [The first dinosaurs probably didn't have feathers](https://www.nhm.ac.uk/discover/news/2020/march/the-first-dinosaurs-probably-didn-t-have-feathers.html).

(more)=
## More dinosaur names
Chebsaurus Venaticosuchus Yuanmousaurus Rileyasuchus Tianyulong Auroraceratops Acrocanthosaurus Lukousaurus Razanandrongobe Jenghizkhan Malawisaurus Therizinosaurus Razanandrongobe Eustreptospondylus Unescoceratops Shixinggia Parvicursor Gwyneddosaurus Abelisaurus Suzhousaurus Picrodon Herrerasaurus Brontomerus Tangvayosaurus Ultrasaurus Achillobator Quilmesaurus Trigonosaurus Zapsalis

``````

(admonition)=
## Admonitions

> An admonition is advice with a hint of scolding, a warning not to do something. When you're cautioned or warned about some mistake you might be just about to make, or some looming danger, you're receiving an admonition. --- [vocabulary.com](https://www.vocabulary.com/dictionary/admonition)

```{tip}
These little boxes are admonition's. Some of the available admonitions include: 
- Admonition
- Attention
- Caution
- Danger
- Error
- Hint
- Important
- Note
- Title
- Warning
```

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    ```{admonition} Optional title
    Text or markdown here
    ```
    ``````
  - ```{admonition} Watch out!
    Dinosaurs have sharp teeth 
    ```
  - 
`````````

Add an admonition to `05_dino.md` alert your reader to a common mistake.

*05_dino.md*

``````md
```{warning}
Feathers are very difficult to identify in a fossil. Extreme care should be taken when distinguishing between a feather and other grit and debris that may be present.
```
``````

(tables)=
## Tables

The `{list-tables}` directive is provided for creating numbered tables. For example this markup produces the result seen in {numref}`my-table-label`. To reference this table by number use `` {numref}`my-table-label` ``.

```{note}
There is a table available in markdown as well, but I would suggest that you use the `list-table` directive because it is easier to write and includes a caption. 
```

``````md
```{list-table} General characteristics of Sepia officinalis accessory sex gland ESTs [^sepia].
:header-rows: 0
:name: my-table-label

* - Number of high quality **sequenced** cDNA
  - 576
* - Number of high quality ESTs
  - 560
* - Average length of high quality ESTs (bp)
  - 974.6
* - Number of contigs
  - 37
* - Number of singletons
  - 186
* - Redundency
  - 66.7%
```
``````

```{list-table} General characteristics of Sepia officinalis accessory sex gland ESTs [^sepia].
:header-rows: 0
:name: my-table-label

* - Number of high quality **sequenced** cDNA
  - 576
* - Number of high quality ESTs
  - 560
* - Average length of high quality ESTs (bp)
  - 974.6
* - Number of contigs
  - 37
* - Number of singletons
  - 186
* - Redundency
  - 66.7%
```
[^sepia]: Enault, Jeremy & Zatylny-Gaudin, Celine & Bernay, Benoît & Lefranc, Benjamin & Leprince, Jérôme & Baudy-Floc'h, Michèle & Henry, Joël. (2012). A Complex Set of Sex Pheromones Identified in the Cuttlefish Sepia officinalis. PloS one. 7. e46531. 10.1371/journal.pone.0046531. 

Tables with more than two columns require you to describe how to spread out the columns with a `:widths: auto` argument. {numref}`three-column-table` shows an example of a three column table. Also, note the use of column headers.

``````md
```{list-table} Three column table
:header-rows: 1
:widths: auto
:name: three-column-table

* - Col 1
  - Col 2
  - Col 3
* - Data 1.1
  - Data 1.2
  - Data 1.3
* - Data 2.1
  - Data 2.2
  - Data 2.3
```
``````

```{list-table} Three column table
:header-rows: 1
:widths: auto
:name: three-column-table

* - Col 1
  - Col 2
  - Col 3
* - Data 1.1
  - Data 1.2
  - Data 1.3
* - Data 2.1
  - Data 2.2
  - Data 2.3
```
(math-formula)=
## Equations

If you need to include a mathematical formula that can easily be achieved. The formula is considered inline if it flows with the text like this, $a^2 +b^2 = c^2$. Or you can add a block formula which is centered on its own line:

$$
p(H|e) = \frac{p(H)p(e|H)}{p(e)}
$$

Formulas are written in $\LaTeX$. A [good cheat sheet](https://users.dickinson.edu/~richesod/latex/latexcheatsheet.pdf) will show most of the common symbols you will need to know. If that fails you can draw the symbol with your mouse and an [algorithm](https://detexify.kirelabs.org/classify.html) will identify your symbol and and show you the $\LaTeX$ code that will generate it.

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    This is an inline formula $1/2sin(\theta)$
    ``````
  - This is an inline formula $1/2sin(\theta)$
  - 
* - ``````md
    This is a block formula

    $$
    f(x) = x_1 +2x_2
    $$
    ``````
  - This is a block formula

    $$
    f(x) = x_1 +2x_2
    $$
  - 
* - ``````md
    This is a numbered formula

    $$
    z=\sqrt{x^2+y^2}
    $$ (myLabel)
    ``````
  - This is a numbered formula

    $$
    z=\sqrt{x^2+y^2}
    $$ (numbered-equation)
  - See [numbered references](numbered-eq) to refer to this equation by its number
`````````

(glue-results)=
## Embed results
This next section covers a key element of jupyter-book, the ability to embed results from a jupyter notebook into your content. This enables the development of [executable books](exec-book). Adding this capability will slow your writing process down considerably, but over the course of multiple revisions it may just save your sanity.

``````{note}
This section assumes that you have previously created a jupyter notebook. You can read more about [notebooks](notebooks) to get a feel for their true power. For now, just create a sample notebook that we can work with:

1. In your virtual environment, install the prerequisite python libraries `pip install scipy numpy matplotlib myst_nb`
1. Navigate to your book directory `cd book`
1. Open jupyter notebook with `jupyter notebook --no-browser`
1. Follow the link provided in the console
1. Create a new Python 3 notebook and name it `myNotebook`
1. Paste the following into the first cell of the notebook and press `shift + enter` to execute the cell

```python
import numpy as np
import matplotlib.pyplot as plt
from myst_nb import glue

fig, ax = plt.subplots()
N = 100
x = np.random.randn(N)
y = np.random.randn(N)

plt.plot(x,y,'o')
plt.xlabel('Feather Length [mm]')
plt.ylabel('Bone Diameter [cm]')
glue('random-fig',fig, display=False)

myVar = "42"
glue("myLabel", myVar )

m = np.mean(y)  # mean 
s = np.std(y)   # standard deviation
up = m+2*s      # 95% confidence level
low = m-2*s     # 5% confidence level

glue('avg',m, display=False)
glue('upper',up, display=False)
glue('lower',low, display=False)
```
``````

In reality your writing process likely starts with a notebook. After days of meticulous data collection and analysis you finally arrive at a result that you believe is publishable. At that point you would fire up jupyter-book and start describing your results. There are two major use cases for embeding notebook results to consider:

- Numerical content
- Figures

In all cases you make a variable or figure available in your notebook with the `` glue('<label>',<variable>) `` *function*. The `variable` is the object that you created in your notebook. You can give it an easy to remember name with the `label`. You reference the `label` in your writing when you use the `glue` directive. See below for the specific use cases of the `glue` directive to embed content. 

```{important}
The critical benefit of *gluing* notebook outputs into your document is when you update the variable in your notebook, the changes automatically propogate into your document the next time you rebuild your book. Just make sure your notebook is inside your book directory and jupyter-book takes care of the rest.
```

(glue-number)=
### Numerical content

Numerical content is just numbers. 

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    The answer to the 
    “Great Question” of “Life, 
    the Universe and Everything”
     is {glue:}`myLabel`.
    ```
  - The answer to the “Great Question” of “Life, the Universe and Everything” is {glue:}`myLabel`
  - 
`````````

In practice you may need to round your results to a few signifigant digits. All of the [python format strings](https://mkaz.blog/code/python-string-format-cookbook/#f-strings) can be used with the `{glue:text}` directive.

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ```md
    The result was {glue:text}`avg` 
    (95% CI {glue:text}`lower`/
    {glue:text}`upper`).
    ```
  - The result was {glue:text}`avg` (95% CI {glue:text}`lower`/{glue:text}`upper`).
  - Unformatted text
* - ```md
    The result was 
    {glue:text}`avg:2.2f` 
    (95% CI {glue:text}`lower:2.2f`/
    {glue:text}`upper:2.2f`).
    ```
  - The result was {glue:text}`avg:2.2f` (95% CI {glue:text}`lower:2.2f`/{glue:text}`upper:2.2f`).
  - Formatted as a two digit floating point number
`````````

(glue-figure)=
### Figures

Figures typically help to visualize the results of an analysis. A figure can be added to a document with a just a `` {glue:}`<figure-label>` ``, but it is usually more helpful in a technical document to add a numbered figure with a caption.

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    ```{glue:figure} <figure-label>
    ---
    figwidth: 150px
    name: "<figure-reference-name>"
    ---

    Figure caption written in markdown
    ```
    ``````
  - ```{glue:figure} random-fig
    ---
    figwidth: 200px
    name: "fig:random"
    ---

    Feather length vs bone diameter
    ```
  - See [numbered refrences](numbered-ref) to refer to this figure by its figure number.
`````````

(numbered-ref)=
## Numbered Refrences

Numbered references are a more advanced version of [regular references](ref), but very common in technical documents. To make a numbered reference you of course have to have a numbered object to refer to. Numberd references can be made to:

- Figures
- Tables
- Equations

```{tip}
Equations are the odd ball in this group. Figures and tables use the `{numref}` directive, while equations have their own `{eq}` directive. If you reference a figure or table the reference will be inserted as `Figure X` or `Table Y`. If you reference an equation it will be inserted as `(1)`.
```

(numbered-figure)=
### Figures

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    {numref}`<numbered-label>`
    ``````
  - See {numref}`fig:random` for the relationship between...
  - See the [official docs](https://jupyterbook.org/reference/cheatsheet.html#referencing-figures) for many more options
`````````
(numbered-table)=
### Tables
To reference a table by number use `` {numref}`my-table-label` ``.

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    {numref}`<label>`
    ``````
  - See {numref}`my-table-label` for a summary of results
  - See the [official docs](https://jupyterbook.org/reference/cheatsheet.html#referencing-tables) for many more options
`````````

(numbered-eq)=
### Equations

`````````{list-table}
:header-rows: 1
:widths: 20 15 15

* - Syntax
  - Example
  - Note
* - ``````md
    {eq}`<label>`
    ``````
  - Equation {eq}`numbered-equation` shows the result
  - A [numbered equation](math-formula) is needed to use this method
`````````

(citations)=
## Citations

Citations require couple steps. 

- Generate a refrences.bib file and place it in your `book` directory. This should be a standard option in any reference manager (e.g. [Zotero](https://www.zotero.org/)). See {doc}`references` if you need a sample `.bib` file for testing.
- Cite using the directive`` {cite}`citation-label` ``
- Include a list of citations at the end of the document

`````````{list-table}
:header-rows: 1
:widths: auto

* - Syntax
  - Example
  - Note
* - ```md
    {cite}`citation-label`
    ```
  - As described in {cite}`stone_bayes_2015`
  - The citation will not display properly until the bibliography is linked as shown below
`````````

Then include the bibliography with:

``````md
```{bibliography} references.bib
:filter: docname in docnames
```
``````

Your bibliography will be automatically generated like this, and can be formatted to meet any style guide.

```{bibliography} references.bib
:filter: docname in docnames
```

(annotations)=
## Annotations
A very cool integration that jupyter-book makes available is annotations. An annotation is a way for readers to make notes on your document. Seeing is believing, so view the [demo](https://jupyterbook.org/interactive/comments/hypothesis.html) on the jupyter-book website to see it in action and learn how to adjust the `_config.yml` file to enable annotations.

(comments)=
## Reader Comments
Jupyter-book makes integrating a section for reader comments a very easy process (assuming you have a github account). Add the following to your `_config.yml` file to enable comments:

```md
html:
  comments:
    utterances:
      repo: "github-org/github-repo"
```
Where `github-org` is your user name or organization, and `github-repo` is the repository where you are hosting your project. So in the case of this book - which is hosted at https://github.com/SkyRockMoon/jb-kick-tires - the org is `SkyRockMoon` and the repo is `jb-kick-tires`. See below, this site has comments enabled.

```{note}
The comments integration is not visible when viewing your book *locally*. You must [publish to GitHub](build-pub) to see the integration.
```