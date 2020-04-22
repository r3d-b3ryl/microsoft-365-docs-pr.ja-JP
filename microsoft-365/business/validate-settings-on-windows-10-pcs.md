---
title: Windows 10 PC でアプリの保護設定を検証する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Microsoft 365 for business アプリの保護設定がユーザーの Windows 10 デバイスで有効になっていることを確認する方法について説明します。
ms.openlocfilehash: b63681f040b0fe49127693e9cb7aac7ba6c41af6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635706"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="e75ed-103">Windows 10 PC でデバイス保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="e75ed-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="e75ed-104">Windows 10 デバイス ポリシーが設定されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="e75ed-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="e75ed-105">[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e75ed-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="e75ed-106">ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e75ed-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="e75ed-107">ユーザーは Windows 10 デバイスで windows Update および Windows Defender ウイルス対策の設定を変更できないため、多くのオプションが灰色表示されます。</span><span class="sxs-lookup"><span data-stu-id="e75ed-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="e75ed-108">[**設定**\>**更新&amp;セキュリティ** **Windows Update** \> **Restart options** Windows update の再起動オプション] に移動し、すべての設定が淡色表示になっていることを確認します。 \></span><span class="sxs-lookup"><span data-stu-id="e75ed-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![すべての再起動オプションが淡色表示されます。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="e75ed-110">[**設定** \> ] [ \*\* &amp;セキュリティ\*\* \> **Windows update** \>セキュリティ **] [詳細オプション]** の順に移動し、すべての設定が淡色表示になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e75ed-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows Advanced updates のオプションはすべて淡色表示になっています。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="e75ed-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="e75ed-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="e75ed-113">一部の設定が非表示になっているか、組織によって管理されており、すべてのオプションが灰色表示されていることを確認してください (赤)。</span><span class="sxs-lookup"><span data-stu-id="e75ed-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="e75ed-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="e75ed-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="e75ed-116">すべてのオプションが淡色表示になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e75ed-116">Verify that all options are grayed out.</span></span> 
    
    ![ウイルスおよび脅威の保護の設定は灰色表示されています。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="e75ed-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e75ed-118">Related Topics</span></span>

[<span data-ttu-id="e75ed-119">Microsoft 365 for business のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="e75ed-119">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="e75ed-120">Microsoft 365 for business の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="e75ed-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="e75ed-121">Microsoft 365 for business の管理</span><span class="sxs-lookup"><span data-stu-id="e75ed-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="e75ed-122">Windows 10 の PC のデバイス構成を設定する</span><span class="sxs-lookup"><span data-stu-id="e75ed-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

