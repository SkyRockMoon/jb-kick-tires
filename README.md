# Kicking the Tires on Jupyter-Book

Tip: read the full book online at [skyrockmoon.github.io/jb-kick-tires](https://skyrockmoon.github.io/jb-kick-tires/01_intro.html)

This [mini-book](https://skyrockmoon.github.io/jb-kick-tires/01_intro.html) 'kicks the tires' on the open source [jupyter-book](https://jupyterbook.org) project. Jupyter-book can be used to create executable books that can be published as websites and/or paper (dead tree) books. 

The term "kick the tires" is an informal saying from North America that means:

> To inspect something to ensure it meets expected standards or has favored characteristics, typically before committing to purchasing or otherwise selecting it. 
>
> - [Wikitionary](https://en.wiktionary.org/wiki/kick_the_tires)

Jupyter-book is a free and open source project, but you are still in essence investing in it when you decide to author a book (or similar document) with it. The process of writing a book is a long and hard endeavour. If you have to spend a lot of time fussing and struggling with your chosen *tooling* then you will have cost yourself considerable time and money.

[Investopedia](https://www.investopedia.com/terms/k/kickingthetires.asp) makes the following points about "kicking the tires" on an investment:

> - Kicking the tires involves conducting a minimal amount of research before making an investment decision.
> - Taken from the context of car shopping, it is the opposite of conducting serious, in-depth research or due diligence.
> - Kicking the tires can nonetheless be a valid strategy as it cuts down on time and effort in conducting research by performing some cursory analysis, but can also lead investors astray with incomplete or wrong conclusions.
>
> Kicking the tires gets its name from shopping for an automobile. A car shopper who shows some interest in a car probably will not look under the hood or perform a serious comparative analysis versus similar models. However, this shopper usually takes a walk around the car from front to back to get a look and kick the tires. This shopper is not considered a serious buyer or a hot prospect. 

## Intended audience

The intended audience for this mini book is potential authors who are trying to figure out if jupyter-book will meet their needs. If you think the [example jupyter-books](https://executablebooks.org/en/latest/gallery.html) are beautiful, but are unsure if the tooling will fit with your writing style, then this mini-book is for you. If this mini-book convinces you to 'buy into' jupyter-book, then you can read the [official documentation](https://jupyterbook.org) to *actually* learn how to use the tool. What you see here is a very brief and superficial description of a very powerful tool.

Once setup, jupyter-book hides all of the *ugly* business of creating a book using more than a dozen separate tools from the user, but be warned that you will need some level of comfort with command line tools and python to truly appreciate the magic that is jupyter-book.

## Executable books

This mini book skips over many of the useful and powerful features of jupyter-book because we are just kicking the tires. The importance of what an executable book is, and why you might want to write one, however can not be glossed over. An [executable book](https://executablebooks.org/en/latest/) is a set of files that are compiled into a book very much like a computer program. Jupyter-book is not a what you see is what you get (WYSIWYG) editor like a typical word processor. The panels below compare the process of authoring a website and/or dead tree book on a technical topic with both tools. If your authoring the next great fictional novel - which is all prose - stop right now and get busy writing in a word processor. If you are authoring a technical document with figures, equations, tables, and code, keep reading because there is a good chance jupyter-book will be a good fit.

The process of writing a book with a word processor and jupyter-book are vastly different. Each option has parts of the process that are fast, and other parts that are slow. Ultimately if using jupyter-book is the correct choice for you comes down to your use case. 

- Using a word processor is fast initially and then revisions and changes later on become slow and painful. Quality assurance is difficult with a word processor. Figures, equations, tables, and numerical text results - e.g. mean of 34.2 (95% CI 29.2/37.8) - are all updated manually. Creating a book website manually is very challenging for an author that is not a software developer. 
- Jupyter-book requires a very significant investment upfront, and even after mastering the long list of tools writing is slower. However revisions and publishing can be made very rapidly. Collaboration is pleasant and streamlined. If you value the book website, jupyter-book generates a truly beautiful and best in class html output. The PDF output is also very professional. You can be assured that every reference and figure is correct and up to date. Jupyter-book will give you a warning if any of the references are missing.

I believe that jupyter-book is clearly the right tool for you if:

- You are authoring long and complex technical documents
- Have high standards for the accuracy and quality of your documents
- You already utilize the jupyter ecosystem for scientific computing
- Have a business model that is amendable with the open and reproducible research

There are certainly other use cases for jupyter-book that are more traditional, but in those cases the trade offs between jupyter-book and a word processor or a latex tool set are less dramatic. The skill of your collaborators to use advanced tools is also a major decision point.

## Mini-book overview

During the [setup](https://skyrockmoon.github.io/jb-kick-tires/02_setup.html) you will download a jupyter-book [template](https://github.com/SkyRockMoon/sample-book), here is what you can expect to do with that template:

- The [setup](https://skyrockmoon.github.io/jb-kick-tires/02_setup.html) page will show you how to install jupyter-book on a windows machine. The installation method in this book is opinionated, because it aims to show a user how to kick the tires. The [official jupyter-book documentation](https://jupyterbook.org/content/citations.html#references-and-citations) of course has details on other installation methods. Installing jupyter-book alone is not sufficient for success, the setup page also goes into all the other tools that are assumed to be present on your machine.    
- The [build](https://skyrockmoon.github.io/jb-kick-tires/03_build-pub.html) page shows you how to compile and generate both an html and PDF output of the book. This emphasizes the end goal of using jupyter-book, publishing! 
- The [content](https://skyrockmoon.github.io/jb-kick-tires/04_content.html) page introduces a minimal subset of the jupyter-book syntax so you can try your hand at authoring content and get a feel for the jupyter-book workflow. It is critical to understand that authoring content is slower, so that revising and publishing can be faster. Again, only you can determine if this writing model fits your use case. But at least you can quickly kick the tires and decide for yourself.
- The [conclusion](https://skyrockmoon.github.io/jb-kick-tires/05_conclusion.html) will wrap everything up and provide a number of jumping off points to possibly increase the benefit of using jupyter-book.