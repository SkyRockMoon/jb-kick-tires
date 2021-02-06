(build-pub)=
# Build and publish a book

```{warning}
This book is still being actively developed and this version of should be considered a rough draft. [Follow me on GitHub](https://docs.github.com/en/github/getting-started-with-github/following-people#:~:text=If%20someone%20you%20follow%20stars,Unfollow%20under%20their%20profile%20image.) to receive notifications when updates are made.  
```

If you successfully completed the instructions on the [setup](setup) page then you can build a book. In this section we will look in a little bit closer detail at what actually happened during the build process to ensure that jupyter-book is a start to finish solution for your writing process. When using jupyter-book the writing process is slower than say a word processor, but the overall process that ends in publishing your work is both more modern (with an option for a website) and faster. If you don't like what you see here, then jupyter-book may not be a good fit for your use case. It's better to find that out now rather than later if that is the case.

## Build a book website
When you issue the command `jupyter-book build book` you are compiling your source files. The source files are written in either markdown (`md`) or a jupyter notebook (`ipynb`).  The configuration (`_config.yml`) and table of contents (`_toc.yml`) files determine exactly how your content files are organized and look. The output of the `jupyter-book build book` command is to create a new folder inside the `book` directory named `_build`. There are multiple things inside the `_build` directory, but the bits relevant to this discussion are nested further inside the `html` directory. Specifically `index.html` is the homepage for your book website. See [deploying your website to the internet](gh-actions) for details on how you can host your book website for free. For a few dollars per month you can go legit and register a domain like 'my-awesome-book-website.com' (still available the last time I checked!) and host it in an amazon s3 bucket or a similar service.

## Build a book PDF
Publishing a PDF from a webpage is not hard (e.g. print to PDF). Publishing a *beautiful* PDF is very, very difficult. This is one of the main reasons that the investment of your time to learn jupyter-book is probably well worth the upfront cost. 

To build your PDF: 

```bash
jupyter-book build book --builder pdflatex
```

This uses latex to build your PDF. Learning latex can be a very steep learning curve, but the results can be visually spectacular. I am grateful that jupyter-book handles all the heavy lifting without any configuration for me.

The result in the console should look something like:

```md
===============================================================================

A PDF of your book can be found at:
    /mnt/c/projects/sample-book/book/_build/latex


===============================================================================
```

If you open the `book.pdf` file inside the directory listed in your console then you should see the PDF version of your book. 

## Conclusion
It was short and sweet, but this chapter demonstrated that you could complete the publishing workflow from start to finish. This might seem trivial, but it proves that you can actually finish and publish the book! With this out of the way, it is time to focus on where the real work happens - [authoring content](content) - in the next chapter.