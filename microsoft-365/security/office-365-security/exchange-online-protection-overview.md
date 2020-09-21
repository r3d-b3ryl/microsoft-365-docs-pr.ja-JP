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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) によって、オンプレミスの電子メール組織がスタンドアロン環境およびハイブリッド環境で保護される方法について説明します。
ms.openlocfilehash: b546b60e242d7f4f7fd4c4550bb61b94052ff4d1
ms.sourcegitcommit: eb905c5b4d7e71fc930a207357295b0160c4f065
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2020
ms.locfileid: "48137020"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="c27a4-103">Exchange Online Protection の概要</span><span class="sxs-lookup"><span data-stu-id="c27a4-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="c27a4-104">Exchange Online Protection (EOP) は、組織をスパムやマルウェアから保護するために役立つクラウドベースのフィルタリングサービスです。</span><span class="sxs-lookup"><span data-stu-id="c27a4-104">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="c27a4-105">EOP は、Exchange Online メールボックスを使用するすべての Microsoft 365 組織に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c27a4-105">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="c27a4-106">ただし、EOP は、次のオンプレミスのシナリオでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-106">However, EOP is also available in the following on-premises scenarios:</span></span>

- <span data-ttu-id="c27a4-107">**スタンドアロンのシナリオで**は、EOP は、オンプレミスの Exchange 組織またはその他の社内 SMTP 電子メールソリューションに対して、クラウドベースの電子メール保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-107">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="c27a4-108">**ハイブリッド展開で**は、社内メールボックスとクラウドメールボックスが混在している場合に、電子メール環境を保護し、メールルーティングを制御するように EOP を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-108">**In a hybrid deployment**: EOP can be configured to protect your email environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

<span data-ttu-id="c27a4-109">このようなシナリオでは、EOP を使用してメール環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-109">In these scenarios, EOP can simplify the management of your email environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="c27a4-110">このトピックの残りの部分では、スタンドアロン環境とハイブリッド環境で EOP がどのように機能するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-110">The rest of this topic explains how EOP works in standalone and hybrid environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="c27a4-111">EOP の仕組み</span><span class="sxs-lookup"><span data-stu-id="c27a4-111">How EOP works</span></span>

<span data-ttu-id="c27a4-112">EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c27a4-112">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="インターネットまたは顧客からのフィードバックによって EOP に渡される電子メールの画像。また、接続、マルウェア対策、メールフロールールのフィルター処理、およびコンテンツフィルター、迷惑メールまたは検疫の verdict の前、またはエンドユーザーのメール配信のいずれかです。":::

