---
title: アプリケーション監視 & レポート作成-セキュリティセンター
description: 組織でクラウドアプリを使用する方法について詳しく説明します。 には、さまざまな種類のアプリ、リスクレベル、およびアラートが含まれています。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、アプリ
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6ca9e178ab69e578ef2d84d3051a5df314c527
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414336"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="9fc70-105">Microsoft 365 セキュリティセンターでのアプリの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="9fc70-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9fc70-106">これらのレポートでは、組織内でのクラウドアプリの使用方法についての洞察が得られます。</span><span class="sxs-lookup"><span data-stu-id="9fc70-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="9fc70-107">には、さまざまな種類のアプリ、リスクレベル、およびアラートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fc70-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="9fc70-108">危険性の高い電子メール アカウントの監視</span><span class="sxs-lookup"><span data-stu-id="9fc70-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="9fc70-109">**電子メール保護** は、危険にさらされている電子メールアカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="9fc70-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="9fc70-110">Microsoft Defender セキュリティセンターでさらに調査するアカウントを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="9fc70-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![電子メール保護カード](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="9fc70-112">ユーザーによって付与されるアプリのアクセス許可を監視する</span><span class="sxs-lookup"><span data-stu-id="9fc70-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="9fc70-113">**Cloud App security-OAuth アプリ** は、ユーザーによってアクセス許可が付与されている Cloud app security によって検出されたアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9fc70-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="9fc70-114">Cloud App Security のリスクカタログには、16000 70 を超えるリスク要因を使用して評価されるのアプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fc70-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="9fc70-115">リスク要因は、アプリ発行者などの一般的な情報から開始されます。</span><span class="sxs-lookup"><span data-stu-id="9fc70-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="9fc70-116">その後、アプリが rest での暗号化をサポートしているかどうかや、ユーザーアクティビティの監査ログを表示するかどうかなど、セキュリティの測定およびコントロールに移動します。</span><span class="sxs-lookup"><span data-stu-id="9fc70-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth アプリカード](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="9fc70-118">Cloud app のユーザーアカウントを監視する</span><span class="sxs-lookup"><span data-stu-id="9fc70-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="9fc70-119">**確認のためのクラウドアプリアカウントに** は、注意が必要なアカウントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc70-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![レビューカード用の Cloud App アカウント](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="9fc70-121">使用されているクラウドアプリを理解する</span><span class="sxs-lookup"><span data-stu-id="9fc70-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="9fc70-122">検出された**クラウドアプリ (カテゴリ)** は、組織で使用されているアプリの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="9fc70-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="9fc70-123">Cloud App Security の Cloud Discovery dashboard にリンクします。</span><span class="sxs-lookup"><span data-stu-id="9fc70-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="9fc70-124">詳細については、「 [クイックスタート: 検出されたアプリの操作](https://docs.microsoft.com/cloud-app-security/discovered-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fc70-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![検出されたクラウドアプリのカテゴリカード](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="9fc70-126">ユーザーがクラウドアプリにアクセスする監視を監視する</span><span class="sxs-lookup"><span data-stu-id="9fc70-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="9fc70-127">**クラウドアプリのアクティビティの場所** は、ユーザーがクラウドアプリにアクセスする場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="9fc70-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![クラウドアプリのアクティビティの場所カード](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="9fc70-129">インフラストラクチャの負荷の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="9fc70-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="9fc70-130">**インフラストラクチャの状態** Azure セキュリティセンターのインフラストラクチャワークロードの正常性状態アラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="9fc70-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="9fc70-131">Azure セキュリティセンターでは、オンプレミスとクラウドのワークロード全体にわたる統合セキュリティ管理と高度な脅威保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9fc70-131">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="9fc70-132">ファイアウォールやその他のパートナーソリューションを含む、さまざまなソースからのセキュリティデータを収集、検索、および分析することができます。</span><span class="sxs-lookup"><span data-stu-id="9fc70-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="9fc70-133">詳細については、「 [Azure セキュリティセンターのドキュメント](https://docs.microsoft.com/azure/security-center/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fc70-133">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![インフラストラクチャ正常性カード](../../media/infrastructure-health.png)
