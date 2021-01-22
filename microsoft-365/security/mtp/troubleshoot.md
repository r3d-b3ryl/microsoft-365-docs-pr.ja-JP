---
title: Microsoft 365 Defender サービスの問題のトラブルシューティング
description: 既知の Microsoft 365 Defender の問題に対する解決策と回避方法を見つける
keywords: Microsoft Threat Protection のトラブルシューティング, トラブルシューティング, Azure ATP, 問題, アドオン, 設定ページ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925720"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="97883-104">Microsoft 365 Defender サービスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="97883-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="97883-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="97883-105">**Applies to:**</span></span>
- <span data-ttu-id="97883-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97883-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="97883-107">このセクションでは、Microsoft 365 Defender サービスを使用する際に発生する可能性のある問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="97883-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="97883-108">Microsoft 365 Defender コンテンツが表示できない</span><span class="sxs-lookup"><span data-stu-id="97883-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="97883-109">ポータルの [インシデント]、アクション センター、検索などの機能がナビゲーション ウィンドウに表示されていない場合は、テナントに適切なライセンスが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97883-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="97883-110">詳細については、「[前提条件](prerequisites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97883-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="97883-111">Microsoft 365 Defender のインシデントで、Id 用 Microsoft Defender のアラートが表示されない</span><span class="sxs-lookup"><span data-stu-id="97883-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="97883-112">環境に Microsoft Defender for Identity が展開されているが、Microsoft 365 Defender インシデントの一部として Id 用 Defender のアラートが表示されない場合は、Microsoft Cloud App Security と Defender for Identity の統合が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97883-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="97883-113">詳しくは [、Id 統合のための Microsoft Defender に関するページをご覧ください](https://docs.microsoft.com/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="97883-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="97883-114">サービスを有効にする設定ページの場所</span><span class="sxs-lookup"><span data-stu-id="97883-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="97883-115">Microsoft 365 Defender を有効にする場合は、Microsoft 365 セキュリティ センターのナビゲーション ウィンドウから [設定] にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="97883-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="97883-116">このナビゲーション アイテムは、必要なアクセス許可とライセンスを持 [っている場合にのみ表示されます](mtp-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="97883-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
