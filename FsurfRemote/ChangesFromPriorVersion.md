[title]: - "What's New in Fsurf 2.0"


## Overview
This document describes the new features in Fsurf 2.0 and 
the differences from the 1.x versions.

## What's New

Fsurf 2.0 adds a few new features:

* [Support for running the recon-all workflow using multiple scans of the same subject](https://support.opensciencegrid.org/support/solutions/articles/12000008490-an-example-of-processing-a-scan#reconstructing-an-image-with-multiple-inputs).  This allows for FreeSurfer to apply correct for errors in the scans due to subject movement. 
* [Support for running the recon-all workflow using a custom set of options](https://support.opensciencegrid.org/support/solutions/articles/12000008490-an-example-of-processing-a-scan#running-recon-all-with-custom-options).  This allows users to run the recon-all workflow step by step using a specific options for each step.
* Better indications of workflow progress and information on completed  workflows.

## Differences from Fsurf 1.x
### Inputs for submission 

Fsurf 2.0 added support for two new workflow types (multiple input and custom).
Since Fsurf 1.x only supports the standard workflow, it uses different options
for inputs. The input file is derived from the subject name and doesn't
necessarily need to be specified.  E.g. if the subject is `MRN_1` then Fsurf 1.x
would look for a mgz file called `MRN_1_defaced.mgz`.  If the file is in the
current directory, Fsurf 1.x would look for that file by default.  Therefore,
you could run a workflow on the `MRN_1` subject when using Fsurf 1.x by running

    fsurf --subject MRN_1
    
If the file was in another directory, you would need to specify this
using the `--dir` option:

    fsurf --subject MRN_1 --dir /path/to/scans

### Output 

Fsurf 2.x and Fsurf 1.x also vary slightly in the output generated.  The only
place where this varies significantly is when displaying information about
workflows.  Fsurf 1.x does not show the number of total tasks and completed tasks
when the `list` command is used.  In addition, Fsurf 1.x only gives the workflow
status when the `status` command is used.  Fsurf 2.x provides a more complete
summary of the workflow status and some details about resources that the
workflow used.

### Workflow status

Fsurf 1.x also used slightly differnt terms to indicate the status of a workflow.
Fsurf 1.x uses `UPLOADED` when a workflow has been created instead of `QUEUED`.
Similarly, Fsurf 1.x uses `PROCESSING` instead of `RUNNING` when a workflow has
been started.
