---
title: デバイスの削除
description: Microsoft Managed Desktop 管理からデバイスを削除する
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893813"
---
# <a name="remove-devices"></a><span data-ttu-id="95c67-103">デバイスの削除</span><span class="sxs-lookup"><span data-stu-id="95c67-103">Remove devices</span></span>

<span data-ttu-id="95c67-104">管理ポータルを使用して、Microsoft Managed Desktop 管理からデバイスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="95c67-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="95c67-105">このアクションは永続的ですが、登録手順に従って Microsoft Managed Desktop に再度 [登録できます](../get-started/register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="95c67-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="95c67-106">デバイスを削除すると、次のすべてが発生します。</span><span class="sxs-lookup"><span data-stu-id="95c67-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="95c67-107">Autopilot からデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="95c67-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="95c67-108">すべての "モダン ワークプレース" デバイス グループからデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="95c67-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="95c67-109">管理ポータルの [デバイス] **ブレード** からデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="95c67-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="95c67-110">デバイスを削除する場合は、Azure Active Directory (Azure Active Directory) と Microsoft Intune からデバイスを削除ADオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="95c67-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="95c67-111">デバイスに関連するオブジェクトを Azure AD Microsoft Intune から削除すると、永続的です。</span><span class="sxs-lookup"><span data-stu-id="95c67-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="95c67-112">オブジェクトを削除すると、Intune および Azure ポータルからデバイスを表示または管理できません。</span><span class="sxs-lookup"><span data-stu-id="95c67-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="95c67-113">デバイスは会社の企業リソースにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="95c67-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="95c67-114">デバイスが削除された後にサインインしようとする場合、会社のデータが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95c67-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="95c67-115">[Microsoft Endpoint Manager で、](https://endpoint.microsoft.com/)左側 **のナビゲーション ウィンドウで**[デバイス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95c67-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="95c67-116">メニューの **[Microsoft Managed Desktop]** セクションを探し、[デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="95c67-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="95c67-117">[Microsoft Managed Desktop Devices] ワークスペースで、削除するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c67-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="95c67-118">[ **デバイスの操作]** を選択し、[デバイスの **削除]** を選択して、フライインを開いてデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="95c67-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="95c67-119">フライインで、選択したデバイスを確認し、[デバイスの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95c67-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="95c67-120">Azure オブジェクトと Intune オブジェクトAD同時に削除する場合は、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="95c67-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="95c67-121">デバイスの削除が完了するには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95c67-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="95c67-122">保留中の登録状態にあるデバイス **は** 削除できません。</span><span class="sxs-lookup"><span data-stu-id="95c67-122">You can't remove devices that are in a **pending** registration state.</span></span>