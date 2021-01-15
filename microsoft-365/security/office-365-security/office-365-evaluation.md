---
title: Microsoft Defender を 365 Office評価する
description: 評価モードOffice 365 用の Defender は、マルウェアなどの評価を記録するが、メッセージには作用しない Office 365 電子メール ポリシー用の Defender を作成します。
keywords: evaluate Office 365, Microsoft Defender for Office 365, office 365 evaluation, try office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8f105215b23ec49318c133714e758e2a2a9c1df
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870923"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="d33ec-104">Microsoft Defender を 365 Office評価する</span><span class="sxs-lookup"><span data-stu-id="d33ec-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="d33ec-105">Microsoft Defender for Office 365 評価版はパブリック プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="d33ec-105">Microsoft Defender for Office 365 evaluation is in public preview.</span></span> <span data-ttu-id="d33ec-106">このプレビュー バージョンは、サービス レベルアグリーメントなしで提供されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="d33ec-107">一部の機能がサポートされていないか、機能が制限されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="d33ec-108">包括的なセキュリティ製品評価を実施すると、アップグレードと購入に関する情報に基づいた意思決定を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-108">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="d33ec-109">セキュリティ製品の機能を試して、セキュリティ運用チームが日常業務に役立つ方法を評価するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-109">It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="d33ec-110">[Microsoft Defender for Office 365](office-365-atp.md)の評価エクスペリエンスは、セキュリティ ソリューションの機能の評価に集中できるよう、デバイスと環境の構成の複雑さを排除するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d33ec-110">The [Microsoft Defender for Office 365](office-365-atp.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the security solution.</span></span> <span data-ttu-id="d33ec-111">これは電子メール保護にのみ適用され、SharePoint、Office Teams には適用されません。</span><span class="sxs-lookup"><span data-stu-id="d33ec-111">It only applies to email protection and not SharePoint, Office Clients, or Teams.</span></span>

