---
title: メールフローダッシュボードのトップドメインメールフローのステータスの洞察
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインのメールフロー状態の洞察を使用して、MX レコードに関連するメールフローの問題のトラブルシューティングを行う方法について説明します。
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920586"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="e12eb-103">セキュリティ & コンプライアンスセンターでの上位ドメインメールフローのステータスの洞察</span><span class="sxs-lookup"><span data-stu-id="e12eb-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e12eb-104">[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)にある **上位ドメインのメールフローの状態** に関する洞察は、組織の現在のメールフローの状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="e12eb-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="e12eb-105">この洞察は、\* *_メールフロー_* の問題が発生しているドメインを特定し、トラブルシューティングするのに役立つ情報です。</span><span class="sxs-lookup"><span data-stu-id="e12eb-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow_* _ issues.</span></span> <span data-ttu-id="e12eb-106">たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部メールを受信できません。</span><span class="sxs-lookup"><span data-stu-id="e12eb-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのトップドメインフロー状態ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="e12eb-108">ウィジェットの [_ *View details* ] をクリックすると、 **ドメイン状態** ポップアップが表示され、各ドメインの状態の詳細がわかります。</span><span class="sxs-lookup"><span data-stu-id="e12eb-108">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="e12eb-109">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="e12eb-109">**Domain**</span></span>
- <span data-ttu-id="e12eb-110">**以前の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="e12eb-110">**Previous MX record**</span></span>
- <span data-ttu-id="e12eb-111">**現在の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="e12eb-111">**Current MX record**</span></span>
- <span data-ttu-id="e12eb-112">**受信した電子メールの状態**</span><span class="sxs-lookup"><span data-stu-id="e12eb-112">**Email receiving status**</span></span>
- <span data-ttu-id="e12eb-113">**ドメインの状態** : 緑のチェックマークは、現在の MX レコード (ウィジェットをクリックしたとき) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="e12eb-113">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="e12eb-114">赤の X は MX レコードが変更されたことを示し、ドメインは過去6時間以内に電子メールを受信していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e12eb-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="e12eb-115">これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e12eb-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="e12eb-116">ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e12eb-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="e12eb-117">[ **詳細表示** ] をクリックすると、他のドメインについても同じ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e12eb-117">You can click **View more** to see the same information for more domains.</span></span>

![上位ドメインのメールフローの状態に関する詳細ポップアップ](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="e12eb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e12eb-119">See also</span></span>

<span data-ttu-id="e12eb-120">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12eb-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
