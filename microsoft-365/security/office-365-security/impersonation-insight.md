---
title: 偽装の分析情報
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、偽装の分析情報がどのように機能するのかについて説明します。 電子メール認証チェック (SPF、DKIM、DMARC) に合格しないドメインから組織に電子メールを正当に送信している送信者をすばやく特定できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a11dd30030ccce886abd50ff72b5a09b10938ece
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535770"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a><span data-ttu-id="00b97-104">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="00b97-104">Impersonation insight in Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="00b97-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="00b97-105">**Applies to**</span></span>
- [<span data-ttu-id="00b97-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="00b97-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="00b97-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="00b97-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="00b97-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00b97-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="00b97-109">この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。</span><span class="sxs-lookup"><span data-stu-id="00b97-109">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="00b97-110">偽装とは、電子メール メッセージの送信者が実際または予想される送信者の電子メール アドレスと非常に似ている場所です。</span><span class="sxs-lookup"><span data-stu-id="00b97-110">Impersonation is where the sender of an email message looks very similar to a real or expected sender email address.</span></span> <span data-ttu-id="00b97-111">攻撃者は、多くの場合、受信者の信頼を得るために、フィッシングなどの攻撃で送信者の電子メール アドレスを偽装します。</span><span class="sxs-lookup"><span data-stu-id="00b97-111">Attackers often user impersonated sender email addresses in phishing or other types of attacks in an effort to gain the trust of the recipient.</span></span> <span data-ttu-id="00b97-112">偽装には基本的に 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="00b97-112">There are basically two types of impersonation:</span></span>

- <span data-ttu-id="00b97-113">**ドメイン偽装**: 偽装 lila@contoso.com 送信者の電子メール アドレスが lila@ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="00b97-113">**Domain impersonation**: Instead of lila@contoso.com, the impersonated sender's email address is lila@ćóntoso.com.</span></span>
- <span data-ttu-id="00b97-114">**ユーザーの偽装**: 偽装 michelle@contoso.com 送信者の電子メール アドレスが rnichell@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="00b97-114">**User impersonation**: Instead of michelle@contoso.com, the impersonated sender's email address is rnichell@contoso.com.</span></span>

<span data-ttu-id="00b97-115">偽装ドメインは通常、実際[](anti-spoofing-protection.md)の登録済みドメインなので、ドメイン偽装はドメインスプーフィングとは異なります。</span><span class="sxs-lookup"><span data-stu-id="00b97-115">Domain impersonation is different from [domain spoofing](anti-spoofing-protection.md), because the impersonated domain is typically a real, registered domain.</span></span> <span data-ttu-id="00b97-116">偽装ドメイン内の送信者からのメッセージは、スプーフィングの試行 (SPF、DKIM、DMARC) を識別する通常の電子メール認証チェックに合格する場合があります。</span><span class="sxs-lookup"><span data-stu-id="00b97-116">Messages from senders in the impersonated domain can and often do pass regular email authentication checks that would otherwise identify spoofing attempts (SPF, DKIM, and DMARC).</span></span>

<span data-ttu-id="00b97-117">偽装保護は、フィッシング対策ポリシー設定の一部です) は、Microsoft Defender に限定Office 365。</span><span class="sxs-lookup"><span data-stu-id="00b97-117">Impersonation protection is part of the anti-phishing policy settings) that are exclusive to Microsoft Defender for Office 365.</span></span> <span data-ttu-id="00b97-118">これらの設定の詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの偽装[設定」を参照してください](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="00b97-118">For more information about these settings, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="00b97-119">偽装の分析情報を使用して、偽装保護用に構成した偽装送信者または送信者ドメインからのメッセージをすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="00b97-119">You can use the impersonation insight to quickly identify messages from impersonated senders or sender domains that you've configured for impersonation protection.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="00b97-120">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="00b97-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="00b97-121"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="00b97-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="00b97-122">[フィッシング対策] ページで偽装の分析情報に直接 **移動** するには、 を使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="00b97-122">To go directly to the impersonation insight on the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="00b97-123">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="00b97-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="00b97-124">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="00b97-124">**Organization Management**</span></span>
  - <span data-ttu-id="00b97-125">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="00b97-125">**Security Administrator**</span></span>
  - <span data-ttu-id="00b97-126">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="00b97-126">**Security Reader**</span></span>
  - <span data-ttu-id="00b97-127">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="00b97-127">**Global Reader**</span></span>

  <span data-ttu-id="00b97-128">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00b97-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="00b97-129">**注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンス センターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="00b97-129">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="00b97-130">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00b97-130">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="00b97-131">Microsoft Defender のフィッシング対策ポリシーで偽装保護を有効にして構成Office 365。</span><span class="sxs-lookup"><span data-stu-id="00b97-131">You enable and configure impersonation protection in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="00b97-132">偽装保護は既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="00b97-132">Impersonation protection is not enabled by default.</span></span> <span data-ttu-id="00b97-133">詳細については[、「Microsoft Defender でフィッシング対策ポリシー](configure-atp-anti-phishing-policies.md)を構成する」を参照Office 365。</span><span class="sxs-lookup"><span data-stu-id="00b97-133">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="open-the-impersonation-insight-in-the-security--compliance-center"></a><span data-ttu-id="00b97-134">セキュリティ コンプライアンス センターで偽装&を開く</span><span class="sxs-lookup"><span data-stu-id="00b97-134">Open the impersonation insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="00b97-135">[セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="00b97-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="00b97-136">メインのフィッシング **対策ページでは**、偽装の分析情報は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="00b97-136">On the main **Anti-phishing page**, the impersonation insight looks like this:</span></span>

   <span data-ttu-id="00b97-137">この分析情報には、次の 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="00b97-137">This insight has two modes:</span></span>

    - <span data-ttu-id="00b97-138">**インサイト モード**: フィッシング対策ポリシーで偽装保護が有効および構成されている場合、この分析情報は、過去 7 日間に偽装された送信者から検出されたメッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="00b97-138">**Insight mode**: If impersonation protection is enabled and configured in any anti-phishing policies, the insight shows the number of detected messages from impersonated senders over the past seven days.</span></span> <span data-ttu-id="00b97-139">これは、すべてのフィッシング対策ポリシーから検出された偽装送信者の合計です。</span><span class="sxs-lookup"><span data-stu-id="00b97-139">This is the total of all detected impersonated senders from all anti-phishing policies.</span></span>
    - <span data-ttu-id="00b97-140">**If モード**: アクティブなフィッシング対策ポリシーで偽装保護が有効で構成されていない場合、過去 7 日間に偽装保護機能によって検出されたメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00b97-140">**What if mode**: If impersonation protection is not enabled and configured in any active anti-phishing policies, the insight shows you how many messages *would* have been detected by our impersonation protection capabilities over the past seven days.</span></span>

   <span data-ttu-id="00b97-141">いずれにし **ろ**、偽装ドメインは保護されたドメイン内の送信者からのメッセージの数を示しますが、偽装されたユーザーは保護されたユーザーからのメッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="00b97-141">Either way, **Domains impersonated** shows the number of messages from senders in protected domains, while **Users impersonated** shows the number of messages from protected users.</span></span>

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a><span data-ttu-id="00b97-142">偽装ドメインの送信者からのメッセージに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="00b97-142">View information about messages from senders in impersonated domains</span></span>

<span data-ttu-id="00b97-143">偽装の分析情報で、[偽装ドメイン **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="00b97-143">On the impersonation insight, click **Domains impersonated**.</span></span> <span data-ttu-id="00b97-144">開 **く偽装インサイト ページ** には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="00b97-144">The **Impersonation insight** page that opens contains the following information:</span></span>

- <span data-ttu-id="00b97-145">**Sender Domain**: 偽装ドメイン 。これは、電子メール メッセージの送信に使用されたドメインです。</span><span class="sxs-lookup"><span data-stu-id="00b97-145">**Sender Domain**: The impersonating domain, which is the domain that was used to send the email message.</span></span> 
- <span data-ttu-id="00b97-146">**メッセージ数**: 過去 7 日間に送信者ドメインを偽装したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="00b97-146">**Message count**: The number of messages from impersonating sender domain over the last 7 days.</span></span>
- <span data-ttu-id="00b97-147">**偽装の種類**: この値は、偽装の検出された場所 (たとえば、アドレス内 **のドメイン) を示します**。</span><span class="sxs-lookup"><span data-stu-id="00b97-147">**Impersonation type**: This value shows the detected location of the impersonation (for example, **Domain in address**).</span></span>
- <span data-ttu-id="00b97-148">**偽装ドメイン**: 偽装されたドメインは、フィッシング対策ポリシーで偽装保護用に構成されているドメインによく似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="00b97-148">**Impersonated domain(s)**: The impersonated domain, which should closely resemble the domain that's configured for impersonation protection in the anti-phishing policy.</span></span>
- <span data-ttu-id="00b97-149">**ドメインの種類**: この値は **、内部ドメイン** の会社ドメイン、またはカスタム **ドメイン** のカスタム ドメインです。</span><span class="sxs-lookup"><span data-stu-id="00b97-149">**Domain type**: This value is **Company domain** for internal domains or **Custom domain** for custom domains.</span></span>
- <span data-ttu-id="00b97-150">**ポリシー**: 偽装ドメインを検出したフィッシング対策ポリシー。</span><span class="sxs-lookup"><span data-stu-id="00b97-150">**Policy**: The anti-phishing policy that detected the impersonated domain.</span></span>
- <span data-ttu-id="00b97-151">**偽装を許可する**: 次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="00b97-151">**Allowed to impersonate**: One of the following values:</span></span>
  - <span data-ttu-id="00b97-152">**は** い: ドメインはスパム対策ポリシーで信頼されたドメイン (偽装保護の例外) として構成されています。</span><span class="sxs-lookup"><span data-stu-id="00b97-152">**Yes**: The domain was configured as trusted domain (an exception for impersonation protection) in the anti-spam policy.</span></span> <span data-ttu-id="00b97-153">偽装ドメイン内の送信者からのメッセージが検出されましたが、許可されています。</span><span class="sxs-lookup"><span data-stu-id="00b97-153">Messages from senders in the impersonated domain were detected, but allowed.</span></span>
  - <span data-ttu-id="00b97-154">**いいえ**: ドメインはスパム対策ポリシーで偽装保護用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="00b97-154">**No**: The domain was configured for impersonation protection in the anti-spam policy.</span></span> <span data-ttu-id="00b97-155">偽装ドメイン内の送信者からのメッセージが検出され、スパム対策ポリシーの偽装ドメインのアクションに基づいて処理されました。</span><span class="sxs-lookup"><span data-stu-id="00b97-155">Messages from senders in the impersonated domain were detected and acted upon based on the action for impersonated domains in the anti-spam policy.</span></span>

<span data-ttu-id="00b97-156">選択した列見出しをクリックすると、結果を並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="00b97-156">You can click selected column headings to sort the results.</span></span>

<span data-ttu-id="00b97-157">結果をフィルター処理するには、[Filter **domain]** ボックスを使用して、結果をフィルター処理する値のコンマ区切りリストを入力できます。</span><span class="sxs-lookup"><span data-stu-id="00b97-157">To filter the results, you can use the **Filter domain** box to enter a comma-separated list of values to filter the results.</span></span>

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a><span data-ttu-id="00b97-158">偽装ドメイン内の送信者からのメッセージに関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="00b97-158">View details about messages from senders in impersonated domains</span></span>

<span data-ttu-id="00b97-159">[偽装 **の分析情報] ページ** で、使用可能な行のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="00b97-159">On the **Impersonation insight** page, select one of the available rows.</span></span> <span data-ttu-id="00b97-160">表示される詳細フライアウトには、次の情報と機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="00b97-160">The details flyout that appears contains the following information and features:</span></span>

- <span data-ttu-id="00b97-161">**変更する選択偽装ポリシー**: 変更する影響を受けるフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="00b97-161">**Selection impersonation policy to modify**: Select the affected anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="00b97-162">ポリシーで偽装ドメインが定義されているポリシーのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="00b97-162">Only polices where the impersonated domain is defined in the policy are available.</span></span> <span data-ttu-id="00b97-163">前のページを参照して、偽装ドメインの検出に実際に責任を負ったポリシーを確認します (受信者とポリシーの優先度に基づく可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="00b97-163">Refer to the previous page to see which policy was actually responsible for detecting the impersonated domain (likely based on the recipient and the priority of the policy).</span></span>

- <span data-ttu-id="00b97-164">**偽装許可** リストに追加する: 次のトグルを使用して、選択したフィッシング対策ポリシーの信頼できる送信者とドメイン **(偽装** 例外) に送信者を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="00b97-164">**Add to the allowed to impersonation list**: Use this toggle to add or remove the sender from the **Trusted senders and domains** (impersonation exceptions) for the anti-phishing policy that you selected:</span></span>
  - <span data-ttu-id="00b97-165">このエントリ **の [偽装を許可する]** 値が **[いいえ**] の場合、トグルはオフになります。</span><span class="sxs-lookup"><span data-stu-id="00b97-165">If the **Allowed to impersonate** value for this entry was **No**, the toggle is off.</span></span> <span data-ttu-id="00b97-166">偽装保護によってこのドメイン内のすべての送信者を評価から除外するには、トグルを on: Toggle on に ![ スライドします ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="00b97-166">To exempt all senders in this domain from evaluation by impersonation protection, slide the toggle to on: ![Toggle on](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="00b97-167">ドメインは、フィッシング **対策ポリシーの** 偽装保護設定の信頼済みドメインリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="00b97-167">The domain is added to the **Trusted domains** list in the impersonation protection settings of the anti-phishing policy.</span></span>
  - <span data-ttu-id="00b97-168">このエントリ **の [偽装を許可する]** の値が **[は** い] の場合、トグルはオンになります。</span><span class="sxs-lookup"><span data-stu-id="00b97-168">If the **Allowed to impersonate** value for this entry was **Yes**, the toggle is on.</span></span> <span data-ttu-id="00b97-169">偽装保護によってこのドメイン内のすべての送信者を評価に戻す場合は、トグルを ![ オフにスライドします。 ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="00b97-169">To return all senders in this domain to evaluation by impersonation protection, slide the toggle to off: ![Toggle off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="00b97-170">ドメインは、フィッシング **対策ポリシーの** 偽装保護設定の [信頼されたドメイン] リストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="00b97-170">The domain is removed from the **Trusted domains** list in the impersonation protection settings of the anti-phishing policy.</span></span>

- <span data-ttu-id="00b97-171">なぜこれをキャッチしたのか。</span><span class="sxs-lookup"><span data-stu-id="00b97-171">Why we caught this.</span></span>
- <span data-ttu-id="00b97-172">何をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00b97-172">What you need to do.</span></span>
- <span data-ttu-id="00b97-173">偽装されたドメインを一覧表示するドメインの概要。</span><span class="sxs-lookup"><span data-stu-id="00b97-173">A domain summary that list the impersonated domain.</span></span>
- <span data-ttu-id="00b97-174">送信者に関する WhoIs データ。</span><span class="sxs-lookup"><span data-stu-id="00b97-174">WhoIs data about the sender.</span></span>
- <span data-ttu-id="00b97-175">脅威エクスプローラーを開 [き](threat-explorer.md) 、送信者に関するその他の詳細を表示するリンク。</span><span class="sxs-lookup"><span data-stu-id="00b97-175">A link to open [Threat Explorer](threat-explorer.md) to see additional details about the sender.</span></span>
- <span data-ttu-id="00b97-176">組織に配信された同じ送信者からの類似のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="00b97-176">Similar messages from the same sender that were delivered to your organization.</span></span>

## <a name="view-information-about-messages-from-impersonated-senders"></a><span data-ttu-id="00b97-177">偽装された送信者からのメッセージに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="00b97-177">View information about messages from impersonated senders</span></span>

<span data-ttu-id="00b97-178">偽装の分析情報で、[偽装ユーザー **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="00b97-178">On the impersonation insight, click **Users impersonated**.</span></span> <span data-ttu-id="00b97-179">開 **く偽装インサイト ページ** には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="00b97-179">The **Impersonation insight** page that opens contains the following information:</span></span>

- <span data-ttu-id="00b97-180">**Sender**: 電子メール メッセージを送信した偽装送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="00b97-180">**Sender**: The email address of the impersonating sender that sent the email message.</span></span>
- <span data-ttu-id="00b97-181">**メッセージ数**: 過去 7 日間の偽装送信者からのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="00b97-181">**Message count**: The number of messages from the impersonating sender over the last 7 days.</span></span>
- <span data-ttu-id="00b97-182">**偽装の種類**: この値は、 **表示名の User です**。</span><span class="sxs-lookup"><span data-stu-id="00b97-182">**Impersonation type**: This value is **User in display name**.</span></span>
- <span data-ttu-id="00b97-183">**偽装ユーザー**: 偽装された送信者の電子メール アドレスで、フィッシング対策ポリシーで偽装保護用に構成されているユーザーと密接に似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="00b97-183">**Impersonated user(s)**: The email address of the impersonated sender, which should closely resemble the user that's configured for impersonation protection in the anti-phishing policy.</span></span>
- <span data-ttu-id="00b97-184">**ユーザーの種類**: この値は、適用される保護の種類(保護されたユーザーやメールボックス インテリジェンスなど)**を示します**。</span><span class="sxs-lookup"><span data-stu-id="00b97-184">**User type**: This value shows the type of protection applied (for example, **Protected user** or **Mailbox Intelligence**).</span></span>
- <span data-ttu-id="00b97-185">**ポリシー**: 偽装された送信者を検出したフィッシング対策ポリシー。</span><span class="sxs-lookup"><span data-stu-id="00b97-185">**Policy**: The anti-phishing policy that detected the impersonated sender.</span></span>
- <span data-ttu-id="00b97-186">**偽装を許可する**: 次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="00b97-186">**Allowed to impersonate**: One of the following values:</span></span>
  - <span data-ttu-id="00b97-187">**は** い : 送信者はスパム対策ポリシーで信頼できるユーザー (偽装保護の例外) として構成されています。</span><span class="sxs-lookup"><span data-stu-id="00b97-187">**Yes**: The sender was configured as trusted user (an exception for impersonation protection) in the anti-spam policy.</span></span> <span data-ttu-id="00b97-188">偽装された送信者からのメッセージは検出されましたが、許可されています。</span><span class="sxs-lookup"><span data-stu-id="00b97-188">Messages from the impersonated sender were detected, but allowed.</span></span>
  - <span data-ttu-id="00b97-189">**いいえ**: 送信者はスパム対策ポリシーで偽装保護用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="00b97-189">**No**: The sender was configured for impersonation protection in the anti-spam policy.</span></span> <span data-ttu-id="00b97-190">偽装された送信者からのメッセージが検出され、スパム対策ポリシーの偽装ユーザーに対するアクションに基づいて処理されました。</span><span class="sxs-lookup"><span data-stu-id="00b97-190">Messages from the impersonated sender were detected and acted upon based on the action for impersonated users in the anti-spam policy.</span></span>

<span data-ttu-id="00b97-191">選択した列見出しをクリックすると、結果を並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="00b97-191">You can click selected column headings to sort the results.</span></span>

<span data-ttu-id="00b97-192">結果をフィルター処理するには、[送信者のフィルター  ] ボックスを使用して、結果をフィルター処理する値のコンマ区切りリストを入力できます。</span><span class="sxs-lookup"><span data-stu-id="00b97-192">To filter the results, you can use the **Filter sender** box to enter a comma-separated list of values to filter the results.</span></span>

### <a name="view-details-about-messages-from-impersonated-senders"></a><span data-ttu-id="00b97-193">偽装された送信者からのメッセージに関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="00b97-193">View details about messages from impersonated senders</span></span>

<span data-ttu-id="00b97-194">[偽装 **の分析情報] ページ** で、使用可能な行のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="00b97-194">On the **Impersonation insight** page, select one of the available rows.</span></span> <span data-ttu-id="00b97-195">表示される詳細フライアウトには、次の情報と機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="00b97-195">The details flyout that appears contains the following information and features:</span></span>

- <span data-ttu-id="00b97-196">**変更する選択偽装ポリシー**: 変更する影響を受けるフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="00b97-196">**Selection impersonation policy to modify**: Select the affected anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="00b97-197">ポリシーで偽装された送信者が定義されているポリシーのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="00b97-197">Only polices where the impersonated sender is defined in the policy are available.</span></span> <span data-ttu-id="00b97-198">前のページを参照して、偽装された送信者の検出に実際に責任を負ったポリシーを確認します (受信者とポリシーの優先度に基づく可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="00b97-198">Refer to the previous page to see which policy was actually responsible for detecting the impersonated sender (likely based on the recipient and the priority of the policy).</span></span>

- <span data-ttu-id="00b97-199">**偽装許可** リストに追加する: 次のトグルを使用して、選択したフィッシング対策ポリシーの信頼できる送信者とドメイン **(偽装** 例外) に送信者を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="00b97-199">**Add to the allowed to impersonation list**: Use this toggle to add or remove the sender from the **Trusted senders and domains** (impersonation exceptions) for the anti-phishing policy that you selected:</span></span>
  - <span data-ttu-id="00b97-200">このエントリ **の [偽装を許可する]** 値が **[いいえ**] の場合、トグルはオフになります。</span><span class="sxs-lookup"><span data-stu-id="00b97-200">If the **Allowed to impersonate** value for this entry was **No**, the toggle is off.</span></span> <span data-ttu-id="00b97-201">偽装保護によって送信者の評価を除外するには、トグルを on: トグル オンに ![ スライドします ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="00b97-201">To exempt the sender from evaluation by impersonation protection, slide the toggle to on: ![Toggle on](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="00b97-202">送信者は、フィッシング **対策ポリシーの** 偽装保護設定の [信頼済みユーザー] リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="00b97-202">The sender is added to the **Trusted users** list in the impersonation protection settings of the anti-phishing policy.</span></span>
  - <span data-ttu-id="00b97-203">このエントリ **の [偽装を許可する]** の値が **[は** い] の場合、トグルはオンになります。</span><span class="sxs-lookup"><span data-stu-id="00b97-203">If the **Allowed to impersonate** value for this entry was **Yes**, the toggle is on.</span></span> <span data-ttu-id="00b97-204">偽装保護によって送信者を評価に戻す場合は、トグルをオフにスライドします。トグルを ![ オフにします ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="00b97-204">To return the sender to evaluation by impersonation protection, slide the toggle to off: ![Toggle off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="00b97-205">送信者は、フィッシング対策ポリシー **の** 偽装保護設定の [信頼済みユーザー] リストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="00b97-205">The sender is removed from the **Trusted users** list in the impersonation protection settings of the anti-phishing policy.</span></span>

- <span data-ttu-id="00b97-206">なぜこれをキャッチしたのか。</span><span class="sxs-lookup"><span data-stu-id="00b97-206">Why we caught this.</span></span>
- <span data-ttu-id="00b97-207">何をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00b97-207">What you need to do.</span></span>
- <span data-ttu-id="00b97-208">偽装された送信者を一覧表示する送信者の概要。</span><span class="sxs-lookup"><span data-stu-id="00b97-208">A sender summary that list the impersonated sender.</span></span>
- <span data-ttu-id="00b97-209">送信者に関する WhoIs データ。</span><span class="sxs-lookup"><span data-stu-id="00b97-209">WhoIs data about the sender.</span></span>
- <span data-ttu-id="00b97-210">脅威エクスプローラーを開 [き](threat-explorer.md) 、送信者に関するその他の詳細を表示するリンク。</span><span class="sxs-lookup"><span data-stu-id="00b97-210">A link to open [Threat Explorer](threat-explorer.md) to see additional details about the sender.</span></span>
- <span data-ttu-id="00b97-211">組織に配信された同じ送信者からの類似のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="00b97-211">Similar messages from the same sender that were delivered to your organization.</span></span>
