---
title: 手順 5 - 元従業員のモバイル デバイスをワイプしてブロックする
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 次の手順に従って、元従業員のモバイル デバイス アクセスをブロックします。
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244239"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="2c853-103">手順 5 - 元従業員のモバイル デバイスをワイプしてブロックする</span><span class="sxs-lookup"><span data-stu-id="2c853-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="2c853-104">元従業員が組織の電話を持っていた場合は、Exchange 管理センターを使用してデバイスをワイプしてブロックし、すべての組織データがデバイスから削除され、Office 365 に接続できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2c853-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="2c853-105">組織で Basic Mobility and Security を使用してモバイル デバイスを管理している場合は、Basic Mobility and Security を使用してそれらのデバイスをワイプしてブロックできます。</span><span class="sxs-lookup"><span data-stu-id="2c853-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="2c853-106">管理センターでモバイル デバイスExchangeワイプする</span><span class="sxs-lookup"><span data-stu-id="2c853-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="2c853-107"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="2c853-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="2c853-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span><span class="sxs-lookup"><span data-stu-id="2c853-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="2c853-109">ユーザーを選択し、[モバイル デバイス] **で、[** 詳細の表示] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2c853-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="2c853-110">[モバイル デバイス **の詳細]** ページの [モバイル デバイス] で、モバイル デバイスを選択し、[データ ワイプ デバイスのワイプ] を選択し、[ブロック] ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2c853-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="2c853-111">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c853-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="2c853-112">オンプレミスの Blackberry Enterprise サービスからユーザーを削除またはEnterpriseしてください。</span><span class="sxs-lookup"><span data-stu-id="2c853-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="2c853-113">さらに、そのユーザーのすべての Blackberry デバイスを無効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2c853-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="2c853-114">ユーザーを無効にする具体的な手順については、「Blackberry Business Cloud Services Administration Guide」 (Blackberry Business Cloud Services 管理ガイド) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c853-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
