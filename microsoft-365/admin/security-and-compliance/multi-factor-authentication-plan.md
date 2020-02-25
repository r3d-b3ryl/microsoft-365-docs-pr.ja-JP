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
ms.openlocfilehash: c3d5e83b951e4fd4a05cb18408ecb3d26e397cf9
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257207"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="2b562-103">Office 365 展開用の多要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="2b562-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="2b562-p101">多要素認証 (MFA) では、複数の確認方法を使用することが求められ、ユーザーのサインインとトランザクションに加えてもう 1 つのセキュリティ レイヤーを追加する認証方法です。 この方法では、次のうち 2 つ以上の確認方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2b562-p101">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions. It works by requiring any two or more of the following verification methods:</span></span>
  
- <span data-ttu-id="2b562-106">ランダムに生成されるパス コード</span><span class="sxs-lookup"><span data-stu-id="2b562-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="2b562-107">電話</span><span class="sxs-lookup"><span data-stu-id="2b562-107">A phone call</span></span>
    
- <span data-ttu-id="2b562-108">スマート カード (仮想または物理)</span><span class="sxs-lookup"><span data-stu-id="2b562-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="2b562-109">生体認証デバイス</span><span class="sxs-lookup"><span data-stu-id="2b562-109">A biometric device</span></span> 
    
## <a name="multi-factor-authentication-in-office-365"></a><span data-ttu-id="2b562-110">Office 365 の多要素認証</span><span class="sxs-lookup"><span data-stu-id="2b562-110">Multi-factor authentication in Office 365</span></span>

<span data-ttu-id="2b562-111">Office 365 では、複数要素認証を使用して、セキュリティを強化し、Microsoft 365 管理センターから管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2b562-111">Office 365 uses multi-factor authentication to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="2b562-112">Office 365 では、次のような Azure 多要素認証機能のサブセットがサブスクリプションの一部として提供されています。</span><span class="sxs-lookup"><span data-stu-id="2b562-112">Office 365 offers the following subset of Azure multi-factor authentication capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="2b562-113">エンド ユーザーに対して多要素認証を有効にする、または強制する</span><span class="sxs-lookup"><span data-stu-id="2b562-113">The ability to enable and enforce multi-factor authentication for end users</span></span>
    
