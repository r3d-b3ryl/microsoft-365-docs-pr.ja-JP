---
title: 基本的なモビリティとセキュリティをオフにする
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
description: グループまたはポリシーを削除して、基本のモビリティとセキュリティをオフにします。
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336962"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="5b7e0-103">基本的なモビリティとセキュリティをオフにする</span><span class="sxs-lookup"><span data-stu-id="5b7e0-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="5b7e0-104">基本的なモビリティとセキュリティを効果的に無効にするには、デバイス管理ポリシーからセキュリティグループによって定義されたユーザーのグループを削除するか、ポリシー自体を削除します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="5b7e0-105">作成したデバイスポリシーからユーザーセキュリティグループを削除して、ユーザーのグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="5b7e0-106">すべての基本的なモビリティとセキュリティデバイスポリシーを削除することによって、すべてのユーザーの基本的なモビリティとセキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="5b7e0-107">これらのオプションは、組織内のデバイスの基本的なモビリティとセキュリティの適用を削除します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="5b7e0-108">残念ながら、セットアップ後に基本的なモビリティとセキュリティを単に "準備解除" することはできません。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="5b7e0-109">ユーザーのセキュリティグループをポリシーから削除したり、ポリシー自体を削除したりすると、ユーザーのデバイスに与える影響に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="5b7e0-110">たとえば、電子メールプロファイルやキャッシュされたメールは、デバイスによっては削除されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="5b7e0-111">詳細については、「  [ポリシーを削除するか、ポリシーからユーザーを削除するとどうなりますか?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="5b7e0-112">基本的なモビリティとセキュリティデバイスポリシーからユーザーセキュリティグループを削除する</span><span class="sxs-lookup"><span data-stu-id="5b7e0-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="5b7e0-113">ブラウザーで、次のように入力  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="5b7e0-114">デバイスポリシーを選択し、[ **ポリシーの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="5b7e0-115">[  **展開**   ] ページで、[ **削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="5b7e0-116">[  **グループ**] で、セキュリティグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="5b7e0-117">[  **削除**] を選択し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="5b7e0-118">基本的なモビリティとセキュリティデバイスポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="5b7e0-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="5b7e0-119">ブラウザーで、次のように入力  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="5b7e0-120">デバイスポリシーを選択し、[  **ポリシーの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="5b7e0-121">警告ダイアログボックスで、[ **はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="5b7e0-122">組織のデバイスがまだブロックされている状態である場合にデバイスのブロックを解除する手順の詳細については、ブログ投稿「 [Office 365 のモバイルデバイス管理からのアクセス制御の削除](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b7e0-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
