---
title: Contoso 社の Windows 10 Enterprise 展開
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
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Windows 10 Enterprise の一括アップグレードを展開した方法について説明します。
ms.openlocfilehash: 7907bf64acce3af8b21459202cb6f5cbc1e9f990
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907688"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="e1fa7-103">Contoso 社の Windows 10 Enterprise 展開</span><span class="sxs-lookup"><span data-stu-id="e1fa7-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="e1fa7-104">エンタープライズ向け Microsoft 365 の広範な展開に先だって、contoso 社では Windows 互換の PC とデバイスが Windows 7 (10%)、Windows 8.1 (65%)、Windows 10 (25%)の混合を実行していた。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-104">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%).</span></span> <span data-ttu-id="e1fa7-105">Contoso 社は、高度なセキュリティを利用Windows 10 Enterprise、更新プログラムの自動展開による IT オーバーヘッドを削減するために、PC をアップグレードしたいと考えました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-105">Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="e1fa7-106">インフラストラクチャとビジネス ニーズを評価した後、Contoso 社は展開に向けて、以下の重要な要件を特定しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="e1fa7-107">できるだけ多くの PC やデバイスで Windows 10 Enterprise を実行する必要がある</span><span class="sxs-lookup"><span data-stu-id="e1fa7-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="e1fa7-108">一括アップグレードのロールアウトには、既存の Configuration Manager インフラストラクチャを活用する</span><span class="sxs-lookup"><span data-stu-id="e1fa7-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="e1fa7-109">Windows 10 Enterprise のどのバージョンを展開するかを制御し、更新プログラムはリングを介して行う</span><span class="sxs-lookup"><span data-stu-id="e1fa7-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="e1fa7-110">PC やデバイスは、IT 管理コストとエンドユーザーに与える影響を最小限に抑えつつ、最新の状態に保つ必要がある</span><span class="sxs-lookup"><span data-stu-id="e1fa7-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="e1fa7-111">最新とは、Contoso 社のビジネス ニーズを満たす Windows 10 Enterprise のサポート バージョンとして定義されます。これは、すべての Windows 互換の PC が Windows 10 Enterprise の最新バージョンを実行することとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="e1fa7-112">展開ツール</span><span class="sxs-lookup"><span data-stu-id="e1fa7-112">Deployment tools</span></span>

<span data-ttu-id="e1fa7-113">Contoso 社は、Windows 10 Enterprise の一括アップグレードの前および最中に、Windows Analytics の次のソリューションを使用しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="e1fa7-114">Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="e1fa7-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="e1fa7-115">分析のためにシステム、アプリケーション、ドライバーのデータを収集し、更新の妨げになる可能性がある互換性の問題、推奨される修正、Microsoft によって既に認識されている問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="e1fa7-116">Update Compliance</span><span class="sxs-lookup"><span data-stu-id="e1fa7-116">Update Compliance</span></span>  

  <span data-ttu-id="e1fa7-117">Windows 更新に関するデバイスの状態が表示されるため、必要に応じて最新の更新プログラムが適用されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="e1fa7-118">デバイスの正常性</span><span class="sxs-lookup"><span data-stu-id="e1fa7-118">Device Health</span></span>  

  <span data-ttu-id="e1fa7-119">頻繁にクラッシュするデバイスを特定します。そのため、再構築または交換が必要になる可能性があり、デバイス クラッシュの原因となるデバイス ドライバーと、クラッシュの数を減らす可能性のあるドライバーの代替バージョンを提案します。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="e1fa7-120">エンド ユーザーにプロンプ​​トを送信する Windows 情報保護の構成の誤りを通知します。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="e1fa7-p103">Contoso 社には、既存の Configuration Manager (Current Branch) インフラストラクチャがあります。Configuration Manager は大規模環境向けに拡張され、インストール、更新、設定に対する幅広い管理が可能です。また、Windows 10 Enterprise の展開と管理をより簡単で効率的にするための機能も組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="e1fa7-124">計画プロセス</span><span class="sxs-lookup"><span data-stu-id="e1fa7-124">Planning process</span></span>

<span data-ttu-id="e1fa7-125">Contoso 社は、Windows Analytics のアップグレード準備を使用して、インストールされているアプリのセットと、インストールされているアプリとの互換性をWindows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="e1fa7-126">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="e1fa7-126">Deployment process</span></span>

<span data-ttu-id="e1fa7-127">Contoso 社は、Windows 10 Enterprise の一括アップグレードの展開を完了するために、Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="e1fa7-128">構成マネージャーのピア キャッシュを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="e1fa7-129">ボリューム ライセンス サービス センターからのイメージに基づくカスタムの Windows パッケージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="e1fa7-130">Configuration Manager を使用して、Windowsパッケージをネットワーク全体の配布ポイントに展開し、3 つの検証および展開ステージング グループにビルドを展開しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="e1fa7-131">Windows Analytics のデバイスの正常性および Update Compliance ソリューションを使用して、3 つの検証および展開ステージング リングで PC およびデバイスに対して成功の評価を実施しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="e1fa7-132">Contoso 社は、Windows分析情報に基づいて、広範な展開グループに展開するWindows 10 Enterpriseのバージョンを決定しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="e1fa7-133">Configuration Manager 展開タスク シーケンスを実行して、選択した Windowsを広範な展開グループに展開しました。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="e1fa7-134">デバイス正常性ソリューションと更新コンプライアンス ソリューションを使用して、問題に対処するために広範な展開グループ内の監視対象の PC とデバイス。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="e1fa7-135">次に一括アップグレード、および進行中の更新プログラムの展開アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contoso 社の Windows 10 Enterprise の展開インフラストラクチャ](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="e1fa7-137">このインフラストラクチャは以下で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="e1fa7-138">Configuration Manager は、以下を行います:</span><span class="sxs-lookup"><span data-stu-id="e1fa7-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="e1fa7-139">Microsoft Network の Microsoft ボリューム ライセンス センターから Windows 10 Enterprise パッケージのイメージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="e1fa7-140">展開パッケージに対する中央の管理ポイントです。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="e1fa7-141">通常は Contoso 社の地域ハブ オフィスにある地域配布ポイント。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="e1fa7-142">Windowsグループ メンバーシップに基づくインプレイス アップグレードまたは継続的な更新プログラムの展開パッケージを受信およびインストールするさまざまな場所の PC とデバイス。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1fa7-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1fa7-143">Next step</span></span>

<span data-ttu-id="e1fa7-144">Contoso 社が Configuration Manager インフラストラクチャを活用して、組織全体に最新のMicrosoft 365 Apps for enterpriseを展開し、維持[する](contoso-o365pp.md)方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1fa7-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e1fa7-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1fa7-145">See also</span></span>

[<span data-ttu-id="e1fa7-146">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e1fa7-146">Windows 10 Enterprise</span></span>](/windows/deployment/)

[<span data-ttu-id="e1fa7-147">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="e1fa7-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e1fa7-148">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e1fa7-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)