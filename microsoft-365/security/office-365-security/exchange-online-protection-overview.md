---
title: Exchange Online Protection (EOP) の概要
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
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) によって、オンプレミスの電子メール組織がスタンドアロン環境およびハイブリッド環境で保護される方法について説明します。
ms.openlocfilehash: 37b38df9e94bee93202be02c01a220afa9470b8a
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204805"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="b69af-103">Exchange Online Protection の概要</span><span class="sxs-lookup"><span data-stu-id="b69af-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="b69af-104">Exchange Online Protection (EOP) は、組織をスパムやマルウェアから保護するために役立つクラウドベースのフィルタリングサービスです。</span><span class="sxs-lookup"><span data-stu-id="b69af-104">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="b69af-105">EOP は、Exchange Online メールボックスを使用するすべての Microsoft 365 組織に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b69af-105">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span>

<span data-ttu-id="b69af-106">ただし、EOP は、次のオンプレミスのシナリオでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b69af-106">But, EOP is also available in the following on-premises scenarios:</span></span>

- <span data-ttu-id="b69af-107">**スタンドアロンのシナリオで**は、EOP は、オンプレミスの Exchange 組織またはその他の社内 SMTP 電子メールソリューションに対して、クラウドベースの電子メール保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="b69af-107">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="b69af-108">**ハイブリッド展開で**は、社内メールボックスとクラウドメールボックスが混在している場合に、電子メール環境を保護し、メールルーティングを制御するように EOP を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b69af-108">**In a hybrid deployment**: EOP can be configured to protect your email environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

<span data-ttu-id="b69af-109">このようなシナリオでは、EOP を使用してメール環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="b69af-109">In these scenarios, EOP can simplify the management of your email environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="b69af-110">このトピックの残りの部分では、スタンドアロン環境とハイブリッド環境で EOP がどのように機能するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-110">The rest of this topic explains how EOP works in standalone and hybrid environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="b69af-111">EOP の仕組み</span><span class="sxs-lookup"><span data-stu-id="b69af-111">How EOP works</span></span>

<span data-ttu-id="b69af-112">EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b69af-112">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

![電子メールプロセスの図](../../media/emailprocessingineop1.png)

- <span data-ttu-id="b69af-114">受信メッセージは、最初は、送信者の評価をチェックし、マルウェアのメッセージを検査することによって、接続フィルターによって渡されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-114">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware.</span></span> <span data-ttu-id="b69af-115">スパムの大部分は、この時点で停止し、EOP によって削除されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-115">The majority of spam is stopped at this point and deleted by EOP.</span></span> <span data-ttu-id="b69af-116">詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69af-116">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="b69af-117">メッセージはポリシーのフィルター処理によって続行されます。これにより、テンプレートから作成または適用するカスタムメールフロールール (トランスポートルールとも呼ばれる) に対してメッセージが評価されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-117">Messages continue through policy filtering, where messages are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="b69af-118">たとえば、特定の送信者からのメールが到着すると、管理者に通知を送信するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b69af-118">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="b69af-119">データ損失防止 (DLP) チェックも、この時点で発生します (Exchange Enterprise CAL with Services)。</span><span class="sxs-lookup"><span data-stu-id="b69af-119">Data loss prevention (DLP) checks also occur at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="b69af-120">次に、メッセージはスパム対策フィルター処理 (コンテンツフィルターとも呼ばれます) を通過します。</span><span class="sxs-lookup"><span data-stu-id="b69af-120">Next, messages pass through anti-spam filtering (also known as content filtering).</span></span> <span data-ttu-id="b69af-121">スパムと判断されたメッセージは、他のオプションの中から、ユーザーの迷惑メールフォルダーまたは検疫に送信できます。</span><span class="sxs-lookup"><span data-stu-id="b69af-121">A message that's determined to be spam can be sent to a user's Junk Email folder or to the quarantine, among other options.</span></span> <span data-ttu-id="b69af-122">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69af-122">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="b69af-123">このような保護層をすべて正常に通過すると、メッセージは受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-123">After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>

