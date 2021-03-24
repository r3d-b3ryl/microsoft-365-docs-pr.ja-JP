---
title: Microsoft Defender ATP for Mac のパフォーマンスの問題のトラブルシューティング
description: Microsoft Defender ATP for Mac のパフォーマンスの問題をトラブルシューティングします。
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
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062220"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="adbc9-104">Microsoft Defender for Endpoint for Mac のパフォーマンスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="adbc9-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="adbc9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="adbc9-105">**Applies to:**</span></span>

- [<span data-ttu-id="adbc9-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="adbc9-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="adbc9-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="adbc9-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="adbc9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adbc9-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="adbc9-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="adbc9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="adbc9-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="adbc9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="adbc9-111">このトピックでは、Microsoft Defender for Endpoint for Mac に関連するパフォーマンスの問題を絞り込む一般的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="adbc9-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="adbc9-112">リアルタイム保護 (RTP) は、Microsoft Defender for Endpoint for Mac の機能であり、デバイスを継続的に監視し、脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="adbc9-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="adbc9-113">ファイルとプロセスの監視、その他のヒューリスティックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="adbc9-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="adbc9-114">実行中のアプリケーションとデバイスの特性によっては、Microsoft Defender for Endpoint for Mac を実行するときに最適でないパフォーマンスが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="adbc9-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="adbc9-115">特に、短時間で多くのリソースにアクセスするアプリケーションまたはシステム プロセスは、Microsoft Defender for Endpoint for Mac のパフォーマンスの問題につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="adbc9-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="adbc9-116">次の手順を使用して、これらの問題のトラブルシューティングと軽減を行います。</span><span class="sxs-lookup"><span data-stu-id="adbc9-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="adbc9-117">次のいずれかの方法を使用してリアルタイム保護を無効にし、パフォーマンスが向上するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="adbc9-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="adbc9-118">この方法は、Microsoft Defender for Endpoint for Mac がパフォーマンスの問題に貢献するかどうかを絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="adbc9-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="adbc9-119">デバイスが組織によって管理されていない場合は、次のいずれかのオプションを使用してリアルタイム保護を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="adbc9-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="adbc9-120">ユーザー インターフェイスから。</span><span class="sxs-lookup"><span data-stu-id="adbc9-120">From the user interface.</span></span> <span data-ttu-id="adbc9-121">Microsoft Defender for Endpoint for Mac を開き、[設定の管理] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="adbc9-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![リアルタイム保護のスクリーンショットを管理する](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="adbc9-123">ターミナルから。</span><span class="sxs-lookup"><span data-stu-id="adbc9-123">From the Terminal.</span></span> <span data-ttu-id="adbc9-124">セキュリティ上の目的で、この操作には昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="adbc9-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="adbc9-125">デバイスが組織によって管理されている場合は [、「Microsoft Defender for Endpoint for Mac](mac-preferences.md)の設定」の手順に従って、管理者がリアルタイム保護を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="adbc9-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="adbc9-126">Finder を開き、[アプリケーション ユーティリティ **]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="adbc9-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="adbc9-127">[ **アクティビティ モニター] を** 開き、システムでリソースを使用しているアプリケーションを分析します。</span><span class="sxs-lookup"><span data-stu-id="adbc9-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="adbc9-128">一般的な例としては、ソフトウェアアップデータとコンパイラが含まれます。</span><span class="sxs-lookup"><span data-stu-id="adbc9-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="adbc9-129">パフォーマンスの問題に寄与するプロセスまたはディスクの場所の除外を使用して Microsoft Defender for Endpoint for Mac を構成し、リアルタイム保護を再び有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="adbc9-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="adbc9-130">詳細 [については、「Configure and validate exclusions for Microsoft Defender for Endpoint for Mac」](mac-exclusions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adbc9-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
