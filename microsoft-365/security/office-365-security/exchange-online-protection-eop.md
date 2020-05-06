---
title: Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: EOP サービスのセットアップ方法を含め、Microsoft Exchange Online Protection (EOP) でホストされている電子メールフィルターサービスについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee39e051d3be0e3b27013929bdc3d3a948457c9b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036538"
---
# <a name="exchange-online-protection"></a><span data-ttu-id="1c91f-103">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1c91f-103">Exchange Online Protection</span></span>

<span data-ttu-id="1c91f-p101">Microsoft Exchange Online Protection (EOP) でホストされる電子メール フィルタリング サービスへようこそ。ここでは、EOP で作業を開始する前に注意すべき点をいくつか取り上げ、以下のコンテンツを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-p101">Welcome to the Microsoft Exchange Online Protection (EOP) hosted email filtering service. Here are a few things you should be aware of before you start working with EOP and using this content:</span></span>

- <span data-ttu-id="1c91f-106">EOP の詳細については、「 [Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c91f-106">To learn more about EOP, check out the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="1c91f-107">その他の有益なリソースとして、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」、「[EOP の一般的な FAQ](eop-general-faq.md)」、および「[EOP の機能](eop-features.md)」、および「[Exchange Online Protection ホームページ](https://products.office.com/exchange/exchange-email-security-spam-protection)」があります。</span><span class="sxs-lookup"><span data-stu-id="1c91f-107">Other useful resources are [Exchange Online Protection overview](exchange-online-protection-overview.md), [EOP general FAQ](eop-general-faq.md), and [EOP features](eop-features.md), as well as the [Exchange Online Protection home page](https://products.office.com/exchange/exchange-email-security-spam-protection).</span></span>

- <span data-ttu-id="1c91f-108">EOP を初めて使うお客様は、まず「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c91f-108">To get started with EOP, new customers should head for [Set up your EOP service](set-up-your-eop-service.md).</span></span> <span data-ttu-id="1c91f-109">このトピックには、EOP を使い始める際に役立つ手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="1c91f-109">This topic provides steps that'll help you get EOP up and running.</span></span>

- <span data-ttu-id="1c91f-110">さらに支援が必要な場合や、アイデアを共有したい場合は、「[EOP のフォーラム](https://go.microsoft.com/fwlink/?LinkId=285351)」からご確認ください。</span><span class="sxs-lookup"><span data-stu-id="1c91f-110">If you need more help or want to share ideas, the [EOP forum](https://go.microsoft.com/fwlink/?LinkId=285351) is a great place to start.</span></span>

## <a name="eop-help-for-administrators"></a><span data-ttu-id="1c91f-111">管理者向けの EOP ヘルプ</span><span class="sxs-lookup"><span data-stu-id="1c91f-111">EOP Help for administrators</span></span>

<span data-ttu-id="1c91f-112">EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1c91f-112">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="1c91f-113">[Exchange Online Protection の概要](exchange-online-protection-overview.md): EOP のしくみについて説明し、追加情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-113">[Exchange Online Protection overview](exchange-online-protection-overview.md): Introduces how EOP works and provides links to additional information.</span></span>

- <span data-ttu-id="1c91f-114">[EOP features](eop-features.md): EOP で使用できる機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-114">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="1c91f-115">[EOP サービス](set-up-your-eop-service.md)をセットアップする: EOP サービスをセットアップする手順、および追加情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-115">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="1c91f-116">[EOP に Google Postini、Barracuda Spam And Virus Firewall、または Cisco IronPort を切り替え](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)ます。別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-116">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="1c91f-117">[EOP の受信者と管理役割グループを管理](manage-recipients-and-admin-role-groups-in-eop.md)する受信者を管理する方法と、ユーザーを管理役割グループに割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-117">[Manage recipients and admin role groups in EOP](manage-recipients-and-admin-role-groups-in-eop.md): Describes how to manage recipients and how to assign users to admin role groups.</span></span>

- <span data-ttu-id="1c91f-118">[EOP のメールフロー](mail-flow-in-eop.md): コネクタを使用してカスタムメールフローシナリオを構成する方法、サービスに関連付けられたドメインを管理する方法、およびディレクトリベースのエッジブロック (DBEB) 機能を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-118">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="1c91f-119">[EOP を構成するためのベストプラクティス](best-practices-for-configuring-eop.md): サービスをセットアップしてプロビジョニングした後の推奨される構成設定および考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-119">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="1c91f-120">[EOP のメッセージングポリシーとコンプライアンス](messaging-policy-and-compliance-in-eop.md): Exchange メールフロールール (トランスポートルールとも呼ばれます) を使用して特定の会社の規制やポリシーを適用する方法、および監査レポートを使用してサービスへの構成の変更を追跡する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-120">[Messaging policy and compliance in EOP](messaging-policy-and-compliance-in-eop.md): Describes how to use Exchange mail flow rules (also known as transport rules) to enforce specific company regulations and policies, and how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="1c91f-121">[Office 365 でのスパム対策およびマルウェア対策の保護](anti-spam-and-anti-malware-protection.md): スパムフィルター処理とマルウェアフィルター処理について説明し、組織のニーズに合わせてカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-121">[Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="1c91f-122">また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。</span><span class="sxs-lookup"><span data-stu-id="1c91f-122">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="1c91f-123">[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md): 使用可能なレポートとトラブルシューティングツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-123">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="1c91f-124">「Exchange [Online Protection の exchange 管理センター」](exchange-admin-center-in-exchange-online-protection-eop.md): EOP サービスを管理するために、exchange 管理センター (EAC) 管理インターフェイスを介してアクセスおよびナビゲートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c91f-124">[Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="1c91f-125">[Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、EOP サービスをコマンドラインから管理できます。</span><span class="sxs-lookup"><span data-stu-id="1c91f-125">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="1c91f-126">「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="1c91f-126">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>

## <a name="eop-help-for-end-users"></a><span data-ttu-id="1c91f-127">エンド ユーザー向けの EOP ヘルプ</span><span class="sxs-lookup"><span data-stu-id="1c91f-127">EOP Help for end users</span></span>

<span data-ttu-id="1c91f-128">EOP エンド ユーザーによるスパム管理を支援するためのヘルプ コンテンツは、次のトピックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1c91f-128">The Help content for assisting EOP end users to manage spam consists of the following topics:</span></span>

- [<span data-ttu-id="1c91f-129">メッセージとファイルを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="1c91f-129">Report messages and files to Microsoft</span></span>](report-junk-email-messages-to-microsoft.md)

- <span data-ttu-id="1c91f-130">エンドユーザーは、Outlook または web 上の Outlook で、自分の信頼できる差出人のリストまたは受信拒否リストに送信者を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1c91f-130">End users can add senders to their own Safe Senders list or Block Senders list in Outlook or Outlook on the web.</span></span> <span data-ttu-id="1c91f-131">管理者は、ユーザーメールボックス内のこれらのリストを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c91f-131">Admins can also modify these lists in user mailboxes.</span></span> <span data-ttu-id="1c91f-132">詳細については、「 [Outlook での迷惑メール設定につい](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c91f-132">For more information, see [About junk email settings in Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook).</span></span>

- <span data-ttu-id="1c91f-133">「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="1c91f-133">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>
