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
ms.openlocfilehash: c68fdb5c1a144c6bfe1161d95e1d6808461e2456
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627706"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a><span data-ttu-id="2d223-103">Microsoft 365 の展開で多要素認証を計画する</span><span class="sxs-lookup"><span data-stu-id="2d223-103">Plan for multi-factor authentication for Microsoft 365 Deployments</span></span>

<span data-ttu-id="2d223-104">多要素認証 (MFA) では、複数の確認方法を使用することが求められ、ユーザーのサインインとトランザクションに加えてもう 1 つのセキュリティ レイヤーを追加する認証方法です。</span><span class="sxs-lookup"><span data-stu-id="2d223-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="2d223-105">これは、次のようなユーザーアカウントのパスワード以外の情報を使用して、追加の確認手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2d223-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="2d223-106">ランダムに生成されるパス コード</span><span class="sxs-lookup"><span data-stu-id="2d223-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="2d223-107">電話</span><span class="sxs-lookup"><span data-stu-id="2d223-107">A phone call</span></span>
    
- <span data-ttu-id="2d223-108">スマート カード (仮想または物理)</span><span class="sxs-lookup"><span data-stu-id="2d223-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="2d223-109">生体認証デバイス</span><span class="sxs-lookup"><span data-stu-id="2d223-109">A biometric device</span></span> 
    
## <a name="multi-factor-authentication-in-microsoft-365"></a><span data-ttu-id="2d223-110">Microsoft 365 での多要素認証</span><span class="sxs-lookup"><span data-stu-id="2d223-110">Multi-factor authentication in Microsoft 365</span></span>

