# Atomicity with change-sets and topic submission

In our software development environment, with source code spread across hundreds of source
code repositories,  related  changes created in a same source code repository and  or across
multiple source code repositories need to be reviewed, approved, tested  and committed together.
Developers creating changes across multiple repositories need ability to group the changes
together as a unit. The grouping of changes should be intact across all re-write operations
in GIT like commit amend and rebase.  Developers need the flexibility to group the related
changes implicitly or explicitly. Developers need the ability to work on multiple related
change-sets simultaneously in the same sandbox. While developers need ability to group the
changes flexibly, the system needs the ability to detect the dependencies between the
change-sets created in the same sandbox .

Come and find out how we use topic submission feature of Gerrit along with wrapper scripts,
hooks and plugin to provide atomicity for changes throughout lifecycle of related changes.

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/changesets.pdf)

*Basavaraj Kradakal, Juniper Networks*
