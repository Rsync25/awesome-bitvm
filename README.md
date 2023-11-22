# Awesome BitVM 💻

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
- 2WP for sidechains


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

## Videos

- [What is BitVM?](https://www.youtube.com/watch?v=XxqQU6j6jI8)
- [BitVM Intro: Create Logic Gates and Circuits in Python](https://www.youtube.com/watch?v=cnijtOVRwgg)

## Libraries

- [Bitcoin compiler in C++](https://github.com/maitrebitcoin/bitcoin-bitvm-compiler)
- [BitVM in Rust](https://github.com/BitVM/rust-bitcoin-scriptexec)
  
## Apps

- [BitLDC (Bitcoin Life/Death Certificate) Protocol](https://github.com/araujo88/BitLDC)

## Contributors

<a align="center" href="https://github.com/Rsyn25/awesome-bitvm/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Rsync25/awesome-bitvm" />
</a>
