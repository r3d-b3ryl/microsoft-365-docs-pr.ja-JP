---
title: Microsoft 365 Defender API の概要
description: Microsoft 365 Defender で使用可能な API について説明します。
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
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="8698f-104">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="8698f-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8698f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8698f-105">**Applies to:**</span></span>

- <span data-ttu-id="8698f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8698f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8698f-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="8698f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8698f-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="8698f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8698f-109">Microsoft 365 Defender は、統合対応プラットフォームの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="8698f-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="8698f-110">Microsoft 365 Defender API を使用して、共有インシデントと高度なハンティング テーブルに基づいてワークフローを自動化します。</span><span class="sxs-lookup"><span data-stu-id="8698f-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="8698f-111">**[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃スコープ全体と影響を受けたすべてのアセットをグループ化して、重要な機能に重点を置きます。</span><span class="sxs-lookup"><span data-stu-id="8698f-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="8698f-112">**[製品間の](api-advanced-hunting.md)** 脅威の検出 - セキュリティ チームの組織の知識を活用して、複数の保護製品で収集された生データをふるいにかけ、独自のカスタム クエリを作成することで、侵害の兆候を探します。</span><span class="sxs-lookup"><span data-stu-id="8698f-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="8698f-113">これらの Microsoft 365 Defender 固有の API と共に、他[](api-articles.md)の各セキュリティ製品は、独自の機能を利用するために追加の API を公開します。</span><span class="sxs-lookup"><span data-stu-id="8698f-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="8698f-114">統合ポータルへの移行は、Microsoft Defender for Endpoint API に基づく PowerBi ダッシュボードに影響を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="8698f-114">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="8698f-115">対話型ポータルの移行に関係なく、既存の API を引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="8698f-115">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="8698f-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8698f-116">Learn more</span></span>

| <span data-ttu-id="8698f-117">**API にアクセスする方法を理解する**</span><span class="sxs-lookup"><span data-stu-id="8698f-117">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="8698f-118">API クォータとライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="8698f-118">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="8698f-119">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="8698f-119">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="8698f-120">**アプリのビルド**</span><span class="sxs-lookup"><span data-stu-id="8698f-120">**Build apps**</span></span> |
| [<span data-ttu-id="8698f-121">'Hello world' アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8698f-121">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="8698f-122">ユーザーに代わって Microsoft 365 Defender API にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8698f-122">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="8698f-123">ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8698f-123">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="8698f-124">Microsoft 365 Defender API へのマルチテナント パートナー アクセスでアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8698f-124">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="8698f-125">**アプリのトラブルシューティングと保守**</span><span class="sxs-lookup"><span data-stu-id="8698f-125">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="8698f-126">API エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="8698f-126">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="8698f-127">Azure Key Vault を使用してアプリ内のシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="8698f-127">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="8698f-128">ユーザー サインインの OAuth 2.0 承認を実装する</span><span class="sxs-lookup"><span data-stu-id="8698f-128">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |