# DIQKD Thesis

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/wikiti/pandoc-book-template/blob/master/LICENSE.md)
https://www.overleaf.com/project/6225e87cfde1be655696e8f4


# Introduction
The objective of this project is to build a Quantum Computing simulator in Maxima with the following characteristics:



1. OpQSDS programming language development.

  1. Ability to generate general quantum circuits by specifying parameters, for example the number of qubits, a natural number, the size of a set, etc.

  Ability to integrate data into the quantum gates of the circuit (wire the data), with the aim of reducing the number of required qubits.

  Use of general quantum gates (generalized Toffoli, etc) to facilitate algorithm coding.

  Automatic optimization of quantum circuits.

  Simulation of errors during the execution of quantum algorithms.

  Visualization of the quantum state at intermediate points in the execution of algorithms.

  Use of classical calculations, for example for conditional management, during quantum computing in order to reduce the number of required qubits.

  The simulator will be integrated into Maxima as a library for use as free software.



2. Code generation for Qiskit and OpenQASM.

5. Implementation in OpenQSDS of error-correcting quantum codes.

4. Simulation in OpenQSDS of qubit errors.

5. Implementation in OpenQSDS of QKD protocols.

6. Design of quantum codes that correct errors in two qubits.






# \input{chapters/introduction}
# \input{chapters/methods}
# \input{chapters/results}


resents observations in a logical and coherent
manner; use illustrations, graphs, tables to
document


Provide a description of your observations
• Organize in a logical way and introduce briefly what the
section/paragraph is about
• Describe and illustrate main observations; additional details
can go into appendices/suppl. Material
• Qualitative or quantitative
• Statistical analysis
• Graphical representations
• Do not interpret/discuss data unless absolutely necessary for a
logical flow of thought (but check with your supervisor about
preferences/customs in the lab).

Do not repeat methods in results!
Write results as results; what is the parameter you observe


Example: better
In order to visualize the development of connectivity in the developing brain,
all tracing methods had to be developed, aiming to determine optimal
injection and survival parameters as well as establishing surgical procedures
and stereotaxic coordinates. Relevant for this study is that we ascertained
that successful tracing with anterograde and retrograde tracing is feasible in
pups, starting at postnatal day 0 (P0) and that a survival time between 20-24
hours yields sufficient transport of injected tracers to label all central
projections, i.e. those restricted to the fore- and midbrain. This is illustrated
when comparing the pattern of labeling seen following a retrograde injection
in area X at Px with a survival period of 20 hours with that of an animal
injected with the same tracer, in the same area but now with a survival time
of 24 or 48 hours. From this we concluded that using a survival time
between 20- 24 hours is sufficient to provide a reliable overview of
established connections.


# \input{chapters/conclusions}
# \input{chapters/perspectives}


## Description

