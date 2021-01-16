---
title: iOS デバイス用の APNs 証明書を作成する
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
description: Basic Mobility and Security で iOS デバイスを管理します。
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877082"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="c150d-103">iOS デバイス用の APNs 証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="c150d-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="c150d-104">Basic Mobility and Security で iPad や iPhone などの iOS デバイスを管理するには、ANS 証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="c150d-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="c150d-105">グローバル管理者アカウントで Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c150d-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="c150d-106">ブラウザーで、「.」と入力します  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="c150d-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="c150d-107">[ **データ損失防止デバイス**   >  **管理] を選択し**、[iOS デバイスの **APNs 証明書] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c150d-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="c150d-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span><span class="sxs-lookup"><span data-stu-id="c150d-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="c150d-109">[CSR ファイルをダウンロードする] を選択し、コンピューター上の任意の場所に証明書署名要求を保存します。</span><span class="sxs-lookup"><span data-stu-id="c150d-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="c150d-110">[次へ  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c150d-110">Select  **Next**.</span></span>

6. <span data-ttu-id="c150d-111">[APNs 証明書の作成] ページで、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="c150d-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="c150d-112">Apple APNS ポータルを選択して、Apple Push Certificates Portal を開きます。</span><span class="sxs-lookup"><span data-stu-id="c150d-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="c150d-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="c150d-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="c150d-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="c150d-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="c150d-116">[  **証明書の作成] を**   選択し、使用条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="c150d-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="c150d-117">Microsoft 365 からコンピューターにダウンロードした証明書署名要求を参照し、[アップロード] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c150d-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="c150d-118">Apple Push Certificate Portal によって作成された APNs 証明書をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c150d-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="c150d-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="c150d-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="c150d-120">Microsoft 365 に戻り、[次へ]**を選択して**[APNS 証明書のアップロード   ]  **ページに移動**   します。</span><span class="sxs-lookup"><span data-stu-id="c150d-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="c150d-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="c150d-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="c150d-122">[完了]  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c150d-122">Select  **Finish**.</span></span>

<span data-ttu-id="c150d-123">セットアップを完了するには、セキュリティ センターコンプライアンス センターに戻り&セキュリティ > **デバイス** 管理   > の管理 **の** 設定に   >  **戻る必要があります**。</span><span class="sxs-lookup"><span data-stu-id="c150d-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
