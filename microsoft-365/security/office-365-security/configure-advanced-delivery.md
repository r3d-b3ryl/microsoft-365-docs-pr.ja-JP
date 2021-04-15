---
title: サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Exchange Online Protection (EOP) の高度な配信ポリシーを使用して、サポートされている特定のシナリオ (サード パーティのフィッシング シミュレーションとセキュリティ操作 (SecOps) メールボックスに配信されるメッセージ) でフィルター処理すべきではないメッセージを識別する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 09e07d8406b470fd3dac25944d013b997f2f90c1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760437"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="344b0-103">サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成</span><span class="sxs-lookup"><span data-stu-id="344b0-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="344b0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="344b0-104">**Applies to**</span></span>
- [<span data-ttu-id="344b0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="344b0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="344b0-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="344b0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="344b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="344b0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="344b0-108">この記事で説明する機能はプレビューで、すべてのユーザーが利用できるとは言え、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="344b0-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="344b0-109">Exchange Online Protection [](secure-by-default.md)(EOP) では、マルウェアや信頼性の高いフィッシングの評決を引き起こしているメッセージに対して、安全なリストやフィルター バイパスを許可しないので、組織を既定でセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="344b0-109">We want to keep your organization [secure by default](secure-by-default.md), so Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that result in malware or high confidence phishing verdicts.</span></span> <span data-ttu-id="344b0-110">ただし、フィルター処理されていないメッセージの配信を必要とする特定のシナリオがあるという認識があります。</span><span class="sxs-lookup"><span data-stu-id="344b0-110">But, we recognize there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="344b0-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="344b0-111">For example:</span></span>

- <span data-ttu-id="344b0-112">**サード パーティのフィッシング シミュレーション**: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="344b0-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="344b0-113">**セキュリティ操作 (SecOps)** メールボックス: セキュリティ チームがフィルター処理されていないメッセージ (良いメッセージと悪いメッセージの両方) を収集および分析するために使用する専用のメールボックス。</span><span class="sxs-lookup"><span data-stu-id="344b0-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="344b0-114">Microsoft 365 の高度な配信ポリシーを使用して、これらの特定のシナリオでこれらのメッセージがフィルター処理されるのを防 <sup>\*</sup> ぐ。</span><span class="sxs-lookup"><span data-stu-id="344b0-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered<sup>\*</sup>.</span></span> <span data-ttu-id="344b0-115">高度な配信ポリシーにより、次のシナリオのメッセージはフィルター処理されません。</span><span class="sxs-lookup"><span data-stu-id="344b0-115">The advanced delivery policy ensures that messages in these scenarios are not filtered:</span></span>

- <span data-ttu-id="344b0-116">EOP と Microsoft Defender 365 のフィルター Office、これらのメッセージに対してアクションを実行しません。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="344b0-116">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="344b0-117">[スパムとフィッシングのゼロアワー パージ (ZAP)](zero-hour-auto-purge.md) は、これらのメッセージに対してアクションを実行しません。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="344b0-117">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="344b0-118">[既定のシステム通知](alerts.md) は、これらのシナリオではトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="344b0-118">[Default system alerts](alerts.md) are not triggered for these scenarios.</span></span>
- <span data-ttu-id="344b0-119">[365 の Defender の AIR とクラスター Office、これらの](office-365-air.md) メッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="344b0-119">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="344b0-120">特に、サード パーティ製のフィッシング シミュレーションの場合:</span><span class="sxs-lookup"><span data-stu-id="344b0-120">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="344b0-121">[管理者の申請は](admin-submission.md) 、メッセージがフィッシング シミュレーション キャンペーンの一部であり、実際の脅威ではないという自動応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="344b0-121">[Admin submissions](admin-submission.md) generates an automatic response stating that the message is part of a phishing simulation campaign and is not a real threat.</span></span> <span data-ttu-id="344b0-122">アラートと AIR はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="344b0-122">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="344b0-123">[Defender for Office 365](safe-links.md) のセーフ リンクは、これらのメッセージで特定された URL をブロックまたは削除しません。</span><span class="sxs-lookup"><span data-stu-id="344b0-123">[Safe Links in Defender for Office 365](safe-links.md) does not block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="344b0-124">[Defender 365 の安全な添付Office、](safe-attachments.md) これらのメッセージの添付ファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="344b0-124">[Safe Attachments in Defender for Office 365](safe-attachments.md) does not detonate attachments in these messages.</span></span>

<span data-ttu-id="344b0-125"><sup>\*</sup> マルウェアのフィルター処理やマルウェアに対する ZAP をバイパスできない。</span><span class="sxs-lookup"><span data-stu-id="344b0-125"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="344b0-126">高度な配信ポリシーによって識別されるメッセージはセキュリティ上の脅威ではないので、メッセージはシステムオーバーライドとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="344b0-126">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="344b0-127">管理者は、次のエクスペリエンスでこれらのシステムオーバーライドをフィルター処理して分析できます。</span><span class="sxs-lookup"><span data-stu-id="344b0-127">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="344b0-128">脅威エクスプローラー/365 プラン 2 の Defender Officeリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="344b0-128">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="344b0-129">脅威[エクスプローラー/リアルタイム検出](mdo-email-entity-page.md)の Email エンティティ ページ</span><span class="sxs-lookup"><span data-stu-id="344b0-129">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="344b0-130">脅威 [保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="344b0-130">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="344b0-131">エンドポイント向け Microsoft Defender での高度な検索</span><span class="sxs-lookup"><span data-stu-id="344b0-131">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="344b0-132">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="344b0-132">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="344b0-133">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="344b0-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="344b0-134"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="344b0-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="344b0-135">[高度な配信] ページに **直接移動するには** 、を開きます <https://protection.office.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="344b0-135">To go directly to the **Advanced delivery** page, open <https://protection.office.com/advanceddelivery>.</span></span>

- <span data-ttu-id="344b0-136">この記事の手順を実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="344b0-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="344b0-137">高度な配信ポリシーで構成された設定を作成、変更、または削除するには、セキュリティ **&** コンプライアンスセンターのセキュリティ管理者役割グループのメンバーであり **、Exchange Online** の組織の管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="344b0-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Security & Compliance Center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="344b0-138">高度な配信ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="344b0-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="344b0-139">詳細については、「セキュリティ コンプライアンス [センターのアクセス許可」と「exchange Online &アクセス](permissions-in-the-security-and-compliance-center.md) 許可 [」を参照してください](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="344b0-139">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="344b0-140">セキュリティ サービス コンプライアンス &を使用して、高度な配信ポリシーでサード パーティのフィッシング シミュレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="344b0-140">Use the Security & Compliance Center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="344b0-141">セキュリティ 管理コンプライアンス センター&、 **脅威管理ポリシー** \> **の [高度な配信** \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="344b0-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="344b0-142">[高度 **な配信] ページ** で、[フィッシング シミュレーション] **タブを** 選択し、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="344b0-142">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="344b0-143">開く **サード パーティのフィッシング シミュレーション の** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="344b0-143">On the **Third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="344b0-144">**送信ドメイン**: 少なくとも 1 つの電子メール アドレス ドメインが必要です (たとえば、contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="344b0-144">**Sending domain**: At least one email address domain is required (for example, contoso.com).</span></span> <span data-ttu-id="344b0-145">最大 10 のエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="344b0-145">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="344b0-146">**送信 IP**: 少なくとも 1 つの有効な IPv4 アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="344b0-146">**Sending IP**: At least one valid IPv4 address is required.</span></span> <span data-ttu-id="344b0-147">最大 10 のエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="344b0-147">You can add up to 10 entries.</span></span> <span data-ttu-id="344b0-148">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="344b0-148">Valid values are:</span></span>
     - <span data-ttu-id="344b0-149">単一 IP: たとえば、192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="344b0-149">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="344b0-150">IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。</span><span class="sxs-lookup"><span data-stu-id="344b0-150">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="344b0-151">CIDR IP: たとえば、192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="344b0-151">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="344b0-152">**許可するシミュレーション URL**: 必要に応じて、ブロックまたは削除すべきではないフィッシング シミュレーション キャンペーンの一部である特定の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="344b0-152">**Simulation URLs to allow**: Optionally, enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated.</span></span> <span data-ttu-id="344b0-153">最大 10 のエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="344b0-153">You can add up to 10 entries.</span></span>

4. <span data-ttu-id="344b0-154">完了したら、[保存] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="344b0-154">When you're finished, click **Save.**</span></span>

<span data-ttu-id="344b0-155">構成したサード パーティのフィッシング シミュレーション エントリが [フィッシング シミュレーション] **タブに表示** されます。変更するには、タブの **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="344b0-155">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="344b0-156">高度な配信ポリシー& SecOps メールボックスを構成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="344b0-156">Use the Security & Compliance Center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="344b0-157">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシーの **[高度な** \> **配信** \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="344b0-157">In the Security & Compliance Center, go to **Threat Management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="344b0-158">[高度 **な配信] ページ** で **、[SecOps** メールボックス] タブを選択し、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="344b0-158">On the **Advanced delivery** page, select the **SecOps mailbox** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="344b0-159">開く **SecOps メールボックス** のフライアウトで、SecOps メールボックスとして指定する既存の Exchange Online メールボックスの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="344b0-159">On the **SecOps mailbox** flyout that opens, enter the email addresses of existing Exchange Online mailboxes that you want to designate as SecOps mailboxes.</span></span> <span data-ttu-id="344b0-160">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="344b0-160">Distribution groups are not allowed.</span></span>

4. <span data-ttu-id="344b0-161">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="344b0-161">When you're finished, click **Save**.</span></span>

<span data-ttu-id="344b0-162">構成した SecOps メールボックス エントリは **、[SecOps** メールボックス] タブに表示されます。変更するには、タブの **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="344b0-162">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="344b0-163">フィルター バイパスが必要なその他のシナリオ</span><span class="sxs-lookup"><span data-stu-id="344b0-163">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="344b0-164">高度な配信ポリシーが役立つ 2 つのシナリオに加えて、フィルター処理をバイパスする必要がある他のシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="344b0-164">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="344b0-165">**サード パーティ製フィルター**: ドメインの MX レコードが Office 365 を指していない場合 (メッセージは最初にどこか別 [](secure-by-default.md)の場所にルーティングされます)、既定ではセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="344b0-165">**Third-party filters**: If you domain's MX record doesn't point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) is not available.</span></span>

  <span data-ttu-id="344b0-166">サード パーティのフィルター処理によって既に評価されているメッセージに対して Microsoft のフィルター処理をバイパスするには、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用します。「メッセージで [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)を設定するには、メール フロー ルールを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344b0-166">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules), see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

- <span data-ttu-id="344b0-167">**レビュー中** の誤検知 : 管理者の申請を通じて Microsoft によって分析中の特定の [](admin-submission.md)メッセージを一時的に許可して、Microsoft に不適切とマークされている既知の良いメッセージ (誤検知) を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="344b0-167">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="344b0-168">すべての上書きと同様に、これらの許容量は一時的なものとすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="344b0-168">As with all overrides, we highly recommended that these allowances are temporary.</span></span>
