---
title: Microsoft Defender ATP の API エクスプローラー
ms.reviewer: ''
description: API エクスプローラーを使用して、API クエリの作成と実行、テスト、および使用可能な API の要求の送信を行う
keywords: api, explorer, send, request, get, post,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 0cfe5227d5d1cdb1f1f4eaea2c859937d7e75264
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065060"
---
# <a name="api-explorer"></a><span data-ttu-id="0ff1a-104">API エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="0ff1a-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ff1a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0ff1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="0ff1a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ff1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="0ff1a-107">Microsoft Defender for Endpoint API Explorer は、さまざまな Defender for Endpoint API を対話的に探索するのに役立つツールです。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="0ff1a-108">API エクスプローラーを使用すると、使用可能な Defender for Endpoint API エンドポイントに対する API クエリの作成と実行、テスト、および要求の送信が容易になります。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="0ff1a-109">API Explorer を使用して、ユーザー インターフェイスでまだ使用できない可能性があるアクションを実行したり、データを見つけたりします。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="0ff1a-110">このツールは、アプリの開発中に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-110">The tool is useful during app development.</span></span> <span data-ttu-id="0ff1a-111">これにより、ユーザー アクセス設定を尊重する API クエリを実行し、アクセス トークンを生成する必要性を減らします。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="0ff1a-112">ツールを使用して、サンプル クエリのギャラリーを探索し、結果コード サンプルをコピーし、デバッグ情報を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="0ff1a-113">API エクスプローラーを使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="0ff1a-114">任意のメソッドの要求を実行し、リアルタイムで応答を確認する</span><span class="sxs-lookup"><span data-stu-id="0ff1a-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="0ff1a-115">API サンプルをすばやく参照し、サポートするパラメーターを確認する</span><span class="sxs-lookup"><span data-stu-id="0ff1a-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="0ff1a-116">API 呼び出しを簡単に行います。管理ポータルのサインインを超えて認証する必要はありません</span><span class="sxs-lookup"><span data-stu-id="0ff1a-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="0ff1a-117">Access API Explorer</span><span class="sxs-lookup"><span data-stu-id="0ff1a-117">Access API Explorer</span></span>

<span data-ttu-id="0ff1a-118">左側のナビゲーション メニューで、[**パートナー] を選択& API**  >  **API エクスプローラーを選択します**。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="0ff1a-119">サポートされている API</span><span class="sxs-lookup"><span data-stu-id="0ff1a-119">Supported APIs</span></span>

<span data-ttu-id="0ff1a-120">API エクスプローラーは、Defender for Endpoint によって提供される API をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="0ff1a-121">サポートされている API の一覧は [、API のドキュメントで確認できます](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="0ff1a-122">API エクスプローラーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="0ff1a-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="0ff1a-123">左側のウィンドウには、使用できるサンプル要求の一覧があります。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="0ff1a-124">リンクに従い、[クエリの実行 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="0ff1a-125">一部のサンプルでは、URL にパラメーター ({machine- ID} など) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="0ff1a-126">FAQ</span><span class="sxs-lookup"><span data-stu-id="0ff1a-126">FAQ</span></span>

<span data-ttu-id="0ff1a-127">**API エクスプローラーを使用するには、API トークンが必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="0ff1a-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="0ff1a-128">API にアクセスするための資格情報は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="0ff1a-129">API エクスプローラーは、要求を行うたびに Defender for Endpoint 管理ポータル トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="0ff1a-130">ログインしているユーザー認証資格情報を使用して、API Explorer がユーザーに代わってデータにアクセスする権限を持つかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="0ff1a-131">特定の API 要求は、RBAC 特権に基づいて制限されます。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="0ff1a-132">たとえば、"送信インジケーター" への要求は、セキュリティ管理者の役割に制限されます。</span><span class="sxs-lookup"><span data-stu-id="0ff1a-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
