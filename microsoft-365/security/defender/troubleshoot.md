---
title: Microsoft 365 Defender サービスの問題のトラブルシューティング
description: 既知の Microsoft 365 Defender の問題に関する解決策を見つけて回避する
keywords: Microsoft Threat Protection のトラブルシューティング、トラブルシューティング、Azure ATP、問題、アドオン、設定ページ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8d8083cbba3582c41ca91c57978675987822d0d9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065899"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="d7327-104">Microsoft 365 Defender サービスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d7327-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d7327-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d7327-105">**Applies to:**</span></span>
- <span data-ttu-id="d7327-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7327-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d7327-107">このセクションでは、Microsoft 365 Defender サービスを使用する際に発生する可能性のある問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7327-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="d7327-108">Microsoft 365 Defender コンテンツが表示される</span><span class="sxs-lookup"><span data-stu-id="d7327-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="d7327-109">ポータルでインシデント、アクション センター、ハンティングなどの機能がナビゲーション ウィンドウに表示されていない場合は、テナントに適切なライセンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d7327-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="d7327-110">詳細については、[前提条件](prerequisites.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d7327-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="d7327-111">Microsoft Defender for Identity アラートが Microsoft 365 Defender インシデントに表示されない</span><span class="sxs-lookup"><span data-stu-id="d7327-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="d7327-112">環境に Microsoft Defender for Identity が展開されているが、Microsoft 365 Defender インシデントの一部として Defender for Identity アラートが表示されない場合は、Microsoft Cloud App Security と Defender for Identity の統合が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7327-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="d7327-113">詳細については [、「Microsoft Defender for Identity integration」を参照してください](/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="d7327-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="d7327-114">サービスを有効にする設定ページはどこに表示されますか?</span><span class="sxs-lookup"><span data-stu-id="d7327-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="d7327-115">Microsoft 365 Defender を有効にするには、Microsoft 365 セキュリティ センターのナビゲーション ウィンドウから [設定] にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d7327-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="d7327-116">このナビゲーション アイテムは、前提条件のアクセス許可とライセンスを持 [っている場合にのみ表示されます](m365d-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="d7327-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>
