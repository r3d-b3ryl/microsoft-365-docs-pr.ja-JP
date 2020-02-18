---
title: Contoso 社での Office 365 ProPlus の展開
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Office 365 ProPlus を展開する方法について説明します。
ms.openlocfilehash: 45c9933ea04632b255acfa1062ae7ecaf9810030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068321"
---
# <a name="office-365-proplus-deployment-for-contoso"></a><span data-ttu-id="aeb80-103">Contoso 社での Office 365 ProPlus の展開</span><span class="sxs-lookup"><span data-stu-id="aeb80-103">Office 365 ProPlus deployment for Contoso</span></span>

<span data-ttu-id="aeb80-p101">Contoso 社では自社の PC を Windows 10 Enterprise と Office 365 ProPlus にアップグレードして、これまで以上に効果的な共同作業、セキュリティの向上、および最新のデスクトップ エクスペリエンスを実現しました。インフラストラクチャとビジネス ニーズを評価した後、Contoso 社は展開に向けて、以下の重要な要件を特定しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p101">Contoso upgraded their PCs to Windows 10 Enterprise and Office 365 ProPlus to enable more effective collaboration, better security, and a more modern desktop experience. After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="aeb80-106">すべての PC で Office 365 ProPlus を実行します</span><span class="sxs-lookup"><span data-stu-id="aeb80-106">All PCs should run Office 365 ProPlus</span></span>
- <span data-ttu-id="aeb80-107">可能な場合は、既存の管理ツールとインフラストラクチャを使用します</span><span class="sxs-lookup"><span data-stu-id="aeb80-107">Deployment should use existing management tools and infrastructure when possible</span></span>
- <span data-ttu-id="aeb80-108">展開はエンドユーザーのデバイス上で複数の言語と既存のアーキテクチャをサポートする必要があります</span><span class="sxs-lookup"><span data-stu-id="aeb80-108">Deployment must support multiple languages and existing architectures on end-user devices</span></span>
- <span data-ttu-id="aeb80-109">PC は、IT 管理コストとエンドユーザーに与える影響を最小限に抑えながら、安全で最新の状態に保ちます</span><span class="sxs-lookup"><span data-stu-id="aeb80-109">PCs should stay up-to-date and secure with minimal IT administrative costs and with minimal impact to end-users</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="aeb80-110">展開ツール</span><span class="sxs-lookup"><span data-stu-id="aeb80-110">Deployment tools</span></span>

<span data-ttu-id="aeb80-p102">Contoso 社では自社の要件に基づいて、Configuration Manager (Current Branch) を使用した Windows 10 Enterprise と Office 365 ProPlus の展開を選択しました。Configuration Manager は大規模環境向けに拡張され、インストール、更新、設定に対する幅広い管理が可能です。また、Office の展開と管理をより簡単で効率的にするために、以下の機能も組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p102">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Office 365 ProPlus with Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="aeb80-114">ピア キャッシュ。遠隔地のデバイスに展開する際にネットワーク キャパシティが限られている場合に役立ちます</span><span class="sxs-lookup"><span data-stu-id="aeb80-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations</span></span>
- <span data-ttu-id="aeb80-115">Office クライアント管理ダッシュボード。Office の展開と更新の監視を容易にし、管理者が最新の展開と管理機能にアクセスできるようにします</span><span class="sxs-lookup"><span data-stu-id="aeb80-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features</span></span>
- <span data-ttu-id="aeb80-116">高度な言語パックの展開。オペレーティング システムと同じ言語の自動展開を含みます</span><span class="sxs-lookup"><span data-stu-id="aeb80-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system</span></span>
- <span data-ttu-id="aeb80-117">展開時にクライアントから既存のバージョンの Office を削除する方法を完全にサポートし、簡単に使用できるようにします</span><span class="sxs-lookup"><span data-stu-id="aeb80-117">Fully supported and easy-to-use method of removing existing versions of Office from a client during deployment</span></span>

<span data-ttu-id="aeb80-118">Configuration Manager のほかに、Contoso 社では[準備ツールキット](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro)も使用しました。これは、Office マクロとアドインとの互換性の問題を評価する Microsoft の無料ツールです。</span><span class="sxs-lookup"><span data-stu-id="aeb80-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-the-deployment-and-updates"></a><span data-ttu-id="aeb80-119">展開および更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="aeb80-119">Managing the deployment and updates</span></span>

