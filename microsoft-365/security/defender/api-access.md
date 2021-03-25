---
title: Microsoft 365 Defender API へのアクセス
description: Microsoft 365 Defender API にアクセスする方法について説明します。
keywords: access、apis、アプリケーション コンテキスト、ユーザー コンテキスト、aad アプリケーション、アクセス トークン
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
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064723"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="2d480-104">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="2d480-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2d480-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2d480-105">**Applies to:**</span></span>

- <span data-ttu-id="2d480-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d480-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d480-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="2d480-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2d480-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="2d480-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2d480-109">Microsoft 365 Defender は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="2d480-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="2d480-110">これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能をフルに活用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2d480-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="2d480-111">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d480-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="2d480-112">Azure Active Directory アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="2d480-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="2d480-113">このアプリケーションを使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="2d480-113">Get an access token using this application</span></span>
- <span data-ttu-id="2d480-114">トークンを使用して Microsoft 365 Defender API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2d480-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="2d480-115">API アクセスには、OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d480-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="2d480-116">詳細については [、「OAuth 2.0 Authorization Code Flow」を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="2d480-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="2d480-117">これらの手順を完了したら、特定のコンテキストを使用して Microsoft 365 Defender API にアクセスする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="2d480-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="2d480-118">アプリケーション コンテキスト (推奨)</span><span class="sxs-lookup"><span data-stu-id="2d480-118">Application context (Recommended)</span></span>

<span data-ttu-id="2d480-119">バックグラウンド サービスやデーモンなど、サインインしているユーザーが存在せずに実行されるアプリには、このコンテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d480-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="2d480-120">Azure Active Directory Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d480-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="2d480-121">目的のアクセス許可をアプリケーションに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2d480-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="2d480-122">アプリケーションのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d480-122">Create a key for the application.</span></span>
4. <span data-ttu-id="2d480-123">アプリケーションとそのキーを使用してセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d480-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="2d480-124">トークンを使用して Microsoft 365 Defender API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2d480-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2d480-125">詳細については、「ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成 **[する」を参照してください](api-create-app-web.md)**。</span><span class="sxs-lookup"><span data-stu-id="2d480-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="2d480-126">ユーザー コンテキスト</span><span class="sxs-lookup"><span data-stu-id="2d480-126">User context</span></span>

<span data-ttu-id="2d480-127">このコンテキストを使用して、1 人のユーザーに代わってアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d480-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="2d480-128">Azure Active Directory ネイティブ アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d480-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="2d480-129">目的のアクセス許可をアプリケーションに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2d480-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="2d480-130">アプリケーションのユーザー資格情報を使用してセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d480-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="2d480-131">トークンを使用して Microsoft 365 Defender API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2d480-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2d480-132">詳細については、「ユーザーに代わって **[Microsoft 365 Defender API](api-create-app-user-context.md)** にアクセスするアプリを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d480-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="2d480-133">パートナー コンテキスト</span><span class="sxs-lookup"><span data-stu-id="2d480-133">Partner context</span></span>

<span data-ttu-id="2d480-134">複数のテナント間で多くのユーザーにアプリを提供する必要がある場合は、この [コンテキストを使用します](/azure/active-directory/develop/single-and-multi-tenant-apps)。</span><span class="sxs-lookup"><span data-stu-id="2d480-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="2d480-135">Azure Active Directory マルチテナント アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d480-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="2d480-136">目的のアクセス許可をアプリケーションに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2d480-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="2d480-137">各 [テナントからアプリ](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) の管理者の同意を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d480-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="2d480-138">顧客のテナント ID に基づくユーザー資格情報を使用してセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d480-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="2d480-139">トークンを使用して Microsoft 365 Defender API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2d480-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2d480-140">詳細については **[、「Microsoft 365 Defender API](api-partner-access.md)** へのパートナー アクセスを使用してアプリを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d480-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2d480-141">関連記事</span><span class="sxs-lookup"><span data-stu-id="2d480-141">Related articles</span></span>

- [<span data-ttu-id="2d480-142">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="2d480-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2d480-143">ユーザー サインインと API アクセスの OAuth 2.0 承認</span><span class="sxs-lookup"><span data-stu-id="2d480-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="2d480-144">Azure Key Vault を使用してサーバー アプリのシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="2d480-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="2d480-145">Microsoft 365 API にアクセスする 'Hello world' アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="2d480-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)