---
title: データ損失防止のレポートの表示
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Office 365 の DLP レポートを使用して、DLP ポリシーの一致、上書き、または誤検知の数を表示し、時間の流れによって上昇または下向きかどうかを確認します。
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928391"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="7a4fb-103">データ損失防止のレポートの表示</span><span class="sxs-lookup"><span data-stu-id="7a4fb-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="7a4fb-104">データ損失防止 (DLP) ポリシーを作成した後、意図した通り動作し、準拠を維持することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="7a4fb-105">セキュリティ コンプライアンス センターの DLP レポートを使用 &amp; すると、次の情報をすばやく表示できます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="7a4fb-106">**DLP ポリシーの一致** このレポートには、時間の間に一致する DLP ポリシーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="7a4fb-107">レポートは、日付、場所、ポリシー、またはアクションによってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="7a4fb-108">このレポートを使用すると、以下のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="7a4fb-109">テスト モードで実行しているときに、DLP ポリシーの調整や絞り込みができる。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="7a4fb-110">コンテンツと一致する特定のルールを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="7a4fb-111">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="7a4fb-112">組織の DLP ポリシーに違反するビジネス プロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="7a4fb-113">コンテンツに適用されているアクションを確認することで、DLP ポリシーのビジネスへの影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="7a4fb-114">特定の DLP ポリシーに関する一致箇所を表示することによって、そのポリシーのコンプライアンス遵守を確認します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="7a4fb-115">組織内のインシデントに貢献している上位ユーザーとリピート ユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="7a4fb-116">組織内の機密情報の種類の上位一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="7a4fb-117">**DLP インシデント** また、このレポートには、ポリシーの一致レポートなど、時間の間にポリシーの一致が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="7a4fb-118">ただし、ポリシーが一致するレポートには、ルール レベルでの一致が表示されます。たとえば、メールが 3 つの異なるルールに一致した場合、ポリシー一致レポートには 3 つの異なる行項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="7a4fb-119">対照的に、インシデント レポートにはアイテム レベルでの一致が表示されます。たとえば、電子メールが 3 つの異なるルールに一致した場合、インシデント レポートには、そのコンテンツの 1 つの行アイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="7a4fb-120">レポート数は集計方法が異なっていますので、ポリシー一致レポートは、特定のルールとの一致を識別し、DLP ポリシーを微調整する方が優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="7a4fb-121">インシデント レポートは、DLP ポリシーで問題となる特定のコンテンツを特定するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="7a4fb-122">**DLP の誤検知と上書き** DLP ポリシーでユーザーが上書きしたり、誤検知を報告したりできる場合、このレポートには時間のかかるインスタンスの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="7a4fb-123">レポートは、日付、場所、ポリシー、またはポリシーによってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="7a4fb-124">このレポートを使用すると、以下のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="7a4fb-125">多くの偽陽性が発生しているポリシーを確認し、DLP ポリシーの調整や絞り込みをします。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="7a4fb-126">ユーザーがポリシーを上書きしてポリシーのヒントを解決するときに送信する正当な理由を表示します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="7a4fb-127">ユーザーによる多くの上書きが行われることによって、DLP ポリシーと有効なビジネスプロセスとの競合を検出します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="7a4fb-128">すべての DLP レポートでは、最新の 4 か月間のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="7a4fb-129">最新のデータは、レポートに表示されるまで最大で 24 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="7a4fb-130">これらのレポートは、セキュリティ コンプライアンス センター レポート &amp; ダッシュボードで \> **確認** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP ポリシーがレポートと一致する](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="7a4fb-132">ユーザーがオーバーライドのために送信した位置合わせを表示する</span><span class="sxs-lookup"><span data-stu-id="7a4fb-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="7a4fb-133">DLP ポリシーでユーザーがそれを上書きすることを許可している場合は、誤検知および上書きレポートを使用して、ポリシーのヒントでユーザーが送信したテキストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![DLP 誤検知レポートおよび上書きレポートの詳細の位置合わせフィールド](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="7a4fb-135">インサイトと推奨事項に対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="7a4fb-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="7a4fb-136">レポートには分析情報と推奨事項が表示され、赤い警告アイコンをクリックすると、潜在的な問題に関する詳細を確認し、修復可能なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![インサイト アイコンをクリックして、実行する詳細とアクションを表示する](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="7a4fb-138">DLP レポートのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7a4fb-138">Permissions for DLP reports</span></span>

<span data-ttu-id="7a4fb-139">セキュリティ コンプライアンス センターで DLP レポートを&するには、次の情報を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="7a4fb-140">**管理者センター** のセキュリティ リーダー Exchange役割。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="7a4fb-141">既定では、この役割は管理センターの組織の管理およびセキュリティ リーダーの役割グループExchangeされます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="7a4fb-142">**セキュリティ コンプライアンス センターの [表示のみ] DLP** コンプライアンス&役割。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="7a4fb-143">既定では、この役割は、コンプライアンス 管理者、組織の管理、セキュリティ管理者、セキュリティ リーダーの各役割グループに割り当て&されます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="7a4fb-144">**管理センターの [受信者** の表示のみ] Exchange役割。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="7a4fb-145">既定では、この役割は、コンプライアンス管理、組織の管理、View-Only管理センターの組織の管理役割グループExchange割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="7a4fb-146">DLP レポートのコマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="7a4fb-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="7a4fb-147">セキュリティ &amp; コンプライアンス センターのほとんどのコマンドレットを使用するには、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="7a4fb-148">Connect PowerShell を使用 &amp; してセキュリティ コンプライアンス センターにアクセスする</span><span class="sxs-lookup"><span data-stu-id="7a4fb-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. <span data-ttu-id="7a4fb-149">これらのセキュリティ コンプライアンス センター [のコマンドレット &amp; を使用する](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7a4fb-149">Use any of these [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell)</span></span>
    
<span data-ttu-id="7a4fb-150">ただし、DLP レポートは、Exchange Online を含む Office 365 全体からデータを取り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="7a4fb-151">このため、DLP レポートのコマンドレットは、セキュリティ コンプライアンス センター Powershell ではなく、Exchange Online Powershell &amp; で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="7a4fb-152">したがって、DLP レポートのコマンドレットを使用するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="7a4fb-153">リモート PowerShell で Exchange Online に接続する</span><span class="sxs-lookup"><span data-stu-id="7a4fb-153">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="7a4fb-154">DLP レポート用のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a4fb-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="7a4fb-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="7a4fb-155">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [<span data-ttu-id="7a4fb-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="7a4fb-156">Get-DlpDetailReport</span></span>](/powershell/module/exchange/get-dlpdetailreport)