<span data-ttu-id="aeb80-p103">Office 365 ProPlus には、サービスとしての Office という新しいリリース モデルがあります。このサービス モデルにより、容易に新機能を最新のものにできますが、新リリースの展開やテストの方法に関する IT 部門のアプローチに対して、頻繁に変更が求められることになります。互換性の問題を最小限に抑え、コンピューターの最新状態を維持するため、Contoso 社では Windows と Office を次の 2 段階で展開しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p103">Office 365 ProPlus has a new release model: Office as a service. The service model makes it easy to stay up to date with new features, but often requires a change in approach for IT departments in how new releases are deployed and tested. To minimize any compatibility issues and to ensure their computers stayed up to date, Contoso deployed Windows and Office in two stages:</span></span> 

- <span data-ttu-id="aeb80-p104">最初の段階では、組織全体にわたって、少数の代表的なデバイスに Office 365 ProPlus を展開しました。このパイロット グループは、Office 365 ProPlus でのアプリ、アドイン、およびハードウェアのテストに使用されました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p104">For the first stage, they deployed Office 365 ProPlus to a small set of representative devices across the organization. This pilot group was used to test apps, add-ins, and hardware with Office 365 ProPlus</span></span>
- <span data-ttu-id="aeb80-125">4 か月後、パイロット グループのアプリ、アドイン、ハードウェアに関する重要な問題を解決した後、Contoso 社では Office 365 ProPlus を組織内の残り (広範グループ) のデバイスに展開しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-125">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Office 365 ProPlus to the rest of the devices in the organization (the broad group).</span></span> 

<span data-ttu-id="aeb80-p105">Configuration Manager を使用して Office の更新を管理する代わりに、Contoso 社ではクラウドからの自動更新を有効にしました。クラウドベースの更新は、デバイスを最新の状態に保ちながら、管理上のオーバーヘッドを削減しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p105">Instead of managing updates to Office with Configuration Manager, Contoso enabled automatic updates from the cloud. Cloud-based updates reduced their administrative overhead while ensuring the devices stayed up to date.</span></span> 

<span data-ttu-id="aeb80-p106">Contoso 社では Office の展開に使用した 2 段階アプローチ、つまりパイロット グループ内のデバイスが組織の残り (広範グループ) のデバイスよりも 4 か月早く機能の更新を受け取る方法と同じアプローチを機能の更新にも使用しました。これを Office で可能にするために、Contoso 社では 2 つの推奨される[更新チャネル](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)を使用しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p106">Contoso followed the same two-stage approach for feature updates that they used for deploying Office: devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group). To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus):</span></span> 

- <span data-ttu-id="aeb80-130">パイロット グループ用の半期チャネル (対象指定)</span><span class="sxs-lookup"><span data-stu-id="aeb80-130">Semi-Annual Channel (Targeted) for updates to the pilot group</span></span> 
- <span data-ttu-id="aeb80-131">広範グループ用の半期チャネル。</span><span class="sxs-lookup"><span data-stu-id="aeb80-131">Semi-Annual Channel for updates to the broad group.</span></span> 

<span data-ttu-id="aeb80-132">半期チャネル (対象指定) は半期チャネルよりも 4 か月早いバージョンの Office 365 ProPlus をリリースするため、Contoso 社は更新プログラムを管理する必要なしに、それらを検証する時間があります。</span><span class="sxs-lookup"><span data-stu-id="aeb80-132">Because the Semi-Annual (Targeted) Channel releases a version of Office 365 ProPlus four months earlier than the Semi-Annual Channel, Contoso has time to validate the updates without having to manage them.</span></span> 

## <a name="deployment-process"></a><span data-ttu-id="aeb80-133">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="aeb80-133">Deployment process</span></span>

