---
title: メール フロー ダッシュボードのトップ ドメイン メール フローの状態の分析情報
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでトップ ドメイン メール フローの状態分析情報を使用して、MX レコードに関連するメール フローの問題をトラブルシューティングする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206970"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="0f34a-103">セキュリティ コンプライアンス センターのトップ ドメイン メール フロー&分析</span><span class="sxs-lookup"><span data-stu-id="0f34a-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0f34a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0f34a-104">**Applies to**</span></span>
- [<span data-ttu-id="0f34a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0f34a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0f34a-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0f34a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0f34a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f34a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0f34a-108">セキュリティ [](mail-flow-insights-v2.md)**センターの [メール フロー]** ダッシュボードの [トップ ドメイン メール フローの状態] &[は](https://protection.office.com)、組織の現在のメール フローの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="0f34a-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="0f34a-109">この分析情報は、メール フローの問題が発生しているドメインを特定してトラブルシューティング ***するのに*** 役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f34a-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="0f34a-110">たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部メールを受信できません。</span><span class="sxs-lookup"><span data-stu-id="0f34a-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードのトップ ドメイン フロー&ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="0f34a-112">ウィジェットの [**詳細の表示]** をクリックすると、各ドメインの状態の詳細を示すドメイン状態のフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f34a-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="0f34a-113">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0f34a-113">**Domain**</span></span>
- <span data-ttu-id="0f34a-114">**以前の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="0f34a-114">**Previous MX record**</span></span>
- <span data-ttu-id="0f34a-115">**現在の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="0f34a-115">**Current MX record**</span></span>
- <span data-ttu-id="0f34a-116">**電子メールの受信状態**</span><span class="sxs-lookup"><span data-stu-id="0f34a-116">**Email receiving status**</span></span>
- <span data-ttu-id="0f34a-117">**ドメインの** 状態 : 緑色のチェック マークは、現在の MX レコード (ウィジェットをクリックした時点) が、記録されている値と一致し、ドメインが過去 2 時間の間にメールを受信した状態を示します。</span><span class="sxs-lookup"><span data-stu-id="0f34a-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="0f34a-118">赤い X は、MX レコードが変更され、ドメインが過去 6 時間の間にメールを受信しきっていない状態を示します。</span><span class="sxs-lookup"><span data-stu-id="0f34a-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="0f34a-119">これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f34a-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="0f34a-120">ドメイン レジストラーまたは DNS ホスティング サービスに確認して、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないか確認します。</span><span class="sxs-lookup"><span data-stu-id="0f34a-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="0f34a-121">[詳細を表示 **] をクリック** すると、他のドメインの同じ情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f34a-121">You can click **View more** to see the same information for more domains.</span></span>

![トップ ドメイン メール フローの状態の分析情報の詳細の飛び出し](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="0f34a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f34a-123">See also</span></span>

<span data-ttu-id="0f34a-124">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="0f34a-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
