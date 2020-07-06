---
title: 悪意のある電子メールの検索と調査
keywords: TIMailData-インライン、セキュリティインシデント、インシデント、ATP PowerShell、電子メールマルウェア、侵害されたユーザー、電子メールフィッシング、電子メールマルウェア、電子メールヘッダーの読み取り、ヘッダーの読み取り、電子メールのヘッダーを開く
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 脅威の調査と応答機能を使用して、悪意のある電子メールを検索して調査する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ac44ab06aaff1618df2dfc1485d15a68458f385
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039414"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="e98b9-104">Office 365 で配信された悪意のある電子メールを調査および修復する</span><span class="sxs-lookup"><span data-stu-id="e98b9-104">Investigate and remediate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="e98b9-105">[Office 365 Advanced Threat Protection](office-365-atp.md)を使用すると、組織内のユーザーにリスクがあるというアクティビティを調査し、組織を保護するための処置を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="e98b9-106">たとえば、組織のセキュリティチームに属している場合は、配信された不審な電子メールメッセージを見つけて調査することができます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="e98b9-107">これを行うには、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e98b9-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="e98b9-108">Before you begin...</span></span>

<span data-ttu-id="e98b9-109">次の要件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e98b9-109">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="e98b9-110">組織では、 [Office 365 Advanced Threat Protection](office-365-atp.md)と[ライセンスがユーザーに割り当てら](../../admin/manage/assign-licenses-to-users.md)れています。</span><span class="sxs-lookup"><span data-stu-id="e98b9-110">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
    
