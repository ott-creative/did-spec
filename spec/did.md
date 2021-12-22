## OTT DID Specification  
### 1. DID Define
    
```did:ott:<method-specific-string>```  

```ott``` is fixed did method  
```<method-specific-string> = HEX-encoded Ed25519 public key```  

For example：```did:ott:z6MktgQYKEkMYgQpHJMEsQ8hgWnGPDM6ZoVZHneZhoqTGDW4```  

### 2. DID Document Define  
|  Field | Description |
|  ----    | ---- |
| @context | [https://w3id.org/did/v1,<br> additional context define(url or JSON LD)]|
| id | did string value |
| verificationMethod | pub keys which can verify did subject related signature |
| authentication | did document controllers, normally is did self |
| assertionMethod | used to verify VC, normally point to did verificationMethod |
| created | metadata, document create timestamp |
| updated | metadata, docuemnt updated timestamp |
| service | service endpoints collection, describe did related capabilities |  




