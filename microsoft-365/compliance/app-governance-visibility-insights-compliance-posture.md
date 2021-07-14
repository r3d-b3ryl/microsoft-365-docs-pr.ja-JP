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
ms.openlocfilehash: 2fde19e385d4797e04c8f991efa673d33cea3b58
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430674"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="93bd1-103">アプリのコンプライアンスへの取り組みを決定する</span><span class="sxs-lookup"><span data-stu-id="93bd1-103">Determine your app compliance posture</span></span>

><span data-ttu-id="93bd1-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="93bd1-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="93bd1-105">Microsoft アプリ ガバナンスを使用すると、[Microsoft 365 コンプライアンス センター](https://aka.ms/appgovernance)のアプリ ガバナンスの概要ページから、サード パーティ製アプリのコンプライアンスへの取り組みと、Microsoft 365 テナント内のデータへのアクセスを迅速に評価できます。</span><span class="sxs-lookup"><span data-stu-id="93bd1-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://aka.ms/appgovernance).</span></span>

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス概要] ページ](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="93bd1-107">アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのロール](app-governance-get-started.md#administrator-roles)のいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="93bd1-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="93bd1-108">このページから次の情報が確認できます:</span><span class="sxs-lookup"><span data-stu-id="93bd1-108">From this page, you can see:</span></span>

- <span data-ttu-id="93bd1-109">Microsoft Graph API を使用する OAuth 対応アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="93bd1-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="93bd1-110">テナント内のアプリの数</span><span class="sxs-lookup"><span data-stu-id="93bd1-110">How many are in your tenant</span></span>
  - <span data-ttu-id="93bd1-111">特権が過剰である可能性のあるアプリの数</span><span class="sxs-lookup"><span data-stu-id="93bd1-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="93bd1-112">高い特権のアプリの数</span><span class="sxs-lookup"><span data-stu-id="93bd1-112">How many are high privilege</span></span>

  <span data-ttu-id="93bd1-113">この情報から、特権が過剰なアプリや高い特権を持つアプリによって、組織が晒されるリスクのレベルを判断できます。</span><span class="sxs-lookup"><span data-stu-id="93bd1-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="93bd1-114">アラートの場合:</span><span class="sxs-lookup"><span data-stu-id="93bd1-114">For alerts:</span></span>

  - <span data-ttu-id="93bd1-115">テナントに含まれているアクティブなアラートの数</span><span class="sxs-lookup"><span data-stu-id="93bd1-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="93bd1-116">アプリ ガバナンスの検出に基づく数 (**脅威アラート**)</span><span class="sxs-lookup"><span data-stu-id="93bd1-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="93bd1-117">設定されているアプリ ポリシーに基づく数 (**ポリシー アラート**)</span><span class="sxs-lookup"><span data-stu-id="93bd1-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="93bd1-118">最新の 10 件のアラート</span><span class="sxs-lookup"><span data-stu-id="93bd1-118">The 10 latest alerts</span></span>

  <span data-ttu-id="93bd1-119">この情報から、アラートの生成速度と、検出されたアラートとポリシー ベースのアラートの相対的な数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="93bd1-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="93bd1-120">データとリソースへのアクセス:</span><span class="sxs-lookup"><span data-stu-id="93bd1-120">For data and resources access:</span></span>

  - <span data-ttu-id="93bd1-121">過去 90 日間のアプリケーションの API データ アクセス</span><span class="sxs-lookup"><span data-stu-id="93bd1-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="93bd1-122">過去 90 日間の上位リソースの使用状況</span><span class="sxs-lookup"><span data-stu-id="93bd1-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="93bd1-123">この情報から、Microsoft 365 テナント内のデータへのアクセスに異常なスパイクがあるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="93bd1-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
