---
title: Defender API Microsoft 365の概要
description: Defender で使用可能な API についてMicrosoft 365する
keywords: api, apis, 概要, インシデント, インシデント, 脅威の検出, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904190"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="6e038-104">Defender API Microsoft 365の概要</span><span class="sxs-lookup"><span data-stu-id="6e038-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6e038-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6e038-105">**Applies to:**</span></span>

- <span data-ttu-id="6e038-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e038-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e038-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="6e038-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6e038-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="6e038-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6e038-109">Microsoft 365Defender は統合対応プラットフォームの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="6e038-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="6e038-110">Defender API Microsoft 365使用して、共有インシデントテーブルと高度なハンティング テーブルに基づいてワークフローを自動化します。</span><span class="sxs-lookup"><span data-stu-id="6e038-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="6e038-111">**[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃スコープ全体と影響を受けたすべてのアセットをグループ化して、重要な機能に重点を置きます。</span><span class="sxs-lookup"><span data-stu-id="6e038-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="6e038-112">**[製品間の](api-advanced-hunting.md)** 脅威の検出 - セキュリティ チームの組織の知識を活用して、複数の保護製品で収集された生データをふるいにかけ、独自のカスタム クエリを作成することで、侵害の兆候を探します。</span><span class="sxs-lookup"><span data-stu-id="6e038-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="6e038-113">Defender 固有の API Microsoft 365に加え、他の各セキュリティ製品は、独自[](api-articles.md)の機能を利用するために追加の API を公開します。</span><span class="sxs-lookup"><span data-stu-id="6e038-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="6e038-114">統合ポータルへの移行は、Microsoft Defender for Endpoint API に基づく PowerBi ダッシュボードに影響を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e038-114">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="6e038-115">対話型ポータルの移行に関係なく、既存の API を引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="6e038-115">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="6e038-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6e038-116">Learn more</span></span>

| <span data-ttu-id="6e038-117">**API にアクセスする方法を理解する**</span><span class="sxs-lookup"><span data-stu-id="6e038-117">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="6e038-118">API クォータとライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="6e038-118">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="6e038-119">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="6e038-119">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="6e038-120">**アプリのビルド**</span><span class="sxs-lookup"><span data-stu-id="6e038-120">**Build apps**</span></span> |
| [<span data-ttu-id="6e038-121">'Hello world' アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="6e038-121">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="6e038-122">ユーザーに代わって Defender API Microsoft 365アクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="6e038-122">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="6e038-123">ユーザーなしで Defender にアクセスMicrosoft 365アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="6e038-123">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="6e038-124">複数テナントパートナーが Defender API にアクセスできるアプリMicrosoft 365作成する</span><span class="sxs-lookup"><span data-stu-id="6e038-124">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="6e038-125">**アプリのトラブルシューティングと保守**</span><span class="sxs-lookup"><span data-stu-id="6e038-125">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="6e038-126">API エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="6e038-126">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="6e038-127">Azure Key Vault を使用してアプリ内のシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="6e038-127">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="6e038-128">ユーザー サインインの OAuth 2.0 承認を実装する</span><span class="sxs-lookup"><span data-stu-id="6e038-128">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |