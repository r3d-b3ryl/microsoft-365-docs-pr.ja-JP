---
title: スプーフィング インテリジェンス分析のチュートリアル
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理者は、スプーフィング インテリジェンスのインサイトのしくみを学習できます。 電子メール認証チェック (SPF、DKIM、DMARC) に合格しないドメインから組織に正当に電子メールを送信している送信者を迅速に判断できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287973"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff2d5-104">チュートリアル - Microsoft Defender for Office 365 でのスプーフィング インテリジェンスの分析情報</span><span class="sxs-lookup"><span data-stu-id="ff2d5-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff2d5-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ff2d5-105">**Applies to**</span></span>
- [<span data-ttu-id="ff2d5-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ff2d5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ff2d5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff2d5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ff2d5-108">Defender for Office 365 を使用している Microsoft 365 組織では、スプーフィング インテリジェンスの洞察を使用して、認証されていないメール (SPF、DKIM、または DMARC チェックに合格しないドメインからのメッセージ) を正当に送信している外部送信者をすばやく特定できます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-108">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="ff2d5-109">既知の外部送信者が既知の場所からスプーフィングされたメッセージを送信することを許可することで、誤検知を減らします (良いメールは悪いとマークされます)。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-109">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="ff2d5-110">許可されたスプーフィングされた送信者を監視することで、安全でないメッセージが組織に到着することを防ぐため、セキュリティの追加レイヤーを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-110">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="ff2d5-111">レポートと分析情報の詳細については、セキュリティ/コンプライアンス センターの「レポート [と&参照してください](reports-and-insights-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-111">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="ff2d5-112">このチュートリアルは、セキュリティ/コンプライアンス センター&の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-112">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="ff2d5-113">レポートと分析情報のナビゲーションについては、「関連トピック」セクションのチュートリアル [を参照](#related-topics) してください。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-113">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ff2d5-114">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ff2d5-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ff2d5-115"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-115">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ff2d5-116">[セキュリティ ダッシュボード] ページに **直接移動するには** 、次のコマンドを使用します <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-116">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="ff2d5-117">セキュリティ/コンプライアンス センターでは、複数のダッシュボードからスプーフィング インテリジェンス&表示できます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-117">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="ff2d5-118">どのダッシュボードを参照している場合でも、インサイトは同じ詳細を提供し、同じタスクをすばやく実行できます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-118">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly do the same tasks.</span></span>

- <span data-ttu-id="ff2d5-119">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="ff2d5-119">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ff2d5-120">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="ff2d5-120">**Organization Management**</span></span>
  - <span data-ttu-id="ff2d5-121">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="ff2d5-121">**Security Administrator**</span></span>
  - <span data-ttu-id="ff2d5-122">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="ff2d5-122">**Security Reader**</span></span>
  - <span data-ttu-id="ff2d5-123">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="ff2d5-123">**Global Reader**</span></span>

  <span data-ttu-id="ff2d5-124">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ff2d5-125">**注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-125">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ff2d5-126">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="ff2d5-127">Microsoft Defender for Office 365 のフィッシング対策ポリシーでスプーフィング インテリジェンスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-127">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ff2d5-128">スプーフィング インテリジェンスは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-128">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="ff2d5-129">詳細については [、「Microsoft Defender for Office 365」](configure-atp-anti-phishing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-129">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="ff2d5-130">スプーフィング インテリジェンスを使用して、認証されていないメッセージを送信している送信者を監視および管理するには [、「Microsoft 365](learn-about-spoof-intelligence.md)でスプーフィング インテリジェンスを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-130">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="ff2d5-131">セキュリティ/コンプライアンス センターでスプーフィング インテリジェンス&開く</span><span class="sxs-lookup"><span data-stu-id="ff2d5-131">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="ff2d5-132">セキュリティ/コンプライアンス センター&、脅威管理 **ダッシュボードに移動** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="ff2d5-132">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="ff2d5-133">**[Insights] 行** で、次のいずれかの項目を探します。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-133">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="ff2d5-134">**過去 7** 日間のスプーフィングされたドメインの可能性: この分析情報は、スプーフィング インテリジェンスが有効 (既定で有効になっている) を示します。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-134">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="ff2d5-135">**スプーフィング保護** を有効にする : このインサイトは、スプーフィング インテリジェンスが無効に設定され、そのインサイトをクリックすると、スプーフィング インテリジェンスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-135">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="ff2d5-136">ダッシュボードのインサイトには、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-136">The insight on the dashboard shows you information like this:</span></span>

   ![スプーフィング インテリジェンスの分析情報のスクリーンショット](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="ff2d5-138">このインサイトには、次の 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-138">This insight has two modes:</span></span>

   - <span data-ttu-id="ff2d5-139">**インサイト モード**: スプーフィング インテリジェンスが有効になっている場合、過去 7 日間にスプーフィング インテリジェンス機能によって影響を受け取ったメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-139">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="ff2d5-140">**モードの場合**: スプーフィング インテリジェンスが無効になっている場合、過去7 日間にスプーフィング インテリジェンス機能によって影響を受けるメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-140">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="ff2d5-141">どちらの場合も、分析情報に表示されるスプーフィングされたドメインは、疑わしいドメインと疑わしいドメイン以外の 2 つのカテゴリ **に分かれています**。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-141">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="ff2d5-142">**不審なドメインには、次のものが** 含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-142">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="ff2d5-143">信頼度の高いスプーフィング: ドメインの過去の送信パターンと評判スコアに基づいて、ドメインがスプーフィングを行い、これらのドメインからのメッセージが悪意のある可能性が高いという確信を持っています。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-143">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="ff2d5-144">中程度の信頼度のスプーフィング: 過去の送信パターンとドメインの評判スコアに基づいて、ドメインがスプーフィングを行い、これらのドメインから送信されたメッセージが正当であると確信しています。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-144">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="ff2d5-145">誤検知は、高確度スプーフィングよりもこのカテゴリに含まれる可能性が高いです。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-145">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="ff2d5-146">**疑わしいドメイン以外**: ドメインが SPF、DKIM、[](use-dkim-to-validate-outbound-email.md)[および DMARC](use-dmarc-to-validate-email.md)の明示的な電子メール認証チェックに失敗しました。 [](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="ff2d5-146">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="ff2d5-147">ただし、ドメインは暗黙的な電子メール認証チェック (複合認証)[に合格しました](email-validation-and-authentication.md#composite-authentication)。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-147">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="ff2d5-148">その結果、メッセージに対してスプーフィング対策アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-148">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="ff2d5-149">スプーフィング インテリジェンスの分析情報から疑わしいドメインに関する詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="ff2d5-149">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="ff2d5-150">スプーフィング インテリジェンスの分析情報で、[**疑わしいドメイン**] または [疑わしいドメインではないドメイン] をクリックして、[スプーフィング インテリジェンスの分析 **情報] ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-150">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="ff2d5-151">ス **プーフィング インテリジェンスのインサイト** ページには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-151">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="ff2d5-152">**スプーフィン** グされたドメイン: メール クライアントの [From] ボックスに表示されるスプーフィング **されたユーザーの** ドメイン。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-152">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="ff2d5-153">このアドレスは、アドレスとも呼 `5322.From` ばれる。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-153">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="ff2d5-154">**インフラストラクチャ**: 送信インフラストラクチャ _とも呼ばれる。_</span><span class="sxs-lookup"><span data-stu-id="ff2d5-154">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="ff2d5-155">送信元の電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-155">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="ff2d5-156">送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (例: 192.168.100.100/24)。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-156">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="ff2d5-157">**メッセージ数**: 過去 7 日以内に指定されたスプーフィングされたドメインを含む、送信インフラストラクチャから組織へのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-157">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="ff2d5-158">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span><span class="sxs-lookup"><span data-stu-id="ff2d5-158">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="ff2d5-159">**スプーフィングの** 種類 : この値は **External です**。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-159">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="ff2d5-160">**スプーフィングが許可されますか?**: ここに表示される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-160">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="ff2d5-161">**は** い : スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われるのではありません。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-161">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="ff2d5-162">**いいえ**: スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィング済みとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-162">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="ff2d5-163">アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシー (既定値は [メッセージを迷惑メール フォルダーに移動] です) **によって制御されます**。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-163">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="ff2d5-164">詳細については [、「Microsoft Defender for Office 365」](configure-atp-anti-phishing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-164">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="ff2d5-165">リスト内の項目を選択して、ドメインと送信インフラストラクチャのペアに関する詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-165">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="ff2d5-166">情報には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-166">The information includes:</span></span>
   - <span data-ttu-id="ff2d5-167">これをキャッチした理由。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-167">Why we caught this.</span></span>
   - <span data-ttu-id="ff2d5-168">実行する必要がある操作。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-168">What you need to do.</span></span>
   - <span data-ttu-id="ff2d5-169">ドメインの概要。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-169">A domain summary.</span></span>
   - <span data-ttu-id="ff2d5-170">送信者に関する WhoIs データ。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-170">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="ff2d5-171">テナントで同じ送信者から見た同様のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-171">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="ff2d5-172">ここから、[送信者のスプーフィングを許可する] 許可リストからドメイン/送信インフラストラクチャのペアを追加または削除 **する方法も** 選択できます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-172">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="ff2d5-173">必要に応じてトグルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-173">Simply set the toggle accordingly.</span></span>

   ![[スプーフィング インテリジェンスの分析情報] ウィンドウのドメインのスクリーンショット](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="ff2d5-175">許可されたスプーフィングリストへのドメインの追加</span><span class="sxs-lookup"><span data-stu-id="ff2d5-175">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="ff2d5-176">スプーフィング インテリジェンスの洞察からのスプーフィングの許可リストにドメインを追加すると、スプーフィングされたドメインと送信インフラストラクチャの組み合わせだけが許可されます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-176">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="ff2d5-177">スプーフィングされたドメインからの電子メールをソースから許可したり、ドメインの送信インフラストラクチャからの電子メールを許可したりは許可されません。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-177">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="ff2d5-178">たとえば、許可されたスプーフィングリストに対して次のドメインを許可します。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-178">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="ff2d5-179">**ドメイン**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="ff2d5-179">**Domain**: gmail.com</span></span>
- <span data-ttu-id="ff2d5-180">**インフラストラクチャ**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="ff2d5-180">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="ff2d5-181">そのドメイン/送信インフラストラクチャ のペアからのメールだけがスプーフィングを許可されます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-181">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="ff2d5-182">スプーフィングを試みるgmail.com送信者は許可されません。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-182">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="ff2d5-183">他のドメインのメッセージは、tms.mx.com インテリジェンスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="ff2d5-183">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff2d5-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff2d5-184">Related topics</span></span>

[<span data-ttu-id="ff2d5-185">Microsoft 365 のスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="ff2d5-185">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
