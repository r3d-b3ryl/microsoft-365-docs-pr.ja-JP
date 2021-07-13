---
title: 既定の DLP ポリシーの使用を開始する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: レポートを使用して組織の既定のデータ損失防止 (DLP) ポリシーを絞り込む方法について学習します。
ms.openlocfilehash: 98f2a95d66860695034fa958969d1c195e9d58be
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408962"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="61fca-103">既定の DLP ポリシーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="61fca-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="61fca-104">最初のデータ損失防止 (DLP) ポリシーを作成する前に、DLP は既定のポリシーを使用して機密情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="61fca-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="61fca-105">この既定のポリシーと推奨事項 (以下に示す) は、メールまたはクレジット カード番号を含むドキュメントが組織外のユーザーと共有されたときに通知することで、機密コンテンツを安全に保つのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="61fca-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="61fca-106">この推奨事項は、セキュリティ コンプライアンス センター **の [ホーム** ] ページに &amp; 表示されます。</span><span class="sxs-lookup"><span data-stu-id="61fca-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="61fca-107">このウィジェットを使用すると、機密情報が共有された時間と量をすばやく表示し、クリックまたは 2 回で既定の DLP ポリシーを絞り込めます。</span><span class="sxs-lookup"><span data-stu-id="61fca-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="61fca-108">既定の DLP ポリシーは完全にカスタマイズ可能なので、いつでも編集できます。</span><span class="sxs-lookup"><span data-stu-id="61fca-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="61fca-109">最初に推奨事項が表示しない場合は、[おすすめ] セクションの下部にある **[+More]** **をクリック** してください。</span><span class="sxs-lookup"><span data-stu-id="61fca-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![[共有コンテンツをさらに保護する] という名前のウィジェット](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="61fca-111">レポートを表示し、既定の DLP ポリシーを絞り込む</span><span class="sxs-lookup"><span data-stu-id="61fca-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="61fca-112">ユーザーが組織外のユーザーと機密情報を共有しているというウィジェットが表示された場合は、下部にある **[DLP ポリシー** の絞り込み] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61fca-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="61fca-113">詳細レポートには、過去 30 日間にクレジット カード番号を含むコンテンツが共有された時間と量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61fca-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="61fca-114">ルールの一致には、ウィジェットに表示するには最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61fca-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="61fca-115">機密情報を保護するために、既定の DLP ポリシーは次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="61fca-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="61fca-116">少なくとも 1 つのクレジット カード番号を含む Exchange、SharePoint、および OneDrive のコンテンツが組織外のユーザーと共有される場合を検出します。</span><span class="sxs-lookup"><span data-stu-id="61fca-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="61fca-117">この機密情報を組織外のユーザーと共有しようとすると、ポリシー ヒントを表示し、ユーザーに電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="61fca-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="61fca-118">これらのオプションの詳細については、「電子メール通知を送信する」と「DLP ポリシーのポリシー [ヒントを表示する」を参照してください](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="61fca-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="61fca-119">詳細なアクティビティ レポートを生成して、組織外のユーザーとコンテンツを共有したユーザーや、コンテンツをいつ共有したのかなどについて追跡できます。</span><span class="sxs-lookup"><span data-stu-id="61fca-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="61fca-120">DLP レポートと [監査ログ データ](view-the-dlp-reports.md)[(アクティビティ](search-the-audit-log-in-security-and-compliance.md)   =  **DLP)** を使用して、この情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="61fca-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="61fca-121">既定の DLP ポリシーをすばやく絞り込むには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="61fca-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="61fca-122">ユーザーが組織外のユーザーとこの機密情報を共有するときに、インシデント レポートの電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="61fca-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="61fca-123">電子メール インシデント レポートに他のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="61fca-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="61fca-124">機密情報を含むコンテンツへのアクセスをブロックしますが、必要に応じてユーザーが上書きして共有または送信できます。</span><span class="sxs-lookup"><span data-stu-id="61fca-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="61fca-125">インシデント レポートまたはアクセスの制限の詳細については、「データ損失防止 [リファレンス」を参照してください](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="61fca-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="61fca-126">これらのオプションを後で変更する場合は、既定の DLP ポリシーをいつでも編集できます。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61fca-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![設定共有コンテンツをさらに保護するという名前のウィジェットの場合](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="61fca-128">既定の DLP ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="61fca-128">Edit the default DLP policy</span></span>

<span data-ttu-id="61fca-129">このポリシーは Default **DLP ポリシーという名前で**、セキュリティ コンプライアンスセンターの [ポリシー] ページの [データ損失防止] の下に &amp; 表示されます。</span><span class="sxs-lookup"><span data-stu-id="61fca-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="61fca-130">このポリシーは完全にカスタマイズ可能で、最初から自分で作成した DLP ポリシーと同じです。</span><span class="sxs-lookup"><span data-stu-id="61fca-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="61fca-131">また、ポリシーをオフまたは削除して、ユーザーがポリシー ヒントや電子メール通知を受け取らなくなりました。</span><span class="sxs-lookup"><span data-stu-id="61fca-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![既定の DLP ポリシーという名前の DLP ポリシー](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="61fca-133">ウィジェットが表示され、表示されない場合</span><span class="sxs-lookup"><span data-stu-id="61fca-133">When the widget does and does not appear</span></span>

<span data-ttu-id="61fca-134">共有コンテンツ **をさらに保護するという名前のウィジェット** は、セキュリティ コンプライアンス センターの **ホーム** ページの [推奨されるユーザー] セクションに &amp; 表示されます。</span><span class="sxs-lookup"><span data-stu-id="61fca-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="61fca-135">このウィジェットは、次の場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="61fca-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="61fca-136">セキュリティ コンプライアンス センターまたは管理センターには、データ &amp; 損失防止Exchangeはありません。</span><span class="sxs-lookup"><span data-stu-id="61fca-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="61fca-137">このウィジェットは、DLP の使用を開始するのに役立つウィジェットなので、DLP ポリシーが既に設定されている場合は表示されません。</span><span class="sxs-lookup"><span data-stu-id="61fca-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="61fca-138">過去 30 日間に、少なくとも 1 つのクレジット カードを含むコンテンツが組織外のユーザーと共有されています。</span><span class="sxs-lookup"><span data-stu-id="61fca-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="61fca-139">ルールの一致は、ウィジェットで使用するには最大 48 時間かかる場合があります。そのため、外部で共有される機密情報が検出された後、推奨事項が表示されるには最大 2 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61fca-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="61fca-140">最後に、ウィジェットを使用して既定の DLP ポリシーを絞り込むと、ウィジェットはホーム ページから **消** えます。</span><span class="sxs-lookup"><span data-stu-id="61fca-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

