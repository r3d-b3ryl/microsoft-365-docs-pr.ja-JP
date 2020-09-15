---
title: Microsoft の脅威保護 Api にアクセスする
description: Microsoft の脅威保護 Api にアクセスする方法について説明します。
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
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650428"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="e5dba-104">Microsoft の脅威保護 Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="e5dba-104">Access the Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="e5dba-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e5dba-105">**Applies to:**</span></span>
- <span data-ttu-id="e5dba-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e5dba-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e5dba-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="e5dba-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e5dba-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e5dba-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="e5dba-109">Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="e5dba-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="e5dba-110">これらの Api を使用すると、Microsoft の脅威保護機能に基づいてワークフローとイノベーションを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="e5dba-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="e5dba-111">API へのアクセスには、OAuth 2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5dba-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="e5dba-112">詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5dba-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="e5dba-113">一般に、Api を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5dba-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="e5dba-114">AAD アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="e5dba-114">Create an AAD application</span></span>
- <span data-ttu-id="e5dba-115">このアプリケーションを使用してアクセストークンを取得する</span><span class="sxs-lookup"><span data-stu-id="e5dba-115">Get an access token using this application</span></span>
- <span data-ttu-id="e5dba-116">トークンを使用して Microsoft の脅威保護 API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="e5dba-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="e5dba-117">**アプリケーションコンテキスト**または**ユーザーコンテキスト**を使用して、MICROSOFT の脅威保護 API にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e5dba-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="e5dba-118">**アプリケーションコンテキスト: (推奨)**</span><span class="sxs-lookup"><span data-stu-id="e5dba-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="e5dba-119">サインインしているユーザーなしで実行するアプリによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5dba-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="e5dba-120">たとえば、バックグラウンドサービスまたはデーモンとして実行されるアプリです。</span><span class="sxs-lookup"><span data-stu-id="e5dba-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="e5dba-121">アプリケーションコンテキストを使用して Microsoft の脅威保護 API にアクセスするために実行する必要がある手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5dba-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="e5dba-122">AAD Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5dba-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="e5dba-123">必要なアクセス許可をアプリケーションに割り当てます。たとえば、 **インシデント.** **AdvancedHunting**, read.</span><span class="sxs-lookup"><span data-stu-id="e5dba-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="e5dba-124">このアプリケーションのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5dba-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="e5dba-125">アプリケーションとそのキーを使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5dba-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="e5dba-126">トークンを使用して Microsoft の脅威保護 API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="e5dba-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="e5dba-127">詳細については、「 [Get access with application context](api-create-app-web.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5dba-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="e5dba-128">**ユーザーコンテキスト:**</span><span class="sxs-lookup"><span data-stu-id="e5dba-128">**User Context:**</span></span> <br>
    <span data-ttu-id="e5dba-129">ユーザーに代わって API でアクションを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5dba-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="e5dba-130">アプリケーションコンテキストを使用して Microsoft の脅威保護 API にアクセスするために実行する必要がある手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5dba-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="e5dba-131">AAD ネイティブアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5dba-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="e5dba-132">アプリケーションに必要なアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e5dba-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="e5dba-133">たとえば、「 **AdvancedHunting** **」と読みます**。</span><span class="sxs-lookup"><span data-stu-id="e5dba-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="e5dba-134">ユーザー資格情報を使用してアプリケーションを使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5dba-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="e5dba-135">トークンを使用して Microsoft の脅威保護 API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="e5dba-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="e5dba-136">詳細については、「 [Get access with user context](api-create-app-user-context.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5dba-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="e5dba-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5dba-137">Related topics</span></span>
- [<span data-ttu-id="e5dba-138">Microsoft の脅威保護 Api</span><span class="sxs-lookup"><span data-stu-id="e5dba-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="e5dba-139">アプリケーションコンテキストを使用して Microsoft の脅威保護にアクセスする</span><span class="sxs-lookup"><span data-stu-id="e5dba-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="e5dba-140">ユーザーコンテキストを使用して Microsoft の脅威保護にアクセスする</span><span class="sxs-lookup"><span data-stu-id="e5dba-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
