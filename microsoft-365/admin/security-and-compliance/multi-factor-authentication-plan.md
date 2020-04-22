---
title: Microsoft 365 の展開で多要素認証を計画する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 での多要素認証について、および設定するために従う必要のある手順について説明します。
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665670"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a><span data-ttu-id="f5f45-103">Microsoft 365 の展開で多要素認証を計画する</span><span class="sxs-lookup"><span data-stu-id="f5f45-103">Plan for multi-factor authentication for Microsoft 365 deployments</span></span>

<span data-ttu-id="f5f45-104">多要素認証 (MFA) では、複数の確認方法を使用することが求められ、ユーザーのサインインとトランザクションに加えてもう 1 つのセキュリティ レイヤーを追加する認証方法です。</span><span class="sxs-lookup"><span data-stu-id="f5f45-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="f5f45-105">これは、次のようなユーザーアカウントのパスワード以外の情報を使用して、追加の確認手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f5f45-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="f5f45-106">スマートフォンに送信された、ランダムに生成された検証コード</span><span class="sxs-lookup"><span data-stu-id="f5f45-106">A randomly generated verification code sent to your smart phone</span></span>
    
- <span data-ttu-id="f5f45-107">電話</span><span class="sxs-lookup"><span data-stu-id="f5f45-107">A phone call</span></span>
    
- <span data-ttu-id="f5f45-108">スマート カード (仮想または物理)</span><span class="sxs-lookup"><span data-stu-id="f5f45-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="f5f45-109">生体認証デバイス</span><span class="sxs-lookup"><span data-stu-id="f5f45-109">A biometric device</span></span> 
    
## <a name="mfa-in-microsoft-365"></a><span data-ttu-id="f5f45-110">Microsoft 365 の MFA</span><span class="sxs-lookup"><span data-stu-id="f5f45-110">MFA in Microsoft 365</span></span>

