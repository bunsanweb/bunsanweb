# Anatta Overview

## About Anatta

Anattaとは、
各々が自由に情報をシェアできるプログラムを構築、実行可能な
基盤(foundation)を、
インターネット上にWebベースの技術を利用してdecentralizedに構築する
システム群である。

## Anatta 

Anattaでは現在、以下の要素が提案されている:

- [Anatta Engine](https://github.com/anatta-project/anatta-engine/)
- [Hashnet](https://github.com/anatta-project/hashnet/)
- Dashboard/Inst

「Anatta Engine」は、小さな非同期プログラムの集合を、
URIに基づいて構造化し、REST型メッセージングで
相互連携させてシステムを構成できるプログラム実行環境である。
メッセージやプログラム状態を始めとする、プリミティブなデータ構造として、
HTML DOMを使い、メタデータアクセス可能にするインタフェースを追加する。
Engineによって具現化するものは、自分自身が中心にして自由に
割り当てができるURI空間であり、
データやプログラムから、ファイルやデータベースなどのローカルシステム、
そしてユニバーサルなWebへとシームレスなハイパーリンクアクセスを可能にする。

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
アプリケーションである。

「Dashboard」は、Hashnetに基づく分散イベントを、Anatta Engineに基づく
小さな非同期プログラミング群で処理するための、各人が用いる実行環境である。
このDashboard上で管理される、Hashnetに対してイベントを処理するための
非同期プログラム群を、「Inst」と呼ぶパッケージの単位で扱う。
「Inst」パッケージ自体もまたHashnetを通じて、
公開し利用しあうことをDashboardを通じて行うことを想定したものであり、
そのパッケージリポジトリもHashnetを用いた分散システムとして、
Dashboardが備える機能となる。

## Architecture of Anatta

See; [architecture.md](architecture.md)

## Mission of Anatta

See; [mission.md](mission.md)
