---
title: Microsoft 365 Enterprise を展開する
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 組織内で Microsoft 365 Enterprise を展開するのに使用できるリソースについて説明します。
ms.openlocfilehash: ba0dd4d8af9f647b5368fdaa55837d3fe482fb55
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869537"
---
# <a name="deploy-microsoft-365-enterprise"></a><span data-ttu-id="418b0-103">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="418b0-103">Deploy Microsoft 365 Enterprise</span></span>

<span data-ttu-id="418b0-104">Microsoft 365 Enterprise は、Office 365、Enterprise Mobility + Security (EMS)、Windows 10 Enterprise の組み合わせであり、次の特長があります。</span><span class="sxs-lookup"><span data-stu-id="418b0-104">Microsoft 365 Enterprise is a combination of Office 365, Enterprise Mobility + Security (EMS), and Windows 10 Enterprise that:</span></span> 

- <span data-ttu-id="418b0-105">インテリジェントなセキュリティを備えている。</span><span class="sxs-lookup"><span data-stu-id="418b0-105">Has intelligent security.</span></span>
- <span data-ttu-id="418b0-106">簡素化のため統合されている。</span><span class="sxs-lookup"><span data-stu-id="418b0-106">Is integrated for simplicity.</span></span>
- <span data-ttu-id="418b0-107">創造性を引き出す。</span><span class="sxs-lookup"><span data-stu-id="418b0-107">Unlocks creativity.</span></span>
- <span data-ttu-id="418b0-108">共同作業向けに構築されている。</span><span class="sxs-lookup"><span data-stu-id="418b0-108">Is built for teamwork.</span></span>

<span data-ttu-id="418b0-p101">上記の特長を実現するには、この 3 つの製品のライセンスを入手するだけでなく、これらの製品とその機能を特定の方法で展開します。このドキュメント セットでは、これらの製品とその機能の展開と、必要な正しい構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="418b0-p101">These benefits are not realized just by obtaining the licenses for these three products, but by deploying them and their features in a specific way. This documentation set guides you through that deployment and the correct and required configuration of these products and their features.</span></span>

<span data-ttu-id="418b0-111">Microsoft 365 Enterprise の展開は 2 つのフェーズで構成されています。</span><span class="sxs-lookup"><span data-stu-id="418b0-111">There are two main phases to deploying Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="418b0-112">最初に、組み込みセキュリティと管理の簡素化のための統合で必要な[基礎インフラストラクチャ](deploy-foundation-infrastructure.md)を展開します。これにより、クライアント ソフトウェアが最新の生産性およびセキュリティ機能拡張で更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="418b0-112">First, deploy the required [foundation infrastructure](deploy-foundation-infrastructure.md) for built-in security and integration for simplified management, which makes it easier to ensure your client software is updated with the latest productivity and security enhancements.</span></span>
2. <span data-ttu-id="418b0-113">次に、基礎インフラストラクチャにオプションの[ワークロードとシナリオ](deploy-workloads.md)を展開します。これにより、組織内で創造性が引き出され、共同作業が可能になります。</span><span class="sxs-lookup"><span data-stu-id="418b0-113">Next, deploy a set of optional [workloads and scenarios](deploy-workloads.md) on top of the foundation infrastructure, to unlock creativity and teamwork in your organization.</span></span>

<span data-ttu-id="418b0-114">次の図に、基礎インフラストラクチャとワークロードやシナリオとの関係、およびこの内容の進み方を示します。</span><span class="sxs-lookup"><span data-stu-id="418b0-114">The following figure shows the relationship between the foundation infrastructure and the workloads and scenarios and your path through the content.</span></span>

![](./media/deploy-microsoft-365-enterprise/m365-deploy-content-arch.png)

<span data-ttu-id="418b0-115">セキュリティは、基礎インフラストラクチャのすべてのフェーズに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="418b0-115">Security is built into all phases of the foundation infrastructure.</span></span>

## <a name="fasttrack"></a><span data-ttu-id="418b0-116">FastTrack</span><span class="sxs-lookup"><span data-stu-id="418b0-116">FastTrack</span></span>

