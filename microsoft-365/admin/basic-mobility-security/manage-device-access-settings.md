---
title: Basic Mobility and Security のデバイス アクセス設定を管理する
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
description: 基本的なモビリティとセキュリティは、モバイル デバイスのセキュリティ保護と管理に役立ちます。
ms.openlocfilehash: dd9d777798c2c96776a8f9b40a3c4dfe0b95702a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876950"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="3abf2-103">Basic Mobility and Security のデバイス アクセス設定を管理する</span><span class="sxs-lookup"><span data-stu-id="3abf2-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="3abf2-104">Basic Mobility and Security を使用している場合は、Basic Mobility and Security では管理できないデバイスがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3abf2-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="3abf2-105">その場合は、基本モビリティとセキュリティExchange ActiveSyncサポートされていないモバイル デバイスMicrosoft 365メールへのアプリアクセスをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3abf2-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="3abf2-106">これにより、より多くのデバイスで組織の情報をセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="3abf2-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="3abf2-107">次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3abf2-107">Use these steps:</span></span>

1. <span data-ttu-id="3abf2-108">グローバル管理者アカウントMicrosoft 365にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3abf2-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="3abf2-109">ブラウザーで、次と入力します  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="3abf2-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="3abf2-110">基本モビリティとセキュリティを初めて使用する場合は、Microsoft 365 Business Standardセキュリティとモビリティのライセンス認証を[行います](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3abf2-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="3abf2-111">ライセンスをアクティブ化した後、コンプライアンスに関するセキュリティ Office 365[を&します](https://protection.office.com/)。</span><span class="sxs-lookup"><span data-stu-id="3abf2-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="3abf2-112">[デバイス管理デバイス ポリシー>データ損失防止 **]** に移動し、[組織全体のデバイス アクセス設定の管理   >  \*\*\*\* **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3abf2-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="3abf2-113">[ブロック **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3abf2-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="[Basic Mobility and Security block access] チェック ボックス":::

5. <span data-ttu-id="3abf2-115">[保存 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3abf2-115">Select **Save**.</span></span>

<span data-ttu-id="3abf2-116">Basic Mobility and Security がサポートするデバイスについては、「基本モビリティとセキュリティの機能」 [を参照してください](capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="3abf2-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>