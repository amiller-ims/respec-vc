# Verifiable Credentials for ReSpec

This ReSpec extension enhances the 
[Verifiable Credential](https://www.w3.org/TR/vc-data-model/) 
examples in your specification.

The [Verifiable Credentials](https://www.w3.org/TR/vc-data-model/) 
extension to the [ReSpec](https://respec.org/docs/#abstract) 
document authoring environment enables authors to express simple 
examples of [credentials](https://www.w3.org/TR/vc-data-model/#abstract) 
in their specification which are then enhanced by this extension to 
show the digitally signed forms of the credential. An example of the 
output of this extension is provided below (this extension adds the
tabs seen in the image below):

![image](https://user-images.githubusercontent.com/108611/142772916-03bafc46-c176-4673-b8b3-da19999dccd8.png)

# Usage

To use this extension, include the following line in your ReSpec file:

```html
<script class="remove" src="https://cdn.jsdelivr.net/gh/digitalbazaar/respec-vc@1.0.0/dist/main.js"></script>
```

Note that there might be releases later than the one listed above. 
Check this repository's [tags](https://github.com/digitalbazaar/respec-vc/tags) 
for all known releases.

# ReSpec Markup

To use this extension, you must add the `vc` class to your examples
and optionally provide a digital proof verification method (e.g., 
a URL to a public key) via the `data-vc-vm` attribute.

```html
<pre class="example nohighlight vc" title="Usage of the id property"
  data-vc-vm="https://example.edu/issuers/565049#key-1">
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://www.w3.org/2018/credentials/examples/v1"
  ],
  <span class="highlight">"id": "http://example.edu/credentials/3732"</span>,
  "type": ["VerifiableCredential", "UniversityDegreeCredential"],
  "issuer": "https://example.edu/issuers/565049",
  "issuanceDate": "2010-01-01T00:00:00Z",
  "credentialSubject": {
    <span class="highlight">"id": "did:example:ebfeb1f712ebc6f1c276e12ec21"</span>,
    "degree": {
      "type": "BachelorDegree",
      "name": "Bachelor of Science and Arts"
    }
  }
}
</pre>
```
