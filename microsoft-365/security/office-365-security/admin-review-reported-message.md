---
title: 報告されたメッセージの管理者によるレビュー
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 報告されたメッセージを確認し、ユーザーにフィードバックを与える方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7386f5b283e2bfabb76eee91d33dfda0e42ec7b1
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769127"
---
# <a name="admin-review-for-reported-messages"></a>報告されたメッセージの管理者によるレビュー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。 このドキュメントは、評価と探索の目的でのみ提供されています。

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365メールボックスExchange Online Microsoft Defender for Office 365 の組織では、管理者は報告されたメッセージを確認した後、テンプレートメッセージをエンド ユーザーに送り返す機能を備えました。 これは、組織に合わせてカスタマイズし、管理者の評決にも基づいてカスタマイズできます。

この機能は、ユーザーにフィードバックを提供するように設計されますが、システム内のメッセージの評決は変更しません。 Microsoft がフィルターを更新して改善するには、管理者申請を使用して分析用のメッセージを送信 [する必要があります](admin-submission.md)。

メッセージが誤検知または偽陰性として報告された場合にのみ、ユーザーにレビュー結果をマークして [通知できます](report-false-positives-and-false-negatives.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識

- ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。
  - セキュリティ センターの組織の管理[またはMicrosoft 365管理者](permissions-microsoft-365-security-center.md)です。
  - [組織の管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo)。

- PowerShell にアクセスする必要Exchange Onlineがあります。 使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、「ドメインに電子メール アドレスを指定する」というエラーが *表示されます*。 PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。
  - [Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [クライアント アクセス ルール (Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>ユーザーに通知するために使用するメッセージを構成する

1. [セキュリティ センター [Microsoft 365に移動](../defender/overview-security-center.md)し、[ポリシー  ] &脅威ポリシー ユーザーがメッセージ設定 \>  \> **を報告しました**。

2. 送信者の表示名を指定する場合は、[管理者レビュー結果の電子メール通知] セクションの [送信者として使用する **Office 365** 電子メール アドレスを指定する] チェック ボックスをオンにし、使用する名前を入力します。 これは、返信が送信されるメール アドレスとOutlookに表示される電子メール アドレスです。

3. テンプレートをカスタマイズする場合は、[メール通知のカスタマイズ **] をクリックします**。 このフライアウトでは、次の情報のみをカスタマイズできます。
    - フィッシング詐欺
    - 迷惑メール
    - 脅威は検出されませんでした
    - 意識トレーニング
    - フッター

4. 完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[ユーザー申請] **ページ** で [破棄] をクリックします。