This repository contains a simple template for building [Pandoc](http://pandoc.org/) documents;
Pandoc is a suite of tools to compile markdown files into readable files (PDF, EPUB, HTML...).

## Usage

### Installing

Please, check [this page](http://pandoc.org/installing.html) for more information. On ubuntu, it
can be installed as the *pandoc* package:

```sh
sudo apt-get install pandoc
```

This template uses [make](https://www.gnu.org/software/make/) to build the output files, so don't
forget to install it too:

```sh
sudo apt-get install make
```

To export to PDF files, make sure to install the following packages:

```sh
sudo apt-get install texlive-fonts-recommended texlive-xetex
```

### Folder structure

Here's a folder structure for a Pandoc book:

```
my-book/         # Root directory.
|- build/        # Folder used to store builded (output) files.
|- chapters/     # Markdowns files; one for each chapter.
|- images/       # Images folder.
|  |- cover.png  # Cover page for epub.
|- metadata.yml  # Metadata content (title, author...).
|- Makefile      # Makefile used for building our books.
```

### Setup generic data

Edit the *metadata.yml* file to set configuration data (note that it must start and end with `---`):

```yml
---
title: My book title
author: Alessandro Cucci
rights:  MIT License
language: it-IT
tags: [book, my-book, etc]
abstract: |
  Your summary text.
mainfont: DejaVu Sans
---
```

You can find the list of all available keys on
[this page](http://pandoc.org/MANUAL.html#extension-yaml_metadata_block).

### Creating chapters

Creating a new chapter is as simple as creating a new markdown file in the *chapters/* folder;
you'll end up with something like this:

```
chapters/01-introduction.md
chapters/02-installation.md
chapters/03-usage.md
chapters/04-references.md
```

Pandoc and Make will join them automatically ordered by name; that's why the numeric prefixes are
being used.

All you need to specify for each chapter at least one title:

```md
# Introduction

This is the first paragraph of the introduction chapter.

## First

This is the first subsection.

## Second

This is the second subsection.
```

Each title (*#*) will represent a chapter, while each subtitle (*##*) will represent a chapter's
section. You can use as many levels of sections as markdown supports.

#### Manual control over page ordering

You may prefer to have manual control over page ordering instead of using numeric prefixes.

To do so, replace `CHAPTERS = chapters/*.md` in the Makefile with your own order. For example:

```
CHAPTERS += $(addprefix ./chapters/,\
 01-introduction.md\
 02-installation.md\
 03-usage.md\
 04-references.md\
)
```

#### Links between chapters

Anchor links can be used to link chapters within the book:

```md
// chapters/01-introduction.md
# Introduction

For more information, check the [Usage] chapter.

// chapters/02-installation.md
# Usage

...
```

If you want to rename the reference, use this syntax:

```md
For more information, check [this](#usage) chapter.
```

Anchor names should be downcased, and spaces, colons, semicolons... should be replaced with hyphens.
Instead of `Chapter title: A new era`, you have: `#chapter-title-a-new-era`.

#### Links between sections

It's the same as anchor links:

```md
# Introduction

## First

For more information, check the [Second] section.

## Second

...
```

Or, with al alternative name:

```md
For more information, check [this](#second) section.
```

### Inserting objects

Text. That's cool. What about images and tables?

#### Insert an image

Use Markdown syntax to insert an image with a caption:

```md
![A cool seagull.](images/seagull.png)
```

Pandoc will automatically convert the image into a figure (image + caption).

If you want to resize the image, you may use this syntax, available in Pandoc 1.16:

```md
![A cool seagull.](images/seagull.png){ width=50% height=50% }
```

Also, to reference an image, use LaTeX labels:

```md
Please, admire the gloriousnes of Figure \ref{seagull_image}.

![A cool seagull.\label{seagull_image}](images/seagull.png)
```

#### Insert a table

Use markdown table, and use the `Table: <Your table description>` syntax to add a caption:

```md
| Index | Name |
| ----- | ---- |
| 0     | AAA  |
| 1     | BBB  |
| ...   | ...  |

Table: This is an example table.
```

If you want to reference a table, use LaTeX labels:

```md
Please, check Table /ref{example_table}.

| Index | Name |
| ----- | ---- |
| 0     | AAA  |
| 1     | BBB  |
| ...   | ...  |

Table: This is an example table.\label{example_table}
```

#### Insert an equation

Wrap a LaTeX math equation between `$` delimiters for inline (tiny) formulas:

```md
This, $\mu = \sum_{i=0}^{N} \frac{x_i}{N}$, the mean equation, ...
```

Pandoc will transform them automatically into images using online services.

If you want to center the equation instead of inlining it, use double `$$` delimiters:

```md
$$\mu = \sum_{i=0}^{N} \frac{x_i}{N}$$
```

[Here](https://www.codecogs.com/latex/eqneditor.php)'s an online equation editor.

### Output

This template uses *Makefile* to automatize the building process. Instead of using the *pandoc cli
util*, we're going to use some *make* commands.

#### Export to PDF

Use this command:

```sh
make pdf
```

The generated file will be placed in *build/pdf*.

Please, note that PDF file generation requires some extra dependencies (~ 800 MB):

```sh
sudo apt-get install texlive-xetex ttf-dejavu
```

#### Export to EPUB

Use this command:

```sh
make epub
```

The generated file will be placed in *build/epub*.

#### Export to HTML

Use this command:

```sh
make html
```

The generated file(s) will be placed in *build/html*.

#### Extra configuration

If you want to configure the output, you'll probably have to look the
[Pandoc Manual](http://pandoc.org/MANUAL.html) for further information about pdf (LaTeX) generation,
custom styles, etc.

## References

- [Pandoc](http://pandoc.org/)
- [Pandoc Manual](http://pandoc.org/MANUAL.html)
- [Wikipedia: Markdown](http://wikipedia.org/wiki/Markdown)

## Contributors

This project has been developed by:

| Avatar | Name | Nickname | Email |
| ------ | ---- | -------- | ----- |
| ![](http://www.gravatar.com/avatar/2ae6d81e0605177ba9e17b19f54e6b6c.jpg?s=64)  | Daniel Herzog | Wikiti | [info@danielherzog.es](mailto:info@danielherzog.es)
|   | Alessandro Cucci | alessandrocucci | [alessandro.cucci@gmail.com](mailto:alessandro.cucci@gmail.com)
