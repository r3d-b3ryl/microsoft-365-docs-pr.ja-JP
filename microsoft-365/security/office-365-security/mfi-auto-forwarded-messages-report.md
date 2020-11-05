---
title: 自動転送されたメッセージの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの自動転送メッセージレポートについて説明します。
ms.openlocfilehash: 28cb593d56d0b0054c8c8cbe4596d4f7df6442ab
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920598"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでの自動転送メッセージの洞察

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)に表示される **自動転送メッセージ** には、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。

![セキュリティ & コンプライアンスセンターの自動転送メッセージウィジェット](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自動転送されたメッセージの詳細

ウィジェット内のメッセージ数をクリックすると、自動的に転送されるメッセージに関する詳細情報を示すフライアウトウィンドウが表示されます。

- **転送方法による自動転送メッセージ** :

  - **メールフロールール**
  - **受信トレイルール**
  - **SMTP 転送によって** : このメソッドは [、「メールボックスの電子メール転送を構成する](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)」で説明されているように、管理者がメールボックスに対して構成できる自動転送を示します。
  - 詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンクを参照してください。

- **ドメインおよびユーザーによる自動転送メッセージ** :

  - **上位5ドメイン転送先**
  - **新しいドメイン (先週)**
  - **上位5人のユーザーの転送**
  - **新しいユーザー (先週)**
  - 詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンクを参照してください。

![セキュリティ & コンプライアンスセンターの自動転送されたメッセージレポートの詳細ポップアップ](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>分析情報

レポートデータに基づいて、2つの洞察が生成されます。

- [新しいユーザーがメールを転送する](mfi-new-users-forwarding-email.md)
- [メールを転送する新しいドメイン](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