<span data-ttu-id="2d223-111">Microsoft 365 では、複数要素認証を使用して、セキュリティを強化し、Microsoft 365 管理センターから管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2d223-111">Microsoft 365 uses multi-factor authentication to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="2d223-112">Microsoft 365 では、次のような Azure 多要素認証機能のサブセットをサブスクリプションの一部として提供しています。</span><span class="sxs-lookup"><span data-stu-id="2d223-112">Microsoft 365 offers the following subset of Azure multi-factor authentication capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="2d223-113">エンドユーザーに対して MFA を有効にし、適用する機能</span><span class="sxs-lookup"><span data-stu-id="2d223-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="2d223-114">第 2 認証要素としてモバイル アプリ (オンラインおよびワンタイム パスワード [OTP]) を使用する</span><span class="sxs-lookup"><span data-stu-id="2d223-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="2d223-115">第 2 認証要素として電話を使用する</span><span class="sxs-lookup"><span data-stu-id="2d223-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="2d223-116">第 2 認証要素としてショート メッセージ サービス (SMS) のメッセージを使用する</span><span class="sxs-lookup"><span data-stu-id="2d223-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="2d223-117">非ブラウザークライアントのアプリケーションパスワード (たとえば、Microsoft Lync 2013 通信ソフトウェア)</span><span class="sxs-lookup"><span data-stu-id="2d223-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="2d223-118">電話認証時の既定の案内応答</span><span class="sxs-lookup"><span data-stu-id="2d223-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="2d223-p103">追加された機能の一覧については、「[バージョンごとの機能の比較](https://go.microsoft.com/fwlink/?LinkId=506927)」を参照してください。 Azure Multi-Factor Authentication サービスを購入すると、すべての機能をいつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="2d223-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="2d223-121">さまざまな機能のサブセットを取得するには、Microsoft 365 のクラウドのみの展開、またはシングルサインオンと Active Directory フェデレーションサービス (AD FS) を使用したハイブリッドセットアップのどちらを使用するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2d223-121">You get a different subset of capabilities depending on whether you have a cloud-only deployment for Microsoft 365 or a hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="2d223-122">**Microsoft 365 を管理する場所**</span><span class="sxs-lookup"><span data-stu-id="2d223-122">**Where do you manage Microsoft 365?**</span></span>|<span data-ttu-id="2d223-123">**MFA の第 2 要素のオプション**</span><span class="sxs-lookup"><span data-stu-id="2d223-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d223-124">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="2d223-124">Cloud only</span></span>  <br/> |<span data-ttu-id="2d223-125">Azure Active Directory MFA (テキストまたは電話)</span><span class="sxs-lookup"><span data-stu-id="2d223-125">Azure Active Directory MFA (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="2d223-126">ハイブリッド セットアップ、オンプレミスで管理</span><span class="sxs-lookup"><span data-stu-id="2d223-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="2d223-127">ユーザー ID をオンプレミスで管理する場合、次のような選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="2d223-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="2d223-128">物理または仮想スマート カード (AD FS)</span><span class="sxs-lookup"><span data-stu-id="2d223-128">Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="2d223-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (AD FS 用モジュール)</span><span class="sxs-lookup"><span data-stu-id="2d223-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="2d223-130">Azure AD MFA</span><span class="sxs-lookup"><span data-stu-id="2d223-130">Azure AD MFA</span></span>  <br/> |
   
  
<span data-ttu-id="2d223-p104">次の図は、最新の Windows 版 Office 2013 のデバイス アプリで MFA を使用してユーザーがどのようにサインインするかを示しています。 Office 2013 デバイス アプリは、[Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) を使用して多要素認証をサポートしています。 Azure AD は、ユーザーがサインインする Web ページをホストします。 ID プロバイダーは、Azure AD の場合も、AD FS などのフェデレーション ID プロバイダーの場合もあります。 フェデレーション ユーザーを認証する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d223-p104">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA. TheOffice 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hosts a webpage where users can sign in. The identity provider can be Azure AD or a federated identity provider like AD FS. The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="2d223-136">Azure AD は、組織のレコードの id プロバイダーによってホストされているサインイン web ページにユーザーをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="2d223-136">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the organization.</span></span> <span data-ttu-id="2d223-137">この ID プロバイダーは、ユーザーのサインイン名に指定されたドメインに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="2d223-137">The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="2d223-138">ユーザーは、自分のデバイスに表示されたサインイン用の Web ページでサインインを行います。</span><span class="sxs-lookup"><span data-stu-id="2d223-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="2d223-139">サインインが正常に完了すると、ID プロバイダーから Azure AD にトークンが返されます。</span><span class="sxs-lookup"><span data-stu-id="2d223-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="2d223-140">Azure AD は、Office デバイスアプリに対して JSON Web Token (JWT) を返し、デバイスアプリは、Microsoft 365 を使用して JWT を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="2d223-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Microsoft 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="2d223-141">Office 2013 クライアントアプリの要件</span><span class="sxs-lookup"><span data-stu-id="2d223-141">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="2d223-142">Office 2013 クライアント アプリで MFA を有効にするには、[クイック実行ベースのインストール](#click-to-run-based-installations)か、[MSI ベースのインストール](#msi-based-installations)かに基づいて、次のソフトウェアがインストールされている必要があります (以下に記載されているバージョンまたはそれ以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="2d223-142">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="2d223-143">Office のインストールがクイック実行または MSI ベースかどうかを判断するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d223-143">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="2d223-144">Outlook 2013 を起動します。</span><span class="sxs-lookup"><span data-stu-id="2d223-144">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="2d223-145">[**ファイル**] メニューの [ **Office アカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d223-145">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="2d223-146">Outlook 2013 のクイック実行インストールの場合、[ **更新オプション**] アイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d223-146">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="2d223-147">MSI ベースのインストールの場合、[ **更新オプション**] アイテムは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2d223-147">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Office 2013 のインストールがクイック実行または MSI ベースかどうかを確認する方法](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="2d223-149">詳細については、「[モダン認証 wiki の FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d223-149">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="2d223-150">クイック実行ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="2d223-150">Click-to-run based installations</span></span>

<span data-ttu-id="2d223-151">クイック実行ベースのインストールの場合、次のソフトウェアがインストールされている必要があります。ファイルのバージョンは、以下のファイルバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="2d223-151">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="2d223-152">ファイル バージョンが記載されているバージョンよりも古い場合は、次の手順に従って更新します。</span><span class="sxs-lookup"><span data-stu-id="2d223-152">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="2d223-153">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="2d223-153">**File name**</span></span>|<span data-ttu-id="2d223-154">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="2d223-154">**Install path on your computer**</span></span>|<span data-ttu-id="2d223-155">**ファイル バージョン**</span><span class="sxs-lookup"><span data-stu-id="2d223-155">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d223-156">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2d223-156">MSO.DLL</span></span>  <br/> |<span data-ttu-id="2d223-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="2d223-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="2d223-158">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="2d223-158">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="2d223-159">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2d223-159">CSI.DLL</span></span>  <br/> |<span data-ttu-id="2d223-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="2d223-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="2d223-161">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="2d223-161">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="2d223-162">Groove</span><span class="sxs-lookup"><span data-stu-id="2d223-162">Groove.EXE</span></span>  <br/> |<span data-ttu-id="2d223-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="2d223-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="2d223-164">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="2d223-164">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="2d223-165">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="2d223-165">Outlook.exe</span></span>  <br/> |<span data-ttu-id="2d223-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="2d223-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="2d223-167">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="2d223-167">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="2d223-168">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2d223-168">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="2d223-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="2d223-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="2d223-170">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="2d223-170">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="2d223-171">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="2d223-171">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="2d223-172">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2d223-172">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="2d223-173">可変</span><span class="sxs-lookup"><span data-stu-id="2d223-173">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="2d223-174">MSI ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="2d223-174">MSI-based installations</span></span>

<span data-ttu-id="2d223-p108">MSI ベースのインストールの場合、次のソフトウェアがインストールされている必要があります (以下に記載されているファイル バージョンまたはそれ以降のファイル バージョン)。ファイル バージョンが記載されているバージョンよりも古い場合は、サポート技術情報の更新記事の列のリンクを使用して更新します。</span><span class="sxs-lookup"><span data-stu-id="2d223-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="2d223-177">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="2d223-177">**File name**</span></span>|<span data-ttu-id="2d223-178">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="2d223-178">**Install path on your computer**</span></span>|<span data-ttu-id="2d223-179">**更新プログラムを取得する場所**</span><span class="sxs-lookup"><span data-stu-id="2d223-179">**Where to get the update**</span></span>|<span data-ttu-id="2d223-180">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="2d223-180">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d223-181">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2d223-181">MSO.DLL</span></span>  <br/> |<span data-ttu-id="2d223-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="2d223-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="2d223-183">KB3085480</span><span class="sxs-lookup"><span data-stu-id="2d223-183">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="2d223-184">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="2d223-184">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="2d223-185">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2d223-185">CSI.DLL</span></span>  <br/> |<span data-ttu-id="2d223-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="2d223-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="2d223-187">KB3085504</span><span class="sxs-lookup"><span data-stu-id="2d223-187">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="2d223-188">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="2d223-188">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="2d223-189">Groove</span><span class="sxs-lookup"><span data-stu-id="2d223-189">Groove.exe</span></span>  <br/> |<span data-ttu-id="2d223-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="2d223-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="2d223-191">KB3085509</span><span class="sxs-lookup"><span data-stu-id="2d223-191">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="2d223-192">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="2d223-192">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="2d223-193">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="2d223-193">Outlook.exe</span></span>  <br/> |<span data-ttu-id="2d223-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="2d223-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="2d223-195">KB3085495</span><span class="sxs-lookup"><span data-stu-id="2d223-195">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="2d223-196">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="2d223-196">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="2d223-197">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2d223-197">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="2d223-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="2d223-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="2d223-199">KB3055000</span><span class="sxs-lookup"><span data-stu-id="2d223-199">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="2d223-200">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="2d223-200">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="2d223-201">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="2d223-201">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="2d223-202">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2d223-202">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="2d223-203">MS14-052</span><span class="sxs-lookup"><span data-stu-id="2d223-203">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="2d223-204">該当しない</span><span class="sxs-lookup"><span data-stu-id="2d223-204">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="2d223-205">MFA を有効にする</span><span class="sxs-lookup"><span data-stu-id="2d223-205">Enable MFA</span></span>

<span data-ttu-id="2d223-206">サブスクリプションで MFA を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d223-206">To enable MFA for your subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="2d223-207">必要に応じ[て、Windows デバイスで Office 2013 の先進認証を有効](enable-modern-authentication.md)にします。</span><span class="sxs-lookup"><span data-stu-id="2d223-207">If needed, [enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
  - <span data-ttu-id="2d223-208">サードパーティのディレクトリ サービスを使用して Azure MFA をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2d223-208">Set up Azure MFA with third-party directory services.</span></span>
    
    <span data-ttu-id="2d223-209">このプログラムに受け入れられる特定の id プロバイダーの情報については[、「Azure 多要素認証」および「サードパーティ VPN ソリューションを使用した高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d223-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. [<span data-ttu-id="2d223-210">Microsoft 365 用の多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2d223-210">Set up multi-factor authentication for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)
    
3. <span data-ttu-id="2d223-211">個人ユーザーに、MFA によるサインイン方法を指示します。 [2 段階認証で Microsoft 365 にサインイン](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="2d223-211">Tell individual users how to sign in by MFA: [Sign in to Microsoft 365 with 2-step verification](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d223-p109">先進認証が有効になっていない Office 2013 が実行されているデバイスをユーザーが使用している場合、ユーザーに対して Azure AD MFA を有効にしても、それらのデバイスではアプリケーション パスワードを使用する必要があります。 アプリケーション パスワード、パスワードを使用するタイミング、場所、方法については、「[Azure Multi-Factor Authentication でのアプリケーション パスワード](https://go.microsoft.com/fwlink/p/?LinkId=528178)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d223-p109">If you have enabled your users for Azure AD MFA and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices. More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span>
  
## <a name="faq"></a><span data-ttu-id="2d223-214">FAQ</span><span class="sxs-lookup"><span data-stu-id="2d223-214">FAQ</span></span>

[<span data-ttu-id="2d223-215">Wiki の記事「先進認証についてよく寄せられる質問」</span><span class="sxs-lookup"><span data-stu-id="2d223-215">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a><span data-ttu-id="2d223-216">既知の問題</span><span class="sxs-lookup"><span data-stu-id="2d223-216">Known issues</span></span>

[<span data-ttu-id="2d223-217">Office 2013 および Microsoft 365 Apps for enterprise モダン authentication: オンボードの前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="2d223-217">Office 2013 and Microsoft 365 Apps for enterprise modern authentication : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="2d223-218">**Azure Multi-Factor Authentication のトラブルシューティング**</span><span class="sxs-lookup"><span data-stu-id="2d223-218">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="2d223-219">「[Azure Multi-Factor Authentication についてよく寄せられる質問](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d223-219">See [Troubleshoot Azure MFA](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="2d223-220">AD FS を運用している組織のモダン認証によるサインイン問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2d223-220">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="2d223-221">**代替 ID が機能しない場合の対応策:**</span><span class="sxs-lookup"><span data-stu-id="2d223-221">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="2d223-222">How to use PowerShell to fix duplicate UPN (PowerShell を使用してユーザー プリンシパル名の重複を修正する方法)</span><span class="sxs-lookup"><span data-stu-id="2d223-222">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="2d223-223">ユーザー プリンシパル名の重複を修正するためのスクリプト</span><span class="sxs-lookup"><span data-stu-id="2d223-223">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="2d223-224">**クライアント アクセスのフィルタリング:**</span><span class="sxs-lookup"><span data-stu-id="2d223-224">**Client access filtering:**</span></span>
  
[<span data-ttu-id="2d223-225">エンタープライズモダン認証およびクライアントアクセスフィルターポリシー用の Office 2013 および Microsoft 365 アプリ: オンボードの前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="2d223-225">Office 2013 and Microsoft 365 Apps for enterprise modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="2d223-226">**MFA をサポートするアプリ**</span><span class="sxs-lookup"><span data-stu-id="2d223-226">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="2d223-227">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2d223-227">**Windows**</span></span>|<span data-ttu-id="2d223-228">**Mac**</span><span class="sxs-lookup"><span data-stu-id="2d223-228">**Mac**</span></span>|<span data-ttu-id="2d223-229">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2d223-229">**iOS**</span></span>|<span data-ttu-id="2d223-230">**Android スマートフォン**</span><span class="sxs-lookup"><span data-stu-id="2d223-230">**Android phone**</span></span>|<span data-ttu-id="2d223-231">**Android タブレット**</span><span class="sxs-lookup"><span data-stu-id="2d223-231">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d223-232">Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013、Skype for Business の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-232">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="2d223-233">Word 2016 for Mac、Excel 2016 for Mac、PowerPoint 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-233">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="2d223-234">Word for iPad、Excel for iPad、PowerPoint for iPad の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-234">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="2d223-235">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-235">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="2d223-236">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-236">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="2d223-237">Outlook 2013 と Outlook 2016 の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-237">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="2d223-238">Outlook 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-238">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="2d223-239">iPad 版 Outlook の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d223-239">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

