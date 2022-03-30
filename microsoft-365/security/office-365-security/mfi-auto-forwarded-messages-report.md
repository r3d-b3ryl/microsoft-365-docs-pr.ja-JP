---
title: 自動転送されたメッセージのインサイト
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理者は、セキュリティ コンプライアンス センターのメール フロー ダッシュボードで自動転送&できます。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 05ad934fbc7736c0cfbb86f7411a2ca73705112f
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680162"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターでの自動転送&分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの [](mail-flow-insights-v2.md)自動転送メッセージ分析情報 [](https://protection.office.com)には、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。

![コンプライアンス センターのセキュリティ サーバーの自動転送&ウィジェット。](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自動転送されたメッセージの詳細

ウィジェット内のメッセージの数をクリックすると、自動転送されたメッセージの詳細を示すフライアウト ウィンドウが表示されます。

- **転送方法による自動転送メッセージ**:

  - **メール フロー ルール別**
  - **受信トレイ ルール別**
  - **SMTP 転送による:** このメソッドは、「メールボックスの電子メール転送の構成」の説明に従って、管理者がメールボックスで構成できる自動転送 [を示します](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。
  - 詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。

- **ドメインとユーザーによる自動転送メッセージ**:

  - **転送先の上位 5 つのドメイン**
  - **新しいドメイン (先週)**
  - **上位 5 人の転送ユーザー**
  - **新しいユーザー (先週)**
  - 詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンク。

![[セキュリティ] コンプライアンス センターの [自動転送されたメッセージ] レポートの詳細&表示されます。](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>分析情報

レポート データに基づいて 2 つの分析情報が生成されます。

- [新しいユーザーがメールを転送する](mfi-new-users-forwarding-email.md)
- [メールの転送中の新しいドメイン](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、「Security [& コンプライアンス センター」を参照してください](mail-flow-insights-v2.md)。