---
title: 手順 4. エンタープライズ テナント向け Microsoft 365 の移行
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナント用Office Windows デバイス、Office クライアント アプリ、およびサーバーを移行します。
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908626"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="4a483-104">手順 4.</span><span class="sxs-lookup"><span data-stu-id="4a483-104">Step 4.</span></span> <span data-ttu-id="4a483-105">エンタープライズ テナント向け Microsoft 365 の移行</span><span class="sxs-lookup"><span data-stu-id="4a483-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="4a483-106">ほとんどの企業組織には、オペレーティング システム、クライアント ソフトウェア、およびサーバー ソフトウェアの複数のリリースを含む異種環境があります。</span><span class="sxs-lookup"><span data-stu-id="4a483-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="4a483-107">Microsoft 365 enterprise には、IT インフラストラクチャの主要なコンポーネントの最も安全なバージョンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a483-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="4a483-108">また、クラウド テクノロジを活用するように設計された生産性機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a483-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="4a483-109">Microsoft 365 enterprise 統合製品スイートのビジネス価値を最大限に高めるには、次のリリースを移行する戦略の計画と実装を開始します。</span><span class="sxs-lookup"><span data-stu-id="4a483-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="4a483-110">送信元</span><span class="sxs-lookup"><span data-stu-id="4a483-110">From</span></span> | <span data-ttu-id="4a483-111">宛先</span><span class="sxs-lookup"><span data-stu-id="4a483-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="4a483-112">Windows 7 および Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4a483-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="4a483-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4a483-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="4a483-114">Officeのデバイスにインストールされているクライアント製品を管理する</span><span class="sxs-lookup"><span data-stu-id="4a483-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="4a483-115">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="4a483-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="4a483-116">Officeサーバーにインストールされているサーバー製品を管理する</span><span class="sxs-lookup"><span data-stu-id="4a483-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="4a483-117">Microsoft 365 の同等のクラウドベースのサービス</span><span class="sxs-lookup"><span data-stu-id="4a483-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="4a483-118">Windows 10 への移行</span><span class="sxs-lookup"><span data-stu-id="4a483-118">Migrating to Windows 10</span></span>

