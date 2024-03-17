# Awesome BitVM 💻 🪙 ⚡

[![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)


![image](https://github.com/22388o/awesome-bitvm/assets/83122757/9015d3ec-fea9-497c-9c68-c0bd98221b86)

A curated list of resources around  BitVM

## About

BitVM is a computing paradigm to express Turing-complete Bitcoin contracts. This requires no changes to the network’s consensus rules.

Committing to a large program in a Taproot address requires significant amounts of off-chain computation and communication, however the resulting on-chain footprint is minimal. As long as both parties collaborate, they can perform arbitrarily complex, stateful off-chain computation, without leaving any trace in the chain. On-chain execution is required only in case of a dispute.

### Potential Use Case

- Complex smart contracts
- Prediction Markets
- Privacy
- Multisig
- 2WP for sidechains (Pegin and Pegout)
- Bridges
- Compatible with BIP-300/301
  


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

## Tech Overview

BitVM operates on a simple yet powerful architecture involving two principal actors: the Prover and the Verifier. The Prover is the party that initiates a computation or claim, essentially saying, “Here’s a program, and here’s what I assert it will do or produce.” The Verifier, on the other hand, is responsible for validating that claim. This dual-role system enables a level of checks and balances, ensuring that the computational results are both accurate and trustworthy.

The ingenuity of BitVM lies in its handling of computational workloads. Unlike conventional blockchain operations, which put significant computational burdens on-chain, BitVM performs most of its complex calculations off-chain. This drastically reduces the amount of data that needs to be stored directly on the Bitcoin blockchain, enhancing efficiency and lowering costs. This off-chain methodology also provides greater speed and flexibility, as developers or users can run intricate programs or simulations without worrying about overwhelming the blockchain.

However, BitVM does employ on-chain verification when needed, especially in cases of disputes. Should the Verifier question the legitimacy of the Prover’s claim, the system will then refer to the unalterable, decentralised ledger of the Bitcoin blockchain to resolve the issue. This is accomplished through what are known as “Fraud Proofs.” 

If the Prover’s claim turns out to be false, the Verifier can submit a concise fraud proof to the blockchain, thereby exposing the dishonesty. This not only settles the dispute but also maintains the overall integrity of the system. By integrating both off-chain computations and on-chain verifications, BitVM has struck a balance that offers both computational efficiency and robust security.

Optimistic Rollups are a Layer 2 scaling solution for blockchains that enable more efficient computation and data storage by performing most operations off-chain while maintaining the same level of security as on-chain transactions. The fundamental idea is to assume that all transactions are correct (“optimistic”) unless proven otherwise. Only if a dispute arises is the relevant data and computation published and verified on the main blockchain. This significantly reduces the amount of data that has to be stored on-chain, thereby freeing up space and lowering transaction fees.

In BitVM, Optimistic Rollups can be particularly beneficial. Recall that BitVM primarily works with two parties: a Prover and a Verifier. Most of the computational work happens off-chain, reducing the amount of data that needs to be stored on the Bitcoin blockchain. When a transaction is initiated, BitVM can use Optimistic Rollups to bundle multiple off-chain transactions into a single on-chain transaction, further reducing the blockchain footprint.

Moreover, in the event of a dispute, BitVM’s use of fraud proofs dovetails well with the “challenge-response” system inherent in Optimistic Rollups. If the Prover makes a false claim, the Verifier can quickly expose the dishonesty by providing a succinct fraud proof. This fraud proof would then be scrutinised within the Optimistic Rollup framework, and if validated, the dishonest party would be penalised.

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
  
## Apps

- [BitLDC (Bitcoin Life/Death Certificate) Protocol](https://github.com/araujo88/BitLDC)
- [ASM to Bin](https://magical-frangipane-149aba.netlify.app/compiler)
- [Citrea](https://www.blog.citrea.xyz/)
- [Bitstake: A proof of stake bridge based on BitVM](https://lightco.in/2024/02/13/bitstake/)

## Extra lists

- [BitVM website](https://bitvm.org/)

## Contributors

<a align="center" href="https://github.com/Rsyn25/awesome-bitvm/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Rsync25/awesome-bitvm" />
</a>
