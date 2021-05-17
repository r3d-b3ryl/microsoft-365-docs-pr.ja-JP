---
title: Microsoft Defender のセキュリティ評価Office 365
description: 評価モードOffice 365 Defender は、マルウェアなどのOffice 365をログに記録するが、メッセージに対して動作しない電子メール ポリシー用の Defender を作成します。
keywords: 評価Office 365、Microsoft Defender for Office 365、office 365 評価、try office 365、Microsoft Defender、Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 005c1f6ad7806c8d1ba1d38e4e82edd25034075d
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51942995"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="82f59-104">Microsoft Defender のセキュリティ評価Office 365</span><span class="sxs-lookup"><span data-stu-id="82f59-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="82f59-105">Microsoft Defender for Office 365評価はパブリック プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="82f59-105">Microsoft Defender for Office 365 evaluation is in public preview.</span></span> <span data-ttu-id="82f59-106">このプレビュー バージョンは、サービス レベル契約なしで提供されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="82f59-107">一部の機能はサポートされていないか、制限された機能を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="82f59-108">セキュリティ製品の徹底的な評価を実施すると、アップグレードと購入に関する情報に基づいた意思決定を行う際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82f59-108">Conducting a thorough security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="82f59-109">セキュリティ製品の機能を試して、セキュリティ運用チームの日常業務に役立つ方法を評価するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82f59-109">It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="82f59-110">[Microsoft Defender for Office 365](defender-for-office-365.md)評価エクスペリエンスは、デバイスと環境の構成の複雑さを排除するように設計され、Microsoft Defender の機能をOffice 365。</span><span class="sxs-lookup"><span data-stu-id="82f59-110">The [Microsoft Defender for Office 365](defender-for-office-365.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="82f59-111">評価モードでは、MX レコードを Microsoft にExchange Online、メールボックスに送信されるメッセージはすべて評価できます。</span><span class="sxs-lookup"><span data-stu-id="82f59-111">With evaluation mode, all messages sent to Exchange Online mailboxes can be evaluated without pointing MX records to Microsoft.</span></span> <span data-ttu-id="82f59-112">この機能は電子メール保護にのみ適用され、Word、Office、またはクライアントSharePointクライアントには適用Teams。</span><span class="sxs-lookup"><span data-stu-id="82f59-112">The feature only applies to email protection and not to Office Clients like Word, SharePoint, or Teams.</span></span>

<span data-ttu-id="82f59-113">microsoft Defender for Office 365 をサポートするライセンスをまだ持ってない場合は、[無料の 30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)日間の評価を開始し、Office 365 セキュリティ & コンプライアンス センター () で機能をテストできます https://protection.office.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="82f59-113">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="82f59-114">クイック セットアップを楽しめ、必要に応じて簡単にオフにできます。</span><span class="sxs-lookup"><span data-stu-id="82f59-114">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="82f59-115">統合 Microsoft 365 セキュリティ ポータル (security.microsoft.com) を使用している場合は、Office 365 評価用の Defender を開始できます。メール & Collaboration > Policies & Rules > Threat Policies > 追加ポリシー)。</span><span class="sxs-lookup"><span data-stu-id="82f59-115">If you're in the unified Microsoft 365 security portal (security.microsoft.com) you can start a Defender for Office 365 evaluation here: Email & Collaboration > Policies & Rules > Threat Policies > Additional Policies.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="82f59-116">評価のしくみ</span><span class="sxs-lookup"><span data-stu-id="82f59-116">How the evaluation works</span></span>

<span data-ttu-id="82f59-117">評価モードOffice 365 Defender は、マルウェアなどのOffice 365をログに記録するが、メッセージに対して動作しない電子メール ポリシー用の Defender を作成します。</span><span class="sxs-lookup"><span data-stu-id="82f59-117">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don't act on messages.</span></span> <span data-ttu-id="82f59-118">MX レコードの構成を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="82f59-118">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="82f59-119">評価モードでは [、セーフ 、セーフ](safe-attachments.md) [リンク](safe-links.md)、メールボックス インテリジェンス ベース [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)の偽装ポリシーが代理で設定されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-119">With evaluation mode, [Safe Attachments](safe-attachments.md), [Safe Links](safe-links.md), and [mailbox intelligence based impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are set up on your behalf.</span></span> <span data-ttu-id="82f59-120">すべての Defender for Office 365ポリシーは、バックグラウンドで強制不可モードで作成され、表示されません。</span><span class="sxs-lookup"><span data-stu-id="82f59-120">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="82f59-121">セットアップの一環として、評価モードではコネクタの [拡張フィルターも構成します](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="82f59-121">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="82f59-122">IP アドレスと送信者情報を保持することで、フィルターの精度が向上します。それ以外の場合、メールが Defender for Office 365 の前にあるメール セキュリティ ゲートウェイ (ESG) を通過すると失われます。</span><span class="sxs-lookup"><span data-stu-id="82f59-122">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="82f59-123">また、コネクタのフィルター機能が強化され、既存のスパム対策 (EOP) Exchange Online Protectionフィッシング対策ポリシーのフィルタリング精度も向上します。</span><span class="sxs-lookup"><span data-stu-id="82f59-123">Enhanced Filtering for Connectors also improves the filtering accuracy for your existing Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="82f59-124">コネクタの拡張フィルター処理を有効にすると、フィルターの精度が向上しますが、Office 365 の Defender の前に ESG を設定し、現在 EOP フィルター処理をバイパスしていない場合は、特定のメッセージの配信可能性が変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-124">Enabled Enhanced Filtering for Connectors improves filtering accuracy but may alter deliverability for certain messages if you have an ESG in front of Defender for Office 365, and currently do not bypass EOP filtering.</span></span> <span data-ttu-id="82f59-125">影響は EOP ポリシーに制限されます。評価の一部としてセットアップされる MDO ポリシーは、強制以外のモードで作成されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-125">The impact is limited to EOP policies; MDO policies setup as part of the evaluation are created in non-enforcement mode.</span></span> <span data-ttu-id="82f59-126">潜在的な運用への影響を最小限に抑えるために、トランスポート ルールを作成してスパム信頼レベル (SCL) を -1 に設定することで、すべての EOP フィルターをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="82f59-126">To minimize potential production impact, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="82f59-127">詳細 [については、「EAC を使用してメッセージの SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を設定するメール フロー ルールを作成する」   を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82f59-127">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="82f59-128">評価モードが設定されている場合、ポリシーが実装された場合にブロックされたメッセージを定量化する最大 90 日間のデータを含むレポートが毎日更新されます (たとえば、削除、迷惑メールへの送信、検疫など)。</span><span class="sxs-lookup"><span data-stu-id="82f59-128">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked if the policies were implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="82f59-129">レポートは、すべての Defender に対して、Office 365 EOP 検出用に生成されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-129">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="82f59-130">これらは検出テクノロジ (偽装など) ごとに集計され、時間範囲でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="82f59-130">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="82f59-131">さらに、メッセージ レポートをオンデマンドで作成して、カスタム ピボットを作成したり、Threat Explorer を使用して詳細なメッセージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="82f59-131">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="82f59-132">セットアップの簡略化により、次の作業に集中できます。</span><span class="sxs-lookup"><span data-stu-id="82f59-132">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="82f59-133">評価の実行</span><span class="sxs-lookup"><span data-stu-id="82f59-133">Running the evaluation</span></span>
- <span data-ttu-id="82f59-134">詳細なレポートの取得</span><span class="sxs-lookup"><span data-stu-id="82f59-134">Getting a detailed report</span></span>
- <span data-ttu-id="82f59-135">アクションのレポートの分析</span><span class="sxs-lookup"><span data-stu-id="82f59-135">Analyzing the report for action</span></span>
- <span data-ttu-id="82f59-136">評価結果の提示</span><span class="sxs-lookup"><span data-stu-id="82f59-136">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="82f59-137">はじめに</span><span class="sxs-lookup"><span data-stu-id="82f59-137">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="82f59-138">ライセンス</span><span class="sxs-lookup"><span data-stu-id="82f59-138">Licensing</span></span>

<span data-ttu-id="82f59-139">評価にアクセスするには、ライセンス要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-139">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="82f59-140">次のライセンスが動作します。</span><span class="sxs-lookup"><span data-stu-id="82f59-140">Any of the following licenses will work:</span></span>

- <span data-ttu-id="82f59-141">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="82f59-141">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="82f59-142">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="82f59-142">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="82f59-143">Microsoft 365 E5、Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="82f59-143">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="82f59-144">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="82f59-144">Office 365 E5</span></span>

<span data-ttu-id="82f59-145">これらのライセンスを 1 つも持ってない場合は、試用版ライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-145">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="82f59-146">試用版</span><span class="sxs-lookup"><span data-stu-id="82f59-146">Trial</span></span>

<span data-ttu-id="82f59-147">Microsoft Defender for microsoft Defender for Office 365を取得するには、課金管理者の役割またはグローバル管理者の役割 **を持っている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="82f59-147">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="82f59-148">グローバル管理者の役割を持つユーザーにアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="82f59-148">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="82f59-149">サブスクリプションとライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="82f59-149">Learn about subscriptions and licenses</span></span>](../../commerce/licenses/subscriptions-and-licenses.md)

