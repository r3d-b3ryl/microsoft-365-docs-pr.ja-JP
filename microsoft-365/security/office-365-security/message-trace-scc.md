---
title: ポータル内のMicrosoft 365 Defenderトレース
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理者は、ポータルのメッセージ トレース リンクをMicrosoft 365 Defender、メッセージに何が起こったのかを確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 934a8a0cf3c6eb0b828e334252707043d0d87e03
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61938158"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>ポータル内のMicrosoft 365 Defenderトレース

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

メッセージ追跡は、Exchange Online 組織を通過する電子メール メッセージを追跡します。 メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断できます。 メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。

メッセージ トレースの情報を使用して、メッセージに何が起こったかについてのユーザーの質問に効率的に回答し、メール フローの問題をトラブルシューティングし、ポリシーの変更を検証できます。

> [!NOTE]
> ポータル内のメッセージ Microsoft 365 Defenderは、管理センターのメッセージ トレースへのExchangeです。 詳細については、「モダン 管理センターのメッセージ トレース[」をExchangeしてください](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- メッセージ トレースを使用するには、組織の管理、コンプライアンス管理、またはヘルプ **デスクの役割グループ** のメンバー Exchange Online必要があります。  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**: グループ内の対応する Azure Active Directory ロールMicrosoft 365 管理センターメンバーシップは、ユーザーに、Microsoft 365 の他の機能に対して必要なアクセス許可とアクセス許可を付与します。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

- メッセージ トレースの結果に表示されるメッセージの最大数は、選択したレポートの種類によって異なります (詳細については、「レポートの種類の選択 [」セクションを](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) 参照してください)。 [PowerShell またはスタンドアロン EOP PowerShell Exchange Online Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch)コマンドレットは、結果のすべてのメッセージを返します。

## <a name="open-message-trace"></a>メッセージのトレースを開く

[電子メール Microsoft 365 Defender] の [メール] に移動し、& <https://security.microsoft.com> **のExchange** \> **を確認します**。 メッセージ トレース ページに直接移動するには、 を使用します <https://admin.exchange.microsoft.com/#/messagetrace> 。

この時点で、EAC のメッセージ トレースが開きます。 詳細については、「モダン 管理センターのメッセージ トレース[」をExchangeしてください](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。
