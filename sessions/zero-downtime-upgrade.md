# Zero-downtime Gerrit upgrades

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

*Luca Milanesio,GerritForge*
