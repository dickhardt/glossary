# IETF Terminology

# THIS IS A PROOF OF CONCEPT FOR WHAT A GLOSSARY COULD LOOK LIKE #

## Introduction

This is a living document that captures how key terms are used in IETF and other SDO documents. 

## Motivation

The development of standards in the IETF requires extensive discussions that are essential to ensure consensus on the issues at hand. Many of these standards introduce concepts that are novel, and existing terms are used to describe the novel concept. While the core participants are usually aligned on the specific meaning behind a term, they may not be aware of other definitions of a term. Infrequent participants may have a different definition in mind when encountering a term, leading to misunderstandings and a lack of consensus.

The goal of this glossary is to increase the awareness of the different definitions of a term, and enable core participants to select or create the definition they are using for a term, assisting infrequent participants' understanding and facilitating smoother collaboration in the IETF standards development process.

The challenge of the different meanings of terms has become apparent in discussions that include identity related terms. The glossary would initially focus on identity terms and be hosted by the Security Area Group, and then if desired by the broader IETF community, promoted to include the broader community.

## Glossary Content

The glossary will contain: terms and definitions used in finalized documents; and references to new terms and definitions being proposed in draft documents. 

New definitions for existing terms, or new terms being used in draft documents will not be published in the Glossary until the document has been finalized. This creates awareness of new terms and definitions, and where the work is being done. The draft document MUST have a reference to the Glossary, which creates awareness of the Glossary and related terms. This allows the broader community to provide feedback on how the term is used and being defined, and eliminates confusion if usage of the term is dropped or the definition is updated in future drafts.


## Glossary Update Process

Updates are processed differently depending on if the update is referencing a finalized document, or a draft document.

### References to Finalized Documents
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

Referencing working drafts that are using a new term, is the key task to achieving the goal of creating awareness of the definitions of terms, and how a term is being used.

Draft authors can either: reference an existing definition by providing a reference to the definition in the glossary adding the draft as a reference in the glossary; or create a new definition by writing the definition in the draft and providing a reference to a placeholder for the definition in the glossary. In both cases, there is now a reference to the draft creating awareness for others that a draft is using the term.

If the draft is published and it has a new definition, a PR will be created for the new definition on publication.

## Seeding the Glossary

The creation of the glossary was motivated by confusion of identity related terms. The id-align group was created to work on aligning identity related work, and its members will be the initial contributors to the glossary, with identity related terms.


## Open Questions

Locations: 
- GitHub repository org and name
- Official hostname and path
  - ietf.org or rfc-editor.org
- Definition reference format

Source Document Format:
* Markdown?
    
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
- The glossary project is not creating definitions, it is gathering existing definitions from existing documents. If a term is used in a finalized document, then the individuals that created that document will gather consensus on the definition on how the term was used in that document.

Q3: Why not allow working documents to define new terms before they are published?
- We don't want other documents  to reference a term and definitions that may change. Only terms / definitions that have been finalized are included in the Glossary, and those are never updated.

Q4: How will new terms and definitions from working documents be added to the Glossary?
- When a working document is finalized, the new term, or new definition to an existing term will be added to the glossary.





[A](#A) [B](#B) [C](#C) [D](#D) ...

# A

## Access Token
### [RFC 6749 §1.4](https://www.rfc-editor.org/rfc/rfc6749#section-1.4)  

Access tokens are credentials used to access protected resources.  An
access token is a string representing an authorization issued to the
client.  The string is usually opaque to the client.  Tokens
represent specific scopes and durations of access, granted by the
resource owner, and enforced by the resource server and authorization
server.

The token may denote an identifier used to retrieve the authorization
information or may self-contain the authorization information in a
verifiable manner (i.e., a token string consisting of some data and a
signature).  Additional authentication credentials, which are beyond
the scope of this specification, may be required in order for the
client to use a token.

The access token provides an abstraction layer, replacing different
authorization constructs (e.g., username and password) with a single
token understood by the resource server.  This abstraction enables
issuing access tokens more restrictive than the authorization grant
used to obtain them, as well as removing the resource server's need
to understand a wide range of authentication methods.

Access tokens can have different formats, structures, and methods of
utilization (e.g., cryptographic properties) based on the resource
server security requirements.  Access token attributes and the
methods used to access protected resources are beyond the scope of
this specification and are defined by companion specifications such
as [RFC6750].

See also [Bearer Token](#Bearer_Token), [DPoP Proof JWT](#DPoP_Proof), [Refresh Token](#Refresh_Token)
# B

## Bearer Token

### [RFC 6750 §1.2](https://www.rfc-editor.org/rfc/rfc6750.html#section-1.2) 

A security token with the property that any party in possession of the token (a "bearer") can use the token in any way that any other
party in possession of it can.  Using a bearer token does not
require a bearer to prove possession of cryptographic key material (proof-of-possession)

See also [Access Token](#Access_Token), [DPoP Proof JWT](#DPoP_Proof_JWT)
# C

## Credential 

### [NIST 800-63-3 §A.1 Credential](https://pages.nist.gov/800-63-3/sp800-63-3.html)
An object or data structure that authoritatively binds an identity - via an identifier or identifiers - and (optionally) additional attributes, to at least one authenticator possessed and controlled by a subscriber.

While common usage often assumes that the subscriber maintains the credential, these guidelines also use the term to refer to electronic records maintained by the CSP that establish binding between the subscriber’s authenticator(s) and identity.

### [W3C Verifiable Credentials Data Model v1.1 Credential](https://www.w3.org/TR/vc-data-model/#dfn-credential)
A set of one or more claims made by an issuer. A verifiable credential is a tamper-evident credential that has authorship that can be cryptographically verified. Verifiable credentials can be used to build verifiable presentations, which can also be cryptographically verified. The claims in a credential can be about different subjects.

# D

## DPoP Proof JWT
### [RFC 9449 §4](https://www.rfc-editor.org/rfc/rfc9449.html#name-dpop-proof-jwts)
DPoP introduces the concept of a DPoP proof, which is a JWT created by the client and sent with an HTTP request using the DPoP header field. Each HTTP request requires a unique DPoP proof.

A valid DPoP proof demonstrates to the server that the client holds the private key that was used to sign the DPoP proof JWT. This enables authorization servers to bind issued tokens to the corresponding public key (as described in Section 5) and enables resource servers to verify the key-binding of tokens that it receives (see Section 7.1), which prevents said tokens from being used by any entity that does not have access to the private key.

The DPoP proof demonstrates possession of a key and, by itself, is not an authentication or access control mechanism. When presented in conjunction with a key-bound access token as described in Section 7.1, the DPoP proof provides additional assurance about the legitimacy of the client to present the access token. However, a valid DPoP proof JWT is not sufficient alone to make access control decisions.

See also [Access Token](#Access_Token), [Bearer Token](#Bearer_Token)
