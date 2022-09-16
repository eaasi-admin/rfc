# Meeting Notes

[Dev Meeting Notes](https://docs.google.com/document/d/1FVOQU9eM6hNaKeOIZCVAfS-G6ljhGbOuht_6rf90c3E/edit?usp=sharing)

# Summary

Users start the process of creating new base environments or content environments by compiling hardware templates and bootable objects into an emulation project.

# Motivation

Users need to compile resources together and run them in emulation in order to perform configuration/installation tasks for the creation of new environments or modification of existing environments.

# Proposal

## Definitions

* **Base environment** An environment whose bootable operating system or ROM contains only installed and configured software. A software environment cannot contain content.
* **Content environment** A derivative environment in which content has been saved, and/or installed into an existing environment’s operating system. The intended use of a Content Environment is to provide access to digital/collection objects as they would have been rendered in their original (or a representative) computing environment. *A content environment may not be used as a base environment in a new emulation project. It can only be revised once saved as a content environment.*

## Emulation Project Queue

* Users may add a base environment or object to their Emulation Project Queue by selecting the "Add to Emulation Project" option in the action menu.
* The queue has two sections: environments and objects.
* An "Empty Disk" option should always be available at the top of the objects queue in the Advanced emulation project.
* Resources may be removed from the queue individually or all at once by clearing the queue.
* Resource cards in the queue displays the resource name, type icon, and permission icon.

## Advanced Emulation Project Configuration

* Users access the advanced emulation workflow by selecting the Emulation Project tab in the navigation menu, where they are presented with the Basic or Advanced workflow options.
* The Advanced workflow starts by requesting a user select an appropriate hardware template. The user may switch between templates as needed to find the correct hardware settings. 
* The interface displays metadata about the hardware configuration of the selected template:

| Metadata Property | Example |
| --------------- | --------------- |
| Emulator (version) | QEMU v3.1 |
| Architecture | x86 |
| RAM | 512 |
| CPU Cores | 1 |

* The Drives section is also populated once a user selects their hardware template.
* Users can drag/drop compatible objects into a drive slot as needed
* Once an object is placed in the emulation project, the object section (environment or object) expands to display metadata (if available:

| Section | Metadata Property | Example |
| --------------- | --------------- | --------------- |
| Software | Related Software | Adobe Acrobat 3.0 |
| Object Part | Label (or filename if no label) | Disc 1 of 3  |
| Object Part | Physical Format | CD-ROM (maybe an icon?) |

*Related software may have more than one value*
*Object part entries repeat if object consists of more than one file*

* Objects may only be placed in a compatible drive type: CD-ROM in a CD-ROM drive, hard disk images in hard drive, etc. When a user drags an object from their queue, the compatible drive slots are they only ones made available.
* Users may load as many of the drives in the array as they wish.
* Any drive with an object loaded into it may be marked as a "Boot Drive"
* Objects can be replaced with other objects by dragging a resource card into the compatible slot. The object previously occupying the active slot is returned to the queue.
* The Run button is not made available until a hardware template is selected and a bootable object is placed in a compatible drive slot.

## Empty Disk

* A set of empty disk images should be available to a user that wants to install an operating system from scratch.
* To use the empty disk, the user must first drag it into a compatible Hard Disk drive slot
* The system then makes available a dropdown list of the available drive sizes from which the user selects.

## Use Cases

### Create environment from scratch

Pre-conditions: OS installer object in emulation project queue

1. User opens Emulation Project page from navigation menu
2. User selects Advanced project option
3. System prompts user to select hardware template
4. User chooses hardware template from dropdown
5. System populates metadata and drive array in project interface
6. User drags OS installer object to CD-ROM drive
7. System populates metadata in drive section
8. User selects CD-ROM drive as Boot Disk
9. User drags empty disk to hard drive slot
10. System populates drive slot and displays disk size dropdown
11. User selects empty disk size
12. System makes Run Project button active
13. User begins emulation session

### Create environment from existing hard drive image

Pre-condition: Hard drive image object in emulation project queue

1. User opens Emulation Project page from navigation menu
2. User selects Advanced project option
3. System prompts user to select hardware template
4. User chooses hardware template from dropdown
5. System populates metadata and drive array in project interface
6. User drags hard drive image object into compatible hard disk drive slot
7. User selects hard drive as Boot Disk
8. System makes Run Project button active
9. User begins emulation session

# Open Questions

* Is there a need to save the Project (and create multiple Emulation Projects, each with a separate pool of resources)?
* How does the emulator know which drive should boot first if multiple drives are selected as Boot Drive?
* How do we include other components required by systems, like ROMs?

# Answered Questions


