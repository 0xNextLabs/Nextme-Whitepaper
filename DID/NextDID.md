# Next DID
## Abstract
Next DID is a Decentralized Identity created by Nextme to the user, the format is as follows:
> did:next:ceNobbK6Me9F5zwyE3MKY88QZLw

Its corresponding json structure is as follows:
```
{
  "@context": "https://nextme.one/did/v1/create",
  "publicKey": [
    {
      "id": "#keys-1",
      "type": "Secp256k1",
      "publicKeyHex": "02b97c30de767f084ce3080168ee293053ba33b235d7116a3263d29f1450936b71"
    },
    {
      "id": "#keys-2",
      "type": "Secp256k1",
      "publicKeyHex": "4b4042665b3235a12fb49730ff620fef1c96e9efa5c90119abd2e8acfe856053"
    }
  ],
  "authentication": ["#key-1"],
  "recovery": ["#key-2"]
}
```
## Next DID
#### DID Creation
##### Process
1. Generate two pairs of public and private keys as master and backup.
2. Generate user's Json data
3. Implement sha256 to Json
4. Implement the above result again with ripemd160
5. Implement base58 on the above result
6. Add did:next: before the above result as the final Next DID
##### Request
Mock version:
```
{
    "did": "did:next:3CzQLF3qfFVQ1CjGVzVRZaFXrjAd",
    "document": {
        "@context": "https://nextme.one/did/v1/create",
        "id": "did:next:3CzQLF3qfFVQ1CjGVzVRZaFXrjAd",
        "version": 1,
        "created": "2019-10-23T09:14:17.961Z",
        "updated": "2019-10-23T09:14:17.961Z",
        "publicKey": [
            {
                "id": "did:ccp:3CzQLF3qfFVQ1CjGVzVRZaFXrjAd#key-1",
                "type": "Secp256k1",
                "publicKeyHex": "0440b3fa8e848297ff26b04088263101fa87d3541ac48bbc32fe7b77b73246578241236ab6097d4012ac17a514272a54a7b728790e914bbbff431e49d421aa1eef"
            },
            {
                "id": "did:ccp:3CzQLF3qfFVQ1CjGVzVRZaFXrjAd#key-2",
                "type": "Secp256k1",
                "publicKeyHex": "04df4cf82984c9ecd4cf113e24762fb4404c1653df84ac424e4e2985ba7eb4de9249c2609414a24feea7845649299049b4babd6380ee69ef9e91c843931c877e7f"
            }
        ],
        "authentication": [
            "did:next:3CzQLF3qfFVQ1CjGVzVRZaFXrjAd#key-1"
        ],
        "recovery": [
            "did:next:3CzQLF3qfFVQ1CjGVzVRZaFXrjAd#key-2"
        ],
        "proof": {
            "type": "Secp256k1",
            "creator": "did:ccp:3CzQLF3qfFVQ1CjGVzVRZaFXrjAd#key-1",
            "signatureValue": "3045022100ff51c2629c9eb5d75d9786506ad45e82a87bf91b991a4b37f6d81ce70984220302201f4aa4f609a7ff96de190db68a25603fc849f1098d3f506098dc79af826b4a67"
        }
    },
    "operation": "create",
    "timestamp": 253146316
}
```
#### DID Read
##### Process
For example, your did is: `did:next:cxxxxxxxxxxxxxx`, run this command
> curl https://nextme.one/did/v1/read/did:next:cxxxxxxxxxxxxxx
And you'll get the result as below
##### Result
```
{
  "code": 0,
  "message": "ok",
  "requestId": "",
  "content": {
    "didDocument": {
      "@context": "https://nextme.one/did/v1",
      "id": "did:next:cxxxxxxxxxxxxxx",
      "version": 2,
      "created": "2022-10-21T11:12:13.065Z",
      "updated": "2022-10-21T11:17:49.379Z",
      "publicKey": [
        {
          "id": "did:next:cxxxxxxxxxxxxxx#key-1",
          "type": "Secp256k1",
          "publicKeyHex": "046fcbedd1107ca45be3e81fc445e5a366886a89e7087fe3d128e6236302f31594740f250433ebe9f0abcbd04dbf9c5979e270a0772ad1cc502cec2d5de9504c8c"
        },
        {
          "id": "did:next:cxxxxxxxxxxxxxx#key-2",
          "type": "Secp256k1",
          "publicKeyHex": "0496712d16b0836684aacd5ab6ba3d489c35efa31f414a1c6a455fc6b37ff28e5fa97ac29c1021b76e5b78e2bbceac1dfc4ec98e6b2b3e65a29f7f1cd4944dfb93"
        }
      ],
      "authentication": ["did:next:cxxxxxxxxxxxxxx#key-1"],
      "recovery": ["did:next:cxxxxxxxxxxxxxx#key-2"],
      "proof": {
        "type": "Secp256k1",
        "creator": "did:next:cxxxxxxxxxxxxxx#key-1",
        "signatureValue": "30440220211ffc76ae2858d6baa29faa9b576d6b2e048e8f4f7767ee1c2fba7ae6c2a78102205f5b56cd1431830b45109d716631638d961e5b252c2c2354d8bb96782d8a62ef"
      }
    }
  }
}
```
#### DID Update
It is worth mentioning that old versions of DID document are still stored on the chain due to the natures of the data structure used by blockchain. So this operation is not updating the DID document in place but putting a new version over the existing one.
#### DID Revoke
##### Request
```
{
    "did": "did:next:cxxxxxxxxxxxxxx",
    "operation": "delete",
    "timestamp": 253146316,
    "signature": "212w6nedqdm2wdp2dpdkasxkapp12kw12w12w"
}
```
## DID Authentication Flow

## Uses Cases

## APIs