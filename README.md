# IETF Glossary

*This is a proposal for a glossary of terms used in IETF RFCs*

## Introduction

The purpose of this glossary is to collect terms from existing, published standards documents, and provide a place from
which they can be referenced. Specific terms can have more than one definition, as long as it comes from a published
standards document. Documents - including draft and non-standards documents - that subscribe to a specific definition of
a term, may provide a link to their document, and the specific definition they are using.

The intent of this glossary is to provide a single source of truth for the definitions of terms that are used, but also
to provide a method by which other uses of a specific definition may be easily discovered. With any luck, this will lead
to a convergence of vocabulary usage.

[Here is a sample](./sample.glossary.md)

## Motivation

The development of standards in the IETF requires extensive discussions that are essential to ensure consensus on the issues at hand. Many of these standards introduce concepts that are novel, and existing terms are used to describe the novel concept. While the core participants are usually aligned on the specific meaning behind a term, they may not be aware of other definitions of a term. Infrequent participants may have a different definition in mind when encountering a term, leading to misunderstandings and a lack of consensus.

The goal of this glossary is to increase the awareness of the different definitions of a term, and enable core participants to select or create the definition they are using for a term, assisting infrequent participants' understanding and facilitating smoother collaboration in the IETF standards development process.

The challenge of the different meanings of terms has become apparent in discussions that include identity related terms. The glossary would initially focus on identity terms and be hosted by the Security Area Group. If this experiment proves useful, it can be expanded to the broader IETF community if desired.

## Glossary Content

The glossary will contain: terms and definitions used in published (finalized) documents; and references to new terms and definitions being proposed in draft (work in progress) documents.

New definitions for existing terms, or new terms being used in draft documents will not be published in the Glossary until the document has been published. This creates awareness of new terms and definitions, where the work is being done, and prevents other documents referencing a definition that may change or be dropped. The draft document that has a definition for an existing term, or is defining a new term, SHOULD have a reference to the Glossary. This creates awareness of a new definition or term to the broader community who can provide feedback on how the term is used and being defined, and suggestions on using existing definitions, or alternative terms.


## Glossary Update Process

Updates are processed differently depending on if the update is referencing a published document, or a draft document.

### References to Published Documents
1. Anyone can propose a new term, definition, or reference by creating a GitHub pull request (PR). A GitHub Action will then run the initial checks that the update meets the update requirements:
- a. Does not delete a term, definition, or reference for final documents.
- b. Does not update an existing term.
- c. New definitions MUST either:
  - exist in a final document
  - consensus on the definition has been reached on the mail list of the working group that created the document

2. A member of the Glossary Team will review the PR and provide feedback to the proposal or submit the PR to the publication queue.

3. Anyone can subscribe to be notified when a PR is promoted to be in the publication queue, and provide comments to the PR.

4. After a minimum of two weeks, a separate member of the Glossary Team will review the PR and will provide feedback and return the PR to the proposer or publish the PR.

5. When a PR is published, a GitHub Action is run that updates the official glossary document.

### References to Draft Documents

1. A draft author can propose a new reference to their draft for an existing term, an existing definition, a new term, or a placeholder for a new definition, or delete a reference to their draft. The draft MUST include a reference to the Glossary.

2. A member of the Glossary Team will review the PR and provide feedback to the proposal, or publish the PR to the official glossary document.

## Draft Documents and the Glossary

The references in the Glossary to drafts that are using a new term, or providing a new definition, is the key task to achieving the goal of creating awareness of the definitions of terms, and how a term is being used.

Draft authors can either: reference an existing definition by providing a reference to the definition in the glossary adding the draft as a reference in the glossary; or create a new definition by writing the definition in the draft and providing a reference to a placeholder for the definition in the glossary. In both cases, there is now a reference to the draft creating awareness for others that a draft is using the term.

If the draft is published and it has a new definition, a PR will be created for the new definition on publication.

## Seeding the Glossary

The creation of the glossary was motivated by confusion of identity related terms. The id-align group was created to work on aligning identity related work, and its members will be the initial contributors to the glossary, with identity related terms.

## Glossary Build Process

We are proposing using a YAML file for each term, that is named for the term. See [YAML proposal](./yaml.schema.md).

## Open Questions

Locations:
- GitHub repository org and name
- Official hostname and path
  - ietf.org or rfc-editor.org
- Definition reference format

Source Document Format:
* Markdown?
* [YAML proposal](./yaml.schema.md)

Official published formats:
* HTML, PDF, ???

Expired Draft References
* Are they kept in the glossary, or deleted? (deleted after a while as they are only references)

Glossary Team
* Who are the initial members (from id-align)? How are new members added?


## FAQ

Q1: Can the glossary be normatively referenced?
- No. The glossary is intended for informative references.

Q2: How will consensus be achieved on the definition of a term?
- The glossary project is not creating definitions, it is gathering existing definitions from existing documents. If a term is used in a published document, then the individuals that created that document will gather consensus on the definition on how the term was used in that document.

Q3: Why not allow working documents to define new terms before they are published?
- We don't want other documents  to reference a term and definitions that may change. Only terms / definitions that have been published are included in the Glossary, and those are never updated.

Q4: How will new terms and definitions from working documents be added to the Glossary?
- When a working document is published, the new term, or new definition to an existing term will be added to the glossary.

# Additional Links

* [Editor's Copy](https://krotscheck.github.io/ietf-glossary/#go.draft-ietf-glossary.html)
* [Datatracker Page](https://datatracker.ietf.org/doc/draft-ietf-glossary)
* [Working Group Draft](https://datatracker.ietf.org/doc/html/draft-ietf-glossary)
* [Compare Editor's Copy to Working Group Draft](https://krotscheck.github.io/ietf-glossary/#go.draft-ietf-glossary.diff)

## Command Line Usage

Formatted text and HTML versions of the draft can be built using `make`.

```sh
$ make
```

Command line usage requires that you have the necessary software installed. See
[the instructions](https://github.com/martinthomson/i-d-template/blob/main/doc/SETUP.md).

