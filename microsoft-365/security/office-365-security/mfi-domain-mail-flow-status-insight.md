---
title: メール フロー ダッシュボードのトップ ドメイン メール フローの状態に関する分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで、トップ ドメインのメール フロー状態の分析情報を使用して、MX レコードに関連するメール フローの問題をトラブルシューティングする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150209"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="2ce78-103">セキュリティ/コンプライアンス センターのトップ ドメイン メール フロー&分析情報</span><span class="sxs-lookup"><span data-stu-id="2ce78-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2ce78-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="2ce78-104">**Applies to**</span></span>
- [<span data-ttu-id="2ce78-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2ce78-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="2ce78-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="2ce78-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="2ce78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ce78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="2ce78-108">セキュリティ **/コンプライアンス センターの**[メール [](mail-flow-insights-v2.md)フロー] ダッシュボード [](https://protection.office.com)の [トップ ドメイン のメール フローの状態] の分析情報&組織の現在のメール フローの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ce78-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="2ce78-109">この分析情報は、メール フローの問題が発生しているドメインの特定と ***トラブルシューティングに役立*** ちます。</span><span class="sxs-lookup"><span data-stu-id="2ce78-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="2ce78-110">たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部電子メールを受信できません。</span><span class="sxs-lookup"><span data-stu-id="2ce78-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの&状態ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="2ce78-112">ウィジェットの [**詳細の** 表示] をクリックすると、各ドメインの状態に関する詳細を表示するドメイン状態のフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ce78-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="2ce78-113">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="2ce78-113">**Domain**</span></span>
- <span data-ttu-id="2ce78-114">**以前の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="2ce78-114">**Previous MX record**</span></span>
- <span data-ttu-id="2ce78-115">**現在の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="2ce78-115">**Current MX record**</span></span>
- <span data-ttu-id="2ce78-116">**電子メールの受信状態**</span><span class="sxs-lookup"><span data-stu-id="2ce78-116">**Email receiving status**</span></span>
- <span data-ttu-id="2ce78-117">**ドメインの** 状態 : 緑色のチェック マークは、(ウィジェットをクリックした時点で) 現在の MX レコードが記録されている値と一致し、ドメインが過去 2 時間以内にメールを受信したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2ce78-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="2ce78-118">赤い X は MX レコードが変更され、過去 6 時間以内にドメインが電子メールを受信しきっていない状態を示します。</span><span class="sxs-lookup"><span data-stu-id="2ce78-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="2ce78-119">これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ce78-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="2ce78-120">ドメイン レジストラーまたは DNS ホスティング サービスに確認して、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="2ce78-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="2ce78-121">[詳細を **表示] をクリック** すると、他のドメインの同じ情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2ce78-121">You can click **View more** to see the same information for more domains.</span></span>

![トップ ドメイン メール フローの状態の分析情報の詳細フライアウト](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="2ce78-123">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="2ce78-123">See also</span></span>

<span data-ttu-id="2ce78-124">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce78-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
