---
layout: post
title:  "The Trenches of the AEM Workflow API!"
---

One of the key things that in AEM is the widespread use of the Workflow and its a
use for updating metadata. Each customized workflow step can add metadata.

However, the key is to check if the following step picks up the metadata
added by the previous step. This can be sometimes challenging because the
workflow API does not explicity state but provides multiple avenues.

The workflow API provides a workflow session object to update this metadata.
Workflow session is a valuable object for working with workflow API.
It provides methods to access the workflow instances, models and routes.

Coming back to the part of metadata updates, its always recommended to use the
updateWorkflowData method to ensure that metadata updates are properly
synced in the workflow session object.

An example is that If your workflow is using a customized step for cache clearance,
a list of URLs can be appended in the metadata so that the cache clearance
step can execute operation on these URLs.

A pro tip is to have this list always cleared at the start
 before updating metadata to only add new URLs and avoid appending same URLs
 which is always a common problem with List objects.
