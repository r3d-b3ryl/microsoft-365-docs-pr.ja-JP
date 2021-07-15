---
title: 可視性と分析情報の使用を開始する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 可視性と分析情報の使用を開始します。
ms.openlocfilehash: 12c1a01667b1bda545b619e931d99132e6611e35
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420270"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="1f735-103">可視性と分析情報の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="1f735-103">Get started with visibility and insights</span></span>

><span data-ttu-id="1f735-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="1f735-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1f735-105">開始する最初の場所は、[https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance) のアプリ ガバナンス ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="1f735-105">The first place to get started is the app governance dashboard at [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="1f735-106">アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのアプリ ガバナンス管理者の役割](app-governance-get-started.md#administrator-roles)のいずれかが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1f735-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス概要] ページ](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="1f735-108">**[Microsoft 365 管理センター] > [Microsoft 365 コンプライアンス センター] > [アプリ ガバナンス] > [概要ページ]** からアプリ ガバナンス ダッシュボードにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1f735-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="1f735-109">ダッシュボードで使用できる機能</span><span class="sxs-lookup"><span data-stu-id="1f735-109">What’s available on the dashboard</span></span>

<span data-ttu-id="1f735-110">ダッシュボードには、テナント内の Microsoft 365 アプリ エコシステムのコンポーネントの概要が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f735-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="1f735-111">**テナントの概要**: 主要なアプリとアラートのカテゴリの数。</span><span class="sxs-lookup"><span data-stu-id="1f735-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="1f735-112">**検出およびポリシー アラート**: テナント内の最新のアクティブなアラート</span><span class="sxs-lookup"><span data-stu-id="1f735-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="1f735-113">**データとリソースへのアクセス**: アプリケーション API アクセスと、テナント内の上位リソースの全体的な使用状況を集約します。</span><span class="sxs-lookup"><span data-stu-id="1f735-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="1f735-114">グラフの各月の列にマウスでポイントすると、対応する値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f735-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="1f735-115">**アプリの保護とガバナンスの改善**: アプリの使用法やアクセス許可ポリシーの作成など、推奨されるアクション。</span><span class="sxs-lookup"><span data-stu-id="1f735-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="1f735-116">**カテゴリ別の上位アプリ**: 次のカテゴリ別に並べ替えられた上位アプリ:</span><span class="sxs-lookup"><span data-stu-id="1f735-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="1f735-117">**すべてのカテゴリ**: 使用可能なすべてのカテゴリに並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1f735-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="1f735-118">**高特権**: 高特権は、プラットフォームの機械学習とシグナルに基づいて内部で決定されたカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="1f735-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="1f735-119">**特権超過**: アプリ ガバナンスが、アプリケーションに付与されたアクセス許可が過去 90 日間使用されていないことを示すテレメトリを受信すると、そのアプリケーションは特権超過になります。</span><span class="sxs-lookup"><span data-stu-id="1f735-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="1f735-120">アプリ ガバナンスは、アプリが特権超過かどうかを判断するために、少なくとも 90 日間稼働している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f735-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="1f735-121">**未確認**: [発行元の認定](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview)を受けていないアプリケーションは未確認と見なされます。</span><span class="sxs-lookup"><span data-stu-id="1f735-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="1f735-122">**アプリのみ**: [アプリケーションのアクセス許可](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types)は、サインインしているユーザーなしで実行できるアプリに使用します。</span><span class="sxs-lookup"><span data-stu-id="1f735-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="1f735-123">テナント全体のデータにアクセスする権限を持つアプリは、潜在的にリスクが高くなります。</span><span class="sxs-lookup"><span data-stu-id="1f735-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="1f735-124">**新しいアプリ**: 過去 7 日間に登録された新しい Microsoft 365 アプリ。</span><span class="sxs-lookup"><span data-stu-id="1f735-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="1f735-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="1f735-125">Next step</span></span>

<span data-ttu-id="1f735-126">[特定のアプリに関する詳細な分析情報を取得します](app-governance-visibility-insights-view-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="1f735-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>
