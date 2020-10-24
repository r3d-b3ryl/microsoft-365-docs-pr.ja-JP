---
title: Contoso 社の Microsoft 365 Apps for enterprise の展開
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Microsoft 365 Apps for enterprise を展開する方法について説明します。
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754358"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a><span data-ttu-id="d7116-103">Contoso 社の Microsoft 365 Apps for enterprise の展開</span><span class="sxs-lookup"><span data-stu-id="d7116-103">Microsoft 365 Apps for enterprise deployment for Contoso</span></span>

<span data-ttu-id="d7116-p101">Contoso 社は Pc を Windows 10 Enterprise にアップグレードし、エンタープライズ向け Microsoft 365 アプリを使用することで、より効果的なコラボレーション、セキュリティの向上、およびよりモダンなデスクトップ環境を実現しています。インフラストラクチャとビジネスのニーズを評価した後、Contoso は展開に関して次の主要な要件を特定しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-p101">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience. After they assessed their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="d7116-106">すべての Pc で、Microsoft 365 Apps for enterprise を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7116-106">All PCs should run Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="d7116-107">展開では、可能な場合は既存の管理ツールおよびインフラストラクチャを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7116-107">Deployment should use existing management tools and infrastructure when possible.</span></span>
- <span data-ttu-id="d7116-108">展開では、ユーザーのデバイス上に複数の言語と既存のアーキテクチャがサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7116-108">Deployment must support multiple languages and existing architectures on users' devices.</span></span>
- <span data-ttu-id="d7116-109">Pc は、最小限の IT 管理コストとユーザーへの影響を最小限に抑えて、最新の状態に保たれます。</span><span class="sxs-lookup"><span data-stu-id="d7116-109">PCs should stay up-to-date and secure with minimal IT administrative costs and minimal impact to users.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="d7116-110">展開ツール</span><span class="sxs-lookup"><span data-stu-id="d7116-110">Deployment tools</span></span>

<span data-ttu-id="d7116-p102">Contoso 社は、要件に基づいて、構成マネージャー (Current Branch) を使用して、Windows 10 Enterprise と Microsoft 365 Apps for enterprise を展開することを選択しました。構成マネージャーは大規模な環境に合わせて拡張され、インストール、更新、および設定を詳細に制御します。また、次のような Office をより簡単かつ効率的に展開および管理する機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d7116-p102">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise through Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="d7116-114">ピアキャッシュ。これは、リモートの場所にあるデバイスに展開するときに、制限されたネットワーク容量で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d7116-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations.</span></span>
- <span data-ttu-id="d7116-115">Office クライアント管理ダッシュボードを使用すると、Office の展開と更新の監視が容易になり、管理者は最新の展開および管理機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7116-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features.</span></span>
- <span data-ttu-id="d7116-116">インテリジェント言語パックの展開 (オペレーティングシステムと同じ言語の自動展開を含む)。</span><span class="sxs-lookup"><span data-stu-id="d7116-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system.</span></span>
- <span data-ttu-id="d7116-117">展開時にクライアントから既存のバージョンの Office を削除するための完全にサポートされた、使いやすい方法。</span><span class="sxs-lookup"><span data-stu-id="d7116-117">A fully supported and easy-to-use method of removing existing versions of Office from a client during deployment.</span></span>

<span data-ttu-id="d7116-118">構成マネージャーに加えて、Contoso 社は [office アドインと VBA の準備ツールキット](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)を使用して、Microsoft の無料ツールである office マクロやアドインとの互換性の問題を評価していました。</span><span class="sxs-lookup"><span data-stu-id="d7116-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit for Office add-ins and VBA](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-deployment-and-updates"></a><span data-ttu-id="d7116-119">展開と更新を管理する</span><span class="sxs-lookup"><span data-stu-id="d7116-119">Managing deployment and updates</span></span>

<span data-ttu-id="d7116-p103">Microsoft 365 enterprise 用アプリには、サービスとしての Office という新しいリリースモデルがあります。サービスモデルを使用すると、新機能に関する最新情報を簡単に入手できます。しかし、多くの場合、IT 部門が新しいリリースを展開してテストする方法を変更する必要があります。互換性の問題を最小限に抑え、コンピューターが最新の状態に保たれるようにするために、Contoso 社は Windows と Office を2段階で展開しています。</span><span class="sxs-lookup"><span data-stu-id="d7116-p103">Microsoft 365 Apps for enterprise has a new release model: Office as a service. The service model makes it easy to stay up to date with new features. But it often requires IT departments to change how they deploy and test new releases. To minimize compatibility issues and to ensure their computers stay up to date, Contoso deployed Windows and Office in two stages:</span></span>

