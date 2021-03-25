---
title: エンドポイント API 用 Microsoft Defender にアクセスする
ms.reviewer: ''
description: API を使用してワークフローを自動化し、Microsoft Defender ATP 機能に基づいて革新する方法について説明します。
keywords: apis, api, wdatp, open api, microsoft defender atp api, public api, supported apis, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度なハンティング, クエリ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 70a8ba9d3ff864ca58c856714b00f0e8feba933a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164764"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="95aab-104">エンドポイント API 用 Microsoft Defender にアクセスする</span><span class="sxs-lookup"><span data-stu-id="95aab-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95aab-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="95aab-105">**Applies to:**</span></span>
- [<span data-ttu-id="95aab-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="95aab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95aab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95aab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="95aab-108">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="95aab-108">**Applies to:**</span></span> 
- [<span data-ttu-id="95aab-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="95aab-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="95aab-110">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="95aab-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="95aab-111">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="95aab-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="95aab-112">Defender for Endpoint は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="95aab-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="95aab-113">これらの API を使用すると、Defender for Endpoint の機能に基づいてワークフローを自動化し、革新することができます。</span><span class="sxs-lookup"><span data-stu-id="95aab-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="95aab-114">API アクセスには、OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="95aab-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="95aab-115">詳細については [、「OAuth 2.0 Authorization Code Flow」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="95aab-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="95aab-116">Defender for Endpoint の API の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95aab-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="95aab-117">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95aab-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="95aab-118">AAD アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="95aab-118">Create an AAD application</span></span>
- <span data-ttu-id="95aab-119">このアプリケーションを使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="95aab-119">Get an access token using this application</span></span>
- <span data-ttu-id="95aab-120">トークンを使用して Defender for Endpoint API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="95aab-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="95aab-121">アプリケーション コンテキストまたはユーザー コンテキストを使用して Defender for Endpoint API **にアクセスできます**。</span><span class="sxs-lookup"><span data-stu-id="95aab-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="95aab-122">**アプリケーション コンテキスト: (推奨)**</span><span class="sxs-lookup"><span data-stu-id="95aab-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="95aab-123">サインインしているユーザーが存在せずに実行されるアプリで使用されます。</span><span class="sxs-lookup"><span data-stu-id="95aab-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="95aab-124">たとえば、バックグラウンド サービスまたはデーモンとして実行されるアプリ。</span><span class="sxs-lookup"><span data-stu-id="95aab-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="95aab-125">アプリケーション コンテキストを使用して Defender for Endpoint API にアクセスするために必要な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95aab-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="95aab-126">AAD Web-Application を作成します。</span><span class="sxs-lookup"><span data-stu-id="95aab-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="95aab-127">目的のアクセス許可をアプリケーションに割り当てる (たとえば、「アラートの読み取り」、"コンピューターの分離" など)。</span><span class="sxs-lookup"><span data-stu-id="95aab-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="95aab-128">このアプリケーションのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="95aab-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="95aab-129">キーを使用してアプリケーションを使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="95aab-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="95aab-130">トークンを使用して Microsoft Defender ATP API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="95aab-130">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="95aab-131">詳細については、「Get [access with application context 」を参照してください](exposed-apis-create-app-webapp.md)。</span><span class="sxs-lookup"><span data-stu-id="95aab-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="95aab-132">**ユーザー コンテキスト:**</span><span class="sxs-lookup"><span data-stu-id="95aab-132">**User Context:**</span></span> <br>
    <span data-ttu-id="95aab-133">ユーザーに代わって API でアクションを実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="95aab-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="95aab-134">アプリケーション コンテキストを使用して Defender for Endpoint API にアクセスするための手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95aab-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="95aab-135">AAD ネイティブ アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="95aab-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="95aab-136">目的のアクセス許可をアプリケーションに割り当てる (「アラートの読み取り」、"コンピューターの分離" など)。</span><span class="sxs-lookup"><span data-stu-id="95aab-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="95aab-137">ユーザー資格情報を使用してアプリケーションを使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="95aab-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="95aab-138">トークンを使用して Microsoft Defender ATP API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="95aab-138">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="95aab-139">詳細については、「ユーザー コンテキストで [アクセスを取得する」を参照してください](exposed-apis-create-app-nativeapp.md)。</span><span class="sxs-lookup"><span data-stu-id="95aab-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="95aab-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="95aab-140">Related topics</span></span>
- [<span data-ttu-id="95aab-141">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="95aab-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="95aab-142">アプリケーション コンテキストを使用して Microsoft Defender for Endpoint にアクセスする</span><span class="sxs-lookup"><span data-stu-id="95aab-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="95aab-143">ユーザー コンテキストを使用して Microsoft Defender for Endpoint にアクセスする</span><span class="sxs-lookup"><span data-stu-id="95aab-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
