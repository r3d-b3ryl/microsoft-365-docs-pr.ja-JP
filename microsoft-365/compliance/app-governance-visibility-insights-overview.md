---
title: 可視性と分析情報について学習する
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
description: 可視性と分析情報について学習する。
ms.openlocfilehash: ee485c972193c515bafec55f58a7a89aa1f567f1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420260"
---
# <a name="learn-about-visibility-and-insights"></a><span data-ttu-id="0c323-103">可視性と分析情報について学習する</span><span class="sxs-lookup"><span data-stu-id="0c323-103">Learn about visibility and insights</span></span>

><span data-ttu-id="0c323-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="0c323-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0c323-105">Microsoft アプリ ガバナンスを使用すると、Microsoft 365 アプリケーション エコシステムに関する可視性と意味のある分析情報をすばやく得ることができます。</span><span class="sxs-lookup"><span data-stu-id="0c323-105">With Microsoft app governance, you can quickly gain visibility and meaningful insights on your Microsoft 365 application ecosystem.</span></span> <span data-ttu-id="0c323-106">管理者の注意が必要なテナント内のアラートとアプリの概要を提供するアプリ ガバナンス ダッシュボードから開始します。</span><span class="sxs-lookup"><span data-stu-id="0c323-106">You start from the app governance dashboard that provides a high-level summary of the alerts and apps in your tenant that require administrator attention.</span></span>

<span data-ttu-id="0c323-107">アプリ ガバナンスの可視性と分析情報を使用すると、次の情報を確認できます:</span><span class="sxs-lookup"><span data-stu-id="0c323-107">With app governance visibility and insights, you can see:</span></span>

- <span data-ttu-id="0c323-108">Microsoft Graph API を介して Microsoft 365 データにアクセスする OAuth 対応アプリの一覧です。</span><span class="sxs-lookup"><span data-stu-id="0c323-108">A list of the OAuth-enabled apps that access Microsoft 365 data via Microsoft Graph APIs.</span></span>
- <span data-ttu-id="0c323-109">反応または対応できる豊富なアプリ アクティビティのビュー。</span><span class="sxs-lookup"><span data-stu-id="0c323-109">A rich view on app activities so that you can react or respond to them.</span></span>

>[!Note]
><span data-ttu-id="0c323-110">Microsoft 365 リソースにアクセスするためのアクセス許可が付与されていない Azure 専用アプリは、アプリ ガバナンスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="0c323-110">Azure-only apps that are not granted permissions to access Microsoft 365 resources are not displayed in app governance.</span></span>
>

