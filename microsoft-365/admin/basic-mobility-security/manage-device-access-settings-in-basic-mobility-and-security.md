---
title: 基本的なモビリティとセキュリティでデバイスアクセス設定を管理する
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティは、モバイルデバイスをセキュリティで保護し、管理するのに役立ちます。
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336963"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="511dd-103">基本的なモビリティとセキュリティでデバイスアクセス設定を管理する</span><span class="sxs-lookup"><span data-stu-id="511dd-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="511dd-104">基本的なモビリティとセキュリティを使用している場合は、基本的なモビリティとセキュリティで管理できないデバイスが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="511dd-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="511dd-105">その場合は、基本的なモビリティとセキュリティでサポートされていないモバイルデバイスに対して、Exchange ActiveSync アプリの Microsoft 365 メールへのアクセスをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="511dd-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="511dd-106">これにより、組織の情報をより多くのデバイスで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="511dd-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="511dd-107">次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="511dd-107">Use these steps:</span></span>

1. <span data-ttu-id="511dd-108">グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="511dd-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="511dd-109">ブラウザーで、次のように入力  [https://protection.office.com](https://protection.office.com/) します。</span><span class="sxs-lookup"><span data-stu-id="511dd-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="511dd-110">初めて MDM を Microsoft 365 Business Standard 用に使用している場合は、「activate the [Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="511dd-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="511dd-111">ライセンス認証を行った後、 [Office 365 セキュリティ & コンプライアンス](https://protection.office.com/)を使用してデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="511dd-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="511dd-112">[データ損失防止 > **デバイス管理**   >  **デバイスポリシー**] に移動し、[ **組織全体のデバイスアクセス設定の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="511dd-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="511dd-113">[ **ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="511dd-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本的なモビリティおよびセキュリティブロックアクセスのチェックボックス":::

5. <span data-ttu-id="511dd-115">[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="511dd-115">Select **Save**.</span></span> 

<span data-ttu-id="511dd-116">基本的なモビリティとセキュリティでサポートされるデバイスについては、「 [ベーシックモビリティとセキュリティの機能](capabilities-of-basic-mobility-and-secruity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="511dd-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>