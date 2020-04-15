---
title: Office 365 展開用の多要素認証の計画
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
description: Office 365 での多要素認証について、および設定するために従う必要のある手順について説明します。
ms.openlocfilehash: 715baeb0355ab203e890f2c87cf0751eff69e7f8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503997"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="9067b-103">Office 365 展開用の多要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="9067b-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="9067b-104">多要素認証 (MFA) では、複数の確認方法を使用することが求められ、ユーザーのサインインとトランザクションに加えてもう 1 つのセキュリティ レイヤーを追加する認証方法です。</span><span class="sxs-lookup"><span data-stu-id="9067b-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="9067b-105">これは、次のようなユーザーアカウントのパスワード以外の情報を使用して、追加の確認手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="9067b-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="9067b-106">ランダムに生成されるパス コード</span><span class="sxs-lookup"><span data-stu-id="9067b-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="9067b-107">電話</span><span class="sxs-lookup"><span data-stu-id="9067b-107">A phone call</span></span>
    
- <span data-ttu-id="9067b-108">スマート カード (仮想または物理)</span><span class="sxs-lookup"><span data-stu-id="9067b-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="9067b-109">生体認証デバイス</span><span class="sxs-lookup"><span data-stu-id="9067b-109">A biometric device</span></span> 
    
## <a name="mfa-in-office-365"></a><span data-ttu-id="9067b-110">Office 365 の MFA</span><span class="sxs-lookup"><span data-stu-id="9067b-110">MFA in Office 365</span></span>

<span data-ttu-id="9067b-111">Office 365 は、特別なサインインセキュリティに MFA を使用し、Microsoft 365 管理センターからの個々のユーザーアカウントに対して管理できます。</span><span class="sxs-lookup"><span data-stu-id="9067b-111">Office 365 uses MFA for extra sign-in security and can be managed for each individual user account from the Microsoft 365 admin center.</span></span> <span data-ttu-id="9067b-112">Office 365 には、サブスクリプションの一部として、次のような Azure 多要素認証機能のサブセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9067b-112">Office 365 offers the following subset of Azure Multi-Factor Authentication capabilities as a part of your subscription:</span></span> 
  
