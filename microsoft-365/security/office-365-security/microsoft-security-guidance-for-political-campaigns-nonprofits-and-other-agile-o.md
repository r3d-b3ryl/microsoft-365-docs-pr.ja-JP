---
title: Microsoft Security ガイダンス - 選挙運動および非営利団体
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: '概要: 増大する脅威プロファイルを抱え、急速に変化する組織向けの計画および実装のガイダンスです。'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac278103caf5d4d70b303b50b73db1b4b3571e6b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205283"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="7c465-103">選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス</span><span class="sxs-lookup"><span data-stu-id="7c465-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7c465-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7c465-104">**Applies to**</span></span>
- [<span data-ttu-id="7c465-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7c465-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7c465-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="7c465-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="7c465-107">**概要:** 増大する脅威プロファイルを抱え、急速に変化する組織向けの計画および実装のガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="7c465-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="7c465-p101">組織が機敏であり、少人数の IT チームを抱え、脅威プロファイルが平均より高い場合は、このガイダンスが適しています。このソリューションでは、セキュリティで保護されたコントロールを含む重要なクラウド サービスを使用する環境を一から迅速に構築する方法を示します。このガイダンスには、モバイル デバイスからのデータ、ID、電子メール、およびアクセスを保護するための規範的なセキュリティの推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c465-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="7c465-111">セキュリティ ソリューション ガイダンス</span><span class="sxs-lookup"><span data-stu-id="7c465-111">Security solution guidance</span></span>

<span data-ttu-id="7c465-p102">このガイドでは、セキュリティで保護されたクラウド環境を実装する方法について説明します。ソリューション ガイダンスは、どのような組織でも使用できます。BYOD アクセスとゲスト アカウントを使用するアジャイル組織用に、追加のヘルプが含まれています。このガイダンスは、独自の環境を設計するための開始点としてご利用ください。お客様のフィードバックを [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com) までお寄せください。</span><span class="sxs-lookup"><span data-stu-id="7c465-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="7c465-117">アイテム</span><span class="sxs-lookup"><span data-stu-id="7c465-117">Item</span></span>|<span data-ttu-id="7c465-118">内容</span><span class="sxs-lookup"><span data-stu-id="7c465-118">Description</span></span>|
|---|---|
|<span data-ttu-id="7c465-119">**選挙運動のための Microsoft Security ガイダンス**</span><span class="sxs-lookup"><span data-stu-id="7c465-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="7c465-120">[![ミニ ポスター セット用のサムネイル。](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="7c465-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="7c465-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="7c465-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="7c465-p103">このガイダンスでは、選挙運動を行う団体を例として使用しています。このガイダンスは、任意の環境を設計するための開始点としてご利用ください。</span><span class="sxs-lookup"><span data-stu-id="7c465-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="7c465-124">**非営利組織のための Microsoft Security ガイダンス**</span><span class="sxs-lookup"><span data-stu-id="7c465-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="7c465-125">[![ダウンロード可能なファイル用のサムネイル画像](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="7c465-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="7c465-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="7c465-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="7c465-p104">このガイドは、非営利組織用に少し改定されています。たとえば、Office 365 Nonprofit のプランについて言及しています。技術的なガイダンスは選挙運動のソリューション ガイドと同じです。</span><span class="sxs-lookup"><span data-stu-id="7c465-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="7c465-130">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="7c465-130">Test Lab Guides</span></span>

<span data-ttu-id="7c465-131">このソリューションの開発/テスト環境を作成するには、次のテスト ラボ ガイドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c465-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="7c465-132">選挙運動の開発/テスト環境用にグループとユーザーを構成する</span><span class="sxs-lookup"><span data-stu-id="7c465-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="7c465-133">Office 365 および EMS の試用版サブスクリプションを作成し、代表的な選挙運動のためのグループとユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c465-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="7c465-134">選挙運動用の開発/テスト環境でチーム サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="7c465-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="7c465-135">SharePoint Online の 4 つのチーム サイトを内部、プライベート、機密、および非常に機密性の高い社外秘のセキュリティ レベルで作成します。</span><span class="sxs-lookup"><span data-stu-id="7c465-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="7c465-136">デモのための追加のセキュリティ機能や概念実証については、[Office 365 テスト ラボ ガイド](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c465-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c465-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c465-137">See Also</span></span>

[<span data-ttu-id="7c465-138">Microsoft クラウド IT アーキテクチャのリソース</span><span class="sxs-lookup"><span data-stu-id="7c465-138">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
