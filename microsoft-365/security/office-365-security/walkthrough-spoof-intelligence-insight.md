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
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602117"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="d40d9-104">チュートリアル-Office 365 の Microsoft Defender のスプーフィングインテリジェンスの洞察</span><span class="sxs-lookup"><span data-stu-id="d40d9-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d40d9-105">Office 365 の Defender を使用する Microsoft 365 組織では、スプーフィングインテリジェンスの洞察を使用して、認証されていない電子メール (SPF、DKIM、または DMARC のチェックに合格しないドメインからのメッセージ) をどの外部送信者が正当に送信しているかをすばやく判断できます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="d40d9-106">既知の外部送信者に、既知の場所からのスプーフィングされたメッセージの送信を許可することにより、誤検知 (正常なメールが不良としてマークされている) を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-106">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="d40d9-107">許可された送信者を監視することで、安全でないメッセージが組織内に到着しないようにするためのセキュリティの追加の層を提供します。</span><span class="sxs-lookup"><span data-stu-id="d40d9-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="d40d9-108">レポートと分析情報の詳細については、「 [Security & コンプライアンスセンターのレポートと分析](reports-and-insights-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40d9-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="d40d9-109">このチュートリアルは、セキュリティ & コンプライアンスセンターに対していくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="d40d9-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="d40d9-110">レポートと分析情報の移動については、「 [関連項目](#related-topics) 」セクションのチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40d9-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d40d9-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="d40d9-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d40d9-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d40d9-113">[ **Security dashboard** ] ページに直接移動するには、を使用 <https://protection.office.com/searchandinvestigation/dashboard> します。</span><span class="sxs-lookup"><span data-stu-id="d40d9-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="d40d9-114">セキュリティ & コンプライアンスセンターでは、複数のダッシュボードからスプーフィングインテリジェンスの洞察を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="d40d9-115">どのダッシュボードを使用しているかに関係なく、洞察は同じ情報を提供し、同じタスクをすばやく実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="d40d9-116">この記事の手順を実行する前に、セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40d9-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d40d9-117">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="d40d9-117">**Organization Management**</span></span>
  - <span data-ttu-id="d40d9-118">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="d40d9-118">**Security Administrator**</span></span>
  - <span data-ttu-id="d40d9-119">**セキュリティリーダ**</span><span class="sxs-lookup"><span data-stu-id="d40d9-119">**Security Reader**</span></span>
  - <span data-ttu-id="d40d9-120">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="d40d9-120">**Global Reader**</span></span>

  <span data-ttu-id="d40d9-121">**注**: microsoft 365 管理センターで対応する Azure Active Directory の役割にユーザーを追加すると、セキュリティ & コンプライアンスセンター _と_ 、microsoft 365 の他の機能に対するアクセス許可で必要なアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d40d9-122">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40d9-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="d40d9-123">Office 365 の Microsoft Defender で、フィッシング対策ポリシーのスプーフィングインテリジェンスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d40d9-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="d40d9-124">スプーフィングインテリジェンスは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d40d9-124">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="d40d9-125">詳細については、「 [Configure フィッシング対策ポリシーを Microsoft Defender の Office 365 に構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40d9-125">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="d40d9-126">スプーフィングインテリジェンスを使用して、認証されていないメッセージを送信する送信者を監視および管理する方法については、「 [Microsoft 365 でスプーフィングインテリジェンスを構成](learn-about-spoof-intelligence.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40d9-126">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="d40d9-127">セキュリティ & コンプライアンスセンターでのスプーフィングインテリジェンスに関する洞察を開く</span><span class="sxs-lookup"><span data-stu-id="d40d9-127">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="d40d9-128">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理**] ダッシュボードに移動し \> **ます。**</span><span class="sxs-lookup"><span data-stu-id="d40d9-128">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="d40d9-129">[ **Insights** ] 行で、次のいずれかのアイテムを探します。</span><span class="sxs-lookup"><span data-stu-id="d40d9-129">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="d40d9-130">**過去7日間にわたって偽装** されたドメイン: この洞察は、スプーフィングインテリジェンスが有効になっていることを示します (既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="d40d9-130">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="d40d9-131">**スプーフィング保護を有効に** する: この洞察は、スプーフィングインテリジェンスが無効であることを示し、[洞察] をクリックすると、スプーフィングインテリジェンスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-131">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="d40d9-132">ダッシュボードの洞察には、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-132">The insight on the dashboard shows you information like this:</span></span>

   ![スプーフィングインテリジェンスの洞察のスクリーンショット](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="d40d9-134">この洞察には、次の2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="d40d9-134">This insight has two modes:</span></span>

   - <span data-ttu-id="d40d9-135">**洞察モード**: スプーフィングインテリジェンスが有効になっている場合は、過去7日間のスプーフィングインテリジェンス機能によって影響を受けたメッセージの数が洞察によって示されます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="d40d9-136">**If モード**: スプーフィングインテリジェンスが無効な場合、過去7日間のスプーフィングインテリジェンス機能によって影響を受け *たメッセージの数が洞察* に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="d40d9-137">どちらの方法でも、洞察に表示される偽装されたドメインは、 **疑わしいドメイン** と不審では **ないドメイン** の2つのカテゴリに分かれています。</span><span class="sxs-lookup"><span data-stu-id="d40d9-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="d40d9-138">**疑わしいドメイン** は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d40d9-138">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="d40d9-139">信頼度の高いスプーフィング: 過去の送信パターンとドメインの評価スコアに基づいて、ドメインがスプーフィングされており、これらのドメインからのメッセージが悪意を持っている可能性が高いことを確信しています。</span><span class="sxs-lookup"><span data-stu-id="d40d9-139">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="d40d9-140">適度な信頼度のスプーフィング: 過去の送信パターンとドメインの評価スコアに基づいて、ドメインがスプーフィングされており、これらのドメインから送信されたメッセージが正当であると確信しています。</span><span class="sxs-lookup"><span data-stu-id="d40d9-140">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="d40d9-141">誤検知は、信頼度の高いスプーフィングよりも、このカテゴリの可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="d40d9-141">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="d40d9-142">**非疑わしいドメイン**: ドメインに障害が発生した明示的な電子メール認証チェック [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [dkim](use-dkim-to-validate-outbound-email.md)、および [DMARC](use-dmarc-to-validate-email.md))。</span><span class="sxs-lookup"><span data-stu-id="d40d9-142">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="d40d9-143">しかし、ドメインは暗黙的な電子メール認証チェック ([複合認証](email-validation-and-authentication.md#composite-authentication)) に合格しています。</span><span class="sxs-lookup"><span data-stu-id="d40d9-143">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="d40d9-144">その結果、メッセージに対してスプーフィング対策アクションが実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d40d9-144">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="d40d9-145">スプーフィングインテリジェンスの洞察から、疑わしいドメインに関する詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="d40d9-145">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="d40d9-146">スプーフィングインテリジェンスの情報については、「 **疑わしいドメイン** または不審では **ないドメイン** 」をクリックして、「 **スプーフィングインテリジェンス** の情報」ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d40d9-146">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="d40d9-147">[ **スプーフィングインテリジェンスの洞察** ] ページには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d40d9-147">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="d40d9-148">**偽装ドメイン**: 電子メールクライアントの [ **差出人** ] ボックスに表示されている偽装ユーザーのドメイン。</span><span class="sxs-lookup"><span data-stu-id="d40d9-148">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="d40d9-149">このアドレスは、アドレスとも呼ばれ `5322.From` ます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-149">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="d40d9-150">**インフラストラクチャ**: _送信元インフラストラクチャ_ とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-150">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="d40d9-151">送信元の電子メールサーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) に含まれているドメイン。</span><span class="sxs-lookup"><span data-stu-id="d40d9-151">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="d40d9-152">送信元 IP アドレスに PTR レコードがない場合は、送信元のインフラストラクチャが \<source IP\> /24 (たとえば、192.168.100.100/24) として識別されます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-152">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="d40d9-153">**Message count**: 過去7日間の指定したスプーフィングドメインを含む組織への送信元インフラストラクチャからのメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="d40d9-153">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="d40d9-154">**最終表示** 日: 偽装ドメインを含む送信元インフラストラクチャからメッセージが受信された最後の日付。</span><span class="sxs-lookup"><span data-stu-id="d40d9-154">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="d40d9-155">**スプーフィングの種類**: この値は **External** です。</span><span class="sxs-lookup"><span data-stu-id="d40d9-155">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="d40d9-156">**スプーフィングが許可されますか?**: ここに表示される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d40d9-156">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="d40d9-157">**Yes**: スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージを許可し、スプーフィングされた電子メールとして処理しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d40d9-157">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="d40d9-158">**いいえ**: スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-158">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="d40d9-159">このアクションは、既定のフィッシング対策ポリシーまたはカスタムのマルウェア対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動** します)]。</span><span class="sxs-lookup"><span data-stu-id="d40d9-159">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="d40d9-160">詳細については、「 [Configure フィッシング対策ポリシーを Microsoft Defender の Office 365 に構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40d9-160">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="d40d9-161">リスト内の項目を選択して、フライアウトのドメイン/送信インフラストラクチャペアに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="d40d9-161">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="d40d9-162">情報には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-162">The information includes:</span></span>
   - <span data-ttu-id="d40d9-163">これをキャッチした理由。</span><span class="sxs-lookup"><span data-stu-id="d40d9-163">Why we caught this.</span></span>
   - <span data-ttu-id="d40d9-164">必要な作業</span><span class="sxs-lookup"><span data-stu-id="d40d9-164">What you need to do.</span></span>
   - <span data-ttu-id="d40d9-165">ドメインの概要。</span><span class="sxs-lookup"><span data-stu-id="d40d9-165">A domain summary.</span></span>
   - <span data-ttu-id="d40d9-166">送信者に関する WhoIs データ。</span><span class="sxs-lookup"><span data-stu-id="d40d9-166">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="d40d9-167">同じ送信者からのテナントに表示された同様のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d40d9-167">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="d40d9-168">ここから、ドメイン/送信インフラストラクチャペアを [ **スプーフィングを許可する** ] 送信者許可一覧から追加または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-168">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="d40d9-169">それに応じてトグルを設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="d40d9-169">Simply set the toggle accordingly.</span></span>

   ![スプーフィングインテリジェンスの詳細情報ウィンドウにあるドメインのスクリーンショット](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="d40d9-171">[スプーフィングを許可する] リストへのドメインの追加</span><span class="sxs-lookup"><span data-stu-id="d40d9-171">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="d40d9-172">スプーフィングインテリジェンスの洞察から [スプーフィングを許可する] 一覧にドメインを追加すると、スプーフィングされたドメイン *と* 送信元インフラストラクチャの組み合わせのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-172">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="d40d9-173">偽装されたドメインからの電子メールを任意のソースから許可することも、すべてのドメインの送信元インフラストラクチャから電子メールを許可することもできません。</span><span class="sxs-lookup"><span data-stu-id="d40d9-173">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="d40d9-174">たとえば、次のドメインに [スプーフィングを許可する] リストを許可します。</span><span class="sxs-lookup"><span data-stu-id="d40d9-174">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="d40d9-175">**ドメイン**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="d40d9-175">**Domain**: gmail.com</span></span>
- <span data-ttu-id="d40d9-176">**インフラストラクチャ**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="d40d9-176">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="d40d9-177">そのドメイン/送信側のインフラストラクチャペアからの電子メールのみがスプーフィングを許可されます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-177">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="d40d9-178">他の送信者が gmail.com をスプーフィングすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="d40d9-178">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="d40d9-179">Tms.mx.com からの他のドメイン内のメッセージは、スプーフィングインテリジェンスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="d40d9-179">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d40d9-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="d40d9-180">Related topics</span></span>

[<span data-ttu-id="d40d9-181">Microsoft 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="d40d9-181">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
