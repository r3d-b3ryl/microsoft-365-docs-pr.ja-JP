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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689115"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3dc67-104">macOS 上の Microsoft Defender for Endpoint のライセンスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3dc67-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3dc67-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3dc67-105">**Applies to:**</span></span>

- [<span data-ttu-id="3dc67-106">macOS 上のエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3dc67-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="3dc67-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3dc67-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3dc67-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3dc67-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3dc67-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3dc67-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3dc67-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3dc67-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3dc67-111">[MacOS](microsoft-defender-endpoint-mac.md)および手動展開テストまたは概念実証 (PoC) で Microsoft Defender for Endpoint を実行している間に、次のエラーが表示される場合があります。 [](mac-install-manually.md)</span><span class="sxs-lookup"><span data-stu-id="3dc67-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![ライセンス エラーのイメージ](images/no-license-found.png)

<span data-ttu-id="3dc67-113&quot;>**メッセージ：**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dc67-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;3dc67-114&quot;>ライセンスが見つかりません</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dc67-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;3dc67-115&quot;>組織が Microsoft 365 Enterprise サブスクリプションのライセンスを持たしていないように見えます。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dc67-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;3dc67-116&quot;>ヘルプについては、管理者に問い合わせてください。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dc67-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;3dc67-117&quot;>**原因:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dc67-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;3dc67-118&quot;>Microsoft Defender for Endpoint on macOS パッケージ (&quot;Download installation package") を展開またはインストールしましたが、構成スクリプト (「オンボード パッケージのダウンロード」) を実行している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3dc67-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="3dc67-119">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="3dc67-119">**Solution:**</span></span>

<span data-ttu-id="3dc67-120">ここに記載されている MicrosoftDefenderATPOnboardingMacOs.py 手順に従います。クライアント [構成](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="3dc67-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

