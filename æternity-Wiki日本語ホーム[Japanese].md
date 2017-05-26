## Whitepaper日本語版（未完）
- [Whitepaper (Japanese)](Whitepaper_Japanese)

## æternity関連サイトまとめ(日本語)

[æternity関連サイトまとめ(日本語)](https://github.com/aeternity/wiki/wiki/%C3%86ternity%E9%96%A2%E9%80%A3%E3%82%B5%E3%82%A4%E3%83%88%E3%81%BE%E3%81%A8%E3%82%81(%E6%97%A5%E6%9C%AC%E8%AA%9E))

<a href="http://www.aeternity.com/"><img width="160px" src="http://www.aeternity.com/user/themes/aeon/img/aeternity_logo.png" align="left" hspace="10" vspace="10"></a>

<p align = right><a target="_blank" href="https://twitter.com/intent/tweet?original_referer=https%3A%2F%2Fabout.twitter.com%2Fresources%2Fbuttons&text=Aeternity:%20scalable%20smart%20contracts%20interfacing%20with%20real%20world%20data&tw_p=tweetbutton&url=http%3A%2F%2Fwww.aeternity.com%2F&via=aetrnty"><img src="http://s30.postimg.org/j2q6ql27h/Tweet.png"></a>
<a target="_blank" href="https://twitter.com/aetrnty"> <img src="https://s24.postimg.org/4xcf9j8xh/Follow-_Twitter.jpg?2"></a>
</p>
<b>æternity ブロックチェーン – 機能的なオラクルマシーン<p>

æternityは[[Ethereum]]ネットワークをベースに作られた非常にスケーラブルなブロックチェーンプロトコルです。æternityは[[コンセンサスメカニズム]]を多重使用しないので、[[オラクル]]をチェックするのに利用できるユニークなコンセンサスメカニズムを利用することができます。 [[ステートチャネル]]はスケーラビリティとプライバシーを最大化するために実装されてます。チャネルの[[トークン]]は、オラクルの結果にアクセスできる機能的な[[スマートコントラクト]]を使用し、送受信することができます。æternityはスマートコントラクトの高速化や簡易化を実現します。なぜならスマートコントラクトの機能になんら悪影響もなく、ブロックチェーン、すなわちオンチェーン上にコントラクトコードやその状態を記録する必要もないからです。 <p>

[[ホワイトペーパー]]はæternityのアーキテクチャとポテンシャルとユースケースについて紹介するために公開されました。 æternityは[[予測市場]]と[[総合的な資産]]に関することを世界規模で動かすことができます。 <p>

<b>どのようにしてæternityブロックチェーンはスマートコントラクトプラットフォームを提供できますか？<p>

現在利用可能なスマートコントラクトプラットフォームは、十分なスケーラビリティー、安全なコーディング、比較的安価な実世界のデータへのアクセスの欠如という3つの主な問題点があります。<p>

<ol>
<li>現在普及しているステートフルな設計は、スマートコントラクトや、スマートコントラクトプラットフォームのためにコードされたものを分析するのはむしろ難しくなってます。さらに、statfefulnessはトランザクションの順番付けによりスケーラビリティが低下します。
<li>実世界のデータを分散型かつ信頼性の高い方法でトラストレスなスマートコントラクトプラットフォームに導入することは、ハードルが高くそのため多くの有益なアプリケーションの実現を阻害していた。
<li>ほとんどのスマートコントラクトプラットフォームは新しい技術や経済的なものに対処するために、アップデートする手段や能力が限られています。</ol><p>

ステートチャネル技術に関する最近の研究では、多くの場合、ステートオンチェーン上にデータを保存することは不要であることが証明されてます。ほとんどの場合、全てのデータはステートチャネル内に保存することができます。そしてブロックチェーンは結果の情報を保存し解決すため、及び・または争いが発生した際の仲裁方法としてのみ使用されます。これは、ステートチャンネルではできるが、ブロックチェーンではできないチューリング完全なスマートコントラクトによってマークされているアルタネイティブブロックチェーンアーキテクチャを示してます。これにより、全てのトランザクションが独立して処理されるため、スケーラビリティが爆発的に向上します。さらに、このアプローチは、スマートコントラクトが共有されないため、コントラクトのテスト及び検証が大幅に簡素化されます。<p>

[[Augur]] is a decentralized prediction market that attempted to integrate real-world data with the blockchain in a decentralized manner via a process that implements a consensus mechanism on smart contracts, rather than implementing the consensus mechanism provided by the underlying blockchain. This will result in inefficiencies, yet it won’t boost security. So, it is logically better to generalize the consensus mechanism of the blockchain so that it can provide information on the next [[internal state]] as well as on the external world’s state. So, we can assume that the blockchain’s consensus mechanism dictates the outcome of executing what [[complexity theory]] describes as an “[[oracle machine]]”. An oracle machine is a theoretical machine that is far more powerful than a [[Turing machine]] due to the fact that it can bear answers to questions whose answers cannot be computed such as “Who won the Super Bowl in 2016?”<p>

<b>Overview and Applications of æternity:<p>

æternity is a blockchain protocol that is designed to solve all the aforementioned problems that are challenging smart contract platforms. æternity provides a highly efficient system for transferring value. Practically speaking, æternity represents a global oracle machine that can be utilized to provide decision making services on an enormous scale.<p>

The stateless nature of æternity’s smart contracts makes it ideal for building a myriad of applications including:<ol>
<li>Identities: Each account will be associated with a [[unique ID number]]. Users will be allowed to register distinctive names and link them to a data structure’s [[Merkle]] root.
<li>Wallet: the [[wallet]] manages the cryptocurrency, Aeon, [[private keys]], sends and signs transactions. It can also be used to create channel transactions and use apps within the [[channel network]].
<li>Toll API: Payment channels open the door to a novel type of APIs where a user can pay for every API request. [[Toll API]]s mitigate [[DDoS]] problems and simplify the creation of high quality APIs.
<li>Insured Crowdfunding: [[Insured crowdfunding]] can be implemented via means of [[dominant assurance contracts]], which are smart contracts that are created to raise money for a good cause.
<li>Others: other possible applications include [[cross-chain atomic swaps]], [[event contracts]] (e.g. insurance, whistleblowing) and prediction markets. </ol><p>

<i>Extracted from deepdotweb.com article by Tamer Sameeh from Feb 28, 2017. 

[comment]: <> (Using a table to clear the floated image! doesn't seem to be a nice markdown way!)
<table border=0>
</table>

## Wikiの編集


    コンテンツをWikiに追加する前に,コンテンツが重複するのを避けるため、既存のコンテンツを全部読んでおいてください！また、コンテンツを寄稿する前に Wiki GuidelinesとTo Doをお読みください

    æternityのスペルはæternityです。Æternityではないです。
    

## もっと詳しく
SlackでのWikiチャンネルは[ここ](https://pacific-beach-20900.herokuapp.com/)です。どうぞお気軽にご参加ください！

* [[Wiki Guidelines & To Do's]]
* [[Understanding æternity]]
* [[Getting Started]]
* [æternity Contracts](æternity-Contracts)
* [æternity Team](æternity-Team)
* [æternity Technology](æternity-Technology)
* [[State Channels]]
* [æternity Blog](https://blog.aeternity.com/)
* [æternity Wallet](https://wallet.aeternity.com/)
* [[Mining]]
* [[Frequently Asked Questions]]
* [[Research and Theory]]
* [[Contacts and Groups]]
* [[Bounty]]
* [[Idea Box]]
* [[Community]]
* [[Wikipedia page]]

## 外部サイト
[æternity Wikipedia page](https://en.wikipedia.org/wiki/AEternity).

[Whitepaper_English]: Whitepaper_English
[Whitepaper_Korean (한국어)]: Whitepaper_Korean-(한국어)
[Whitepaper_Indonesia]: Whitepaper_Indonesia
[Whitepaper_French]: Whitepaper_French
[Whitepaper_Chinese]: Whitepaper_Chinese
[Whitepaper_Russian]: Whitepaper_Russian
[Whitepaper_Español]: Whitepaper_Español
[Whitepaper_Japanese]: Whitepaper_Japanese