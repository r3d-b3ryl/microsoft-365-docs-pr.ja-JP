---
title: Microsoft 365 Enterprise のワークロード
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 組織のユーザーを Microsoft 365 Enterprise の生産性向上ワークロードに参加させます。
ms.openlocfilehash: 0e1658655c4b97a7e571d1ac09c4b2edcc6c82ce
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268287"
---
# <a name="microsoft-365-for-enterprise-workloads"></a><span data-ttu-id="e1adc-103">Microsoft 365 Enterprise のワークロード</span><span class="sxs-lookup"><span data-stu-id="e1adc-103">Microsoft 365 for enterprise workloads</span></span>

<span data-ttu-id="e1adc-104">Microsoft 365 Enterprise の創造性およびチームワークに関するメリットを得るには、これらのワークロードを基盤インフラストラクチャに展開します。</span><span class="sxs-lookup"><span data-stu-id="e1adc-104">To get the creativity and teamwork benefits of Microsoft 365 for enterprise, deploy these workloads over your foundation infrastructure:</span></span>

- [<span data-ttu-id="e1adc-105">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1adc-105">Microsoft Teams</span></span>](teams-workload.md)
- [<span data-ttu-id="e1adc-106">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e1adc-106">Exchange Online</span></span>](exchangeonline-workload.md)
- [<span data-ttu-id="e1adc-107">SharePoint および OneDrive</span><span class="sxs-lookup"><span data-stu-id="e1adc-107">SharePoint and OneDrive</span></span>](sharepoint-online-onedrive-workload.md)

<span data-ttu-id="e1adc-108">組織全体を Microsoft 365 Enterprise に移行するための一般的なロードマップについては、[移行](migration-microsoft-365-enterprise-workload.md)に関する記事を参照してください。それには Microsoft Office クライアント製品、オンプレミス Office サーバー製品、および Microsoft Windows ベースのデバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1adc-108">See the [migration](migration-microsoft-365-enterprise-workload.md) article for a general roadmap to migrate your entire organization to Microsoft 365 for enterprise, which includes Microsoft Office client products, on-premises Office Server products, and Microsoft Windows-based devices.</span></span>

<span data-ttu-id="e1adc-109">全体的な Microsoft 365 Enterprise 展開ガイドのワークロードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1adc-109">Here are the workloads in the overall Microsoft 365 for enterprise deployment guide:</span></span>

![全体的な Microsoft 365 Enterprise 展開ガイドのワークロード](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a><span data-ttu-id="e1adc-111">基盤インフラストラクチャの前提条件</span><span class="sxs-lookup"><span data-stu-id="e1adc-111">Foundation infrastructure prerequisites</span></span>

<span data-ttu-id="e1adc-112">*理想的には*、[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)のすべてのフェーズを設定した後で、ワークロードを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1adc-112">*Ideally*, you should deploy workloads after you have configured all of the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span> <span data-ttu-id="e1adc-113">これにより、基になるすべての基盤レイヤーがユーザーとそのデバイスに対して統合、セキュリティ、および最適な操作性を提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1adc-113">This ensures that all of the underlying foundation layers are in place to provide integration, security, and the best experience for your users and their devices.</span></span>

| <span data-ttu-id="e1adc-114">フェーズ</span><span class="sxs-lookup"><span data-stu-id="e1adc-114">Phase</span></span> | <span data-ttu-id="e1adc-115">結果</span><span class="sxs-lookup"><span data-stu-id="e1adc-115">Result</span></span> |
|:-------|:-----|
| <span data-ttu-id="e1adc-116">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="e1adc-116">Network</span></span> | <span data-ttu-id="e1adc-117">Microsoft 365 のクラウド サービスに対して最適なパフォーマンスを得るためにネットワークが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e1adc-117">Your network is updated for optimum performance to Microsoft 365 cloud services.</span></span> |
| <span data-ttu-id="e1adc-118">ID</span><span class="sxs-lookup"><span data-stu-id="e1adc-118">Identity</span></span> | <span data-ttu-id="e1adc-119">ユーザー アカウントの強力な認証と管理アカウントの保護により、ID は同期されセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="e1adc-119">Identity is synchronized and secured with strong authentication for user accounts and protection for admin accounts.</span></span> |
| <span data-ttu-id="e1adc-120">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e1adc-120">Windows 10 Enterprise</span></span> | <span data-ttu-id="e1adc-121">Windows 7 または Windows 8.1 を実行しているコンピューターは Windows 10 Enterprise にアップグレードすることができ、新しいデバイスは Windows 10 Enterprise と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1adc-121">Your computers running Windows 7 or Windows 8.1 can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
| <span data-ttu-id="e1adc-122">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="e1adc-122">Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="e1adc-123">Microsoft Office を使用している既存のユーザーは、Microsoft 365 Apps for enterprise にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="e1adc-123">Your existing users of Microsoft Office can upgrade to Microsoft 365 Apps for enterprise.</span></span> |
| <span data-ttu-id="e1adc-124">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="e1adc-124">Mobile device management</span></span> | <span data-ttu-id="e1adc-125">デバイスを登録し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e1adc-125">Your devices can be enrolled and managed.</span></span> |
| <span data-ttu-id="e1adc-126">情報保護</span><span class="sxs-lookup"><span data-stu-id="e1adc-126">Information protection</span></span> | <span data-ttu-id="e1adc-127">Office 365 の情報保護機能が構成されると、機密ラベルまたは Azure Information Protection ラベルでドキュメントを保護する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="e1adc-127">Microsoft 365 information protection features are configured and your sensitivity or Azure Information Protection labels are ready to protect documents and email.</span></span> |

<span data-ttu-id="e1adc-128">これは理想的であり、計画、構成、テスト、およびパイロットのために時間がかかる場合があることに注意してください。特に既存のインフラストラクチャで複数の場所が対象になる大規模な組織が該当します。</span><span class="sxs-lookup"><span data-stu-id="e1adc-128">Remember that this is ideal and can take some time to plan for, configure, test, and pilot, especially in large organizations with existing infrastructure and multiple locations.</span></span> <span data-ttu-id="e1adc-129">すべての場所でこれらのフェーズを完了させることは、Microsoft 365 Enterprise からビジネス上の価値をより迅速に得るためには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e1adc-129">Completing all of these phases in all locations is not necessary for you to more quickly get business value from Microsoft 365 for enterprise.</span></span> 

<span data-ttu-id="e1adc-130">すぐに展開するための一般的なワークロードを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e1adc-130">Here are some common workloads to deploy right away:</span></span> 

- <span data-ttu-id="e1adc-131">基盤インフラストラクチャの **ID** フェーズがユーザーにロールアウトされた後で、多くの組織は以下を展開します。</span><span class="sxs-lookup"><span data-stu-id="e1adc-131">After the **Identity** phase of the foundation infrastructure is rolled out to users, many organizations deploy:</span></span>
  - <span data-ttu-id="e1adc-132">[OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) と統合された [Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="e1adc-132">[Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md) combined with [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span> <span data-ttu-id="e1adc-133">Microsoft 365 Apps for enterprise は、先進的な認証のセキュリティと最新の Microsoft Office クライアントのユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1adc-133">Microsoft 365 Apps for enterprise provides the security of modern authentication and the user experience of the latest Microsoft Office client.</span></span> <span data-ttu-id="e1adc-134">ユーザーの個人用ファイルを OneDrive に移行すると、インフラストラクチャが削減され、ホーム フォルダーとドライブをサポートする必要性が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="e1adc-134">The migration of user's personal files to OneDrive reduces infrastructure and the need to support home folders and drives.</span></span>
  - <span data-ttu-id="e1adc-135">[Exchange Online](exchangeonline-workload.md)。ユーザーはクラウド ベースのメールの使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1adc-135">[Exchange Online](exchangeonline-workload.md) so that users can begin using cloud-based email.</span></span>
- <span data-ttu-id="e1adc-136">厳しく規制されたデジタル資産をすぐにクラウドに保存する必要がない場合は、**情報保護**フェーズの前に [Microsoft Teams](teams-workload.md) と [SharePoint](sharepoint-online-onedrive-workload.md) をユーザー向けに展開します。</span><span class="sxs-lookup"><span data-stu-id="e1adc-136">If you don't have an immediate need for storing highly regulated digital assets in the cloud, deploy [Microsoft Teams](teams-workload.md) and [SharePoint](sharepoint-online-onedrive-workload.md) for your users prior to the **Information protection** phase.</span></span>

<span data-ttu-id="e1adc-137">ビジネス ニーズを満たすように、基盤インフラストラクチャの前提となるフェーズの設定について最適な順序と展開を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1adc-137">You must decide on how to best order and deploy the configuration of prerequisite phases of foundation infrastructure to meet your business needs.</span></span>

### <a name="best-practice"></a><span data-ttu-id="e1adc-138">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="e1adc-138">Best practice</span></span>

<span data-ttu-id="e1adc-139">ユーザーを何らかのワークロードまたはシナリオに参加させる前に、基盤インフラストラクチャの **ID** フェーズを展開しロールアウトすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="e1adc-139">We highly recommend that you deploy and roll out the **Identity** phase of the foundation infrastructure prior to onboarding your users to any workloads or scenarios.</span></span>

<span data-ttu-id="e1adc-140">**ID** フェーズでは、クラウド ベースの ID は、クラウド専用であるかオンプレミスの Active Directory Domain Services (AD DS) と同期されているかにかかわらず、認証とアクセスの管理のためにユーザーおよびコンピューター アカウントとグループを含むようになります。</span><span class="sxs-lookup"><span data-stu-id="e1adc-140">The **Identity** phase ensures that your cloud-based identity, whether cloud-only or synchronized with your on-premises Active Directory Domain Services (AD DS), contains the user and computer accounts and groups to manage authentication and access.</span></span> <span data-ttu-id="e1adc-141">Microsoft 365 クラウドに組織のデジタル資産を配置する前に、すべてのユーザーの強力な認証のほか管理者アカウントの強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1adc-141">Strong authentication for all your users along with strong protection of admin accounts is required before placing your organization's digital assets in the Microsoft 365 cloud.</span></span>

<span data-ttu-id="e1adc-142">全体的なパフォーマンスにとって基本的かつ非常に重要なことですが、Microsoft 365 のワークロードとサービスのパフォーマンスが時間と共に向上することを考慮すると、ユーザーをワークロードに参加させながら **ネットワーキング** フェーズのロールアウトを進行させることができます。</span><span class="sxs-lookup"><span data-stu-id="e1adc-142">Although foundational and very important to overall performance, the rollout of the **Networking** phase can be in progress while onboarding your users to workloads, with the understanding that Microsoft 365 workload and service performance will improve over time.</span></span> <span data-ttu-id="e1adc-143">これは特に複数の場所とエッジ デバイスとインターネット接続が混在する企業にあてはまります。</span><span class="sxs-lookup"><span data-stu-id="e1adc-143">This is especially true for enterprise organizations with multiple locations and a mixture of edge devices and Internet connections.</span></span>