<span data-ttu-id="aeb80-134">Office の展開を完了するために、Contoso 社では Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-134">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="aeb80-135">展開の前に準備ツールキットを使用して、アプリと Office アドインをテストし、Office 365 ProPlus との互換性を評価しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-135">Before deploying, they used the Readiness Toolkit to test their apps and Office add-ins to assess their compatibility with Office 365 ProPlus.</span></span>
2. <span data-ttu-id="aeb80-136">Configuration Manager では、Contoso 社はクライアント デバイス上でピア キャッシュを有効にしました。これは遠隔地にあるクライアントのデバイスに展開する際にネットワーク キャパシティが限られている場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="aeb80-136">In Configuration Manager, Contoso enabled peer cache on their client devices, which helped with limited network capacity when deploying to client devices in remote locations.</span></span> 
3. <span data-ttu-id="aeb80-p107">Configuration Manager で、パイロット グループと広範グループの 2 つの展開グループをデバイス コレクションとして定義しました。パイロットグループ (組織全体にわたる少数の代表的なデバイスを含む) は、Windows 10 Enterprise と Office 365 ProPlus を使用してアプリ、アドイン、およびハードウェアの追加テストを行うために使用されました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p107">They defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group. The pilot group, which included a small set of representative devices across the organization, was used to do additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Office 365 ProPlus.</span></span> 
4. <span data-ttu-id="aeb80-p108">Office クライアント管理ダッシュボードと Office 365 インストーラー ウィザード (いずれもConfiguration Manager コンソールの一部) を使用して、Office の展開パッケージを作成しました。2 つの Office 365 ProPlus パッケージを作成しました (1 つは半期チャネル (対象指定) のパイロット グループ用、1 つは半期チャネルの広範グループ用)。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p108">They created deployment packages for Office using the Office Client Management dashboard and the Office 365 Installer wizard, both of which are part of the Configuration Manager console. They built two Office 365 ProPlus packages, one for the pilot group on the Semi-Annual Channel (Targeted) and one for the broad group on the Semi-Annual Channel.</span></span> 
5. <span data-ttu-id="aeb80-p109">各 Office パッケージの一部として、英語、フランス語、ドイツ語の言語パックが含まれていました。デバイスに、Office パッケージに含まれていない言語が必要な場合は、Office コンテンツ配信ネットワーク (CDN) から自動的にダウンロードされました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-p109">As part of each Office package, they included English, French, and German Language packs. If a device required a language not included in the Office package, it was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
6. <span data-ttu-id="aeb80-143">Office パッケージの組み込み機能を使用して、Office 365 ProPlus のインストール前に既存の MSI バージョンの Office をすべて自動的に削除しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-143">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Office 365 ProPlus.</span></span>
7. <span data-ttu-id="aeb80-144">Configuration Manager では、Windows と Office パッケージをネットワーク上の配布ポイントに展開し、Configuration Manager の展開タスク シーケンスを実行して、パイロットの Office 365 ProPlus パッケージをパイロット グループに展開しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-144">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network, and then ran the Configuration Manager deployment task sequences to deploy the pilot Office 365 ProPlus package to the pilot group.</span></span>
8. <span data-ttu-id="aeb80-145">パイロット グループとの互換性問題を解決した後、Contoso 社ではタスク シーケンスを実行して、さまざまな Office 365 ProPlus パッケージを広範囲のグループに展開しました。</span><span class="sxs-lookup"><span data-stu-id="aeb80-145">After addressing any compatibility issues with the pilot group, Contoso ran the task sequences to deploy the broad Office 365 ProPlus package to the broad group.</span></span>

<span data-ttu-id="aeb80-146">Contoso 社ではクラウドからデバイスを自動的に更新するよう選択しているため、Configuration Manger でプロセスを管理する必要はありませんでした。</span><span class="sxs-lookup"><span data-stu-id="aeb80-146">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="aeb80-147">デバイスは、最初の展開の一部として定義された更新チャネルに基づいて、直接クラウドから自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="aeb80-147">Their devices are automatically updated directly from the cloud-based on the update channel that was defined as part of the initial deployment.</span></span> 

<span data-ttu-id="aeb80-148">次に Contoso 社の Office 365 ProPlus のインストール、および進行中の更新プログラムの展開アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="aeb80-148">Here is Contoso’s Office 365 ProPlus installation and ongoing updates deployment architecture.</span></span>

![Contoso 社の Office 365 ProPlus の展開インフラストラクチャ](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="aeb80-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="aeb80-150">Next step</span></span>

<span data-ttu-id="aeb80-151">Contoso 社が Microsoft 365 Enterprise で Microsoft Intune を使用して、組織全体で実行されるデバイスとアプリを管理する方法について[説明](contoso-mdm.md)します。</span><span class="sxs-lookup"><span data-stu-id="aeb80-151">[Learn](contoso-mdm.md) how Contoso is using Microsoft Intune in Microsoft 365 Enterprise to manage its devices and the apps that run on them across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="aeb80-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="aeb80-152">See also</span></span>

[<span data-ttu-id="aeb80-153">Microsoft 365 Enterprise 向けの Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="aeb80-153">Office 365 ProPlus for Microsoft 365 Enterprise</span></span>](office365proplus-infrastructure.md)

[<span data-ttu-id="aeb80-154">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="aeb80-154">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="aeb80-155">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="aeb80-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
