# Bunsan Overview

## About Bunsan

Bunsanとは、
各々が自由に情報をシェアできるプログラムを構築、実行可能な
基盤(foundation)を、
インターネット上にWebベースの技術を利用してdecentralizedに構築する
システム群である。

## Sources of Bunsan

Bunsanは現在、以下のリポジトリを公開する:

- [anatta-engine](https://github.com/anatta-project/anatta-engine/)
- [Hashnet](https://github.com/anatta-project/hashnet/)
- [grp](https://github.com/anatta-project/grp/)

### anatta-engine

「Anatta Engine」は、小さな非同期プログラムの集合を、
URIに基づいて構造化し、REST型メッセージングで
相互連携させてシステムを構成できるプログラム実行環境である。

メッセージやプログラム状態を始めとする、プリミティブなデータ構造として、
HTML DOMを使い、メタデータアクセス可能にするインタフェースを追加する。
Engineによって具現化するものは、自分自身が中心にして自由に
割り当てができるURI空間であり、
データやプログラムから、ファイルやデータベースなどのローカルシステム、
そしてユニバーサルなWebへとシームレスなハイパーリンクアクセスを可能にする。

このリポジトリには、nodejs上で稼働するランタイムとそのexamplesが含まれる。
[anatta-engine-potluck](https://github.com/anatta-project/anatta-engine-potluck/)
は、anatta-engineを用いたアプリケーション例としてWebページへのコメント共有システムである。

### hashnet

「Hashnet」は、非同期プログラミングのための「イベント」を、
インターネット上の各々が分散的に発行でき、それらを各々で分散的に利用できる、
基盤になるネットワークを構成するために設計したシステムである。

Hashnetにおける「イベント」とは、一般的なイベントシステムとは違い
発行者単位での事前にsubscribeを行わない、ユニバーサルに通用する
永続的なデータである。
この「イベント」では、その内容が持つ意味を示す「Context」が含まれており、
発行者から"Hashnetへ"「イベント」をPUTすると、
利用したい「Context」を元に利用者が"Hashnetから"非同期でイベントをGETすることが
可能となる、構造を提供するものである。

インターネット上で、各々の「イベント」発行者は非公開鍵ペアを保有し、
PUTされたすべての「イベント」に署名があり、署名を検証することで
正当であるとして扱う。各々が正当なイベントの範囲としての自分自身を起点に、
他者との間で正当なイベントとして扱う範囲を融合させていく分散システムを
構成する。この分散システム自体もまたhashnetの「イベント」の上で構築した
アプリケーションとなる構造である。

このリポジトリには、この構造で実装したhashnetを構成するピアのプロトタイプ実装、及び、
ピア間ネットワークにおけるイベントのシミュレーションでの統計用のコードとその結果データが含まれる。
ピア実装ではREPLが起動し、JavaScript関数呼び出しを通じてピアの機能を実行させるUIとなっている。
イベント例としてブックマーク共有イベントと、及びそのElectronベースのGUIも含んでいる。

### grp

grpは、小さなプログラムのための「汎用リバースプロクシ機構」システムのプロトタイプである。

「汎用リバースプロクシ機構」は、Anatta Engineの、プログラムをURIでアクセスさせる構造について切り出し、
それ単体で利用可能にしたものである。
クラウドではなく、ブラウザページ上のスクリプトのレベルのプログラムからURIでアクセスを可能にする。

このリポジトリには、nodejsで稼動させるリバースプロクシサーバ部分と、
WebSocketで通信しServiceWorkerの
[fetchイベント型のクライアント](https://developer.mozilla.org/docs/Web/API/FetchEvent#Examples)
インタフェースを提供するJavaScriptライブラリ、及びそのアプリケーション例を含む。

## Architecture of Bunsan

See: [architecture.md](architecture.md)

## Mission of Bunsan

See: [mission.md](mission.md)

## A History of Bunsan

See: [history.md](history.md)

