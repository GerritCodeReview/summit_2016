# Keep the conversation flowing

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
