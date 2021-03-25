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
description: 管理者は、スプーフィング インテリジェンスの分析情報がどのように機能するのかについて説明します。 電子メール認証チェック (SPF、DKIM、DMARC) に合格しないドメインから組織に電子メールを正当に送信している送信者をすばやく特定できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2b48b8540fb71404a0636120a5884d381b08cd1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206775"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="20d71-104">ウォークスルー - Microsoft Defender for microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="20d71-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="20d71-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="20d71-105">**Applies to**</span></span>
- [<span data-ttu-id="20d71-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="20d71-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="20d71-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20d71-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="20d71-108">Defender for Office 365 の Microsoft 365 組織では、スプーフィング インテリジェンスインサイトを使用して、認証されていないメール (SPF、DKIM、または DMARC チェックに合格しないドメインからのメッセージ) を正当に送信している外部送信者をすばやく特定できます。</span><span class="sxs-lookup"><span data-stu-id="20d71-108">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="20d71-109">既知の外部送信者が既知の場所からスプーフィングされたメッセージを送信できるようにすることで、誤検知を減らします (良いメールは悪いとマークされています)。</span><span class="sxs-lookup"><span data-stu-id="20d71-109">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="20d71-110">許可されたスプーフィングされた送信者を監視することで、セキュリティの層を追加して、安全でないメッセージが組織に到着することを防止します。</span><span class="sxs-lookup"><span data-stu-id="20d71-110">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="20d71-111">レポートと分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](reports-and-insights-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="20d71-111">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="20d71-112">このチュートリアルは、コンプライアンス センターのセキュリティ &の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="20d71-112">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="20d71-113">レポートと分析情報のナビゲーションについては、「関連トピック」セクションのチュートリアル [を参照](#related-topics) してください。</span><span class="sxs-lookup"><span data-stu-id="20d71-113">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

> [!NOTE]
> <span data-ttu-id="20d71-114">スプーフィング インテリジェンスの分析情報には、過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d71-114">The spoof intelligence insight shows data from the last 7 days.</span></span> <span data-ttu-id="20d71-115">Exchange Online PowerShell [の](learn-about-spoof-intelligence.md) スプーフィング インテリジェンス ポリシーと対応する [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) コマンドレットには、過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d71-115">The [spoof intelligence policy](learn-about-spoof-intelligence.md) and the corresponding [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) cmdlet in Exchange Online PowerShell shows data from the last 30 days.</span></span> <span data-ttu-id="20d71-116">[Get-SpoofMailReport には](/powershell/module/exchange/get-spoofmailreport)、最大 90 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d71-116">The [Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport) shows data for up to 90 days.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20d71-117">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="20d71-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20d71-118"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="20d71-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="20d71-119">[セキュリティ ダッシュボード] ページに **直接移動するには** 、 を使用します <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="20d71-119">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="20d71-120">スプーフィング インテリジェンスの分析情報は、セキュリティ コンプライアンス センターの複数のダッシュボード&できます。</span><span class="sxs-lookup"><span data-stu-id="20d71-120">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="20d71-121">どのダッシュボードを見ているかにかかわらず、インサイトは同じ詳細を提供し、同じタスクをすばやく実行できます。</span><span class="sxs-lookup"><span data-stu-id="20d71-121">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly do the same tasks.</span></span>

- <span data-ttu-id="20d71-122">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="20d71-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="20d71-123">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="20d71-123">**Organization Management**</span></span>
  - <span data-ttu-id="20d71-124">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="20d71-124">**Security Administrator**</span></span>
  - <span data-ttu-id="20d71-125">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="20d71-125">**Security Reader**</span></span>
  - <span data-ttu-id="20d71-126">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="20d71-126">**Global Reader**</span></span>

  <span data-ttu-id="20d71-127">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20d71-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="20d71-128">**注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="20d71-128">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="20d71-129">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20d71-129">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="20d71-130">365 の Microsoft Defender のフィッシング対策ポリシーでスプーフィング インテリジェンスを有効Officeします。</span><span class="sxs-lookup"><span data-stu-id="20d71-130">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="20d71-131">スプーフィング インテリジェンスは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="20d71-131">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="20d71-132">詳細については、「Configure anti-フィッシング ポリシー in [Microsoft Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="20d71-132">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="20d71-133">スプーフィング インテリジェンスを使用して、認証されていないメッセージを送信している送信者を監視および管理するには、「Configure スプーフィング インテリジェンス in [Microsoft 365」を参照してください](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="20d71-133">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="20d71-134">セキュリティ コンプライアンス センターでスプーフィング インテリジェンス&開く</span><span class="sxs-lookup"><span data-stu-id="20d71-134">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="20d71-135">[セキュリティ とコンプライアンス &] で、[脅威管理ダッシュボード **] に移動** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="20d71-135">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="20d71-136">**[Insights] 行** で、次のいずれかの項目を探します。</span><span class="sxs-lookup"><span data-stu-id="20d71-136">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="20d71-137">**過去 7 日間に** スプーフィングされたドメインの可能性が高い : この分析情報は、スプーフィング インテリジェンスが有効になっている (既定で有効になっている) かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="20d71-137">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="20d71-138">**スプーフィング保護** を有効にする: この分析情報は、スプーフィング インテリジェンスが無効になっていると示し、その分析情報をクリックするとスプーフィング インテリジェンスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="20d71-138">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="20d71-139">ダッシュボードの分析情報には、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d71-139">The insight on the dashboard shows you information like this:</span></span>

   ![スプーフィング インテリジェンスの分析情報のスクリーンショット](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="20d71-141">この分析情報には、次の 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="20d71-141">This insight has two modes:</span></span>

   - <span data-ttu-id="20d71-142">**インサイト モード**: スプーフィング インテリジェンスが有効になっている場合、過去 7 日間にスプーフィング インテリジェンス機能によって影響を受けるメッセージの数がインサイトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d71-142">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="20d71-143">**If モード**: スプーフィング インテリジェンスが無効になっている場合、この分析情報は、過去 7 日間にスプーフィング インテリジェンス機能によって影響を受けるメッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="20d71-143">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="20d71-144">いずれの場合も、インサイトに表示されるスプーフィングされたドメインは、疑わしいドメインと疑わしいドメイン以外の 2 つのカテゴリ **に分けられます**。</span><span class="sxs-lookup"><span data-stu-id="20d71-144">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="20d71-145">**疑わしいドメインには、次のものが** 含まれます。</span><span class="sxs-lookup"><span data-stu-id="20d71-145">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="20d71-146">高信頼スプーフィング: ドメインの過去の送信パターンと評判スコアに基づいて、ドメインがスプーフィングを行い、これらのドメインからのメッセージが悪意のある可能性が高いという確信が高いです。</span><span class="sxs-lookup"><span data-stu-id="20d71-146">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="20d71-147">中程度の信頼スプーフィング: 過去の送信パターンとドメインの評判スコアに基づいて、ドメインがスプーフィングを行い、これらのドメインから送信されるメッセージが正当であると適度に確信しています。</span><span class="sxs-lookup"><span data-stu-id="20d71-147">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="20d71-148">誤検知は、高信頼スプーフィングよりもこのカテゴリに含まれる可能性が高いです。</span><span class="sxs-lookup"><span data-stu-id="20d71-148">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="20d71-149">**疑わしいドメイン以外**: ドメインで明示的な電子メール認証が [失敗し、SPF、DKIM、](how-office-365-uses-spf-to-prevent-spoofing.md)および DMARC が [チェックされます](use-dmarc-to-validate-email.md)。 [](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="20d71-149">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="20d71-150">ただし、ドメインは暗黙的な電子メール認証チェック (複合認証)[に合格しました](email-validation-and-authentication.md#composite-authentication)。</span><span class="sxs-lookup"><span data-stu-id="20d71-150">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="20d71-151">その結果、メッセージに対してスプーフィング対策アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="20d71-151">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="20d71-152">スプーフィング インテリジェンスの分析情報から疑わしいドメインに関する詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="20d71-152">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="20d71-153">スプーフィング インテリジェンスの分析情報で、[疑 **わしい** ドメイン] または [不審でないドメイン] をクリックして、[スプーフィング インテリジェンスの分析情報]**ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="20d71-153">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="20d71-154">ス **プーフィング インテリジェンスの分析** 情報ページには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="20d71-154">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="20d71-155">**スプーフィング** されたドメイン: メール クライアントの [From] ボックスに表示されるスプーフィング **された** ユーザーのドメイン。</span><span class="sxs-lookup"><span data-stu-id="20d71-155">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="20d71-156">このアドレスは、アドレスとも呼 `5322.From` ばれる。</span><span class="sxs-lookup"><span data-stu-id="20d71-156">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="20d71-157">**インフラストラクチャ**: 送信インフラストラクチャ _とも呼ばれる_。</span><span class="sxs-lookup"><span data-stu-id="20d71-157">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="20d71-158">送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。</span><span class="sxs-lookup"><span data-stu-id="20d71-158">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="20d71-159">送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。</span><span class="sxs-lookup"><span data-stu-id="20d71-159">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="20d71-160">**メッセージ数**: 過去 7 日以内に、指定されたスプーフィングされたドメインを含む送信インフラストラクチャから組織へのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="20d71-160">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="20d71-161">**最後に** 表示される : スプーフィングされたドメインを含む送信インフラストラクチャからメッセージを受信した最後の日付。</span><span class="sxs-lookup"><span data-stu-id="20d71-161">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="20d71-162">**スプーフィングの** 種類 : この値は **外部です**。</span><span class="sxs-lookup"><span data-stu-id="20d71-162">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="20d71-163">**スプーフィングを許可しますか。**: ここに表示される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20d71-163">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="20d71-164">**は** い : スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われるのではありません。</span><span class="sxs-lookup"><span data-stu-id="20d71-164">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="20d71-165">**いいえ**: スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="20d71-165">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="20d71-166">アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシーによって制御されます (既定値は [メッセージを迷惑メール フォルダーに移動する] **です**)。</span><span class="sxs-lookup"><span data-stu-id="20d71-166">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="20d71-167">詳細については、「Configure anti-フィッシング ポリシー in [Microsoft Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="20d71-167">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="20d71-168">リスト内のアイテムを選択して、フライアウトのドメイン/送信インフラストラクチャ ペアに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="20d71-168">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="20d71-169">この情報には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="20d71-169">The information includes:</span></span>
   - <span data-ttu-id="20d71-170">なぜこれをキャッチしたのか。</span><span class="sxs-lookup"><span data-stu-id="20d71-170">Why we caught this.</span></span>
   - <span data-ttu-id="20d71-171">何をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d71-171">What you need to do.</span></span>
   - <span data-ttu-id="20d71-172">ドメインの概要。</span><span class="sxs-lookup"><span data-stu-id="20d71-172">A domain summary.</span></span>
   - <span data-ttu-id="20d71-173">送信者に関する WhoIs データ。</span><span class="sxs-lookup"><span data-stu-id="20d71-173">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="20d71-174">テナントで同じ送信者から見た同様のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="20d71-174">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="20d71-175">ここから、[送信者のスプーフィングを許可する] 一覧からドメイン/送信インフラストラクチャのペアを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="20d71-175">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="20d71-176">単にトグルを設定します。</span><span class="sxs-lookup"><span data-stu-id="20d71-176">Simply set the toggle accordingly.</span></span>

   ![スプーフィング インテリジェンスインサイト詳細ウィンドウのドメインのスクリーンショット](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="20d71-178">[スプーフィングを許可する] リストへのドメインの追加</span><span class="sxs-lookup"><span data-stu-id="20d71-178">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="20d71-179">スプーフィング インテリジェンスインサイトからスプーフィングを許可するリストにドメインを追加すると、スプーフィングされたドメインと送信インフラストラクチャの組み合わせだけが許可されます。</span><span class="sxs-lookup"><span data-stu-id="20d71-179">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="20d71-180">スプーフィングされたドメインからのメールを任意のソースから許可したり、任意のドメインの送信インフラストラクチャからの電子メールを許可したりはしない。</span><span class="sxs-lookup"><span data-stu-id="20d71-180">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="20d71-181">たとえば、次のドメインを [スプーフィングを許可する] リストに許可します。</span><span class="sxs-lookup"><span data-stu-id="20d71-181">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="20d71-182">**ドメイン**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="20d71-182">**Domain**: gmail.com</span></span>
- <span data-ttu-id="20d71-183">**インフラストラクチャ**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="20d71-183">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="20d71-184">スプーフィングが許可されるのは、そのドメイン/送信インフラストラクチャ ペアからのメールのみです。</span><span class="sxs-lookup"><span data-stu-id="20d71-184">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="20d71-185">スプーフィングを試みる gmail.com 送信者は許可されません。</span><span class="sxs-lookup"><span data-stu-id="20d71-185">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="20d71-186">スプーフィング インテリジェンスによって、tms.mx.com ドメイン内のメッセージがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="20d71-186">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="20d71-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="20d71-187">Related topics</span></span>

[<span data-ttu-id="20d71-188">Microsoft 365 でのスプーフィング防止保護</span><span class="sxs-lookup"><span data-stu-id="20d71-188">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)