- <span data-ttu-id="d7116-124">最初に、企業向けの Microsoft 365 アプリを組織全体の少数の代表的なデバイスに展開しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-124">First, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization.</span></span> <span data-ttu-id="d7116-125">このパイロットグループは、Microsoft 365 Apps for enterprise を使用してアプリ、アドイン、およびハードウェアをテストするために使用されました。</span><span class="sxs-lookup"><span data-stu-id="d7116-125">This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="d7116-126">4 か月後、パイロット グループのアプリ、アドイン、ハードウェアに関する重要な問題を解決した後、Contoso 社では Microsoft 365 Apps for enterprise を組織内の残り (広範グループ) のデバイスに展開しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-126">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Microsoft 365 Apps for enterprise to the rest of the devices in the organization (the broad group).</span></span>

<span data-ttu-id="d7116-127">構成マネージャーを使用して Office の更新プログラムを管理する代わりに、クラウドからの Contoso 社による自動更新を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7116-127">Instead of managing updates to Office by using Configuration Manager, Contoso enabled automatic updates from the cloud.</span></span> <span data-ttu-id="d7116-128">クラウドベースの更新プログラムは、デバイスを最新の状態に保つ一方で、管理上のオーバーヘッドを軽減します。</span><span class="sxs-lookup"><span data-stu-id="d7116-128">Cloud-based updates reduce administrative overhead while ensuring that devices stay up to date.</span></span>

