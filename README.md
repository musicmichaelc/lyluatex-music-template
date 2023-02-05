# `LaTeX/lyluatex` **text & music** starter template


_Template for projects that combine `LaTeX` and `lilypond` in one document using the `lyluatex` package._

[![Typeset document](https://github.com/musicmichaelc/lyluatex-music-template/actions/workflows/main.yml/badge.svg)](https://github.com/musicmichaelc/lyluatex-music-template/actions/workflows/main.yml)

## Github workflow pre-configured

Pushing new commits to a repository created from this starter template will trigger a workflow which produces pdf-files as artifacts.

## `latexmk` pre-configured for local builds

Simply run the command `latexmk` in the root folder of this repository to build locally. If you change the name of `document.tex`, modify `.latexmkrc` accordingly, e.g. if the file to be compiled is `main-project.tex`, then change the corresponding line to:

```bash
@default_files = ('main-project.tex');
```

## Usage

_For more detailed information about using `lyluatex`, consult the [readme file](https://github.com/jperon/lyluatex#usage) in the [lyluatex repo](https://github.com/jperon/lyluatex). The following is a little summary:_

### Including lilypond `.ly` files

```TeX
\lilypondfile[staffsize=17]{PATH/TO/THE/FILE}
```

The optional argument `staffsize` changes the size of the score.
You can change the size for all subsequent scores in a document by
placing the following command before your first include statement:

```TeX
\setluaoption{ly}{staffsize}{24}
```

### Including short snippets directly 

#### 1. With the `lilypond` environment


```TeX
\begin{lilypond}
\relative c' { c d e f g a b c }
\end{lilypond}
```

#### 2. Inlining very short snippets with `\lily`

One can use `\lily` or `\lilypond`&mdash;both seem to have the same effect:

```TeX
Some text here... Lorem ipsum etc. and the motive 
that reads \lily[staffsize=12]{c' d' g'} returns 
again in the recapitulation in a new form, etc. 
etc. lorem ipsum.
```

**Important:** The `\lily` command *does not* support blocks of LilyPond
code with explicit `\score` blocks.  Such code must be included with the
`lilypond` environment or as a separate file.

## Legal

This starter template is licensed under the BSD Zero Clause License (0BSD). However, the software being used therein, such as `lilypond`, `lyluatex`, etc. themselves are licensed under their respective licenses, e.g. the `lyluatex` package is licensed under the MIT license, whereas `lilypond` is licensed under GPL.