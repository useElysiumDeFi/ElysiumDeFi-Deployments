# ElysiumDeFi deployments

Contract addresses and deployment records for **ElysiumSwap** (DEX) and **ElysiumPad** (launchpad) on Elysium mainnet.

ElysiumSwap and ElysiumPad are independent projects built on Elysium. They are not affiliated with, or endorsed by, Elysium or Kinetiq.

## Network

| | |
|---|---|
| Chain | Elysium mainnet (Arbitrum Orbit, settles to HyperEVM) |
| Chain ID | `99901` |
| Gas token | HYPE |
| Public RPC | `https://rpc.elysiumswap.finance` |

## ElysiumSwap (DEX)

| Contract | Address | Block |
|---|---|---|
| WHYPE (canonical bridged WHYPE) | `0xbA876237B0F021A6c6D852d6c26E107997cC5E81` | – |
| V2 Factory | `0xC48C733F9cEaC05d79D0d583A15f3C68a14B8715` | 139223 |
| V2 Router | `0x194a77bCA0Ada3Eb15d7B3Af201AcA197dbE3B26` | 139243 |
| V3 Factory | `0x7266c0EcfF2A687B4Ad0Ead7B24840929540b697` | 139258 |
| V3 SwapRouter | `0x9fae201fa4c0740b1b92DebEcDDfFE74C1Ecd8b3` | 139338 |
| V3 QuoterV2 | `0xc256C98819BB29661Dd66e3DBCE3cA71875D8143` | 139352 |
| V3 NonfungiblePositionManager | `0xC6Dc519451F58dFd27bB2920EeFAe57597bd91f5` | 139381 |
| NFTDescriptor library | `0xa12bcdC89aBC39D28BDB305259C59D916735786f` | 139357 |
| NonfungibleTokenPositionDescriptor | `0xd2eaA286Ae7fc6DD4E65bCa59Cb2209D681BA3b0` | 139374 |
| Aggregator (cross-DEX split routing) | `0xD9106be99e93cC88A0c81522F416fF4e8394fe51` | 141305 |

## ElysiumPad (launchpad)

Instant launches (straight into a locked 1% ElysiumSwap v3 pool):

| Contract | Address | Block |
|---|---|---|
| ElysiumPadLauncher | `0x3318b09E6e4D222513D8fBCF76205b3c5566d76c` | 139422 |
| ElysiumPadLocker | `0xa83212Cac640Cb27005B956531c6cB251F14465C` | 139412 |
| ElysiumPadToken (implementation) | `0x4Bf70643c298a7c438f1cAcDBf1F71B041AEEE8E` | 139406 |
| ElysiumPadQuoter | `0xc730A76E6339A41Acf2D430264603484Fd592aC8` | 139431 |

Bonding-curve launches (graduate to an ElysiumSwap v2 pair):

| Contract | Address | Block |
|---|---|---|
| ElysiumPadCurveLauncher | `0xB7F444558A6Ae7ded39E859769bF4497D3FEfFC5` | 161259 |
| ElysiumPadTaxToken (implementation) | `0x8aFB6A16374520923a6749F32D7E722d0A16CfEa` | 161239 |
| ElysiumPadBondingCurve (implementation) | `0x5cF201Fda7771878FfC68958b2cC28A619421a92` | 161252 |

The contract source is at [useElysiumDeFi/ElysiumPad](https://github.com/useElysiumDeFi/ElysiumPad).

## Tokens

| Token | Address | Decimals |
|---|---|---|
| USDC (bridged from HyperEVM) | `0xb47c4C8F73F009CC0C0d3f92B388d13E293F0B65` | 6 |

## Ownership and fees

- Owner of every ownable contract, and recipient of protocol fees: `0x1c723Cf0451e6635C748283a3e87413079E7C198`.
- Deployer: `0xAFC6E333A176bcA7aA3043E1810a42ab82D01a1B`. It holds no roles after deployment.
- ElysiumSwap v2 protocol fee: on, 1/6 of the 0.3% swap fee.
- ElysiumSwap v3 protocol fee: set per pool, with a denominator of 6.
- Current settings can always be read on-chain from each contract.

## Files

`elysium-mainnet/addresses.json` holds every address above in one machine-readable file.

The other files are deployment records: each step's transaction hash, block, gas and resulting address.
- `elysium-mainnet/dex-and-pad.deploy.json`: ElysiumSwap v2/v3, ElysiumPad's instant-launch contracts, and the ownership handover.
- `elysium-mainnet/aggregator.deploy.json`: the Aggregator.
- `elysium-mainnet/pad-curve.deploy.json`: ElysiumPad's bonding-curve contracts and their configuration transactions.