- <span data-ttu-id="c27a4-114">受信メッセージが EOP に入った場合、まず、送信者の評価を確認するために接続フィルターを通過します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-114">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="c27a4-115">スパムの大部分は、この時点で停止し、EOP によって拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-115">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="c27a4-116">詳細については、「[接続フィルターを構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c27a4-116">For more information, see [Configure connection filtering](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy?view=o365-worldwide).</span></span>

- <span data-ttu-id="c27a4-117">その後、メッセージはマルウェアの兆候を調査します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-117">Then the message is inspected for signs of malware.</span></span> <span data-ttu-id="c27a4-118">メッセージまたは添付ファイルにマルウェアが検出された場合、メッセージは管理のみの検疫ストアにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-118">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="c27a4-119">[ここで](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide)は、マルウェア対策の構成について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-119">You can learn more about configuring anti-malware [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>

- <span data-ttu-id="c27a4-120">メッセージはポリシーフィルター処理によって続行され、テンプレートを使用して作成または適用するカスタムメールフロールール (トランスポートルールとも呼ばれる) に対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-120">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="c27a4-121">たとえば、特定の送信者からのメールが到着すると、管理者に通知を送信するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-121">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="c27a4-122">データ損失防止 (DLP) チェックも、この時点で発生します (Exchange Enterprise CAL with Services)。</span><span class="sxs-lookup"><span data-stu-id="c27a4-122">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="c27a4-123">次に、メッセージはコンテンツフィルター (スパム対策とも呼ばれます) を通過します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-123">Next, the message passes through content filtering (also known as Anti-spam).</span></span> <span data-ttu-id="c27a4-124">このフィルターがスパム *またはフィッシング* を検疫に送信することを決定するメッセージ、またはユーザーの迷惑メールフォルダーなどのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-124">A message that this filter determines to be spam *or phish* can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="c27a4-125">詳細については、「 [スパム対策ポリシーを構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide) 」および「 [フィッシング対策ポリシーを構成](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-phishing-policies-eop?view=o365-worldwide)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c27a4-125">For more information see [Configure anti-spam policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide) and [Configure anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-phishing-policies-eop?view=o365-worldwide).</span></span>

<span data-ttu-id="c27a4-126">これらの保護層をすべて正常に通過するメッセージはすべて、受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-126">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="c27a4-127">詳細については、「 [メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c27a4-127">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="c27a4-128">オンプレミスの電子メール組織の EOP プランと機能</span><span class="sxs-lookup"><span data-stu-id="c27a4-128">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="c27a4-129">利用可能な EOP サブスクリプションプランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c27a4-129">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="c27a4-130">**EOP スタンドアロン**: 社内の電子メール組織を保護するために EOP に登録します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-130">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="c27a4-131">**Exchange online の EOP 機能**: exchange online (スタンドアロンまたは Microsoft 365 の一部) を含むサブスクリプションは、EOP を使用して exchange online メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-131">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="c27a4-132">**Exchange ENTERPRISE cal With services**: 追加の EXCHANGE enterprise Cal をサービスライセンスと共に購入したオンプレミスの exchange 組織がある場合、EOP は含まれているサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="c27a4-132">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="c27a4-133">すべての EOP サブスクリプションプランでの要件、重要な制限、および機能の可用性の詳細については、「 [Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c27a4-133">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="c27a4-134">オンプレミスの電子メール組織の EOP のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c27a4-134">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="c27a4-p106">EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="c27a4-p106">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="c27a4-137">すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c27a4-137">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="c27a4-138">EOP データセンター</span><span class="sxs-lookup"><span data-stu-id="c27a4-138">EOP datacenters</span></span>

<span data-ttu-id="c27a4-139">EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-139">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="c27a4-140">たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-140">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="c27a4-141">各データセンターのサーバーは、ユーザーの代わりにメッセージを受け付け、組織とインターネットの間に分離された層を提供して、サーバーの負荷を軽減します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-141">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="c27a4-142">この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-142">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="c27a4-p108">EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-p108">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="c27a4-146">ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-146">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="c27a4-147">アジア太平洋 (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置されており、現在、メッセージは EOP フィルター処理のために APAC データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-147">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="c27a4-148">南北アメリカでは、サービスは次の場所に配布されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-148">In the Americas, services are distributed in the following locations:</span></span>

  - <span data-ttu-id="c27a4-149">南アメリカ: Exchange Online メールボックスは、ブラジルおよびチリのデータセンターにあります。</span><span class="sxs-lookup"><span data-stu-id="c27a4-149">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="c27a4-150">すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-150">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="c27a4-151">検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-151">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="c27a4-152">カナダ: Exchange Online メールボックスは、カナダのデータセンターに配置されています。</span><span class="sxs-lookup"><span data-stu-id="c27a4-152">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="c27a4-153">すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-153">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="c27a4-154">検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-154">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="c27a4-155">米国: Exchange Online メールボックスは、米国データセンターに配置されています。</span><span class="sxs-lookup"><span data-stu-id="c27a4-155">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="c27a4-156">すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-156">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="c27a4-157">検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-157">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="c27a4-158">Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-158">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="c27a4-159">管理者向けの EOP ヘルプ</span><span class="sxs-lookup"><span data-stu-id="c27a4-159">EOP Help for admins</span></span>

<span data-ttu-id="c27a4-160">EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-160">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="c27a4-161">[EOP, Day 1, For office 365 の ATP 管理者](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide): Office 365 Advanced Threat protection のコアで EOP 保護および検出ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-161">[Configure EOP, Day 1, for Office 365 ATP admins](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide): Configuring EOP protection and detection tools at the core of Office 365 Advanced Threat Protection.</span></span>

- <span data-ttu-id="c27a4-162">[EOP features](eop-features.md): EOP で使用できる機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-162">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="c27a4-163">[EOP サービス](set-up-your-eop-service.md)をセットアップする: EOP サービスをセットアップする手順、および追加情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-163">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="c27a4-164">[EOP に Google Postini、Barracuda Spam And Virus Firewall、または Cisco IronPort を切り替え](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)ます。別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-164">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="c27a4-165">[[スタンドアロンでの受信者の管理 EOP](manage-recipients-in-eop.md): EOP でメールユーザーとグループを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-165">[Manage recipients in standalone EOP](manage-recipients-in-eop.md): Describes how to manage mail users and groups in EOP.</span></span>

- <span data-ttu-id="c27a4-166">[EOP のメールフロー](mail-flow-in-eop.md): コネクタを使用してカスタムメールフローシナリオを構成する方法、サービスに関連付けられたドメインを管理する方法、およびディレクトリベースのエッジブロック (DBEB) 機能を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-166">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="c27a4-167">[EOP を構成するためのベストプラクティス](best-practices-for-configuring-eop.md): サービスをセットアップしてプロビジョニングした後の推奨される構成設定および考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-167">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="c27a4-168">[スタンドアロン EOP の監査レポート](auditing-reports-in-eop.md): 監査レポートを使用して、サービスに対する構成の変更を追跡する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-168">[Auditing reports in standalone EOP](auditing-reports-in-eop.md): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="c27a4-169">[EOP のスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md): スパムフィルター処理とマルウェアフィルター処理について説明し、組織のニーズに合わせてカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-169">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="c27a4-170">また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。</span><span class="sxs-lookup"><span data-stu-id="c27a4-170">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="c27a4-171">[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md): 使用可能なレポートとトラブルシューティングツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-171">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="c27a4-172">[スタンドアロン EOP の exchange 管理センター](exchange-admin-center-in-exchange-online-protection-eop.md): EOP サービスを管理するために、exchange 管理センター (EAC) 管理インターフェイスを使用してアクセスおよびナビゲートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c27a4-172">[Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="c27a4-173">[Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、EOP サービスをコマンドラインから管理できます。</span><span class="sxs-lookup"><span data-stu-id="c27a4-173">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="c27a4-174">「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="c27a4-174">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>
