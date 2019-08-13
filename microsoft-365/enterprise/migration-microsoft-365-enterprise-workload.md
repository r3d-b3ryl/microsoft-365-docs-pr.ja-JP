---
title: Microsoft 365 Enterprise への移行
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft Office、Office サーバー、Windows のバージョンを Microsoft 365 Enterprise に移行するプロセスの手順に従います。
ms.openlocfilehash: f82e65cdff674884466fe70a299250c92f356186
ms.sourcegitcommit: 86dba00cd786ac8ea761cdfcd85dfbd33e64d088
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2019
ms.locfileid: "36297883"
---
# <a name="migration-to-microsoft-365-enterprise"></a><span data-ttu-id="29f32-103">Microsoft 365 Enterprise への移行</span><span class="sxs-lookup"><span data-stu-id="29f32-103">Migration to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="29f32-p101">ほとんどの企業では、オペレーティング システム、クライアント ソフトウェア、サーバー ソフトウェアの複数のリリースを使った異種混合環境使用しています。Microsoft 365 Enterprise には、IT インフラストラクチャのこれらのキー コンポーネントの最も安全なバージョンと共に、クラウド テクノロジを活用するために設計されている生産性機能がそろっています。</span><span class="sxs-lookup"><span data-stu-id="29f32-p101">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software. Microsoft 365 Enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="29f32-106">製品の Microsoft 365 Enterprise の統合スイートのビジネス価値を最大化するには、次のソフトウェアのリリースを移行するための戦略を計画および導入してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-106">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="29f32-107">コンピューターにインストールされている Office クライアントから Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="29f32-107">The Office client installed on your computers to Office 365 ProPlus</span></span>
- <span data-ttu-id="29f32-108">サーバーにインストールされている Office サーバーから Office 365 の同等のサービス</span><span class="sxs-lookup"><span data-stu-id="29f32-108">Office servers installed on your servers to their equivalent services in Office 365</span></span>
- <span data-ttu-id="29f32-109">デバイス上の Windows 7 および Windows 8.1 から Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="29f32-109">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

