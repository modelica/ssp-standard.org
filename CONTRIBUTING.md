# Contributing to the ssp-standard.org website

Please take a moment to review this document in order to make the contribution process easy and effective for everyone involved.
Following these guidelines helps to communicate that you respect the time of the developers managing and developing this open source project.
In return, they should reciprocate that respect in addressing your issue or assessing patches and features.

## Feature requests

Feature requests are welcome. But take a moment to find out whether your idea fits with the scope and aims of the project.
It's up to *you* to make a strong case to convince the project's developers of the merits of this feature.
Please provide as much detail and context as possible.

## Pull requests

Good pull requests - patches, improvements, new features - are a fantastic help.
They should remain focused in scope and avoid containing unrelated commits.

If you only want to make small changes you can [edit files](https://help.github.com/articles/editing-files-in-your-repository/) and [open pull requests](https://help.github.com/articles/creating-a-pull-request) directly from your browser.
Please chose an expressive name for your branch like `add-my-news-post` (not ~~`patch-x`~~).

If you plan bigger changes you can [fork](https://guides.github.com/activities/forking/) and [clone](https://help.github.com/articles/cloning-a-repository/) the repository to your local machine.

*Please ask first* before embarking on any significant pull request (e.g. implementing features, refactoring code, porting to a different language),
otherwise you risk spending a lot of time working on something that the project's developers might not want to merge into the project.

## Commit messages

Please follow [the seven rules of a great Git commit message](https://chris.beams.io/posts/git-commit/) when committing your changes:

- Separate subject from body with a blank line
- Limit the subject line to 50 characters
- Capitalize the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line
- Wrap the body at 72 characters
- Use the body to explain what and why vs. how

For example:

```
Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If the commit it related to an issue, put references to them at the
bottom, like this:

Resolves: #123
See also: #456, #789
```

## Updating the tools list

The tools page [tools page](https://ssp-standard.org/tools/) is generated from the HTML file [tools.html](content/tools.html) in this repository. The page uses a simple HTML table: to add, edit or remove an entry update the corresponding <tbody> <tr> row in [tools.html](content/tools.html) and create a pull request.

Follow these rules when editing the table rows:

- Keep one tool per `<tr>` (table row) with six `<td>` columns in the same order as the existing file: **Name**, **Vendor**, **Description**, **License**, **Import**, **Export**.
- Do not include HTML markup inside the **Description** cell other than plain text; links for the **Name** or **Vendor** (using `<a href="...">`) are allowed.
- Keep descriptions short.
- For **License** use concise values like `commercial`, `free`, or `osi`.
- For **Import** and **Export** list supported SSP versions or `no` when not supported (examples: `1.0`, `2.0`, `1.0/2.0`, `no`).

Example row (HTML fragment):

```html
<tr>
  <td><a href="https://example.com/example-sim">Example Sim</a></td>
  <td><a href="https://example.com/">Example Company</a></td>
  <td>A short neutral one-line description without trailing dot</td>
  <td>commercial</td>
  <td>1.0/2.0</td>
  <td>1.0/2.0</td>
</tr>
```

## Adding a news post

To create a post, add a file to `/content/news/` with the following format:

```
YEAR-MONTH-DAY-title.MARKUP
```

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. The date determines the placement in the news chronology and must not be in the future in order to be listed. `title` should not be longer than 50 characters and only contain lower case characters (`a-z`), digits (`0-9`) and hyphens (`-`).

The file name determines the [permalink](https://en.wikipedia.org/wiki/Permalink) to the post and must not be changed after it has been merged into `main`.
E.g. the post

```
2025-08-29-SSP-LS-Traceability-v1.0.0.md
```

can be accessed as

```
https://ssp-standard.org/news/2025-08-29-ssp-ls-traceability-v1.0.0/
```

You typically write posts in [Markdown](https://daringfireball.net/projects/markdown/) (`.md`), however HTML (`.html`) is also supported.

All blog post files must begin with a front matter that sets the title and date:

```markdown
---
title: SSP Layered Standard Traceability (SSP-LS-Traceability) v1.0.0 released
date: 2025-08-29
---

# SSP Layered Standard for Traceability (SSP-LS-Traceability) v1.0.0 released

The SSP Project is happy to announce the release of the first layered standard on top of the SSP Standard developed by the SSP Project.

The [System Structure & Parameterization (SSP) standard](https://ssp-standard.org/) has established itself as a format for the exchange of composite system simulation models and simulation model architectures.

...
```

To include images, downloads or other files along with a post place them in the `static` directory and reference them using the following markdown syntax:

```markdown
... which is shown in the screenshot below:
![My helpful screenshot](/static/images/screenshot.jpg)
```

Linking to a PDF for readers to download:

```markdown
... you can [get the PDF](/static/publications/mydoc.pdf) directly.
```

## Serve the website locally

1. [Install Hugo extended version](https://gohugo.io/getting-started/installing/)
2. [Add a SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
3. Clone the repo `git clone --recurse-submodules git@github.com:modelica/ssp-standard.org.git`
4. Change into the repository folder `cd ssp-standard.org`
5. Run `hugo serve` and browse to [http://localhost:1313](http://localhost:1313/)