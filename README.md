# Hello Beam

Beam is a sovereign network focused on gaming brought to you by the Merit Circle DAO. Powered by the established Avalanche network, Beam operates independently to cater towards gamers and game developers.


## Contributions
Beam is currently in a developer preview, and both the service and the documentation are work in progress. If you would like to contribute to the documentation, please open a pull request.


### TL;DR

If you would like to get your hands dirty without reading our documentation, we strongly advise you to get started with one of our implementations ready [SDKs](https://docs.onbeam.com/service/sdk). We currently provide SDKs for Node.js and C#, but are happy to facilitate more. If you are interested in an SDK for your implementation language which we don't provide yet, please open an [issue](https://github.com/Merit-Circle/beam-docs/issues/new).


## Getting started


```typescript
import { Beam } from '@onbeam/node';
 
const beam = new Beam('x-api-key');

const profile = await beam.profiles.createProfile('profileID');
// {
//   "id": "string",
//   "gameId": "string",
//   "externalId": "string",
//   "wallets": [
//     {
//       "id": "string",
//       "externalId": "string",
//       "address": "string",
//       "chainId": 0,
//       ...
//     }
//   ]
// }

const profiles =  await beam.profiles.getAllProfiles({
  offset: 0,
  limit: 10
});
```

In this example, we initialize an instance of Beam by passing your api key. We then proceed to create a Profile. A Profile is the Beam entity you'll be mostly interacting with. Each profile automatically gets assigned a wallet on the Beam blockchain.

---
**View full documentation and examples on [docs.onbeam.com](https://docs.onbeam.com).**


### Managing assets

Profiles are custodial, and through your api key you are able to transfer / trade and manage assets of the profiles of your users - for as long as the users are custodial. In late 2023, we're aiming to release a feature for users to take self-custody of their accounts, but you'll be in control of implementing the feature to allow them to take custody.

```typescript
import { Beam } from '@onbeam/node';
 
const beam = new Beam('x-api-key');

const transfer = await beam.assets.transfer({
  sender: 'ProfileID-A',
  receiver: 'ProfileID-B',
  assetAddress: '0x0',
  tokenId: 23
})
```
---
**View full documentation and examples on [docs.onbeam.com](https://docs.onbeam.com).**
