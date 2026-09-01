# Jornada Data Commons: Training (jeds)

This is the repository for the Jornada Data Commons: Training site (formerly JEDS). These pages contain educational materials for hands-on environmental data science learning at the [Jornada Basin LTER (JRN)](https://lter.jornada.nmsu.edu) and [Jornada Experimental Range (JER)](https://jornada.nmsu.edu) programs. Our aim is to teach environmental data science concepts and skills to Jornada researchers using accessible methods and relatable data. 

The website is created using the [Quarto](https://quarto.org) documentation publishing system and served by [GitHub Pages](https://docs.github.com/en/pages). The `main` branch of this repository contains all source files for the web pages, which Quarto renders into HTML files that are served from the `gh-pages` branch. These HTML files are what you see when you visit [the site](https://jornada-im.github.io) with your web browser. Source files are written in the Quarto variant of [Markdown](https://www.markdownguide.org/getting-started/) - a simple, plain-text markup language. The website and the documentation it contains are intended as a community-supported resource, and if you are so-inclined we welcome your contributions. For more on this, see "Contributing" below.

## Site and repository layout

 The [Jornada Data Commons: Training](https://jornada-im.github.io/jeds) site has a landing page, collections of lessons and presentations for data users, a listing of workshops, and a few other standalone pages. The Quarto build system also provides a top menu bar, side navigation, and search indexing to tie the website together and make pages discoverable. Content for all web pages is created in source files written in Quarto-flavored markdown stored throughout the repository file system. These files have the `.qmd` file extension. This repository is structured as shown below:

```
jeds/
|-- data/                       # A few data files needed for the lessons
|-- docs/                       # Documentation files
|  |-- lessons/                 #   Hands-on lessons
|  `-- slides/                  #   Presentations (usually reveal.js)
|-- img/                        # Images for embedding in documents
|-- workshops/                  # Workshop-specific pages
|-- index.qmd                   # The website landing page
|-- _quarto.yml                 # Quarto structure
`-- README.md                   # This file
```

The `index.qmd` file is the source for the HTML index, or landing page, of the website. The `_quarto.yml` file is a YAML file that defines how the website is structured, the navigation system, and the rendering options that Quarto uses to build the HTML and other files. The lessons (`docs/lessons/`) and presentation (`docs/slides/`) directories contain source files for the rendered training content.

## Related materials

* The Jornada Data Commons, rendered from [this repository](https://github.com/jornada-im/jornada-im.github.io), is the parent site for this training site.

## Contributing

Jornada researchers, staff, and data managers are welcome to contribute to this documentation. Contributions could include fixing typos and errors, suggesting new and improved text, or just pointing out documentation that should exist but doesn't. There are a few ways you can do this:

1. The easiest method is to file an issue in [this repository](https://github.com/jornada-im/jeds). Go to the [Issues tab](https://github.com/jornada-im/jeds/issues) at the top of the repository page and then select **New issue**. Provide a thorough description of your issue and suggested changes. You can even put suggested text into your issue. Once you submit it, the IM team will review and make changes.
2. Use the "fork and pull request" method by forking this repository to your own GitHub profile using the **Fork** button at the top right of the page. Then make your changes and submit a pull request from your fork. Someone on the IM team will review and merge them in. You can read more about GitHub [forks](https://docs.github.com/articles/fork-a-repo) and [pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) in the GitHub documentation.
3. If you would like to contribute directly to this repository without using the fork and pull request method, request to join the Jornada IM team on GitHub so that you can contribute changes directly. We still recommend creating a branch first, instead of committing directly to `main`.

Note that for contribution methods 2 and 3, you can make changes directly in the GitHub web interface using the **Edit** button at the top right of any page (it has a pencil icon on it), or you can clone the repository locally, make changes using your favorite editor, and push them back to GitHub. 

### Markdown

When you create new documentation you should use [Markdown](https://www.markdownguide.org/getting-started/) to write the text. Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes many text formatting and styling conventions for publishing documents.

```markdown
This is a Markdown syntax-highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

The [Quarto](https://quarto.org) publishing system we use has its own additions to standard Markdown and there is quite a bit you can do with the Quarto Markdown variant. Consult the [Quarto authoring guide](https://quarto.org/docs/guide/) for more on writing documentation pages.

## Building and deployment

Whenever a new Git commit is pushed to the `main` branch of this repository, a GitHub Action (see it in `.github/workflows/publish.yml`) will run to render and rebuild the website with any new content changes in the source files. This action takes all content in the `main` branch and uses Quarto to render HTML and other files, then commits the result to the `gh-pages` branch. It is these files that are served to visitors at <https://jornada-im.github.io/jeds>. 

There are a couple things to take note of in this setup. The GitHub action must load R and any dependencies to produce the code-heavy tutorials, so **make sure any R package dependencies are met in the action file**. There is also an authentication key for EDI used in some of the files ("EDI_API_KEY"). **This must be present as a GitHub secret for the repository**.

## Contact us

If you have questions or concerns about the website or its content, or you'd like to know more about contributing, please contact the Jornada IM team at <jornada.data@nmsu.edu>.