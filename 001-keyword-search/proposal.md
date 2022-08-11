[Dev Planning Meeting Notes](https://docs.google.com/document/d/1A-g-b59uG3P5wN2shbcQEG1H_A--uAqfRUg90iMlYTY/edit?usp=sharing)

[Dev Planning Meeting Notes - 7/14](https://docs.google.com/document/d/1XVAfRK5LuGlTonzzlI9wvwDlMaaJazjZPLKlGRTRX_k/edit?usp=sharing)

# Summary

Additional properties describing environments and objects are searchable via the keyword search bar in the EaaSI interface. Search results are displayed as resource cards in Explore Resources UI.

# Motivation

Users need to locate and understand relevant resources so they can complete actions in the system, such as compiling resources in an emulation project, editing metadata, sharing to node/network, and/or providing access to end users.

# Proposal

## Current State

metadata for all resources and each requesting user...

* is fetched from backend
* cached in RAM in the middle-layer

keywords are then searched in each cached resource-metadata (label and id)

## Desired State

* System utilizes infrastructure to store metadata describing environment and object resources that can be indexed for search and displayed as results in UI. Standardized documentation format (e.g., extended METS XML) stores metadata about resources at rest, which may then be utilized for search and other applications within the system. 
* Reduces redundant storage of metadata in front and back-end and establishes a single source of truth within system. 
* Enables completion of search query within seconds. 
* User should be able to find relevant resource within 1-2 pages of search results based on individual keyword.

### Potential properties for indexing

**Environment**

* Source Organization
* Environment Name
* Description
* Operating System Name
* Operable Software Name
* Content Name
* External Identifier
* Tags

**Object**

* Source Organization
* Name
* Software Name
* Content Name
* External Identifier
* Developer/Publisher (TBD)

# Open Questions

* When and how is data exchanged for various search and display requirements?
* What is our benchmark for search? Exact targets?


# Answered Questions



# Proposed Iterations

First iteration, keep the search box simple
Don’t complicate the box itself with advanced searches, ability to add prefixes to search certain subfields
Focus first on actually adjusting the metadata we capture and the way its stored
1. Server-side pagination and cache improvements (moving data to back-end?) to avoid every user replicating metadata for all resources
2. Expand available subfields
Go in this order b/c 1) will simply/make 2) more feasible