- <span data-ttu-id="9067b-113">エンドユーザーに対して MFA を有効にし、適用する機能</span><span class="sxs-lookup"><span data-stu-id="9067b-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="9067b-114">第 2 認証要素としてモバイル アプリ (オンラインおよびワンタイム パスワード [OTP]) を使用する</span><span class="sxs-lookup"><span data-stu-id="9067b-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="9067b-115">第 2 認証要素として電話を使用する</span><span class="sxs-lookup"><span data-stu-id="9067b-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="9067b-116">第 2 認証要素としてショート メッセージ サービス (SMS) のメッセージを使用する</span><span class="sxs-lookup"><span data-stu-id="9067b-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="9067b-117">非ブラウザークライアントのアプリケーションパスワード (たとえば、Microsoft Lync 2013 通信ソフトウェア)</span><span class="sxs-lookup"><span data-stu-id="9067b-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="9067b-118">電話認証時の既定の案内応答</span><span class="sxs-lookup"><span data-stu-id="9067b-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="9067b-p103">追加された機能の一覧については、「[バージョンごとの機能の比較](https://go.microsoft.com/fwlink/?LinkId=506927)」を参照してください。 Azure Multi-Factor Authentication サービスを購入すると、すべての機能をいつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="9067b-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="9067b-121">Office 365 または Active Directory フェデレーションサービス (AD FS) を使用したフェデレーション認証のどちらに対しても、クラウド専用またはハイブリッド id を使用しているかどうかに応じて、さまざまな機能のサブセットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9067b-121">You get a different subset of capabilities depending on whether you have a cloud-only or hybrid identity for Office 365 or federated authentication with Active Directory Federation Services (AD FS).</span></span> 
  
<span data-ttu-id="9067b-122">|**Office 365 テナントの管理場所**| **MFA の第2要素オプション**|</span><span class="sxs-lookup"><span data-stu-id="9067b-122">|**Where do you manage your Office 365 tenant?**|**MFA second factor options**|</span></span>

<span data-ttu-id="9067b-123">|:-----|:-----| |クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="9067b-123">|:-----|:-----| |Cloud only</span></span>  <br/> <span data-ttu-id="9067b-124">|Azure 多要素認証 (テキストまたは電話通話)</span><span class="sxs-lookup"><span data-stu-id="9067b-124">|Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> <span data-ttu-id="9067b-125">| |ハイブリッドセットアップ、オンプレミスで管理</span><span class="sxs-lookup"><span data-stu-id="9067b-125">| |Hybrid setup, managed on-premises</span></span>  <br/> <span data-ttu-id="9067b-126">|オンプレミスでユーザー id を管理する場合は、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="9067b-126">| If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="9067b-127">物理または仮想スマートカード (AD FS を使用している場合)</span><span class="sxs-lookup"><span data-stu-id="9067b-127">Physical or virtual smart card (when using AD FS)</span></span>  <br/> <span data-ttu-id="9067b-128">[Azure 多要素認証](https://go.microsoft.com/fwlink/p/?LinkId=526677)(AD FS のモジュール)</span><span class="sxs-lookup"><span data-stu-id="9067b-128">[Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="9067b-129">Azure Active Directory (Azure AD) 多要素認証</span><span class="sxs-lookup"><span data-stu-id="9067b-129">Azure Active Directory (Azure AD) Multi-Factor Authentication</span></span>  <br/> |
   
  
<span data-ttu-id="9067b-130">次の図は、最新の Windows 版 Office 2013 のデバイス アプリで MFA を使用してユーザーがどのようにサインインするかを示しています。</span><span class="sxs-lookup"><span data-stu-id="9067b-130">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA.</span></span> 

![Office 2013 デバイス アプリ用の先進認証。](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)

<span data-ttu-id="9067b-132">Office 2013 デバイスアプリは、 [Active Directory 認証ライブラリ (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684)を使用して多要素認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9067b-132">The Office 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="9067b-133">Azure AD は、ユーザーがサインインする Web ページをホストします。</span><span class="sxs-lookup"><span data-stu-id="9067b-133">Azure AD hosts a webpage where users can sign in.</span></span> <span data-ttu-id="9067b-134">ID プロバイダーは、Azure AD の場合も、AD FS などのフェデレーション ID プロバイダーの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9067b-134">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="9067b-135">フェデレーション ユーザーを認証する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9067b-135">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="9067b-p105">Azure AD では、Office 365 テナントのレコードで示された ID プロバイダーがホストする、サインイン用の Web ページにユーザーをリダイレクトします。 この ID プロバイダーは、ユーザーのサインイン名に指定されたドメインに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="9067b-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="9067b-138">ユーザーは、自分のデバイスに表示されたサインイン用の Web ページでサインインを行います。</span><span class="sxs-lookup"><span data-stu-id="9067b-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="9067b-139">サインインが正常に完了すると、ID プロバイダーから Azure AD にトークンが返されます。</span><span class="sxs-lookup"><span data-stu-id="9067b-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="9067b-140">Azure AD は Office デバイス アプリに JSON Web トークン (JWT) を返し、デバイス アプリは JWT を使用して Office 365 で認証されます。</span><span class="sxs-lookup"><span data-stu-id="9067b-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="9067b-141">Office 2013 クライアントアプリの要件</span><span class="sxs-lookup"><span data-stu-id="9067b-141">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="9067b-142">Office 2013 クライアント アプリで MFA を有効にするには、[クイック実行ベースのインストール](#click-to-run-based-installations)か、[MSI ベースのインストール](#msi-based-installations)かに基づいて、次のソフトウェアがインストールされている必要があります (以下に記載されているバージョンまたはそれ以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="9067b-142">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="9067b-143">Office のインストールがクイック実行または MSI ベースかどうかを判断するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9067b-143">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="9067b-144">Outlook 2013 を起動します。</span><span class="sxs-lookup"><span data-stu-id="9067b-144">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="9067b-145">[**ファイル**] メニューの [ **Office アカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9067b-145">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="9067b-146">Outlook 2013 のクイック実行インストールの場合、[ **更新オプション**] アイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9067b-146">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="9067b-147">MSI ベースのインストールの場合、[ **更新オプション**] アイテムは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9067b-147">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Office 2013 のインストールがクイック実行または MSI ベースかどうかを確認する方法](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="9067b-149">詳細については、「[モダン認証 wiki の FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9067b-149">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="9067b-150">クイック実行ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="9067b-150">Click-to-run based installations</span></span>

<span data-ttu-id="9067b-151">クイック実行ベースのインストールの場合、次のソフトウェアがインストールされている必要があります。ファイルのバージョンは、以下のファイルバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="9067b-151">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="9067b-152">ファイル バージョンが記載されているバージョンよりも古い場合は、次の手順に従って更新します。</span><span class="sxs-lookup"><span data-stu-id="9067b-152">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="9067b-153">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="9067b-153">**File name**</span></span>|<span data-ttu-id="9067b-154">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="9067b-154">**Install path on your computer**</span></span>|<span data-ttu-id="9067b-155">**ファイル バージョン**</span><span class="sxs-lookup"><span data-stu-id="9067b-155">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9067b-156">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="9067b-156">MSO.DLL</span></span>  <br/> |<span data-ttu-id="9067b-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="9067b-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="9067b-158">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="9067b-158">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="9067b-159">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="9067b-159">CSI.DLL</span></span>  <br/> |<span data-ttu-id="9067b-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="9067b-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="9067b-161">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="9067b-161">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="9067b-162">Groove</span><span class="sxs-lookup"><span data-stu-id="9067b-162">Groove.EXE</span></span>  <br/> |<span data-ttu-id="9067b-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="9067b-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="9067b-164">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="9067b-164">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="9067b-165">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="9067b-165">Outlook.exe</span></span>  <br/> |<span data-ttu-id="9067b-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="9067b-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="9067b-167">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="9067b-167">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="9067b-168">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="9067b-168">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="9067b-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="9067b-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="9067b-170">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="9067b-170">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="9067b-171">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="9067b-171">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="9067b-172">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9067b-172">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="9067b-173">可変</span><span class="sxs-lookup"><span data-stu-id="9067b-173">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="9067b-174">MSI ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="9067b-174">MSI-based installations</span></span>

<span data-ttu-id="9067b-p108">MSI ベースのインストールの場合、次のソフトウェアがインストールされている必要があります (以下に記載されているファイル バージョンまたはそれ以降のファイル バージョン)。ファイル バージョンが記載されているバージョンよりも古い場合は、サポート技術情報の更新記事の列のリンクを使用して更新します。</span><span class="sxs-lookup"><span data-stu-id="9067b-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="9067b-177">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="9067b-177">**File name**</span></span>|<span data-ttu-id="9067b-178">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="9067b-178">**Install path on your computer**</span></span>|<span data-ttu-id="9067b-179">**更新プログラムを取得する場所**</span><span class="sxs-lookup"><span data-stu-id="9067b-179">**Where to get the update**</span></span>|<span data-ttu-id="9067b-180">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="9067b-180">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9067b-181">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="9067b-181">MSO.DLL</span></span>  <br/> |<span data-ttu-id="9067b-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="9067b-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="9067b-183">KB3085480</span><span class="sxs-lookup"><span data-stu-id="9067b-183">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="9067b-184">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="9067b-184">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="9067b-185">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="9067b-185">CSI.DLL</span></span>  <br/> |<span data-ttu-id="9067b-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="9067b-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="9067b-187">KB3085504</span><span class="sxs-lookup"><span data-stu-id="9067b-187">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="9067b-188">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="9067b-188">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="9067b-189">Groove</span><span class="sxs-lookup"><span data-stu-id="9067b-189">Groove.exe</span></span>  <br/> |<span data-ttu-id="9067b-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="9067b-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="9067b-191">KB3085509</span><span class="sxs-lookup"><span data-stu-id="9067b-191">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="9067b-192">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="9067b-192">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="9067b-193">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="9067b-193">Outlook.exe</span></span>  <br/> |<span data-ttu-id="9067b-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="9067b-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="9067b-195">KB3085495</span><span class="sxs-lookup"><span data-stu-id="9067b-195">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="9067b-196">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="9067b-196">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="9067b-197">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="9067b-197">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="9067b-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="9067b-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="9067b-199">KB3055000</span><span class="sxs-lookup"><span data-stu-id="9067b-199">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="9067b-200">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="9067b-200">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="9067b-201">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="9067b-201">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="9067b-202">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9067b-202">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="9067b-203">MS14-052</span><span class="sxs-lookup"><span data-stu-id="9067b-203">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="9067b-204">該当しない</span><span class="sxs-lookup"><span data-stu-id="9067b-204">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="9067b-205">MFA を有効にする</span><span class="sxs-lookup"><span data-stu-id="9067b-205">Enable MFA</span></span>

<span data-ttu-id="9067b-206">Office 365 サブスクリプションで MFA を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9067b-206">To enable MFA for your Office 365 subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="9067b-207">必要に応じ[て、Windows デバイスで Office 2013 の先進認証を有効](enable-modern-authentication.md)にします。</span><span class="sxs-lookup"><span data-stu-id="9067b-207">If needed, [enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
2. <span data-ttu-id="9067b-208">フェデレーション認証の場合は、サードパーティ製のディレクトリサービスを使用して Azure 多要素認証を設定します。</span><span class="sxs-lookup"><span data-stu-id="9067b-208">For federated authentication, set up Azure Multi-Factor Authentication with your third-party directory service.</span></span>
    
    <span data-ttu-id="9067b-209">このプログラムに受け入れられる特定の id プロバイダーの情報については[、「Azure 多要素認証」および「サードパーティ VPN ソリューションを使用した高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9067b-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
3. <span data-ttu-id="9067b-210">[Office 365 に対して多要素認証をセットアップ](set-up-multi-factor-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="9067b-210">[Set up multi-factor authentication for Office 365](set-up-multi-factor-authentication.md).</span></span>
    
4. <span data-ttu-id="9067b-211">[Office 365 ユーザーアカウントに MFA](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14)をセットアップする方法をユーザーに知らせます。</span><span class="sxs-lookup"><span data-stu-id="9067b-211">Tell your users how to [set up MFA for their Office 365 user account](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14).</span></span> <span data-ttu-id="9067b-212">2番目の認証方法を設定した後、今後のサインインには MFA が必要になります。</span><span class="sxs-lookup"><span data-stu-id="9067b-212">After they set up their secondary authentication method, their future sign-ins will require MFA.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="9067b-213">ユーザーが Azure 多要素認証を有効にしており、モダン認証が有効になっていない Office 2013 を実行しているデバイスがある場合は、アプリパスワードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9067b-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use App Passwords.</span></span> <span data-ttu-id="9067b-214">アプリのパスワードとその使用方法/場所については、「 [Azure Multi_Factor 認証を](https://go.microsoft.com/fwlink/p/?LinkId=528178)使用したアプリパスワード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9067b-214">More information on App Passwords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="known-issues"></a><span data-ttu-id="9067b-215">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9067b-215">Known issues</span></span>
  
[<span data-ttu-id="9067b-216">Office 2013 および Office 365 ProPlus モダン認証: オンボードの前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="9067b-216">Office 2013 and Office 365 ProPlus modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="9067b-217">**Azure Multi-Factor Authentication のトラブルシューティング**</span><span class="sxs-lookup"><span data-stu-id="9067b-217">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="9067b-218">「 [Azure 多要素認証のトラブルシューティング](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9067b-218">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="9067b-219">AD FS を運用している組織のモダン認証によるサインイン問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9067b-219">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="9067b-220">**代替 ID が機能しない場合の対応策:**</span><span class="sxs-lookup"><span data-stu-id="9067b-220">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="9067b-221">How to use PowerShell to fix duplicate UPN (PowerShell を使用してユーザー プリンシパル名の重複を修正する方法)</span><span class="sxs-lookup"><span data-stu-id="9067b-221">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="9067b-222">ユーザー プリンシパル名の重複を修正するためのスクリプト</span><span class="sxs-lookup"><span data-stu-id="9067b-222">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="9067b-223">**クライアント アクセスのフィルタリング:**</span><span class="sxs-lookup"><span data-stu-id="9067b-223">**Client access filtering:**</span></span>
  
[<span data-ttu-id="9067b-224">Office 2013 と Office 365 ProPlus の先進認証およびクライアント アクセスのフィルタリング ポリシー: 導入前の注意事項</span><span class="sxs-lookup"><span data-stu-id="9067b-224">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="9067b-225">**MFA をサポートするアプリ**</span><span class="sxs-lookup"><span data-stu-id="9067b-225">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="9067b-226">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9067b-226">**Windows**</span></span>|<span data-ttu-id="9067b-227">**Mac**</span><span class="sxs-lookup"><span data-stu-id="9067b-227">**Mac**</span></span>|<span data-ttu-id="9067b-228">**iOS**</span><span class="sxs-lookup"><span data-stu-id="9067b-228">**iOS**</span></span>|<span data-ttu-id="9067b-229">**Android スマートフォン**</span><span class="sxs-lookup"><span data-stu-id="9067b-229">**Android phone**</span></span>|<span data-ttu-id="9067b-230">**Android タブレット**</span><span class="sxs-lookup"><span data-stu-id="9067b-230">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9067b-231">Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013、Skype for Business の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-231">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="9067b-232">Word 2016 for Mac、Excel 2016 for Mac、PowerPoint 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-232">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="9067b-233">Word for iPad、Excel for iPad、PowerPoint for iPad の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-233">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="9067b-234">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-234">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="9067b-235">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-235">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="9067b-236">Outlook 2013 と Outlook 2016 の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-236">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="9067b-237">Outlook 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-237">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="9067b-238">iPad 版 Outlook の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9067b-238">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