- <span data-ttu-id="e98b9-111">組織の[監査ログ](../../compliance/turn-audit-log-search-on-or-off.md)が有効になっている。</span><span class="sxs-lookup"><span data-stu-id="e98b9-111">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="e98b9-112">組織には、スパム対策、マルウェア対策、フィッシング対策などに対して定義されたポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-112">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="e98b9-113">「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e98b9-113">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="e98b9-114">グローバル管理者であるか、セキュリティ管理者、またはセキュリティ/コンプライアンスセンターで割り当てられている検索および削除の役割を持っているかどうか &amp; 。</span><span class="sxs-lookup"><span data-stu-id="e98b9-114">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="e98b9-115">[セキュリティ/ &amp; コンプライアンスセンターの「アクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e98b9-115">See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="e98b9-116">操作によっては、新しいプレビューの役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-116">For some actions, you must also have a new Preview role assigned.</span></span> 

#### <a name="preview-role-permissions"></a><span data-ttu-id="e98b9-117">ロールの権限のプレビュー</span><span class="sxs-lookup"><span data-stu-id="e98b9-117">Preview role permissions</span></span>

<span data-ttu-id="e98b9-118">メッセージヘッダーの表示や電子メールメッセージのコンテンツのダウンロードなどの特定のアクションを実行するには、別の適切な役割グループに*プレビュー*が追加された新しい役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-118">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="e98b9-119">次の表で、必要な役割とアクセス許可を明確にします。</span><span class="sxs-lookup"><span data-stu-id="e98b9-119">The following table clarifies required roles and permissions.</span></span>

|<span data-ttu-id="e98b9-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e98b9-120">Activity</span></span>  |<span data-ttu-id="e98b9-121">役割グループ</span><span class="sxs-lookup"><span data-stu-id="e98b9-121">Role group</span></span> |<span data-ttu-id="e98b9-122">必要なプレビューの役割</span><span class="sxs-lookup"><span data-stu-id="e98b9-122">Preview role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e98b9-123">脅威エクスプローラー (およびリアルタイム検出) を使用して脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="e98b9-123">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |<span data-ttu-id="e98b9-124">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e98b9-124">Global Administrator</span></span> <br> <span data-ttu-id="e98b9-125">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="e98b9-125">Security Administrator</span></span> <br> <span data-ttu-id="e98b9-126">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="e98b9-126">Security Reader</span></span>     | <span data-ttu-id="e98b9-127">不要</span><span class="sxs-lookup"><span data-stu-id="e98b9-127">No</span></span>   |
|<span data-ttu-id="e98b9-128">脅威エクスプローラー (およびリアルタイム検出) を使用して、電子メールメッセージのヘッダーを表示し、検疫された電子メールメッセージをプレビューしてダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e98b9-128">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>    |<span data-ttu-id="e98b9-129">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e98b9-129">Global Administrator</span></span> <br> <span data-ttu-id="e98b9-130">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="e98b9-130">Security Administrator</span></span> <br><span data-ttu-id="e98b9-131">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="e98b9-131">Security Reader</span></span>   |       <span data-ttu-id="e98b9-132">不要</span><span class="sxs-lookup"><span data-stu-id="e98b9-132">No</span></span>  |
|<span data-ttu-id="e98b9-133">脅威エクスプローラーを使用してヘッダーを表示し、メールボックスに配信された電子メールメッセージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e98b9-133">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>     |<span data-ttu-id="e98b9-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e98b9-134">Global Administrator</span></span> <br><span data-ttu-id="e98b9-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="e98b9-135">Security Administrator</span></span> <br> <span data-ttu-id="e98b9-136">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="e98b9-136">Security Reader</span></span> <br> <span data-ttu-id="e98b9-137">Preview</span><span class="sxs-lookup"><span data-stu-id="e98b9-137">Preview</span></span>   |   <span data-ttu-id="e98b9-138">はい</span><span class="sxs-lookup"><span data-stu-id="e98b9-138">Yes</span></span>      |

> [!NOTE]
> <span data-ttu-id="e98b9-139">*プレビュー*は役割であり、役割グループではありません。Office 365 の既存の役割グループにプレビューの役割を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-139">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="e98b9-140">グローバル管理者の役割には、Microsoft 365 管理センター () が割り当てられ [https://admin.microsoft.com](https://admin.microsoft.com) ており、セキュリティ管理者およびセキュリティリーダーの役割はセキュリティ & コンプライアンスセンター () で割り当てられ [https://protection.office.com](https://protection.office.com) ます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-140">The Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="e98b9-141">役割とアクセス許可の詳細については、「[セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e98b9-141">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="e98b9-142">配信された疑わしいメールを見つけて削除する</span><span class="sxs-lookup"><span data-stu-id="e98b9-142">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="e98b9-143">脅威エクスプローラーは、メッセージの検索と削除、悪意のある電子メールの送信者の IP アドレスの識別、さらなる調査のためのインシデントの開始など、複数の目的に使用できる強力なレポートです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-143">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="e98b9-144">次の手順では、エクスプローラーを使用して受信者のメールボックスから悪意のある電子メールを検索し、削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-144">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="e98b9-145">現在、エクスプローラーでの既定の検索には Zapped の項目は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e98b9-145">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="e98b9-146">これは、マルウェアまたはフィッシングのようなビューなど、すべてのビューに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-146">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="e98b9-147">Zapped アイテムを含めるには、' 配信アクション ' セットを追加して、「削除による ZAP」を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-147">To include Zapped items you need to add a 'Delivery action' set to include 'Removed by ZAP'.</span></span> <span data-ttu-id="e98b9-148">すべてのオプションを含めると、Zapped アイテムを含むすべての配信アクションの結果が表示できます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-148">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="e98b9-149">[**脅威エクスプローラー] に移動**します。「 [https://protection.office.com](https://protection.office.com) Office 365 の職場または学校アカウントを使用してサインインする」に移動します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-149">**Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="e98b9-150">これにより、セキュリティコンプライアンスセンターに移動し &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-150">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="e98b9-151">左側のナビゲーションサイドリンクバーで、[**脅威管理**エクスプローラー] を選択し \> **Explorer**ます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-151">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![配信アクションと配信場所フィールドを含むエクスプローラ。](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. <span data-ttu-id="e98b9-153">**脅威エクスプローラーのビュー**: [**表示**] メニューで、[**すべての電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-153">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![脅威エクスプローラの [表示] メニュー、および電子メールのマルウェア、フィッシング、提出、およびすべての電子メールオプション。また、コンテンツマルウェアの場合もあります。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="e98b9-155">現在、*マルウェア*の表示は既定の設定であり、マルウェアの脅威が検出されたメールをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="e98b9-155">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="e98b9-156">*フィッシング*ビューは、フィッシングの場合と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-156">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="e98b9-157">ただし、*すべての電子メール*ビューは、脅威が検出されたかどうかにかかわらず、組織が受信するすべてのメールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-157">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="e98b9-158">想像できるように、これは大量のデータなので、このビューにはフィルターを適用するように求めるプレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-158">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="e98b9-159">(このビューは、ATP P2 のお客様に対してのみ使用できます。)</span><span class="sxs-lookup"><span data-stu-id="e98b9-159">(This view is only available for ATP P2 customers.)</span></span>

    <span data-ttu-id="e98b9-160">*提出*されたメールは、管理者またはユーザーが Microsoft に報告したすべてのメールを表示します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-160">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="e98b9-161">**脅威エクスプローラーでの検索とフィルター**: 検索バーのページの上部にフィルターが表示され、管理者が調査を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-161">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="e98b9-162">複数のフィルターを同時に適用して、検索を絞り込むために複数のコンマで区切られた値をフィルターに追加することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e98b9-162">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="e98b9-163">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e98b9-163">Remember:</span></span>
    - <span data-ttu-id="e98b9-164">フィルターは、ほとんどのフィルター条件を完全に一致させます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-164">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="e98b9-165">件名フィルターは、CONTAINS クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-165">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="e98b9-166">URL フィルターは、プロトコルを使用してもしなくても機能しません (例、</span><span class="sxs-lookup"><span data-stu-id="e98b9-166">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="e98b9-167">https)。</span><span class="sxs-lookup"><span data-stu-id="e98b9-167">https).</span></span>
    - <span data-ttu-id="e98b9-168">URL ドメイン、URL パス、URL ドメインおよびパスフィルターは、フィルター処理のためにプロトコルを必要としません。</span><span class="sxs-lookup"><span data-stu-id="e98b9-168">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="e98b9-169">フィルターの値を変更して関連性の高い結果を取得するたびに、[最新の情報に更新] アイコンをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-169">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="e98b9-170">**高度なフィルター**: これらのフィルターを使用すると、複雑なクエリを作成し、データセットをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-170">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="e98b9-171">[*高度なフィルター* ] をクリックすると、ポップアップが表示され、オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-171">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="e98b9-172">高度なフィルター処理は、検索機能に優れています。</span><span class="sxs-lookup"><span data-stu-id="e98b9-172">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="e98b9-173">ブール値フィルターは、*受信者*、*送信者*、および*送信者ドメイン*で導入され、管理者が値を除外して調査できるようにし**ています**。</span><span class="sxs-lookup"><span data-stu-id="e98b9-173">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="e98b9-174">このオプションは、[選択パラメーター*には含ま*れません] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-174">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="e98b9-175">管理者は、通知メールボックス、既定の返信メールボックスを調査から除外することができ**ない**ため、管理者が特定の件名 (subject = "アテンション") を検索して、その受信者が*defaultmail \@ contoso.com のどれ*にも設定されていない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e98b9-175">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail\@contoso.com*.</span></span> <span data-ttu-id="e98b9-176">これは厳密な値の検索です。</span><span class="sxs-lookup"><span data-stu-id="e98b9-176">This is an exact value search.</span></span>

   ![受信者-' には、"Advanced filter" が含まれていません。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="e98b9-178">*時間でのフィルター処理によっ*て、組織のセキュリティチームが迅速にドリルダウンされます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-178">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="e98b9-179">最短許容期間は30分です。</span><span class="sxs-lookup"><span data-stu-id="e98b9-179">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="e98b9-180">タイムフレーム (3 時間前に発生したなど) で疑わしいアクションを絞り込むことができる場合は、コンテキストを制限し、問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-180">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

  ![[時間によるフィルタリング] オプションを選択すると、セキュリティチームが処理する必要のあるデータの量を絞り込むことができ、最短時間は30分です。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="e98b9-182">**脅威エクスプローラーのフィールド**: 脅威エクスプローラは、*配信アクション*、*配信場所*、*特別なアクション*、*方向性*、*オーバーライド*、 *URL の脅威*など、より多くのセキュリティ関連のメール情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-182">**Fields in threat explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="e98b9-183">また、組織のセキュリティチームがより確実に調査を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-183">It also allows your organization's security team to investigate with a higher certainty.</span></span> 

    <span data-ttu-id="e98b9-184">*配信アクション*は、既存のポリシーまたは検出のために電子メールに対して実行されたアクションです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-184">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="e98b9-185">電子メールで実行可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-185">Here are the possible actions an email can take:</span></span>
    - <span data-ttu-id="e98b9-186">**配信**済み–電子メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーは直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-186">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="e98b9-187">**Junked** (迷惑メールに配信)-電子メールは、ユーザーの迷惑メールフォルダーまたは削除済みフォルダーに送信され、ユーザーは迷惑メールまたは削除されたフォルダー内の電子メールメッセージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-187">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="e98b9-188">[**ブロック**済み]: 検疫された、失敗した、または削除された電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e98b9-188">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="e98b9-189">(ユーザーが完全にアクセスすることはできません。)</span><span class="sxs-lookup"><span data-stu-id="e98b9-189">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="e98b9-190">[**置換**] –悪意のある添付ファイルが、添付ファイルが悪意のあるファイルに置き換えられた場合の電子メール</span><span class="sxs-lookup"><span data-stu-id="e98b9-190">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="e98b9-191">**配信先**: 配信場所フィルターは、管理者が悪意のあるメールが終了した場所と、それに対して実行された操作を把握するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-191">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="e98b9-192">結果のデータをスプレッドシートにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-192">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="e98b9-193">可能な配信場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-193">Possible delivery locations are:</span></span>
    - <span data-ttu-id="e98b9-194">**受信トレイまたはフォルダー** –メールルールに従って、受信トレイまたは特定のフォルダーに電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-194">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="e98b9-195">**オンプレミスまたは外部**–メールボックスはクラウドには存在しませんが、オンプレミスになっています。</span><span class="sxs-lookup"><span data-stu-id="e98b9-195">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="e98b9-196">**迷惑メールフォルダー** –電子メールはユーザーの迷惑メールフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-196">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="e98b9-197">**削除済みアイテムフォルダー** –電子メールはユーザーの [削除済みアイテム] フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-197">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="e98b9-198">**検疫**–検疫内の電子メール。ユーザーのメールボックスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="e98b9-198">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="e98b9-199">**Failed** –メールがメールボックスに到達できませんでした。</span><span class="sxs-lookup"><span data-stu-id="e98b9-199">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="e98b9-200">**削除**されました。メールフロー内の任意の場所で電子メールが失われました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-200">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="e98b9-201">**方向性**: このオプションを使用すると、セキュリティ運用チームがメールの送信元または移行先の「direction」によってフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-201">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="e98b9-202">方向性の値は、*受信*、*送信*、および*組織内*(外部から組織に入ってくるメールに対応するもの、組織外から送信されるもの、組織内に内部で送信されるものなど) です。</span><span class="sxs-lookup"><span data-stu-id="e98b9-202">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="e98b9-203">この情報によって、セキュリティ運用チームは、方向性の値 (例.</span><span class="sxs-lookup"><span data-stu-id="e98b9-203">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="e98b9-204">*受信*) と、送信者のドメイン (内部ドメインとして*表示*されます) は、明らかになります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-204">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="e98b9-205">方向性の値は独立しており、メッセージの追跡とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-205">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="e98b9-206">結果をスプレッドシートにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-206">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="e98b9-207">**Overrides**: このフィルターは、メールの [詳細] タブに表示される情報を取得し、それを使用*して、* メールの受信を許可またはブロックするための組織またはユーザーポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-207">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="e98b9-208">このフィルターの最も重要な点は、組織のセキュリティチームが構成によって配信された疑わしいメールの数を確認するのに役立つということです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-208">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="e98b9-209">これにより、許可とブロックを必要に応じて変更する機会が得られます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-209">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="e98b9-210">このフィルターの結果セットは、スプレッドシートにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-210">This result set of this filter can be exported to spreadsheet.</span></span>

|<span data-ttu-id="e98b9-211">脅威エクスプローラーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="e98b9-211">Threat Explorer Overrides</span></span>  | <span data-ttu-id="e98b9-212">意味</span><span class="sxs-lookup"><span data-stu-id="e98b9-212">What they mean</span></span>  |
|---------|---------|
|<span data-ttu-id="e98b9-213">組織のポリシーによって許可される</span><span class="sxs-lookup"><span data-stu-id="e98b9-213">Allowed by Org Policy</span></span>     |   <span data-ttu-id="e98b9-214">組織のポリシーによって指示されたメールボックスへのメールが許可されています。</span><span class="sxs-lookup"><span data-stu-id="e98b9-214">Mail was allowed into the mailbox as directed by the organization policy.</span></span>       |
|<span data-ttu-id="e98b9-215">組織のポリシーによるブロック</span><span class="sxs-lookup"><span data-stu-id="e98b9-215">Blocked by Org policy</span></span>      |  <span data-ttu-id="e98b9-216">組織のポリシーに従ってメールボックスへの配信がブロックされました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-216">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>    |
|<span data-ttu-id="e98b9-217">組織のポリシーによってブロックされるファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="e98b9-217">File extension blocked by Org Policy</span></span>     | <span data-ttu-id="e98b9-218">組織のポリシーによって指示されたように、ファイルはメールボックスへの配信がブロックされました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-218">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>        |
|<span data-ttu-id="e98b9-219">ユーザーポリシーによって許可される</span><span class="sxs-lookup"><span data-stu-id="e98b9-219">Allowed by User Policy</span></span>     | <span data-ttu-id="e98b9-220">メールボックスには、ユーザーポリシーによって指示されたとおりにメールが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-220">Mail was allowed into the mailbox as directed by the user policy.</span></span>        |
|<span data-ttu-id="e98b9-221">ユーザーポリシーによるブロック</span><span class="sxs-lookup"><span data-stu-id="e98b9-221">Blocked by User Policy</span></span>     | <span data-ttu-id="e98b9-222">ユーザーポリシーの指示に従ってメールボックスへの配信がブロックされました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-222">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>        |

<span data-ttu-id="e98b9-223">**Url の脅威**: url によって提示される脅威を示すために、[url の脅威] フィールドが電子メールの [*詳細*] タブに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e98b9-223">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="e98b9-224">URL によって提示される脅威には、*マルウェア*、*フィッシング*、*スパム*が含まれる可能性があります。脅威のない url は、[脅威] セクションでは*何も\*\*ありません*。</span><span class="sxs-lookup"><span data-stu-id="e98b9-224">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="e98b9-225">**電子メールのタイムラインビュー**: これ以上調査するには、セキュリティ運用チームが電子メールの詳細を掘り下げなければならない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-225">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="e98b9-226">電子メールタイムラインを使用すると、管理者は電子メールの配信から配信後のアクションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-226">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="e98b9-227">電子メールのタイムラインを表示するには、電子メールメッセージの件名をクリックし、[電子メールのタイムライン] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e98b9-227">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="e98b9-228">(概要や詳細など、パネル上の他の見出しの中に表示されます)。これらの結果は、スプレッドシートにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-228">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="e98b9-229">電子メールのタイムラインには、電子メールのすべての配信イベントと配信後イベントを示すテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-229">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="e98b9-230">その他のアクションが電子メールに存在しない場合、元の配信に対して1つのイベントが表示されます。これは、*ブロック*された場合など、verdict のように、*フィッシング*のようになります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-230">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="e98b9-231">管理者は、すべての電子メールのタイムラインをエクスポートできます。これには、タブおよび電子メールのすべての詳細 (たとえば、件名、送信者、受信者、ネットワーク、メッセージ ID など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-231">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="e98b9-232">メールが到着した後に発生したイベントを理解するために、さまざまな場所をチェックするのにかかる時間が短くなるため、電子メールのタイムラインはランダム化されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-232">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="e98b9-233">複数のイベントが電子メールで同時に発生するか、または同じ時刻になると、それらのイベントはタイムラインビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-233">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="e98b9-234">**プレビュー/ダウンロード**: 脅威エクスプローラは、疑わしい電子メールを調査するために必要な詳細をセキュリティ運用チームに提供します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-234">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="e98b9-235">セキュリティ運用チームは、次のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-235">Your security operations team can either:</span></span>

    - <span data-ttu-id="e98b9-236">[配信アクションと場所を確認](#check-the-delivery-action-and-location)します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-236">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="e98b9-237">[メールのタイムラインを表示](#view-the-timeline-of-your-email)します。</span><span class="sxs-lookup"><span data-stu-id="e98b9-237">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

    ##### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="e98b9-238">配信アクションと場所を確認する</span><span class="sxs-lookup"><span data-stu-id="e98b9-238">Check the delivery action and location</span></span>

    <span data-ttu-id="e98b9-239">[脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)で、[前の**配信状態**] 列ではなく、**配信アクション**と**配信場所**の列が作成されました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-239">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="e98b9-240">この結果、電子メールメッセージがどこにあるかをより完全に把握できます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-240">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="e98b9-241">この変更の目的の1つは、調査をセキュリティ運用チームにとって簡単にすることですが、最終的に問題の電子メールメッセージの場所をひとめで把握することになります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-241">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

    <span data-ttu-id="e98b9-242">配信状態は、次の2つの列に分けられました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-242">Delivery Status is now broken out into two columns:</span></span>

    - <span data-ttu-id="e98b9-243">**配信アクション**-この電子メールの状態は何ですか。</span><span class="sxs-lookup"><span data-stu-id="e98b9-243">**Delivery action** - What is the status of this email?</span></span>

    - <span data-ttu-id="e98b9-244">**配信場所**-この電子メールは、結果としてルーティングされましたか?</span><span class="sxs-lookup"><span data-stu-id="e98b9-244">**Delivery location** - Where was this email routed as a result?</span></span>

    <span data-ttu-id="e98b9-245">配信アクションは、既存のポリシーまたは検出のために電子メールに対して実行されたアクションです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-245">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="e98b9-246">電子メールで実行可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-246">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="e98b9-247">**配信**済み–電子メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーは直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-247">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

    - <span data-ttu-id="e98b9-248">**Junked** –電子メールがユーザーの迷惑フォルダーまたは削除されたフォルダーに送信され、ユーザーは迷惑メールまたは削除されたフォルダー内の電子メールメッセージにアクセスできる。</span><span class="sxs-lookup"><span data-stu-id="e98b9-248">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

    - <span data-ttu-id="e98b9-249">[**ブロック**済み]: 検疫された、失敗した、または削除された電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e98b9-249">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="e98b9-250">(ユーザーが完全にアクセスすることはできません。)</span><span class="sxs-lookup"><span data-stu-id="e98b9-250">(This is completely inaccessible by the user.)</span></span>

    - <span data-ttu-id="e98b9-251">[**置換**] –悪意のある添付ファイルが、添付ファイルが悪意のあるファイルに置き換えられた場合の電子メール。</span><span class="sxs-lookup"><span data-stu-id="e98b9-251">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
    <span data-ttu-id="e98b9-252">[配信場所] には、配信後に実行されるポリシーと検出の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-252">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="e98b9-253">配信アクションにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="e98b9-253">It's linked to a Delivery Action.</span></span> <span data-ttu-id="e98b9-254">このフィールドは、問題のメールが検出されたときに実行される処理を把握するために追加されました。</span><span class="sxs-lookup"><span data-stu-id="e98b9-254">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="e98b9-255">配信場所の指定可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-255">Here are the possible values of delivery location:</span></span>

    - <span data-ttu-id="e98b9-256">**受信トレイまたはフォルダー** –メールが受信トレイまたはフォルダーにある (メールルールに従って)。</span><span class="sxs-lookup"><span data-stu-id="e98b9-256">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

    - <span data-ttu-id="e98b9-257">**オンプレミスまたは外部**–メールボックスがクラウド上に存在していますが、オンプレミスになっています。</span><span class="sxs-lookup"><span data-stu-id="e98b9-257">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

    - <span data-ttu-id="e98b9-258">**迷惑メールフォルダー** –電子メールはユーザーの迷惑メールフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-258">**Junk folder** – The email is in a user's Junk folder.</span></span>

    - <span data-ttu-id="e98b9-259">**削除済みアイテムフォルダー** –電子メールはユーザーの [削除済みアイテム] フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="e98b9-259">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

    - <span data-ttu-id="e98b9-260">**検疫**–検疫内の電子メール。ユーザーのメールボックスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="e98b9-260">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

    - <span data-ttu-id="e98b9-261">**Failed** –メールがメールボックスに到達できませんでした。</span><span class="sxs-lookup"><span data-stu-id="e98b9-261">**Failed** – The email failed to reach the mailbox.</span></span>

    - <span data-ttu-id="e98b9-262">**削除**–メールフロー内の任意の場所に電子メールが失われます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-262">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

     ##### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="e98b9-263">メールのタイムラインを表示する</span><span class="sxs-lookup"><span data-stu-id="e98b9-263">View the timeline of your email</span></span>
  
     <span data-ttu-id="e98b9-264">**電子メールタイムライン**は、セキュリティ運用チームにとって使いやすいようにするための脅威エクスプローラーのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e98b9-264">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="e98b9-265">電子メールで複数のイベントが同時に発生するか、または同じ時刻に近いときに、これらのイベントがタイムラインビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-265">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="e98b9-266">電子メールへの配信後に発生する一部のイベントは、[**特殊なアクション**] 列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="e98b9-266">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="e98b9-267">メールメッセージのタイムラインからの情報と、配信後に実行された特別な操作によって、管理者はポリシーと脅威の処理についての洞察を得ることができます (メールがルーティングされた場所や、場合によっては最終的な評価は何かなど)。</span><span class="sxs-lookup"><span data-stu-id="e98b9-267">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view. 
    
    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was. 

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body) 

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps: 

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 
    
2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table. 

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a><span data-ttu-id="e98b9-268">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e98b9-268">Related topics</span></span>

[<span data-ttu-id="e98b9-269">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e98b9-269">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)
  
[<span data-ttu-id="e98b9-270">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="e98b9-270">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e98b9-271">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="e98b9-271">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