>[!Note]
><span data-ttu-id="29f32-110">Windows 7 は、2020 年 1 月 14 日にサポート終了になります。</span><span class="sxs-lookup"><span data-stu-id="29f32-110">Windows 7 reaches end of support on January 14, 2020.</span></span> <span data-ttu-id="29f32-111">詳細については、[こちら](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="29f32-111">For cost information, click [here](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="29f32-112">時経つうちにこれらすべての移行が完了すれば、組織内のチームワークと創造性を引き出す安全で統合された[最新の職場](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)環境に組織を近づけることができます。これはすべて Microsoft 365 Enterprise によって成し遂げることができます。</span><span class="sxs-lookup"><span data-stu-id="29f32-112">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="29f32-113">特定の Office 365 ワークロード向けのユーザーとデータの移行に関する情報:</span><span class="sxs-lookup"><span data-stu-id="29f32-113">For information about migrating users and data for specific Office 365 workloads:</span></span>

- <span data-ttu-id="29f32-114">ユーザーのメールボックスを Exchange Server から Exchange Online へ: [Exchange Online ワークロード](exchangeonline-workload.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-114">User mailboxes from Exchange Server to Exchange Online, see the [Exchange Online workload](exchangeonline-workload.md).</span></span>
- <span data-ttu-id="29f32-115">SharePoint データを SharePoint Server から SharePoint Online へ: [SharePoint Online ワークロード](sharepoint-online-onedrive-workload.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-115">SharePoint data from SharePoint Server to SharePoint Online, see the [SharePoint Online workload](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="29f32-116">Skype for Business Online から Microsoft Teams へ: [Microsoft Teams ワークロード](teams-workload.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-116">Skype for Business Online to Microsoft Teams, see the [Microsoft Teams workload](teams-workload.md).</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="29f32-117">Microsoft Office クライアント製品の移行</span><span class="sxs-lookup"><span data-stu-id="29f32-117">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="29f32-p103">大小問わず多くの組織では、Word、Excel、PowerPoint など、Office クライアント製品の古いバージョンの組み合わせを使っている可能性があります。これらの古いバージョンには以下の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="29f32-p103">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="29f32-120">最新のセキュリティ更新プログラムおよびサポート修正プログラムで[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)できますが、プロセスを手動で行う必要があったり、組織全体にまで行き渡らなかったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29f32-120">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="29f32-121">Microsoft クラウド テクノロジを活用しビジネスをデジタルに変換するうえで、最適ではありません。</span><span class="sxs-lookup"><span data-stu-id="29f32-121">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
 
<span data-ttu-id="29f32-p104">Microsoft 365 Enterprise には、Microsoft 365 Enterprise ライセンスで利用でき、Microsoft クラウドからインストールおよび更新される Office クライアント製品のバージョンである Office 365 ProPlus が含まれています。詳細については、「[エンタープライズでの Office 365 ProPlus について](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p104">Microsoft 365 Enterprise includes Office 365 ProPlus, a version of the Office client products that is available with a Microsoft 365 Enterprise license and is installed and updated from the Microsoft cloud. See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="29f32-124">Office 2007</span><span class="sxs-lookup"><span data-stu-id="29f32-124">Office 2007</span></span>

<span data-ttu-id="29f32-p105">Office 2007 リリースの Office のバージョンは、サポート期間が過ぎています。詳細については、「[Office 2007 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p105">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="29f32-127">Office 2007 を実行しているコンピューターを Office 2010、Office 2013、または Office 2016 にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-127">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="29f32-128">ユーザー用に Microsoft 365 ライセンスを取得して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="29f32-128">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="29f32-129">ユーザーのコンピューターから Office 2007 をアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="29f32-129">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="29f32-p106">Office 365 ProPlus を個別にまたは IT ロールアウトと合わせてインストールする。詳細については、「[フェーズ 4: Office 365 ProPlus](office365proplus-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p106">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="29f32-132">Office 365 ProPlus は更新プログラムを自動的にインストールし、Office 365 のクラウドベースのサービスを活用して強化されたセキュリティと生産性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="29f32-132">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="29f32-133">Office 2010</span><span class="sxs-lookup"><span data-stu-id="29f32-133">Office 2010</span></span>

<span data-ttu-id="29f32-p107">Office 2010 リリースの Office のバージョンは、サポートが 2020 年 10 月 13 日に終了します。詳細については、「[Office 2010 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p107">For versions of Office in the Office 2010 release, the end of support is October 13, 2020. For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="29f32-136">Office 2010 を実行しているコンピューターを Office 2013 または Office 2016 (両方とも手動で更新する必要があります) にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-136">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span> 

1. <span data-ttu-id="29f32-137">ユーザー用に Microsoft 365 ライセンスを取得して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="29f32-137">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="29f32-138">ユーザーのコンピューターから Office 2010 をアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="29f32-138">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="29f32-p108">Office 365 ProPlus を個別にまたは IT ロールアウトと合わせてインストールする。詳細については、「[フェーズ 4: Office 365 ProPlus](office365proplus-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p108">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="29f32-141">Office 365 ProPlus は更新プログラムを自動的にインストールし、Office 365 のクラウドベースのサービスを活用して強化されたセキュリティと生産性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="29f32-141">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="29f32-142">Office 2013 および Office 2016</span><span class="sxs-lookup"><span data-stu-id="29f32-142">Office 2013 and Office 2016</span></span>

<span data-ttu-id="29f32-p109">Office の Office 2013 および Office 2016 バージョンのサポート終了ロードマップはまだ決まっていません。ただし、Office 2010 のように、[更新プログラムをインストールする](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)必要があるため、組織の規模によっては全体に行き渡らない可能性があります。Office 2013 または Office 2016 の最新の更新プログラムでコンピューターを更新し続けたり、Office 2013 から Office 2016 にコンピューターを更新したりするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p109">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined. However, like Office 2010, you must still [install updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization. Rather than keep updating your computers with the latest updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="29f32-146">ユーザー用に Microsoft 365 ライセンスを取得して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="29f32-146">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="29f32-147">ユーザーのコンピューターから Office 2013 または Office 2016 をアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="29f32-147">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="29f32-p110">Office 365 ProPlus を個別にまたは IT ロールアウトと合わせてインストールする。詳細については、「[フェーズ 4: Office 365 ProPlus](office365proplus-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p110">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="29f32-150">Office 365 ProPlus は更新プログラムを自動的にインストールし、Office 365 のクラウドベースのサービスを活用して強化されたセキュリティと生産性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="29f32-150">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="29f32-151">Microsoft Office サーバー製品の移行</span><span class="sxs-lookup"><span data-stu-id="29f32-151">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="29f32-p111">大小問わず多くの組織では、Exchange Server や SharePoint Server などの Office サーバー製品の古いバージョンの組み合わせを使っている可能性があります。これらの古いバージョンには以下の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="29f32-p111">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="29f32-p112">最新のセキュリティ更新プログラムとサポート修正プログラムで更新する必要があります。場合によっては、これらの更新プログラムは毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="29f32-p112">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="29f32-156">Microsoft クラウド テクノロジを活用しビジネスをデジタルに変換するうえで、最適ではありません。</span><span class="sxs-lookup"><span data-stu-id="29f32-156">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="29f32-157">Microsoft Teams などの新しい生産性向上アプリケーションは含まれません。</span><span class="sxs-lookup"><span data-stu-id="29f32-157">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="29f32-158">Exchange Advanced Threat Protection などの最新のセキュリティ機能は含まれません。</span><span class="sxs-lookup"><span data-stu-id="29f32-158">Do not include the latest security features, such as Exchange Advanced Threat Protection.</span></span>

<span data-ttu-id="29f32-p113">Microsoft 365 Enterprise には、オンプレミス バージョン Office サーバー ソフトウェアと同じいくつかのツール (Web ブラウザーや Outlook クライアントなど) を使用する、クラウドベース バージョンの Office サーバー サービスを含む Office 365 が含まれます。これらのサービスは IT 部門の手を煩わさずに継続的に更新されるため、オンプレミス サーバーを維持および更新するためにかかる時間を節約できます。これらのサービスには、Office サーバー ソフトウェアにはない拡張機能もあります。</span><span class="sxs-lookup"><span data-stu-id="29f32-p113">Microsoft 365 Enterprise includes Office 365, which includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client. These services are continually updated without involving IT, saving you the time it takes to maintain and update on-premises servers. These services also have enhancements not present in Office server software.</span></span> 

### <a name="office-server-2007"></a><span data-ttu-id="29f32-162">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="29f32-162">Office Server 2007</span></span>

<span data-ttu-id="29f32-p114">Office 2007 リリースのサーバー製品については、サポート期間が過ぎています。詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p114">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="29f32-165">Exchange 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="29f32-165">Exchange 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [<span data-ttu-id="29f32-166">SharePoint Server 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="29f32-166">SharePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [<span data-ttu-id="29f32-167">Project Server 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="29f32-167">Project Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [<span data-ttu-id="29f32-168">Office Communications Server のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="29f32-168">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="29f32-169">PerformancePoint Server 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="29f32-169">PerformancePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

<span data-ttu-id="29f32-170">Office 2007 リリースのサーバー製品を Office 2010、Office 2013、または Office 2016 リリースのサーバー製品にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-170">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="29f32-p115">Office 2007 サーバー上のデータを Office 365 に移行する。これをサポートするために、Microsoft パートナーを採用してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p115">Migrating the data on your Office 2007 servers to Office 365. To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="29f32-173">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="29f32-173">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="29f32-174">Office 2007 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="29f32-174">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="29f32-175">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="29f32-175">Office Server 2010</span></span>

<span data-ttu-id="29f32-176">Office 2010 リリースのサーバー製品については、次のものに関してサポートの終了日が決まっています。</span><span class="sxs-lookup"><span data-stu-id="29f32-176">For server products in the Office 2010 release, the end of support has been determined for the following:</span></span>

- [<span data-ttu-id="29f32-177">Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="29f32-177">Exchange Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support)
- [<span data-ttu-id="29f32-178">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="29f32-178">SharePoint Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010)

<span data-ttu-id="29f32-179">Office 2010 リリースのこれらのサーバー製品を Office 2013 または Office 2016 リリースのサーバー製品にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-179">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="29f32-p116">Office 2010 サーバー上のデータを Office 365 に移行する。これをサポートするために、「[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365)」を参照するか、Microsoft パートナーを採用してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p116">Migrating the data on your Office 2010 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="29f32-182">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="29f32-182">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="29f32-183">Office 2010 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="29f32-183">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="29f32-184">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="29f32-184">Office Server 2013</span></span>

<span data-ttu-id="29f32-p117">Office 2013 リリースのサーバー製品については、サポートの終了日は決まっていません。Office 2013 リリースのサーバー製品を Office 2016 リリースにアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p117">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="29f32-p118">Office 2013 サーバー上のデータを Office 365 に移行する。これをサポートするために、「[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365)」を参照するか、Microsoft パートナーを採用してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p118">Migrating the data on your Office 2013 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="29f32-189">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="29f32-189">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="29f32-190">Office 2013 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="29f32-190">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="29f32-191">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="29f32-191">Office Server 2016</span></span>

<span data-ttu-id="29f32-p119">Office 2016 リリースのサーバー製品については、サポートの終了日は決まっていません。ビジネスをデジタルに変革するクラウドベースのサービスおよび拡張機能を活用するには、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p119">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="29f32-p120">Office 2016 サーバー上のデータを Office 365 に移行する。これをサポートするために、「[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365)」を参照するか、Microsoft パートナーを採用してください。</span><span class="sxs-lookup"><span data-stu-id="29f32-p120">Migrating the data on your Office 2016 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="29f32-196">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="29f32-196">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="29f32-197">Office 2016 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="29f32-197">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows"></a><span data-ttu-id="29f32-198">Microsoft Windows の移行</span><span class="sxs-lookup"><span data-stu-id="29f32-198">Migration for Microsoft Windows</span></span>

<span data-ttu-id="29f32-199">Windows 7 または Windows 8.1 を実行しているデバイスを移行するには、[一括アップグレード](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="29f32-199">To migrate your devices running Windows 7 or Windows 8.1, you can perform an [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade).</span></span> 

<span data-ttu-id="29f32-p121">その他の方法については、「[Windows 10 展開シナリオ](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)」を参照してください。[Windows 10 の展開を計画](https://aka.ms/planforwin10deployment)することもできます。</span><span class="sxs-lookup"><span data-stu-id="29f32-p121">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="29f32-202">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="29f32-202">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="29f32-203">Microsoft の IT 担当者がどのように会社のデータを Microsoft 365 Enterprise に移行しているかについては、以下のリソースで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="29f32-203">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise with these resources:</span></span> 

- [<span data-ttu-id="29f32-204">Microsoft Office 365 ProPlus の展開と更新</span><span class="sxs-lookup"><span data-stu-id="29f32-204">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="29f32-205">Microsoft では 150,000 のメールボックスを Exchange Online に移行</span><span class="sxs-lookup"><span data-stu-id="29f32-205">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="29f32-206">SharePoint からクラウドへ: Microsoft が実施した移行方法</span><span class="sxs-lookup"><span data-stu-id="29f32-206">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="29f32-207">Microsoft における、Windows 10 のインプレース アップグレードとしての展開方法</span><span class="sxs-lookup"><span data-stu-id="29f32-207">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="29f32-208">[Windows 10 の展開: Microsoft の IT 担当者からのヒント](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="29f32-208">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="29f32-209">組織全体の移行</span><span class="sxs-lookup"><span data-stu-id="29f32-209">Transition your entire organization</span></span>

<span data-ttu-id="29f32-210">組織全体を Microsoft 365 Enterprise に移行する方法をより良く理解するためには、[移行のポスター](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transitionorgtom365.pdf)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="29f32-210">To get a better picture of how to move your entire organization to Microsoft 365 Enterprise, download the [transition poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transitionorgtom365.pdf).</span></span>

![](./media/deploy-microsoft-365-enterprise/TransitionOrgToM365.png)

<span data-ttu-id="29f32-211">この見開きポスター (2 ページ) で簡単に既存のインフラストラクチャのインベントリを確認して、Microsoft 365 Enterprise で対応する製品またはサービスに移行するためのガイダンスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="29f32-211">This two-page poster is a quick way to inventory your existing infrastructure and get to the guidance for moving to the corresponding product or service in Microsoft 365 Enterprise.</span></span> <span data-ttu-id="29f32-212">この記事に記載されている製品、その他のインフラストラクチャ、それから、デバイス管理、ID、情報および脅威保護などのセキュリティ要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="29f32-212">It includes the products in this article and other infrastructure and security elements such as device management, identity, and information and threat protection.</span></span>

<span data-ttu-id="29f32-213">このポスターは、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷できます。</span><span class="sxs-lookup"><span data-stu-id="29f32-213">You can print this poster in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="result"></a><span data-ttu-id="29f32-214">結果</span><span class="sxs-lookup"><span data-stu-id="29f32-214">Result</span></span>

<span data-ttu-id="29f32-215">お客様の組織では Microsoft Office、Office サーバー、Windows の古いバージョンが Microsoft 365 Enterprise に移行されます。</span><span class="sxs-lookup"><span data-stu-id="29f32-215">Your organization has migrated older versions of Microsoft Office, Office servers, and Windows to Microsoft 365 Enterprise.</span></span>
