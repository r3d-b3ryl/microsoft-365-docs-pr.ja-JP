---
title: Microsoft 365 Defender サービスに関する問題のトラブルシューティング
description: 既知の Microsoft 365 Defender に関する問題の解決策と回避策を見つける
keywords: Microsoft の脅威保護、トラブルシューティング、Azure ATP、問題、アドオン、設定ページのトラブルシューティング
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844670"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="f07c2-104">Microsoft 365 Defender サービスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f07c2-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f07c2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f07c2-105">**Applies to:**</span></span>
- <span data-ttu-id="f07c2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f07c2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f07c2-107">このセクションでは、Microsoft 365 Defender サービスの使用時に発生する可能性のある問題について取り上げます。</span><span class="sxs-lookup"><span data-stu-id="f07c2-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>


## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="f07c2-108">Microsoft 365 Defender コンテンツが表示されない</span><span class="sxs-lookup"><span data-stu-id="f07c2-108">I don't see Microsoft 365 Defender content</span></span>
<span data-ttu-id="f07c2-109">ポータルでインシデント、アクションセンター、探している機能など、ナビゲーションウィンドウに機能が表示されない場合は、テナントに適切なライセンスがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07c2-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="f07c2-110">詳細については、「[前提条件](prerequisites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f07c2-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="f07c2-111">Microsoft Defender の Id 通知は Microsoft 365 Defender インシデントに表示されません。</span><span class="sxs-lookup"><span data-stu-id="f07c2-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>
<span data-ttu-id="f07c2-112">お客様の環境に展開されている Id に対して Microsoft Defender を使用しているが、Microsoft 365 Defender インシデントの一部として Id 通知の Defender が表示されていない場合は、Microsoft Cloud App Security と Identity 統合の Defender が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07c2-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span> 

<span data-ttu-id="f07c2-113">詳細については、「 [id 統合のための Microsoft Defender](https://docs.microsoft.com/cloud-app-security/aatp-integration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f07c2-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="f07c2-114">サービスをオンにするための設定ページはどこにありますか。</span><span class="sxs-lookup"><span data-stu-id="f07c2-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="f07c2-115">Microsoft 365 Defender を有効にするには、Microsoft 365 セキュリティセンターのナビゲーションウィンドウの **設定** にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f07c2-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="f07c2-116">このナビゲーション項目は、 [必要なアクセス許可とライセンス](mtp-enable.md#check-license-eligibility-and-required-permissions)がある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f07c2-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

