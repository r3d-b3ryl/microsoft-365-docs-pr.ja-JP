---
title: アプリケーション監視 & レポート作成-セキュリティセンター
description: 組織でクラウドアプリを使用する方法について説明します。これには、アプリの種類、リスクのレベル、アラートなどが含まれます。
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
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd7a86751ac58f60051891544c9fd68c51b439e1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034024"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="55200-104">Microsoft 365 セキュリティセンターでのアプリの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="55200-104">App monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="55200-105">これらのレポートでは、組織でクラウドアプリがどのように使用されているかについて、より多くの洞察を得ることができます。これには、アプリの種類、リスクレベル、アラートなどがあります。</span><span class="sxs-lookup"><span data-stu-id="55200-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="55200-106">危険性の高い電子メール アカウントの監視</span><span class="sxs-lookup"><span data-stu-id="55200-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="55200-107">**電子メール保護**は、危険にさらされている電子メールアカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="55200-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="55200-108">Microsoft Defender セキュリティセンターでは、アカウントをクリックしてさらに調査することができます。</span><span class="sxs-lookup"><span data-stu-id="55200-108">You can click an account to investigate further in Microsoft Defender Security Center.</span></span>

![電子メール保護カード](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="55200-110">ユーザーによって付与されるアプリのアクセス許可を監視する</span><span class="sxs-lookup"><span data-stu-id="55200-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="55200-111">**Cloud App security-OAuth アプリ**は、ユーザーによってアクセス許可が付与されている Cloud app security によって検出されたアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="55200-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="55200-112">Cloud App Security のリスクカタログには、16000 70 を超えるリスク要因を使用して評価されるのアプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="55200-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="55200-113">リスク要因は、アプリの発行元などの一般的な情報から、アプリケーションが rest での暗号化をサポートしているかどうか、またはユーザーアクティビティの監査ログを提供するかどうかなど、一般的な情報から始めて、セキュリティ対策や統制を開始します。</span><span class="sxs-lookup"><span data-stu-id="55200-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth アプリカード](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="55200-115">Cloud app のユーザーアカウントを監視する</span><span class="sxs-lookup"><span data-stu-id="55200-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="55200-116">**確認のためのクラウドアプリアカウントに**は、注意が必要なアカウントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="55200-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![レビューカード用の Cloud App アカウント](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="55200-118">使用されているクラウドアプリを理解する</span><span class="sxs-lookup"><span data-stu-id="55200-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="55200-119">検出された**クラウドアプリ (カテゴリ)** は、組織で使用されているアプリの種類と、Cloud App Security でのクラウド検出ダッシュボードへのリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="55200-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="55200-120">詳細については、「[クイックスタート: 検出されたアプリの操作](https://docs.microsoft.com/cloud-app-security/discovered-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55200-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![検出されたクラウドアプリのカテゴリカード](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="55200-122">ユーザーがクラウドアプリにアクセスする監視を監視する</span><span class="sxs-lookup"><span data-stu-id="55200-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="55200-123">**クラウドアプリのアクティビティの場所**は、ユーザーがクラウドアプリにアクセスする場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="55200-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![クラウドアプリのアクティビティの場所カード](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="55200-125">インフラストラクチャの負荷の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="55200-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="55200-126">**インフラストラクチャの状態**Azure セキュリティセンターのインフラストラクチャワークロードの正常性状態アラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="55200-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="55200-127">Azure セキュリティセンターでは、オンプレミスとクラウドのワークロード全体にわたる統合セキュリティ管理と高度な脅威保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="55200-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="55200-128">ファイアウォールやその他のパートナーソリューションを含む、さまざまなソースからのセキュリティデータを収集、検索、および分析することができます。</span><span class="sxs-lookup"><span data-stu-id="55200-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="55200-129">詳細については、「 [Azure セキュリティセンターのドキュメント](https://docs.microsoft.com/azure/security-center/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55200-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![インフラストラクチャ正常性カード](../../media/infrastructure-health.png)
