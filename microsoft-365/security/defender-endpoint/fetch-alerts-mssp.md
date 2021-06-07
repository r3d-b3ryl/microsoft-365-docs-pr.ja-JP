---
title: MSSP カスタマー テナントからのアラートの取得
description: 顧客テナントからアラートを取得する方法について学習する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770771"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="f2128-104">MSSP カスタマー テナントからのアラートの取得</span><span class="sxs-lookup"><span data-stu-id="f2128-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2128-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f2128-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2128-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f2128-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="f2128-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="f2128-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f2128-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f2128-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="f2128-109">このアクションは MSSP によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="f2128-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="f2128-110">アラートを取得するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f2128-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="f2128-111">SIEM メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="f2128-111">Using the SIEM method</span></span>
- <span data-ttu-id="f2128-112">API の使用</span><span class="sxs-lookup"><span data-stu-id="f2128-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="f2128-113">SIEM にアラートをフェッチする</span><span class="sxs-lookup"><span data-stu-id="f2128-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="f2128-114">SIEM システムにアラートをフェッチするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2128-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="f2128-115">手順 1: サード パーティ製アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="f2128-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="f2128-116">手順 2: 顧客のテナントからアクセストークンと更新トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="f2128-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="f2128-117">手順 3: アプリケーションのインストールを許可Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="f2128-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="f2128-118">手順 1: アプリケーションを作成する (AD Azure Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="f2128-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="f2128-119">アプリケーションを作成し、顧客の Microsoft Defender for Endpoint テナントからアラートを取得するためのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2128-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="f2128-120">Azure AD [ポータルにサインインします](https://aad.portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="f2128-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="f2128-121">[アプリ  >  **Azure Active Directory] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f2128-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="f2128-122">[新規 **登録] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2128-122">Click **New registration**.</span></span>

4. <span data-ttu-id="f2128-123">次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2128-123">Specify the following values:</span></span>

    - <span data-ttu-id="f2128-124">名前: \<Tenant_name\> SIEM MSSP コネクタ (Tenant_name表示名に置き換える)</span><span class="sxs-lookup"><span data-stu-id="f2128-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="f2128-125">サポートされているアカウントの種類: この組織ディレクトリのアカウントのみ</span><span class="sxs-lookup"><span data-stu-id="f2128-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="f2128-126">リダイレクト URI: [Web] を選択して入力 `https://<domain_name>/SiemMsspConnector` します (<domain_name>テナント名に置き換えてください)</span><span class="sxs-lookup"><span data-stu-id="f2128-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="f2128-127">**[登録]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2128-127">Click **Register**.</span></span> <span data-ttu-id="f2128-128">アプリケーションは、所有するアプリケーションの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2128-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="f2128-129">アプリケーションを選択し、[概要] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2128-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="f2128-130">[アプリケーション (クライアント **) ID]** フィールドの値を安全な場所にコピーすると、次の手順でこの値が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f2128-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="f2128-131">新 **しいアプリケーション パネル& [** 証明書の秘密] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2128-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="f2128-132">[新 **しいクライアント シークレット] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2128-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="f2128-133">説明: キーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2128-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="f2128-134">有効期限: **[1 年間] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="f2128-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="f2128-135">[ **追加]** をクリックし、クライアント シークレットの値を安全な場所にコピーします。次の手順でこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2128-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="f2128-136">手順 2: 顧客のテナントからアクセストークンと更新トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="f2128-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="f2128-137">このセクションでは、PowerShell スクリプトを使用して顧客のテナントからトークンを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2128-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="f2128-138">このスクリプトでは、前の手順のアプリケーションを使用して、OAuth 認証コード を使用してアクセス トークンと更新トークンを取得Flow。</span><span class="sxs-lookup"><span data-stu-id="f2128-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="f2128-139">資格情報を指定した後、アプリケーションが顧客のテナントにプロビジョニングされるので、アプリケーションに同意を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2128-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="f2128-140">新しいフォルダーを作成し、名前を付きます `MsspTokensAcquisition` 。</span><span class="sxs-lookup"><span data-stu-id="f2128-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="f2128-141">[LoginBrowser.psm1 モジュールをダウンロードし](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1)、フォルダーに保存 `MsspTokensAcquisition` します。</span><span class="sxs-lookup"><span data-stu-id="f2128-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f2128-142">30 行目で、 に置き `authorzationUrl` 換える `authorizationUrl` 。</span><span class="sxs-lookup"><span data-stu-id="f2128-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="f2128-143">次の内容のファイルを作成し、フォルダーに名前 `MsspTokensAcquisition.ps1` を付けて保存します。</span><span class="sxs-lookup"><span data-stu-id="f2128-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="f2128-144">フォルダーで管理者特権の PowerShell コマンド プロンプトを開 `MsspTokensAcquisition` きます。</span><span class="sxs-lookup"><span data-stu-id="f2128-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="f2128-145">次のコマンドを実行します。`Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="f2128-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="f2128-146">次のコマンドを入力します。 `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="f2128-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="f2128-147">前 \<client_id\> の手順 **で取得したアプリケーション (クライアント) ID** に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="f2128-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="f2128-148">前 \<app_key\> の手順 **で作成した** クライアント シークレットに置き換える。</span><span class="sxs-lookup"><span data-stu-id="f2128-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="f2128-149">顧客 \<customer_tenant_id\> のテナント ID **に置き換える**。</span><span class="sxs-lookup"><span data-stu-id="f2128-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="f2128-150">資格情報と同意を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2128-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="f2128-151">ページ リダイレクトを無視します。</span><span class="sxs-lookup"><span data-stu-id="f2128-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="f2128-152">PowerShell ウィンドウで、アクセス トークンと更新トークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f2128-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="f2128-153">SIEM コネクタを構成するには、更新トークンを保存します。</span><span class="sxs-lookup"><span data-stu-id="f2128-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="f2128-154">手順 3: アプリケーションのインストールを許可Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="f2128-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="f2128-155">アプリケーションで作成したアプリケーションを許可する必要Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="f2128-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="f2128-156">アプリケーションを許可するには、ポータル システム設定の **管理** 権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="f2128-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="f2128-157">それ以外の場合は、アプリケーションを許可する顧客を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2128-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="f2128-158">に移動 `https://securitycenter.windows.com?tid=<customer_tenant_id>` します ( \<customer_tenant_id\> 顧客のテナント ID に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="f2128-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="f2128-159">[SIEM  >  **設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2128-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="f2128-160">**[MSSP] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="f2128-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="f2128-161">最初の **手順とテナント ID** からアプリケーション ID を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="f2128-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="f2128-162">[アプリケーション **の承認] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2128-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="f2128-163">これで、SIEM に関連する構成ファイルをダウンロードし、Defender for Endpoint API に接続できます。</span><span class="sxs-lookup"><span data-stu-id="f2128-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="f2128-164">詳細については、「SIEM ツールにアラート [をプルする」を参照してください](configure-siem.md)。</span><span class="sxs-lookup"><span data-stu-id="f2128-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="f2128-165">ArcSight 構成ファイル / Splunk Authentication Properties ファイルで、シークレット値を設定してアプリケーション キーを手動で記述します。</span><span class="sxs-lookup"><span data-stu-id="f2128-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="f2128-166">ポータルで更新トークンを取得する代わりに、前の手順のスクリプトを使用して更新トークンを取得 (または他の方法で取得) します。</span><span class="sxs-lookup"><span data-stu-id="f2128-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="f2128-167">API を使用して MSSP 顧客のテナントからアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="f2128-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="f2128-168">REST API を使用してアラートをフェッチする方法については、「REST API を使用 [してアラートをプルする」を参照してください](pull-alerts-using-rest-api.md)。</span><span class="sxs-lookup"><span data-stu-id="f2128-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="f2128-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2128-169">See also</span></span>
- [<span data-ttu-id="f2128-170">ポータルへの MSSP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="f2128-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="f2128-171">MSSP カスタマー ポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f2128-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="f2128-172">アラート通知を構成する</span><span class="sxs-lookup"><span data-stu-id="f2128-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
