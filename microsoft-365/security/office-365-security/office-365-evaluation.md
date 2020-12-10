---
title: Microsoft Defender for Office 365 の評価
description: 評価モードでの Office 365 の defender では、verdicts (マルウェアなど) をログに記録し、メッセージに対しては処理しない Office 365 の電子メールポリシーを作成します。
keywords: office 365、Microsoft Defender for Office 365、office 365 評価、試用版 office 365、Microsoft Defender、ATP を評価する
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
ms.openlocfilehash: b5b095a1d75ead0f963a71d816e7d879b7cd3697
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614800"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="32c5d-104">Microsoft Defender for Office 365 の評価</span><span class="sxs-lookup"><span data-stu-id="32c5d-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="32c5d-105">Microsoft Defender for Office 365 の評価は、すぐにパブリックプレビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-105">Evaluate Microsoft Defender for Office 365 will soon be in public preview.</span></span> <span data-ttu-id="32c5d-106">このプレビュー版は、サービスレベル契約なしで提供されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="32c5d-107">一部の機能はサポートされていない場合や、制限された機能を備えている場合があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="32c5d-108">包括的なセキュリティ製品の評価を実施することで、アップグレードと購入に関する情報を得られるようになります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-108">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="32c5d-109">セキュリティ製品の機能を試して、毎日のタスクでセキュリティ運用チームをどのように支援するかを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-109">It helps to try out the security product’s capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="32c5d-110">[Microsoft Defender For Office 365](office-365-atp.md)の評価の体験は、セキュリティソリューションの機能を評価することに重点を置くために、デバイスと環境の構成の複雑さを排除するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="32c5d-110">The [Microsoft Defender for Office 365](office-365-atp.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the security solution.</span></span> <span data-ttu-id="32c5d-111">これは、SharePoint、Office クライアント、または Teams ではなく、電子メール保護にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-111">It only applies to email protection and not SharePoint, Office Clients, or Teams.</span></span>

<span data-ttu-id="32c5d-112">Office 365 用の Microsoft Defender をサポートするライセンスをまだ持っていない場合は、 [無料の30日間の評価](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) を開始して、Office 365 セキュリティ & コンプライアンスセンターで機能をテストでき https://protection.office.com/homepage) ます (。</span><span class="sxs-lookup"><span data-stu-id="32c5d-112">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="32c5d-113">クイックセットアップを楽しんで、必要に応じて簡単にオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-113">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="32c5d-114">評価のしくみ</span><span class="sxs-lookup"><span data-stu-id="32c5d-114">How the evaluation works</span></span>

