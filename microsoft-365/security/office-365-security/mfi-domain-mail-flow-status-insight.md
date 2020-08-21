---
title: メール フロー ダッシュボードの上位ドメインのメール フローの状態に関する分析情報
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで上位ドメインのメール フローの状態のインサイトを使用して、メール ドメイン内の MX レコードに関連するメール フロー問題のトラブルシューティングを行う方法を学習できます。
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827017"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="9a5e4-103">セキュリティ センターの上位ドメインのメール フローの状態&分析情報</span><span class="sxs-lookup"><span data-stu-id="9a5e4-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="9a5e4-104">セキュリティ &**コンプライアンス センターの**メール フロー ダッシュボード[Mail flow dashboard](mail-flow-insights-v2.md)で上位ドメインのメール フロー状態の分析情報は、メール フローの点で組織のドメインの現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="9a5e4-105">この分析情報は、問題に影響を与えるメール フロー (外部メールを受信できない***mail flow impacting***など) を特定してトラブルシューティングする際に役立ちます。特に、ドメインの有効期限または MX レコードが正しくないドメイン。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの上位ドメイン フローの状態ウィジ&イジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="9a5e4-107">ウィジェ **ットの [** 詳細の表示] をクリックすると、 **各ドメイン** の状態に関する詳細が [ドメインの状態] ポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="9a5e4-108">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-108">**Domain**</span></span>
- <span data-ttu-id="9a5e4-109">**以前の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-109">**Previous MX record**</span></span>
- <span data-ttu-id="9a5e4-110">**現在の MX レコード**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-110">**Current MX record**</span></span>
- <span data-ttu-id="9a5e4-111">**メールの受信状態**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-111">**Email receiving status**</span></span>
- <span data-ttu-id="9a5e4-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="9a5e4-113">赤い X は、MX レコードが変更されたことを示し、そのドメインが現在 6 時間前にメールを受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="9a5e4-114">これは、ドメインの有効期限が切れていること、または MX レコードが正しく更新されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="9a5e4-115">ドメイン レジストラーか DNS ホスティング サービスに確認して、ドメインの有効期限が切れていないか、ドメインの MX レコードが正しくないかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="9a5e4-116">[詳細表示] **をクリックすると** 、その他のドメインに対して同じ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-116">You can click **View more** to see the same information for more domains.</span></span>

![[トップ ドメインのメール フロー状態] の詳細ポップアップ](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="9a5e4-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9a5e4-118">Related topics</span></span>

<span data-ttu-id="9a5e4-119">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="9a5e4-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
