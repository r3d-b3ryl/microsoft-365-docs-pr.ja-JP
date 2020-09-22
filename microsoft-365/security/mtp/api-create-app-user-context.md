---
title: ユーザーの代理として Microsoft の脅威保護 Api にアクセスする
description: ユーザーの代理として Microsoft の脅威保護 Api にアクセスする方法について説明します。
keywords: ユーザーの代理としてのアクセス、api、アプリケーション、ユーザー、アクセストークン、トークン、
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
ms.openlocfilehash: a62d90004d00e8c553f1b011e77b871df7cd94f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197799"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a><span data-ttu-id="5a4db-104">ユーザーの代わりに Microsoft の脅威保護 Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="5a4db-104">Access Microsoft Threat Protection APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5a4db-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5a4db-105">**Applies to:**</span></span>
- <span data-ttu-id="5a4db-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5a4db-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="5a4db-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="5a4db-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5a4db-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5a4db-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="5a4db-109">このページでは、ユーザーの代わりに Microsoft の脅威保護へのプログラムによるアクセスを得るためのアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a4db-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection on behalf of a user.</span></span>

<span data-ttu-id="5a4db-110">ユーザーなしで Microsoft の脅威保護にプログラムにアクセスする必要がある場合は、「 [ユーザーなしで microsoft の脅威保護にアクセスするアプリを作成](api-create-app-web.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4db-110">If you need programmatic access Microsoft Threat Protection without a user, refer to [Create an app to access Microsoft Threat Protection without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="5a4db-111">必要なアクセスが不明な場合は、「Microsoft の [脅威保護 api にアクセス](api-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4db-111">If you are not sure which access you need, read the [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="5a4db-112">Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="5a4db-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="5a4db-113">これらの Api を使用すると、Microsoft の脅威保護機能に基づいて、作業フローとイノベーションを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="5a4db-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="5a4db-114">API へのアクセスには、OAuth 2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a4db-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="5a4db-115">詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4db-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="5a4db-116">一般に、Api を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a4db-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="5a4db-117">AAD アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="5a4db-117">Create an AAD application</span></span>
- <span data-ttu-id="5a4db-118">このアプリケーションを使用してアクセストークンを取得する</span><span class="sxs-lookup"><span data-stu-id="5a4db-118">Get an access token using this application</span></span>
- <span data-ttu-id="5a4db-119">トークンを使用して Microsoft の脅威保護 API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="5a4db-119">Use the token to access Microsoft Threat Protection API</span></span>

<span data-ttu-id="5a4db-120">このページでは、AAD アプリケーションを作成する方法、Microsoft の脅威保護へのアクセストークンを取得する方法、トークンを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a4db-120">This page explains how to create an AAD application, get an access token to Microsoft Threat Protection and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="5a4db-121">ユーザーに代わって Microsoft Threat Protection API にアクセスする場合は、適切なアプリケーションのアクセス許可とユーザーのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a4db-121">When accessing Microsoft Threat Protection API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="5a4db-122">ポータルでアクションを実行するためのアクセス許可がある場合は、API でアクションを実行するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="5a4db-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="5a4db-123">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="5a4db-123">Create an app</span></span>

1. <span data-ttu-id="5a4db-124">**グローバル管理者**の役割を持つユーザーを使用して[Azure](https://portal.azure.com)にログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a4db-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="5a4db-125">**Azure Active Directory**  >  **アプリ登録**  >  の**新しい登録**に移動します。</span><span class="sxs-lookup"><span data-stu-id="5a4db-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="5a4db-127">[登録元] で、次の情報を入力し、[ **登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a4db-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![アプリケーションの作成ウィンドウのイメージ](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="5a4db-129">**Name:** アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="5a4db-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="5a4db-130">**アプリケーションの種類:** パブリッククライアント</span><span class="sxs-lookup"><span data-stu-id="5a4db-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="5a4db-131">**リダイレクト URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="5a4db-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="5a4db-132">アプリが Microsoft の脅威保護にアクセスできるようにして、it アクセス許可を割り当てるには、アプリケーションページで、[ **API アクセス**許可 api を追加する] [  >  **Add permission**  >  **組織は**> を使用します] を選択し、「 **microsoft threat protection**」と入力して、[ **microsoft threat protection**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a4db-132">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="5a4db-133">Microsoft の脅威保護は、元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5a4db-133">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="5a4db-134">テキストボックスに名前を記述して、表示されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a4db-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![API アクセスと API 選択の画像](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="5a4db-136">[委任された **アクセス許可** ] を選択して、 **インシデント**などの該当するアクセス許可を選択し、[ **アクセス許可の追加**] を選択 > ます。</span><span class="sxs-lookup"><span data-stu-id="5a4db-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read**, and then select **Add permissions**.</span></span>

      ![API アクセスと API 選択の画像](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="5a4db-138">関連するアクセス許可を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a4db-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="5a4db-139">必要なアクセス許可を確認するには、呼び出したい API の [ **Permissions** ] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4db-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="5a4db-140">[**同意を許可**する] をクリックする</span><span class="sxs-lookup"><span data-stu-id="5a4db-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="5a4db-141">アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意** を得る] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a4db-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![許可権限の画像](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="5a4db-143">アプリケーション ID とテナント ID を書き留めておきます。</span><span class="sxs-lookup"><span data-stu-id="5a4db-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="5a4db-144">アプリケーションページで、[ **概要** ] に移動し、次の内容をコピーします。</span><span class="sxs-lookup"><span data-stu-id="5a4db-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![作成されたアプリ id の画像](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="5a4db-146">PowerShell を使用してアクセストークンを取得する</span><span class="sxs-lookup"><span data-stu-id="5a4db-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="5a4db-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a4db-147">Related topics</span></span>
- [<span data-ttu-id="5a4db-148">Microsoft の脅威保護 Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="5a4db-148">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="5a4db-149">アプリケーションコンテキストを使用して Microsoft の脅威保護にアクセスする</span><span class="sxs-lookup"><span data-stu-id="5a4db-149">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