<span data-ttu-id="b69af-124">詳細については、「[メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69af-124">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="b69af-125">EOP データセンター</span><span class="sxs-lookup"><span data-stu-id="b69af-125">EOP datacenters</span></span>

<span data-ttu-id="b69af-126">EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。</span><span class="sxs-lookup"><span data-stu-id="b69af-126">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="b69af-127">たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b69af-127">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="b69af-128">各データセンターのサーバーは、ユーザーの代わりにメッセージを受け付け、組織とインターネットの間に分離された層を提供して、サーバーの負荷を軽減します。</span><span class="sxs-lookup"><span data-stu-id="b69af-128">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="b69af-129">この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="b69af-129">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="b69af-p106">EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b69af-p106">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="b69af-133">ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b69af-133">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="b69af-134">アジア太平洋 (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置されており、現在、メッセージは EOP フィルター処理のために APAC データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b69af-134">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="b69af-135">南北アメリカでは、サービスは次の場所に配布されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-135">In the Americas, services are distributed in the following locations:</span></span>

  - <span data-ttu-id="b69af-136">南アメリカ: Exchange Online メールボックスは、ブラジルおよびチリのデータセンターにあります。</span><span class="sxs-lookup"><span data-stu-id="b69af-136">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="b69af-137">すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b69af-137">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="b69af-138">検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-138">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="b69af-139">カナダ: Exchange Online メールボックスは、カナダのデータセンターに配置されています。</span><span class="sxs-lookup"><span data-stu-id="b69af-139">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="b69af-140">すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b69af-140">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="b69af-141">検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-141">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="b69af-142">米国: Exchange Online メールボックスは、米国データセンターに配置されています。</span><span class="sxs-lookup"><span data-stu-id="b69af-142">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="b69af-143">すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b69af-143">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="b69af-144">検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-144">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="b69af-145">Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b69af-145">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="b69af-146">オンプレミスの電子メール組織の EOP プランと機能</span><span class="sxs-lookup"><span data-stu-id="b69af-146">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="b69af-147">利用可能な EOP サブスクリプションプランは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b69af-147">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="b69af-148">**EOP スタンドアロン**: 社内の電子メール組織を保護するために EOP に登録します。</span><span class="sxs-lookup"><span data-stu-id="b69af-148">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="b69af-149">**Exchange online の EOP 機能**: exchange online (スタンドアロンまたは Microsoft 365 の一部) を含むサブスクリプションは、EOP を使用して exchange online メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="b69af-149">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="b69af-150">**Exchange ENTERPRISE cal With services**: 追加の EXCHANGE enterprise Cal をサービスライセンスと共に購入したオンプレミスの exchange 組織がある場合、EOP は含まれているサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="b69af-150">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="b69af-151">すべての EOP サブスクリプションプランでの要件、重要な制限、および機能の可用性の詳細については、「 [Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69af-151">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="b69af-152">オンプレミスの電子メール組織の EOP のセットアップ</span><span class="sxs-lookup"><span data-stu-id="b69af-152">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="b69af-p110">EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="b69af-p110">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="b69af-155">すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b69af-155">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="b69af-156">管理者向けの EOP ヘルプ</span><span class="sxs-lookup"><span data-stu-id="b69af-156">EOP Help for admins</span></span>

<span data-ttu-id="b69af-157">EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b69af-157">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="b69af-158">[Exchange Online Protection の概要](exchange-online-protection-overview.md): EOP のしくみについて説明し、追加情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="b69af-158">[Exchange Online Protection overview](exchange-online-protection-overview.md): Introduces how EOP works and provides links to additional information.</span></span>

- <span data-ttu-id="b69af-159">[EOP features](eop-features.md): EOP で使用できる機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b69af-159">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="b69af-160">[EOP サービス](set-up-your-eop-service.md)をセットアップする: EOP サービスをセットアップする手順、および追加情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="b69af-160">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="b69af-161">[EOP に Google Postini、Barracuda Spam And Virus Firewall、または Cisco IronPort を切り替え](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)ます。別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-161">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="b69af-162">[[スタンドアロンでの受信者の管理 EOP](manage-recipients-in-eop.md): EOP でメールユーザーとグループを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-162">[Manage recipients in standalone EOP](manage-recipients-in-eop.md): Describes how to manage mail users and groups in EOP.</span></span>

- <span data-ttu-id="b69af-163">[EOP のメールフロー](mail-flow-in-eop.md): コネクタを使用してカスタムメールフローシナリオを構成する方法、サービスに関連付けられたドメインを管理する方法、およびディレクトリベースのエッジブロック (DBEB) 機能を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-163">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="b69af-164">[EOP を構成するためのベストプラクティス](best-practices-for-configuring-eop.md): サービスをセットアップしてプロビジョニングした後の推奨される構成設定および考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-164">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="b69af-165">[スタンドアロン EOP の監査レポート](auditing-reports-in-eop.md): 監査レポートを使用して、サービスに対する構成の変更を追跡する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-165">[Auditing reports in standalone EOP](auditing-reports-in-eop.md): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="b69af-166">[EOP のスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md): スパムフィルター処理とマルウェアフィルター処理について説明し、組織のニーズに合わせてカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b69af-166">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="b69af-167">また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。</span><span class="sxs-lookup"><span data-stu-id="b69af-167">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="b69af-168">[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md): 使用可能なレポートとトラブルシューティングツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-168">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="b69af-169">[スタンドアロン EOP の exchange 管理センター](exchange-admin-center-in-exchange-online-protection-eop.md): EOP サービスを管理するために、exchange 管理センター (EAC) 管理インターフェイスを使用してアクセスおよびナビゲートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b69af-169">[Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="b69af-170">[Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、EOP サービスをコマンドラインから管理できます。</span><span class="sxs-lookup"><span data-stu-id="b69af-170">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="b69af-171">「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="b69af-171">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>