<span data-ttu-id="32c5d-115">評価モードでの Office 365 の defender では、verdicts (マルウェアなど) をログに記録し、メッセージに対しては処理しない Office 365 の電子メールポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-115">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don’t act on messages.</span></span> <span data-ttu-id="32c5d-116">MX レコード構成を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="32c5d-116">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="32c5d-117">評価モード、 [安全な添付ファイル](atp-safe-attachments.md)、 [安全なリンク](atp-safe-links.md)、および [フィッシング対策ポリシー](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) は、お客様の代わりにセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-117">With evaluation mode, [Safe Attachments](atp-safe-attachments.md), [Safe Links](atp-safe-links.md), and [anti-phishing impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are setup on your behalf.</span></span> <span data-ttu-id="32c5d-118">すべての Defender for Office 365 ポリシーは、バックグラウンドで非強制モードで作成され、ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="32c5d-118">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="32c5d-119">セットアップの一環として、評価モードでは、 [コネクタの拡張フィルター処理](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)も構成されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-119">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="32c5d-120">IP アドレスと送信者情報を保持することで、フィルターの精度が向上します。これは、メールが Office 365 の Defender の前にある電子メールセキュリティゲートウェイ (ESG) を通過するときには失われます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-120">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="32c5d-121">これにより、Exchange Online Protection (EOP) スパム対策ポリシーとフィッシング対策ポリシーのフィルターの精度も向上します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-121">This also improves the filtering accuracy for your Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="32c5d-122">サポートされていないシナリオによって生産上の影響を最小限に抑えるには、スパム信頼レベル (SCL) を-1 に設定するトランスポートルールを作成して、すべての EOP フィルタリングをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="32c5d-122">To minimize potential production impact on some unsupported scenarios, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="32c5d-123">詳細については [、「EAC を使用してメッセージの SCL を設定するメールフロールールを作成する」を](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)参照してください   。</span><span class="sxs-lookup"><span data-stu-id="32c5d-123">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="32c5d-124">評価モードが設定されている場合、毎日最大90日間のデータ量を含むレポートが更新されます。ブロックされたメッセージは、削除、迷惑メールへの送信などのポリシーが作成および実装されていました。</span><span class="sxs-lookup"><span data-stu-id="32c5d-124">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked had the policies been made and implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="32c5d-125">すべての Defender for Office 365 と EOP の検出に関するレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-125">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="32c5d-126">これらは検出テクノロジ (たとえば、偽装) ごとに集計され、時間範囲によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-126">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="32c5d-127">さらに、メッセージレポートをオンデマンドで作成して、カスタムピボットを作成したり、脅威エクスプローラーを使用して詳細なメッセージを表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-127">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="32c5d-128">シンプルなセットアップ環境を使用すると、以下のことに集中できます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-128">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="32c5d-129">評価を実行する</span><span class="sxs-lookup"><span data-stu-id="32c5d-129">Running the evaluation</span></span>
- <span data-ttu-id="32c5d-130">詳細レポートを取得する</span><span class="sxs-lookup"><span data-stu-id="32c5d-130">Getting a detailed report</span></span>
- <span data-ttu-id="32c5d-131">アクションのレポートを分析する</span><span class="sxs-lookup"><span data-stu-id="32c5d-131">Analyzing the report for action</span></span>
- <span data-ttu-id="32c5d-132">評価結果の提示</span><span class="sxs-lookup"><span data-stu-id="32c5d-132">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="32c5d-133">開始する前に</span><span class="sxs-lookup"><span data-stu-id="32c5d-133">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="32c5d-134">ライセンス</span><span class="sxs-lookup"><span data-stu-id="32c5d-134">Licensing</span></span>

<span data-ttu-id="32c5d-135">評価にアクセスするには、ライセンス要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-135">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="32c5d-136">次のいずれかのライセンスが機能します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-136">Any of the following licenses will work:</span></span>

- <span data-ttu-id="32c5d-137">Microsoft Defender for Office 365 プラン1</span><span class="sxs-lookup"><span data-stu-id="32c5d-137">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="32c5d-138">Microsoft Defender for Office 365 プラン2</span><span class="sxs-lookup"><span data-stu-id="32c5d-138">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="32c5d-139">Microsoft 365 E5、Microsoft 365 E5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="32c5d-139">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="32c5d-140">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="32c5d-140">Office 365 E5</span></span>

<span data-ttu-id="32c5d-141">これらのライセンスのいずれかがない場合は、試用版ライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-141">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="32c5d-142">試用版</span><span class="sxs-lookup"><span data-stu-id="32c5d-142">Trial</span></span>

<span data-ttu-id="32c5d-143">Microsoft Defender for Office 365 の試用版ライセンスを取得するには、 **課金管理者** ロールまたは **グローバル管理者ロール** を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-143">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="32c5d-144">グローバル管理者の役割を持つユーザーからアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-144">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="32c5d-145">サブスクリプションとライセンスについて</span><span class="sxs-lookup"><span data-stu-id="32c5d-145">Learn about subscriptions and licenses</span></span>](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

<span data-ttu-id="32c5d-146">適切な役割を持っている場合は、365 Microsoft Defender for Office 365 (Plan 2) の試用版ライセンスを取得するには、「Billing > Purchase services」にアクセスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32c5d-146">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="32c5d-147">試用版には、30日間の無料試用版の25ライセンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="32c5d-147">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="32c5d-148">[Microsoft Defender For Office 365 (Plan 2) の試用版を取得](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-148">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="32c5d-149">高度な脅威を監視して報告するための評価については、30日間のウィンドウが用意されています。</span><span class="sxs-lookup"><span data-stu-id="32c5d-149">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="32c5d-150">Office 365 の機能を完全に Defender 使用する場合は、有料サブスクリプションを購入するオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-150">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="32c5d-151">ロール</span><span class="sxs-lookup"><span data-stu-id="32c5d-151">Roles</span></span>

<span data-ttu-id="32c5d-152">評価モードで Office 365 の Defender をセットアップするには、Exchange Online の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="32c5d-152">Exchange Online roles are required to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="32c5d-153">次の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="32c5d-153">The following roles are needed:</span></span>

|<span data-ttu-id="32c5d-154">タスク</span><span class="sxs-lookup"><span data-stu-id="32c5d-154">Task</span></span>|<span data-ttu-id="32c5d-155">Role</span><span class="sxs-lookup"><span data-stu-id="32c5d-155">Role</span></span>|
|---|---|
|<span data-ttu-id="32c5d-156">無料試用版を入手するか、Microsoft Defender for Office 365 (Plan 2) を購入する</span><span class="sxs-lookup"><span data-stu-id="32c5d-156">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="32c5d-157">課金管理者の役割またはグローバル管理者の役割</span><span class="sxs-lookup"><span data-stu-id="32c5d-157">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="32c5d-158">評価ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="32c5d-158">Create evaluation policy</span></span>|<span data-ttu-id="32c5d-159">[リモートドメインと承認済みドメイン] 役割セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="32c5d-159">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="32c5d-160">評価ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="32c5d-160">Edit evaluation policy</span></span>|<span data-ttu-id="32c5d-161">[リモートドメインと承認済みドメイン] 役割セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="32c5d-161">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="32c5d-162">評価ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="32c5d-162">Delete evaluation policy</span></span>|<span data-ttu-id="32c5d-163">[リモートドメインと承認済みドメイン] 役割セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="32c5d-163">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="32c5d-164">評価レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="32c5d-164">View evaluation report</span></span>|<span data-ttu-id="32c5d-165">セキュリティ管理者の役割またはセキュリティリーダーの役割</span><span class="sxs-lookup"><span data-stu-id="32c5d-165">Security admin role OR Security reader role</span></span>|
|

### <a name="enhanced-filtering"></a><span data-ttu-id="32c5d-166">拡張されたフィルター処理</span><span class="sxs-lookup"><span data-stu-id="32c5d-166">Enhanced filtering</span></span>

<span data-ttu-id="32c5d-167">一括保護やスパム対策など、Exchange Online の保護ポリシーは変わりません。</span><span class="sxs-lookup"><span data-stu-id="32c5d-167">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="32c5d-168">メッセージ配信も同じままです。</span><span class="sxs-lookup"><span data-stu-id="32c5d-168">Message delivery will also remain the same.</span></span> <span data-ttu-id="32c5d-169">ただし、この評価は、メールフローと Exchange Online Protection ポリシーに影響するコネクタの拡張されたフィルター処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="32c5d-169">However, the evaluation turns on enhanced filtering for connectors, which will impact your mailflow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="32c5d-170">コネクタのフィルター処理を強化することで、テナントがスプーフィング対策保護を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-170">Enhanced filtering for connectors will allow tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="32c5d-171">メールセキュリティゲートウェイ (ESG) を使用していても、コネクタの拡張フィルター処理を有効にしていない場合、スプーフィング対策はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="32c5d-171">Anti-spoofing is not supported if you’re using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="32c5d-172">URL</span><span class="sxs-lookup"><span data-stu-id="32c5d-172">URLs</span></span>

<span data-ttu-id="32c5d-173">メールフローでは、Url は分析になります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-173">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="32c5d-174">特定の Url を分析したくない場合は、許可された Url のリストを適切に管理します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-174">If you don’t want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="32c5d-175">詳細について [は、「テナントの許可/ブロック」リストの「Manage URLs](tenant-allow-block-list.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32c5d-175">See [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="32c5d-176">電子メールメッセージの本文内の URL リンクは、顧客への影響を軽減するために折り返されません。</span><span class="sxs-lookup"><span data-stu-id="32c5d-176">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="32c5d-177">電子メールルーティング</span><span class="sxs-lookup"><span data-stu-id="32c5d-177">Email routing</span></span>

<span data-ttu-id="32c5d-178">メールをルーティングする受信コネクタの名前など、電子メールの現在のルーティング方法を設定するために必要な対応する詳細を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-178">You need to prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="32c5d-179">Exchange Online Protection のみを使用している場合は、コネクタがありません。 [メールフローと電子メールルーティングについて](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="32c5d-179">If you are just using Exchange Online Protection, you won’t have a connector. [Learn about mail flow and email routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="32c5d-180">サポートされている電子メールルーティングのシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32c5d-180">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="32c5d-181">**サードパーティのパートナーまたはオンプレミスのサービスプロバイダー**: 評価する受信コネクタがサードパーティプロバイダーを使用しているか、オンプレミスのメールセキュリティ用のソリューションを使用しています。</span><span class="sxs-lookup"><span data-stu-id="32c5d-181">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you’re using a solution for email security on-premises.</span></span>
- <span data-ttu-id="32c5d-182">**Microsoft Exchange Online Protection のみ**: 評価するテナントは、電子メールのセキュリティに Office 365 を使用し、メール交換 (MX) レコードは Microsoft を指しています。</span><span class="sxs-lookup"><span data-stu-id="32c5d-182">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="32c5d-183">電子メールセキュリティゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="32c5d-183">Email security gateway</span></span>

<span data-ttu-id="32c5d-184">サードパーティの電子メールセキュリティゲートウェイ (ESG) を使用している場合は、プロバイダーの名前を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-184">If you’re using a third-party email security gateway (ESG), you’ll need to know the provider’s name.</span></span> <span data-ttu-id="32c5d-185">ESG オンプレミスまたはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-185">If you’re using an ESG on-premises or non-supported vendors, you’ll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="32c5d-186">サポートされているサードパーティパートナーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32c5d-186">Supported third-party partners include:</span></span>

- <span data-ttu-id="32c5d-187">Barracuda</span><span class="sxs-lookup"><span data-stu-id="32c5d-187">Barracuda</span></span>
- <span data-ttu-id="32c5d-188">IronPort</span><span class="sxs-lookup"><span data-stu-id="32c5d-188">IronPort</span></span>
- <span data-ttu-id="32c5d-189">Mimecast</span><span class="sxs-lookup"><span data-stu-id="32c5d-189">Mimecast</span></span>
- <span data-ttu-id="32c5d-190">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="32c5d-190">Proofpoint</span></span>
- <span data-ttu-id="32c5d-191">Sophos</span><span class="sxs-lookup"><span data-stu-id="32c5d-191">Sophos</span></span>
- <span data-ttu-id="32c5d-192">社</span><span class="sxs-lookup"><span data-stu-id="32c5d-192">Symantec</span></span>
- <span data-ttu-id="32c5d-193">トレンドマイクロ</span><span class="sxs-lookup"><span data-stu-id="32c5d-193">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="32c5d-194">スコープ</span><span class="sxs-lookup"><span data-stu-id="32c5d-194">Scoping</span></span>

<span data-ttu-id="32c5d-195">評価を受信コネクタに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-195">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="32c5d-196">コネクタが構成されていない場合は、評価スコープによって、管理者がテナント内の任意のユーザーからデータを収集し、Office 365 の Defender を評価することができます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-196">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="32c5d-197">評価を開始する</span><span class="sxs-lookup"><span data-stu-id="32c5d-197">Get started with the evaluation</span></span>

<span data-ttu-id="32c5d-198">Office 365 Security & コンプライアンスセンター (3 つのアクセスポイント) で、Microsoft Defender for Office 365 評価版カードを検索し https://protection.office.com/homepage) ます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-198">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="32c5d-199">脅威管理 > ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="32c5d-199">Threat management > Dashboard</span></span>
- <span data-ttu-id="32c5d-200">脅威管理 > ポリシー</span><span class="sxs-lookup"><span data-stu-id="32c5d-200">Threat management > Policy</span></span>
- <span data-ttu-id="32c5d-201">レポート > ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="32c5d-201">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="32c5d-202">評価の設定</span><span class="sxs-lookup"><span data-stu-id="32c5d-202">Setting up the evaluation</span></span>

<span data-ttu-id="32c5d-203">評価のためにセットアップフローを開始すると、2つのルーティングオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-203">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="32c5d-204">組織のメールルーティングのセットアップと評価のニーズに応じて、サードパーティのサービスプロバイダーとオンプレミスまたはその両方、または Microsoft Exchange Online のみを使用しているかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-204">Depending on your organization’s mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="32c5d-205">サードパーティのパートナーやオンプレミスのサービスプロバイダーを使用している場合は、ドロップダウンメニューからベンダー名を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-205">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="32c5d-206">その他のコネクタ関連の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-206">Provide the other connector-related details.</span></span>

- <span data-ttu-id="32c5d-207">MX レコードが Microsoft を指していて、Exchange Online メールボックスを持っている場合は、Microsoft Exchange Online を選択します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-207">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="32c5d-208">設定を確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-208">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="32c5d-209">[評価の **作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-209">Then, select **Create evaluation**.</span></span> <span data-ttu-id="32c5d-210">セットアップが完了したことを示す確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-210">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="32c5d-211">Microsoft Defender for Office 365 評価レポートは、1日に1回生成されます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-211">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="32c5d-212">データの入力には最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="32c5d-212">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="32c5d-213">Exchange ルール (オプション)</span><span class="sxs-lookup"><span data-stu-id="32c5d-213">Exchange rules (optional)</span></span>

<span data-ttu-id="32c5d-214">既存のゲートウェイを使用している場合は、コネクタの拡張フィルター処理を有効にし、受信側の送信元 IP アドレスを変更するため、フィルター処理をバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32c5d-214">If you have an existing gateway, you might want to bypass filtering because it will activate enhanced filtering for connectors and alter the incoming sender IP address.</span></span> <span data-ttu-id="32c5d-215">バイパスするには、Exchange 管理センターに移動し、SCL-1 のポリシーを作成します (まだ使用していない場合)。</span><span class="sxs-lookup"><span data-stu-id="32c5d-215">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don’t already have one).</span></span> <span data-ttu-id="32c5d-216">ルールコンポーネントの詳細と動作方法については、「Exchange Online のメールフロールール (トランスポートルール)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32c5d-216">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="32c5d-217">機能を評価する</span><span class="sxs-lookup"><span data-stu-id="32c5d-217">Evaluate capabilities</span></span>

<span data-ttu-id="32c5d-218">評価レポートが生成された後、組織内の電子メールおよびコラボレーションワークスペースで、高度な脅威のリンク数、高度な脅威の添付ファイル、および潜在的な impersonations が特定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-218">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="32c5d-219">試用期間が終了したら、90日間レポートへのアクセスを続行できます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-219">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="32c5d-220">ただし、これ以上情報は収集されません。</span><span class="sxs-lookup"><span data-stu-id="32c5d-220">However, it won’t collect any more information.</span></span> <span data-ttu-id="32c5d-221">試用期間が終了した後に Microsoft Defender for Office 365 を引き続き使用する場合は、 [Microsoft defender For office 365 (Plan 2) の有料サブスクリプションを購入](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)してください。</span><span class="sxs-lookup"><span data-stu-id="32c5d-221">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="32c5d-222">[ **設定** ] に移動すると、ルーティングを更新したり、いつでも評価をオフにしたりできます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-222">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="32c5d-223">ただし、同じセットアッププロセスをもう一度実行する必要があります。これをオフにした後に評価を続行することを決定します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-223">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="32c5d-224">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="32c5d-224">Provide feedback</span></span>

<span data-ttu-id="32c5d-225">フィードバックは、高度な攻撃から環境を保護する上で役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="32c5d-225">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="32c5d-226">製品の機能や評価結果の印象とインプレッションを共有します。</span><span class="sxs-lookup"><span data-stu-id="32c5d-226">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="32c5d-227">[ **フィードバックを提供** する] を選択して、ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="32c5d-227">Select **Give feedback** to let us know what you think.</span></span>
