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
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインのメールフロー状態の洞察を使用して、電子メールドメイン内の MX レコードに関連するメールフローの問題のトラブルシューティングを行う方法を学習できます。
ms.openlocfilehash: d4abc311e96df87894d5f059328f1a16a00190b8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877512"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="0da86-103">セキュリティ & コンプライアンスセンターでの上位ドメインメールフローのステータスの洞察</span><span class="sxs-lookup"><span data-stu-id="0da86-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0da86-104">[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)にある **上位ドメインメールフローの状態** に関する洞察は、メールフローの観点から、組織のドメインの現在の状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="0da86-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="0da86-105">この洞察により、\* *_メールフローに影響を与える_* ドメインを特定してトラブルシューティングするのに役立ちます。 (たとえば、外部電子メールを受信できない)、特にドメインの有効期限、または間違った MX レコードがあるドメイン。</span><span class="sxs-lookup"><span data-stu-id="0da86-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow impacting_* _ issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのトップドメインフロー状態ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="0da86-107">ウィジェットの [_ *View details* ] をクリックすると、 **ドメイン状態** ポップアップが表示され、各ドメインの状態の詳細がわかります。</span><span class="sxs-lookup"><span data-stu-id="0da86-107">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="0da86-108">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0da86-108">**Domain**</span></span>
- <span data-ttu-id="0da86-109">**以前の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="0da86-109">**Previous MX record**</span></span>
- <span data-ttu-id="0da86-110">**現在の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="0da86-110">**Current MX record**</span></span>
- <span data-ttu-id="0da86-111">**受信した電子メールの状態**</span><span class="sxs-lookup"><span data-stu-id="0da86-111">**Email receiving status**</span></span>
- <span data-ttu-id="0da86-112">**ドメインの状態** : 緑のチェックマークは、現在の MX レコード (ウィジェットをクリックしたとき) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="0da86-112">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="0da86-113">赤の X は、MX レコードが変更されたこと、および過去6時間以内にドメインがメールを受信していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="0da86-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="0da86-114">これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0da86-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="0da86-115">ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0da86-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="0da86-116">[ **詳細表示** ] をクリックすると、他のドメインについても同じ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0da86-116">You can click **View more** to see the same information for more domains.</span></span>

![上位ドメインのメールフローの状態に関する詳細ポップアップ](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="0da86-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0da86-118">Related topics</span></span>

<span data-ttu-id="0da86-119">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da86-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
