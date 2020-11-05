---
title: チュートリアル-スプーフィングインテリジェンスの洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理者は、スプーフィングインテリジェンスの理解がどのように機能するかを知ることができます。 電子メール認証の確認 (SPF、DKIM、または DMARC) を通過しないドメインから組織に対して、どの送信者がメールを正当に送信しているかを迅速に判断できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920480"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a2be-104">チュートリアル-Office 365 の Microsoft Defender のスプーフィングインテリジェンスの洞察</span><span class="sxs-lookup"><span data-stu-id="0a2be-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0a2be-105">Office 365 の Defender を使用する Microsoft 365 組織では、スプーフィングインテリジェンスの洞察を使用して、どの送信者が認証された電子メールを正当に送信しているかをすばやく判断できます (SPF、DKIM、または DMARC チェックに合格していないドメインからのメッセージ)。</span><span class="sxs-lookup"><span data-stu-id="0a2be-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="0a2be-106">既知の送信者が既知の場所からスプーフィングされたメッセージを送信することを許可することにより、誤検知 (正常なメールが不良としてマークされる) を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="0a2be-107">許可された送信者を監視することで、安全でないメッセージが組織内に到着しないようにするためのセキュリティの追加の層を提供します。</span><span class="sxs-lookup"><span data-stu-id="0a2be-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="0a2be-108">レポートと分析情報の詳細については、「 [Security & コンプライアンスセンターのレポートと分析](reports-and-insights-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a2be-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="0a2be-109">このチュートリアルは、セキュリティ & コンプライアンスセンターに対していくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0a2be-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="0a2be-110">レポートと分析情報の移動については、「 [関連項目](#related-topics) 」セクションのチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a2be-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0a2be-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0a2be-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0a2be-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0a2be-113">[ **Security dashboard** ] ページに直接移動するには、を使用 <https://protection.office.com/searchandinvestigation/dashboard> します。</span><span class="sxs-lookup"><span data-stu-id="0a2be-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="0a2be-114">セキュリティ & コンプライアンスセンターでは、複数のダッシュボードからスプーフィングインテリジェンスの洞察を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="0a2be-115">どのダッシュボードを使用しているかに関係なく、洞察は同じ情報を提供し、同じタスクをすばやく実行することができます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="0a2be-116">このトピックの手順を実行する前に、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2be-116">You need to be assigned permissions before you can do the procedures in this topic.</span></span> <span data-ttu-id="0a2be-117">スプーフィングインテリジェンスの洞察を使用するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2be-117">To use the spoof intelligence insight, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="0a2be-118">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者** 。</span><span class="sxs-lookup"><span data-stu-id="0a2be-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="0a2be-119">**組織の管理** または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **検疫管理** 。</span><span class="sxs-lookup"><span data-stu-id="0a2be-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>
  - <span data-ttu-id="0a2be-120">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ閲覧者** 。</span><span class="sxs-lookup"><span data-stu-id="0a2be-120">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="0a2be-121">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **表示限定の組織管理** 。</span><span class="sxs-lookup"><span data-stu-id="0a2be-121">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="0a2be-122">Office 365 の Microsoft Defender で、フィッシング対策ポリシーのスプーフィングインテリジェンスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="0a2be-122">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0a2be-123">詳細については、「 [Configure フィッシング対策ポリシーを Microsoft Defender の Office 365 に構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a2be-123">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="0a2be-124">スプーフィングインテリジェンスを使用して、認証されていないメッセージを送信する送信者を監視および管理する方法については、「 [Microsoft 365 でスプーフィングインテリジェンスを構成](learn-about-spoof-intelligence.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a2be-124">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="0a2be-125">セキュリティ & コンプライアンスセンターでのスプーフィングインテリジェンスに関する洞察を開く</span><span class="sxs-lookup"><span data-stu-id="0a2be-125">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="0a2be-126">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** ] ダッシュボードに移動し \> **ます。**</span><span class="sxs-lookup"><span data-stu-id="0a2be-126">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="0a2be-127">[ **Insights** ] 行で、次のいずれかのアイテムを探します。</span><span class="sxs-lookup"><span data-stu-id="0a2be-127">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="0a2be-128">**スプーフィングインテリジェンスが有効になっ** ています。この洞察は、 **過去30日間の認証に失敗したスプーフィングドメイン** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-128">**Spoof intelligence is enabled** : The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="0a2be-129">これが既定です。</span><span class="sxs-lookup"><span data-stu-id="0a2be-129">This is the default.</span></span>
   - <span data-ttu-id="0a2be-130">**スプーフィングインテリジェンスが無効になっ** ています。名前付きの **スプーフィング保護を有効** にし、それをクリックすると、スプーフィングインテリジェンスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-130">**Spoof intelligence is disabled** : The insight in named **Enable Spoof Protection** , and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="0a2be-131">ダッシュボードの洞察には、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-131">The insight on the dashboard shows you information like this:</span></span>

   ![スプーフィングインテリジェンスの洞察のスクリーンショット](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="0a2be-133">この洞察には、次の2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="0a2be-133">This insight has two modes:</span></span>

   - <span data-ttu-id="0a2be-134">[ **洞察モード** ]: スプーフィングインテリジェンスが有効になっている場合、過去30日間のスプーフィングインテリジェンス機能によって影響を受けたメッセージの数が洞察に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-134">**Insight mode** : If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="0a2be-135">**If モード** : スプーフィングインテリジェンスが無効な場合、過去30日間のスプーフィングインテリジェンス機能によって影響を受け *たメッセージの数が洞察* に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-135">**What if mode** : If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="0a2be-136">どちらの方法でも、洞察に表示される偽装されたドメインは、 **疑わしいドメイン** の組と **不審でないドメインのペア** という2つのカテゴリに分かれています。</span><span class="sxs-lookup"><span data-stu-id="0a2be-136">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="0a2be-137">これらのカテゴリは、確認のために3つの異なるバケットにさらに細分化されています。</span><span class="sxs-lookup"><span data-stu-id="0a2be-137">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="0a2be-138">**ドメインペア** は、From アドレスと送信元インフラストラクチャの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="0a2be-138">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="0a2be-139">From アドレスは、電子メールクライアントの [差出人] ボックスに表示される送信者の電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0a2be-139">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="0a2be-140">このアドレスは、アドレスとも呼ばれ `5322.From` ます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-140">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="0a2be-141">送信元のインフラストラクチャまたは送信者は、送信元 IP アドレスの逆引き DNS 参照 (PTR レコード) の組織ドメインです。</span><span class="sxs-lookup"><span data-stu-id="0a2be-141">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="0a2be-142">送信元の IP アドレスに PTR レコードがない場合、送信元の IP アドレスは、CIDR 表記法 (/24) で255.255.255.0 サブネットマスクを使用して識別されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-142">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="0a2be-143">たとえば、IP アドレスが192.168.100.100 の場合、送信者の完全な IP アドレスは 192.168.100.100/24 です。</span><span class="sxs-lookup"><span data-stu-id="0a2be-143">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="0a2be-144">**疑わしいドメインペア** は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0a2be-144">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="0a2be-145">**信頼度の高いスプーフィング** : 過去の送信パターンとドメインの評価スコアに基づいて、ドメインがスプーフィングされており、これらのドメインからのメッセージが悪意を持っている可能性が高いことを確信しています。</span><span class="sxs-lookup"><span data-stu-id="0a2be-145">**High-confidence spoof** : Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="0a2be-146">**適度な信頼度のスプーフィング** : 過去の送信パターンとドメインの評価スコアに基づいて、ドメインがスプーフィングされており、これらのドメインから送信されたメッセージが正当であると確信しています。</span><span class="sxs-lookup"><span data-stu-id="0a2be-146">**Moderate confidence spoof** : Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="0a2be-147">誤検知は、信頼度の高いスプーフィングよりも、このカテゴリの可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0a2be-147">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="0a2be-148">**不審でないドメインのペア** ( **rescued スプーフィング** を含む): ドメインに障害が発生した明示的な電子メール認証チェック [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [dkim](use-dkim-to-validate-outbound-email.md)、および [DMARC](use-dmarc-to-validate-email.md))。</span><span class="sxs-lookup"><span data-stu-id="0a2be-148">**Non-suspicious domain pairs** (includes **rescued spoof** ): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="0a2be-149">しかし、ドメインは暗黙的な電子メール認証チェック ([複合認証](email-validation-and-authentication.md#composite-authentication)) に合格しています。</span><span class="sxs-lookup"><span data-stu-id="0a2be-149">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="0a2be-150">その結果、メッセージに対してスプーフィング対策アクションが実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="0a2be-150">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="0a2be-151">スプーフィングインテリジェンスの洞察から、疑わしいドメインペアに関する詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="0a2be-151">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="0a2be-152">スプーフィングインテリジェンスの洞察で、いずれかのドメインペア (high、中、または rescued) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a2be-152">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="0a2be-153">[ **スプーフィングインテリジェンスの理解** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-153">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="0a2be-154">このページには、認証されていない電子メールを組織に送信している送信者の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-154">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="0a2be-155">この情報は、スプーフィングされたメッセージを承認するか、さらにアクションを実行する必要があるかを判断するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-155">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="0a2be-156">メッセージ数、スプーフィングが最後に検出された日付などによって、情報を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-156">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="0a2be-157">テーブル内のアイテムを選択して、ドメインペアに関する豊富な情報を含む詳細ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-157">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="0a2be-158">情報には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-158">The information includes:</span></span>
   - <span data-ttu-id="0a2be-159">これをキャッチした理由。</span><span class="sxs-lookup"><span data-stu-id="0a2be-159">Why we caught this.</span></span>
   - <span data-ttu-id="0a2be-160">必要な作業</span><span class="sxs-lookup"><span data-stu-id="0a2be-160">What you need to do.</span></span>
   - <span data-ttu-id="0a2be-161">ドメインの概要。</span><span class="sxs-lookup"><span data-stu-id="0a2be-161">A domain summary.</span></span>
   - <span data-ttu-id="0a2be-162">送信者に関する WhoIs データ。</span><span class="sxs-lookup"><span data-stu-id="0a2be-162">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="0a2be-163">同じ送信者からのテナントに表示された同様のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0a2be-163">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="0a2be-164">ここから、ドメインペアを **Allowedtospoof** safe sender リストから追加または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-164">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![スプーフィングインテリジェンスの詳細情報ウィンドウにあるドメインのスクリーンショット](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="0a2be-166">AllowedToSpoof リストのドメインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0a2be-166">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="0a2be-167">ドメインのペアのスプーフィングインテリジェンスに関する情報ウィンドウにある、AllowedToSpoof (安全な送信者) 一覧のドメインを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="0a2be-167">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="0a2be-168">それに応じてトグルを設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="0a2be-168">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="0a2be-169">ドメインペアを許可すると、偽装されたドメイン *と* 送信元インフラストラクチャの組み合わせのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-169">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="0a2be-170">偽装されたドメインからの電子メールを任意のソースから許可することも、すべてのドメインの送信元インフラストラクチャから電子メールを許可することもできません。</span><span class="sxs-lookup"><span data-stu-id="0a2be-170">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="0a2be-171">たとえば、次のドメインペアが組織にスプーフィングされたメッセージを送信することを許可します。</span><span class="sxs-lookup"><span data-stu-id="0a2be-171">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="0a2be-172">*スプーフィング* されたドメイン: gmail.com "</span><span class="sxs-lookup"><span data-stu-id="0a2be-172">*Spoofed Domain* : gmail.com"</span></span>
- <span data-ttu-id="0a2be-173">*インフラストラクチャの送信* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="0a2be-173">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="0a2be-174">そのドメインペアからの電子メールのみがスプーフィングを許可されます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-174">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="0a2be-175">他の送信者が gmail.com をスプーフィングすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="0a2be-175">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="0a2be-176">Tms.mx.com からの他のドメイン内のメッセージは、スプーフィングインテリジェンスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="0a2be-176">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a2be-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a2be-177">Related topics</span></span>

[<span data-ttu-id="0a2be-178">Microsoft 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="0a2be-178">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
