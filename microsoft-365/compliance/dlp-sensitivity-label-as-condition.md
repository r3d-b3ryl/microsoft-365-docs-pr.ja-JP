---
title: DLP ポリシーで秘密度ラベルを条件として使用する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 秘密度ラベルを DLP ポリシーの条件として使用できるサービスやアイテムの種類について説明します。
ms.openlocfilehash: 55803a2c354890264f99753af2aa6337cf49182a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632401"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>DLP ポリシーで秘密度ラベルを条件として使用する

次の場所の DLP ポリシーでは、[秘密度ラベル](sensitivity-labels.md)を条件として使用できます。

- Exchange Online メール メッセージ
- SharePoint Online
- OneDrive for Business サイト
- Windows 10 デバイス

秘密度ラベルは、**コンテンツに含まれている** 一覧にオプションとして表示されます。

> [!div class="mx-imgBorder"]
> ![条件としての秘密度ラベル。](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> DLP ポリシーを適用する場所として **Teams チャットとチャネル メッセージ** を選択している場合、条件としての **秘密度ラベル** は使用できません。


## <a name="supported-items-scenarios-and-policy-tips"></a>サポートされているアイテム、シナリオ、ポリシー ヒント

秘密度ラベルは、これらのアイテム上やシナリオ内での条件として使用することができます。

### <a name="supported-items"></a>サポートされているアイテム

|サービス  |アイテムの種類  |ポリシー ヒントに利用可能  |強制可能  |
|---------|---------|---------|---------|
|Exchange    |メール メッセージ         |はい         |はい         |
|Exchange    |メールの添付ファイル         |いいえ         |はい *         |
|SharePoint Online     |SharePoint Online 内のアイテム         |はい         |はい         |
|OneDrive for Business     |アイテム         |はい         |はい         |
|Teams     |Teams とチャネル メッセージ         |該当なし         |該当なし         |
|Teams     |attachments         |はい **         |はい **         |
|Windows 10 デバイス     |アイテム         |はい         |はい         |
|MCAS (プレビュー) |アイテム         |はい         |はい         |

\* DLPによる秘密度ラベル付きメール添付ファイルの検出は、Open XML ベースの Office ファイルタイプにのみ対応しています。

\** 1:1 チャットまたはチャネルを介して Teams で送信された添付ファイルは、OneDrive for Business や SharePoint に自動的にアップロードされます。 そのため、SharePoint Online や OneDrive for Business が DLP ポリシー内の場所として含まれている場合、Teams で送信されたラベル付きの添付ファイルは自動的にこの条件の範囲に含まれます。 場所としての Teams は、DLP ポリシーで選択する必要はありません。

> [!NOTE]
> SharePoint および OneDrive for Business で秘密度ラベルを検出する DLP の機能は制限されています。 詳細については、「[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md#limitations)」を参照してください。

### <a name="supported-scenarios"></a>サポートされるシナリオ

- DLP 管理者が 1 つ以上の秘密度ラベルを条件として含めることを選択すると、DLP 管理者はテナント内のすべての秘密度ラベルの一覧を表示することができます。

- 秘密度ラベルの条件としての使用は、上記のサポートのマトリックスで示されているように、すべてのワークロードでサポートされています。

- DLP ポリシーのヒントは、秘密度ラベルを条件として含む DLP ポリシーのワークロード (Outlook Win32 を除く) 全体で表示され続けます。

- 秘密度ラベルを条件として持つ DLP ポリシーが一致した場合、秘密度ラベルはインシデント レポート メールの一部としても表示されます。

- 秘密度ラベルの詳細は、条件として秘密度ラベルを含む DLP ポリシー一致の DLP ルール一致監査ログにも表示されます。


### <a name="support-policy-tips"></a>ポリシー ヒントのサポート


|ワークロード  |ポリシー ヒントのサポートあり/サポートなし  |
|---------|---------|
|OWA |    サポート対象     |
|Outlook Win 32    |  サポートなし       |
|SharePoint   |   サポート対象      |
|OneDrive for Business    |    サポート対象     |
|エンドポイント デバイス   |  サポートなし       |
