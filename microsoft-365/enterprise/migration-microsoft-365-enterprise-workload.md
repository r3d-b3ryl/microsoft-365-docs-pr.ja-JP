---
title: Microsoft 365 Enterprise への移行
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/29/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft Office、Office サーバー、Windows のバージョンを Microsoft 365 Enterprise に移行するプロセスの手順に従います。
ms.openlocfilehash: 05654e4714d2328f2f5853ed49df83a907e580f6
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528062"
---
# <a name="migration-to-microsoft-365-enterprise"></a><span data-ttu-id="dcaba-103">Microsoft 365 Enterprise への移行</span><span class="sxs-lookup"><span data-stu-id="dcaba-103">Migration to Microsoft 365 Enterprise</span></span>


>[!Note]
><span data-ttu-id="dcaba-104">*コンテンツ* を Microsoft 365 に移行するのに役立つツールをお探しですか?</span><span class="sxs-lookup"><span data-stu-id="dcaba-104">Looking for tools to help you migrate your *content* to Microsoft 365?</span></span>  <span data-ttu-id="dcaba-105">ネットワーク ファイル共有、SharePoint Server、その他のクラウド プロバイダーからコンテンツを移行する場合でも、ユーザーのニーズを満たす無料の移行ツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dcaba-105">Whether migrating content from network file shares, SharePoint Server, or other cloud providers, we have a free migration tool to meet your needs.</span></span> <span data-ttu-id="dcaba-106">無料の移行ツールの詳細については、以下をご覧ください:</span><span class="sxs-lookup"><span data-stu-id="dcaba-106">Learn more about our FREE migration tools at:</span></span>
>
>[<span data-ttu-id="dcaba-107">Microsoft 365 にコンテンツを移行する</span><span class="sxs-lookup"><span data-stu-id="dcaba-107">Migrate your content to Microsoft 365</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

<span data-ttu-id="dcaba-p102">ほとんどの企業では、オペレーティング システム、クライアント ソフトウェア、サーバー ソフトウェアの複数のリリースを使った異種混合環境使用しています。Microsoft 365 Enterprise には、IT インフラストラクチャのこれらのキー コンポーネントの最も安全なバージョンと共に、クラウド テクノロジを活用するために設計されている生産性機能がそろっています。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p102">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software. Microsoft 365 Enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="dcaba-110">製品の Microsoft 365 Enterprise の統合スイートのビジネス価値を最大化するには、次のソフトウェアのリリースを移行するための戦略を計画および導入してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-110">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="dcaba-111">お使いのコンピューターにインストールされている Office クライアントから、Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="dcaba-111">The Office client installed on your computers to Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="dcaba-112">サーバーにインストールされている Office サーバーから Office 365 の同等のサービス</span><span class="sxs-lookup"><span data-stu-id="dcaba-112">Office servers installed on your servers to their equivalent services in Office 365</span></span>
- <span data-ttu-id="dcaba-113">デバイス上の Windows 7 および Windows 8.1 から Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dcaba-113">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

>[!Note]
><span data-ttu-id="dcaba-114">Windows 7 は、**2020 年 1 月 14 日**にサポートが終了しました。</span><span class="sxs-lookup"><span data-stu-id="dcaba-114">Windows 7 reached end of support on **January 14, 2020**.</span></span> <span data-ttu-id="dcaba-115">詳細については、[こちら](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-115">For more information, click [here](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="dcaba-116">時経つうちにこれらすべての移行が完了すれば、組織内のチームワークと創造性を引き出す安全で統合された[最新の職場](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)環境に組織を近づけることができます。これはすべて Microsoft 365 Enterprise によって成し遂げることができます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-116">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="dcaba-117">特定の Office 365 ワークロード向けのユーザーとデータの移行に関する情報:</span><span class="sxs-lookup"><span data-stu-id="dcaba-117">For information about migrating users and data for specific Office 365 workloads:</span></span>

- <span data-ttu-id="dcaba-118">ユーザーのメールボックスを Exchange Server から Exchange Online へ: [Exchange Online ワークロード](exchangeonline-workload.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-118">User mailboxes from Exchange Server to Exchange Online, see the [Exchange Online workload](exchangeonline-workload.md).</span></span>
- <span data-ttu-id="dcaba-119">SharePoint データを SharePoint Server から SharePoint Online へ: [SharePoint Online ワークロード](sharepoint-online-onedrive-workload.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-119">SharePoint data from SharePoint Server to SharePoint Online, see the [SharePoint Online workload](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="dcaba-120">Skype for Business Online から Microsoft Teams へ: [Microsoft Teams ワークロード](teams-workload.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-120">Skype for Business Online to Microsoft Teams, see the [Microsoft Teams workload](teams-workload.md).</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="dcaba-121">Microsoft Office クライアント製品の移行</span><span class="sxs-lookup"><span data-stu-id="dcaba-121">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="dcaba-p104">大小問わず多くの組織では、Word、Excel、PowerPoint など、Office クライアント製品の古いバージョンの組み合わせを使っている可能性があります。これらの古いバージョンには以下の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p104">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="dcaba-124">最新のセキュリティ更新プログラムおよびサポート修正プログラムで[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)できますが、プロセスを手動で行う必要があったり、組織全体にまで行き渡らなかったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dcaba-124">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="dcaba-125">Microsoft クラウド テクノロジを活用しビジネスをデジタルに変換するうえで、最適ではありません。</span><span class="sxs-lookup"><span data-stu-id="dcaba-125">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="dcaba-126">新機能は含まれません。</span><span class="sxs-lookup"><span data-stu-id="dcaba-126">Do not contain new features.</span></span>
 
<span data-ttu-id="dcaba-127">Microsoft 365 Enterprise には、Microsoft 365 Enterprise ライセンスで利用でき、Microsoft クラウドからインストールおよび更新される Office クライアント製品のバージョンである Microsoft 365 Apps for enterprise が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dcaba-127">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products that is available with a Microsoft 365 Enterprise license and is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="dcaba-128">Microsoft 365 Apps for enterprise には、セキュリティ更新プログラムおよび最新機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-128">Microsoft 365 Apps for enterprise includes security updates and the latest features.</span></span> <span data-ttu-id="dcaba-129">詳細については、「[Microsoft 365 Apps for enterprise について](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-129">See [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="dcaba-130">Office 2007</span><span class="sxs-lookup"><span data-stu-id="dcaba-130">Office 2007</span></span>

<span data-ttu-id="dcaba-p106">Office 2007 リリースの Office のバージョンは、サポート期間が過ぎています。詳細については、「[Office 2007 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p106">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="dcaba-133">Office 2007 を実行しているコンピューターを Office 2010、Office 2013、または Office 2016 にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-133">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="dcaba-134">ユーザー用に Microsoft 365 ライセンスを取得して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dcaba-134">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="dcaba-135">ユーザーのコンピューターから Office 2007 をアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="dcaba-135">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="dcaba-136">Microsoft 365 Apps for enterprise を個別に、または IT ロールアウトと一緒にインストールする。</span><span class="sxs-lookup"><span data-stu-id="dcaba-136">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="dcaba-137">詳細については、「[フェーズ 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-137">For more information, see [Phase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="dcaba-138">Microsoft 365 Apps for enterprise は更新プログラムを自動的にインストールし、クラウドベースのサービスを活用して強化されたセキュリティと生産性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-138">Microsoft 365 Apps for enterprise installs updates automatically and can take advantage of cloud-based services for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="dcaba-139">Office 2010</span><span class="sxs-lookup"><span data-stu-id="dcaba-139">Office 2010</span></span>

<span data-ttu-id="dcaba-140">Office 2010 でリリースした Office バージョンの場合、サポートの終了は**2020 年 10 月 13 日**です。</span><span class="sxs-lookup"><span data-stu-id="dcaba-140">For versions of Office in the Office 2010 release, the end of support is **October 13, 2020**.</span></span> <span data-ttu-id="dcaba-141">詳細については、[Office 2010 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-141">For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="dcaba-142">Office 2010 を実行しているコンピューターを Office 2013 または Office 2016 (両方とも手動で更新する必要があります) にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-142">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span> 

1. <span data-ttu-id="dcaba-143">ユーザー用に Microsoft 365 ライセンスを取得して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dcaba-143">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="dcaba-144">ユーザーのコンピューターから Office 2010 をアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="dcaba-144">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="dcaba-145">Microsoft 365 Apps for enterprise を個別に、または IT ロールアウトと一緒にインストールする。</span><span class="sxs-lookup"><span data-stu-id="dcaba-145">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="dcaba-146">詳細については、「[フェーズ 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-146">For more information, see [Phase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="dcaba-147">Microsoft 365 Apps for enterprise はセキュリティと新機能の両方の更新プログラムを自動的にインストールし、Microsoft 365 のクラウドベースのサービスを活用して強化されたセキュリティと生産性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-147">Microsoft 365 Apps for enterprise installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="dcaba-148">Office 2013 および Office 2016</span><span class="sxs-lookup"><span data-stu-id="dcaba-148">Office 2013 and Office 2016</span></span>

<span data-ttu-id="dcaba-149">Office の Office 2013 および Office 2016 バージョンのサポート ロードマップの終了はまだ決定されていません。</span><span class="sxs-lookup"><span data-stu-id="dcaba-149">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined.</span></span> <span data-ttu-id="dcaba-150">ただし、Office 2010 と同様に、[セキュリティ更新プログラムをインストール](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)する必要があります。これは、組織の規模によっては適切に拡大されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcaba-150">However, like Office 2010, you must still [install security updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization.</span></span>

<span data-ttu-id="dcaba-151">Office 2013 または Office 2016 の最新のセキュリティ更新プログラムでコンピューターを更新し続けるか、Office 2013 から Office 2016 にコンピューターを更新するのではなく、以下を検討してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-151">Rather than keep updating your computers with the latest security updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="dcaba-152">ユーザー用に Microsoft 365 ライセンスを取得して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dcaba-152">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="dcaba-153">ユーザーのコンピューターから Office 2013 または Office 2016 をアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="dcaba-153">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="dcaba-154">Microsoft 365 Apps for enterprise を個別に、または IT ロールアウトと一緒にインストールする。</span><span class="sxs-lookup"><span data-stu-id="dcaba-154">Installing Microsoft 365 Apps for enterprise, either individually or in conjunction with an IT rollout.</span></span> <span data-ttu-id="dcaba-155">詳細については、「[フェーズ 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-155">For more information, see [Phase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="dcaba-156">Microsoft 365 Apps for enterprise はセキュリティと新機能の両方の更新プログラムを自動的にインストールし、Microsoft 365 のクラウドベースのサービスを活用して強化されたセキュリティと生産性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-156">Microsoft 365 Apps for enterprise installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="dcaba-157">Microsoft Office サーバー製品の移行</span><span class="sxs-lookup"><span data-stu-id="dcaba-157">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="dcaba-p112">大小問わず多くの組織では、Exchange Server や SharePoint Server などの Office サーバー製品の古いバージョンの組み合わせを使っている可能性があります。これらの古いバージョンには以下の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p112">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="dcaba-p113">最新のセキュリティ更新プログラムとサポート修正プログラムで更新する必要があります。場合によっては、これらの更新プログラムは毎月リリースされます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p113">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="dcaba-162">Microsoft クラウド テクノロジを活用しビジネスをデジタルに変換するうえで、最適ではありません。</span><span class="sxs-lookup"><span data-stu-id="dcaba-162">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="dcaba-163">Microsoft Teams などの新しい生産性向上アプリケーションは含まれません。</span><span class="sxs-lookup"><span data-stu-id="dcaba-163">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="dcaba-164">Exchange Advanced Threat Protection などの最新のセキュリティ機能は含まれません。</span><span class="sxs-lookup"><span data-stu-id="dcaba-164">Do not include the latest security features, such as Exchange Advanced Threat Protection.</span></span>

<span data-ttu-id="dcaba-165">Microsoft 365 Enterprise には Office 365 が含まれています。これには、Web ブラウザーや Outlook クライアントなど、オンプレミス バージョンの Office サーバー ソフトウェアと同じツールの一部を使用するクラウドベース バージョンの Office サーバー サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-165">Microsoft 365 Enterprise includes Office 365, which includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="dcaba-166">これらのサービスは、IT を関与させることなくセキュリティのために継続的に更新されるため、オンプレミス サーバーの管理と更新にかかる時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-166">These services are continually updated for security without involving IT, saving you the time it takes to maintain and update on-premises servers.</span></span> <span data-ttu-id="dcaba-167">これらのサービスには、Office サーバー ソフトウェアにはない新しい拡張機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="dcaba-167">These services also have new features enhancements that are not present in Office server software.</span></span> 

### <a name="office-server-2007"></a><span data-ttu-id="dcaba-168">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="dcaba-168">Office Server 2007</span></span>

<span data-ttu-id="dcaba-p115">Office 2007 リリースのサーバー製品については、サポート期間が過ぎています。詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p115">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="dcaba-171">Exchange 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dcaba-171">Exchange 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [<span data-ttu-id="dcaba-172">SharePoint Server 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dcaba-172">SharePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [<span data-ttu-id="dcaba-173">Project Server 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dcaba-173">Project Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [<span data-ttu-id="dcaba-174">Office Communications Server のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dcaba-174">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="dcaba-175">PerformancePoint Server 2007 のサポート終了ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dcaba-175">PerformancePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

<span data-ttu-id="dcaba-176">Office 2007 リリースのサーバー製品を Office 2010、Office 2013、または Office 2016 リリースのサーバー製品にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-176">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="dcaba-p116">Office 2007 サーバー上のデータを Office 365 に移行する。これをサポートするために、Microsoft パートナーを採用してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p116">Migrating the data on your Office 2007 servers to Office 365. To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="dcaba-179">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-179">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="dcaba-180">Office 2007 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-180">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="dcaba-181">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="dcaba-181">Office Server 2010</span></span>

<span data-ttu-id="dcaba-182">[Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) のサポートは、**2020 年 10 月 13 日**に終了します。</span><span class="sxs-lookup"><span data-stu-id="dcaba-182">The end of support for [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) is **October 13, 2020**.</span></span>

<span data-ttu-id="dcaba-183">[SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) のサポートは、**2021 年 4 月 13 日**に終了します。</span><span class="sxs-lookup"><span data-stu-id="dcaba-183">The end of support for [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) is **April 13, 2021**.</span></span>

<span data-ttu-id="dcaba-184">Office 2010 リリースのこれらのサーバー製品を Office 2013 または Office 2016 リリースのサーバー製品にアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-184">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="dcaba-185">Office 2010 サーバー上のデータを Microsoft 365 に移行します。</span><span class="sxs-lookup"><span data-stu-id="dcaba-185">Migrating the data on your Office 2010 servers to Microsoft 365.</span></span> <span data-ttu-id="dcaba-186">これを行うには、「[Microsoft 365 の FastTrack](https://fasttrack.microsoft.com/microsoft365)」を参照するか、Microsoft パートナーを採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcaba-186">To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="dcaba-187">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-187">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="dcaba-188">Office 2010 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-188">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="dcaba-189">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcaba-189">Office Server 2013</span></span>

<span data-ttu-id="dcaba-p118">Office 2013 リリースのサーバー製品については、サポートの終了日は決まっていません。Office 2013 リリースのサーバー製品を Office 2016 リリースにアップグレードするのではなく、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p118">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="dcaba-p119">Office 2013 サーバー上のデータを Office 365 に移行する。これをサポートするために、「[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365)」を参照するか、Microsoft パートナーを採用してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p119">Migrating the data on your Office 2013 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="dcaba-194">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-194">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="dcaba-195">Office 2013 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-195">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="dcaba-196">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="dcaba-196">Office Server 2016</span></span>

<span data-ttu-id="dcaba-p120">Office 2016 リリースのサーバー製品については、サポートの終了日は決まっていません。ビジネスをデジタルに変革するクラウドベースのサービスおよび拡張機能を活用するには、以下を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p120">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="dcaba-p121">Office 2016 サーバー上のデータを Office 365 に移行する。これをサポートするために、「[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365)」を参照するか、Microsoft パートナーを採用してください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-p121">Migrating the data on your Office 2016 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="dcaba-201">新しい機能と作業プロセスをユーザーに展開する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-201">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="dcaba-202">Office 2016 サーバー製品を実行しているオンプレミス サーバーが必要なくなった場合は使用を停止する。</span><span class="sxs-lookup"><span data-stu-id="dcaba-202">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows-7-and-81"></a><span data-ttu-id="dcaba-203">Microsoft Windows 7 および 8.1 の移行</span><span class="sxs-lookup"><span data-stu-id="dcaba-203">Migration for Microsoft Windows 7 and 8.1</span></span>

<span data-ttu-id="dcaba-204">Windows 7 は、**2020 年 1 月 14 日**にサポートが終了しました。</span><span class="sxs-lookup"><span data-stu-id="dcaba-204">Windows 7 reached end of support on **January 14, 2020**.</span></span> <span data-ttu-id="dcaba-205">Windows 7 または Windows 8.1 を実行しているデバイスを移行するには、[一括アップグレード](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-205">To migrate your devices running Windows 7 or Windows 8.1, you can perform an [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade).</span></span> 

<span data-ttu-id="dcaba-206">その他の方法については、「[Windows 10 展開のシナリオ](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-206">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="dcaba-207">自分で[Windows 10 の展開を計画](https://aka.ms/planforwin10deployment)することもできます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-207">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a><span data-ttu-id="dcaba-208">Office 2010 クライアントとサーバー、および Windows 7 のオプションの概要</span><span class="sxs-lookup"><span data-stu-id="dcaba-208">Summary of options for Office 2010 clients and servers and Windows 7</span></span>

<span data-ttu-id="dcaba-209">これらの製品のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめたものとしては、[サポート終了ポスター](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-209">For a visual summary of the upgrade, migrate, and move-to-the-cloud options for these products, see the [end of support poster](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf).</span></span>

<span data-ttu-id="dcaba-210">[![Office 2010 クライアントおよびサーバー サポート終了についての画像、 Windows 7 のポスター](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="dcaba-210">[![Image for the end of support for Office 2010 clients and servers and Windows 7 poster](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="dcaba-211">この 1 ページのポスターで、Office 2010 クライアントおよびサーバー製品と Windows 7 がサポート終了に達してしまうことを防ぐさまざまなパスをすばやく理解できます。ここには、強調表示された Microsoft 365 Enterprise で推奨されるパスとそれによる宛先サポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-211">This one-page poster is a quick way to understand the various paths you can take to prevent Office 2010 client and server products and Windows 7 from reaching end of support, with preferred paths and resulting destination support in Microsoft 365 Enterprise highlighted.</span></span>

<span data-ttu-id="dcaba-212">[このポスターをダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)して、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-212">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="dcaba-213">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="dcaba-213">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="dcaba-214">Microsoft の IT 担当者がどのように会社のデータを Microsoft 365 Enterprise に移行しているかについては、以下のリソースで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-214">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise with these resources:</span></span> 

- [<span data-ttu-id="dcaba-215">Microsoft Microsoft 365 Apps for enterprise の展開と更新</span><span class="sxs-lookup"><span data-stu-id="dcaba-215">Deploying and updating Microsoft Microsoft 365 Apps for enterprise</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="dcaba-216">Microsoft では 150,000 のメールボックスを Exchange Online に移行</span><span class="sxs-lookup"><span data-stu-id="dcaba-216">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="dcaba-217">SharePoint からクラウドへ: Microsoft が実施した移行方法</span><span class="sxs-lookup"><span data-stu-id="dcaba-217">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="dcaba-218">Microsoft における、Windows 10 のインプレース アップグレードとしての展開方法</span><span class="sxs-lookup"><span data-stu-id="dcaba-218">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="dcaba-219">[Windows 10 の展開: Microsoft の IT 担当者からのヒント](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="dcaba-219">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="dcaba-220">組織全体の移行</span><span class="sxs-lookup"><span data-stu-id="dcaba-220">Transition your entire organization</span></span>

<span data-ttu-id="dcaba-221">組織全体を Microsoft 365 Enterprise の製品とサービスに移行する方法をより良く理解するためには、[移行のポスター](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dcaba-221">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 Enterprise, see the [transition poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf).</span></span>

<span data-ttu-id="dcaba-222">[![「Microsoft 365への移行」ポスターの画像](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="dcaba-222">[![Image for the Transition to Microsoft 365 poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="dcaba-223">この見開きポスター (2 ページ) で簡単に既存のインフラストラクチャのインベントリを確認して、Microsoft 365 Enterprise で対応する製品またはサービスに移行するためのガイダンスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-223">This two-page poster is a quick way to inventory your existing infrastructure and get to the guidance for moving to the corresponding product or service in Microsoft 365 Enterprise.</span></span> <span data-ttu-id="dcaba-224">Windows および Office の製品、その他のインフラストラクチャ、それから、デバイス管理、ID、情報および脅威保護などのセキュリティ要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-224">It includes Windows and Office products and other infrastructure and security elements such as device management, identity, and information and threat protection.</span></span>

<span data-ttu-id="dcaba-225">[このポスターをダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)して、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-225">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="result"></a><span data-ttu-id="dcaba-226">結果</span><span class="sxs-lookup"><span data-stu-id="dcaba-226">Result</span></span>

<span data-ttu-id="dcaba-227">お客様の組織では Microsoft Office、Office サーバー、Windows の古いバージョンが Microsoft 365 Enterprise に移行されます。</span><span class="sxs-lookup"><span data-stu-id="dcaba-227">Your organization has migrated older versions of Microsoft Office, Office servers, and Windows to Microsoft 365 Enterprise.</span></span>