<span data-ttu-id="0c323-111">可視性と分析情報に必要な管理者ロールの概要については、「[管理者ロール](app-governance-get-started.md#administrator-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c323-111">See [administrator roles](app-governance-get-started.md#administrator-roles) for an overview of required administrator roles for visibility and insights.</span></span>

<!--
From messaging doc, page 21:

View M365 App List & Metadata
View M365 App List of Consented Users
View M365 App Permissions
View M365 App Permission Usage
View Over permissioned Apps
Aggregate M365 API Usage Data by Workload (count, download/upload)
Per-App M365 API Usage Data by Workload (count, download/upload)
Per-User M365 API Usage Data by Workload (count, download/upload)
M365 API Usage Data For High-Value/Classified Assets (count, download/upload)
M365 API Error Analysis per App
-->

<span data-ttu-id="0c323-112">アプリ ガバナンスを使用すると、次の情報を確認できます:</span><span class="sxs-lookup"><span data-stu-id="0c323-112">With app governance, you can see:</span></span>

- <span data-ttu-id="0c323-113">すべての分析情報のダッシュボード。</span><span class="sxs-lookup"><span data-stu-id="0c323-113">A dashboard of all insights.</span></span>
- <span data-ttu-id="0c323-114">ワークロードとユーザー レベルの分析情報を使用して、1 つのアプリとすべてのアプリからアクセスされるデータ。</span><span class="sxs-lookup"><span data-stu-id="0c323-114">Data accessed by single and all apps with workload and user level insights.</span></span>
- <span data-ttu-id="0c323-115">アクセス許可、登録日、認定などのアプリケーション情報およびメタデータ。</span><span class="sxs-lookup"><span data-stu-id="0c323-115">App information and metadata, such as permissions, registration date, and certification.</span></span>
- <span data-ttu-id="0c323-116">名前、検証状態などの発行元の情報およびメタデータ。</span><span class="sxs-lookup"><span data-stu-id="0c323-116">Publisher information and metadata, such as name and verification status.</span></span>
- <span data-ttu-id="0c323-117">テナント全体の上位リソース (電子メールとファイル) の使用状況。</span><span class="sxs-lookup"><span data-stu-id="0c323-117">Usage of top resources (emails and files) across the tenant.</span></span>
- <span data-ttu-id="0c323-118">分析情報:</span><span class="sxs-lookup"><span data-stu-id="0c323-118">Insights on:</span></span>

  - <span data-ttu-id="0c323-119">高い特権を有するアプリ。</span><span class="sxs-lookup"><span data-stu-id="0c323-119">High-privileged apps.</span></span>
  - <span data-ttu-id="0c323-120">過度な特権を有するアプリ。</span><span class="sxs-lookup"><span data-stu-id="0c323-120">Overprivileged apps.</span></span>
  - <span data-ttu-id="0c323-121">頻繁に使用されているアプリ。</span><span class="sxs-lookup"><span data-stu-id="0c323-121">High-usage apps.</span></span>
  - <span data-ttu-id="0c323-122">特定のアプリがアクセスできるデータを持つ上位の同意ユーザー。</span><span class="sxs-lookup"><span data-stu-id="0c323-122">Top consented users whose data a specific app can access.</span></span>
  - <span data-ttu-id="0c323-123">特定のアプリがアクセスできるデータを持つ優先度の高いアカウント。</span><span class="sxs-lookup"><span data-stu-id="0c323-123">Priority accounts who have data that a specific app can access.</span></span>

- <span data-ttu-id="0c323-124">アプリにアクセスしているユーザーの累積ビュー。</span><span class="sxs-lookup"><span data-stu-id="0c323-124">A cumulative view of users accessing apps.</span></span>
- <span data-ttu-id="0c323-125">アラートの分析情報。</span><span class="sxs-lookup"><span data-stu-id="0c323-125">Alerts insights.</span></span>
- <span data-ttu-id="0c323-126">ポリシー リストの分析情報。</span><span class="sxs-lookup"><span data-stu-id="0c323-126">Policy list insights.</span></span>
<span data-ttu-id="0c323-127"><!--></span><span class="sxs-lookup"><span data-stu-id="0c323-127"><!--></span></span>
- <span data-ttu-id="0c323-128">アプリ ガバナンス ポータルの MCAS で作成されたポリシー。</span><span class="sxs-lookup"><span data-stu-id="0c323-128">Policies created in MCAS in the app governance portal.</span></span>
-->
- <span data-ttu-id="0c323-129">アプリ ガバナンスにおいて、MCAS で生成される OAuth のアラート。</span><span class="sxs-lookup"><span data-stu-id="0c323-129">Alerts for OAuth apps generated in MCAS, in the app governance portal.</span></span>

<span data-ttu-id="0c323-130">以下のことも実行できます:</span><span class="sxs-lookup"><span data-stu-id="0c323-130">You can also:</span></span>

- <span data-ttu-id="0c323-131">関連付けられている分析情報をすべて含む 1 つのアプリ (アプリ ページ) にドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="0c323-131">Drill down to a single app (app page) with all its associated insights.</span></span>
- <span data-ttu-id="0c323-132">データ別の上位ユーザーと、1 つのアプリ内の優先度の高いアカウントにドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="0c323-132">Drill-down into top users by data, and priority accounts within a single app.</span></span>

## <a name="next-step"></a><span data-ttu-id="0c323-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="0c323-133">Next step</span></span>

[<span data-ttu-id="0c323-134">アプリケーションの分析情報から始めます。</span><span class="sxs-lookup"><span data-stu-id="0c323-134">Get started with application insights.</span></span>](app-governance-visibility-insights-get-started.md)
