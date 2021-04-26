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
description: グループまたはポリシーを削除して、Basic Mobility and Security をオフにします。
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023871"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="b2a6e-103">基本的なモビリティとセキュリティをオフにする</span><span class="sxs-lookup"><span data-stu-id="b2a6e-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="b2a6e-104">Basic Mobility and Security を効果的にオフにするには、セキュリティ グループによって定義されたユーザーのグループをデバイス管理ポリシーから削除するか、ポリシー自体を削除します。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="b2a6e-105">作成したデバイス ポリシーからユーザー セキュリティ グループを削除して、ユーザーのグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="b2a6e-106">すべての Basic Mobility および Security デバイス ポリシーを削除して、すべてのユーザーに対して基本モビリティとセキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="b2a6e-107">これらのオプションを使用すると、組織内のデバイスに対する Basic Mobility と Security の適用が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="b2a6e-108">残念ながら、基本モビリティとセキュリティをセットアップした後は、単に "プロビジョニング解除" を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="b2a6e-109">ポリシーからユーザー セキュリティ グループを削除したり、ポリシー自体を削除したりすると、ユーザーのデバイスに与える影響に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="b2a6e-110">たとえば、デバイスによっては、メール プロファイルとキャッシュされたメールが削除される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="b2a6e-111">詳細については、「ポリシーを削除するか、ポリシーからユーザーを削除するとどう  [なるか」を参照してください。](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b2a6e-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="b2a6e-112">Basic Mobility および Security デバイス ポリシーからユーザー セキュリティ グループを削除する</span><span class="sxs-lookup"><span data-stu-id="b2a6e-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="b2a6e-113">ブラウザーの種類:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) です。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="b2a6e-114">デバイス ポリシーを選択し、[ポリシーの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="b2a6e-115">[展開]  **ページで**   、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="b2a6e-116">[グループ  **] で**、セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="b2a6e-117">[削除  **] を選択** し、[保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="b2a6e-118">基本モビリティおよびセキュリティ デバイス ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="b2a6e-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="b2a6e-119">ブラウザーの種類:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) です。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="b2a6e-120">デバイス ポリシーを選択し、[ポリシーの削除]  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="b2a6e-121">[警告] ダイアログ ボックスで、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b2a6e-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="b2a6e-122">組織のデバイスがまだブロック状態にある場合にデバイスのブロックを解除する手順については、ブログ記事「モバイル デバイス管理からアクセス制御を削除する」を参照Office [365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="b2a6e-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
