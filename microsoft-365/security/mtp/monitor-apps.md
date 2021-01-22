---
title: アプリの監視&レポート - セキュリティ センター
description: 組織でのクラウド アプリの使用に関するより詳しい情報を得る方法について学習します。 さまざまな種類のアプリ、リスクのレベル、アラートが含まれます。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, アプリ
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930524"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="31cf0-105">Microsoft 365 セキュリティ センターでのアプリの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="31cf0-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="31cf0-106">これらのレポートは、クラウド アプリが組織でどのように使用されているのかについてより詳しい情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="31cf0-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="31cf0-107">さまざまな種類のアプリ、リスクのレベル、アラートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31cf0-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="31cf0-108">危険性の高い電子メール アカウントの監視</span><span class="sxs-lookup"><span data-stu-id="31cf0-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="31cf0-109">**メール保護は、** 危険にさらされているメール アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="31cf0-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="31cf0-110">Microsoft Defender セキュリティ センターでさらに調査するアカウントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="31cf0-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![電子メール保護カード](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="31cf0-112">ユーザーによって付与されたアプリのアクセス許可を監視する</span><span class="sxs-lookup"><span data-stu-id="31cf0-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="31cf0-113">**Cloud App Security - OAuth アプリは、Cloud** App Security によって検出され、ユーザーがアクセス許可を付与したアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="31cf0-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="31cf0-114">Cloud App Security のリスク カタログには、70 以上のリスク要因を使用して評価される 16,000 を超えるアプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31cf0-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="31cf0-115">リスク要因は、アプリの発行元などの一般的な情報から始まるものになります。</span><span class="sxs-lookup"><span data-stu-id="31cf0-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="31cf0-116">その後、アプリが保存中の暗号化をサポートするかどうかや、ユーザー アクティビティの監査ログを提供するかどうかなどのセキュリティ対策と制御に移動します。</span><span class="sxs-lookup"><span data-stu-id="31cf0-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth アプリ カード](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="31cf0-118">クラウド アプリのユーザー アカウントを監視する</span><span class="sxs-lookup"><span data-stu-id="31cf0-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="31cf0-119">**注意が必要なレビュー リスト アカウント** 用のクラウド アプリ アカウント。</span><span class="sxs-lookup"><span data-stu-id="31cf0-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![レビュー カード用のクラウド アプリ アカウント](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="31cf0-121">使用されているクラウド アプリを理解する</span><span class="sxs-lookup"><span data-stu-id="31cf0-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="31cf0-122">**検出されたクラウド アプリ (カテゴリ) は** 、組織で使用されているアプリの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="31cf0-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="31cf0-123">Cloud App Security の Cloud Discovery ダッシュボードにリンクします。</span><span class="sxs-lookup"><span data-stu-id="31cf0-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="31cf0-124">詳細については、「クイック スタート: 検出されたアプリ [を使用する」を参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="31cf0-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![検出されたクラウド アプリカテゴリ カード](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="31cf0-126">ユーザーがクラウド アプリにアクセスする場所を監視する</span><span class="sxs-lookup"><span data-stu-id="31cf0-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="31cf0-127">**クラウド アプリ アクティビティの場所には、** ユーザーがクラウド アプリにアクセスしている場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="31cf0-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![クラウド アプリ アクティビティの場所カード](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="31cf0-129">インフラストラクチャ ワークロードの正常性を監視する</span><span class="sxs-lookup"><span data-stu-id="31cf0-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="31cf0-130">**インフラストラクチャの正常性は** 、Azure Defender のインフラストラクチャ ワークロードに関する正常性状態のアラートを示します。</span><span class="sxs-lookup"><span data-stu-id="31cf0-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="31cf0-131">Azure Defender は、オンプレミスとクラウドのワークロードOffice 365 をサポートする統合セキュリティ管理と Defender を提供します。</span><span class="sxs-lookup"><span data-stu-id="31cf0-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="31cf0-132">ファイアウォールや他のパートナー ソリューションなど、さまざまなソースからセキュリティ データを収集、検索、分析できます。</span><span class="sxs-lookup"><span data-stu-id="31cf0-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="31cf0-133">詳細については [、Azure Defender のドキュメントを参照してください](https://docs.microsoft.com/azure/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="31cf0-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![インフラストラクチャ正常性カード](../../media/infrastructure-health.png)
