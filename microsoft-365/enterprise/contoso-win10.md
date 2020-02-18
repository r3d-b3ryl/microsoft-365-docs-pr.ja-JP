---
title: Contoso 社の Windows 10 Enterprise 展開
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
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Windows 10 Enterprise の一括アップグレードを展開した方法について説明します。
ms.openlocfilehash: 5dc58a9090dd6976d7c521f7552181a10f22f5b2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068010"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="d6c53-103">Contoso 社の Windows 10 Enterprise 展開</span><span class="sxs-lookup"><span data-stu-id="d6c53-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="d6c53-p101">Microsoft 365 Enterprise の広範なロールアウトに先立ち、Contoso 社には、Windows 7 (10%)、Windows 8.1 (65%)、Windows 10 (25%) が混在する Windows 互換の PC とデバイスがありました。Contoso 社は、Windows 10 Enterprise 用の PC をアップグレードして、高度なセキュリティを利用したいと考え、更新プログラムの自動展開により IT 部門の負荷を削減しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="d6c53-106">インフラストラクチャとビジネス ニーズを評価した後、Contoso 社は展開に向けて、以下の重要な要件を特定しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="d6c53-107">できるだけ多くの PC やデバイスで Windows 10 Enterprise を実行する必要がある</span><span class="sxs-lookup"><span data-stu-id="d6c53-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="d6c53-108">一括アップグレードのロールアウトには、既存の Configuration Manager インフラストラクチャを活用する</span><span class="sxs-lookup"><span data-stu-id="d6c53-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="d6c53-109">Windows 10 Enterprise のどのバージョンを展開するかを制御し、更新プログラムはリングを介して行う</span><span class="sxs-lookup"><span data-stu-id="d6c53-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="d6c53-110">PC やデバイスは、IT 管理コストとエンドユーザーに与える影響を最小限に抑えつつ、最新の状態に保つ必要がある</span><span class="sxs-lookup"><span data-stu-id="d6c53-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="d6c53-111">最新とは、Contoso 社のビジネス ニーズを満たす Windows 10 Enterprise のサポート バージョンとして定義されます。これは、すべての Windows 互換の PC が Windows 10 Enterprise の最新バージョンを実行することとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6c53-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="d6c53-112">展開ツール</span><span class="sxs-lookup"><span data-stu-id="d6c53-112">Deployment tools</span></span>

<span data-ttu-id="d6c53-113">Contoso 社は、Windows 10 Enterprise の一括アップグレードの前および最中に、Windows Analytics の次のソリューションを使用しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="d6c53-114">Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="d6c53-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="d6c53-115">分析のためにシステム、アプリケーション、ドライバーのデータを収集し、更新の妨げになる可能性がある互換性の問題、推奨される修正、Microsoft によって既に認識されている問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="d6c53-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="d6c53-116">Update Compliance</span><span class="sxs-lookup"><span data-stu-id="d6c53-116">Update Compliance</span></span>  

  <span data-ttu-id="d6c53-117">Windows 更新に関するデバイスの状態が表示されるため、必要に応じて最新の更新プログラムが適用されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d6c53-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="d6c53-118">デバイスの正常性</span><span class="sxs-lookup"><span data-stu-id="d6c53-118">Device Health</span></span>  

  <span data-ttu-id="d6c53-119">頻繁にクラッシュするデバイスを特定します。そのため、再構築または交換が必要になる可能性があり、デバイス クラッシュの原因となるデバイス ドライバーと、クラッシュの数を減らす可能性のあるドライバーの代替バージョンを提案します。</span><span class="sxs-lookup"><span data-stu-id="d6c53-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="d6c53-120">エンド ユーザーにプロンプ​​トを送信する Windows 情報保護の構成の誤りを通知します。</span><span class="sxs-lookup"><span data-stu-id="d6c53-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="d6c53-p103">Contoso 社には、既存の Configuration Manager (Current Branch) インフラストラクチャがあります。Configuration Manager は大規模環境向けに拡張され、インストール、更新、設定に対する幅広い管理が可能です。また、Windows 10 Enterprise の展開と管理をより簡単で効率的にするための機能も組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d6c53-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="d6c53-124">計画プロセス</span><span class="sxs-lookup"><span data-stu-id="d6c53-124">Planning process</span></span>