<span data-ttu-id="d7116-129">Contoso 社は、Office の展開に使用した機能更新プログラムに対して同じ2段階のアプローチを採用しています。パイロットグループ received 機能の更新プログラムは、組織の他の部分 (広範なグループ) のデバイスよりも4か月早く更新されています。</span><span class="sxs-lookup"><span data-stu-id="d7116-129">Contoso followed the same two-stage approach for feature updates as they used for deploying Office: Devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group).</span></span> <span data-ttu-id="d7116-130">これを Office で可能にするために、Contoso 社では 2 つの推奨される[更新チャネル](https://docs.microsoft.com/DeployOffice/overview-update-channels)を使用しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-130">To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels):</span></span>

- <span data-ttu-id="d7116-131">パイロット グループへの更新向け半期エンタープライズ チャネル (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d7116-131">Semi-Annual Enterprise Channel (Preview) for updates to the pilot group</span></span>
- <span data-ttu-id="d7116-132">広範なグループに対する更新に対してエンタープライズチャネルを Semi-Annual</span><span class="sxs-lookup"><span data-stu-id="d7116-132">Semi-Annual Enterprise Channel for updates to the broad group</span></span>

<span data-ttu-id="d7116-133">エンタープライズ チャネル (プレビュー) は半期エンタープライズ チャネルよりも 4 か月早いバージョンの Microsoft 365 Apps for enterprise をリリースするため、Contoso 社は更新プログラムを管理する必要なしに、それらを検証する時間があります。</span><span class="sxs-lookup"><span data-stu-id="d7116-133">Because the Semi-Annual Enterprise Channel (Preview) releases a version of Microsoft 365 Apps for enterprise four months earlier than the Semi-Annual Enterprise Channel, Contoso has time to validate the updates without having to manage them.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="d7116-134">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="d7116-134">Deployment process</span></span>

<span data-ttu-id="d7116-135">Office の展開を完了するために、Contoso 社では Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-135">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="d7116-136">展開前に、Contoso 社は Office アドインと VBA の準備ツールキットを使用して、アプリと Office アドインをテストし、Microsoft 365 Apps for enterprise との互換性を評価していました。</span><span class="sxs-lookup"><span data-stu-id="d7116-136">Before deployment, Contoso used the Readiness Toolkit for Office add-in and VBA to test their apps and Office Add-ins to assess their compatibility with Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="d7116-137">構成マネージャーでは、クライアントデバイスのピアキャッシュを有効にします。これにより、リモートの場所にクライアントデバイスに展開する際にネットワークの容量が制限されます。</span><span class="sxs-lookup"><span data-stu-id="d7116-137">In Configuration Manager, they enabled peer cache on their client devices, which helps with limited network capacity when deploying to client devices in remote locations.</span></span> 
1. <span data-ttu-id="d7116-138">Contoso 社は、構成マネージャーでのデバイスコレクションとして、2つの展開グループを定義しています。パイロットグループと広範なグループ。</span><span class="sxs-lookup"><span data-stu-id="d7116-138">Contoso defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group.</span></span> <span data-ttu-id="d7116-139">パイロットグループには、組織全体の代表的なデバイスのセットが含まれていました。アプリ、アドイン、およびハードウェアの追加テストには、Windows 10 Enterprise および Microsoft 365 Apps for enterprise が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="d7116-139">The pilot group, which included a small set of representative devices across the organization, was used for additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="d7116-140">Office クライアント管理ダッシュボードと office 365 インストーラウィザードを使用して、Office の展開パッケージを作成しました。これは、Configuration Manager コンソールの一部です。</span><span class="sxs-lookup"><span data-stu-id="d7116-140">They created deployment packages for Office by using the Office Client Management dashboard and the Office 365 Installer wizard, which are both part of the Configuration Manager console.</span></span> <span data-ttu-id="d7116-141">エンタープライズパッケージ用に2つの Microsoft 365 アプリが構築されています。1つは Semi-Annual エンタープライズチャネル (プレビュー) のパイロットグループ用、もう1つは Semi-Annual エンタープライズチャネルの広範なグループ用です。</span><span class="sxs-lookup"><span data-stu-id="d7116-141">They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span></span>
2. <span data-ttu-id="d7116-142">各 Office パッケージには、英語、フランス語、ドイツ語の言語パックが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="d7116-142">Each Office package included English, French, and German Language packs.</span></span> <span data-ttu-id="d7116-143">デバイスに Office パッケージに含まれていない言語が必要な場合、その言語パックは Office コンテンツ配信ネットワーク (CDN) から自動的にダウンロードされていました。</span><span class="sxs-lookup"><span data-stu-id="d7116-143">If a device required a language that wasn't included in the Office package, that language pack was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
3. <span data-ttu-id="d7116-144">Office パッケージの組み込み機能を使用して、Microsoft 365 Apps for enterprise のインストール前に既存の MSI バージョンの Office をすべて自動的に削除しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-144">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Microsoft 365 Apps for enterprise.</span></span>
4. <span data-ttu-id="d7116-145">構成マネージャーでは、ネットワークを介して配布ポイントに Windows および Office パッケージを展開しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-145">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network.</span></span> <span data-ttu-id="d7116-146">その後、構成マネージャーの展開タスクシーケンスを実行して、パイロットグループにエンタープライズパッケージのパイロット Microsoft 365 アプリを展開しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-146">Then they ran the Configuration Manager deployment task sequences to deploy the pilot Microsoft 365 Apps for enterprise package to the pilot group.</span></span>
5. <span data-ttu-id="d7116-147">パイロットグループとの互換性の問題に対処した後、Contoso 社はタスクシーケンスを実行して、エンタープライズパッケージ用の Microsoft 365 アプリを広範なグループに展開しました。</span><span class="sxs-lookup"><span data-stu-id="d7116-147">After they addressed compatibility issues with the pilot group, Contoso ran the task sequences to deploy the Microsoft 365 Apps for enterprise package to the broad group.</span></span>

<span data-ttu-id="d7116-148">Contoso 社ではクラウドからデバイスを自動的に更新するよう選択しているため、Configuration Manger でプロセスを管理する必要はありませんでした。</span><span class="sxs-lookup"><span data-stu-id="d7116-148">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="d7116-149">これらのデバイスは、最初の展開で定義された更新プログラムチャネルで、クラウドベースから直接更新されます。</span><span class="sxs-lookup"><span data-stu-id="d7116-149">Their devices are automatically updated directly from the cloud-based on the update channel that was defined in the initial deployment.</span></span>

<span data-ttu-id="d7116-150">ここでは、Contoso Microsoft 365 Apps for enterprise のインストールと継続的な更新プログラムの展開アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d7116-150">Here is the Contoso Microsoft 365 Apps for enterprise installation and ongoing updates deployment architecture.</span></span>

![Microsoft 365 Apps for enterprise の Contoso 展開インフラストラクチャ](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="d7116-152">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d7116-152">Next step</span></span>

<span data-ttu-id="d7116-153">Contoso 社が microsoft 365 で microsoft [Intune を使用して](contoso-mdm.md) 、自社のデバイスと、組織全体で実行されるアプリを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7116-153">Learn how Contoso is [using Microsoft Intune](contoso-mdm.md) in Microsoft 365 for enterprise to manage its devices and the apps that they run across the organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7116-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7116-154">See also</span></span>

[<span data-ttu-id="d7116-155">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="d7116-155">Microsoft 365 Apps for enterprise</span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[<span data-ttu-id="d7116-156">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="d7116-156">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d7116-157">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="d7116-157">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
