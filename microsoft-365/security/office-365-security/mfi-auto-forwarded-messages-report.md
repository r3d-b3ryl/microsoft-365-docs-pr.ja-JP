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
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの自動転送メッセージレポートについて説明します。
ms.openlocfilehash: e9e3a0159671dd4ce62f4fa0b07b7162807fe0e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949858"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでの自動転送メッセージの洞察

[セキュリティ & コンプライアンスセンター](https://protection.office.com)の[メールフローダッシュボード](mail-flow-insights-v2.md)に表示される**自動転送メッセージ**には、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。

![セキュリティ & コンプライアンスセンターの自動転送メッセージウィジェット](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自動転送されたメッセージの詳細

ウィジェット内のメッセージ数をクリックすると、自動的に転送されるメッセージに関する詳細情報を示すフライアウトウィンドウが表示されます。

- **転送方法による自動転送メッセージ**:

  - **メールフロールール**
  - **受信トレイルール**
  - **SMTP 転送による**
  - 詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンクを参照してください。

- **ドメインおよびユーザーによる自動転送メッセージ**:

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