<span data-ttu-id="4a483-119">各 Microsoft 365 enterprise ライセンスには、Windows 10 Enterprise のライセンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a483-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="4a483-120">Windows 7 または Windows 8.1 を実行するデバイスを移行するには、一時アップグレードを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a483-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="4a483-121">Windows 7 のサポートは *、2020 年 1 月 14 日に終了しました*。</span><span class="sxs-lookup"><span data-stu-id="4a483-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="4a483-122">一時アップグレード以外に Windows 10 Enterprise をインストールするその他の方法については [、Windows 10 の展開シナリオに関するページをご覧ください](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="4a483-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="4a483-123">自分で[Windows 10 の展開を計画](https://aka.ms/planforwin10deployment)することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a483-123">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4a483-124">Microsoft 365 Apps for enterprise への移行</span><span class="sxs-lookup"><span data-stu-id="4a483-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="4a483-125">Microsoft 365 for enterprise には、Microsoft クラウドからインストールおよび更新される Office クライアント製品 (Word、PowerPoint、Excel、Outlook) のバージョンである Microsoft 365 Apps for enterprise が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a483-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="4a483-126">詳細については [、「Microsoft 365 Apps for enterprise について」を参照してください](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="4a483-126">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="4a483-127">2019 以前のバージョンのコンピューターを最新Officeするのではなく、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4a483-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="4a483-128">ユーザーに Microsoft 365 ライセンスを取得して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="4a483-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="4a483-129">コンピューター Office 2013 2016 Officeまたは 2016 をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a483-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="4a483-130">Microsoft 365 Apps for enterprise を個別に、または IT ロールアウト中にインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a483-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="4a483-131">詳細については [、Microsoft 365 アプリの展開ガイドを参照してください](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="4a483-131">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="4a483-132">Microsoft 365 Apps for enterprise は、セキュリティ更新プログラムと新しい機能更新プログラムの両方を自動的にインストールし、Microsoft 365 のクラウドベースのサービスを活用してセキュリティと生産性を強化できます。</span><span class="sxs-lookup"><span data-stu-id="4a483-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="4a483-133">オンプレミスのサーバーとデータを Microsoft 365 に移行する</span><span class="sxs-lookup"><span data-stu-id="4a483-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="4a483-134">Microsoft 365 for enterprise には、Web ブラウザーや Outlook クライアントなど、オンプレミス バージョンの Office サーバー ソフトウェアと同じツールの一部を使用するクラウドベースのバージョンの Office サーバー サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a483-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="4a483-135">これらのクラウドベースのサービスは、セキュリティと新機能のために自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="4a483-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="4a483-136">移行後、IT 部門はオンプレミス サーバーの保守と更新にかかる時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="4a483-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="4a483-137">特定の Microsoft 365 ワークロードのユーザーとデータの移行に関する情報については、次のリソースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="4a483-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="4a483-138">オンプレミスのメールボックスから Exchange Online Exchange Serverメールボックスを移動する</span><span class="sxs-lookup"><span data-stu-id="4a483-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="4a483-139">SharePoint Server から SharePoint Online に SharePoint データを移行する</span><span class="sxs-lookup"><span data-stu-id="4a483-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="4a483-140">Skype for Business Online を Microsoft Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="4a483-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="4a483-141">組織全体の移行</span><span class="sxs-lookup"><span data-stu-id="4a483-141">Transition your entire organization</span></span>

<span data-ttu-id="4a483-142">組織全体を Microsoft 365 enterprise の製品とサービスに移行する方法をより良く理解するには、次の移行ポスターをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="4a483-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="4a483-143">[![Microsoft 365 への移行ポスターを示す画像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="4a483-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="4a483-144">この2ページのポスターをご覧になると、既存のインフラストラクチャを簡単にインベントリできます。</span><span class="sxs-lookup"><span data-stu-id="4a483-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="4a483-145">Microsoft 365 enterprise の製品またはサービスへの移行に関するガイダンスを受け取る場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="4a483-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="4a483-146">Windows と Office製品、デバイス管理、ID と脅威の保護、情報保護とコンプライアンスなどの他のインフラストラクチャとセキュリティ要素を示します。</span><span class="sxs-lookup"><span data-stu-id="4a483-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="4a483-147">手順 4 の結果</span><span class="sxs-lookup"><span data-stu-id="4a483-147">Results of Step 4</span></span>

<span data-ttu-id="4a483-148">Microsoft 365 テナントの移行では、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="4a483-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="4a483-149">Windows 7 または Windows 8.1 を実行しているデバイスと、それらを Windows 10 Enterprise に更新する計画。</span><span class="sxs-lookup"><span data-stu-id="4a483-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="4a483-150">Office クライアント アプリを実行しているデバイスと、それらを Microsoft 365 Enterprise アプリに更新する計画。</span><span class="sxs-lookup"><span data-stu-id="4a483-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="4a483-151">どのオンプレミスの Office サーバー サービスを Microsoft 365 と同等のサービスに移行し、それらのサービスとそのデータを移行する計画を立てるべきか。</span><span class="sxs-lookup"><span data-stu-id="4a483-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="4a483-152">オンプレミス サーバーの移行が完了したテナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a483-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![オンプレミス サーバーの移行が完了したテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="4a483-154">この図では、組織には次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="4a483-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="4a483-155">オンプレミスのメールボックスを Exchange Online Exchange Server移行しました。</span><span class="sxs-lookup"><span data-stu-id="4a483-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="4a483-156">オンプレミスの SharePoint Server サイトとデータを Microsoft 365 の SharePoint に移行しました。</span><span class="sxs-lookup"><span data-stu-id="4a483-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="4a483-157">移行の継続的なメンテナンス</span><span class="sxs-lookup"><span data-stu-id="4a483-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="4a483-158">継続的に、次の必要が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="4a483-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="4a483-159">Exchange メールボックスの移行の状態に応じて、引き続き Exchange Online への組織への移行を展開します。</span><span class="sxs-lookup"><span data-stu-id="4a483-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="4a483-160">オンプレミスの SharePoint サイトの移行の状態に応じて、Microsoft 365 の SharePoint への移行を引き続き組織に展開します。</span><span class="sxs-lookup"><span data-stu-id="4a483-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="4a483-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="4a483-161">Next step</span></span>

<span data-ttu-id="4a483-162">[![手順 5.デバイスとアプリの管理を展開する](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="4a483-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="4a483-163">デバイスと [アプリの管理を続行して、](tenant-management-device-management.md) デバイスとアプリの管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="4a483-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>
