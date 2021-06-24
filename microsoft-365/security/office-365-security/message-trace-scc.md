---
title: ポータル内のMicrosoft 365 Defenderトレース
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理者は、ポータルのメッセージ トレース リンクをMicrosoft 365 Defender、メッセージに何が起こったのかを確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108129"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c21b1-103">ポータル内のMicrosoft 365 Defenderトレース</span><span class="sxs-lookup"><span data-stu-id="c21b1-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c21b1-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c21b1-104">**Applies to**</span></span>
- [<span data-ttu-id="c21b1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c21b1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c21b1-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c21b1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c21b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c21b1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c21b1-108">ポータル内のメッセージ トレースMicrosoft 365 Defender、組織を通過する電子メール メッセージにExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="c21b1-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="c21b1-109">メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="c21b1-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="c21b1-110">メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="c21b1-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="c21b1-111">メッセージ トレースの情報を使用して、メッセージに何が起こったかについてのユーザーの質問に効率的に回答し、メール フローの問題をトラブルシューティングし、ポリシーの変更を検証できます。</span><span class="sxs-lookup"><span data-stu-id="c21b1-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="c21b1-112">ポータル内のメッセージ Microsoft 365 Defenderは、管理センターのメッセージ トレースへのExchangeです。</span><span class="sxs-lookup"><span data-stu-id="c21b1-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="c21b1-113">詳細については、「モダン 管理センターのメッセージ トレース[」をExchangeしてください](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。</span><span class="sxs-lookup"><span data-stu-id="c21b1-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c21b1-114">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c21b1-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c21b1-115">メッセージ トレースを使用するには、組織の管理、コンプライアンス管理、またはヘルプ **デスクの役割グループ** のメンバー Exchange Online必要があります。 </span><span class="sxs-lookup"><span data-stu-id="c21b1-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="c21b1-116">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c21b1-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="c21b1-117">**注**: グループ内の対応する Azure Active Directory ロールMicrosoft 365 管理センターメンバーシップは、ユーザーに、Microsoft 365 の他の機能に対して必要なアクセス許可とアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c21b1-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c21b1-118">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c21b1-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="c21b1-119">メッセージ トレースの結果に表示されるメッセージの最大数は、選択したレポートの種類によって異なります (詳細については、「レポートの種類の選択 [」セクションを](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) 参照してください)。</span><span class="sxs-lookup"><span data-stu-id="c21b1-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="c21b1-120">[PowerShell またはスタンドアロン EOP PowerShell Exchange Online Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch)コマンドレットは、結果のすべてのメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="c21b1-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="c21b1-121">メッセージのトレースを開く</span><span class="sxs-lookup"><span data-stu-id="c21b1-121">Open message trace</span></span>

<span data-ttu-id="c21b1-122">[ポータル( Microsoft 365 Defender] で <https://security.microsoft.com> 、[メール] に移動し、&**のExchange** \> **追跡します**。</span><span class="sxs-lookup"><span data-stu-id="c21b1-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="c21b1-123">または、メッセージ トレース ページに直接移動するには、 を使用します <https://admin.exchange.microsoft.com/#/messagetrace> 。</span><span class="sxs-lookup"><span data-stu-id="c21b1-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="c21b1-124">この時点で、EAC のメッセージ トレースが開きます。</span><span class="sxs-lookup"><span data-stu-id="c21b1-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="c21b1-125">詳細については、「モダン 管理センターのメッセージ トレース[」をExchangeしてください](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。</span><span class="sxs-lookup"><span data-stu-id="c21b1-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
