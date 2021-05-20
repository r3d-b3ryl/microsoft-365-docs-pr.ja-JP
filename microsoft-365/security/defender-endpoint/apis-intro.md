---
title: Microsoft Defender for Endpoint API にアクセスする
ms.reviewer: ''
description: API を使用してワークフローを自動化し、エンドポイント用 Microsoft Defender 機能に基づく革新を行う方法を学びます。
keywords: apis, api, wdatp, オープン API, エンドポイント API 用マイクロソフトディフェンダー, マイクロソフトディフェンダー atp, パブリック API, サポートされている API, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度な狩猟, クエリ
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
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571831"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="35383-104">Microsoft Defender for Endpoint API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="35383-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35383-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="35383-105">**Applies to:**</span></span>
- [<span data-ttu-id="35383-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35383-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35383-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35383-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="35383-108">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="35383-108">**Applies to:**</span></span> 
- [<span data-ttu-id="35383-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35383-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="35383-110">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="35383-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35383-111">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="35383-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="35383-112">エンドポイントの Defender は、プログラム API のセットを通じてデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="35383-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="35383-113">これらの API を使用すると、ワークフローを自動化し、Endpoint 用 Defender 機能に基づいてイノベーションを起こします。</span><span class="sxs-lookup"><span data-stu-id="35383-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="35383-114">API アクセスには OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="35383-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="35383-115">詳細については[、「OAuth 2.0 認証コード Flow」](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35383-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="35383-116">エンドポイントの API の Defender の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35383-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="35383-117">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35383-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="35383-118">[AAD アプリケーション](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)を作成する</span><span class="sxs-lookup"><span data-stu-id="35383-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="35383-119">このアプリケーションを使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="35383-119">Get an access token using this application</span></span>
- <span data-ttu-id="35383-120">トークンを使用してエンドポイント API の Defender にアクセスする</span><span class="sxs-lookup"><span data-stu-id="35383-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="35383-121">**アプリケーション コンテキスト** または **ユーザー** コンテキスト を使用して、Endpoint API の Defender にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="35383-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="35383-122">**アプリケーションコンテキスト: (推奨)**</span><span class="sxs-lookup"><span data-stu-id="35383-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="35383-123">サインインしているユーザーが存在しないまま実行されるアプリで使用されます。</span><span class="sxs-lookup"><span data-stu-id="35383-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="35383-124">たとえば、バックグラウンド サービスまたはデーモンとして実行されるアプリなどです。</span><span class="sxs-lookup"><span data-stu-id="35383-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="35383-125">アプリケーションコンテキストを持つエンドポイントAPIのDefenderにアクセスするために実行する必要がある手順:</span><span class="sxs-lookup"><span data-stu-id="35383-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="35383-126">AAD Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="35383-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="35383-127">「アラートの読み取り」「マシンの分離」など、アプリケーションに必要なアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="35383-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="35383-128">このアプリケーションのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="35383-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="35383-129">アプリケーションをキーと共に使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="35383-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="35383-130">エンドポイント API の Microsoft Defender にアクセスするトークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="35383-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="35383-131">詳細については、「アプリケーション [コンテキストを使用したアクセスの取得](exposed-apis-create-app-webapp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35383-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="35383-132">**ユーザー コンテキスト:**</span><span class="sxs-lookup"><span data-stu-id="35383-132">**User Context:**</span></span> <br>
    <span data-ttu-id="35383-133">ユーザーの代わりに API でアクションを実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="35383-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="35383-134">アプリケーションコンテキストを使用してエンドポイントAPIのDefenderにアクセスするための手順:</span><span class="sxs-lookup"><span data-stu-id="35383-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="35383-135">AAD ネイティブ アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="35383-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="35383-136">「アラートの読み取り」「マシンの分離」など、アプリケーションに必要なアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="35383-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="35383-137">ユーザーの資格情報を持つアプリケーションを使用してトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="35383-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="35383-138">エンドポイント API の Microsoft Defender にアクセスするトークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="35383-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="35383-139">詳細については、「ユーザー [コンテキストを使用したアクセスの取得](exposed-apis-create-app-nativeapp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35383-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="35383-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="35383-140">Related topics</span></span>
- [<span data-ttu-id="35383-141">エンドポイント API のマイクロソフト ディフェンダー</span><span class="sxs-lookup"><span data-stu-id="35383-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="35383-142">アプリケーション コンテキストを使用してエンドポイント用の Microsoft Defender にアクセスする</span><span class="sxs-lookup"><span data-stu-id="35383-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="35383-143">ユーザー コンテキストを使用してエンドポイント用の Microsoft Defender にアクセスする</span><span class="sxs-lookup"><span data-stu-id="35383-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
