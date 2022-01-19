---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Types and Effects"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-08-20T15:43:17-05:00
lastmod: 2021-08-24T09:06:11-05:00

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## Type and Effect Systems
How can we reason about the effects of a program without using monads or uniqueness types?

An effect describes how an expression computes. Denoted by $\varphi$ annotation in the statics of the language.

## Region-Based Memory Management
A region-inference judgment such as
> $TE \vdash e ⇒ e' :(τ, ρ), \varphi$

where $TE$ is a type environment mapping variables with pairs $(\tau, \rho)$ of types and region variables (or _place_) and $\varphi$ is an effect (a finite set of region variables). It is read as:

> in the type environment $TE$, the source expression $e$ is translated into a region-annotated expression $e'$, which has type $τ$, is placed in region $ρ$, and has effect $\varphi$.

$\varphi$ contains the superset of regions needed to evaluate $e$.

One of my misconceptions associated with regions was that they involve allocations only on the heap. But turns out the most common case is to have regions which only ever contain one value, called _finite regions_. A common optimization then is to allocate those on the stack.



## (Partial) History

{{< figure src="pottier-history.png" caption="Partial history circa 2007. Credits: [François Pottier](http://pauillac.inria.fr/~fpottier/slides/fpottier-2007-05-linear-bestiary.pdf#page=5)" >}}


## References
{{< spoiler text="References" >}}
- Mads Tofte, Jean-Pierre Talpin. 1997. Region-Based Memory Management.
- Dan Grossman, Greg Morrisett, Trevor Jim, Michael Hicks, Yanling Wang, and James Cheney. 2002. Region-based memory management in cyclone. PLDI '02. http://www.cs.umd.edu/projects/cyclone/papers/cyclone-regions-tr.pdf
- Philip Wadler and Peter Thiemann. 2003. The marriage of effects and monads. ACM Transactions on Computational Logic. https://homepages.inf.ed.ac.uk/wadler/papers/effectstocl/effectstocl.pdf
- Tofte, M., Birkedal, L., Elsman, M. et al. A Retrospective on Region-Based Memory Management. Higher-Order and Symbolic Computation 17, 245--265 (2004).
- Fritz Henglein, Henning Makholm, and Henning Niss. 2005. Effect Types and Region-Based Memory Management. Ch-3 of Advanced Topics in Types and Programming Languages.
- Nikhil Swamy, Michael Hicks, Greg Morrisett, Dan Grossman, and Trevor Jim. 2006. Safe Manual Memory Management in Cyclone. Science of Computer Programming. Special issue on memory management. http://www.cs.umd.edu/projects/PL/cyclone/scp.pdf
- François Pottier. 2007. Wandering through linear types, capabilities, and
regions. http://pauillac.inria.fr/~fpottier/slides/fpottier-2007-05-linear-bestiary.pdf
- Asumu Takikawa. 2012. Type and Effect Systems. http://www.ccs.neu.edu/home/amal/course/7480-s12/effects-notes.pdf
- El Pin Al. 2019. Incomplete Bibliography of Region-based Memory Management. https://github.com/elpinal/regions#incomplete-bibliography-of-region-based-memory-management
{{< /spoiler >}}