<span data-ttu-id="d33ec-112">microsoft Defender for Office 365 をサポートするライセンスをまだお持ちでない場合は、無料の [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 日間の評価を開始し、Office 365 セキュリティ & コンプライアンス センター https://protection.office.com/homepage) (.</span><span class="sxs-lookup"><span data-stu-id="d33ec-112">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="d33ec-113">迅速なセットアップが楽しめ、必要に応じて簡単にオフにできます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-113">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="d33ec-114">評価のしくみ</span><span class="sxs-lookup"><span data-stu-id="d33ec-114">How the evaluation works</span></span>

<span data-ttu-id="d33ec-115">評価モードOffice 365 用の Defender は、マルウェアなどの評価を記録するが、メッセージには作用しない Office 365 電子メール ポリシー用の Defender を作成します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-115">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don't act on messages.</span></span> <span data-ttu-id="d33ec-116">MX レコード構成を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d33ec-116">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="d33ec-117">評価モードでは、 [安全な添付ファイル](atp-safe-attachments.md)、安全な [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [リンク](atp-safe-links.md)、フィッシング詐欺対策の偽装ポリシーがユーザーに代わって設定されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-117">With evaluation mode, [Safe Attachments](atp-safe-attachments.md), [Safe Links](atp-safe-links.md), and [anti-phishing impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are set up on your behalf.</span></span> <span data-ttu-id="d33ec-118">365 Office用のすべての Defender は、バックグラウンドで非強制モードで作成され、表示されません。</span><span class="sxs-lookup"><span data-stu-id="d33ec-118">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="d33ec-119">セットアップの一環として、評価モードではコネクタの [拡張フィルターも構成されます](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="d33ec-119">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="d33ec-120">IP アドレスと送信者情報を保持することでフィルターの精度が向上します。それ以外の場合、メールが Office 365 の Defender の前にある電子メール セキュリティ ゲートウェイ (DEFENDER) を通過すると失われます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-120">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="d33ec-121">拡張フィルタリングは、Exchange Online Protection (EOP) のスパム対策およびフィッシング対策ポリシーのフィルタリング精度も向上します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-121">Enhanced Filtering also improves the filtering accuracy for your Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="d33ec-122">一部のサポートされていないシナリオに対する潜在的な運用への影響を最小限に抑えるために、Spam Confidence Level (SCL) を -1 に設定するトランスポート ルールを作成することで、すべての EOP フィルタリングをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-122">To minimize potential production impact on some unsupported scenarios, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="d33ec-123">詳細 [については、「EAC を使用して、メッセージの SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を設定するメール フロー ルールを作成する」   を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d33ec-123">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="d33ec-124">評価モードを設定すると、ポリシーが実装された場合にブロックされるメッセージを数値化する最大 90 日間のデータ (削除、迷惑メールへの送信、検疫など) で毎日レポートが更新されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-124">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked if the policies were implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="d33ec-125">レポートは、365 および EOP の検出Office Defender すべてについて生成されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-125">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="d33ec-126">これらは検出テクノロジ (偽装など) ごとに集計され、時間範囲でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-126">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="d33ec-127">さらに、カスタム ピボットを作成したり、脅威エクスプローラーを使用して詳細なメッセージを作成したりするために、メッセージ レポートをオンデマンドで作成できます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-127">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="d33ec-128">簡素化されたセットアップ エクスペリエンスを使用すると、次の作業に集中できます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-128">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="d33ec-129">評価の実行</span><span class="sxs-lookup"><span data-stu-id="d33ec-129">Running the evaluation</span></span>
- <span data-ttu-id="d33ec-130">詳細レポートの取得</span><span class="sxs-lookup"><span data-stu-id="d33ec-130">Getting a detailed report</span></span>
- <span data-ttu-id="d33ec-131">アクションに関するレポートの分析</span><span class="sxs-lookup"><span data-stu-id="d33ec-131">Analyzing the report for action</span></span>
- <span data-ttu-id="d33ec-132">評価結果の提示</span><span class="sxs-lookup"><span data-stu-id="d33ec-132">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d33ec-133">開始する前に</span><span class="sxs-lookup"><span data-stu-id="d33ec-133">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="d33ec-134">ライセンス</span><span class="sxs-lookup"><span data-stu-id="d33ec-134">Licensing</span></span>

<span data-ttu-id="d33ec-135">評価にアクセスするには、ライセンス要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-135">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="d33ec-136">次のライセンスが機能します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-136">Any of the following licenses will work:</span></span>

- <span data-ttu-id="d33ec-137">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="d33ec-137">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="d33ec-138">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="d33ec-138">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="d33ec-139">Microsoft 365 E5、Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="d33ec-139">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="d33ec-140">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="d33ec-140">Office 365 E5</span></span>

<span data-ttu-id="d33ec-141">これらのライセンスが 1 つも持たなかった場合は、試用版ライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-141">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="d33ec-142">試用版</span><span class="sxs-lookup"><span data-stu-id="d33ec-142">Trial</span></span>

<span data-ttu-id="d33ec-143">Office 365 用の Microsoft Defender の試用版ライセンスを取得するには、課金管理者の役割またはグローバル管理者の役割 **が必要です**。</span><span class="sxs-lookup"><span data-stu-id="d33ec-143">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="d33ec-144">グローバル管理者ロールを持つユーザーにアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-144">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="d33ec-145">サブスクリプションとライセンスについて</span><span class="sxs-lookup"><span data-stu-id="d33ec-145">Learn about subscriptions and licenses</span></span>](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

<span data-ttu-id="d33ec-146">適切なロールを取得したら、課金サービス > に移動して、Microsoft 365 管理センターで Office 365 (プラン 2) 用の Microsoft Defender の試用版ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-146">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="d33ec-147">試用版には、25 ライセンスの 30 日間の無料試用版が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d33ec-147">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="d33ec-148">[microsoft Defender for Office 365 (プラン 2) の試用版を取得します](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="d33ec-148">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="d33ec-149">高度な脅威を監視および報告する評価を含む 30 日間のウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-149">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="d33ec-150">また、365 の機能に対する完全な Defender を使用する場合は、有料サブスクリプションをOfficeすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-150">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="d33ec-151">Roles</span><span class="sxs-lookup"><span data-stu-id="d33ec-151">Roles</span></span>

<span data-ttu-id="d33ec-152">Exchange Online の役割は、評価モードで 365 Office Defender をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-152">Exchange Online roles are required to set up Defender for Office 365 in evaluation mode.</span></span>

- [<span data-ttu-id="d33ec-153">Exchange Online のアクセス許可について</span><span class="sxs-lookup"><span data-stu-id="d33ec-153">Learn about permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [<span data-ttu-id="d33ec-154">管理者ロールの割り当てについて</span><span class="sxs-lookup"><span data-stu-id="d33ec-154">Learn about assigning admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

<span data-ttu-id="d33ec-155">次の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="d33ec-155">The following roles are needed:</span></span>

|<span data-ttu-id="d33ec-156">Task</span><span class="sxs-lookup"><span data-stu-id="d33ec-156">Task</span></span>|<span data-ttu-id="d33ec-157">Role</span><span class="sxs-lookup"><span data-stu-id="d33ec-157">Role</span></span>|
|---|---|
|<span data-ttu-id="d33ec-158">無料試用版を取得するか、Microsoft Defender を Office 365 用に購入する (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="d33ec-158">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="d33ec-159">課金管理者ロールまたはグローバル管理者ロール</span><span class="sxs-lookup"><span data-stu-id="d33ec-159">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="d33ec-160">評価ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d33ec-160">Create evaluation policy</span></span>|<span data-ttu-id="d33ec-161">"Remote and Accepted Domains/リモートドメインと受け入れドメイン" 役割セキュリティ管理者ロール</span><span class="sxs-lookup"><span data-stu-id="d33ec-161">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="d33ec-162">評価ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="d33ec-162">Edit evaluation policy</span></span>|<span data-ttu-id="d33ec-163">"Remote and Accepted Domains/リモートドメインと受け入れドメイン" 役割セキュリティ管理者ロール</span><span class="sxs-lookup"><span data-stu-id="d33ec-163">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="d33ec-164">評価ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d33ec-164">Delete evaluation policy</span></span>|<span data-ttu-id="d33ec-165">"Remote and Accepted Domains/リモートドメインと受け入れドメイン" 役割セキュリティ管理者ロール</span><span class="sxs-lookup"><span data-stu-id="d33ec-165">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="d33ec-166">評価レポートの表示</span><span class="sxs-lookup"><span data-stu-id="d33ec-166">View evaluation report</span></span>|<span data-ttu-id="d33ec-167">セキュリティ管理者ロールまたはセキュリティ閲覧者ロール</span><span class="sxs-lookup"><span data-stu-id="d33ec-167">Security admin role OR Security reader role</span></span>|
|


### <a name="enhanced-filtering"></a><span data-ttu-id="d33ec-168">拡張フィルタリング</span><span class="sxs-lookup"><span data-stu-id="d33ec-168">Enhanced filtering</span></span>

<span data-ttu-id="d33ec-169">一括保護やスパム保護などの Exchange Online Protection ポリシーは変わりません。</span><span class="sxs-lookup"><span data-stu-id="d33ec-169">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="d33ec-170">メッセージ配信も同じままです。</span><span class="sxs-lookup"><span data-stu-id="d33ec-170">Message delivery will also remain the same.</span></span> <span data-ttu-id="d33ec-171">ただし、この評価ではコネクタの拡張フィルター処理が有効にされ、バイパスされていない限り、メール フローと Exchange Online Protection ポリシーに影響します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-171">However, the evaluation turns on enhanced filtering for connectors, which will impact your mail flow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="d33ec-172">コネクタのフィルター処理が強化され、テナントはスプーフィング対策保護を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-172">Enhanced filtering for connectors will allow tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="d33ec-173">コネクタの拡張フィルタリングを有効にせずに電子メール セキュリティ ゲートウェイ (RF) を使用している場合、スプーフィング対策はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d33ec-173">Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="d33ec-174">URL</span><span class="sxs-lookup"><span data-stu-id="d33ec-174">URLs</span></span>

<span data-ttu-id="d33ec-175">URL はメール フロー中にデトニトされます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-175">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="d33ec-176">特定の URL を分析しない場合は、許可されている URL の一覧を適切に管理します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-176">If you don't want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="d33ec-177">詳細 [については、「テナントの許可/ブロックリストの URL](tenant-allow-block-list.md) の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d33ec-177">See [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="d33ec-178">電子メール メッセージのボディ内の URL リンクは折り返されません。お客様への影響を減らします。</span><span class="sxs-lookup"><span data-stu-id="d33ec-178">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="d33ec-179">電子メールルーティング</span><span class="sxs-lookup"><span data-stu-id="d33ec-179">Email routing</span></span>

<span data-ttu-id="d33ec-180">メールをルーティングする受信コネクタの名前など、メールの現在のルーティング方法を設定するために必要な対応する詳細を準備します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-180">Prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="d33ec-181">Exchange Online Protection を使用しているだけの場合は、コネクタを使用する必要があります。 [メール フローと電子メール ルーティングの詳細](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="d33ec-181">If you are just using Exchange Online Protection, you won’t have a connector. [Learn about mail flow and email routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="d33ec-182">サポートされる電子メール ルーティング シナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d33ec-182">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="d33ec-183">**サード パーティ** のパートナーまたはオンプレミスのサービス プロバイダー: 評価する受信コネクタは、サード パーティプロバイダーを使用するか、オンプレミスの電子メール セキュリティのソリューションを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d33ec-183">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you're using a solution for email security on-premises.</span></span>
- <span data-ttu-id="d33ec-184">**Microsoft Exchange Online保護** のみ: 評価するテナントは Office 365 を電子メール セキュリティに使用し、Mail Exchange (MX) レコードは Microsoft をポイントします。</span><span class="sxs-lookup"><span data-stu-id="d33ec-184">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="d33ec-185">電子メール セキュリティ ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="d33ec-185">Email security gateway</span></span>

<span data-ttu-id="d33ec-186">サード パーティの電子メール セキュリティ ゲートウェイ (KM) を使用している場合は、プロバイダーの名前を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-186">If you're using a third-party email security gateway (ESG), you'll need to know the provider's name.</span></span> <span data-ttu-id="d33ec-187">オンプレミスベンダーまたはサポートされていないベンダーで、オンプレミスまたはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-187">If you're using an ESG on-premises or non-supported vendors, you'll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="d33ec-188">サポートされているサード パーティパートナーには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-188">Supported third-party partners include:</span></span>

- <span data-ttu-id="d33ec-189">Barracuda</span><span class="sxs-lookup"><span data-stu-id="d33ec-189">Barracuda</span></span>
- <span data-ttu-id="d33ec-190">IronPort</span><span class="sxs-lookup"><span data-stu-id="d33ec-190">IronPort</span></span>
- <span data-ttu-id="d33ec-191">Mimecast</span><span class="sxs-lookup"><span data-stu-id="d33ec-191">Mimecast</span></span>
- <span data-ttu-id="d33ec-192">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="d33ec-192">Proofpoint</span></span>
- <span data-ttu-id="d33ec-193">最も近い</span><span class="sxs-lookup"><span data-stu-id="d33ec-193">Sophos</span></span>
- <span data-ttu-id="d33ec-194">Symantec</span><span class="sxs-lookup"><span data-stu-id="d33ec-194">Symantec</span></span>
- <span data-ttu-id="d33ec-195">Trend Micro</span><span class="sxs-lookup"><span data-stu-id="d33ec-195">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="d33ec-196">スコープ</span><span class="sxs-lookup"><span data-stu-id="d33ec-196">Scoping</span></span>

<span data-ttu-id="d33ec-197">評価の範囲を受信コネクタに設定できます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-197">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="d33ec-198">コネクタが構成されていない場合、評価スコープを使用すると、管理者はテナント内の任意のユーザーからデータを収集し、365 用に Defender を評価Officeできます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-198">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="d33ec-199">評価の開始</span><span class="sxs-lookup"><span data-stu-id="d33ec-199">Get started with the evaluation</span></span>

<span data-ttu-id="d33ec-200">Office 365 セキュリティ & コンプライアンス センター (3 つのアクセス ポイントから) で、Office 365 評価用の Microsoft Office Defender & セットアップ カードを https://protection.office.com/homepage) 検索します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-200">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="d33ec-201">脅威管理> ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="d33ec-201">Threat management > Dashboard</span></span>
- <span data-ttu-id="d33ec-202">脅威管理>ポリシー</span><span class="sxs-lookup"><span data-stu-id="d33ec-202">Threat management > Policy</span></span>
- <span data-ttu-id="d33ec-203">レポート> ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="d33ec-203">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="d33ec-204">評価の設定</span><span class="sxs-lookup"><span data-stu-id="d33ec-204">Setting up the evaluation</span></span>

<span data-ttu-id="d33ec-205">評価のセットアップ フローを開始すると、2 つのルーティング オプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-205">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="d33ec-206">組織のメール ルーティングのセットアップと評価のニーズに応じて、サードパーティまたはオンプレミスのサービス プロバイダーを使用しているか、または Microsoft Exchange Online のみを使用しているかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-206">Depending on your organization's mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="d33ec-207">サードパーティのパートナーやオンプレミスのサービス プロバイダーを使用している場合は、ドロップダウン メニューからベンダーの名前を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-207">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="d33ec-208">その他のコネクタ関連の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-208">Provide the other connector-related details.</span></span>

- <span data-ttu-id="d33ec-209">MX Microsoft Exchange Online Microsoft をポイントし、Exchange Online メールボックスを持っている場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-209">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="d33ec-210">設定を確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-210">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="d33ec-211">次に、[評価の **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d33ec-211">Then, select **Create evaluation**.</span></span> <span data-ttu-id="d33ec-212">セットアップが完了したかどうかを示す確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-212">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="d33ec-213">Microsoft Defender for Office 365 評価レポートは、1 日に 1 回生成されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-213">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="d33ec-214">データが入力されるには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-214">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="d33ec-215">Exchange ルール (オプション)</span><span class="sxs-lookup"><span data-stu-id="d33ec-215">Exchange rules (optional)</span></span>

<span data-ttu-id="d33ec-216">既存のゲートウェイがある場合は、コネクタの拡張フィルター処理がアクティブ化され、受信送信者の IP アドレスが変更されるので、フィルター処理をバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-216">If you have an existing gateway, you might want to bypass filtering because it will activate enhanced filtering for connectors and alter the incoming sender IP address.</span></span> <span data-ttu-id="d33ec-217">バイパスするには、Exchange 管理センターに移動し、SCL -1 のポリシーを作成します (まだポリシーを持ってない場合)。</span><span class="sxs-lookup"><span data-stu-id="d33ec-217">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one).</span></span> <span data-ttu-id="d33ec-218">ルール コンポーネントの詳細と動作方法については、Exchange Online のメール フロー ルール (トランスポート ルール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d33ec-218">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="d33ec-219">機能を評価する</span><span class="sxs-lookup"><span data-stu-id="d33ec-219">Evaluate capabilities</span></span>

<span data-ttu-id="d33ec-220">評価レポートが生成された後、組織内の電子メールとコラボレーション ワークスペースで、高度な脅威リンク、高度な脅威の添付ファイル、および潜在的な偽装が識別された数を確認します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-220">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="d33ec-221">試用版の有効期限が切れた後、90 日間レポートに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-221">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="d33ec-222">ただし、それ以上の情報は収集されます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-222">However, it won't collect any more information.</span></span> <span data-ttu-id="d33ec-223">試用版の有効期限が切れた後に Office 365 の Microsoft Defender を引き続き使用する場合は [、microsoft Defender for Office 365 (プラン 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)の有料サブスクリプションを購入してください。</span><span class="sxs-lookup"><span data-stu-id="d33ec-223">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="d33ec-224">[設定] **に移動** してルーティングを更新したり、評価をいつでもオフにできます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-224">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="d33ec-225">ただし、無効にした後で評価を続行する場合は、同じセットアップ プロセスを再度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33ec-225">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="d33ec-226">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="d33ec-226">Provide feedback</span></span>

<span data-ttu-id="d33ec-227">お客様からのフィードバックは、高度な攻撃から環境を保護する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d33ec-227">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="d33ec-228">製品の機能と評価結果のエクスペリエンスと印象を共有します。</span><span class="sxs-lookup"><span data-stu-id="d33ec-228">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="d33ec-229">フィードバック **を送信するを** 選択して、ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="d33ec-229">Select **Give feedback** to let us know what you think.</span></span>
