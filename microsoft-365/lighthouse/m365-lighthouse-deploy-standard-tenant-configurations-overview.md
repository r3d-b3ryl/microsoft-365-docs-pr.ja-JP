---
title: 基準計画を使用した標準テナント構成の展開の概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseを使用して標準的なテナント構成を展開する方法について説明します。
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409185"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="3b862-103">基準計画を使用した標準テナント構成の展開の概要</span><span class="sxs-lookup"><span data-stu-id="3b862-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="3b862-104">この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b862-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="3b862-105">組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="3b862-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="3b862-106">Microsoft 365 Lighthouseは、複数のテナント間でセキュリティ設定を評価および管理するための反復可能で拡張性Microsoft 365方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="3b862-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="3b862-107">ベースラインは、ユーザー、デバイス、およびデータをセキュリティで保護する構成を使用して、コア セキュリティ ポリシーとテナントコンプライアンス標準を監視するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b862-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="3b862-108">パートナーが独自のペースでセキュリティを導入するのに役立つ設計で、Microsoft 365 Lighthouse は、Microsoft 365 サービスの標準の基準パラメーターと事前定義された構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="3b862-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="3b862-109">これらのセキュリティ構成は、テナントのセキュリティとコンプライアンスMicrosoft 365を測定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b862-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="3b862-110">既定の基準計画とその展開手順は、既定の基準計画内Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="3b862-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="3b862-111">テナントにベースラインを適用するには、左側のナビゲーション ウィンドウ **で [テナント** ] を選択し、テナントを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b862-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="3b862-112">次に、[展開計画] **タブに移動** し、目的の基準計画を実装します。</span><span class="sxs-lookup"><span data-stu-id="3b862-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="3b862-113">標準の基準計画のセキュリティ テンプレート</span><span class="sxs-lookup"><span data-stu-id="3b862-113">Standard baseline security templates</span></span>

<span data-ttu-id="3b862-114">Microsoft 365 Lighthouseワークロードの標準的なベースライン構成は、すべての管理テナントが許容可能なセキュリティ範囲とコンプライアンスの状態に達するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3b862-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="3b862-115">次の表のベースライン構成は、既定の基準計画Microsoft 365 Lighthouse標準です。</span><span class="sxs-lookup"><span data-stu-id="3b862-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="3b862-116">ベースライン構成</span><span class="sxs-lookup"><span data-stu-id="3b862-116">Baseline configuration</span></span> | <span data-ttu-id="3b862-117">説明</span><span class="sxs-lookup"><span data-stu-id="3b862-117">Description</span></span> |
|--|--|
| <span data-ttu-id="3b862-118">管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3b862-118">Require MFA for admins</span></span> | <span data-ttu-id="3b862-119">管理者に多要素認証を必要とするレポート専用の条件付きアクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3b862-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="3b862-120">すべてのクラウド アプリケーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="3b862-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="3b862-121">エンド ユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3b862-121">Require MFA for end users</span></span> | <span data-ttu-id="3b862-122">ユーザーに多要素認証を必要とするレポート専用の条件付きアクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3b862-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="3b862-123">すべてのクラウド アプリケーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="3b862-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="3b862-124">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="3b862-124">Block legacy authentication</span></span> | <span data-ttu-id="3b862-125">レガシ クライアント認証をブロックするレポート専用の条件付きアクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3b862-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="3b862-126">デバイスをデバイスに登録Microsoft エンドポイント マネージャー – Azure AD参加</span><span class="sxs-lookup"><span data-stu-id="3b862-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="3b862-127">テナント デバイスがデバイスに登録できるデバイスMicrosoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="3b862-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="3b862-128">これは、ユーザーとユーザーの間で自動登録Azure Active Directory設定Microsoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="3b862-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="3b862-129">ウイルス対策 (AV) ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="3b862-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="3b862-130">構成済みのデバイスWindowsデバイスのデバイス構成プロファイルMicrosoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="3b862-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="3b862-131">ウィンドウ 10 コンプライアンス ポリシーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3b862-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="3b862-132">基本的Windows要件を満たす、事前に構成された設定を持つデバイス ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3b862-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="3b862-133">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3b862-133">Related content</span></span>

<span data-ttu-id="3b862-134">[ベースラインMicrosoft 365 Lighthouse展開](m365-lighthouse-deploy-baselines.md)する (記事)</span><span class="sxs-lookup"><span data-stu-id="3b862-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="3b862-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="3b862-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
