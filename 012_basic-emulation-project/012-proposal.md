# Meeting Notes

[Dev Meeting Notes](https://docs.google.com/document/d/1FVOQU9eM6hNaKeOIZCVAfS-G6ljhGbOuht_6rf90c3E/edit?usp=sharing)

# Summary

Users combine base environments and objects from a compiled queue of resources before running in the configuration interface. Emulation project interface displays relevant information about the selected environment and object to inform selection of resources.

# Motivation

Users need to compile resources together and run them in emulation in order to perform configuration/installation tasks for the creation of new environments or modification of existing environments

# Proposal

## Definitions

* **Base environment** An environment whose bootable operating system or ROM contains only installed and configured software. A software environment cannot contain content.
* **Content environment** A derivative environment in which content has been saved, and/or installed into an existing environment’s operating system. The intended use of a Content Environment is to provide access to digital/collection objects as they would have been rendered in their original (or a representative) computing environment. *A content environment may not be used as a base environment in a new emulation project. It can only be revised once saved as a content environment.*

## Emulation Project Queue

* Users may add a base environment or object to their Emulation Project Queue by selecting the "Add to Emulation Project" option in the action menu.
* The queue has two sections: environments and objects.
* Resources may be removed from the queue individually or all at once by clearing the queue.
* Resource cards in the queue displays the resource name, type icon, and permission icon.

## Basic Emulation Project Configuration

* Users access the basic emulation workflow by selecting the Emulation Project tab in the navigation menu, where they are presented with the Basic or Advanced workflow options.
* The Basic workflow presents two empty spaces for the user to fill: one environment and one object.
* Users can drag/drop compatible resources (environment in the environment space, object in the object space)
* Once a resource is placed in the emulation project, the resource section (environment or object) expands to display the resource's metadata:

**Environment**

| Section | Metadata Property | Example |
| --------------- | --------------- | --------------- |
| Hardware | Emulator (version) | QEMU v3.1 |
| Hardware | Architecture | x86 |
| Hardware | RAM | 512 |
| Hardware | CPU Cores | 1 |
| Operating Environment | OS Software (Language) | Windows 98 SE (English) |
| Operating Environment | Operable Software (Language) | Microsoft Word 97 (English) |

  *Operating environment section repeats if environment has more than one*

**Object**

| Section | Metadata Property | Example |
| --------------- | --------------- | --------------- |
| Software | Related Software | Adobe Acrobat 3.0 |
| Object Part | Label (or filename if no label) | Disc 1 of 3  |
| Object Part | Physical Format | CD-ROM (maybe an icon?) |

*Related software may have more than one value*
*Object part entries repeat if object consists of more than one file*

* Resources can be replaced with other resources by dragging a resource card into the compatible slot (environment or object). The resource previously occupying the active slot is returned to the queue.
* The Run button is not made available until the emulation project is complete and both an environment and object resource are selected.

# Open Questions

* Is there a need to save the Project (and create multiple Emulation Projects, each with a separate pool of resources)?

# Answered Questions


