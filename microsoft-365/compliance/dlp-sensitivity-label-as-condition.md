---
title: 秘密度ラベルを DLP ポリシーの条件として使用する (プレビュー)
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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 秘密度ラベルを DLP ポリシーの条件として使用できるサービスやアイテムの種類について説明します。
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235724"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a>秘密度ラベルを DLP ポリシーの条件として使用する (プレビュー)

次の場所の DLP ポリシーでは、[秘密度ラベル](sensitivity-labels.md)を条件として使用できます。

- Exchange Online メール メッセージ
- SharePoint Online
- OneDrive for Business サイト
- Windows 10 デバイス

秘密度ラベルは、**コンテンツに含まれている**一覧にオプションとして表示されます。

![条件としての秘密度ラベル](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a>サポートされているアイテム、シナリオ、ポリシー ヒント

秘密度ラベルは、これらのアイテム上やシナリオ内での条件として使用することができます。

### <a name="supported-items"></a>サポートされているアイテム

|サービス  |アイテムの種類  |ポリシー ヒントに利用可能  |強制可能  |
|---------|---------|---------|---------|
|Exchange    |メール メッセージ         |はい         |はい         |
|Exchange    |メールの添付ファイル         |いいえ *         |いいえ *         |
|SharePoint Online     |SharePoint Online 内のアイテム         |はい         |はい         |
|OneDrive for Business     |アイテム         |はい         |はい         |
|Teams     |Teams とチャネル メッセージ         |該当なし         |該当なし         |
|Teams     |添付ファイル         |はい **         |はい **         |
|Windows 10 デバイス (プレビュー)     |アイテム         |はい         |はい         |
|MCAS (プレビュー) |アイテム         |はい         |はい         |

\* メールの秘密度ラベルの DLP 検出がサポートされました。 秘密度ラベル付きのメールの添付ファイルの DLP 検出はサポートされていません。

\** 1:1 チャットまたはチャネルを介して Teams で送信された添付ファイルは、One drive for business や SharePoint に自動的にアップロードされます。 そのため、SharePoint Online や One Drive for Business が DLP ポリシー内の場所として含まれている場合、Teams で送信されたラベル付きの添付ファイルは自動的にこの条件の範囲に含まれます。 場所としての Teams は、DLP ポリシーで選択する必要はありません。

### <a name="supported-scenarios"></a>サポートされるシナリオ

- DLP 管理者が 1 つ以上の秘密度ラベルを条件として含めることを選択すると、DLP 管理者はテナント内のすべての秘密度ラベルの一覧を表示することができます。
- 秘密度ラベルの条件としての使用は、上記のサポートのマトリックスで示されているように、すべてのワークロードでサポートされています。
- DLP ポリシーのヒントは、秘密度ラベルを条件として含む DLP ポリシーのワークロード (Outlook Win32 を除く) 全体で表示され続けます。
- 秘密度ラベルを条件として持つ DLP ポリシーが一致した場合、秘密度ラベルはインシデント レポート メールの一部としても表示されます。
- 秘密度ラベルの詳細情報は、秘密度ラベルを条件として含む DLP ポリシーの一致の DLP ルール一致監査ログにも表示されます。


### <a name="support-policy-tips"></a>ポリシー ヒントのサポート


|ワークロード  |ポリシーヒントのサポートあり/サポートなし  |
|---------|---------|
|OWA |    サポート対象     |
|Outlook Win 32    |  サポートなし       |
|SharePoint   |   サポート対象      |
|OneDrive for Business    |    サポート対象     |
|エンドポイント デバイス   |  サポートなし       |
