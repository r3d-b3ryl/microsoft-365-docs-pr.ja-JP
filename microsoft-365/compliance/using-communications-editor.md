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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: コンテンツの書式設定時にテキストを変更し、フィールド変数を結合するには、Communications Editor を使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769162"
---
# <a name="use-the-communications-editor"></a>通信エディターを使用する

ポータル コンテンツのコンテンツ、法的情報保留通知、関連するリマインダー/エスカレーションを定義する場合、コミュニケーション エディターを使用してコンテンツの書式設定と動的なカスタマイズを行います。

## <a name="rich-text-editor"></a>リッチ テキスト エディター

コミュニケーション エディターを使用すると、ユーザーはエディターオプションを使用してテキストをカスタマイズできます。 たとえば、フォントの種類の変更、箇条書きの作成、コンテンツの強調表示などです。

## <a name="merge-field-variables"></a>フィールド変数を結合する

通信エディターの電子メールの差し込み変数を使用して、カスタマイズされた保管担当者の属性を通信の本文テキストに埋め込む方法があります。 カストディアンに送信すると、マージ フィールドに対応するフィールドが設定されます。 たとえば、カストディアンの John Smith に送信すると、結合フィールド [保管担当者名] は対応する名前で翻訳されます。

リッチ テキスト エディター コントロールの上部にある[差し込み印刷] フィールド アイコンを選択すると、電子メールの差し込みフィールドを使用できます。 プレースホルダーは、ユーザーのカーソルの位置に基づいて追加されます。

### <a name="list-of-merge-field-variables"></a>差し込み印刷フィールド変数のリスト

| フィールド名                  | フィールドの詳細 |
| :------------------- | :------------------- |
| 表示名  | カストディアンの名と名。 | 
| 確認応答リンク | 各保管担当者の確認を記録するカスタマイズされたリンク。|                 |
| ポータル リンク     | カストディアンのコンプライアンス ポータル用にカスタマイズされたリンク。|                |
| 発行責任者                   | 指定された発行者の電子メール アドレス。|                   |
| 発行日                   | 通知が発行された日付 (UTC)。              |
|||
