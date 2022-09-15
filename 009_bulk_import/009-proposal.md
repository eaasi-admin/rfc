# Meeting Notes

[Dev Meeting Notes](https://docs.google.com/document/d/1DtnEhNMwNUnYX8fJ0maj1UiMOcrUpWwBJwWLdXVuu4w/edit?usp=sharing)

# Summary

Users may bulk import files then combine them as objects for use in EaaSI.

# Motivation

Users may have need to add multiple objects at one time and importing each object individually, as is currently supported, may be too arduous a task. Bulk import provides an expeditious means for adding objects to a node.

# Proposal

## Add Files

* "Bulk Import" is an option in the import object section of the EaaSI UI. The other option is "Individual Import"
* A user must first select the files they want to import to their object workspace. Files may be imported from S3 compatible storage, user's computer, or from local watch folder (local deployment only?). No additional metadata about the files is requested; it will be collected when the user builds their object later in the process.
* Users cannot upload more than the allotted storage amount for their node. If the files they've selected exceed this amount, the system must return an error.
* File upload should occur in the background, so users can complete other tasks while it completes. Status should appear in the Running Tasks queue.

## My Files

* Files imported by a user can be found in the My Resources UI in a tab titled "My Files"
* Files are displayed in a list that displays file name, format, size, and date imported. Files may be sorted on any of these properties. 
* A check box is next to each file in the queue. The action menu appears when one file is selected, with options to "Create Object" or "Delete"

## Create Object

* When a user selects the "Create Object" action, a widget is displayed to guide them through the process.
* Users must provide a name to create their object.
* When the object is created, the user is sent to the object's detail page where they can add additional metadata if necessary.

# Open Questions

* Can users import files from their desktop or some other storage location (e.g., FTP? watch folder?)?
* As outlined above, this process ends up at the same point of the individual import workflow. Users are still compiling files into individual objects. How do we enable bulk import with some level of automation?

# Answered Questions


# New Implications

* Uploading numerous files at once may use up the allocated storage for a node rather quickly. There will need to be some mechanism for setting storage quotas at the user level to control how much data a user can add to a node at one time.
* Users will expect some mechanism for integrating with repository systems or maybe even asset management software. We will need to somehow offer a view into those systems to select what files to "import" into a node. I imagine the actual data would not be copied to EaaSI storage until it is needed for use in an emulation session.
