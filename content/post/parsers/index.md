---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "How to write parsers fast"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-15T18:01:03-05:00
lastmod: 2021-09-15T18:01:03-05:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

I had a fun time writing the openQASM parser over two years ago during my two week visit at UMD College Park. Since then, I have been quite fascinated with parsers. Today, I was trying to write a parser for Lambda Q#, but I wanted to figure out if I could reduce the work I need to do and avoid boilerplate.

I found a few projects that seem helpful:
- Steffen Smolka's [Nice Parser](https://github.com/smolkaj/nice-parser) that is meant exactly for this need.
- Lélio Brun's [Obelisk](https://github.com/Lelio-Brun/Obelisk), which I may end up using to generate good documentation for the grammar.

Further, since LambdaQs is based on the Modernized Algol (MA) language of Bob Harper, I somehow also stumbled upon a bunch of projects by Jon Sterling, specifically:
- [sml-modernized-algol](https://github.com/jonsterling/sml-modernized-algol), which seems like an ABT representation of PFPL. Someone also ended up contributing [a parser for the surface syntax later](https://github.com/jonsterling/sml-modernized-algol/pull/4).
- [sml-typed-abts](https://github.com/RedPRL/sml-typed-abts), an implementation of Abstract Binding Trees (ABTs). Jon seems to have [an OCaml port](https://github.com/jonsterling/ocaml-abt) too, but it seems unmaintained with a single commit.

The latter two projects will be helpful for me to translate Q# source syntax directly into PFPL-style ABTs.

---

Turns out what I am really looking for is [BNF Converter](http://bnfc.digitalgrammars.com/).
