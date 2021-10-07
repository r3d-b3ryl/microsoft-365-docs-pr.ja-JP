---
title: 通信エディターを使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: コンテンツの書式設定時にテキスト変数と結合フィールド変数を変更するには、コミュニケーション エディターを使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aceebf9f8a19448c05c137f668c2bca5db2d99bd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205979"
---
# <a name="use-the-communications-editor"></a>通信エディターを使用する

ポータル コンテンツ、法的ホールド通知、関連するアラーム/エスカレーションのコンテンツを定義する場合は、コミュニケーション エディターを使用してコンテンツの書式設定と動的なカスタマイズを行います。

## <a name="rich-text-editor"></a>リッチ テキスト エディター

コミュニケーション エディターを使用すると、エディター オプションを使用してテキストをカスタマイズできます。 たとえば、ユーザーはフォントの種類を変更し、箇条書きリストを作成し、コンテンツを強調表示できます。

## <a name="merge-field-variables"></a>フィールド変数の結合

コミュニケーション エディターの電子メール 差し込み変数を使用して、カスタマイズされた保管担当者の属性を通信の本文に埋め込みできます。 保管担当者に送信すると、マージ フィールドに対応するフィールドが設定されます。 たとえば、保管担当者 John Smith に送信すると、マージ フィールド [カストディアン名] が対応する名前で翻訳されます。

差し込み印刷フィールドを使用するには、リッチ テキスト エディター コントロールの上部にある [差し込み] フィールド アイコンを選択します。 プレースホルダーは、ユーザーのカーソルの位置に基づいて追加されます。

### <a name="list-of-merge-field-variables"></a>差し込みフィールド変数の一覧

<br>

****

|フィールド名|フィールドの詳細|
|---|---|
|表示名|カストディアンの名と名。|
|受信確認リンク|各保管担当者の確認を記録するカスタマイズされたリンク。|
|ポータル リンク|保管担当者のコンプライアンス ポータルのカスタマイズされたリンク。|
|発行責任者|指定された発行担当者の電子メール アドレス。|
|発行日|通知が発行された日付 (UTC)。|
|
