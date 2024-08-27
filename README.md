# Awesome BitVM 💻 🪙 ⚡

[![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)


![image](https://github.com/22388o/awesome-bitvm/assets/83122757/9015d3ec-fea9-497c-9c68-c0bd98221b86)

> A curated list of resources around  BitVM

**Contributions are welcome**

## About

BitVM is a computing paradigm to express Turing-complete Bitcoin contracts. This requires no changes to the network’s consensus rules.

Committing to a large program in a Taproot address requires significant amounts of off-chain computation and communication, however the resulting on-chain footprint is minimal. As long as both parties collaborate, they can perform arbitrarily complex, stateful off-chain computation, without leaving any trace in the chain. On-chain execution is required only in case of a dispute.

## Status Software

Currenctly BitVM is under development allows developers create bridges for now and some apps.

In the last update, BitVM now support [SHA256 script](https://github.com/BitVM/BitVM/pull/65)

[A PR from PayneJoe and Antalpha Labs reducing the size of the Groth16 verifier from ~4GB down to 2.9GB.](https://github.com/BitVM/BitVM/pull/83)


### Potential Use Case

- Complex smart contracts
- Prediction Markets
- Privacy
- Multisig
- 2WP for sidechains (Pegin and Pegout)
- Bridges (on-chain <> sidechain)
- Compatible with BIP-300/301
- Low cost
- Compatible with Groth16 and ZK
- Rollups

## Resources

- [BitVM Whitepaper](https://bitvm.org/bitvm.pdf)
- [BitVM Online](https://techmix.github.io/tapleaf-circuits/)
- [bitcoin-dev BitVM: Compute Anything on Bitcoin](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-October/021997.html)
- [BitVM Primer](https://github.com/twhit223/bitvm_primer)
- [BitVM Toy Implementation](https://github.com/BitVM/BitVM)
- [BitVM FAQ](https://github.com/PraiseTheMithra/BitVm-FAQ)
- [Simple Explanation of BitVM](https://github.com/fiksn/bitvm-explained)
- [BitVM and MATT](https://twitter.com/salvatoshi/status/1712772143753408824)
- [Script, Taproot and BitVM](https://x.com/mononautical/status/1713291840638599206?s=20)
- [Things bitvm needs](https://github.com/supertestnet/things-bitvm-needs)
- [BitVM vs RGB](https://stacker.news/items/294108)
- [Nand Game](https://nandgame.com/)
- [BitVM Illustrated](https://x.com/BTCillustrated/status/1712440417524810227?s=20)
- [BitVM Builders - Telegram group](https://t.me/bitVM_chat)
- [Bitcoin Script Interpreter](https://bitvm.github.io/BitVM/interpreter/)
- [BitVM and sCrypt](https://gist.github.com/msinkec/5827d5285a18de8930324f67b880841e)
- [STARK proof for BitVM circuit execution](https://github.com/neocarmack/STARK/)
- [BitVM in Spanish](https://docs.google.com/presentation/d/1vwWUP6PyDgZ4xh72fUouf5iBEZGuFLIF9-O5z5GUshs/edit?usp=drivesdk)
- [BitVM Transaction Graph](https://x.com/robin_linus/status/1740012153816715507?s=20)
- [Ultimate BitVM Guide](https://x.com/xverseApp/status/1745426619135901871?s=20)
- [Unnamed Noncustodial Inchoate Sidechains On Bitvm (Unisob)](https://gist.github.com/supertestnet/5f262c632cbcd00348824aad5c289705)
- [BitVM website](https://bitvm.org/)
- [BitVM Research](https://github.com/bitlayer-org/BitVM-Research)
- [BitVM 2: Permissionless Verification](https://bitvm.org/bitvm2)
- [BitVM bridge comparison table](https://gist.github.com/john-light/e0cf9ae8a3a68d0d8e80edb25585b64b)
- [Tree++](https://bitvm.org/treeplusplus.html)
- [BitVM2: Bridging Bitcoin to Second Layers](https://bitvm.org/bitvm_bridge.pdf)
  
## Tech Overview

BitVM operates on a simple yet powerful architecture involving two principal actors: the Prover and the Verifier. The Prover is the party that initiates a computation or claim, essentially saying, “Here’s a program, and here’s what I assert it will do or produce.” The Verifier, on the other hand, is responsible for validating that claim. This dual-role system enables a level of checks and balances, ensuring that the computational results are both accurate and trustworthy.

The ingenuity of BitVM lies in its handling of computational workloads. Unlike conventional blockchain operations, which put significant computational burdens on-chain, BitVM performs most of its complex calculations off-chain. This drastically reduces the amount of data that needs to be stored directly on the Bitcoin blockchain, enhancing efficiency and lowering costs. This off-chain methodology also provides greater speed and flexibility, as developers or users can run intricate programs or simulations without worrying about overwhelming the blockchain.

However, BitVM does employ on-chain verification when needed, especially in cases of disputes. Should the Verifier question the legitimacy of the Prover’s claim, the system will then refer to the unalterable, decentralised ledger of the Bitcoin blockchain to resolve the issue. This is accomplished through what are known as “Fraud Proofs.” 

If the Prover’s claim turns out to be false, the Verifier can submit a concise fraud proof to the blockchain, thereby exposing the dishonesty. This not only settles the dispute but also maintains the overall integrity of the system. By integrating both off-chain computations and on-chain verifications, BitVM has struck a balance that offers both computational efficiency and robust security.

Optimistic Rollups are a Layer 2 scaling solution for blockchains that enable more efficient computation and data storage by performing most operations off-chain while maintaining the same level of security as on-chain transactions. The fundamental idea is to assume that all transactions are correct (“optimistic”) unless proven otherwise. Only if a dispute arises is the relevant data and computation published and verified on the main blockchain. This significantly reduces the amount of data that has to be stored on-chain, thereby freeing up space and lowering transaction fees.

In BitVM, Optimistic Rollups can be particularly beneficial. Recall that BitVM primarily works with two parties: a Prover and a Verifier. Most of the computational work happens off-chain, reducing the amount of data that needs to be stored on the Bitcoin blockchain. When a transaction is initiated, BitVM can use Optimistic Rollups to bundle multiple off-chain transactions into a single on-chain transaction, further reducing the blockchain footprint.

Moreover, in the event of a dispute, BitVM’s use of fraud proofs dovetails well with the “challenge-response” system inherent in Optimistic Rollups. If the Prover makes a false claim, the Verifier can quickly expose the dishonesty by providing a succinct fraud proof. This fraud proof would then be scrutinised within the Optimistic Rollup framework, and if validated, the dishonest party would be penalised.

## BitVM Generations

Since BitVM gate, many developers joined into development of protocol. Follow below last generations:

![image](https://github.com/Rsync25/awesome-bitvm/assets/135646455/fbb09e3f-e6a0-4044-bda3-9c3cf0764a68)


## Articles

- [The Big Deal with BitVM: Arbitrary Computation Now Possible on Bitcoin Without a Fork](https://bitcoinmagazine.com/technical/the-big-deal-with-bitvm-arbitrary-computation-now-possible-on-bitcoin-without-a-fork)
- [BitVM: But Can It Run DOOM?](https://bitcoinmagazine.com/technical/bitvm-but-can-it-run-doom)
- [The Protocol: Bitcoin Might Get Ethereum-Style Smart Contracts Under ‘BitVM’ Plan](https://www.coindesk.com/tech/2023/10/11/the-protocol-bitcoin-might-get-ethereum-style-smart-contracts-under-bitvm-plan/?utm_medium=referral&utm_source=rss&utm_campaign=headlines)
- [BitVM: A Computational Revolution in Bitcoin](https://www.eddieoz.com/bitvm-a-computational-revolution-in-bitcoin/)
- [Bitcoin Smart Contracts and BitVM ](https://www.youtube.com/watch?v=oBb9NBxaMfs)
- [Is BitVM the Next Evolution for Smart Contracts on Bitcoin?](https://blog.bitfinex.com/education/is-bitvm-the-next-evolution-for-smart-contracts-on-bitcoin/)
- [Bitcoin’s Fifteen Years Of Evolution: A Look Beyond the Original Whitepaper ](https://bitcoinmagazine.com/technical/bitcoins-fifteen-years-of-evolution-a-look-beyond-the-original-whitepaper-)
- [Lightning Network explainer](https://lightningnetwork.plus/posts/450)
- [Base58 explainer](https://twitter.com/base58btc/status/1711728898730242112)
- [BitVM Slides by Cartesi](https://web3.link/BitVmAndZK_ZkWarsaw.pdf)
- [Deep dive into BitVM -Computing paradigm to express Turing-complete Bitcoin contracts](https://medium.com/crypto-garage/deep-dive-into-bitvm-computing-paradigm-to-express-turing-complete-bitcoin-contracts-1c6cb05edfca)
- [Bitcoin BitVM: What is it?, exactly?](https://www.kraken.com/learn/what-is-bitcoin-bitvm)
- [What is BitVM? And why does it matter to rollups?](https://www.bitcoinrollups.io/bitvm)
- [2024 Crypto Market Outlook by Coinsbase Institutional](https://coinbase.bynder.com/m/c8c6fdc663f44b5/original/2024-Crypto-Market-Outlook-V3.pdf)
- [Introduce sCrypt: a Layer-1 Smart Contract Framework for BTC](https://xiaohuiliu.medium.com/introduce-scrypt-a-layer-1-smart-contract-framework-for-btc-b8b39c125c1a)
- [Exploring the Landing Paths for Bitcoin Layer 2 Ecosystem](https://wublock.substack.com/p/exploring-the-landing-paths-for-bitcoin)
- [Bits, Booleans, Battlestar Galactica](https://docs.google.com/presentation/d/1vwWUP6PyDgZ4xh72fUouf5iBEZGuFLIF9-O5z5GUshs/edit#slide=id.p)
- [Experiment of BitVM White Paper](https://bitlayerlabs.notion.site/Experiment-of-BitVM-White-Paper-ef87e719001e4e2d83765c68f1bb8443)
- [The Spectre of MEV on Bitcoin](https://cyber.fund/content/the-spectre-of-mev-on-bitcoin)
- [BitVM 2: Opening Up The Playing Field](https://bitcoinmagazine.com/technical/bitvm-2-opening-up-the-playing-field)
- [What is BitVM? Exploring Bitcoin's latest scalability solution](https://www.okx.com/learn/what-is-bitvm-exploring-bitcoins-latest-scalability-solution)
- [What is Bitcoin BitVM?](https://www.coinbase.com/en-br/learn/crypto-glossary/what-is-bitcoin-bitvm)
- [BitVM Explained: In-Depth Guide to Smart Contracts on Bitcoin](https://blog.rootstock.io/noticia/bitvm-explained-guide-to-smart-contracts-on-bitcoin/)
- [The Future of Bitcoin #3: Scaling Bitcoin](https://www.binance.com/en/research/analysis/the-future-of-bitcoin-3-scaling-bitcoin)
- [Using Logic Gates to Build Smart Contracts with Taproot Wallets: Case of BitVM](https://medium.com/coinmonks/using-logic-gates-to-build-smart-contracts-with-taproot-wallets-case-of-bitvm-db0f1f2b5bb5)
- [BitVM Bridge and OP-DLC (Part1) : Next Generation of Bitcoin Layer2 Bridges](https://medium.com/@btceden/bitvm-bridge-and-op-dlc-part1-next-generation-of-bitcoin-layer2-bridges-15748efab9d1)
- [Latest Innovations in BitVMX](https://bitvmx.org/post-1-0d6009hx638d305a)
- [Is BitVM Better or Worse than then Lightning Network?](https://www.publish0x.com/cryptoeq/is-bitvm-better-or-worse-than-then-lightning-network-xmjwlvl)
- [BitVM: A Computational Revolution in Bitcoin](https://www.eddieoz.com/bitvm-a-computational-revolution-in-bitcoin/)
- [Bitvm To Become The First Layer-2 On Bitcoin?](https://medium.com/@thecoinrepublic01/bitvm-to-become-the-first-layer-2-on-bitcoin-1613b529278d)
- [BitVM explained in 4 slides](https://x.com/BTCillustrated/status/1712440417524810227)
- [Optimizing Algorithms for Bitcoin Script](https://bitvmx.org/knowledge/optimizing-algorithms-for-bitcoin-script)
- [BitVM becomes pratical](https://blog.bitlayer.org/BitVM_Bridge_Becomes_Practical/)
- [Interactive SNARK Verification on Bitcoin using BitVMX](https://bitvmx.org/knowledge/interactive-snark-verification-on-bitcoin-using-bitvmx)
- [Introduction to BitVM](https://medium.com/coinmonks/introduction-to-bitvm-d483916d39c4)
- [What You Should Know About BitVM](https://blockspace.media/podcast/what-you-should-know-about-bitvm/)
- [Bitcoin sidechain creators tout new ‘permissionless’ version BitVM2](https://cointelegraph.com/news/bitcoin-sidechain-creators-tout-new-permissionless-version-bitvm2)
- [BitVM Version 2 Introduces New Era for Bitcoin L2 Scaling Solutions](https://news.bitcoin.com/bitvm-version-2-introduces-new-era-for-bitcoin-l2-scaling-solutions/)
- [BitVM2: A New Era May Be Dawning for the Bitcoin Ecosystem](https://inbitcoinwetrust.substack.com/p/bitvm2-a-new-era-may-be-dawning-for)
- [Alphen Labs made in verifying field multiplications in Script, which reduce the SNARK verifier script used in BitVM by over 1.2 GB.](https://x.com/AlpenLabs/status/1827004881754034680)
  
## Videos

- [What is BitVM?](https://www.youtube.com/watch?v=XxqQU6j6jI8)
- [BitVM Intro: Create Logic Gates and Circuits in Python](https://www.youtube.com/watch?v=cnijtOVRwgg)
- [BitVM 8 bit CPU: Write Bitcoin programs in Assembly](https://www.youtube.com/watch?v=lQ9agL725G0)
- [Demo of Robin Linus's implementation of bitvm](https://youtu.be/7sRqzoZorn0)
- [BitVM 8 bit CPU: Assembly Quirks](https://youtu.be/MjCyTT-Wpzg)
- [ How bitvm works: from logic gates to an 8bit cpu for bitcoin](https://www.youtube.com/watch?v=IRU83gRcw3Y)
- [S15 E13: Robin Linus on BitVM & Permissionless Bitcoin Development](https://www.youtube.com/watch?v=Defp4sX7eEc)
- [Robin Linus on BitVM](https://brink.dev/blog/2024/01/16/eng-call-bitvm/)
- [BitVM: A Tool for Smarter Smart Contracts](https://www.youtube.com/watch?v=iEM_txmJYxA)
- [Bitvm Crash Course](https://www.youtube.com/watch?v=_Met2lUO0P0)
- [Workshops Casa21 - BitVM: Bitcoin Smart Contracts With Rich State](https://www.youtube.com/watch?v=LwH9fhY4uGA)
- [BitVM: Smarter Bitcoin Contracts - Robin Linus (zerosync)](https://www.youtube.com/live/VIg7BjX_lJw?si=JeyhKppb2lmH2kRN)
- [BitVM: The Holy Grail for Bitcoin? | Creator Robin Linus](https://www.bankless.com/bitvm-robin-linus)
- [S15 E43: Sergio Demian Lerner on BitVMX & Layer 2s](https://www.youtube.com/watch?v=LWy0VI2Eemw)
- [Episode 328 - ZK on Bitcoin with Alpen Labs](https://www.youtube.com/watch?v=E0rBr9ED50s)
- [Why BitVM & BItcoin L2s are Inevitable](https://www.youtube.com/watch?v=8i7dw55H_9Q)
- [Bitvm By Liam Eagen](https://www.youtube.com/watch?v=QKBObsLzBE8)
- [Unlocking Bitcoin's Potential: How Rootstock Uses EVM For Scalability](https://www.youtube.com/watch?v=wQ8JmmtjkT8)
- [Chat_86 - Everything on Bitcoin with Robin Linus & Super Testnet](https://rumble.com/v55b2lo-chat-86-everything-on-bitcoin-with-robin-linus-and-super-testnet.html?e9s=src_v1_finance)
- [What Is BitVM And Does It Allow Rollups On Bitcoin?](https://www.youtube.com/watch?v=C4tQjgAL5hI)
- [BitVM - Bitcoin Asia 2024](https://youtu.be/LEvWi6IjGsU)
- [MIT Bitcoin Expo 2024: Scaling Up - BitVM (Robin Linus)](https://www.youtube.com/watch?v=nhR_g9hPnqM)
- [MIT Bitcoin Expo 2024: Scaling Up-Covenant Panel w Roose (Ark), Linus (BitVM) & Sabouri (Botanix)](https://www.youtube.com/watch?v=TKrXjGTIbx8)
- [Interactive SNARK Verification on Bitcoin using BitVMX](https://www.youtube.com/watch?v=ysXlM_0yAFs)
- [Second layers and other projects on top of bitcoin](https://braiins.com/blog/second-layers-and-other-projects-on-top-of-bitcoin)
- [BitVM2 Explained with Alexei Zamyatin](https://www.youtube.com/watch?v=aOlPZ0o1UEY)

## Libraries

- [Bitcoin compiler in C++](https://github.com/maitrebitcoin/bitcoin-bitvm-compiler)
- [BitVM Toy Implementation](https://github.com/BitVM/bitvm-js)
- [BitVM in Rust](https://github.com/BitVM/BitVM)
- [LogicGates: Logical gates in Python for different scenarios on BitVM (Phython)](https://github.com/mcbagz/LogicGates)
- [SHA256 WASM](https://github.com/BitVM/sha256)
- [BLAKE3 WASM](https://github.com/BitVM/blake3)
- [RIPEMD160 WASM](https://github.com/BitVM/ripemd160)
- [Elftrace](https://github.com/halseth/elftrace)
- [rv32i to BitVM](https://github.com/zippiehq/rv32i-to-bitvm)
- [Toy BitVM RS](https://github.com/chainwayxyz/toy-bitvm-rs)
- [Tapleaf Circuits](https://github.com/supertestnet/tapleaf-circuits)
- [BitVM Workshop](https://github.com/supertestnet/bitvm-workshop)
- [BitVM Groth16 Verifier Toolkit - WIP](https://github.com/chainwayxyz/bitvm-zk-verifier)
- [Plonky2 Experiments](https://github.com/BitVM/zkCoins)
- [Bitcoin Script interpreter implemented in Rust](https://github.com/BitVM/rust-bitcoin-scriptexec)
- [rust-bitcoin-m31-or-babybear](https://github.com/BitVM/rust-bitcoin-m31-or-babybear)
- [BitVM in Phython](https://github.com/krutt/bitvm)
- [BitVM Circom Example in Java](https://github.com/BitVM/bitvm-circom-example)
- [BitVM Macros](https://github.com/BitVM/BitVM_macros)
- [ZkCoins](https://github.com/BitVM/zkCoins)
- [Bitvm Groth16 Verifier](https://github.com/zulu-network/bitvm-groth16-verifier)
- [BitVMX CPU](https://github.com/FairgateLabs/BitVMX-CPU)
- [Rust Bitcoin Script Stack](https://github.com/FairgateLabs/rust-bitcoin-script-stack)

# Apps

- [BitLDC (Bitcoin Life/Death Certificate) Protocol](https://github.com/araujo88/BitLDC)
- [ASM to Bin](https://magical-frangipane-149aba.netlify.app/compiler)
- [Bitstake: A proof of stake bridge based on BitVM](https://lightco.in/2024/02/13/bitstake/)
- [Citrea's BitVM Based Trust-Minimized Two-Way Peg Program](https://github.com/chainwayxyz/clementine)
- [BitVMX](https://bitvmx.org/)
- [Alpen Labs](https://www.alpenlabs.io/blog/snarknado-practical-round-efficient-snark-verifier-on-bitcoin)
- [KNC](https://github.com/BTCapsule/knc)
- [Bitlayer](https://www.bitlayer.org/)
- [Zulu Network](https://zulunetwork.io/)

## BitVM project VS Companies use "BitVM"

[The BitVM project does not endorse any company](https://x.com/robin_linus/status/1794698802731077764)

## Extra lists

- [BitVM website](https://bitvm.org/)

## Disclaimer

Authors of this list is not responsible for eventual issues with third party projects be trading, speculation or any other thing.

Please do your own research

## Donations

[Rsync](https://tourniquet.app/donate/Rsync)

## Contributors

<a align="center" href="https://github.com/Rsyn25/awesome-bitvm/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Rsync25/awesome-bitvm" />
</a>
