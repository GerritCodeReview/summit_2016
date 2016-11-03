# Plugins for CI Systems

I will give an overview of 3 new plugins developed by the Qualcomm Innovation Center for use by CI systems: the batch, manifest, and task plugins.  I will review what these plugins can do, and how we use them along with our future plans and ideas for these plugins. I will also talk about the core modifications that were needed to create these plugins, and what future core modification I believe may still be needed, along with some of the challenges of doing more in plugins.

A quick overview of the 3 plugins:

The batch plugin provides a mechanism for building and previewing sets of proposed updates to multiple projects/branches/refs that should be applied together. The focus of batch updates tend to be verification (by CI systems).  The batch update service provides the tools to build refs by merging changes to temporary “snapshot” refs, which can then be tested extensively, and finally submitted ”as is".

The manifest plugin provides server side utilities to operate on, and query information about repo manifests (xml) stored in git projects on the current server.  This plugin provides APIs to update values in manifests, and to search for manifests with certain values.

The task plugin provides a mechanism to manage tasks which need to be performed on changes along with a way to expose and query this information. Tasks are organized hierarchically, and task definitions use gerrit queries to define which changes each task applies to, and how to define the status criteria for each task. An important use case of the task plugin is to have a common place for CI systems to define which changes they will operate on, and when they will do so.

*Martin Fick, Qualcomm Innovation Center*


