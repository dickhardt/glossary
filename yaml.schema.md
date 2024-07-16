
## Schema

Each term in the glossary is represented by a single YAML document. An example document follows, with more detailed
explanation of each component below.

```yaml
term: Glossary # The term itself. Must not be empty, and must be unique within the glossary.
draft-definitions: # A list of draft RFC's which make use of this term, but have not yet settled on a definition.
  - url: https://foo.bar/some-draft-location
    sdo: none
    label: ietf-draft-oauth2-party-pants-1
  - url: https://foo.bar/some-other-draft-location
    sdo: ietf
    label: ietf-draft-oauth2-rubber-boots-4
definitions: # A list of definitions from published RFC's, as well as the documents that make use of them.
  - id: 1 # An incrementing identifier used to uniquely identify a specific definition for a glossary term.
    source: ## Link type
      url: https://tools.ietf.org/html/rfc6749
      sdo: ietf
      label: rfc-6749 # The source of this definition.
    text: |
      this is a definition that makes use of yaml's multi-line parsing. It contains 
      the text of the definition, as agreed upon by the authors of the published RFC.
    references: # A list of RFC's that make use of this definition of the term, which are not the origin.
      - url: https://www.rfc-editor.org/rfc/rfc8628.txt
        label: OAuth2
        sdo: ietf
      - url: https://ietf.org/rfc/rfc8693.txt
        label: Token Exchange RFC-8693
        sdo: ietf
      - url: https://www.ietf.org/archive/id/draft-ietf-oauth-transaction-tokens-02.txt
        label: Transaction Tokens
        sdo: ietf
    see-also: # A list of glossary terms within this glossary, and the associated definition.
      - term: Access Token
        id: 3
      - term: Id Token
        id: 1
```

### Links to Documents
Links to other documents are used in the `draft-definitions` and `definitions` sections. Each link has three components:

- `url`: The URL of the document. This must be a valid URL, and should point to the specific document that uses the term.
- `sdo`: The standards development organization that published the document. This is an enum eg. [`ietf`,`w3c`,`oidc`,`iso`,`oasis`] etc. 
- `label`: The label of the document, as it is commonly referred to. This is a string, and can be any value.

Note that, given certain standards organizations, the url may have special meaning. For example, the source of truth
for IETF RFC's is `https://rfc-editor.org/rfc/`, and the label is the RFC number.

### Links to Terms

Links to other glossary terms are used in the `see-also` section, and are formatted as a list of terms with two components:
- `term`: The term itself, as it appears in the `term` field of the glossary document.
- `id`: The unique identifier of the definition within the glossary term. This allows for cross-referencing of terms.

## FAQ

Q1: Why YAML?
- Easy to process, widely used, good for representing the metadata. As each definition is just a term with one or more definitions and associated metadata, YAML provides all the required functionality.

Q2: Why not markdown?
- Markdown is good for documents. (we are using it for this document!) It is not great for metadata. 

Q3: Why not XML?
- Umm ... how do I answer that politely?
