# Platform UI ADR Spike

This is a repository set up to demonstrate three alternate methods for
keeping Architecture Decision Records (ADRs) to help aid a discussion about the
method we should adopt as a team.

# Why?

ADRs help newcomers to a project understand the rationale behind past decisions.
Without this understanding they may either:
* blindly accept the decision or
* blindly change it.

If a development team blindly accepts too many decisions, it 'becomes too 
afraid to change anything and the project collapses under its own weight' (Nygard, 2011)
On the other hand, blinding changing decisions may result in damage or inadvertent introduction
of technical debt.

By recording architecturally significant decisions, development teams have an opportunity to
revisit past decisions and decide whether the rationale behind them still makes sense, 
change course safely and appropriately, while keeping the project lean and conceptually 
coherent.

# What?

An Architectural Decision Record (ADR) records a decision that is 
[architecturally significant](https://docs.arc42.org/tips/9-1/). The collection of these within a given project 
constitutes its decision log.

All the templates described below are lightweight. Some are more lightweight than others. The
Nygard format omits certain fields, for example considered options, that are considered essential by others.

## Nygard's ADRs

The original version of ADRs are the lightest weight of the three methods. They have only five
fields: Title, Context, Decision, Status and Consequences. They use markdown and are numbered
sequentially and monotonically. They were first introduced in this [blog article](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions.html)
which is also an ADR.

### Pros

* Simple, fewest fields
* Rich tooling via adr-tools supporting auto-numbering and naming, 
creation of the template, marking as superseded or amended, 
producing a graph and ToC

### Cons

* No 'because' field
* No 'alternatives' field
* No 'neglected options' field

### How to create

1. To install adr

    ```
    brew install adr-tools
    ```

1. To initialise the repository

    ```
    adr init doc/decisions/adr
    ```

1. To add a new ADR

    ```
    adr new Record architecture decisions
    ```
   
1. To generate a table of contents

    ```
    adr generate toc > doc/decisions/adr/index.md
    ```

### Examples

See [here](doc/decisions/adr/index.md)

## MADR

[Markdown Architectural Decision Records](https://adr.github.io/madr/) are a refinement of Nygard's ADRs. They
also use markdown and have a similar file format. They
contain a few more fields including 'considered options' which is required.

### Pros

* MADR project is well-presented and documented
* MADR template is flexible and readable
* Some tooling is available

### Cons

* Tooling not as advanced as available for Nygard ADRs
* ADRs could get big if all the optional fields are used

### How to create

1. To create a new ADR, copy template.md as NNNN-title-of-decision.md, and fill
in the fields.

1. To install adr-log

    ```shell script
    npm install -g adr-log
    ```

1. To generate a table of contents

    ```shell script
    $(cd docs/adr && adr-log -i)
    ```

### Examples

See [here](doc/decisions/madr/index.md)

## Y-Statements

Y-statements were first proposed by [DoC SoC](https://medium.com/@docsoc) in 2012, inspired by 
George Fairbanks' [Architecture Haikus](https://www.georgefairbanks.com/blog/comparch-wicsa-2011-panel-discussion-and-haiku-tutorial/)

They are single sentences with the following elements: in the context of, facing, we decided for, and neglected, to
achieve, accepting downside and (optionally) because.

### Pros

* Simplicity

### Cons

* No tooling
* Potentially hard to read unless structured and formatted with markdown
* Not opinionated on storage or file naming, but could use
the MADR/Nygard convention

### How to create

1. To create a new ADR, copy template.md as NNNN-title-of-decision.md, and fill
in the fields.

### Examples

See [here](doc/decisions/y-statements/0001-use-y-statements-for-recording-decisions.md)

## Questions

* Where should decisions be recorded?
* Do we agree that decisions be kept close to the code if possible?
* Should we keep a separate log for each product/service or one for Plat-UI to cope with changes of ownership? 
* Which template should we use?
* Might we use Jenkins to auto-generate the index?
* Could Slackbot potentially help reduce the friction for creating ADRs?

## References

* ADR github organisation: https://adr.github.io/
* MADR: https://adr.github.io/madr/
* adr-log for MADR ADRs: https://github.com/adr/adr-log
* Nygard ADRs: https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions.html
* Nygard ADR tools: https://github.com/npryce/adr-tools
* Nygard ADR tools article: https://www.hascode.com/2018/05/managing-architecture-decision-records-with-adr-tools/
* Y-Statements: https://medium.com/olzzio/y-statements-10eb07b5a177
* Comparison of ADR templates: https://www.ozimmer.ch/practices/2020/04/27/ArchitectureDecisionMaking.html
* Recording architecturally significant decisions: https://docs.arc42.org/tips/9-1/
