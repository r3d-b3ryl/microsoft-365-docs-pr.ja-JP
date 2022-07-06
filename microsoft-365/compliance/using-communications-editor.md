---
title: 通信エディターを使用する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: コミュニケーション エディターを使用して、コンテンツの書式設定時にテキスト変数とマージ フィールド変数を変更します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 910d25b80775284b8b12d803e722579d987558cd
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636967"
---
# <a name="use-the-communications-editor"></a>通信エディターを使用する

ポータル コンテンツ、訴訟ホールド通知、および関連するアラーム/エスカレーションのコンテンツを定義するときに、コミュニケーション エディターを使用してコンテンツの書式設定と動的なカスタマイズを行うことができます。

## <a name="rich-text-editor"></a>リッチ テキスト エディター

コミュニケーション エディターを使用すると、エディター オプションを使用してテキストをカスタマイズできます。 たとえば、ユーザーはフォントの種類の変更、箇条書きの作成、コンテンツの強調表示などを行うことができます。

## <a name="merge-field-variables"></a>フィールド変数をマージする

コミュニケーション エディターの電子メールマージ変数を使用して、カスタマイズされたカストディアン属性をコミュニケーションの本文テキストに埋め込むことができます。 カストディアンに送信されると、マージ フィールドに対応するフィールドが入力されます。 たとえば、カストディアン John Smith に送信されると、マージ フィールド [Custodian Name] は対応する名前で変換されます。

電子メール差し込み印刷フィールドを使用するには、リッチ テキスト エディター コントロールの上部にある **[差し込み印刷フィールド** ] アイコンを選択します。 プレースホルダーは、ユーザーのカーソルの場所に基づいて追加されます。

### <a name="list-of-merge-field-variables"></a>マージ フィールド変数の一覧

<br>

****

|フィールド名|フィールドの詳細|
|---|---|
|表示名|カストディアンの名と姓。|
|受信確認リンク|各カストディアンの確認を記録するためのカスタマイズされたリンク。|
|ポータル リンク|カストディアンのコンプライアンス ポータルのカスタマイズされたリンク。|
|発行元の責任者|指定した発行元担当者の電子メール アドレス。|
|発行日|通知が発行された日付 (UTC)。|
|
