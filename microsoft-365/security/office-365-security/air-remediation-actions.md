---
title: Office 365 の修復アクション自動調査と応答
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の修復アクションについて説明します。
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955535"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365 での自動調査の後の修復アクション

## <a name="remediation-actions"></a>修復アクション

Office 365 の[自動調査および応答機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)(AIR) [Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) プラン2には、特定の修復アクションが含まれています。 自動化された調査を実行している場合や、完了した場合は、通常、セキュリティ運用チームによる承認を必要とする1つ以上の修復アクションが表示されます。 

次の表に、Office 365 ATP で現在利用可能な修復アクションの概要を示します。 

|アクション | 説明 |
|-----|-----|
|URL のブロック (クリック時) |悪意のある Url を含む電子メールメッセージやドキュメントを保護します。 これにより、ユーザーが既存の Office ファイルまたは古い電子メールメッセージ内のリンクをクリックしたときに、悪意のあるリンクや関連する web ページが[安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)でブロックされるようになります。 |
|電子メールの削除 (ソフト)  |ユーザーのメールボックスから特定の電子メールメッセージを削除します。 <br/>削除済みメッセージは、ユーザーの回復可能なアイテムフォルダーに移動され、削除済みアイテムの保存期間が経過するまで保持されます。 |
|削除済みメールクラスターの回復  |すべてのユーザーのメールボックスからのクエリに一致する悪意のある電子メールメッセージを削除します。 <br/>削除済みメッセージは、ユーザーの [回復可能なアイテム] フォルダーに移動され、削除済みアイテムの保存期間が経過するまで保持されます。 |
|外部メール転送の無効化 |特定のエンドユーザーのメールボックスから転送ルールを削除します。|

> [!NOTE]
> Office 365 ATP では、修復アクションは自動的には実行されません。 修復処理は、組織のセキュリティチームによる承認時にのみ行われます。 

## <a name="next-steps"></a>次の手順

- [Office 365 の自動調査の後に、保留中または完了した修復アクションを表示する](air-review-approve-pending-completed-actions.md)

- [Office 365 の自動調査の詳細と結果](air-view-investigation-results.md)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender Advanced Threat Protection の自動調査](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)