<span data-ttu-id="f5f45-111">Microsoft 365 は、MFA を使用して、セキュリティを強化し、Microsoft 365 管理センターから管理することができます。</span><span class="sxs-lookup"><span data-stu-id="f5f45-111">Microsoft 365 uses MFA to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f5f45-112">Microsoft 365 では、次のような[Azure 多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)機能のサブセットをサブスクリプションの一部として提供しています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-112">Microsoft 365 offers the following subset of [Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="f5f45-113">エンドユーザーに対して MFA を有効にし、適用する機能</span><span class="sxs-lookup"><span data-stu-id="f5f45-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="f5f45-114">第 2 認証要素としてモバイル アプリ (オンラインおよびワンタイム パスワード [OTP]) を使用する</span><span class="sxs-lookup"><span data-stu-id="f5f45-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="f5f45-115">第 2 認証要素として電話を使用する</span><span class="sxs-lookup"><span data-stu-id="f5f45-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="f5f45-116">2番目の認証要素としての短いメッセージサービス (SMS) テキストメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="f5f45-116">The use of a Short Message Service (SMS) text message as a second authentication factor</span></span>
    
- <span data-ttu-id="f5f45-117">非ブラウザークライアントのアプリケーションパスワード (たとえば、Microsoft Lync 2013 通信ソフトウェア)</span><span class="sxs-lookup"><span data-stu-id="f5f45-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="f5f45-118">電話認証時の既定の案内応答</span><span class="sxs-lookup"><span data-stu-id="f5f45-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="f5f45-119">追加された機能の完全な一覧については、「 [Azure 多要素認証](https://go.microsoft.com/fwlink/?LinkId=506927)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f45-119">For the full list of added features, see [Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927).</span></span> <span data-ttu-id="f5f45-120">[Azure 多要素認証のライセンス](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)を購入すると、すべての機能をいつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="f5f45-120">You can always get the full functionality by purchasing [Azure Multi-Factor Authentication licenses](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing).</span></span> 
  
<span data-ttu-id="f5f45-121">ユーザーアカウントが Microsoft 365 に存在する場合は、クラウド専用の id を使用するか、シングルサインオンと Active Directory フェデレーションサービス (AD FS) を使用してセットアップするかに応じて、さまざまな機能のサブセットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="f5f45-121">You get a different subset of capabilities depending on whether you use cloud-only identity where the user accounts on exist in Microsoft 365, or hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="f5f45-122">**Microsoft 365 を管理する場所**</span><span class="sxs-lookup"><span data-stu-id="f5f45-122">**Where do you manage Microsoft 365?**</span></span>|<span data-ttu-id="f5f45-123">**MFA の第 2 要素のオプション**</span><span class="sxs-lookup"><span data-stu-id="f5f45-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f5f45-124">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="f5f45-124">Cloud only</span></span>  <br/> | <span data-ttu-id="f5f45-125">Azure 多要素認証 (テキストまたは電話通話)</span><span class="sxs-lookup"><span data-stu-id="f5f45-125">Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="f5f45-126">ハイブリッド セットアップ、オンプレミスで管理</span><span class="sxs-lookup"><span data-stu-id="f5f45-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="f5f45-127">ユーザー ID をオンプレミスで管理する場合、次のような選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="f5f45-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/> <span data-ttu-id="f5f45-128">-物理または仮想スマートカード (AD FS)</span><span class="sxs-lookup"><span data-stu-id="f5f45-128">-  Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="f5f45-129">-Azure 多要素認証 (AD FS のモジュール)</span><span class="sxs-lookup"><span data-stu-id="f5f45-129">- Azure Multi-Factor Authentication (module for AD FS)</span></span>  <br/>  <span data-ttu-id="f5f45-130">-Azure 多要素認証</span><span class="sxs-lookup"><span data-stu-id="f5f45-130">- Azure Multi-Factor Authentication</span></span>  <br/> |
   
<span data-ttu-id="f5f45-131">Office 2013 デバイスアプリは、 [Active Directory 認証ライブラリ (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684)を使用して MFA をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f5f45-131">The Office 2013 device apps support MFA through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="f5f45-132">Azure Active Directory (Azure AD) は、ユーザーがサインインできる web ページをホストします。</span><span class="sxs-lookup"><span data-stu-id="f5f45-132">Azure Active Directory (Azure AD) hosts a web page where users can sign in.</span></span> <span data-ttu-id="f5f45-133">ID プロバイダーは、Azure AD の場合も、AD FS などのフェデレーション ID プロバイダーの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f5f45-133">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="f5f45-134">フェデレーション ユーザーを認証する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f5f45-134">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="f5f45-135">Azure AD は、組織のレコードの id プロバイダーによってホストされているサインイン web ページにユーザーをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="f5f45-135">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the organization.</span></span> <span data-ttu-id="f5f45-136">この ID プロバイダーは、ユーザーのサインイン名に指定されたドメインに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="f5f45-136">The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="f5f45-137">ユーザーは、自分のデバイスに表示されたサインイン用の Web ページでサインインを行います。</span><span class="sxs-lookup"><span data-stu-id="f5f45-137">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="f5f45-138">サインインが正常に完了すると、ID プロバイダーから Azure AD にトークンが返されます。</span><span class="sxs-lookup"><span data-stu-id="f5f45-138">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="f5f45-139">Azure AD は、Office デバイスアプリに対して JSON Web Token (JWT) を返し、デバイスアプリは、Microsoft 365 を使用して JWT を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="f5f45-139">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Microsoft 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="f5f45-140">Office 2013 クライアントアプリの要件</span><span class="sxs-lookup"><span data-stu-id="f5f45-140">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="f5f45-141">Office 2013 クライアント アプリで MFA を有効にするには、[クイック実行ベースのインストール](#click-to-run-based-installations)か、[MSI ベースのインストール](#msi-based-installations)かに基づいて、次のソフトウェアがインストールされている必要があります (以下に記載されているバージョンまたはそれ以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="f5f45-141">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="f5f45-142">Office のインストールがクイック実行または MSI ベースかどうかを判断するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-142">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="f5f45-143">Outlook 2013 を起動します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-143">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="f5f45-144">[**ファイル**] メニューの [ **Office アカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5f45-144">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="f5f45-145">Outlook 2013 のクイック実行インストールの場合、[ **更新オプション**] アイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5f45-145">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="f5f45-146">MSI ベースのインストールの場合、[ **更新オプション**] アイテムは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f5f45-146">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Office 2013 のインストールがクイック実行または MSI ベースかどうかを確認する方法](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="f5f45-148">詳細については、「[モダン認証 wiki の FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f45-148">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="f5f45-149">クイック実行ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="f5f45-149">Click-to-run based installations</span></span>

<span data-ttu-id="f5f45-150">クイック実行ベースのインストールの場合、次のソフトウェアがインストールされている必要があります。ファイルのバージョンは、以下のファイルバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="f5f45-150">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="f5f45-151">ファイル バージョンが記載されているバージョンよりも古い場合は、次の手順に従って更新します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-151">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="f5f45-152">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="f5f45-152">**File name**</span></span>|<span data-ttu-id="f5f45-153">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="f5f45-153">**Install path on your computer**</span></span>|<span data-ttu-id="f5f45-154">**ファイル バージョン**</span><span class="sxs-lookup"><span data-stu-id="f5f45-154">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f5f45-155">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f5f45-155">MSO.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="f5f45-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-157">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="f5f45-157">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="f5f45-158">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f5f45-158">CSI.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="f5f45-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="f5f45-160">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="f5f45-160">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="f5f45-161">Groove</span><span class="sxs-lookup"><span data-stu-id="f5f45-161">Groove.EXE</span></span>  <br/> |<span data-ttu-id="f5f45-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="f5f45-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="f5f45-163">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="f5f45-163">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="f5f45-164">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="f5f45-164">Outlook.exe</span></span>  <br/> |<span data-ttu-id="f5f45-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="f5f45-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="f5f45-166">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="f5f45-166">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="f5f45-167">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f5f45-167">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="f5f45-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-169">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="f5f45-169">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="f5f45-170">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="f5f45-170">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="f5f45-171">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f5f45-171">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="f5f45-172">可変</span><span class="sxs-lookup"><span data-stu-id="f5f45-172">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="f5f45-173">MSI ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="f5f45-173">MSI-based installations</span></span>

<span data-ttu-id="f5f45-p108">MSI ベースのインストールの場合、次のソフトウェアがインストールされている必要があります (以下に記載されているファイル バージョンまたはそれ以降のファイル バージョン)。ファイル バージョンが記載されているバージョンよりも古い場合は、サポート技術情報の更新記事の列のリンクを使用して更新します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="f5f45-176">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="f5f45-176">**File name**</span></span>|<span data-ttu-id="f5f45-177">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="f5f45-177">**Install path on your computer**</span></span>|<span data-ttu-id="f5f45-178">**更新プログラムを取得する場所**</span><span class="sxs-lookup"><span data-stu-id="f5f45-178">**Where to get the update**</span></span>|<span data-ttu-id="f5f45-179">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="f5f45-179">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f5f45-180">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f5f45-180">MSO.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="f5f45-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="f5f45-182">KB3085480</span><span class="sxs-lookup"><span data-stu-id="f5f45-182">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="f5f45-183">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="f5f45-183">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="f5f45-184">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f5f45-184">CSI.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="f5f45-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="f5f45-186">KB3085504</span><span class="sxs-lookup"><span data-stu-id="f5f45-186">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="f5f45-187">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="f5f45-187">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="f5f45-188">Groove</span><span class="sxs-lookup"><span data-stu-id="f5f45-188">Groove.exe</span></span>  <br/> |<span data-ttu-id="f5f45-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="f5f45-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="f5f45-190">KB3085509</span><span class="sxs-lookup"><span data-stu-id="f5f45-190">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="f5f45-191">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="f5f45-191">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="f5f45-192">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="f5f45-192">Outlook.exe</span></span>  <br/> |<span data-ttu-id="f5f45-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="f5f45-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="f5f45-194">KB3085495</span><span class="sxs-lookup"><span data-stu-id="f5f45-194">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="f5f45-195">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="f5f45-195">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="f5f45-196">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f5f45-196">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="f5f45-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="f5f45-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="f5f45-198">KB3055000</span><span class="sxs-lookup"><span data-stu-id="f5f45-198">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="f5f45-199">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="f5f45-199">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="f5f45-200">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="f5f45-200">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="f5f45-201">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f5f45-201">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="f5f45-202">MS14-052</span><span class="sxs-lookup"><span data-stu-id="f5f45-202">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="f5f45-203">該当しない</span><span class="sxs-lookup"><span data-stu-id="f5f45-203">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="f5f45-204">MFA を有効にする</span><span class="sxs-lookup"><span data-stu-id="f5f45-204">Enable MFA</span></span>

<span data-ttu-id="f5f45-205">サブスクリプションで MFA を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-205">To enable MFA for your subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="f5f45-206">必要な場合:</span><span class="sxs-lookup"><span data-stu-id="f5f45-206">If needed:</span></span> 

  - <span data-ttu-id="f5f45-207">[Windows デバイスで Office 2013 の先進認証を有効に](enable-modern-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-207">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
  - <span data-ttu-id="f5f45-208">サードパーティ製のディレクトリサービスを使用して Azure 多要素認証を設定します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-208">Set up Azure Multi-Factor Authentication with third-party directory services.</span></span>
    
    <span data-ttu-id="f5f45-209">このプログラムに受け入れられる特定の id プロバイダーの情報については[、「Azure 多要素認証」および「サードパーティ VPN ソリューションを使用した高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f45-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. <span data-ttu-id="f5f45-210">[Microsoft 365 の MFA を設定](set-up-multi-factor-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-210">[Set up MFA for Microsoft 365](set-up-multi-factor-authentication.md).</span></span>
    
3. <span data-ttu-id="f5f45-211">個人ユーザーに、MFA によるサインイン方法を指示します。</span><span class="sxs-lookup"><span data-stu-id="f5f45-211">Tell individual users how to sign in by MFA.</span></span> <span data-ttu-id="f5f45-212">「 [Microsoft 365 での MFA へのサインイン」を](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb)参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f45-212">See [Sign in to Microsoft 365 with MFA](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5f45-213">ユーザーが Azure 多要素認証を有効にしていて、モダン認証が有効になっていない Office 2013 を実行しているデバイスがある場合は、それらのデバイスで AppPasswords を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f45-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices.</span></span> <span data-ttu-id="f5f45-214">AppPasswords の詳細、およびその使用方法/場所については、「 [Azure 多要素認証を](https://go.microsoft.com/fwlink/p/?LinkId=528178)使用したアプリパスワード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f45-214">More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span>
  
## <a name="faq"></a><span data-ttu-id="f5f45-215">FAQ</span><span class="sxs-lookup"><span data-stu-id="f5f45-215">FAQ</span></span>

[<span data-ttu-id="f5f45-216">Wiki の記事「先進認証についてよく寄せられる質問」</span><span class="sxs-lookup"><span data-stu-id="f5f45-216">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a><span data-ttu-id="f5f45-217">既知の問題</span><span class="sxs-lookup"><span data-stu-id="f5f45-217">Known issues</span></span>

[<span data-ttu-id="f5f45-218">Office 2013 および Microsoft 365 Apps for enterprise モダン authentication: オンボードの前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="f5f45-218">Office 2013 and Microsoft 365 Apps for enterprise modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="f5f45-219">**Azure Multi-Factor Authentication のトラブルシューティング**</span><span class="sxs-lookup"><span data-stu-id="f5f45-219">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="f5f45-220">「 [Azure 多要素認証のトラブルシューティング](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f45-220">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="f5f45-221">AD FS を運用している組織のモダン認証によるサインイン問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f5f45-221">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="f5f45-222">**代替 ID が機能しない場合の対応策:**</span><span class="sxs-lookup"><span data-stu-id="f5f45-222">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="f5f45-223">How to use PowerShell to fix duplicate UPN (PowerShell を使用してユーザー プリンシパル名の重複を修正する方法)</span><span class="sxs-lookup"><span data-stu-id="f5f45-223">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="f5f45-224">ユーザー プリンシパル名の重複を修正するためのスクリプト</span><span class="sxs-lookup"><span data-stu-id="f5f45-224">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="f5f45-225">**クライアント アクセスのフィルタリング:**</span><span class="sxs-lookup"><span data-stu-id="f5f45-225">**Client access filtering:**</span></span>
  
[<span data-ttu-id="f5f45-226">エンタープライズモダン認証およびクライアントアクセスフィルターポリシー用の Office 2013 および Microsoft 365 アプリ: オンボードの前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="f5f45-226">Office 2013 and Microsoft 365 Apps for enterprise modern authentication and client access filtering policies: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="f5f45-227">**MFA をサポートするアプリ**</span><span class="sxs-lookup"><span data-stu-id="f5f45-227">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="f5f45-228">**Windows**</span><span class="sxs-lookup"><span data-stu-id="f5f45-228">**Windows**</span></span>|<span data-ttu-id="f5f45-229">**Mac**</span><span class="sxs-lookup"><span data-stu-id="f5f45-229">**Mac**</span></span>|<span data-ttu-id="f5f45-230">**iOS**</span><span class="sxs-lookup"><span data-stu-id="f5f45-230">**iOS**</span></span>|<span data-ttu-id="f5f45-231">**Android スマートフォン**</span><span class="sxs-lookup"><span data-stu-id="f5f45-231">**Android phone**</span></span>|<span data-ttu-id="f5f45-232">**Android タブレット**</span><span class="sxs-lookup"><span data-stu-id="f5f45-232">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f5f45-233">Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013、Skype for Business の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-233">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="f5f45-234">Word 2016 for Mac、Excel 2016 for Mac、PowerPoint 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-234">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="f5f45-235">Word for iPad、Excel for iPad、PowerPoint for iPad の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-235">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="f5f45-236">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-236">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="f5f45-237">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="f5f45-238">Outlook 2013 と Outlook 2016 の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-238">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="f5f45-239">Outlook 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-239">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="f5f45-240">iPad 版 Outlook の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f45-240">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