<span data-ttu-id="82f59-150">適切な役割を果たしたら、請求 > 購入サービスに移動して、Microsoft 365 管理センターで Microsoft Defender for Office 365 (プラン 2) の試用版ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="82f59-150">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="82f59-151">試用版には、25 ライセンスの 30 日間の無料試用版が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82f59-151">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="82f59-152">Microsoft Defender for microsoft [Defender for Office 365 (プラン 2) を取得します](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="82f59-152">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="82f59-153">高度な脅威を監視および報告する評価を含む 30 日間のウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="82f59-153">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="82f59-154">また、完全な Defender 機能を使用する場合は、有料サブスクリプションを購入Office 365があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-154">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="82f59-155">Roles</span><span class="sxs-lookup"><span data-stu-id="82f59-155">Roles</span></span>

<span data-ttu-id="82f59-156">**Exchange Online評価モードで** Defender を設定するには、Office 365ロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="82f59-156">**Exchange Online roles are required** to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="82f59-157">コンプライアンスまたはセキュリティMicrosoft 365ロールを割り当てると機能しません。</span><span class="sxs-lookup"><span data-stu-id="82f59-157">Assigning a Microsoft 365 compliance or security admin role won't work.</span></span>

- [<span data-ttu-id="82f59-158">アクセス許可の詳細については、Exchange Online</span><span class="sxs-lookup"><span data-stu-id="82f59-158">Learn about permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
- [<span data-ttu-id="82f59-159">管理者ロールの割り当てについて</span><span class="sxs-lookup"><span data-stu-id="82f59-159">Learn about assigning admin roles</span></span>](../../admin/add-users/assign-admin-roles.md)

<span data-ttu-id="82f59-160">次の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="82f59-160">The following roles are needed:</span></span>

|<span data-ttu-id="82f59-161">タスク</span><span class="sxs-lookup"><span data-stu-id="82f59-161">Task</span></span>|<span data-ttu-id="82f59-162">ロール (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="82f59-162">Role (in Exchange Online)</span></span>|
|---|---|
|<span data-ttu-id="82f59-163">無料試用版を取得するか、Microsoft Defender for Office 365購入する (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="82f59-163">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="82f59-164">課金管理者ロールまたはグローバル管理者ロール</span><span class="sxs-lookup"><span data-stu-id="82f59-164">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="82f59-165">評価ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="82f59-165">Create evaluation policy</span></span>|<span data-ttu-id="82f59-166">リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="82f59-166">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="82f59-167">評価ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="82f59-167">Edit evaluation policy</span></span>|<span data-ttu-id="82f59-168">リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="82f59-168">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="82f59-169">評価ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="82f59-169">Delete evaluation policy</span></span>|<span data-ttu-id="82f59-170">リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="82f59-170">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="82f59-171">評価レポートの表示</span><span class="sxs-lookup"><span data-stu-id="82f59-171">View evaluation report</span></span>|<span data-ttu-id="82f59-172">セキュリティ管理者の役割またはセキュリティ 閲覧者の役割</span><span class="sxs-lookup"><span data-stu-id="82f59-172">Security admin role OR Security reader role</span></span>|
|

### <a name="enhanced-filtering"></a><span data-ttu-id="82f59-173">拡張フィルター</span><span class="sxs-lookup"><span data-stu-id="82f59-173">Enhanced filtering</span></span>

<span data-ttu-id="82f59-174">バルクExchange Online Protectionスパム保護など、ユーザーのポリシーは同じままです。</span><span class="sxs-lookup"><span data-stu-id="82f59-174">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="82f59-175">ただし、この評価ではコネクタの拡張フィルター処理が有効にされ、バイパスしない限り、メール フローやポリシー Exchange Online Protection影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-175">However, the evaluation turns on enhanced filtering for connectors, which may impact your mail flow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="82f59-176">コネクタのフィルター処理が強化され、テナントはスプーフィング防止保護を使用できます。</span><span class="sxs-lookup"><span data-stu-id="82f59-176">Enhanced filtering for connectors allows tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="82f59-177">コネクタの拡張フィルターを有効にせずにメール セキュリティ ゲートウェイ (ESG) を使用している場合、スプーフィング対策はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="82f59-177">Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="82f59-178">URL</span><span class="sxs-lookup"><span data-stu-id="82f59-178">URLs</span></span>

<span data-ttu-id="82f59-179">URL はメール フロー中にデトナ処理されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-179">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="82f59-180">特定の URL を削除しない場合は、許可された URL のリストを適切に管理します。</span><span class="sxs-lookup"><span data-stu-id="82f59-180">If you don't want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="82f59-181">詳細については [、「テナント許可/ブロック一覧の管理」](tenant-allow-block-list.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82f59-181">See [Manage the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="82f59-182">電子メール メッセージのボディ内の URL リンクは折り返されません。顧客への影響を減らします。</span><span class="sxs-lookup"><span data-stu-id="82f59-182">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="82f59-183">メールのルーティング</span><span class="sxs-lookup"><span data-stu-id="82f59-183">Email routing</span></span>

<span data-ttu-id="82f59-184">メールをルーティングする受信コネクタの名前など、メールの現在のルーティング方法を設定する必要がある対応する詳細を準備します。</span><span class="sxs-lookup"><span data-stu-id="82f59-184">Prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="82f59-185">アプリケーションを使用しているExchange Online Protectionコネクタを持つ必要があります。 [メール フローとメール ルーティングの詳細](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="82f59-185">If you are just using Exchange Online Protection, you won't have a connector. [Learn about mail flow and email routing](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="82f59-186">サポートされる電子メール ルーティングシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82f59-186">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="82f59-187">**サード パーティパートナー** またはオンプレミス サービス プロバイダー : 評価する受信コネクタは、サード パーティプロバイダーを使用するか、オンプレミスの電子メール セキュリティ用のソリューションを使用しています。</span><span class="sxs-lookup"><span data-stu-id="82f59-187">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you're using a solution for email security on-premises.</span></span>
- <span data-ttu-id="82f59-188">**Microsoft Exchange Online保護のみ**: 評価するテナントは、Office 365 を電子メール セキュリティに使用し、メール Exchange (MX) レコードは Microsoft をポイントします。</span><span class="sxs-lookup"><span data-stu-id="82f59-188">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="82f59-189">メール セキュリティ ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="82f59-189">Email security gateway</span></span>

<span data-ttu-id="82f59-190">サードパーティの電子メール セキュリティ ゲートウェイ (ESG) を使用している場合は、プロバイダーの名前を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-190">If you're using a third-party email security gateway (ESG), you'll need to know the provider's name.</span></span> <span data-ttu-id="82f59-191">ESG オンプレミスベンダーまたはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-191">If you're using an ESG on-premises or non-supported vendors, you'll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="82f59-192">サポートされているサード パーティパートナーには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82f59-192">Supported third-party partners include:</span></span>

- <span data-ttu-id="82f59-193">バラクーダ</span><span class="sxs-lookup"><span data-stu-id="82f59-193">Barracuda</span></span>
- <span data-ttu-id="82f59-194">IronPort</span><span class="sxs-lookup"><span data-stu-id="82f59-194">IronPort</span></span>
- <span data-ttu-id="82f59-195">Mimecast</span><span class="sxs-lookup"><span data-stu-id="82f59-195">Mimecast</span></span>
- <span data-ttu-id="82f59-196">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="82f59-196">Proofpoint</span></span>
- <span data-ttu-id="82f59-197">Sophos</span><span class="sxs-lookup"><span data-stu-id="82f59-197">Sophos</span></span>
- <span data-ttu-id="82f59-198">シマンテック</span><span class="sxs-lookup"><span data-stu-id="82f59-198">Symantec</span></span>
- <span data-ttu-id="82f59-199">Trend Micro</span><span class="sxs-lookup"><span data-stu-id="82f59-199">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="82f59-200">スコープ</span><span class="sxs-lookup"><span data-stu-id="82f59-200">Scoping</span></span>

<span data-ttu-id="82f59-201">評価の範囲を受信コネクタに指定できます。</span><span class="sxs-lookup"><span data-stu-id="82f59-201">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="82f59-202">コネクタが構成されていない場合、評価スコープを使用すると、管理者はテナント内の任意のユーザーからデータを収集して、Defender のデータをOffice 365。</span><span class="sxs-lookup"><span data-stu-id="82f59-202">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="82f59-203">評価の開始</span><span class="sxs-lookup"><span data-stu-id="82f59-203">Get started with the evaluation</span></span>

<span data-ttu-id="82f59-204">Microsoft Defender for the microsoft Defender for Office 365評価セットアップ カードは、Office 365 コンプライアンス センター (& https://protection.office.com/homepage) 3 つのアクセス ポイントから) にあります。</span><span class="sxs-lookup"><span data-stu-id="82f59-204">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="82f59-205">脅威管理>ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="82f59-205">Threat management > Dashboard</span></span>
- <span data-ttu-id="82f59-206">脅威管理>ポリシー</span><span class="sxs-lookup"><span data-stu-id="82f59-206">Threat management > Policy</span></span>
- <span data-ttu-id="82f59-207">レポート > ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="82f59-207">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="82f59-208">評価のセットアップ</span><span class="sxs-lookup"><span data-stu-id="82f59-208">Setting up the evaluation</span></span>

<span data-ttu-id="82f59-209">評価のセットアップ フローを開始すると、2 つのルーティング オプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-209">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="82f59-210">組織のメール ルーティングのセットアップと評価のニーズに応じて、サード パーティまたはオンプレミスのサービス プロバイダーを使用しているか、または Microsoft Exchange Online のみを使用しているかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="82f59-210">Depending on your organization's mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="82f59-211">サード パーティのパートナーまたはオンプレミス サービス プロバイダーを使用している場合は、ドロップダウン メニューからベンダーの名前を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-211">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="82f59-212">他のコネクタ関連の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="82f59-212">Provide the other connector-related details.</span></span>

- <span data-ttu-id="82f59-213">MX レコードMicrosoft Exchange Online Microsoft をポイントし、ユーザーがメールボックスを持っている場合は、[Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82f59-213">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="82f59-214">必要に応じて設定を確認し、編集します。</span><span class="sxs-lookup"><span data-stu-id="82f59-214">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="82f59-215">次に、[評価の **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="82f59-215">Then, select **Create evaluation**.</span></span> <span data-ttu-id="82f59-216">セットアップが完了したという確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-216">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="82f59-217">Microsoft Defender for Office 365評価レポートは、1 日に 1 回生成されます。</span><span class="sxs-lookup"><span data-stu-id="82f59-217">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="82f59-218">データの入力に最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-218">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="82f59-219">Exchangeルール (オプション)</span><span class="sxs-lookup"><span data-stu-id="82f59-219">Exchange rules (optional)</span></span>

<span data-ttu-id="82f59-220">既存のゲートウェイがある場合は、評価モードを有効にすると、コネクタの拡張フィルター処理がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="82f59-220">If you have an existing gateway, enabling evaluation mode will activate enhanced filtering for connectors.</span></span> <span data-ttu-id="82f59-221">これにより、受信送信者の IP アドレスを変更することで、フィルターの精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="82f59-221">This improves filtering accuracy by altering the incoming sender IP address.</span></span> <span data-ttu-id="82f59-222">これにより、フィルターの評決が変更される可能性があります。また、フィルターをバイパスしていない場合Exchange Online Protectionメッセージの配信可能性が変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-222">This may change the filter verdicts and if you are not bypassing Exchange Online Protection this may alter deliverability for certain messages.</span></span> <span data-ttu-id="82f59-223">この場合、影響を分析するためにフィルター処理を一時的にバイパスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-223">In this case you might want to temporarily bypass filtering to analyze impact.</span></span> <span data-ttu-id="82f59-224">バイパスするには、管理センター Exchangeに移動し、SCL -1 のポリシーを作成します (まだポリシーを持ってない場合)。</span><span class="sxs-lookup"><span data-stu-id="82f59-224">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one).</span></span> <span data-ttu-id="82f59-225">ルール コンポーネントの詳細と動作方法については、「メール フロー ルール (トランスポート ルール)」を参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="82f59-225">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="82f59-226">機能を評価する</span><span class="sxs-lookup"><span data-stu-id="82f59-226">Evaluate capabilities</span></span>

<span data-ttu-id="82f59-227">評価レポートが生成された後、組織内の電子メールとコラボレーション ワークスペースで、高度な脅威リンク、高度な脅威の添付ファイル、および潜在的な偽装が識別された数を確認します。</span><span class="sxs-lookup"><span data-stu-id="82f59-227">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="82f59-228">試用版の有効期限が切れたら、レポートに引き続き 90 日間アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="82f59-228">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="82f59-229">ただし、それ以上の情報は収集しない。</span><span class="sxs-lookup"><span data-stu-id="82f59-229">However, it won't collect any more information.</span></span> <span data-ttu-id="82f59-230">試用版の有効期限が切れた後に microsoft Defender for Office 365 を引き続き使用する場合は、Microsoft Defender for Office 365 (プラン[2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)の有料サブスクリプションを購入してください。</span><span class="sxs-lookup"><span data-stu-id="82f59-230">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="82f59-231">[ユーザー] に **移動設定、** ルーティングを更新したり、評価をいつでもオフにできます。</span><span class="sxs-lookup"><span data-stu-id="82f59-231">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="82f59-232">ただし、無効にした後で評価を続行する場合は、同じセットアップ プロセスを再度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f59-232">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="82f59-233">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="82f59-233">Provide feedback</span></span>

<span data-ttu-id="82f59-234">フィードバックは、高度な攻撃から環境を保護する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82f59-234">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="82f59-235">製品機能と評価結果のエクスペリエンスと印象を共有します。</span><span class="sxs-lookup"><span data-stu-id="82f59-235">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="82f59-236">[ **フィードバックを提供する]** を選択して、ご意見をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="82f59-236">Select **Give feedback** to let us know what you think.</span></span>