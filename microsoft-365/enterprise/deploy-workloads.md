---
title: Microsoft 365 Enterprise のワークロードとシナリオ
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 組織のユーザーを Microsoft 365 Enterprise の生産性ワークロードへ参加させます。
ms.openlocfilehash: 30dbf913016687025c6159f1f1fc311462a13d29
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400141"
---
# <a name="microsoft-365-enterprise-workloads-and-scenarios"></a><span data-ttu-id="bfb88-103">Microsoft 365 Enterprise のワークロードとシナリオ</span><span class="sxs-lookup"><span data-stu-id="bfb88-103">Microsoft 365 Enterprise workloads and scenarios</span></span>

<span data-ttu-id="bfb88-104">Microsoft 365 Enterprise の創造性とチームワークのメリットを得るため、次のワークロードを基礎インフラストラクチャに展開します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-104">To realize the creativity and teamwork benefits of Microsoft 365 Enterprise, deploy these workloads and scenarios to operate on the top of your foundation infrastructure:</span></span>

- [<span data-ttu-id="bfb88-105">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfb88-105">Microsoft Teams</span></span>](teams-workload.md)
- [<span data-ttu-id="bfb88-106">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bfb88-106">Exchange Online</span></span>](exchangeonline-workload.md)
- [<span data-ttu-id="bfb88-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bfb88-107">SharePoint Online</span></span>](sharepoint-online-onedrive-workload.md)

<span data-ttu-id="bfb88-108">組織全体を Microsoft 365 Enterprise に移行するための一般的なロードマップについては、[移行](migration-microsoft-365-enterprise-workload.md)ワークロードを参照してください。Microsoft 365 Enterprise には Microsoft Office クライアント製品、オンプレミス Office サーバー製品、および Microsoft Windows ベースのデバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-108">See the [migration](migration-microsoft-365-enterprise-workload.md) workload for a general roadmap to migrate your entire organization to Microsoft 365 Enterprise, which includes Microsoft Office client products, on-premises Office Server products, and Microsoft Windows-based devices.</span></span>

<span data-ttu-id="bfb88-109">シナリオは Microsoft 365 Enterprise 全体から機能およびサービスを統合された方法で使用し、ビジネスニーズに対応します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-109">Scenarios use features and services from across Microsoft 365 Enterprise in an integrated way to address a business need.</span></span> <span data-ttu-id="bfb88-110">そうしたニーズの 1 つは Microsoft 365 に格納されている規制の厳しいデータを保護することです。</span><span class="sxs-lookup"><span data-stu-id="bfb88-110">One such need is to protect highly regulated data stored in Microsoft 365.</span></span> <span data-ttu-id="bfb88-111">規制の厳しいデータには次に示すデジタル資産が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfb88-111">Highly regulated data includes digital assets that are:</span></span>

- <span data-ttu-id="bfb88-112">地域の規制を遵守しているデータ。</span><span class="sxs-lookup"><span data-stu-id="bfb88-112">Subject to regional regulations.</span></span>
- <span data-ttu-id="bfb88-113">企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータ。</span><span class="sxs-lookup"><span data-stu-id="bfb88-113">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="bfb88-114">こうしたデータを内外の脅威から保護するには、「[Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfb88-114">To protect this data from internal and external threats, see the instructions in [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span> <span data-ttu-id="bfb88-115">このシナリオは段階を追って SharePoint Online サイトまたは Microsoft Teams チームを設定し、最も重要なデータを安全に保管します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-115">This scenario steps you through configuring a SharePoint Online site or a Microsoft Teams team to securely store your most valuable data.</span></span>

<span data-ttu-id="bfb88-116">Microsoft 365 Enterprise 展開ガイド全体のワークロードとシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-116">Here are the workloads and scenarios in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a><span data-ttu-id="bfb88-117">基盤インフラストラクチャの前提条件</span><span class="sxs-lookup"><span data-stu-id="bfb88-117">Foundation infrastructure prerequisites</span></span>

<span data-ttu-id="bfb88-118">*理想的には*、[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)のすべてのフェーズを設定した後で、ワークロードとシナリオを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfb88-118">*Ideally*, you should deploy workloads and scenarios after you have configured all of the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span> <span data-ttu-id="bfb88-119">これにより、基になるすべてのレイヤーがユーザーとそのデバイスに対して統合、セキュリティ、および最適な操作性を提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfb88-119">This ensures that all of the underlying layers are in place to provide integration, security, and the best experience for your users and their devices.</span></span>

| <span data-ttu-id="bfb88-120">フェーズ</span><span class="sxs-lookup"><span data-stu-id="bfb88-120">Phase</span></span> | <span data-ttu-id="bfb88-121">結果</span><span class="sxs-lookup"><span data-stu-id="bfb88-121">Result</span></span> |
|:-------|:-----|
| <span data-ttu-id="bfb88-122">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="bfb88-122">Network</span></span> | <span data-ttu-id="bfb88-123">Microsoft 365 のクラウド サービスに対して最適なパフォーマンスを得るためにネットワークが更新されます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-123">Your network is updated for optimum performance to Microsoft 365 cloud services.</span></span> |
| <span data-ttu-id="bfb88-124">ID</span><span class="sxs-lookup"><span data-stu-id="bfb88-124">Identity</span></span> | <span data-ttu-id="bfb88-125">ユーザー アカウントの強力な認証と管理アカウントの保護により、ID は同期されセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-125">Identity is synchronized and secured with strong authentication for user accounts and protection for admin accounts.</span></span> |
| <span data-ttu-id="bfb88-126">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bfb88-126">Windows 10 Enterprise</span></span> | <span data-ttu-id="bfb88-127">Windows 7 または Windows 8.1 を実行しているコンピューターは Windows 10 Enterprise にアップグレードすることができ、新しいデバイスは Windows 10 Enterprise と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-127">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
| <span data-ttu-id="bfb88-128">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="bfb88-128">Office 365 ProPlus</span></span> | <span data-ttu-id="bfb88-129">Microsoft Office の既存のユーザーは Office 365 ProPlus にアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-129">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
| <span data-ttu-id="bfb88-130">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="bfb88-130">Mobile device management</span></span> | <span data-ttu-id="bfb88-131">デバイスを登録し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-131">Your devices can be enrolled and managed.</span></span> |
| <span data-ttu-id="bfb88-132">情報保護</span><span class="sxs-lookup"><span data-stu-id="bfb88-132">Information protection</span></span> | <span data-ttu-id="bfb88-133">Office 365 のセキュリティ機能が有効で、機密または Azure Information Protection ラベルはドキュメントを保護する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="bfb88-133">Office 365 security features are enabled and your sensitivity or Azure Information Protection labels are ready to protect documents.</span></span> |

<span data-ttu-id="bfb88-134">これは理想的であり、計画、構成、テスト、およびパイロットのために時間がかかる場合があることに注意してください。特に既存のインフラストラクチャで複数の場所が対象になる大規模な組織が該当します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-134">Remember that this is ideal and can take some time to plan for, configure, test, and pilot, especially in large organizations with existing infrastructure and multiple locations.</span></span> <span data-ttu-id="bfb88-135">こうしたレイヤーのすべてをあらゆる場所に配置することは、Microsoft 365 Enterprise からビジネス上の価値をより迅速に得るためには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bfb88-135">Putting all of these layers in place in all locations is not necessary for you to more quickly get business value from Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="bfb88-136">すぐに展開するための一般的なワークロードを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-136">Here are some common workloads to deploy right away:</span></span> 

- <span data-ttu-id="bfb88-137">基盤インフラストラクチャの **ID** レイヤーがユーザーにロールアウトされた後で、多くの組織は以下を展開します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-137">After the **Identity** layer of the foundation infrastructure is rolled out to users, many organizations deploy:</span></span>
  - <span data-ttu-id="bfb88-138">[Office 365 ProPlus](office365proplus-infrastructure.md)。[OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) を組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-138">[Office 365 ProPlus](office365proplus-infrastructure.md) combined with [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span> <span data-ttu-id="bfb88-139">Office 365 ProPlus は先進的な認証のセキュリティと最新の Microsoft Office クライアントのユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-139">Office 365 ProPlus provides the security of modern authentication and the user experience of the latest Microsoft Office client.</span></span> <span data-ttu-id="bfb88-140">ユーザーの個人用ファイルを OneDrive for Business に移行するとインフラストラクチャが削減され、ホーム フォルダーとドライブをサポートする必要性も少なくなります。</span><span class="sxs-lookup"><span data-stu-id="bfb88-140">The migration of user's personal files to OneDrive for Business reduces infrastructure and the need to support home folders and drives.</span></span>
  - <span data-ttu-id="bfb88-141">[Exchange Online](exchangeonline-workload.md)。ユーザーはクラウド ベースのメールの使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfb88-141">[Exchange Online](exchangeonline-workload.md) so that users can begin using cloud-based email.</span></span>
- <span data-ttu-id="bfb88-142">厳しく規制されたデジタル資産をすぐにクラウドで使用する必要がない場合は、**情報保護**レイヤーの前に [Microsoft Teams](teams-workload.md) と [SharePoint Online](sharepoint-online-onedrive-workload.md) をユーザー向けに展開します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-142">If you don't have an immediate need for storing highly regulated digital assets in the cloud, deploy [Microsoft Teams](teams-workload.md) and [SharePoint Online](sharepoint-online-onedrive-workload.md) for your users prior to the **Information protection** layer.</span></span>

<span data-ttu-id="bfb88-143">ビジネス ニーズの達成が最高になるように、基盤インフラストラクチャの前提となるフェーズの設定について最適な順序と展開を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfb88-143">You must decide on how to best order and deploy the configuration of prerequisite phases of foundation infrastructure to best meet your business needs.</span></span>

### <a name="best-practice"></a><span data-ttu-id="bfb88-144">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="bfb88-144">Best practice</span></span>

<span data-ttu-id="bfb88-145">ユーザーを何らかのワークロードまたはシナリオに参加させる前に、基盤インフラストラクチャの **ID** フェーズを展開しロールアウトすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="bfb88-145">We highly recommend that you deploy and roll out the **Identity** phase of the foundation infrastructure prior to onboarding your users to any workloads or scenarios.</span></span>

<span data-ttu-id="bfb88-146">**ID** フェーズでは、クラウド ベースの ID は、クラウド専用であるかオンプレミスの Active Directory Domain Services (AD DS) と同期されているかにかかわらず、認証とアクセスの管理のためにユーザーおよびコンピューター アカウントとグループを含むようになります。</span><span class="sxs-lookup"><span data-stu-id="bfb88-146">The **Identity** phase ensures that your cloud-based identity, whether cloud-only or synchronized with your on-premises Active Directory Domain Services (AD DS), contains the user and computer accounts and groups to manage authentication and access.</span></span> <span data-ttu-id="bfb88-147">Microsoft 365 クラウドに組織のデジタル資産を配置する前に、すべてのユーザーの強力な認証のほか管理者アカウントの強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="bfb88-147">Strong authentication for all your users along with strong protection of admin accounts is required before placing your organization's digital assets in the Microsoft 365 cloud.</span></span>

<span data-ttu-id="bfb88-148">全体的なパフォーマンスにとって基本的で非常に重要ですが、Microsoft 365 のアプリケーションとサービスのパフォーマンスは時間の経過とともに向上することを考慮すると、使用するネットワークにおける**ネットワーキング** フェーズのロールアウトはユーザーをワークロードに参加させながら進めることができます。</span><span class="sxs-lookup"><span data-stu-id="bfb88-148">Although foundational and very important to overall performance, the rollout of the **Networking** phase on your network can be in progress while onboarding your users to workloads, with the understanding that Microsoft 365 application and service performance will improve over time.</span></span>

<span data-ttu-id="bfb88-149">これは特に複数の場所とエッジ デバイスとインターネット接続が混在する企業にあてはまります。</span><span class="sxs-lookup"><span data-stu-id="bfb88-149">This is especially true for enterprise organizations with multiple locations and a mixture of edge devices and Internet connections.</span></span>
