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
ms.openlocfilehash: 819f78883aa75fbbdded2e47c1bb85945f080233
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108405"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="e2f25-103">サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成</span><span class="sxs-lookup"><span data-stu-id="e2f25-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="e2f25-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e2f25-104">**Applies to**</span></span>
- [<span data-ttu-id="e2f25-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e2f25-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e2f25-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e2f25-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e2f25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2f25-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e2f25-108">この記事で説明する機能はプレビューで、すべてのユーザーが利用できるとは言え、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2f25-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="e2f25-109">既定で組織を[](secure-by-default.md)セキュリティで保護するために、Exchange Online Protection (EOP) では、マルウェアまたは高信頼フィッシングとして識別されるメッセージの安全なリストやフィルター バイパスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="e2f25-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="e2f25-110">ただし、フィルター処理されていないメッセージの配信を必要とする特定のシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="e2f25-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="e2f25-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-111">For example:</span></span>

- <span data-ttu-id="e2f25-112">**サード パーティのフィッシング シミュレーション**: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="e2f25-113">**セキュリティ操作 (SecOps)** メールボックス: セキュリティ チームがフィルター処理されていないメッセージ (良いメッセージと悪いメッセージの両方) を収集および分析するために使用する専用のメールボックス。</span><span class="sxs-lookup"><span data-stu-id="e2f25-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="e2f25-114">これらの特定の _シナリオで_ これらのメッセージがフィルター Microsoft 365されるのを防ぐには、Microsoft 365の高度な _配信ポリシーを_ 使用します。 <sup>\*</sup>高度な配信ポリシーにより、これらのシナリオのメッセージで次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="e2f25-115">EOP と Microsoft Defender のフィルターは、Office 365に対してアクションを実行しません。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2f25-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="e2f25-116">[スパムとフィッシングのゼロアワー パージ (ZAP)](zero-hour-auto-purge.md) は、これらのメッセージに対して何も実行しません。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2f25-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="e2f25-117">[これらのシナリオでは](alerts.md) 、既定のシステム通知はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="e2f25-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="e2f25-118">[Defender の AIR とクラスター化では、Office 365](office-365-air.md)メッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="e2f25-119">特に、サード パーティ製のフィッシング シミュレーションの場合:</span><span class="sxs-lookup"><span data-stu-id="e2f25-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="e2f25-120">[管理者の申請は](admin-submission.md) 、メッセージがフィッシング シミュレーション キャンペーンの一部であり、実際の脅威ではないという自動応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="e2f25-121">アラートと AIR はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="e2f25-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="e2f25-122">[セーフ Defender for Office 365](safe-links.md)リンクは、これらのメッセージで特定された URL をブロックまたは削除しません。</span><span class="sxs-lookup"><span data-stu-id="e2f25-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="e2f25-123">[セーフ Defender Office 365](safe-attachments.md)添付ファイルは、これらのメッセージ内の添付ファイルを削除しません。</span><span class="sxs-lookup"><span data-stu-id="e2f25-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="e2f25-124"><sup>\*</sup> マルウェアのフィルター処理やマルウェアに対する ZAP をバイパスできない。</span><span class="sxs-lookup"><span data-stu-id="e2f25-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="e2f25-125">高度な配信ポリシーによって識別されるメッセージはセキュリティ上の脅威ではないので、メッセージはシステムオーバーライドとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="e2f25-126">管理者は、次のエクスペリエンスでこれらのシステムオーバーライドをフィルター処理して分析できます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="e2f25-127">ウイルス対策プラン 2 の Defender での脅威エクスプローラー/Office 365検出</span><span class="sxs-lookup"><span data-stu-id="e2f25-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="e2f25-128">脅威[エクスプローラー/リアルタイム検出](mdo-email-entity-page.md)の Email エンティティ ページ</span><span class="sxs-lookup"><span data-stu-id="e2f25-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="e2f25-129">脅威 [保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e2f25-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="e2f25-130">エンドポイント向け Microsoft Defender での高度な検索</span><span class="sxs-lookup"><span data-stu-id="e2f25-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="e2f25-131">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="e2f25-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e2f25-132">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="e2f25-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e2f25-133"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="e2f25-134">[高度な配信] ページに **直接移動するには** 、を開きます <https://security.microsoft.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="e2f25-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="e2f25-135">この記事の手順を実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2f25-135">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e2f25-136">高度な配信ポリシーで構成された設定を作成、変更、または削除するには、Microsoft 365 Defender ポータルのセキュリティ管理者役割グループのメンバーであり **、Exchange Online** の組織の管理役割グループ **のメンバーである必要があります**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-136">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="e2f25-137">高度な配信ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2f25-137">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e2f25-138">詳細については、「Microsoft 365 Defender[](permissions-microsoft-365-security-center.md)ポータルのアクセス許可」および「Exchange Online」[を参照してください](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="e2f25-138">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e2f25-139">ユーザーを対応する Azure Active Directory ロールに追加すると、ユーザーは Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可を与Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e2f25-139">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e2f25-140">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2f25-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="e2f25-141">高度な配信Microsoft 365 Defender SecOps メールボックスを構成するには、次のポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-141">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="e2f25-142">このポータルMicrosoft 365 Defender、[メールの送信] & **[** ルールの脅威ポリシー&] セクションの [詳細な配信 \>  \>  \> ] \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-142">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="e2f25-143">[高度 **な配信] ページ** で **、[SecOps** メールボックス] タブが選択されていることを確認し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-143">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="e2f25-144">[編集 ![ ] アイコン [ ](../../media/m365-cc-sc-edit-icon.png) **編集] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-144">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="e2f25-145">フィッシング シミュレーションが構成されていない場合は、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-145">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="e2f25-146">開く **[SecOps** メールボックスの編集] フライアウトで、次のいずれかの手順を実行して、SecOps メールボックスとして指定する既存の Exchange Online メールボックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-146">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="e2f25-147">ボックス内をクリックし、メールボックスの一覧を解決し、メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-147">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="e2f25-148">ボックス内をクリックすると、メールボックスの識別子 (名前、表示名、エイリアス、電子メール アドレス、アカウント名など) の入力を開始し、結果からメールボックス (表示名) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-148">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="e2f25-149">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-149">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e2f25-150">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="e2f25-150">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="e2f25-151">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="e2f25-151">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e2f25-153">値の隣。</span><span class="sxs-lookup"><span data-stu-id="e2f25-153">next to the value.</span></span>

4. <span data-ttu-id="e2f25-154">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2f25-154">When you're finished, click **Save**.</span></span>

<span data-ttu-id="e2f25-155">構成した SecOps メールボックス エントリは **、[SecOps** メールボックス] タブに表示されます。変更するには、タブの ![ [編集] ](../../media/m365-cc-sc-edit-icon.png) **アイコン [編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2f25-155">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="e2f25-156">高度な配信Microsoft 365 Defenderでサード パーティのフィッシング シミュレーションを構成するには、Microsoft 365 Defender ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-156">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="e2f25-157">このポータルMicrosoft 365 Defender、[メールの送信] & **[** ルールの脅威ポリシー&] セクションの [詳細な配信 \>  \>  \> ] \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-157">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="e2f25-158">[高度 **な配信] ページ** で、[フィッシング シミュレーション] **タブを選択** し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-158">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="e2f25-159">[編集 ![ ] アイコン [ ](../../media/m365-cc-sc-edit-icon.png) **編集] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-159">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="e2f25-160">フィッシング シミュレーションが構成されていない場合は、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-160">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="e2f25-161">開く **[サード パーティ製フィッシング シミュレーションの編集] フライ** アウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-161">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="e2f25-162">**送信ドメイン**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押したり、ボックスの下に表示される値を選択して、少なくとも 1 つの電子メール アドレス ドメイン (contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-162">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="e2f25-163">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-163">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e2f25-164">最大 10 のエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-164">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="e2f25-165">**送信 IP**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択することで、少なくとも 1 つの有効な IPv4 アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2f25-165">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="e2f25-166">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-166">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e2f25-167">最大 10 のエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-167">You can add up to 10 entries.</span></span> <span data-ttu-id="e2f25-168">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e2f25-168">Valid values are:</span></span>
     - <span data-ttu-id="e2f25-169">単一 IP: たとえば、192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="e2f25-169">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="e2f25-170">IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。</span><span class="sxs-lookup"><span data-stu-id="e2f25-170">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="e2f25-171">CIDR IP: たとえば、192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="e2f25-171">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="e2f25-172">**許可** するシミュレーション URL : この設定を展開し、必要に応じて、フィッシング シミュレーション キャンペーンの一部である特定の URL を入力します。この URL は、ボックス内をクリックして値を入力し、Enter キーを押したり、ボックスの下に表示される値を選択したりしてブロックまたは削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2f25-172">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="e2f25-173">最大 10 のエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-173">You can add up to 10 entries.</span></span>

   <span data-ttu-id="e2f25-174">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="e2f25-174">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e2f25-176">値の隣。</span><span class="sxs-lookup"><span data-stu-id="e2f25-176">next to the value.</span></span>

4. <span data-ttu-id="e2f25-177">完了したら、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-177">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="e2f25-178">**初回:**[追加] を **クリックし**、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-178">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="e2f25-179">**既存の編集 :**[保存] を **クリックし** 、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2f25-179">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="e2f25-180">構成したサード パーティのフィッシング シミュレーション エントリが [フィッシング シミュレーション] **タブに表示** されます。変更するには、タブの ![ [編集] ](../../media/m365-cc-sc-edit-icon.png) **アイコン [編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2f25-180">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="e2f25-181">フィルター バイパスが必要なその他のシナリオ</span><span class="sxs-lookup"><span data-stu-id="e2f25-181">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="e2f25-182">高度な配信ポリシーが役立つ 2 つのシナリオに加えて、フィルター処理をバイパスする必要がある他のシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="e2f25-182">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="e2f25-183">**サード パーティ製フィルター**: ドメインの MXレコードが Office 365 を指していない場合 (メッセージは最初にどこか別の [](secure-by-default.md)場所にルーティングされます)、既定ではセキュリティで保護 *されません。*</span><span class="sxs-lookup"><span data-stu-id="e2f25-183">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="e2f25-184">サード パーティのフィルター処理によって既に評価されているメッセージに対して Microsoft のフィルター処理をバイパスするには、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2f25-184">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e2f25-185">詳細については、「メール フロー ルール [を使用してメッセージの SCL を設定する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)。</span><span class="sxs-lookup"><span data-stu-id="e2f25-185">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="e2f25-186">**レビュー中** の誤検知 : 管理者の申請を通じて Microsoft によって分析中の特定の [](admin-submission.md)メッセージを一時的に許可して、Microsoft に不適切とマークされている既知の良いメッセージ (誤検知) を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="e2f25-186">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="e2f25-187">すべての上書きと同様に、これらの許容量 **_は_** 一時的なものとすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2f25-187">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>
