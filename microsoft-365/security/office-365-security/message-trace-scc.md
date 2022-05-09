---
title: Microsoft 365 Defender ポータルでのメッセージ トレース
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft 365 Defender ポータルのメッセージ トレース リンクを使用して、メッセージに何が発生したかを確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d09470e37c066202d49d7d79788c12853ed42e21
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679744"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでのメッセージ トレース

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

メッセージ追跡は、Exchange Online 組織を通過する電子メール メッセージを追跡します。 メッセージがサービスによって受信、拒否、延期、配信されたかどうかを確認できます。 メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。

メッセージ トレースの情報を使用して、メッセージに何が発生したかに関するユーザーの質問に効率的に回答し、メール フローの問題をトラブルシューティングし、ポリシーの変更を検証できます。

> [!NOTE]
> Microsoft 365 Defender ポータルのメッセージ トレースは、Exchange管理センターのメッセージ トレースにパススルーするだけです。 詳細については、[最新のExchange管理センターのメッセージ トレースに関する説明を参照してください](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- メッセージ トレースを使用するには、**Exchange Online** の **組織管理**、**コンプライアンス管理**、または **ヘルプ デスク** の役割グループのメンバーである必要があります。 詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**: Microsoft 365 管理センターの対応するAzure Active Directory ロールのメンバーシップにより、Microsoft 365の他の機能に必要なアクセス許可 _と_ アクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

- メッセージ トレースの結果に表示されるメッセージの最大数は、選択したレポートの種類によって異なります (詳細については、「レポートの [種類の選択](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) 」セクションを参照してください)。 Exchange Online PowerShell またはスタンドアロン EOP PowerShell の [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) コマンドレットは、結果内のすべてのメッセージを返します。

## <a name="open-message-trace"></a>メッセージ トレースを開く

Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> **Exchangeメッセージ トレース**] に移動します。 メッセージ トレース ページに直接移動するには、 <https://admin.exchange.microsoft.com/#/messagetrace>.

この時点で、EAC のメッセージ トレースが開きます。 詳細については、[最新のExchange管理センターのメッセージ トレースに関する説明を参照してください](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。
