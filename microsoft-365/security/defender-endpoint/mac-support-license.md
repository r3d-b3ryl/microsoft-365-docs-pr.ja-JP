---
title: Microsoft Defender ATP for Mac のライセンスの問題のトラブルシューティング
description: Microsoft Defender ATP for Mac のライセンスの問題のトラブルシューティングを行います。
keywords: microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 645c3657bdd1540ac95b68460b4dff6d25627c2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185930"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="fb906-104">Microsoft Defender for Endpoint for Mac のライセンスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fb906-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fb906-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fb906-105">**Applies to:**</span></span>

- [<span data-ttu-id="fb906-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="fb906-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="fb906-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fb906-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fb906-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb906-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fb906-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fb906-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fb906-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="fb906-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="fb906-111">[Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) [](mac-install-manually.md)および手動展開テスト、または概念実証 (PoC) を実行している間に、次のエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb906-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![ライセンス エラーのイメージ](images/no-license-found.png)

<span data-ttu-id="fb906-113">**メッセージ：**</span><span class="sxs-lookup"><span data-stu-id="fb906-113">**Message:**</span></span> 

<span data-ttu-id="fb906-114">ライセンスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="fb906-114">No license found</span></span>

<span data-ttu-id="fb906-115">組織が Microsoft 365 Enterprise サブスクリプションのライセンスを持たしていないように見えます。</span><span class="sxs-lookup"><span data-stu-id="fb906-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="fb906-116">ヘルプについては、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="fb906-116">Contact your administrator for help.</span></span>

<span data-ttu-id="fb906-117">**原因:**</span><span class="sxs-lookup"><span data-stu-id="fb906-117">**Cause:**</span></span> 

<span data-ttu-id="fb906-118">Microsoft Defender for Endpoint for macOS パッケージ ("Download installation package") を展開またはインストールしましたが、構成スクリプト (「オンボード パッケージのダウンロード」) を実行している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb906-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="fb906-119">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="fb906-119">**Solution:**</span></span>

<span data-ttu-id="fb906-120">ここに記載されている MicrosoftDefenderATPOnboardingMacOs.py 手順に従います。クライアント [構成](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="fb906-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
