---
title: Exchange Online Protection (EOP) の概要
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) がスタンドアロン環境とハイブリッド環境でオンプレミスの電子メール組織を保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b699c0d6353d725b8d03cf4cf556a3e2ac798041
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687055"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="3888f-103">Exchange Online Protection の概要</span><span class="sxs-lookup"><span data-stu-id="3888f-103">Exchange Online Protection overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3888f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3888f-104">**Applies to**</span></span>
- [<span data-ttu-id="3888f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3888f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3888f-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="3888f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3888f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3888f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3888f-108">Exchange Online Protection (EOP) は、スパムやマルウェアから組織を保護するのに役立つクラウドベースのフィルター サービスです。</span><span class="sxs-lookup"><span data-stu-id="3888f-108">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="3888f-109">EOP は、Exchange Online メールボックスを持つすべての Microsoft 365 組織に含まれています。</span><span class="sxs-lookup"><span data-stu-id="3888f-109">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="3888f-110">ただし、EOP は、次のオンプレミスシナリオでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3888f-110">However, EOP is also available in the following on-premises scenarios:</span></span>

- <span data-ttu-id="3888f-111">**スタンドアロンシナリオ:** EOP は、オンプレミスの Exchange 組織または他のオンプレミス SMTP 電子メール ソリューションに対してクラウドベースの電子メール保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="3888f-111">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="3888f-112">**ハイブリッド展開では**、EOP を構成して、オンプレミスメールボックスとクラウド メールボックスが混在している場合にメール環境を保護し、メール ルーティングを制御できます。</span><span class="sxs-lookup"><span data-stu-id="3888f-112">**In a hybrid deployment**: EOP can be configured to protect your email environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

<span data-ttu-id="3888f-113">これらのシナリオでは、EOP はメール環境の管理を簡素化し、オンプレミスのハードウェアとソフトウェアの保守に必要な多くの負担を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="3888f-113">In these scenarios, EOP can simplify the management of your email environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="3888f-114">このトピックの残りの部分では、スタンドアロン環境とハイブリッド環境での EOP の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-114">The rest of this topic explains how EOP works in standalone and hybrid environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="3888f-115">EOP の仕組み</span><span class="sxs-lookup"><span data-stu-id="3888f-115">How EOP works</span></span>

<span data-ttu-id="3888f-116">EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="3888f-116">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="迷惑メールまたは検疫、またはエンド ユーザーのメール配信の判決の前に、インターネットまたは顧客からのフィードバックが EOP に渡され、接続、マルウェア対策、Mailflow Rules-slash-Policy Filtering、およびコンテンツ フィルターを介して送信された電子メールのグラフィック。":::

- <span data-ttu-id="3888f-118">受信メッセージが EOP に入った場合、最初は接続フィルターを通過し、送信者の評判をチェックします。</span><span class="sxs-lookup"><span data-stu-id="3888f-118">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="3888f-119">スパムの大部分はこの時点で停止され、EOP によって拒否されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-119">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="3888f-120">詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3888f-120">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="3888f-121">次に、メッセージがマルウェアの兆候を検査します。</span><span class="sxs-lookup"><span data-stu-id="3888f-121">Then the message is inspected for signs of malware.</span></span> <span data-ttu-id="3888f-122">メッセージまたは添付ファイルにマルウェアが見つかった場合、メッセージは管理者専用の検疫ストアにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-122">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="3888f-123">マルウェア対策の構成の詳細については、こちらを参照 [してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3888f-123">You can learn more about configuring anti-malware [here](configure-anti-malware-policies.md).</span></span>

- <span data-ttu-id="3888f-124">メッセージはポリシー フィルター処理を続け、テンプレートから作成または適用するカスタム メール フロー ルール (トランスポート ルールとも呼ばれる) に対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-124">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="3888f-125">たとえば、特定の送信者からメールが届いたときにマネージャーに通知を送信するルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="3888f-125">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="3888f-126">データ損失防止 (DLP) チェックもこの時点で行います (Exchange Enterprise CAL with Services)。</span><span class="sxs-lookup"><span data-stu-id="3888f-126">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="3888f-127">次に、メッセージはコンテンツ フィルター (スパム対策とも呼ばれる) を通過します。</span><span class="sxs-lookup"><span data-stu-id="3888f-127">Next, the message passes through content filtering (also known as Anti-spam).</span></span> <span data-ttu-id="3888f-128">このフィルターがスパムまたはフィッシングと判断したメッセージは、検疫、またはユーザーの迷惑メール フォルダーなど、他のオプションに送信できます。</span><span class="sxs-lookup"><span data-stu-id="3888f-128">A message that this filter determines to be spam *or phish* can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="3888f-129">詳細については、「 [スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md) 」および「フィッシング対策ポリシーを構成 [する」を参照してください](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3888f-129">For more information see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="3888f-130">これらすべての保護層を正常に通過するメッセージは、受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-130">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="3888f-131">詳細については、「メール保護の [順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="3888f-131">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="3888f-132">オンプレミスの電子メール組織の EOP プランと機能</span><span class="sxs-lookup"><span data-stu-id="3888f-132">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="3888f-133">利用可能な EOP サブスクリプション プランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3888f-133">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="3888f-134">**EOP スタンドアロン**: オンプレミスの電子メール組織を保護するために EOP に登録します。</span><span class="sxs-lookup"><span data-stu-id="3888f-134">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="3888f-135">**Exchange Online の EOP** 機能: Exchange Online (スタンドアロンまたは Microsoft 365 の一部として) を含むサブスクリプションは、EOP を使用して Exchange Online メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="3888f-135">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="3888f-136">**Exchange Enterprise CAL with Services**: 追加の Exchange Enterprise CAL with Services ライセンスを購入したオンプレミスの Exchange 組織がある場合、EOP は付属のサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="3888f-136">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="3888f-137">すべての EOP サブスクリプション プランの要件、重要な制限、および機能の可用性については、「Exchange Online Protection サービスの説明」 [を参照してください](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="3888f-137">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="3888f-138">**365 E3 サブスクリプションOffice EOP が含まれています**。</span><span class="sxs-lookup"><span data-stu-id="3888f-138">If you have an **Office 365 E3 subscription it includes EOP**.</span></span> <span data-ttu-id="3888f-139">サブスクリプションで EOP セキュリティ機能をセットアップする手順と、microsoft Defender for Office 365 サブスクリプションが提供するセキュリティの追加に関する情報については、「脅威から保護する」を参照[してください。](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="3888f-139">For steps to set up EOP security feature in your subscription, and information on the added security a Microsoft Defender for Office 365 subscription can give you, see [protect against threats](protect-against-threats.md).</span></span> <span data-ttu-id="3888f-140">セットアップ用の EOP 機能の推奨設定については、「推奨事項[](best-practices-for-configuring-eop.md)」の記事を参照してください。EOP 設定は特に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-140">The recommended settings for EOP feature for setup can be found in the [Recommendations](best-practices-for-configuring-eop.md) article, where EOP settings are specifically called out.</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="3888f-141">オンプレミスの電子メール組織の EOP のセットアップ</span><span class="sxs-lookup"><span data-stu-id="3888f-141">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="3888f-p107">EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="3888f-p107">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="3888f-144">すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3888f-144">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="3888f-145">EOP データセンター</span><span class="sxs-lookup"><span data-stu-id="3888f-145">EOP datacenters</span></span>

<span data-ttu-id="3888f-146">EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。</span><span class="sxs-lookup"><span data-stu-id="3888f-146">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="3888f-147">たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-147">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="3888f-148">各データセンター内のサーバーは、ユーザーに代わってメッセージを受け入れ、組織とインターネットの間で一層の分離を提供し、サーバーの負荷を軽減します。</span><span class="sxs-lookup"><span data-stu-id="3888f-148">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="3888f-149">この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="3888f-149">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="3888f-p109">EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3888f-p109">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="3888f-153">ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-153">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="3888f-154">このAsia-Pacific (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置され、メッセージは現在、EOP フィルター処理のために APAC データセンターを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-154">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="3888f-155">南北アメリカでは、サービスは次の場所に配布されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-155">In the Americas, services are distributed in the following locations:</span></span>

  - <span data-ttu-id="3888f-156">南アメリカ: Exchange Online メールボックスは、ブラジルとチリのデータセンターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-156">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="3888f-157">すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-157">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="3888f-158">検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-158">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="3888f-159">カナダ: Exchange Online メールボックスは、カナダのデータセンターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-159">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="3888f-160">すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-160">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="3888f-161">検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-161">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="3888f-162">米国: Exchange Online メールボックスは、米国のデータセンターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-162">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="3888f-163">すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-163">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="3888f-164">検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-164">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="3888f-165">Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3888f-165">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="3888f-166">管理者向け EOP ヘルプ</span><span class="sxs-lookup"><span data-stu-id="3888f-166">EOP Help for admins</span></span>

<span data-ttu-id="3888f-167">EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3888f-167">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="3888f-168">[Office 365](protect-against-threats.md)管理者向け Microsoft Defender の EOP、第 1 日の構成 : Office 365 の Microsoft Defender の中核となる EOP 保護と検出ツールの構成。</span><span class="sxs-lookup"><span data-stu-id="3888f-168">[Configure EOP, Day 1, for Microsoft Defender for Office 365 admins](protect-against-threats.md): Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="3888f-169">[EOP 機能: EOP](eop-features.md)で使用できる機能の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="3888f-169">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="3888f-170">[EOP サービスのセットアップ](set-up-your-eop-service.md): EOP サービスをセットアップするための手順と、追加情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="3888f-170">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="3888f-171">[Google Postini、Barracuda Spam and Virus Firewall、または Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)から EOP に切り替える : 別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-171">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="3888f-172">[スタンドアロン EOP で受信者を管理](manage-recipients-in-eop.md)する : EOP でメール ユーザーとグループを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-172">[Manage recipients in standalone EOP](manage-recipients-in-eop.md): Describes how to manage mail users and groups in EOP.</span></span>

- <span data-ttu-id="3888f-173">[EOP](mail-flow-in-eop.md)のメール フロー: コネクタを使用してカスタム メール フロー シナリオを構成する方法、サービスに関連付けられているドメインを管理する方法、およびディレクトリ ベースのエッジ ブロック (DBEB) 機能を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-173">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="3888f-174">[EOP の構成に関するベスト プラクティス](best-practices-for-configuring-eop.md): サービスのセットアップと準備後の推奨構成設定と考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-174">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="3888f-175">[スタンドアロン EOP でのレポートの](auditing-reports-in-eop.md)監査 : 監査レポートを使用してサービスの構成変更を追跡する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-175">[Auditing reports in standalone EOP](auditing-reports-in-eop.md): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="3888f-176">[EOP でのスパム](anti-spam-and-anti-malware-protection.md)対策とマルウェア対策の保護: スパム フィルターとマルウェア フィルターについて説明し、組織のニーズに最も合わせてカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3888f-176">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="3888f-177">また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。</span><span class="sxs-lookup"><span data-stu-id="3888f-177">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="3888f-178">[Exchange Online Protection でのレポートとメッセージの追跡](reporting-and-message-trace-in-exchange-online-protection.md): 使用可能なレポートとトラブルシューティング ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-178">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="3888f-179">[スタンドアロン EOP](exchange-admin-center-in-exchange-online-protection-eop.md)の Exchange 管理センター : EOP サービスを管理するために Exchange 管理センター (EAC) 管理インターフェイスにアクセスして移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3888f-179">[Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="3888f-180">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、コマンド ラインから EOP サービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3888f-180">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="3888f-181">「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="3888f-181">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>