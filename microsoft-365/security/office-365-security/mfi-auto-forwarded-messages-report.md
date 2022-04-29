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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで、自動転送メッセージ レポートについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 2f102f4fbea558f0972fbd4f3e8f4a4bea257bf4
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131044"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターの自動転送メッセージ分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [メール フロー ダッシュボード](mail-flow-insights-v2.md)の **自動転送メッセージ** 分析情報には、組織から外部ドメイン内の受信者に自動的に転送されるメッセージに関する情報が表示されます。

:::image type="content" source="../../media/mfi-auto-forwarded-messages.png" alt-text="ウィジェット(セキュリティ & コンプライアンス センターの自動転送メッセージ)" lightbox="../../media/mfi-auto-forwarded-messages.png":::

## <a name="auto-forwarded-messages-details"></a>自動転送メッセージの詳細

ウィジェット内のメッセージの数をクリックすると、自動転送メッセージの詳細を示すポップアップ ウィンドウが表示されます。

- **転送方法による自動転送メッセージ**:

  - **メール フロー ルール別**
  - **受信トレイルール別**
  - **SMTP 転送:** この方法は、「メールボックスの電子メール転送を構成する」の説明に従って、管理者がメールボックスに対して構成できる自動 [転送を示します](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。
  - 詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。

- **ドメインとユーザーによる自動転送メッセージ**:

  - **上位 5 つのドメインが転送先**
  - **新しいドメイン (先週)**
  - **上位 5 人の転送ユーザー**
  - **新しいユーザー (先週)**
  - 詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンク。

:::image type="content" source="../../media/mfi-auto-forwarded-messages-details.png" alt-text="セキュリティ & コンプライアンス センターの自動転送メッセージ ウィジェット" lightbox="../../media/mfi-auto-forwarded-messages-details.png":::

## <a name="insights"></a>分析情報

レポート データに基づいて、次の 2 つの分析情報が生成されます。

- [新しいユーザーがメールを転送する](mfi-new-users-forwarding-email.md)
- [新しいドメインが電子メールで転送される](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
