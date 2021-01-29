# Introduction

```{warning}
This book is still being actively developed and this version of should be considered a rough draft. [Follow me on GitHub](https://docs.github.com/en/github/getting-started-with-github/following-people#:~:text=If%20someone%20you%20follow%20stars,Unfollow%20under%20their%20profile%20image.) to receive notifications when updates are made.  
```

This mini-book 'kicks the tires' on the open source [jupyter-book](https://jupyterbook.org) project. Jupyter-book can be used to create [executable books](exec-book) that can be published as websites and/or paper (dead tree) books. 

The term "kick the tires" is an informal saying from North America that means:

> To inspect something to ensure it meets expected standards or has favored characteristics, typically before committing to purchasing or otherwise selecting it. 
>
> - [Wikitionary](https://en.wiktionary.org/wiki/kick_the_tires)

Jupyter-book is a free and open source project, but you are still in essence buying it when you decide to author a book (or similar document) with it. The process of writing a book is a long and hard endeavour. If you have to spend a lot of time fussing and struggling with your chosen *tooling* then you will have cost yourself considerable time and money.

[Investopedia](https://www.investopedia.com/terms/k/kickingthetires.asp) makes the following points about "kicking the tires" on an investment:

> - Kicking the tires involves conducting a minimal amount of research before making an investment decision.
> - Taken from the context of car shopping, it is the opposite of conducting serious, in-depth research or due diligence.
> - Kicking the tires can nonetheless be a valid strategy as it cuts down on time and effort in conducting research by performing some cursory analysis, but can also lead investors astray with incomplete or wrong conclusions.
>
> Kicking the tires gets its name from shopping for an automobile. A car shopper who shows some interest in a car probably will not look under the hood or perform a serious comparative analysis versus similar models. However, this shopper usually takes a walk around the car from front to back to get a look and kick the tires. This shopper is not considered a serious buyer or a hot prospect. 

(intended-audience)=
## Intended audience

The intended audience for this mini book is potential authors who are trying to figure out if jupyter-book will meet their needs. If you think the [example jupyter-books](https://executablebooks.org/en/latest/gallery.html) are beautiful, but are unsure if the tooling will fit with your writing style, then this mini-book is for you. If this mini-book convinces you to 'buy into' jupyter-book, then you can read the [official documentation](https://jupyterbook.org) to *actually* learn how to use the tool. What you see here is a very brief and superficial description of a very powerful tool.

Once [setup](setup), jupyter-book hides all of the *ugly* business of creating a book using more than a dozen separate tools from the user, but be warned that you will need some level of comfort with command line tools and python to truly appreciate the magic that is jupyter-book.

(exec-book)=
## Executable books

This mini book skips over many of the useful and powerful features of jupyter-book because we are just kicking the tires. The importance of what an executable book is, and why you might want to write one, however can not be glossed over. An executable book is a set of files that are compiled into a book very much like a computer program. Jupyter-book is not a what you see is what you get (WYSIWYG) editor like a typical word processor. The panels below compare the process of authoring a website and/or dead tree book on a technical topic with both tools. If your authoring the next great fictional novel - which is all prose - stop right now and get busy writing in a word processor. If you are authoring a technical document with figures, equations, tables, and code, keep reading because there is a good chance jupyter-book will be a good fit.

```{panels}
Word Processor
^^^
**Content Creation:**

1. Start with a template 
1. Type your content into the word processor
1. Copy figures and graphs as images into the document
1. Use some simple tricks to number your equations 
1. Use a 3rd party add on to integrate your bibliography
1. Inserted an auto-generated table of contents

**Revisions:**

1. Identify an area of the document for improvement
1. Re-run your analysis in your tool of choice (R, SAS, Matlab, etc.), and generate new figures/tables/results
1. Manually update the document and carefully spot every location where a change in the analysis changes the content

**Peer review:**
1. If your lucky, integrate changes from numerous documents named things like 'chapter_3_final_rev_3_011621_rdl_edits_jkl_comments_02-13-21.docx', changes may or may not be tracked. Suggested changes may or may not be compatible with a coherent dialog.
1. If your unlucky use notes with clues like "On the third paragraph of chapter 5 'XYZ' is incorrect" to identify areas for improvement. 
1. If your really unlucky, squint at a printed, then marked up with a red pen, then scanned, copy of your document 
1. Re-run your analysis in your tool of choice, and generate new figures/tables/results
1. Manually update the document and carefully spot every location where a change in the analysis changes the content
1. It is likely that you will have to restructure the document to account for changes that are not trivial - fight with the template as you do this

**Final editing:**
1. Pour over your document for the umpteenith time late at night trying find inconsistencies and errors introduced by weeks/months of updates and changes to the content that were all made manually.
1. Generate a PDF of your final document

**Website development:**

(usually this step is not included in a word processed book, but here is what you would do if you *really* wanted a website for your book)

Option 1 - become a web developer:

1. Learn HTML/javascript/CSS. Modern web development is not geared towards authoring a website for a book, so picking up a popular tool - like react or angular - would involve learning copious amounts of unnecessary skills that only a professional web developer needs
1. Build your own website from scratch, copy and paste in your content, painfully customize the look of your site manually, as a non-expert your result will probably not be considered a 'beautiful, best in class' site.
1. Implementing features like search and a custom navigation bar will probably be beyond your skill level
1. Pay to get a domain name and host your site on the internet

Option 2 - accept a inferior result:
1. Generate an html document from your word processor
1. Accept the plain, default output. The visual aesthetics will look unprofessional, but you probably don't have the budget to hire a web developer
1. Pay to get a domain name and host your site on the internet

**Publish your book**

Option 1 - Self publish:

1. Send your PDF to a print on demand service like [kindle direct publishing](https://kdp.amazon.com/en_US/help/topic/G202059560) to be converted into a book and sold in an online store. Professional book publishers do not use common word processors for final formatting, so your book might look amateurish unless you used a really good template.
1. If you spot an error, go back and revise the document, and then the website manually. Then resubmit your PDF to the print on demand service.

Option 2 - Self fund an initial production run:
1. Send your PDF to a company that for a fee will print a couple boxes of books for you. Store these boxes in your living room and wait to see if your book becomes a best seller. Typically this costs at least $10,000.
1. If you spot an error after printing, there is nothing you can do short of paying to reprint everything.

Option 3 - Get a publishing deal
1. If you are skilled enough to get a publishing deal then you have a paid team helping you write and format the book. Still, jupyter-book might be a good way to impress your team by submitting your chapters on time with minimal errors.

---

Executable book
^^^
**Install jupyter-book:**
1. Unlike a word processor that comes pre-installed on most computers, jupyter-book must be installed. I like to believe that the instructions found on the [setup](setup) page are sufficiently gentle for a technically savvy, but non-software-developer, to follow. However it took me a couple tries to find a workable method to install jupyter-book, and there is no help line when using free software. 

**Learn the tools:**
1. Jupyter-book uses a simple and straight forward syntax, but it still requires learning something new. This mini-book attempts to introduce a [minimum subset](content) of the syntax that everyone needs to get started, but referencing the [official jupyter-book documentation](https://jupyterbook.org/content/citations.html#references-and-citations) will need to be a common occurrence. You will need at least a superficial understanding of:
    - [Linux and the command line](wsl)
    - [Python](python)
    - [Jupyter notebook](notebooks)
    - [Markdown](mark-vs-myst)
    - [Markedly Structured Text (MyST) ](mark-vs-myst)
    - [Git](git) version control (e.g. [GitHub](https://github.com/))

**Create content:**
1. Choose a template - like this mini book!
1. Write your content in markdown files and jupyter notebooks
1. Figures/tables/equations/bibliographies/refernces are all supported as first class citizens, but you must explicitly link them in your text. This will significantly slow down your writing.
1. Every time you want to see the final form of your book compile the book and wait about ~30 seconds to see the result. This will significantly slow down writing in the beginning until you are proficient with the syntax.

**Revisions:**

1. Identify an area of the document for improvement
1. Re-run your analysis in a jupyter notebook, and generate new figures/tables/results
1. Updates automatically propagate into your text

**Peer review:**
1. For your technically savvy colleagues, send them the URL of your github repository for your book and ask them to make a pull request
1. For your colleagues that are 'old school', enable the [hypothesis web service](https://jupyterbook.org/interactive/comments/hypothesis.html), and then send them the URL of your book website and ask them to directly annotate the document 
1. For your colleagues that are 'old curmudgeons' send them a print out of your book and a red pen
1. To incorporate feedback make changes and re-run your analysis in a jupyter notebook, generate new figures/tables/results that propagate automatically into the text
1. It is likely that you will have to restructure the document to account for changes that are not trivial - these changes proceed like normal writing because the formatting is applied automatically. Feel free to completely change the table of contents with no manual reformatting. 

**Final editing:**
1. Pour over your document for the umpteenith time late at night trying to improve the *content*. Rest assured that all your figures, references, and formatting are correct because they are auto-generated
1. With a simple command generate a website and publication ready PDF

**Website development:**
1. This is automated for you if you follow the instructions on the [setup](setup) page. By default the website is beautiful, professional, and includes many bells and whistles like search and navigation. The website looks as expected on both desktops and cell phones in any browser.

**Publish your book**

Option 1 - Self publish:

1. Send your PDF to a print on demand service like [kindle direct publishing](https://kdp.amazon.com/en_US/help/topic/G202059560) to be converted into a book and sold in an online store. Jupyter-book uses profesional grade tools to create your book PDF, so you can expect your book to be indistinguishable from a professionally produced book. If you spot an error, go back and revise your source files. The website can be updated automatically. Then resubmit your PDF to the print on demand service.

Option 2 - Self fund an initial production run:
1. This option is less likely in this use case because you are giving your book away for free on the website to generate publicity, but you can use your production ready PDF here as well.
1. If you spot an error after printing, there is nothing you can do.

Option 3 - Get a publishing deal
1. Giving away your book for free on a website flies against the business model of most publishers. Then again, very few people have the skills to get a publishing deal for their first book.
```

The process of writing a book with a word processor and jupyter-book are vastly different as chronicled above. Each option has parts of the process that are fast, and other parts that are slow. Ultimately if using jupyter-book is the correct choice for you comes down to your use case. 

- Using a word processor is fast initially and then revisions and changes later on become slow and painful. Quality assurance is difficult with a word processor. Figures, equations, tables, and numerical text results (e.g. mean of 34.2 (95% CI 29.2/37.8)) are all updated manually. Creating a book website manually is very challenging. 
- Jupyter-book requires a very significant investment upfront, and even after mastering the long list of tools writing is slower. However revisions and publishing can be made very rapidly. Collaboration is pleasant and streamlined. If you value the book website, jupyter-book generates a truly beautiful and best in class html output. The PDF output is also very professional. You can be assured that every reference and figure is correct and up to date. Jupyter-book will give you a warning if any of the references are missing.

I believe that jupyter-book is clearly the right tool for you if:

- You are authoring long and complex technical documents
- Have high standards for the accuracy and quality of your documents
- You already utilize the jupyter ecosystem for scientific computing
- Have a business model that is amendable with the open and reproducible research

There are certainly other use cases for jupyter-book that are more traditional, but in those cases the trade offs between jupyter-book and a word processor or a latex tool set are less dramatic. The skill of your collaborators to use advanced tools is also a major decision point.

## Mini-book overview

This mini-book is an example and template in itself.

- The [setup](setup) page will show you how to install jupyter-book on a windows machine. The installation method in this book is opinionated,  because it aims to show a user how to kick the tires. The [official jupyter-book documentation](https://jupyterbook.org/content/citations.html#references-and-citations) of course has details on other installation methods. Installing jupyter-book alone is not sufficient for success, the setup page also goes into all the other tools that are assumed to be present on your machine.    
- The [build](build) page shows you how to compile and generate both an html and PDF output of the book. This emphasizes the end goal of using jupyter-book, publishing! 
- The [content](content) page introduces a minimal subset of the jupyter-book syntax so you can try your hand at authoring content and get a feel for the jupyter-book workflow. It is critical to understand that authoring content is slower, so that revising and publishing can be faster. Again, only you can determine if this writing model fits your use case. But at least you can quickly kick the tires and decide for yourself.

