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
ms.openlocfilehash: b19a6072be5f97b90c117f053ccae4593587c43d
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730898"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="b1eb3-104">Defender API Microsoft 365の概要</span><span class="sxs-lookup"><span data-stu-id="b1eb3-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b1eb3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b1eb3-105">**Applies to:**</span></span>

- <span data-ttu-id="b1eb3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1eb3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1eb3-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b1eb3-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b1eb3-109">Microsoft 365Defender は統合対応プラットフォームの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="b1eb3-110">Defender API Microsoft 365使用して、共有インシデントテーブルと高度なハンティング テーブルに基づいてワークフローを自動化します。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="b1eb3-111">**[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃スコープ全体と影響を受けたすべてのアセットをグループ化して、重要な機能に重点を置きます。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="b1eb3-112">**[製品間の](api-advanced-hunting.md)** 脅威の検出 - セキュリティ チームの組織の知識を活用して、複数の保護製品で収集された生データをふるいにかけ、独自のカスタム クエリを作成することで、侵害の兆候を探します。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="b1eb3-113">ストリーミング API [を使用して](../defender-endpoint/raw-data-export.md) 、1 つのデータ ストリーム内で発生するインスタンスからのリアルタイム イベントとアラートを配信します。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="b1eb3-114">Defender 固有の API Microsoft 365に加え、他の各セキュリティ製品は、独自[](api-articles.md)の機能を利用するために追加の API を公開します。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="b1eb3-115">統合ポータルへの移行は、Microsoft Defender for Endpoint API に基づく PowerBi ダッシュボードに影響を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="b1eb3-116">対話型ポータルの移行に関係なく、既存の API を引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="b1eb3-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b1eb3-117">Learn more</span></span>

| <span data-ttu-id="b1eb3-118">**API にアクセスする方法を理解する**</span><span class="sxs-lookup"><span data-stu-id="b1eb3-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="b1eb3-119">API クォータとライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="b1eb3-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="b1eb3-120">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="b1eb3-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="b1eb3-121">**アプリのビルド**</span><span class="sxs-lookup"><span data-stu-id="b1eb3-121">**Build apps**</span></span> |
| [<span data-ttu-id="b1eb3-122">'Hello world' アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="b1eb3-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="b1eb3-123">ユーザーに代わって Defender API Microsoft 365アクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="b1eb3-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="b1eb3-124">ユーザーなしで Defender にアクセスMicrosoft 365アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="b1eb3-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="b1eb3-125">複数テナントパートナーが Defender API にアクセスできるアプリMicrosoft 365作成する</span><span class="sxs-lookup"><span data-stu-id="b1eb3-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="b1eb3-126">**アプリのトラブルシューティングと保守**</span><span class="sxs-lookup"><span data-stu-id="b1eb3-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="b1eb3-127">API エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="b1eb3-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="b1eb3-128">Azure Key Vault を使用してアプリ内のシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="b1eb3-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="b1eb3-129">ユーザー サインインの OAuth 2.0 承認を実装する</span><span class="sxs-lookup"><span data-stu-id="b1eb3-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |