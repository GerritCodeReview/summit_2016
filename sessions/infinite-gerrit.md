# Infinite Gerrit 

Gerrit Review with Apache Cassandra as JGit storage.

Achieve a "virtually infinite" extensibility of the Gerrit repositories by using a multi-site distributed storage backend based on
Apache Cassandra.

Benefits are:

1. Steps towards a real Gerrit peer-to-peer infrastructure
where every server can potentially read and write to any of the Cassandra nodes.
2. Ability to extend the capacity of the existing network of Gerrit servers by adding additional Cassandra nodes and getting the quorum distribution out-of-the-box.

*Haithem Jarraye, GerritForge*
