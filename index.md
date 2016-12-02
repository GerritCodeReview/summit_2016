# Mountain View 2016

[TOC]

## Accounts in NoteDb

NoteDb is our effort to migrate the Gerrit meta data from the database into the
Git repositories. This migration also includes the Gerrit accounts. This talk
will discuss how the accounts will be stored in Git.

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/accounts-in-notedb.pdf)

*Edwin Kempin, Google*

## Atomicity with change-sets and topic submission

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

## Implementing Gerrit build with Bazel

Gerrit build tool chain is an interesting journey with multiple stops:

* Maven
* Buck
* Blaze, opps.. Bazel

[Slides](http://ostrovsky.org/gerrit/bazel-build-gerrit/)

*David Ostrovsky, Unaffiliated*

## Bringing pull requests to Gerrit

With CollabNet TeamForge it is now possible to use feature branch workflow
in addition to standard gerrit workflow to work on your changes.
In this presentation you will learn how it works, why we have decided to
implement it, how was it implemented and what were the choices we have made
and challenges along the way.

[Slides (slideshare)](http://www.slideshare.net/eryksz/bringing-pull-request-to-gerrit)

*Eryk Szymanski, CollabNet*

## Plugins for CI Systems

I will give an overview of 3 new plugins developed by the Qualcomm
Innovation Center for use by CI systems: the batch, manifest, and task
plugins.  I will review what these plugins can do, and how we use them
along with our future plans and ideas for these plugins. I will also
talk about the core modifications that were needed to create these
plugins, and what future core modification I believe may still be
needed, along with some of the challenges of doing more in plugins.

A quick overview of the 3 plugins:

The batch plugin provides a mechanism for building and previewing sets
of proposed updates to multiple projects/branches/refs that should be
applied together. The focus of batch updates tend to be verification (by
CI systems).  The batch update service provides the tools to build refs
by merging changes to temporary “snapshot” refs, which can then be
tested extensively, and finally submitted ”as is".

The manifest plugin provides server side utilities to operate on, and
query information about repo manifests (xml) stored in git projects on
the current server.  This plugin provides APIs to update values in
manifests, and to search for manifests with certain values.

The task plugin provides a mechanism to manage tasks which need to be
performed on changes along with a way to expose and query this
information. Tasks are organized hierarchically, and task definitions
use gerrit queries to define which changes each task applies to, and how
to define the status criteria for each task. An important use case of
the task plugin is to have a common place for CI systems to define which
changes they will operate on, and when they will do so.

*Martin Fick, Qualcomm Innovation Center*

## Email Ingestion

Email ingestion gives users the option to reply to auto-generated email
notifications from Gerrit, have their comments parsed out from the
email and attached to the change. Email ingestion is currently under
development and this session will be about the design, implementation and
usage of the new feature.

*Patrick Hiesel, Google*

## So what's up with the repo tool and submodules?

This talk will present the current situation for submodules in Git,
Gerrits ability to deal with the awesomeness of submodules and how
we keep git-repo around.

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/bye-bye-repo.pdf)

*Stefan Beller, Google*

## Gerrit Analytics

Gerrit Review Analytics Dashboards. 
Collect, analyze and display in Real Time the Gerrit Code Review activity
to create GitHub-style dashboards and archive the review data audit trail
for off-line reporting.

[Slides](http://www.slideshare.net/lucamilanesio/gerrit-code-review-analytics)

*Luca Milanesio, GerritForge*

## Building Gerrit - a CI story

It is one year since the official introduction of a CI build for Gerrit.
Learn how we implemented a fully featured build pipeline for Gerrit and
its plugins, ranging from Maven, Simple Build Tool, Buck and more recently
Bazel-powered build scripts.

*Luca Milanesio, Maintainer of Gerrit-CI*

## Introducing 'zoekt': git aware codesearch

[Zoekt](https://gerrit.googlesource.com/zoekt/) is an open-source, fast
full-text search engine for code, made to work well for Git repositories.

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/zoekt.pdf)

*Han-Wen Nienhuys, Google*

## Infinite Gerrit

Gerrit Review with Apache Cassandra as JGit storage.

Achieve a "virtually infinite" extensibility of the Gerrit repositories by using
a multi-site distributed storage backend based on Apache Cassandra.

Benefits are:

1. Steps towards a real Gerrit peer-to-peer infrastructure
where every server can potentially read and write to any of the Cassandra nodes.
2. Ability to extend the capacity of the existing network of Gerrit servers by
adding additional Cassandra nodes and getting the quorum distribution
out-of-the-box.

[Slides (slideshare)](http://www.slideshare.net/HaithemJarraya/infinite-gerrit)

*Haithem Jarraya, GerritForge*

## Keep the conversation flowing

A typical Gerrit installation contains integration with an automated
testing system that evaluates patchsets and reports results to Gerrit.
The only way for a Continous Integration system to report results
to Gerrit is by posting a review as a comment.  The problem with this
workflow is that automated reviews and human reviews are stored as one
piece of data (comments).  Human reviews are inherently different than
automated reviews.  Human reviews have more meaning to other human
reviewers, it serves as a conversation between people that are
reviewing the change and thus it is typically given higher priority
over automated reviews.  Comments provide a great forum to discuss a
change however when robots clutter the forum it overwhelms human
reviewers and thus impede the discussion.  Robots should have
a separate feedback channel so that the data can be easily queried,
viewed and analyzed independently from human comments.

This is where the verify-status plugin may help. It creates a separate
"verify-status" channel for automated system to report test results.
It provides a set of SSH commands and REST endpoints allowing easy
integration with any CI system.  It allows the verify-status data to be
stored in the Gerrit database or on a completely separate database.
It provides a set of UI components to view the data independent of
Gerrit comments.  Lastly there's even a Jenkins verify-status-reporter
plugin that helps Jenkins report results to gerrit using this new
communications channel.

This talk with go over the motivation behind this plugin, it's status,
how we plan to use it, and how it can help you keep the conversation
flowing.

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/keep-the-conversation-flowing.pdf)

*Khai Do, OpenStack*

## What's New in Gerrit 2.12, 2.13 and 2.14

Overview of the new features included in the latest Gerrit
releases 2.12 and 2.13, and a preview of what's coming in 2.14.

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/whats-new-12-13-14.pdf)

*David Pursehouse, CollabNet*

## An Update on PolyGerrit

PolyGerrit has been under development for more than a year and is rapidly
approaching feature parity with the current GWT UI. This talk will give an
overview of what’s been done, what’s left, and what’s next.

Come hear what we’ve learned from a product development standpoint and how you
can help us further improve the best code review experience out there.

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/polygerrit.pdf)

*Andrew Bonventre, Google*

## Robot Comments

We are extending Gerrit to better support comments generated by automated
systems ("robot comments"). Robot comments will be specifically visualized in
the UI and users will be able to apply filters on them. Robot comments can also
carry generated fixes that users can apply to the change and create a new patch
set.

This talk gives you an introduction to robot comments and how they will be
implemented in Gerrit.

*Edwin Kempin, Google*

[Slides (PDF)](https://storage.googleapis.com/gerrit-talks/summit/2016/robot-comments.pdf)

## Zero-downtime Gerrit upgrades

How to upgrade a Gerrit production instance without pulling the plug.
Even without having a fully redundant multi-master setup like Google
it is possible to perform a full Gerrit upgrade without having to
interrupt incoming traffic.

Learn how GerritHub.io managed to:
- upgrade its DB
- migrate data-center from Europe to America
- update Gerrit binaries and plugins
- performed full reindex

... and keeping its 100% availability at the same time.

[Slides](http://www.slideshare.net/lucamilanesio/zerodowntime-gerrit-code-review-upgrades)

*Luca Milanesio,GerritForge*
