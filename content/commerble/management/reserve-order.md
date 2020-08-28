---
title: "仮予約"
weight: 30
headless: true
description: 
---

# 仮予約

## 「仮予約」販売とは何ですか？
Commerbleの「仮予約」販売は、いわゆる**整理券販売**です。  
現在販売されていない商品（売切れ・未発売）の購入予約をユーザから受付け、
商品が販売可能になったときに仮予約者に優先的に購入する権利を与えます。

「予約」販売とは異なります。予約販売では発売日前に購入を受付けて、発売日以降に商品を出荷します。

仮予約は、数量限定商品の販売や抽選販売に適しています。

{{< youtube 4hn3krzUSfI >}}

## 仮予約の流れ
商品Aは在庫切れ、仮予約可能商品として設定されてるとします。

1. ユーザー： 商品Aは購入できないので仮予約申込を行う。
2. 運営者： 仮予約申込を管理画面で確認することができます。
3. 運営者： 商品Aが入荷したので仮予約に商品を引当て、購入可能になったことをユーザに通知します。
4. ユーザー： ユーザは通知を受け取り仮予約専用のURLから商品を購入します。

## 仮予約のステータス
{{< mermaid >}}
graph LR
    A(入荷待ち) --> B(引当済み)
    B --> C(購入済み)
    B --> D(キャンセル)
    A --> D
{{< /mermaid >}}

- 入荷待ち： ユーザが仮登録申込をした後の状態。
- 引当済み： 運営者が商品引当てを行った状態。ユーザは購入可能です。
- 購入済み： ユーザが購入した状態。
- キャンセル： 仮予約がキャンセルされた状態。ユーザからもキャンセル可能です。

## 仮予約の制約
- 在庫がない商品のみ仮予約が可能です。
- 仮予約が利用できるのユーザは会員のみです。ゲストでは利用できません。
- 仮予約に引当てる商品数は、通常販売で利用する販売可能数とは独立した数です。仮予約に商品を引当てても販売可能数は減りません。
- 商品の販売ステータス=販売中のもののみ、仮予約から購入できます。

## 仮予約の確保数・確保期限とは何ですか？
仮予約の引当て・キャンセルを、バッチ処理などで制御する場合に利用する項目です。
ECサイトでの仮予約商品の購入には影響はありません。

## 仮予約の商品引当ては一括でできますか？
EC管理画面から商品引当てを個別に行うことはできますが、一括では行うことはできません。（一括キャンセルは可能です）  
一括で引当てを行うには、 OData API を利用してください。

## 入荷通知
仮予約機能の一部機能を利用して、入荷通知を行うことができます。