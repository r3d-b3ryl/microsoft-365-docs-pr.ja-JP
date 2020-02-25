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
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261054"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365 での自動調査の後の修復アクション

## <a name="remediation-actions"></a>修復アクション

Office 365 の[自動調査および応答機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)高度な脅威保護には、特定の修復アクションが含まれています。 自動化された調査を実行している場合や、完了した場合は、通常、セキュリティ運用チームによる承認を必要とする1つ以上の修復アクションが表示されます。 次の表に、Office 365 Advanced Threat Protection で現在利用可能な修復処置の概要を示します。 

|アクション | 説明 |
|-----|-----|
|URL のブロック (クリック時) |悪意のある Url を含む電子メールやドキュメントを保護します。 これにより、ユーザーが既存の Office ファイルまたは古い電子メールメッセージ内のリンクをクリックしたときに、悪意のあるリンクや関連する web ページが[安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)でブロックされるようになります。 |
|電子メールの削除 (ソフト)  |ユーザーのメールボックスから特定の電子メールメッセージを削除する|
|削除済みメールクラスターの回復  |すべてのユーザーのメールボックスからのクエリに一致する悪意のある電子メールメッセージを削除します。|
|外部メール転送の無効化 |特定のエンドユーザーのメールボックスから転送ルールを削除します。|

## <a name="approve-or-reject-pending-actions"></a>保留中のアクションを承認 (または拒否) します。

![AIR の調査処理 ページ](../../media/air-investigationactionspage.png)

[調査の詳細](air-view-investigation-results.md)を表示している間に、保留中の修復処理を承認または拒否することができます。 自動化された調査が完了するように、この手順をできるだけ早く実行することをお勧めします。

> [!IMPORTANT]
> 修復アクションを承認または拒否するには、適切なアクセス許可が必要です。 [AIR 機能を使用するには、必要なアクセス許可を](office-365-air.md#required-permissions-to-use-air-capabilities)参照してください。

1. [**操作**] タブを選択します。

2. リストからアイテムを選択します。 (これにより、[承認] ボタンと [拒否] ボタンが有効になります)。

3. 選択したアイテムの利用可能な情報を確認し、その操作を承認または拒否します。 
 - **承認**は修復を開始することを許可します。
 - **却下**にはその他のアクションはありません

## <a name="next-steps"></a>次のステップ

- [侵害されたユーザーセキュリティのプレイブックについて](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [ATP レポートを表示する](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)