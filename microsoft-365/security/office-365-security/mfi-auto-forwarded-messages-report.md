---
title: 自動転送されたメッセージの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理者は、セキュリティ/コンプライアンス センターのメール フロー ダッシュボードで、自動転送&確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150602"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでの自動転送&の分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

セキュリティ **&** コンプライアンス センターのメール [](mail-flow-insights-v2.md)フロー ダッシュボードの [](https://protection.office.com)自動転送されたメッセージの分析情報には、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。

![セキュリティ/コンプライアンス センターの自動転送&ウィジェット](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自動転送されたメッセージの詳細

ウィジェット内のメッセージ数をクリックすると、自動転送されたメッセージに関する詳細を表示するフライアウト ウィンドウが表示されます。

- **転送方法による自動転送メッセージ**:

  - **メール フロー ルール別**
  - **受信トレイ ルール別**
  - **SMTP 転送による** 転送 : この方法は、「メールボックスのメール転送を構成する」の説明に従って、管理者がメールボックスで構成できる自動転送 [を示します](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。
  - 詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。

- **ドメインおよびユーザーによって自動的に転送されるメッセージ**:

  - **転送先の上位 5 つのドメイン**
  - **新しいドメイン (先週)**
  - **上位 5 人の転送ユーザー**
  - **新しいユーザー (先週)**
  - 詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンク。

![セキュリティ/コンプライアンス センターの [自動転送されたメッセージ] &詳細フライアウト](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>分析情報

レポート データに基づいて 2 つの分析情報が生成されます。

- [新しいユーザーがメールを転送する](mfi-new-users-forwarding-email.md)
- [メールを転送する新しいドメイン](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>こちらもご覧ください

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
