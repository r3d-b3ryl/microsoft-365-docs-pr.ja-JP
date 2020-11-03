---
title: Microsoft 365 Defender Api にアクセスする
description: Microsoft 365 Defender Api にアクセスする方法について説明します。
keywords: access、api、アプリケーションコンテキスト、ユーザーコンテキスト、aad アプリケーション、アクセストークン
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845021"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="2bf70-104">Microsoft 365 Defender Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2bf70-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2bf70-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2bf70-105">**Applies to:**</span></span>
- <span data-ttu-id="2bf70-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bf70-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="2bf70-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="2bf70-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2bf70-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="2bf70-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="2bf70-109">Microsoft 365 Defender は、一連のプログラム Api を使用して、そのデータおよびアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="2bf70-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="2bf70-110">これらの Api を使用すると、Microsoft 365 Defender の機能に基づいてワークフローとイノベーションを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="2bf70-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="2bf70-111">API へのアクセスには、OAuth 2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="2bf70-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="2bf70-112">詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf70-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="2bf70-113">一般に、Api を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bf70-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="2bf70-114">AAD アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="2bf70-114">Create an AAD application</span></span>
- <span data-ttu-id="2bf70-115">このアプリケーションを使用してアクセストークンを取得する</span><span class="sxs-lookup"><span data-stu-id="2bf70-115">Get an access token using this application</span></span>
- <span data-ttu-id="2bf70-116">トークンを使用して Microsoft 365 Defender API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2bf70-116">Use the token to access  Microsoft 365 Defender API</span></span>


<span data-ttu-id="2bf70-117">**アプリケーションコンテキスト** または **ユーザーコンテキスト** を使用して、Microsoft 365 Defender API にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2bf70-117">You can access Microsoft 365 Defender API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="2bf70-118">**アプリケーションコンテキスト: (推奨)**</span><span class="sxs-lookup"><span data-stu-id="2bf70-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="2bf70-119">サインインしているユーザーなしで実行するアプリによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bf70-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="2bf70-120">たとえば、バックグラウンドサービスまたはデーモンとして実行されるアプリです。</span><span class="sxs-lookup"><span data-stu-id="2bf70-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="2bf70-121">アプリケーションコンテキストを使用して Microsoft 365 Defender API にアクセスするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bf70-121">Steps that need to be taken to access  Microsoft 365 Defender API with application context:</span></span>

  1. <span data-ttu-id="2bf70-122">AAD Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bf70-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="2bf70-123">必要なアクセス許可をアプリケーションに割り当てます。たとえば、 **インシデント.** **AdvancedHunting** , read.</span><span class="sxs-lookup"><span data-stu-id="2bf70-123">Assign the desired permission to the applicationFor example, **Incident.Read.All** , **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="2bf70-124">このアプリケーションのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bf70-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="2bf70-125">アプリケーションとそのキーを使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="2bf70-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="2bf70-126">トークンを使用して Microsoft 365 Defender API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2bf70-126">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="2bf70-127">詳細については、「 [Get access with application context](api-create-app-web.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf70-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="2bf70-128">**ユーザーコンテキスト:**</span><span class="sxs-lookup"><span data-stu-id="2bf70-128">**User Context:**</span></span> <br>
    <span data-ttu-id="2bf70-129">ユーザーに代わって API でアクションを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bf70-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="2bf70-130">アプリケーションコンテキストを使用して Microsoft 365 Defender API にアクセスするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bf70-130">Steps that needs to be taken to access  Microsoft 365 Defender API with application context:</span></span>
  1. <span data-ttu-id="2bf70-131">AAD ネイティブアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bf70-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="2bf70-132">アプリケーションに必要なアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2bf70-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="2bf70-133">たとえば、「 **AdvancedHunting** **」と読みます** 。</span><span class="sxs-lookup"><span data-stu-id="2bf70-133">For example, **Incident.Read** , **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="2bf70-134">ユーザー資格情報を使用してアプリケーションを使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="2bf70-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="2bf70-135">トークンを使用して Microsoft 365 Defender API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2bf70-135">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="2bf70-136">詳細については、「 [Get access with user context](api-create-app-user-context.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf70-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="2bf70-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bf70-137">Related topics</span></span>
- [<span data-ttu-id="2bf70-138">Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="2bf70-138">Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="2bf70-139">アプリケーションコンテキストを使用して Microsoft 365 Defender にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2bf70-139">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="2bf70-140">ユーザーコンテキストを使用して Microsoft 365 Defender にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2bf70-140">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
