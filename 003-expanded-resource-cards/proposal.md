[Dev Planning Meeting Notes](https://docs.google.com/document/d/1A-g-b59uG3P5wN2shbcQEG1H_A--uAqfRUg90iMlYTY/edit?usp=sharing)

[Dev Planning Meeting Notes - 7/14](https://docs.google.com/document/d/1XVAfRK5LuGlTonzzlI9wvwDlMaaJazjZPLKlGRTRX_k/edit?usp=sharing)

# Summary

Resources (environments and objects) available to the user are represented in the UI as "resource cards" in bento box-like design. Resource cards display meaningful/descriptive metadata properties about the resource to the user either as text or icons.

# Motivation

The user needs a graphical representation of a resource in order to make choices about how to manipulate and manage it in the system. Enough information about each resource must be provided to allow the user to make decisions about which individual resources they would like to perform additional actions on (bookmark, add to Emulation Project, run in emulator, view details, etc.)

# Proposal

## Current State

Metadata for all resources and each requesting user:
* is fetched from the back-end
* cached in RAM

Resource cards vary in the metadata they display depending on Resource Type (Environment, Software, Content or Image)

Environment cards display:
* Environment Name
* "# of Drives"
* Emulator
* Printing Enabled
* Internet Enabled
* Resource type icon
* Network Status icon

Software cards display:
* Is Operating System
* Resource type icon
* Network Status icon

Content cards display:
* Resource type icon

Image cards display:
* Resource type icon
* Network Status icon



## Desired State

* System utilizes infrastructure to store metadata describing environment and object resources that can be indexed for search and displayed as results in UI. Standardized documentation format (e.g., extended METS XML) stores metadata about resources at rest, which may then be utilized for search and other applications within the system. 
* Reduces redundant storage of metadata in front and back-end and establishes a single source of truth within system. 
* Resource cards line up as much as possible with facets for consistency of user experience

### Potential properties for indexing and display

**Environment**

* Enivornment Type (Base, Content)
* Operating System Name
* Source Organization
* Emulator
* Tags
* Resource type icon
* Network Status icon

**Software**

* Software Product(s)
* Developer/Publisher (TBD)
* Tags
* Resource type icon
* Network Status icon

**Content**
* Tags
* Resource type icon
* Network Status icon

# Open Questions

* When and how is data exchanged for various search and display requirements?
* Will expanded metadata in resource cards require any significant UI redesign/adjustment?
* Clarify role of "image" resources in domain model; will Images continue to be separate resources (meriting their own resource cards) or are these being folded into objects (and therefore either imported and displayed as Software or Content?)


# Answered Questions



# Proposed Iterations

Focus first on actually adjusting the metadata we capture and the way its stored, then take account of "Image" resources in UI design, then adjust and/or expand metadata displayed in resource cards
1. Server-side pagination and cache improvements (moving data to back-end?) to avoid every user replicating metadata for all resources
2. migrate Image resource metadata to fit agreed-upon domain model
3. Expand available subfields
