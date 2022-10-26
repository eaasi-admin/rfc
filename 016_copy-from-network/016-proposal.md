# Meeting Notes

[Dev Meeting Notes](https://docs.google.com/document/d/1mU8bZOeWG665DNtNEszOv-cBTPcGuS0I9I-ndW9eeRQ/edit?usp=sharing)

# Summary

Users copy resources from other nodes to theirs in order to use them in configuration work at their node.

# Motivation

Sharing resources between nodes is a fundamental component of the EaaSI service. It allows organizations to benefit from the software preservation efforts of other organizations in a network and eliminates the need to collect/own every application required by their collections.

# Proposal

* Base environments and software objects may be copied from other nodes. Content environments and objects cannot be published and therefore cannot be copied from other nodes.
* A resource can only be copied to a node after it has first been shared to the network and the resource's metadata copied via sync.
* There should be some method for indicating that the resource's data is saved locally so user's know whether they can use it in an emulation project.
* Public resources from other nodes cannot be added to emulation project's until they are saved from the network.
* The user who triggered a "copy" action becomes owner of that resource
* The copied resource becomes available to all users in that user’s organization tenancy but not in other orgs in a multi-tenancy instance
* The copied resource counts against the org's storage quota
* The metadata model includes some info about where a resource originated that is separate from keycloak/access management ownership information

# Open Questions

* The action menu option for this function is "Save to my Node" but this is not how we refer to individual orgs anymore. What should it say instead? "Save from Network"? "Copy from Network"?

# Answered Questions


