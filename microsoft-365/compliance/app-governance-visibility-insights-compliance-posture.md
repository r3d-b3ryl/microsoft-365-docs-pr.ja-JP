---
title: アプリのコンプライアンスへの取り組みを決定する
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
description: アプリのコンプライアンスへの取り組みを決定する。
ms.openlocfilehash: 152f68e8fe0e7d7340d2e048bc73684bc079386f
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438026"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="80cd8-103">アプリのコンプライアンスへの取り組みを決定する</span><span class="sxs-lookup"><span data-stu-id="80cd8-103">Determine your app compliance posture</span></span>

><span data-ttu-id="80cd8-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="80cd8-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="80cd8-105">Microsoft アプリ ガバナンスを使用すると、[Microsoft 365 コンプライアンス センター](https://aka.ms/appgovernance)のアプリ ガバナンスの概要ページから、サード パーティ製アプリのコンプライアンスへの取り組みと、Microsoft 365 テナント内のデータへのアクセスを迅速に評価できます。</span><span class="sxs-lookup"><span data-stu-id="80cd8-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://aka.ms/appgovernance).</span></span>

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス概要] ページ](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="80cd8-107">アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのロール](app-governance-get-started.md#administrator-roles)のいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="80cd8-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="80cd8-108">このページから次の情報が確認できます:</span><span class="sxs-lookup"><span data-stu-id="80cd8-108">From this page, you can see:</span></span>

- <span data-ttu-id="80cd8-109">Microsoft Graph API を使用する OAuth 対応アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="80cd8-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="80cd8-110">テナント内のアプリの数</span><span class="sxs-lookup"><span data-stu-id="80cd8-110">How many are in your tenant</span></span>
  - <span data-ttu-id="80cd8-111">特権が過剰である可能性のあるアプリの数</span><span class="sxs-lookup"><span data-stu-id="80cd8-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="80cd8-112">高い特権のアプリの数</span><span class="sxs-lookup"><span data-stu-id="80cd8-112">How many are high privilege</span></span>

  <span data-ttu-id="80cd8-113">この情報から、特権が過剰なアプリや高い特権を持つアプリによって、組織が晒されるリスクのレベルを判断できます。</span><span class="sxs-lookup"><span data-stu-id="80cd8-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="80cd8-114">アラートの場合:</span><span class="sxs-lookup"><span data-stu-id="80cd8-114">For alerts:</span></span>

  - <span data-ttu-id="80cd8-115">テナントに含まれているアクティブなアラートの数</span><span class="sxs-lookup"><span data-stu-id="80cd8-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="80cd8-116">アプリ ガバナンスの検出に基づく数 (**脅威アラート**)</span><span class="sxs-lookup"><span data-stu-id="80cd8-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="80cd8-117">設定されているアプリ ポリシーに基づく数 (**ポリシー アラート**)</span><span class="sxs-lookup"><span data-stu-id="80cd8-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="80cd8-118">最新の 10 件のアラート</span><span class="sxs-lookup"><span data-stu-id="80cd8-118">The 10 latest alerts</span></span>

  <span data-ttu-id="80cd8-119">この情報から、アラートの生成速度と、検出されたアラートとポリシー ベースのアラートの相対的な数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="80cd8-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="80cd8-120">データとリソースへのアクセス:</span><span class="sxs-lookup"><span data-stu-id="80cd8-120">For data and resources access:</span></span>

  - <span data-ttu-id="80cd8-121">テナント内のアプリが、現在と過去 3 か月間にGraph API経由でアクセスした合計データ。</span><span class="sxs-lookup"><span data-stu-id="80cd8-121">Total data accessed by apps in the tenant through Graph API over the current and previous three calendar months.</span></span> <span data-ttu-id="80cd8-122">(現在のところ、Outlook メール とファイルのアップロードとダウンロードの使用状況のみが含まれています)</span><span class="sxs-lookup"><span data-stu-id="80cd8-122">(Currently only includes Mail and File upload and download usage)</span></span>
  - <span data-ttu-id="80cd8-123">リソース種類別の、現在と過去 3 か月間のデータ使用状況。</span><span class="sxs-lookup"><span data-stu-id="80cd8-123">Data usage over the current and previous three calendar months, broken down by resource type.</span></span> <span data-ttu-id="80cd8-124">(現在のところ、Outlook メール とファイルのアップロードとダウンロードの使用状況のみが含まれています)</span><span class="sxs-lookup"><span data-stu-id="80cd8-124">(Currently only includes Mail and File upload and download usage)</span></span>

  <span data-ttu-id="80cd8-125">この情報から、Microsoft 365 テナント内のデータへのアクセスに異常なスパイクがあるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="80cd8-125">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
