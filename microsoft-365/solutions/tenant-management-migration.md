---
title: 手順 4. エンタープライズ テナントのMicrosoft 365移行
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: テナント用Windowsデバイス、Office アプリ、Office サーバーを移行Microsoft 365します。
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929146"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="fa9c6-104">手順 4.</span><span class="sxs-lookup"><span data-stu-id="fa9c6-104">Step 4.</span></span> <span data-ttu-id="fa9c6-105">エンタープライズ テナントのMicrosoft 365移行</span><span class="sxs-lookup"><span data-stu-id="fa9c6-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="fa9c6-106">ほとんどのエンタープライズ組織には、オペレーティング システム、クライアント ソフトウェア、およびサーバー ソフトウェアの複数のリリースを含む異種環境があります。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="fa9c6-107">Microsoft 365には、IT インフラストラクチャの主要なコンポーネントの最も安全なバージョンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="fa9c6-108">また、クラウド テクノロジを活用するように設計された生産性機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="fa9c6-109">エンタープライズ統合製品スイートMicrosoft 365のビジネス価値を最大化するには、次のリリースを移行するための戦略の計画と実装を開始します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="fa9c6-110">From</span><span class="sxs-lookup"><span data-stu-id="fa9c6-110">From</span></span> | <span data-ttu-id="fa9c6-111">へ</span><span class="sxs-lookup"><span data-stu-id="fa9c6-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="fa9c6-112">Windows 7 と Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="fa9c6-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="fa9c6-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fa9c6-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="fa9c6-114">Officeのデバイスにインストールされているクライアント製品を管理する</span><span class="sxs-lookup"><span data-stu-id="fa9c6-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="fa9c6-115">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="fa9c6-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="fa9c6-116">Officeサーバーにインストールされているサーバー製品を管理する</span><span class="sxs-lookup"><span data-stu-id="fa9c6-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="fa9c6-117">同じクラウド ベースのサービスをMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="fa9c6-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="fa9c6-118">サーバーへのWindows 10</span><span class="sxs-lookup"><span data-stu-id="fa9c6-118">Migrating to Windows 10</span></span>

<span data-ttu-id="fa9c6-119">エンタープライズ Microsoft 365の各ライセンスには、エンタープライズ ライセンスのWindows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="fa9c6-120">7 または 7 を実行するWindowsを移行Windows 8.1、インプレイス アップグレードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="fa9c6-121">*2020* 年 1 月 14 Windows 7 日にサポートが終了しました。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="fa9c6-122">一時アップグレードを超えてWindows 10 Enterpriseインストールするその他の方法については[、「Windows 10」を参照してください](/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="fa9c6-123">自分で[Windows 10 の展開を計画](/windows/deployment/planning/)することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="fa9c6-124">サーバーへのMicrosoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="fa9c6-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="fa9c6-125">Microsoft 365には、microsoft クラウドからインストールおよび更新される Office クライアント製品 (Word、PowerPoint、Excel、および Outlook) のバージョンである Microsoft 365 Apps for enterprise が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="fa9c6-126">詳細については、「概要[」 を参照Microsoft 365 Apps for enterprise。](/deployoffice/about-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="fa9c6-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="fa9c6-127">2019 以前のバージョンのコンピューターを最新Officeではなく、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="fa9c6-128">ユーザーのライセンスを取得Microsoft 365割り当てる。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="fa9c6-129">コンピューター Office 2013 または Office 2016 をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="fa9c6-130">個別Microsoft 365 Apps for enterpriseまたは IT ロールアウト中に、このファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="fa9c6-131">詳細については、「展開ガイド[for Microsoft 365 Apps」 を参照してください](/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="fa9c6-132">Microsoft 365 Apps for enterprise更新プログラムと新しい機能更新プログラムの両方を自動的にインストールし、セキュリティと生産性を向上Microsoft 365クラウド ベースのサービスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="fa9c6-133">オンプレミスのサーバーとデータをサーバーに移行Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa9c6-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="fa9c6-134">Microsoft 365には、web ブラウザーや Outlook クライアントなど、オンプレミスバージョンの Office サーバー ソフトウェアと同じツールの一部を使用するクラウドベースのバージョンの Office サーバー サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="fa9c6-135">これらのクラウドベースのサービスは、セキュリティと新機能のために自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="fa9c6-136">移行後、IT 部門はオンプレミス サーバーの保守と更新にかかる時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="fa9c6-137">特定のワークロードのユーザーとデータを移行する方法については、次Microsoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="fa9c6-138">メールボックスをオンプレミスのメールボックスからExchange ServerにExchange Online</span><span class="sxs-lookup"><span data-stu-id="fa9c6-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="fa9c6-139">サーバー SharePointからオンラインにSharePointデータをSharePointする</span><span class="sxs-lookup"><span data-stu-id="fa9c6-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="fa9c6-140">オンラインSkype for Businessに移行Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa9c6-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="fa9c6-141">組織全体の移行</span><span class="sxs-lookup"><span data-stu-id="fa9c6-141">Transition your entire organization</span></span>

<span data-ttu-id="fa9c6-142">組織全体をエンタープライズ向け製品とサービスに移動する方法の詳細を確認するには、次のMicrosoft 365ポスターをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="fa9c6-143">[![ポスターへの移行を示Microsoft 365画像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="fa9c6-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="fa9c6-144">この2ページのポスターをご覧になると、既存のインフラストラクチャを簡単にインベントリできます。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="fa9c6-145">エンタープライズ向け製品またはサービスへの移行に関するガイダンスを取得するには、このMicrosoft 365使用します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="fa9c6-146">デバイス管理Windows脅威Office、情報保護とコンプライアンスなど、製品、その他のインフラストラクチャおよびセキュリティ要素に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="fa9c6-147">手順 4 の結果</span><span class="sxs-lookup"><span data-stu-id="fa9c6-147">Results of Step 4</span></span>

<span data-ttu-id="fa9c6-148">テナントの移行Microsoft 365決定しました。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="fa9c6-149">7 または 7 WindowsをWindows 8.1するデバイスと、デバイスを更新する計画Windows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="fa9c6-150">どのデバイスがクライアント Officeを実行し、エンタープライズ向けアプリに更新Microsoft 365計画を立てられています。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="fa9c6-151">サーバー サービスを同等Officeサーバー サービスに移行するMicrosoft 365、それらのサーバー サービスとそのデータを移行する計画。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="fa9c6-152">オンプレミス サーバーの移行が完了したテナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![オンプレミス サーバーの移行が完了したテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="fa9c6-154">この図では、組織には次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="fa9c6-155">オンプレミスのメールボックスをExchange Serverに移行Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="fa9c6-156">オンプレミスのサーバー サイトとデータSharePointを、サーバー 内のSharePointにMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="fa9c6-157">移行の継続的なメンテナンス</span><span class="sxs-lookup"><span data-stu-id="fa9c6-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="fa9c6-158">継続的に、次の必要が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="fa9c6-159">メールボックスの移行の状態に応じてExchange移行を組織にExchange Online展開します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="fa9c6-160">オンプレミスのサイト移行の状態に応じて、SharePointに移行をSharePoint移行Microsoft 365展開します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="fa9c6-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="fa9c6-161">Next step</span></span>

<span data-ttu-id="fa9c6-162">[![手順 5.デバイスとアプリの管理を展開する](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="fa9c6-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="fa9c6-163">デバイスと [アプリの管理を続行して、](tenant-management-device-management.md) デバイスとアプリの管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="fa9c6-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>