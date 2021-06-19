---
title: サービスMicrosoft 365 Defenderのトラブルシューティング
description: 既知の問題に対する解決策と回避策をMicrosoft 365 Defenderする
keywords: トラブルシューティングMicrosoft 365 Defenderトラブルシューティング, Microsoft Defender for Identity, issues, アドオン, 設定ページ
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
ms.openlocfilehash: 14033ffeb3d08efad7f45eb4c319ac0401b7df09
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028474"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="adb94-104">サービスMicrosoft 365 Defenderのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="adb94-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="adb94-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="adb94-105">**Applies to:**</span></span>
- <span data-ttu-id="adb94-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adb94-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="adb94-107">このセクションでは、サービスを使用する際に発生する可能性のあるMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="adb94-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="adb94-108">コンテンツが表示Microsoft 365 Defenderしない</span><span class="sxs-lookup"><span data-stu-id="adb94-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="adb94-109">ポータルでインシデント、アクション センター、ハンティングなどの機能がナビゲーション ウィンドウに表示されていない場合は、テナントに適切なライセンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="adb94-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="adb94-110">詳細については、[前提条件](prerequisites.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="adb94-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="adb94-111">Microsoft Defender for Identity アラートが、インシデントに表示Microsoft 365 Defenderされない</span><span class="sxs-lookup"><span data-stu-id="adb94-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="adb94-112">環境に Microsoft Defender for Identity が展開されているが、Microsoft 365 Defender インシデントの一部として Defender for Identity アラートが表示されない場合は、Microsoft Cloud App Security と Defender for Identity の統合が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="adb94-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="adb94-113">詳細については [、「Microsoft Defender for Identity integration」を参照してください](/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="adb94-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="adb94-114">サービスを有効にする設定ページはどこに表示されますか?</span><span class="sxs-lookup"><span data-stu-id="adb94-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="adb94-115">この機能を有効 **Microsoft 365 Defender、設定** セキュリティ センターのナビゲーション ウィンドウからMicrosoft 365アクセスします。</span><span class="sxs-lookup"><span data-stu-id="adb94-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="adb94-116">このナビゲーション アイテムは、前提条件のアクセス許可とライセンスを持 [っている場合にのみ表示されます](m365d-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="adb94-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="adb94-117">ファイル/URL の例外を作成する方法</span><span class="sxs-lookup"><span data-stu-id="adb94-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="adb94-118">誤検知とは、悪意のあるファイルまたは URL であり、脅威ではないと検出されます。</span><span class="sxs-lookup"><span data-stu-id="adb94-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="adb94-119">インジケーターを作成し、ブロックを解除して特定のファイル/URL を許可する除外を定義できます。</span><span class="sxs-lookup"><span data-stu-id="adb94-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="adb94-120">「Defender [for Endpoint」の「Address false positives/negatives」を参照してください](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。</span><span class="sxs-lookup"><span data-stu-id="adb94-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


