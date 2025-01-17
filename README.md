# Program Examples

### :space_invader: Welcome, Solana Developer. :space_invader:   
   
Do you ever think to yourself: *"OK, but how do I do this on-chain?"*   
   
Or maybe you're in a hackathon right now, the clock's ticking, and you need to get a program off the ground *fast*.   
   
We present to you this list of curated examples for a wide range of use cases implemented using **on-chain programs**.   
   
### :link: All on-chain. :crab: All Rust. :muscle: All the time. 

## Some Basic Concepts to Know
Most system-level operations on Solana involve already-existing Solana programs.   
   
For example, to create a **system account** you use the **system program** and to create a **token mint** you use the **token program**.   
   
So, you'll notice that these operations are in fact conducting what's called a **cross-program invocation** - which is a fancy way of saying it calls other Solana programs to do business. You can see this in action whenever you see `invoke` or `invoke_signed` in the `native` examples, or `CpiContext` in the `anchor` examples.   
   
Deciding when to use cross-program invocation instead of invoking the programs directly from the client is completely up to you as the builder. It depends on how your application is designed.
- Maybe you want to add some checks - such as minimum balance required, allowed ownership, etc.
- Maybe you want to assert that an account has a certain data type.
- Perhaps you want to send only one transaction from your client for a handful of sequential operations.
- The list goes on.
Regardless of what you may want to add on top of existing Solana programs, the number one use case for writing your own program is for using accounts with a **Program Derived Address (PDA)**. Crack open the `pdas` folder to see why.

## Navigating this Repo

:blue_book: This collection is organized into the following sections:
- `program-basics` - The basics of writing Solana programs in Rust.
- `accounts`- Examples of creating & modifying accounts from on-chain.
- `tokens` - Examples of working with SPL Tokens from on-chain.
- `nfts` - Examples for various NFT use cases (including MetaPlex).
- `pdas` - Everything you need to know about working with Program Derived Addresses & program-owned accounts.
- `advanced-pdas` - Common Web2 design patterns implemented with PDAs on Solana.

:file_folder: Each example contains two folders:
- `native` - Written using Solana's native Rust crates and vanilla Rust.
- `anchor` - Written using Anchor's `anchor_lang` Rust crate and the associated Anchor framework to build & deploy.

:wrench: How to build & run:
- Before running anything in any folder make sure you pull in the dependencies with `yarn install`.
- `native` - Use `cicd.sh` to build & deploy the program. Run `yarn run test` to test it.
- `anchor` - Use `anchor build && anchor deploy` to build & deploy the program. Run `anchor run test` to test it.

## To-Do:
:mag: *Got something you want to see here? Add it to the list. Or better yet, write one & create a PR!*
- ### [x] Program Basics
- [x] 1. Hello Solana
- [x] 2. Custom instruction data
- [x] 3. Recommended program layout
- ### [ ] Accounts
- [x] 1. Creating a system account
- [x] 2. Rent
- [x] 3. Transferring SOL
- [ ] 4. Transferring an account's ownership
- [ ] 5. Destroying an account
- ### [ ] Tokens
- [x] 1. Creating an SPL Token
- [x] 2. Mint tokens to a wallet
- [ ] 3. Transferring tokens between wallets
- ### [ ] NFTs
- [x] 1. Creating an NFT
- [ ] 2. Transferring an NFT
- [ ] 3. Selling an NFT
- [ ] 4. NFT metadata expanded
- ### [ ] PDAs
- [ ] 1. A simple PDA
- [ ] 2. Dynamic PDA creation
- ### [ ] Advanced PDAs
- [ ] 1. Twitter
- [ ] 2. Amazon
- [ ] 3. OpenSea
