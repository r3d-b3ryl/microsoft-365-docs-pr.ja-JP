---
title: API にMicrosoft 365 Defenderする
description: アプリ API にアクセスするMicrosoft 365 Defenderする
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
ms.openlocfilehash: 3cbd329c63d7cf1868083c66919773e14ed51156
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029599"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="fecb5-104">API にMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="fecb5-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fecb5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fecb5-105">**Applies to:**</span></span>

- <span data-ttu-id="fecb5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fecb5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fecb5-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="fecb5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fecb5-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="fecb5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="fecb5-109">Microsoft 365 Defender一連のプログラム API を使用して、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="fecb5-110">これらの API は、ワークフローを自動化し、ユーザーの機能をMicrosoft 365 Defenderするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fecb5-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="fecb5-111">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fecb5-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="fecb5-112">アプリケーションのAzure Active Directoryする</span><span class="sxs-lookup"><span data-stu-id="fecb5-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="fecb5-113">このアプリケーションを使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="fecb5-113">Get an access token using this application</span></span>
- <span data-ttu-id="fecb5-114">トークンを使用して API にアクセスMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="fecb5-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="fecb5-115">API アクセスには、OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="fecb5-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="fecb5-116">詳細については[、「OAuth 2.0 Authorization Code Flow」 を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="fecb5-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="fecb5-117">これらの手順を完了したら、特定のコンテキストを使用してMicrosoft 365 Defender API にアクセスする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="fecb5-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="fecb5-118">アプリケーション コンテキスト (推奨)</span><span class="sxs-lookup"><span data-stu-id="fecb5-118">Application context (Recommended)</span></span>

<span data-ttu-id="fecb5-119">バックグラウンド サービスやデーモンなど、サインインしているユーザーが存在せずに実行されるアプリには、このコンテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="fecb5-120">Web アプリケーションAzure Active Directory作成します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="fecb5-121">目的のアクセス許可をアプリケーションに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="fecb5-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="fecb5-122">アプリケーションのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-122">Create a key for the application.</span></span>
4. <span data-ttu-id="fecb5-123">アプリケーションとそのキーを使用してセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="fecb5-124">トークンを使用して API にアクセスMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="fecb5-124">Use the token to access the Microsoft 365 Defender API.</span></span>

<span data-ttu-id="fecb5-125">詳細については、「ユーザーなしでアプリに **[アクセスするアプリを作成Microsoft 365 Defenderを参照してください](api-create-app-web.md)**。</span><span class="sxs-lookup"><span data-stu-id="fecb5-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="fecb5-126">ユーザー コンテキスト</span><span class="sxs-lookup"><span data-stu-id="fecb5-126">User context</span></span>

<span data-ttu-id="fecb5-127">このコンテキストを使用して、1 人のユーザーに代わってアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="fecb5-128">ネイティブ アプリケーションAzure Active Directory作成します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="fecb5-129">目的のアクセス許可をアプリケーションに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="fecb5-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="fecb5-130">アプリケーションのユーザー資格情報を使用してセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="fecb5-131">トークンを使用して API にアクセスMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="fecb5-131">Use the token to access the Microsoft 365 Defender API.</span></span>

<span data-ttu-id="fecb5-132">詳細については、「ユーザーに代わって API にアクセスMicrosoft 365 Defenderアプリを作成する」**[を参照してください](api-create-app-user-context.md)**。</span><span class="sxs-lookup"><span data-stu-id="fecb5-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="fecb5-133">パートナー コンテキスト</span><span class="sxs-lookup"><span data-stu-id="fecb5-133">Partner context</span></span>

<span data-ttu-id="fecb5-134">複数のテナント間で多くのユーザーにアプリを提供する必要がある場合は、この [コンテキストを使用します](/azure/active-directory/develop/single-and-multi-tenant-apps)。</span><span class="sxs-lookup"><span data-stu-id="fecb5-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="fecb5-135">複数テナント アプリケーションAzure Active Directory作成します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="fecb5-136">目的のアクセス許可をアプリケーションに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="fecb5-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="fecb5-137">各 [テナントからアプリ](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) の管理者の同意を取得します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="fecb5-138">顧客のテナント ID に基づくユーザー資格情報を使用してセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="fecb5-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="fecb5-139">トークンを使用して API にアクセスMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="fecb5-139">Use the token to access the Microsoft 365 Defender API.</span></span>

<span data-ttu-id="fecb5-140">詳細については、「パートナー アクセスを **[使用してアプリを作成する」を参照Microsoft 365 Defender参照してください](api-partner-access.md)**。</span><span class="sxs-lookup"><span data-stu-id="fecb5-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fecb5-141">関連記事</span><span class="sxs-lookup"><span data-stu-id="fecb5-141">Related articles</span></span>

- [<span data-ttu-id="fecb5-142">Microsoft 365 DefenderAPI の概要</span><span class="sxs-lookup"><span data-stu-id="fecb5-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="fecb5-143">ユーザー サインインと API アクセスの OAuth 2.0 承認</span><span class="sxs-lookup"><span data-stu-id="fecb5-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="fecb5-144">Azure Key Vault を使用してサーバー アプリのシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="fecb5-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="fecb5-145">アプリケーション API にアクセスする 'Hello world' アプリケーションをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="fecb5-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