<span data-ttu-id="418b0-p102">FastTrack は、サブスクリプションの一部として利用可能であり、Microsoft エンジニアがお客様のペースに合わせたクラウドへの移行を支援する継続的かつ反復的なサービスです。FastTrack では、必要に応じて追加サービスを提供する認定パートナーにアクセスできます。FastTrack はこれまでに 40,000 以上のお客様に対応しており、ROI の最大化、展開の迅速化、組織全体での採用の拡充を支援してきました。「[Microsoft 365 の FastTrack](https://fasttrack.microsoft.com/microsoft365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="418b0-p102">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

<span data-ttu-id="418b0-p103">FastTrack を利用して Microsoft 365 Enterprise を展開する場合は、基礎インフラストラクチャを展開およびセットアップする方法のガイダンスとして FastTrack「[Microsoft 365 展開アドバイザー](https://aka.ms/microsoft365setupguide)」を使用できます。このページにアクセスするため、Office 365 または Microsoft 365 テナントでグローバル管理者としてサインオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="418b0-p103">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="take-a-test-drive"></a><span data-ttu-id="418b0-123">体験版の使用</span><span class="sxs-lookup"><span data-stu-id="418b0-123">Take a test drive</span></span>

<span data-ttu-id="418b0-p104">運用として展開したり、特定のオプションを展開する前に、テスト ラボ ガイド (TLG) を使用して Microsoft 365 Enterprise を試せます。TLG は、モジュラー化されている規範となる記事で、試用版または有料のサブスクリプションを使用して簡略化されているものの代表的な環境で、インフラストラクチャや機能を構成する手順を説明しています。</span><span class="sxs-lookup"><span data-stu-id="418b0-p104">Play with Microsoft 365 Enterprise prior to production deployment or the deployment of specific options with Test Lab Guides (TLGs). TLGs are modular, prescriptive articles that step you through the configuration of infrastructure or a feature in a simplified but representative environment using trial or paid subscriptions.</span></span> 

<span data-ttu-id="418b0-126">TLG を使用すると、複雑な構成、ワークロード、エンド ツー エンドのシナリオの概念実証をデモンストレーション、カスタマイズ、ビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="418b0-126">With TLGs, you can demonstrate, customize, or build a proof of concept of a complex configuration, workload, or end-to-end scenario.</span></span>

<span data-ttu-id="418b0-127">詳細については、「[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。 </span><span class="sxs-lookup"><span data-stu-id="418b0-127">For more information, see [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

## <a name="how-customers-use-microsoft-365-enterprise"></a><span data-ttu-id="418b0-129">お客様の Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="418b0-129">How customers use Microsoft 365 Enterprise</span></span>

<span data-ttu-id="418b0-130">お客様がどのように Microsoft 365 Enterprise を完全かつインテリジェントなソリューションとして活用しているかをご紹介します。誰でも安全な環境でクリエイティブに共同作業が行えます。詳細は、以下のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="418b0-130">See these resources to learn how customers are using Microsoft 365 Enterprise as their complete, intelligent solution that empowers everyone to be creative and work together securely:</span></span>

- <span data-ttu-id="418b0-131">医療サービス</span><span class="sxs-lookup"><span data-stu-id="418b0-131">Health services</span></span>
  - [<span data-ttu-id="418b0-132">Lilly の構想は、社内外の共同作業によって技術革新と新薬の市場投入のスピード化が可能となる職場を実現させること</span><span class="sxs-lookup"><span data-stu-id="418b0-132">Lilly envisions a workplace where internal and external collaboration help enable innovation and accelerate time-to-market for new medicines</span></span>](https://aka.ms/Eli_CLS)
  - [<span data-ttu-id="418b0-133">医療技術の先進的企業が、クラウドでの糖尿病予防を促進</span><span class="sxs-lookup"><span data-stu-id="418b0-133">Healthcare technology innovator accelerates diabetes prevention in the cloud </span></span>](https://aka.ms/Soleracasestudy)
  - [<span data-ttu-id="418b0-134">Adventist Health System の Microsoft 365 を使用した医療提供の拡大</span><span class="sxs-lookup"><span data-stu-id="418b0-134">Adventist Health System is enhancing healthcare delivery using Microsoft 365</span></span>](https://aka.ms/adventisthealth)
  - [<span data-ttu-id="418b0-135">Abrona の Microsoft 365 を使用した GDPR への対応と生産性の向上</span><span class="sxs-lookup"><span data-stu-id="418b0-135">Abrona accelerates GDPR compliance and increases productivity with Microsoft 365</span></span>](https://aka.ms/Abrona)
  - [<span data-ttu-id="418b0-136">Microsoft 365 のインテリジェントなビジネス ツールを使用した、Centra の企業変革および看護ケアの質の向上</span><span class="sxs-lookup"><span data-stu-id="418b0-136">Centra embraces transformation, improves patient care with Microsoft 365 intelligent business tools</span></span>](https://aka.ms/Centra_Health)
  - [<span data-ttu-id="418b0-137">Advocate Aurora Health は、患者の生活向上を目標とし、Microsoft の医療に関する共同ソリューションを活用してコラボレーションを強化</span><span class="sxs-lookup"><span data-stu-id="418b0-137">Advocate Aurora Health helps patients live well using Microsoft care coordination solution to enhance collaboration</span></span>](https://aka.ms/Advocate_)
- <span data-ttu-id="418b0-138">金融サービス</span><span class="sxs-lookup"><span data-stu-id="418b0-138">Financial services</span></span>
  - [<span data-ttu-id="418b0-139">TD Bank では従業員が Office 365 および Windows 10 の支援技術を活用</span><span class="sxs-lookup"><span data-stu-id="418b0-139">TD Bank empowers employees with assistive technology in Office 365 and Windows 10</span></span>](https://aka.ms/tdbankgroup)
  - [<span data-ttu-id="418b0-140">家族の納税準備に一体型のソリューションを適用し、ビジネスの成長もサポート</span><span class="sxs-lookup"><span data-stu-id="418b0-140">Family tax preparation startup chooses all-in-one solution to help grow business</span></span>](https://aka.ms/SOSCaseStudy)
- <span data-ttu-id="418b0-141">運輸</span><span class="sxs-lookup"><span data-stu-id="418b0-141">Transportation</span></span>
  - [<span data-ttu-id="418b0-142">Qantas は、カスタマー エクスペリエンスの向上につながるよう、Microsoft 365 を活用して従業員が最善の業務を行えるようにサポート</span><span class="sxs-lookup"><span data-stu-id="418b0-142">Qantas empowers employees to do their best work with Microsoft 365, enhancing customer experience</span></span>](https://aka.ms/Qantas_CS)
  - [<span data-ttu-id="418b0-143">Amtrak は、Microsoft 365 を活用してスケジュール前倒しで自社の輸送業務を運用</span><span class="sxs-lookup"><span data-stu-id="418b0-143">Amtrak keeps its mobile enterprise running ahead of schedule with Microsoft 365</span></span>](https://aka.ms/Amtrak_)
- <span data-ttu-id="418b0-144">製造</span><span class="sxs-lookup"><span data-stu-id="418b0-144">Manufacturing</span></span>
  - [<span data-ttu-id="418b0-145">製鉄会社がクラウドで、ハードウェア コストの削減、IT の効率化、モバイルによる生産性向上を実現</span><span class="sxs-lookup"><span data-stu-id="418b0-145">Steel company eliminates hardware costs, streamlines IT, and gains mobile productivity in the cloud</span></span>](https://aka.ms/Steeledalecasestudy)
  - [<span data-ttu-id="418b0-146">刺繍機のサプライヤーがクラウドベースのサービスでビジネスを強化し、零細企業の間で注目の的に</span><span class="sxs-lookup"><span data-stu-id="418b0-146">Embroidery equipment supplier empowers its business with cloud-based services, spreads word to other small businesses</span></span>](https://aka.ms/PriorityLLCCaseStudy)
  - [<span data-ttu-id="418b0-147">障碍を持つ従業員にできること。ある父子のビジネスによって世界に示される</span><span class="sxs-lookup"><span data-stu-id="418b0-147">Father and son business shows the world what employees with disabilities can achieve</span></span>](https://aka.ms/JCSCaseStudy)
  - [<span data-ttu-id="418b0-148">あるココナッツの会社は、コラボレーション ツールの最新化により、流動性、測定基準設定、生産性の向上を実現</span><span class="sxs-lookup"><span data-stu-id="418b0-148">Coconut company gains improved mobility, better metrics, and increased productivity by modernizing collaboration tools</span></span>](https://aka.ms/SilvermillCS)
  - [<span data-ttu-id="418b0-149">成長が著しい、ある日本の革新的企業では、Microsoft 365 Business で、将来に向けた組織の柔軟性とセキュリティ強化の方針を明確化</span><span class="sxs-lookup"><span data-stu-id="418b0-149">Thriving Japanese innovator finds future-proof flexibility and enhanced security with Microsoft 365 Business</span></span>](https://aka.ms/DreamFactoryCaseStudy)
- <span data-ttu-id="418b0-150">エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="418b0-150">Engineering</span></span>
   - [<span data-ttu-id="418b0-151">モバイル コラボレーション ツールでビジネスを加速させる Cadence</span><span class="sxs-lookup"><span data-stu-id="418b0-151">Cadence increases the pace of business with mobile collaboration tools</span></span>](https://customers.microsoft.com/story/cadence-partner-professional-services-microsoft-365)
- <span data-ttu-id="418b0-152">専門的サービス</span><span class="sxs-lookup"><span data-stu-id="418b0-152">Professional services</span></span>
  - [<span data-ttu-id="418b0-153">ビジネスおよび不動産専門の法律事務所が包括的なクラウドベースのプラットフォームでの事業拡大をサポート</span><span class="sxs-lookup"><span data-stu-id="418b0-153">Boutique business and real estate law firm supports expansion with comprehensive cloud-based platform </span></span>](https://aka.ms/Lieserskaffcasestudy)
  - [<span data-ttu-id="418b0-154">スポーツ関連テクノロジ企業の、バイオフィードバックおよび分析を基にした運動選手の能力向上への取り組み</span><span class="sxs-lookup"><span data-stu-id="418b0-154">Sports technology company helps athletes reach their peak through biofeedback and analytics </span></span>](https://aka.ms/KMOTIONCasestudy)
  - [<span data-ttu-id="418b0-155">デジタル改革とクラウドにより事業団体が成長し、事業関係者への貢献度も拡大</span><span class="sxs-lookup"><span data-stu-id="418b0-155">Digital transformation and the cloud empower business association to serve its members better </span></span>](https://aka.ms/AIMCS)
- <span data-ttu-id="418b0-156">エネルギー サービス</span><span class="sxs-lookup"><span data-stu-id="418b0-156">Energy services</span></span>
  - [<span data-ttu-id="418b0-157">Microsoft 365 を使用した Schlumberger のチームワークのグローバル展開</span><span class="sxs-lookup"><span data-stu-id="418b0-157">Schlumberger refines global teamwork with Microsoft 365</span></span>](https://aka.ms/Schlumberger_)
- <span data-ttu-id="418b0-158">建築</span><span class="sxs-lookup"><span data-stu-id="418b0-158">Construction</span></span>
  - [<span data-ttu-id="418b0-159">Microsoft 365 の共同作業機能を活用したデータ セキュリティ ソリューションを契約業務全般に適用</span><span class="sxs-lookup"><span data-stu-id="418b0-159">Search for data security solution unearths collaborative capabilities of Microsoft 365 at general contracting company</span></span>](https://aka.ms/Transbluecasestudy)
- <span data-ttu-id="418b0-160">コンサルティング</span><span class="sxs-lookup"><span data-stu-id="418b0-160">Consulting</span></span>
  - [<span data-ttu-id="418b0-161">ERM は、Microsoft 365 で、より持続可能な未来の実現に貢献</span><span class="sxs-lookup"><span data-stu-id="418b0-161">ERM contributes to a more sustainable future with Microsoft 365</span></span>](https://aka.ms/ERM_CS)
- <span data-ttu-id="418b0-162">非営利</span><span class="sxs-lookup"><span data-stu-id="418b0-162">Non-profit</span></span>
  - [<span data-ttu-id="418b0-163">クラウドへの移行で、セキュリティ、モビリティ、コラボレーションが向上し、非営利的な 500,000 ドルの節約が可能に</span><span class="sxs-lookup"><span data-stu-id="418b0-163">Move to the cloud saves nonprofit $500,000 while improving security, mobility, and collaboration </span></span>](https://aka.ms/MOWCaseStudy)
  
## <a name="how-microsoft-uses-microsoft-365-enterprise"></a><span data-ttu-id="418b0-164">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="418b0-164">How Microsoft uses Microsoft 365 Enterprise</span></span>

<span data-ttu-id="418b0-165">Microsoft IT の内側を垣間見て、どのように Microsoft 365 Enterprise を展開して、どのように Microsoft の従業員が日常業務に使用しているかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="418b0-165">Take a peek inside Microsoft IT and learn how they deployed Microsoft 365 Enterprise and how Microsoft employees use it every day.</span></span>

### <a name="networking"></a><span data-ttu-id="418b0-166">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="418b0-166">Networking</span></span>

- [<span data-ttu-id="418b0-167">Microsoft Office 365 のネットワーク パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="418b0-167">Optimizing network performance for Microsoft Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)

### <a name="identity"></a><span data-ttu-id="418b0-168">ID</span><span class="sxs-lookup"><span data-stu-id="418b0-168">Identity</span></span>

- [<span data-ttu-id="418b0-169">Microsoft でのユーザー ID の管理とアクセスの保護</span><span class="sxs-lookup"><span data-stu-id="418b0-169">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="418b0-170">アクセス許可を昇格するために、Azure AD Privileged Identity Management を使用する</span><span class="sxs-lookup"><span data-stu-id="418b0-170">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

### <a name="windows-10-enterprise"></a><span data-ttu-id="418b0-171">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="418b0-171">Windows 10 Enterprise</span></span>

- [<span data-ttu-id="418b0-172">Windows 10 をシームレスに展開するための組織の準備</span><span class="sxs-lookup"><span data-stu-id="418b0-172">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="418b0-173">Microsoft では、サービスとして Windows を使用</span><span class="sxs-lookup"><span data-stu-id="418b0-173">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="418b0-174">Microsoft における、Windows 10 のインプレース アップグレードとしての展開方法</span><span class="sxs-lookup"><span data-stu-id="418b0-174">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="418b0-175">Windows Hello for Business を使用した、強力なユーザー認証の実装</span><span class="sxs-lookup"><span data-stu-id="418b0-175">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="418b0-176">[Windows 10 の展開: Microsoft の IT 担当者からのヒント](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="418b0-176">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="418b0-177">Windows Defender ATP により高度な脅威の検出が可能</span><span class="sxs-lookup"><span data-stu-id="418b0-177">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="418b0-178">[Windows Defender および Windows Defender ATP を使用した、現代の企業のセキュリティ保護](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="418b0-178">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

### <a name="office-365-proplus"></a><span data-ttu-id="418b0-179">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="418b0-179">Office 365 ProPlus</span></span>

- [<span data-ttu-id="418b0-180">Office 365 ProPlus 2016 をシームレスに展開するための組織の準備</span><span class="sxs-lookup"><span data-stu-id="418b0-180">Preparing your organization for a seamless Office 365 ProPlus 2016 deployment</span></span>](https://www.microsoft.com/itshowcase/Office365adoption)
- [<span data-ttu-id="418b0-181">Microsoft Office 365 ProPlus の展開と更新</span><span class="sxs-lookup"><span data-stu-id="418b0-181">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- <span data-ttu-id="418b0-182">[Microsoft Office 365 ProPlus の展開を支援するオートメーションと更新プログラム チャネル](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="418b0-182">[Automation and update channels help deploy Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (video)</span></span>

### <a name="mobility-and-device-management"></a><span data-ttu-id="418b0-183">モビリティおよびデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="418b0-183">Mobility and device management</span></span>

- [<span data-ttu-id="418b0-184">Enterprise Mobility + Security による最新のモバイル生産性の管理</span><span class="sxs-lookup"><span data-stu-id="418b0-184">Managing modern mobile productivity with Enterprise Mobility + Security</span></span>](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [<span data-ttu-id="418b0-185">Microsoft Intune を使用して Windows 10 デバイスでの作業につながる</span><span class="sxs-lookup"><span data-stu-id="418b0-185">Connecting to work on your Windows 10 device with Microsoft Intune</span></span>](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [<span data-ttu-id="418b0-186">Microsoft での iOS、OS X、Android デバイスによる業務効率化を可能にする</span><span class="sxs-lookup"><span data-stu-id="418b0-186">Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

### <a name="security-and-information-protection"></a><span data-ttu-id="418b0-187">セキュリティおよび情報保護</span><span class="sxs-lookup"><span data-stu-id="418b0-187">Security and information protection</span></span>

- [<span data-ttu-id="418b0-188">Azure Information Protection でクラウドのファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="418b0-188">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="418b0-189">Microsoft は脅威からの保護、脅威の検出、脅威への対応に脅威インテリジェンスを使用する</span><span class="sxs-lookup"><span data-stu-id="418b0-189">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="418b0-190">Microsoft の Office 365 を使用したフィッシング阻止の試み</span><span class="sxs-lookup"><span data-stu-id="418b0-190">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

### <a name="microsoft-teams"></a><span data-ttu-id="418b0-191">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="418b0-191">Microsoft Teams</span></span>

- [<span data-ttu-id="418b0-192">Microsoft Teams の展開により、コラボレーションが効率化し、チームワークが向上する</span><span class="sxs-lookup"><span data-stu-id="418b0-192">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="418b0-193">Microsoft Teams は Microsoft の最新の職場でのコラボレーションを向上させる</span><span class="sxs-lookup"><span data-stu-id="418b0-193">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

### <a name="data-migration"></a><span data-ttu-id="418b0-194">データ移行</span><span class="sxs-lookup"><span data-stu-id="418b0-194">Data migration</span></span>

- [<span data-ttu-id="418b0-195">Microsoft では 150,000 のメールボックスを Exchange Online に移行</span><span class="sxs-lookup"><span data-stu-id="418b0-195">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="418b0-196">SharePoint からクラウドへ: Microsoft が実施した移行方法</span><span class="sxs-lookup"><span data-stu-id="418b0-196">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="418b0-197">Contoso Corporation の Microsoft 365 Enterprise 展開方法</span><span class="sxs-lookup"><span data-stu-id="418b0-197">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="418b0-p105">架空の企業、Contoso Corporation は、パリに本社を置く代表的な世界規模の製造業の複合企業です。[Contoso 社が Microsoft 365 Enterprise を展開](contoso-case-study.md)して、ネットワーク、ID、Windows 10 Enterprise、Office 365 ProPlus、モバイル デバイス管理、情報の保護、セキュリティに関する主な設計上の決定と実装の詳細に対応した方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="418b0-p105">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris. See how [Contoso deployed Microsoft 365 Enterprise](contoso-case-study.md) and addressed major design decisions and implementation details for networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, and security.</span></span> 

![](./media/contoso-overview/contoso-icon.png)

## <a name="additional-microsoft-365-solutions"></a><span data-ttu-id="418b0-200">その他の Microsoft 365 ソリューション</span><span class="sxs-lookup"><span data-stu-id="418b0-200">Additional Microsoft 365 solutions</span></span>

- [<span data-ttu-id="418b0-201">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="418b0-201">Microsoft 365 Business</span></span>](https://docs.microsoft.com/microsoft-365/business/)
 
  <span data-ttu-id="418b0-202">小規模および中規模の企業 (SMB) 向けに、Office 365 の優れた生産性やコラボレーション機能と、ビジネス データを保護するためのデバイス管理およびセキュリティ ソリューションを統合します。</span><span class="sxs-lookup"><span data-stu-id="418b0-202">Bring together the best-in-class productivity and collaboration capabilities of Office 365 with device management and security solutions to safeguard business data for small and midsize businesses (SMB).</span></span>

- [<span data-ttu-id="418b0-203">Microsoft 365 Education</span><span class="sxs-lookup"><span data-stu-id="418b0-203">Microsoft 365 Education</span></span>](https://docs.microsoft.com/education)
 
  <span data-ttu-id="418b0-204">手ごろな価格の教育用に構築された単一ソリューションで、教育者が創造力を発揮し、チームワークを促進し、シンプルかつ安全な操作性を実現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="418b0-204">Empower educators to unlock creativity, promote teamwork, and provide a simple and safe experience in a single, affordable solution built for education.</span></span>

## <a name="next-step"></a><span data-ttu-id="418b0-205">次の手順</span><span class="sxs-lookup"><span data-stu-id="418b0-205">Next step</span></span>

<span data-ttu-id="418b0-206">[FastTrack](https://fasttrack.microsoft.com/microsoft365)を使用するか、または[基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に着手します。</span><span class="sxs-lookup"><span data-stu-id="418b0-206">Use [FastTrack](https://fasttrack.microsoft.com/microsoft365) or get started with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
