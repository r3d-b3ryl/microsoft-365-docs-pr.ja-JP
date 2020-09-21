---
title: Microsoft の脅威保護で自動調査を行った後の修復アクション
description: Microsoft の脅威保護で自動化された調査に従う修復アクションの概要を理解する
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 205809bac14cc82e850ea1cbc0349256432bfe68
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962587"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Microsoft の脅威保護で自動調査を行った後の修復アクション

**適用対象:**
- Microsoft Threat Protection


## <a name="remediation-actions"></a>修復アクション

Microsoft の脅威保護の自動化された調査の最中および実行後に、修復アクションは悪意のあるアイテムまたは疑わしいアイテムに対して識別されます。 一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。 その他の修復アクションは、電子メールコンテンツに対して実行されます。 修復アクションが実行、承認、または拒否された後、自動調査が完了します。

次の表に、Microsoft の脅威保護で現在サポートされている修復アクションの概要を示します。 

|デバイス (エンドポイント) の修復アクション  |メールの修復アクション  |
|---------|---------|
|-調査パッケージを収集する <br/>-分離デバイス (この操作は元に戻すことができます)<br/>-オフボードマシン <br/>-リリースコードの実行 <br/>-検疫からの解放 <br/>-要求のサンプル <br/>-コード実行を制限する (このアクションは元に戻すことができます) <br/>-ウイルス対策スキャンを実行する <br/>-停止および検疫      |-ブロック URL (クリック時)<br/>-電子メールメッセージまたはクラスターのソフト削除<br/>-検疫電子メール<br/>-電子メールの添付ファイルを検疫する<br/>-外部メール転送をオフにする          |

修復アクションは、保留中の承認か、既に完了しているかにかかわらず、 [アクションセンター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)に表示できます。

## <a name="remediation-actions-follow-automated-investigations"></a>修復操作は自動調査に従います。

自動調査が完了すると、関連するすべての証拠に対して verdict が到達します。 Verdict に応じて、修復アクションが識別されます。 修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。 これ [は、自動化された調査と応答の構成](mtp-configure-auto-investigation-response.md)方法によって異なります。

考えられる判定と結果を次の表に示します。

|判定    |分野    |結果|
|------|------|------|
|Malicious (悪意のある)    |デバイス (エンドポイント)    |修復処置は自動的に実行されます (組織の [デバイスグループ](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) が **完全に修復**される脅威に自動的に設定されることを前提としています)。|
|Malicious (悪意のある)    |メールのコンテンツ (URL または添付ファイル) | 推奨される修復アクションが承認待ちになります|
|Suspicious (不審)    |デバイスまたはメールのコンテンツ |推奨される修復アクションが承認待ちになります|
|脅威なし    |デバイスまたはメールのコンテンツ    |必要な修復アクションはありません|

> [!IMPORTANT]
> 修復アクションが自動的に実行されるか、承認のみになるかは、組織のデバイスグループポリシーなどの特定の設定によって決まります。 詳細については、次の記事を参照してください。
> - [Microsoft の脅威保護で自動調査および応答機能を構成する](mtp-configure-auto-investigation-response.md)
> - [デバイスでの脅威の修復方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>次の手順

- [アクションセンターにアクセスする](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [保留中のアクションを承認または拒否する](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [自動調査と応答機能で誤検知/否定を処理する](mtp-autoir-report-false-positives-negatives.md)
