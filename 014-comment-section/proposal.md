# Summary

Resource detail pages include a "Comments" section for users within an organization to leave descriptive notes and discuss that resource with each other.

# Motivation

While the EaaSI system itself needs to stay agnostic regarding operation/interaction with system resources, users need to be able to guide and advise each other regarding how certain resources fit within local workflows. 

They may also not be comfortable (or consider these questions and comments relevant) posting these questions in the EaaSI Community Forum. Discussion in a completely different platform also creates considerable distance between the resources being discussed and their actual manifestation in the EaaSI platform, which makes it difficult to be and stay on the same page. (i.e. needing to specify specific resource UUIDs in discussions in the Forum or elsewhere, rather than knowing that everyone is talking about the same resource because you are all on the same resource details page)

# Proposal

Free-text "Comments" field is added to all resources (Environment, Software, and Content) in the metadata model and database implementation.

All resource detail pages (Environment, Software, and Content) contain a "Comments" section with a bare-bones WSYWIG Markdown editor that allows the logged-in user to attach some arbitrary descriptive text, questions, or concerns on a resource.

See potential/suggested designs for the UI on Environment and object details pages:
- https://gitlab.com/eaasi/eaasi-client-dev/-/issues/708/designs/708_Environment-detail.png
- https://gitlab.com/eaasi/eaasi-client-dev/-/issues/700/designs/700_Object-detail.png

(In first iteration, users should only be identified by their user and display names (text-only); profile pictures could be added down the line but this is not important to start. The user information displayed *should* include a tag or icon to indicate whether they are a Configuration or Admin-level user)

The visibility and ability to add/edit comments is defined by whether the resource is "user" or "organization"-private. For instance:
- Configuration and Admin-level users have the ability to add comments on any resources tagged user-private
- Configuration and Admin-level Users have the ability to add comments and view the comments of other users within their organization on resources that have been shared to the organization-private level
- Guest-level (view-only) users can view comments on any resource directly shared with them but can not add or edit comments.
- Configuration User-level users can always edit their own comments.
- Admin-level users can edit the comments of *all other users*.

Adding or editing comments on a resource shared at the organization level **does not create a new/user-private Environment or resource**. Comments remain strictly attached to a given resource identified by UUID.

Comments **are not included in the OAI-PMH data shared when an Environment or other resource is published to the Network**. All comments remain private within an organization, always.

# Open Questions

- We are proposing that "Comments" fields remain visible *only* on the user- and organization-level layers, and are **not** included in the OAI-PMH process when publishing a resource - given privacy concerns (and I don't believe we are prepared for the implications of turning EaaSI into a full-fledged social platform enabling direct communication between individuals in separate nodes). However, there *is* a use case for users to offer guidance or other help text for a particular environment or piece of software they are publishing to users at other nodes (or within other organizations in a multi-organization node). Is a "comments" section the appropriate method to allow the latter? Or is my assumption fair that we should design and encourage other platforms (like the Forum) or features for node-to-node communication?
* Is it possible to add comments to a resource that stay private to an organization even if the resource itself has been published to the network?
  - Example: In a multi-organization node, one user saves/replicates a published environment from a remote node to the multi-org node. That environment is now usable in all orgs in the node. But can users still leave comments on the environment that remain org-private?


# Answered Questions


# New Implications

This feature adds "social" implications to the EaaSI platform (users talking directly to each other) that have not really existed in the platform up until now. This means we will also have to consider and offer some degree of options for moderation to users. (Hopefully there is considerable overlap or built-in options here with Keycloak's user management)