<span data-ttu-id="d6c53-125">展開に先立って、Contoso 社は次のリングを定義しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="d6c53-126">検証と展開ステージング用の 3 つのリング</span><span class="sxs-lookup"><span data-stu-id="d6c53-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="d6c53-127">プレビュー ビルド用のリング</span><span class="sxs-lookup"><span data-stu-id="d6c53-127">One for preview builds</span></span> 
  - <span data-ttu-id="d6c53-128">新規リリース ビルド用のリング</span><span class="sxs-lookup"><span data-stu-id="d6c53-128">One for new release builds</span></span>
  - <span data-ttu-id="d6c53-129">以前のビルド用のリング</span><span class="sxs-lookup"><span data-stu-id="d6c53-129">One for a previous build</span></span> 
- <span data-ttu-id="d6c53-130">検証リングからのデータに基づく Windows 10 Enterprise の幅広い展開のためのリング</span><span class="sxs-lookup"><span data-stu-id="d6c53-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="d6c53-131">Contoso 社は、Windows Analytics の Upgrade Readiness ソリューションを使用して、インストールされているアプリのセットとそれらの Windows 10 Enterprise との互換性を判断しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="d6c53-132">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="d6c53-132">Deployment process</span></span>

<span data-ttu-id="d6c53-133">Contoso 社は、Windows 10 Enterprise の一括アップグレードの展開を完了するために、Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="d6c53-134">構成マネージャーのピア キャッシュを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="d6c53-135">ボリューム ライセンス サービス センターからのイメージに基づくカスタムの Windows パッケージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="d6c53-136">構成マネージャーを使用して、ネットワーク上の配布ポイントに Windows パッケージを展開し、3 つの検証および展開ステージングのリングにビルドを展開しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="d6c53-137">Windows Analytics のデバイスの正常性および Update Compliance ソリューションを使用して、3 つの検証および展開ステージング リングで PC およびデバイスに対して成功の評価を実施しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="d6c53-138">Contoso 社は、Windows Analytics の情報に基づいて、広範な展開リングに展開する Windows 10 Enterprise のバージョンを決定しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="d6c53-139">構成マネージャーの展開タスク シーケンスを実行して、選択した Windows パッケージを広範な展開リングに展開しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="d6c53-140">問題に対応するために、デバイスの正常性および更新プログラムの適用状況 ソリューションを使用して、広範な展開リング内の PC とデバイスを監視しました。</span><span class="sxs-lookup"><span data-stu-id="d6c53-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="d6c53-141">次に一括アップグレード、および進行中の更新プログラムの展開アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="d6c53-141">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contoso 社の Windows 10 Enterprise の展開インフラストラクチャ](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="d6c53-143">このインフラストラクチャは以下で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d6c53-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="d6c53-144">Configuration Manager は、以下を行います:</span><span class="sxs-lookup"><span data-stu-id="d6c53-144">Configuration Manager, which:</span></span>
  - <span data-ttu-id="d6c53-145">Microsoft Network の Microsoft ボリューム ライセンス センターから Windows 10 Enterprise パッケージのイメージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d6c53-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="d6c53-146">展開パッケージに対する中央の管理ポイントです。</span><span class="sxs-lookup"><span data-stu-id="d6c53-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="d6c53-147">通常は Contoso 社の地域ハブ オフィスにある地域配布ポイント。</span><span class="sxs-lookup"><span data-stu-id="d6c53-147">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="d6c53-148">リング メンバーシップに基づいた一括アップグレードまたは進行中の更新プログラムの展開パッケージを受信してインストールする、さまざまな場所にある Windows PC およびデバイス。</span><span class="sxs-lookup"><span data-stu-id="d6c53-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="d6c53-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="d6c53-149">Next step</span></span>

<span data-ttu-id="d6c53-150">Contoso 社が Configuration Manager インフラストラクチャを利用して、現在の Office 365 ProPlus を組織全体に展開し、維持する方法について[説明](contoso-o365pp.md)します。</span><span class="sxs-lookup"><span data-stu-id="d6c53-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="d6c53-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6c53-151">See also</span></span>

[<span data-ttu-id="d6c53-152">Microsoft 365 Enterprise 向け Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d6c53-152">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="d6c53-153">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="d6c53-153">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d6c53-154">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="d6c53-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
