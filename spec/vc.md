## Verifiable Credential
### Core Properties
| Field | Description | Reference |
| ---- | ---- | ---- |
| @context | https://w3c.github.io/vc-data-model/#contexts |
| id | VC identifier URI, machine readable description | https://w3c.github.io/vc-data-model/#identifiers |
| type | ["VerifiableCredential", ...], type of VC | https://w3c.github.io/vc-data-model/#types |
| credentialSubject | specify this VC is for which subject, must contains "id" property | https://w3c.github.io/vc-data-model/#credential-subject |
| issuer | VC issuer, a DISN DID | https://w3c.github.io/vc-data-model/#issuer |
| issuanceDate | VC issue timestamp | https://w3c.github.io/vc-data-model/#issuance-date |
| proof | VC signature | https://w3c.github.io/vc-data-model/#proofs-signatures |  

#### Proof Properties
| Field | Description | Reference |
| ---- | ---- | ---- |
| type | proof type, Ed25519Signature2018 | https://w3c-ccg.github.io/lds-ed25519-2020/#ed25519-signature-2020 |
| proofPurpose | purpose of VC | |
| verificationMethod | pub key URI of verifying signature ||
| created | timestamp | |
| jws | signature value (jws format) || 



### Basic VC Example
```
{
	"@context": "https://www.w3.org/2018/credentials/v1",
	"id": "https://credential.disn.cc/10001",
	"type": ["VerifiableCredential"],
	"credentialSubject": {
		"id": "did:example:d23dd687a7dc6787646f2eb98d0"
	},
	"issuer": "did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4",
	"issuanceDate": "2021-12-23T19:38:13Z",
	"proof": {
		"type": "Ed25519Signature2018",
		"proofPurpose": "assertionMethod",
		"verificationMethod": "did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4#z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4",
		"created": "2021-12-24T05:46:58.784Z",
		"jws": "eyJhbGciOiJFZERTQSIsImNyaXQiOlsiYjY0Il0sImI2NCI6ZmFsc2V9..crJrciE9GjMC6BEFNPm0QtEqAVZ4jqtoue4NwmTG6MGeBlrMlQs2t6_TfFYDwyX60buK7mXfEnjMsLOaTh0cDQ"
	}
}
```