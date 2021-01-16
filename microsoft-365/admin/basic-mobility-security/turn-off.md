---
title: Basic Mobility and Security をオフにする
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
description: Basic Mobility and Security をオフにするグループまたはポリシーを削除します。
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876842"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="6c329-103">Basic Mobility and Security をオフにする</span><span class="sxs-lookup"><span data-stu-id="6c329-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="6c329-104">Basic Mobility and Security を効果的にオフにするには、セキュリティ グループによって定義されたユーザーのグループをデバイス管理ポリシーから削除するか、ポリシー自体を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c329-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="6c329-105">作成したデバイス ポリシーからユーザー セキュリティ グループを削除して、ユーザーのグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="6c329-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="6c329-106">すべての Basic Mobility and Security デバイス ポリシーを削除して、すべてのユーザーに対して Basic Mobility and Security を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6c329-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="6c329-107">これらのオプションを使用すると、組織内のデバイスに対する Basic Mobility and Security の適用が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6c329-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="6c329-108">残念ながら、Basic Mobility and Security をセットアップした後は、単に"準備を解除" する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c329-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="6c329-109">ポリシーからユーザー セキュリティ グループを削除したり、ポリシー自体を削除したりすると、ユーザーのデバイスに与える影響に注意してください。</span><span class="sxs-lookup"><span data-stu-id="6c329-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="6c329-110">たとえば、デバイスによっては、メール プロファイルとキャッシュされたメールが削除される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c329-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="6c329-111">詳しくは、「ポリシーを削除した場合、またはポリシーからユーザーを削除した場合の問題  [」をご覧ください。](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="6c329-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="6c329-112">Basic Mobility and Security デバイス ポリシーからユーザー セキュリティ グループを削除する</span><span class="sxs-lookup"><span data-stu-id="6c329-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="6c329-113">ブラウザーで次の種類を入力します  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。</span><span class="sxs-lookup"><span data-stu-id="6c329-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="6c329-114">デバイス ポリシーを選択し、[ポリシーの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6c329-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="6c329-115">[展開]  **ページで**   、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6c329-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="6c329-116">[  **グループ] で**、セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c329-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="6c329-117">[削除  **] を選択** し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6c329-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="6c329-118">Basic Mobility and Security デバイス ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6c329-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="6c329-119">ブラウザーで次の種類を入力します  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。</span><span class="sxs-lookup"><span data-stu-id="6c329-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="6c329-120">デバイス ポリシーを選択し、[ポリシーの削除]  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6c329-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="6c329-121">[警告] ダイアログ ボックスで、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6c329-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="6c329-122">組織のデバイスがまだブロック状態にある場合にデバイスのブロックを解除する手順については、Office [365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)のモバイル デバイス管理からのアクセス制御の削除に関するブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c329-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
