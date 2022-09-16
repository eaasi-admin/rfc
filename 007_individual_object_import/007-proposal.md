[Dev Planning Meeting notes](https://docs.google.com/presentation/d/1dj8nChm2k2ojUJBPd-v9wOZhm1JI6_LXwjAOIHeyoz0/edit?usp=sharing)

# Summary

Users may import an individual object into their node, providing a limited set of metadata and details of associated files.

# Motivation

Users need to load their objects into the system so they can be used in configuration workflows to create new base and content environments. An individual import option allows non-expert users to add their resources in a quick, straightforward process, especially for content objects.

# Proposal

## Current State

The system provides multiple options for individual import: import software object, import content object, and import image. Users are guided through a three part process: Add name, select file, add file data. There are limits on the size of the uploaded object. Upon completion of the import, a new object is available to the "owner" user. 

## Desired State

Individual object import is consolidated into a single workflow presented as an option in the Import Resource interface. Users are still guided through the three step process:

* **Enter metadata** - *additional properties to capture are listed below*
* **Select file** - users may select files from their desktop? or provide a URL. An object must have at least one file associated with it.
* **Finish import** – users provide details about the file(s) associated with the imported object
  * **Order** - Determines which disk is first loaded into the emulator and how disks are displayed in change media list. *If object is made up of a set of individual files (e.g., a collection of documents), order is not provided as an input option. The system will wrap the files into an .iso for mounting, making any "order" designation irrelevant.*
  * **Format** (Required) – Determines how the system will handle the corresponding object file. May be Floppy, Disk, File, or ISO. If multiple files are selected, the format field can be changed in bulk.
  * **Label** - Defaults to the files name as received from source. Users may update to provide additional information associated with the individual file. For example, labeling the file with label information from the original disk (e.g., "Installation Disc 1 of 3")

Once the import workflow is completed, the system loads the associated object detail page or My Resources page (see question below). The object is assigned the user level permission and may only be seen/used by the user who imported it and node admins.

## Proposed metadata

Properties to be collected in the first step of the individual object import process:

* **Name** (Required) - Name given to the object
* **Type** (Required) - *Content or Software* Indicator of what the object conveys for operation within an emulated environment and how it should be handled by EaaSI.
* **External Identifier** – Reference to object used by other systems or registries.
* **External Identifier Source** - Name of sytem or registry that the identifier is from
* **Product Key** - String of numbers and letters needed to access the contents of the disk

# Open Questions

* Should we continue to offer the option to import directly from the user's computer or require the use of URLs for all imports?
* Does the system currently interpret the order specification of an object? How can we make it easier to navigate the use of multi-disk objects in the system?
* We currently use ISO to identify compact discs, but is this clear to non-expert users?
* What should the default format be set to in the dropdown? It is currently "File"
* Should finishing an import lead the user to the detail page or their My Resources page?

# Answered Questions



# New Implications

We do not anticipate users uploading large collections of content objects of certain types–special collections materials, artworks, maybe data sets. Instead, users may import these materials only as needed at the time of request and not preemptively or in a systematic workflow.
