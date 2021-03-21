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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922188"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="db3f3-104">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="db3f3-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="db3f3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="db3f3-105">**Applies to:**</span></span>

- <span data-ttu-id="db3f3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db3f3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db3f3-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="db3f3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="db3f3-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="db3f3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="db3f3-109">Microsoft 365 Defender は、統合対応プラットフォームの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="db3f3-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="db3f3-110">Microsoft 365 Defender API を使用して、共有インシデントと高度なハンティング テーブルに基づいてワークフローを自動化します。</span><span class="sxs-lookup"><span data-stu-id="db3f3-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="db3f3-111">**[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃スコープ全体と影響を受けたすべてのアセットをグループ化して、重要な機能に重点を置きます。</span><span class="sxs-lookup"><span data-stu-id="db3f3-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="db3f3-112">**[製品間の](api-advanced-hunting.md)** 脅威の検出 - セキュリティ チームの組織の知識を活用して、複数の保護製品で収集された生データをふるいにかけ、独自のカスタム クエリを作成することで、侵害の兆候を探します。</span><span class="sxs-lookup"><span data-stu-id="db3f3-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="db3f3-113">これらの Microsoft 365 Defender 固有の API と共に、他[](api-articles.md)の各セキュリティ製品は、独自の機能を利用するために追加の API を公開します。</span><span class="sxs-lookup"><span data-stu-id="db3f3-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="db3f3-114">詳細情報</span><span class="sxs-lookup"><span data-stu-id="db3f3-114">Learn more</span></span>

| <span data-ttu-id="db3f3-115">**API にアクセスする方法を理解する**</span><span class="sxs-lookup"><span data-stu-id="db3f3-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="db3f3-116">API クォータとライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="db3f3-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="db3f3-117">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="db3f3-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="db3f3-118">**アプリのビルド**</span><span class="sxs-lookup"><span data-stu-id="db3f3-118">**Build apps**</span></span> |
| [<span data-ttu-id="db3f3-119">'Hello world' アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="db3f3-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="db3f3-120">ユーザーに代わって Microsoft 365 Defender API にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="db3f3-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="db3f3-121">ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="db3f3-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="db3f3-122">Microsoft 365 Defender API へのマルチテナント パートナー アクセスでアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="db3f3-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="db3f3-123">**アプリのトラブルシューティングと保守**</span><span class="sxs-lookup"><span data-stu-id="db3f3-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="db3f3-124">API エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="db3f3-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="db3f3-125">Azure Key Vault を使用してアプリ内のシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="db3f3-125">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="db3f3-126">ユーザー サインインの OAuth 2.0 承認を実装する</span><span class="sxs-lookup"><span data-stu-id="db3f3-126">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |