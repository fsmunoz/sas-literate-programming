# Literate Programming with SAS

An overview of the different solutions available for using [Literate
Programming](https://www-cs-faculty.stanford.edu/~knuth/lp.html) with
[SAS](https://www.sas.com/)

By _Literate Programming_ we mean the original definition by Knuth,
and take it in it's broadest way:

> Literate programming is a methodology that combines a programming
> language with a documentation language, thereby making programs more
> robust, more portable, more easily maintained, and arguably more fun
> to write than programs that are written only in a high-level
> language.

This includes different use-cases which are nonetheless closely
related:

* Mixing text formats (LaTeX, Markdown, AsciiDoc...) with code blocks
  (specifically, SAS) in a single document that get's rendered to one
  or more target formats.
* Using text-based formats for presentations (e.g. revealjs), that can
  be used for sharing in a conference.
* Creating client-facing deliverables from text-based source (e.g.,
  Markdown).
* Using text formats to build a web portal.

These examples cater to different needs, from academic publishing
focused on reproducibility to technical documentation writers, but
since they share a common root, the set of tools that are neede will
largely overlap.

## Existing solutions

More often than not, a specific approach will include one or more
existing tools. Our goal is to further describe each one of them in
terms of currency, usage, and how they can be combined.

* [StatRep](https://support.sas.com/rnd/app/papers/statrep.html).The
  StatRep system uses SAS and the LaTeX typesetting system to create
  documents with reproducible results. It consists of a LaTeX package,
  a suite of SAS macros and a user guide. It's a LaTeX only approach
  that does not require additional pre-processors (the only dependency
  is SAS itself, plus LaTeX).

* [SASweave](https://homepage.divms.uiowa.edu/~rlenth/SASweave/). SASweave,
  patterned after Sweave (Leisch, 2002), is a way to easily and
  reliably prepare documents containing SAS code, output, and
  graphics. It works in a similar way to other Sweave/Knitr based
  approaches, with a source file that is transformed into a "regular"
  LaTeX file, which is then converted to whichever target format
  desired (typically, PDF).

* [SASpy](https://github.com/sassoftware/saspy). This package provides
  interfaces between Python and SAS. Not only is it used by other
  solutions (e.g., the SAS Jupyter kernel), by itself it also opens
  the door for using existing literate programming approaches from the
  Python/R ecosystems (cf. [SASpy with
  Rmarkdown](https://github.com/sassoftware/saspy-examples/blob/main/User_contrib/SASpy_with_R_markdown.Rmd)

* [SASmarkdown](https://users.ssc.wisc.edu/~hemken/SASworkshops/Markdown/index.html). This
  R package extends the (limited) built-in SAS engine in `knitr` with
  additional ODS outputs, log output, and more. This allows writing a
  document in `.Rmd` but using SAS as the engine.

* [Quarto](https://quarto.org/): Quarto is an open-source scientific
  and technical publishing system that uses Jupyter or `knitr` with
  `pandoc`markdown to provide support for different programming
  engines and output formats. Explicitly supported are Python, R,
  Julia, and OJS, but [SAS is also a possibility using the Jupyter SAS
  kernel](https://github.com/quarto-dev/quarto-cli/discussions/8541).

* [ESS: Emacs Speaks Statistics](https://ess.r-project.org/): has
  support for R, S, and SAS, and with `polymode` provides support for
  literate programming by doing syntax checking and highlighting
  inside and outside of code chunks, plus evaluating SAS code.

* [SAS Visual Studio Code
  extension](https://github.com/sassoftware/vscode-sas-extension). Provides
  support for SAS programming in Visual Studio Code, including a LSP
  server for the SAS language. Since there are also other modes that
  support `vscode` (e.g. markdown mode, quarto mode), it provides a
  full-featured environment that is officially supported by SAS.
