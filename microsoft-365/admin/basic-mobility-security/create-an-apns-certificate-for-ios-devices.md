---
title: IOS デバイス用の APNs 証明書を作成する
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 基本的なモビリティとセキュリティで iOS デバイスを管理します。
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336985"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="78e77-103">IOS デバイス用の APNs 証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="78e77-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="78e77-104">Ipad や iPhones などの iOS デバイスを基本的なモビリティとセキュリティで管理するには、APNs 証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="78e77-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="78e77-105">グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78e77-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="78e77-106">ブラウザーで、と入力  [https://protection.office.com](https://protection.office.com/) します。</span><span class="sxs-lookup"><span data-stu-id="78e77-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="78e77-107">[ **データ損失防止**   >  **デバイス管理**] を選択し、 **iOS デバイス用の APNs 証明書**を選択します。</span><span class="sxs-lookup"><span data-stu-id="78e77-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="78e77-108">[Apple プッシュ通知の証明書の設定] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78e77-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="78e77-109">[CSR ファイルをダウンロードし、証明書の署名要求をコンピューターのどこかに保存する] を選択して、覚えておきます。</span><span class="sxs-lookup"><span data-stu-id="78e77-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="78e77-110">[  **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78e77-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="78e77-111">[APNs 証明書の作成] ページで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="78e77-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="78e77-112">Apple APNS Portal を選択して、Apple プッシュ証明書ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="78e77-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="78e77-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="78e77-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="78e77-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="78e77-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="78e77-116">[  **証明書を作成**   し、使用条件に同意します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78e77-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="78e77-117">Microsoft 365 からコンピューターにダウンロードした証明書の署名要求を参照し、[ **アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78e77-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="78e77-118">Apple プッシュ証明書ポータルによって作成された APNs 証明書をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="78e77-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="78e77-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="78e77-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="78e77-120">Microsoft 365 に戻り、[**次**へ] を選択して [     **APNS 証明書のアップロード**   ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="78e77-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="78e77-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="78e77-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="78e77-122">[  **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78e77-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="78e77-123">セットアップを完了するには、セキュリティ & コンプライアンスセンター > **セキュリティポリシー**の [デバイスの管理] [設定の管理] に戻り   >  **Device management**   >  **Manage settings**ます。</span><span class="sxs-lookup"><span data-stu-id="78e77-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