- <span data-ttu-id="2b562-114">第 2 認証要素としてモバイル アプリ (オンラインおよびワンタイム パスワード [OTP]) を使用する</span><span class="sxs-lookup"><span data-stu-id="2b562-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="2b562-115">第 2 認証要素として電話を使用する</span><span class="sxs-lookup"><span data-stu-id="2b562-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="2b562-116">第 2 認証要素としてショート メッセージ サービス (SMS) のメッセージを使用する</span><span class="sxs-lookup"><span data-stu-id="2b562-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="2b562-117">ブラウザー以外のクライアント (Microsoft Lync 2013 コミュニケーション ソフトウェアなど) のアプリケーション パスワード</span><span class="sxs-lookup"><span data-stu-id="2b562-117">Application passwords for non browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="2b562-118">電話認証時の既定の案内応答</span><span class="sxs-lookup"><span data-stu-id="2b562-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="2b562-p103">追加された機能の一覧については、「[バージョンごとの機能の比較](https://go.microsoft.com/fwlink/?LinkId=506927)」を参照してください。 Azure Multi-Factor Authentication サービスを購入すると、すべての機能をいつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="2b562-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="2b562-121">Office 365 をクラウドのみで展開しているか、シングル サインオンと Active Directory フェデレーション サービス (AD FS) に対応するハイブリッドをセットアップしているかに応じて、利用できる機能のサブセットは異なります。</span><span class="sxs-lookup"><span data-stu-id="2b562-121">You get a different subset of capabilities depending on whether you have a cloud-only deployment for Office 365 or a hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="2b562-122">**Office 365 テナントを管理する場所**</span><span class="sxs-lookup"><span data-stu-id="2b562-122">**Where do you manage your Office 365 tenant?**</span></span>|<span data-ttu-id="2b562-123">**MFA の第 2 要素のオプション**</span><span class="sxs-lookup"><span data-stu-id="2b562-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b562-124">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="2b562-124">Cloud only</span></span>  <br/> |<span data-ttu-id="2b562-125">Azure Active Directory MFA (テキストまたは電話)</span><span class="sxs-lookup"><span data-stu-id="2b562-125">Azure Active Directory MFA (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="2b562-126">ハイブリッド セットアップ、オンプレミスで管理</span><span class="sxs-lookup"><span data-stu-id="2b562-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="2b562-127">ユーザー ID をオンプレミスで管理する場合、次のような選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="2b562-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="2b562-128">物理または仮想スマート カード (AD FS)</span><span class="sxs-lookup"><span data-stu-id="2b562-128">Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="2b562-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (AD FS 用モジュール)</span><span class="sxs-lookup"><span data-stu-id="2b562-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="2b562-130">Azure AD MFA</span><span class="sxs-lookup"><span data-stu-id="2b562-130">Azure AD MFA</span></span>  <br/> |
   
  
<span data-ttu-id="2b562-p104">次の図は、最新の Windows 版 Office 2013 のデバイス アプリで MFA を使用してユーザーがどのようにサインインするかを示しています。 Office 2013 デバイス アプリは、[Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) を使用して多要素認証をサポートしています。 Azure AD は、ユーザーがサインインする Web ページをホストします。 ID プロバイダーは、Azure AD の場合も、AD FS などのフェデレーション ID プロバイダーの場合もあります。 フェデレーション ユーザーを認証する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2b562-p104">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA. TheOffice 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hosts a webpage where users can sign in. The identity provider can be Azure AD or a federated identity provider like AD FS. The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="2b562-p105">Azure AD では、Office 365 テナントのレコードで示された ID プロバイダーがホストする、サインイン用の Web ページにユーザーをリダイレクトします。 この ID プロバイダーは、ユーザーのサインイン名に指定されたドメインに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="2b562-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="2b562-138">ユーザーは、自分のデバイスに表示されたサインイン用の Web ページでサインインを行います。</span><span class="sxs-lookup"><span data-stu-id="2b562-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="2b562-139">サインインが正常に完了すると、ID プロバイダーから Azure AD にトークンが返されます。</span><span class="sxs-lookup"><span data-stu-id="2b562-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="2b562-140">Azure AD は Office デバイス アプリに JSON Web トークン (JWT) を返し、デバイス アプリは JWT を使用して Office 365 で認証されます。</span><span class="sxs-lookup"><span data-stu-id="2b562-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
<span data-ttu-id="2b562-141">次の図に詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="2b562-141">This is detailed in the following figure:</span></span>
  
![Office 2013 デバイス アプリ用の先進認証。](../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a><span data-ttu-id="2b562-143">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="2b562-143">Software requirements</span></span>

<span data-ttu-id="2b562-144">Office 2013 クライアント アプリで MFA を有効にするには、[クイック実行ベースのインストール](#click-to-run-based-installations)か、[MSI ベースのインストール](#msi-based-installations)かに基づいて、次のソフトウェアがインストールされている必要があります (以下に記載されているバージョンまたはそれ以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="2b562-144">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="2b562-145">Office のインストールがクイック実行または MSI ベースかどうかを判断するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b562-145">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="2b562-146">Outlook 2013 を起動します。</span><span class="sxs-lookup"><span data-stu-id="2b562-146">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="2b562-147">[**ファイル**] メニューの [ **Office アカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b562-147">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="2b562-p106">Outlook 2013 のクイック実行インストールの場合、[ **更新オプション**] アイテムが表示されます。MSI ベースのインストールの場合、[ **更新オプション**] アイテムは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2b562-p106">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="2b562-151">クイック実行ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="2b562-151">Click-to-run based installations</span></span>

<span data-ttu-id="2b562-p107">クイック実行ベースのインストールの場合、次のソフトウェアがインストールされている必要があります (以下に記載されているファイル バージョンまたはそれ以降のファイル バージョン)。ファイル バージョンが記載されているバージョンよりも古い場合は、次の手順に従って更新します。</span><span class="sxs-lookup"><span data-stu-id="2b562-p107">For Click-to-run based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="2b562-154">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="2b562-154">**File name**</span></span>|<span data-ttu-id="2b562-155">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="2b562-155">**Install path on your computer**</span></span>|<span data-ttu-id="2b562-156">**ファイル バージョン**</span><span class="sxs-lookup"><span data-stu-id="2b562-156">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2b562-157">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2b562-157">MSO.DLL</span></span>  <br/> |<span data-ttu-id="2b562-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="2b562-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="2b562-159">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="2b562-159">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="2b562-160">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2b562-160">CSI.DLL</span></span>  <br/> |<span data-ttu-id="2b562-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="2b562-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="2b562-162">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="2b562-162">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="2b562-163">Groove</span><span class="sxs-lookup"><span data-stu-id="2b562-163">Groove.EXE</span></span>  <br/> |<span data-ttu-id="2b562-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="2b562-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="2b562-165">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="2b562-165">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="2b562-166">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="2b562-166">Outlook.exe</span></span>  <br/> |<span data-ttu-id="2b562-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="2b562-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="2b562-168">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="2b562-168">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="2b562-169">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2b562-169">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="2b562-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="2b562-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="2b562-171">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="2b562-171">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="2b562-172">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="2b562-172">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="2b562-173">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2b562-173">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="2b562-174">可変</span><span class="sxs-lookup"><span data-stu-id="2b562-174">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="2b562-175">MSI ベースのインストール</span><span class="sxs-lookup"><span data-stu-id="2b562-175">MSI-based installations</span></span>

<span data-ttu-id="2b562-p108">MSI ベースのインストールの場合、次のソフトウェアがインストールされている必要があります (以下に記載されているファイル バージョンまたはそれ以降のファイル バージョン)。ファイル バージョンが記載されているバージョンよりも古い場合は、サポート技術情報の更新記事の列のリンクを使用して更新します。</span><span class="sxs-lookup"><span data-stu-id="2b562-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="2b562-178">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="2b562-178">**File name**</span></span>|<span data-ttu-id="2b562-179">**パスをコンピューターにインストールする**</span><span class="sxs-lookup"><span data-stu-id="2b562-179">**Install path on your computer**</span></span>|<span data-ttu-id="2b562-180">**更新プログラムを取得する場所**</span><span class="sxs-lookup"><span data-stu-id="2b562-180">**Where to get the update**</span></span>|<span data-ttu-id="2b562-181">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="2b562-181">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b562-182">MSO.DLL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2b562-182">MSO.DLL</span></span>  <br/> |<span data-ttu-id="2b562-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="2b562-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="2b562-184">KB3085480</span><span class="sxs-lookup"><span data-stu-id="2b562-184">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="2b562-185">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="2b562-185">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="2b562-186">CSI.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2b562-186">CSI.DLL</span></span>  <br/> |<span data-ttu-id="2b562-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="2b562-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="2b562-188">KB3085504</span><span class="sxs-lookup"><span data-stu-id="2b562-188">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="2b562-189">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="2b562-189">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="2b562-190">Groove</span><span class="sxs-lookup"><span data-stu-id="2b562-190">Groove.exe</span></span>  <br/> |<span data-ttu-id="2b562-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="2b562-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="2b562-192">KB3085509</span><span class="sxs-lookup"><span data-stu-id="2b562-192">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="2b562-193">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="2b562-193">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="2b562-194">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="2b562-194">Outlook.exe</span></span>  <br/> |<span data-ttu-id="2b562-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="2b562-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="2b562-196">KB3085495</span><span class="sxs-lookup"><span data-stu-id="2b562-196">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="2b562-197">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="2b562-197">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="2b562-198">ADAL.ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2b562-198">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="2b562-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="2b562-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="2b562-200">KB3055000</span><span class="sxs-lookup"><span data-stu-id="2b562-200">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="2b562-201">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="2b562-201">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="2b562-202">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="2b562-202">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="2b562-203">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2b562-203">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="2b562-204">MS14-052</span><span class="sxs-lookup"><span data-stu-id="2b562-204">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="2b562-205">該当しない</span><span class="sxs-lookup"><span data-stu-id="2b562-205">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="2b562-206">MFA を有効にする</span><span class="sxs-lookup"><span data-stu-id="2b562-206">Enable MFA</span></span>

<span data-ttu-id="2b562-207">MFA を有効にするには、次の手順をすべて実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b562-207">To enable MFA, you have to complete the following:</span></span>
  
1. <span data-ttu-id="2b562-208">クライアントの先進認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2b562-208">Enable clients for modern authentication:</span></span>
    
  - <span data-ttu-id="2b562-209">[Windows デバイス上の Office 2013 で先進認証を有効にします](enable-modern-authentication.md) 。</span><span class="sxs-lookup"><span data-stu-id="2b562-209">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md) .</span></span> 
    
  - <span data-ttu-id="2b562-210">サードパーティのディレクトリ サービスを使用して Azure MFA をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2b562-210">Set up Azure MFA with third-party directory services.</span></span>
    
    <span data-ttu-id="2b562-211">このプログラムに対して使用される特定の id プロバイダーの情報については、「 [Azure 多要素認証」および「サードパーティ VPN ソリューションによる高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b562-211">See the [Advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. [<span data-ttu-id="2b562-212">Office 365 用の多要素認証をセットアップします</span><span class="sxs-lookup"><span data-stu-id="2b562-212">Set up multi-factor authentication for Office 365</span></span>](set-up-multi-factor-authentication.md)
    
3. <span data-ttu-id="2b562-213">それぞれのユーザーに MFA を使ったサインイン方法を説明します。[2 段階認証で Office 365 にサインインする](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)</span><span class="sxs-lookup"><span data-stu-id="2b562-213">Tell individual users how to sign in by MFA: [Sign in to Office 365 with 2-step verification](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="2b562-p109">先進認証が有効になっていない Office 2013 が実行されているデバイスをユーザーが使用している場合、ユーザーに対して Azure AD MFA を有効にしても、それらのデバイスではアプリケーション パスワードを使用する必要があります。 アプリケーション パスワード、パスワードを使用するタイミング、場所、方法については、「[Azure Multi-Factor Authentication でのアプリケーション パスワード](https://go.microsoft.com/fwlink/p/?LinkId=528178)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b562-p109">If you have enabled your users for Azure AD MFA and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices. More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="faq"></a><span data-ttu-id="2b562-216">FAQ</span><span class="sxs-lookup"><span data-stu-id="2b562-216">FAQ</span></span>

[<span data-ttu-id="2b562-217">Wiki の記事「先進認証についてよく寄せられる質問」</span><span class="sxs-lookup"><span data-stu-id="2b562-217">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 <span data-ttu-id="2b562-218">**既知の問題**</span><span class="sxs-lookup"><span data-stu-id="2b562-218">**Known issues:**</span></span>
  
[<span data-ttu-id="2b562-219">Office 2013 と Office 365 ProPlus の先進認証: 導入前の注意事項</span><span class="sxs-lookup"><span data-stu-id="2b562-219">Office 2013 and Office 365 ProPlus modern authentication : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="2b562-220">**Azure Multi-Factor Authentication のトラブルシューティング**</span><span class="sxs-lookup"><span data-stu-id="2b562-220">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="2b562-221">「[Azure Multi-Factor Authentication についてよく寄せられる質問](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b562-221">See [Troubleshoot Azure MFA](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="2b562-222">AD FS を運用している組織のモダン認証によるサインイン問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2b562-222">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="2b562-223">**代替 ID が機能しない場合の対応策:**</span><span class="sxs-lookup"><span data-stu-id="2b562-223">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="2b562-224">How to use PowerShell to fix duplicate UPN (PowerShell を使用してユーザー プリンシパル名の重複を修正する方法)</span><span class="sxs-lookup"><span data-stu-id="2b562-224">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="2b562-225">ユーザー プリンシパル名の重複を修正するためのスクリプト</span><span class="sxs-lookup"><span data-stu-id="2b562-225">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="2b562-226">**クライアント アクセスのフィルタリング:**</span><span class="sxs-lookup"><span data-stu-id="2b562-226">**Client access filtering:**</span></span>
  
[<span data-ttu-id="2b562-227">Office 2013 と Office 365 ProPlus の先進認証およびクライアント アクセスのフィルタリング ポリシー: 導入前の注意事項</span><span class="sxs-lookup"><span data-stu-id="2b562-227">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="2b562-228">**MFA をサポートするアプリ**</span><span class="sxs-lookup"><span data-stu-id="2b562-228">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="2b562-229">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2b562-229">**Windows**</span></span>|<span data-ttu-id="2b562-230">**Mac**</span><span class="sxs-lookup"><span data-stu-id="2b562-230">**Mac**</span></span>|<span data-ttu-id="2b562-231">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2b562-231">**iOS**</span></span>|<span data-ttu-id="2b562-232">**Android スマートフォン**</span><span class="sxs-lookup"><span data-stu-id="2b562-232">**Android phone**</span></span>|<span data-ttu-id="2b562-233">**Android タブレット**</span><span class="sxs-lookup"><span data-stu-id="2b562-233">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b562-234">Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013、Skype for Business の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-234">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="2b562-235">Word 2016 for Mac、Excel 2016 for Mac、PowerPoint 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-235">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="2b562-236">Word for iPad、Excel for iPad、PowerPoint for iPad の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-236">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="2b562-237">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="2b562-238">Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-238">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="2b562-239">Outlook 2013 と Outlook 2016 の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-239">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="2b562-240">Outlook 2016 for Mac の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-240">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="2b562-241">iPad 版 Outlook の先進認証は、このリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b562-241">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

