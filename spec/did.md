## DISN DID Specification  
### 1. DID Define
    
```did:disn:<method-specific-string>```  

```disn``` is fixed did method  
```<method-specific-string> = HEX-encoded Ed25519 public key```  

For example：```did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4```  

### 2. DID Document Define 
#### 2.1 Core Properties  
|  Field | Description | Reference |
|  ----    | ---- | ---- |
| @context | [https://w3id.org/did/v1,<br> additional context define(url or JSON LD)]|
| id | did string value | https://w3c.github.io/did-core/#dfn-id |
| verificationMethod | pub keys which can verify did subject related signature | https://w3c.github.io/did-core/#dfn-verificationmethod |
| authentication | did document controllers, normally is did self | https://w3c.github.io/did-core/#dfn-authentication |
| assertionMethod | used to verify VC, normally point to did verificationMethod | https://w3c.github.io/did-core/#dfn-assertionmethod |
| created | metadata, document create timestamp | https://www.w3.org/TR/did-spec-registries/#created |
| updated | metadata, docuemnt updated timestamp | https://www.w3.org/TR/did-spec-registries/#updated |
| service | service endpoints collection, describe did related capabilities | https://w3c.github.io/did-core/#dfn-service |

#### 2.2 verificationMethod
| Field | Description | Reference |
| ---- | ---- | ---- |
| id |  method id | |
| type | Ed25519VerificationKey2018 | https://w3id.org/security#Ed25519VerificationKey2018 |
| controller | owner of method, normally be did self | |
| publicKeyJwk | verification material, JWK public key | https://w3id.org/security#publicKeyJwk |

#### 2.3 service
| Field | Description | Reference |
| ---- | ---- | ---- |
| type | service type | |
| serviceEndpoint | service endpoint url | |

#### DISN DID Document Example
```
{
  "@context": [
    "https://www.w3.org/ns/did/v1",
    {
      "Ed25519VerificationKey2018": "https://w3id.org/security#Ed25519VerificationKey2018",
      "publicKeyJwk": {
        "@id": "https://w3id.org/security#publicKeyJwk",
        "@type": "@json"
      }
    }
  ],
  "id": "did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4",
  "verificationMethod": [
    {
      "id": "did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4#z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4",
      "type": "Ed25519VerificationKey2018",
      "controller": "did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4",
      "publicKeyJwk": {
        "kty": "OKP",
        "crv": "Ed25519",
        "x": "02HF6QNEr2mksfYtTJMgzYo57phJ2h7SNwPBCQTeh70"
      }
    }
  ],
  "authentication": [
    "did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4#z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4"
  ],
  "assertionMethod": [
    "did:disn:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4#z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4"
  ],
  "service": [{
    "type": "OttWalletProvider",
    "serviceEndpoint": "https://wallet.ott.com/service"
  }],
  "created": "2021-12-20T17:00:00Z",
  "updated": "2021-12-20T17:00:00Z"
}
```



