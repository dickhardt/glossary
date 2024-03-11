# IETF Terminology

## Introduction

This is a living document that captures how key terms are used in IETF and other SDO documents. 

## Proposing Updates

To propose an update to this document, clone this repository and make your update, and create a pull request(PR) (link to more detailed directions). Your PR will be reviewed by the current glossary editorial review team. 

Acceptable PRs
- a new definition for an existing term, or a new term with a definition
- a reference to the document where the term is used

Unacceptable PRs
- updates to existing definitions

[A](#A) [B](#B) [C](#C) [D](#D)

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

# D

## DPoP Proof JWT
### [RFC 9449 §4](https://www.rfc-editor.org/rfc/rfc9449.html#name-dpop-proof-jwts)
DPoP introduces the concept of a DPoP proof, which is a JWT created by the client and sent with an HTTP request using the DPoP header field. Each HTTP request requires a unique DPoP proof.

A valid DPoP proof demonstrates to the server that the client holds the private key that was used to sign the DPoP proof JWT. This enables authorization servers to bind issued tokens to the corresponding public key (as described in Section 5) and enables resource servers to verify the key-binding of tokens that it receives (see Section 7.1), which prevents said tokens from being used by any entity that does not have access to the private key.

The DPoP proof demonstrates possession of a key and, by itself, is not an authentication or access control mechanism. When presented in conjunction with a key-bound access token as described in Section 7.1, the DPoP proof provides additional assurance about the legitimacy of the client to present the access token. However, a valid DPoP proof JWT is not sufficient alone to make access control decisions.

See also [Access Token](#Access_Token), [Bearer Token](#Bearer_Token)