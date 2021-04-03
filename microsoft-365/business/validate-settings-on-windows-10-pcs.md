---
title: Windows 10 PC でアプリの保護設定を検証する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Microsoft 365 for Business アプリ保護設定がユーザーの Windows 10 デバイスに適用されたことを確認する方法について説明します。
ms.openlocfilehash: fcb463fd98f692f7d4802689e0c03fe4e3e648a1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579844"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="6eec9-103">Windows 10 PC でデバイス保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="6eec9-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="6eec9-104">Windows 10 デバイス ポリシーが設定されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="6eec9-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="6eec9-105">[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6eec9-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="6eec9-106">ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6eec9-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="6eec9-107">ユーザーは Windows Update を変更したり、Windows 10 デバイスWindows Defenderウイルス対策の設定を変更したりできないので、多くのオプションがグレー表示されます。</span><span class="sxs-lookup"><span data-stu-id="6eec9-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="6eec9-108">[設定更新 \> **プログラムの &amp; セキュリティ]** \> **[Windows Update** \> **Restart] オプションに移動** し、すべての設定が灰色で表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eec9-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![[再起動] オプションはすべて灰色で表示されます。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="6eec9-110">[設定の \> **更新] &amp; セキュリティ** \> **の [Windows Update** \> **Advanced] オプションに移動** し、すべての設定がグレー表示に設定されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eec9-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows Advanced 更新プログラムのオプションはすべて灰色で表示されます。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="6eec9-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="6eec9-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="6eec9-113">一部の設定が非表示または組織によって管理され、すべてのオプションが灰色で表示されるというメッセージが赤で表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eec9-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="6eec9-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="6eec9-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="6eec9-116">すべてのオプションが灰色で表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eec9-116">Verify that all options are grayed out.</span></span> 
    
    ![ウイルスと脅威の保護の設定は灰色で表示されます。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="6eec9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6eec9-118">Related Topics</span></span>

[<span data-ttu-id="6eec9-119">Microsoft 365 for business のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="6eec9-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="6eec9-120">Microsoft 365 for business の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6eec9-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="6eec9-121">ビジネス向け Microsoft 365 の管理</span><span class="sxs-lookup"><span data-stu-id="6eec9-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="6eec9-122">Windows 10 の PC のデバイス構成を設定する</span><span class="sxs-lookup"><span data-stu-id="6eec9-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
