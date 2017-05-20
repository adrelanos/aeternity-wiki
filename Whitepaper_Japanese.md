### Æternity blockchain
トラストレスで、分散化された、 そして純真で機能的なオラクルマシーン

2017/2/6

Ver.0.1

- Zackary Hess
zack@aeternity.com
- Yanislav Malahov
yani@aeternity.com
- Jack Pettersson
jack@aeternity.com

## 概要
Ethereumが2014年に始まって以来、分散型でトラストレスなアプリケーション（スマートコントラクト）に大きな関心が集まってます。
その結果、多くの人々がブロックチェーン上に現実の世界のデータを使ったアプリケーションを実装しようとしています。

私たちは、アプリケーションの状態とコードをブロックチェーン上に保存することはいくつかの理由で間違っていると考えてます。
私たちはオラクルシステムを使ってチェックするコンセンサスメカニズムを使用した、非常にスケーラブルなブロックチェーンアーキテクチャを提案します。
この仕組みはオラクルを非常に効率的にします。なぜならそれは一つのコンセンサスメカニズムを積み重ねるレイヤー構造を避けるからです。
ステートチャネルはプライバシーとスケーラビリティを高めるために統合されています。 チャネルにおけるトークンは、純真で機能的なスマートコントラクトを使用し、オラクルの結果にアクセスして、送信することができます。
コントラクトコードを保存したりオンチェーンを使用せずに、私たちは大幅なロスもない、機能性のあるスマートコントラクトを簡単に分析でき処理も高速です。

総合的な資産と予測のためのマーケット的なアプリケーションは、世界規模で市場をもっと効率的に動かすことができます。

いくつかの分野のProof of Concept(PoC)はErlangという言語を使い実装しています。開発用ツールとアプリケーションや必需のウォレット、身元確認システムも提供されます。


## 目次
I [はじめに](#はじめに) 

I-A [以前](#以前)

II [Æternity ブロックチェーン](#Æternity ブロックチェーン) 

II-A [トークン、アカウント、そしてブロック](#トークン、アカウント、そしてブロック)
II-A.1 [Aeonトークンへのアクセス](#Aeonトークンへのアクセス) 
II-A.2 [アカウント](#アカウント)
II-A.3 [ネームシステム](#ネームシステム)
II-A.4 [ブロックの内容](#ブロックの内容)
II-B [ステートチャネル](#ステートチャネル)
II-B.1 [スマートコントラクト](#スマートコントラクト)
II-B.2 [例](#例)
II-C [コンセンサスメカニズム](#コンセンサスメカニズム)
II-C.1 [オラクル](#オラクル)
II-D [ガバナンス](#ガバナンス)
II-E [スケーラビリティ](#スケーラビリティ)  
II-E.1 [Sharding-trees](#sharding-trees)
II-E.2 [軽量クライアント](#軽量クライアント)
II-E.3 [ステートチャネルと比較](#ステートチャネルと比較)
II-E.4 [Transactions/secとメモリ要件](#Transactions/secとメモリ要件) 
III [アプリケーション](#アプリケーション)
III-A [ブロックチェーンに必要なこと](#ブロックチェーンに必要なこと)
III-A.1 [アイデンティティ](#アイデンティティ)
III-A.2 [ウォレット](#ウォレット)
III-A.3 [PoE(Proof of existence)](#PoE(Proof of existence))
III-B [ステートチャネルアプリケーション](#ステートチャネルアプリケーション)
III-B.1 [APIを叩く](#APIを叩く)
III-B.2 [保険付きクラウドファンディング](#保険付きクラウドファンディング)
III-B.3 [クロスチェーンとアトミックスワップ](#クロスチェーンとアトミックスワップ) 
III-B.4 [安定した価値の資産と、ポートフォリオの複製](#安定した価値の資産と、ポートフォリオの複製)
III-B.5 [イベントコントラクト](#イベントコントラクト) 
III-B.6 [予測市場](#予測市場)
III-B.7 [Market con un lotto in vendita ad un prezzo singolo](#market-con-un-lotto-in-vendita-ad-un-prezzo-singolo) . . . . . . 7  
IV [Implementazione](#implementazione) . . . . . . . . . . . . . . . 8  
IV-A [Macchine e linguaggio del contratto](#macchine-e-linguaggio-del-contratto) . . . . 8  
IV-B [Adozione tramite integrazione web](#adozione-tramite-integrazione-web) . . . . . 8  
IV-C [Moduli open source](#moduli-open-source)  . . . . . . . . . . . . 8  
IV-D [Condizioni d'uso e design dell'UX](#condizioni-duso-e-design-dellux) . . . . . 8  
V [Discussioni](#discussioni)  . . . . . . . . . . . . . . . . . 8  
V-A [Limitazioni e tradeoff](#limitazioni-e-tradeoff) . . . . . . . . . . . 9  
V-A.1 [Stati sulla blockchain](#stati-sulla-blockchain) . . . . . . . . . . 9  
V-A.2 [Problema dell'opzione gratuita](#problema-dellopzione-gratuita) . . . . . . 9  
V-A.3 [Perdita di liquidità e tipologie di macchine a stati](#perdita-di-liquidità-e-tipologie-di-macchine-a-stati) . . . . . 9  
V-B [Lavori Futuri](#lavori-futuri)  . . . . . . . . . . . . . . . 9  
V-B.1 [Linguaggio funzionale del contratto](#linguaggio-funzionale-del-contratto)  . . . 9  
V-B.2 [Canali multi-parti](#canali-multi-parti) . . . . . . . . . . . . 9  
