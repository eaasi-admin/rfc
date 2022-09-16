# EaaSI RFCs

The EaaSI project uses the RFC (request for comment) process to propose and document updates to the EaaSI system in a collaborative environment. Proposals are an opportunity for EaaSI team and community members to describe a new feature, address questions with developers, and establish consensus on an implementation approach before design and development begin.

## When to submit an RFC

RFCs are required for functional changes that will have a significant impact on use and operation of the system, such as:

* Changes to core workflows supported by the system (e.g., search/discovery, import, configuration, access).
* Changes to distribution methods (e.g., installer updates, packaging mechanisms, etc.).
* Changes with substantial architectural implications (e.g., auth schemes, API updates, data management, security protocols, etc.)
* Changes requiring the implementation of new interface components

An RFC is not needed for minor changes or improvements, including bug reports, which may be reported by users in the [EaaSI Community Forum](https://forum.eaasi.cloud). 

## How to submit an RFC

1. Fork this repository.
2. Create a new branch in your forked repository and provide a descriptive name referencing the subject of the proposed change.
3. Create a directory for your proposal within this branch and provide a descriptive name such as '000-search-discovery'.
4. Copy the '000-template' file to your new directory and provide a descriptive name such as '000-new-proposal'.
5. Write a proposal in '000-new-proposal/proposal.md'.
    * Include any dependent assets (use cases, mockups, etc.) under your RFC directory.   
6. Submit a pull request. The pull request number determines the RFC number.
7. Rename the proposal directory to match the pull request number, e.g., '123-new-proposal'.

   For convenience, update the PR description to link to the rendered proposal
   in the pull request body like so:

   ```
   [Rendered](https://github.com/{YOUR NAME}/rfcs/blob/{YOUR BRANCH}/123-my-proposal/proposal.md)
   ```
8. Review the RFC and add comments/questions as you conduct discussions with other stakeholders and developers. This maintains a public record of the collaborative process of proposal design.
9. The RFC will be reviewed by members of the EaaSI team, including the User Support Lead and Lead Developer, adding comments and questions in response to the initial proposal.
10. Update the RFC based on feedback from the team and other stakeholders by pushing commits to your fork. Please provide descriptive commit messages summarizing the changes made to the proposal.

## Resolution of an RFC

Members of the EaaSI team will determine whether the proposal aligns with the design rationale for EaaSI and will result in concrete improvements for users of the system. EaaSI developers will assess the risks of any technical tradeoffs or maintenance requirements to inform assessment of the long-term impact of the proposed change.

Once consensus is reached, the Program Manager will label the RFC to indicate the decision made by the EaaSI team:

* **resolution/merge**: the proposal will be merged; there are no outstanding
  objections, and implementation can begin as soon as the RFC is merged.
* **resolution/close**: the proposal will be closed.
* **resolution/postpone**: resolution will be deferred until a later time when
  the motivating factors may have changed.
  
## Implementing an RFC

TBD

## License

All RFCs, and any accompanying code and example content, will fall under the
Apache v2 license present at the root of this repository.

**The EaaSI RFC process is based proposal process designed by the Concourse CI project as outlined in their [RFC repo](https://github.com/concourse/rfcs)**
