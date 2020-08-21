---
title: 自動転送されたメッセージのインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理者は、セキュリティ コンプライアンス センターのメール フロー ダッシュボードで自動転送メッセージ レポート &について確認できます。
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827029"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>セキュリティ センターの自動転送されたメッセージ&分析情報

セキュリティ**コンプライアンス センターのメール フロー**ダッシュボードの自動[Mail flow dashboard](mail-flow-insights-v2.md)転送メッセージ インサイト &に、組織から自動的に外部ドメイン内の受信者に転送されるメッセージに関する情報が表示されます。

![セキュリティ センターの自動転送メッセージ ウィジェット&ッジ](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自動転送メッセージの詳細

ウィジェットのメッセージ数をクリックすると、自動転送されたメッセージに関する詳細情報を示すポップアップ ウィンドウが表示されます。

- **転送方法による自動転送メッセージ**:

  - **メール フロー ルール別**
  - **受信トレイのルールを使用する**
  - **SMTP 転送によるフィルター**
  - 詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。

- **ドメインおよびユーザー別に自動転送されたメッセージ**:

  - **上位 5 つのドメインに転送**
  - **新しいドメイン (過去 1 週間)**
  - **転送ユーザー数 5 名**
  - **新規ユーザー (過去 1 週間)**
  - 詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンクを参照してください。

![セキュリティ コンプライアンス センターの自動転送メッセージ レポートの詳細&詳細情報](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>分析情報

レポート データに基づいて、次の 2 つのインサイトが生成されます。

- [新しいユーザーのメール転送](mfi-new-users-forwarding-email.md)
- [メール転送される新しいドメイン](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
