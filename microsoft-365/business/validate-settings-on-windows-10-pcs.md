---
title: Pc のアプリ保護設定をWindows 10する
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
description: ビジネス アプリ保護の設定Microsoft 365ユーザーのデバイスに適用されたことを確認するWindows 10します。
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925261"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="08af8-103">PC のデバイス保護設定Windows 10する</span><span class="sxs-lookup"><span data-stu-id="08af8-103">Validate device protection settings for Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="08af8-104">Windows 10 デバイス ポリシーが設定されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="08af8-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="08af8-105">[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08af8-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="08af8-106">ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="08af8-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="08af8-107">ユーザーは Windows 10 デバイスの Windows Update と Windows Defender ウイルス対策 の設定を変更できないので、多くのオプションがグレー表示されます。</span><span class="sxs-lookup"><span data-stu-id="08af8-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="08af8-108">[セキュリティの **更新設定** 更新Windows]オプションに移動し、すべての設定が \> **&amp;** \>  \> 灰色で表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="08af8-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![[再起動] オプションはすべて灰色で表示されます。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="08af8-110">[セキュリティの **設定** 更新Windows]オプションに移動し、すべての設定が灰色 \> **&amp;** \>  \> で表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="08af8-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows詳細な更新プログラムのオプションはすべて灰色で表示されます。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="08af8-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="08af8-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="08af8-113">一部の設定が非表示または組織によって管理され、すべてのオプションが灰色で表示されるというメッセージが赤で表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="08af8-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="08af8-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="08af8-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="08af8-116">すべてのオプションが灰色で表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="08af8-116">Verify that all options are grayed out.</span></span> 
    
    ![ウイルスと脅威の保護の設定は灰色で表示されます。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="08af8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="08af8-118">Related Topics</span></span>

[<span data-ttu-id="08af8-119">Microsoft 365ドキュメントとリソースの詳細</span><span class="sxs-lookup"><span data-stu-id="08af8-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="08af8-120">ビジネス向けMicrosoft 365を開始する</span><span class="sxs-lookup"><span data-stu-id="08af8-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="08af8-121">ビジネスMicrosoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="08af8-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="08af8-122">Windows 10 の PC のデバイス構成を設定する</span><span class="sxs-lookup"><span data-stu-id="08af8-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
