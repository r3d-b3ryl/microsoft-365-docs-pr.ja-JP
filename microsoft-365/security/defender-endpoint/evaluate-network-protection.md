---
title: ネットワーク保護を評価する
description: ネットワーク保護が保護する一般的なシナリオをテストして、ネットワーク保護のしくみを確認します。
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、評価、テスト、デモ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98e4c80c2e0262712885f1e7a2da82886b2ebe80
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309368"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="8be77-104">ネットワーク保護を評価する</span><span class="sxs-lookup"><span data-stu-id="8be77-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8be77-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8be77-105">**Applies to:**</span></span>
- [<span data-ttu-id="8be77-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8be77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="8be77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8be77-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8be77-108">[ネットワーク保護](network-protection.md) は、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8be77-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="8be77-109">この記事は、機能を有効にし、テスト サイトに案内することで、ネットワーク保護を評価するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8be77-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="8be77-110">この評価記事のサイトは悪意のあるものではない。</span><span class="sxs-lookup"><span data-stu-id="8be77-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="8be77-111">悪意のあるふりをする特別に作成された Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="8be77-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="8be77-112">サイトは、ユーザーが悪意のあるサイトまたはドメインにアクセスした場合に発生する動作をレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="8be77-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="8be77-113">また、Microsoft Defender Testground の Web サイトを demo.wd.microsoft.com 他 [の保護](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 機能がどのように機能するのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="8be77-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="8be77-114">監査モードでネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="8be77-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="8be77-115">監査モードでネットワーク保護を有効にして、ブロックされた IP アドレスとドメインを確認します。</span><span class="sxs-lookup"><span data-stu-id="8be77-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="8be77-116">業務用アプリに影響を与えなかったり、ブロックが発生する頻度を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8be77-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="8be77-117">**[powershell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="8be77-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="8be77-118">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="8be77-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="8be77-119">(偽の) 悪意のあるドメインにアクセスする</span><span class="sxs-lookup"><span data-stu-id="8be77-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="8be77-120">ユーザー Internet Explorer、Google Chrome、または任意の他のブラウザーを開きます。</span><span class="sxs-lookup"><span data-stu-id="8be77-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="8be77-121">[https://smartscreentestratings2.net](https://smartscreentestratings2.net) に移動します。</span><span class="sxs-lookup"><span data-stu-id="8be77-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="8be77-122">ネットワーク接続が許可され、テスト メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8be77-122">The network connection will be allowed and a test message will be displayed.</span></span>

![[接続がブロックされました] という通知の例: IT 管理者が、このネットワークWindows セキュリティをブロックする原因になります。](images/np-notif.png)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="8be77-125">イベント ビューアーでネットワーク保護イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="8be77-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="8be77-126">ブロックされているアプリを確認するには、Microsoft-Windows-Windows-Defender/Operational ログでイベント ビューアーを開き、イベント ID 1125 をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="8be77-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="8be77-127">次の表に、すべてのネットワーク保護イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="8be77-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="8be77-128">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8be77-128">Event ID</span></span> | <span data-ttu-id="8be77-129">提供/ソース</span><span class="sxs-lookup"><span data-stu-id="8be77-129">Provide/Source</span></span> | <span data-ttu-id="8be77-130">説明</span><span class="sxs-lookup"><span data-stu-id="8be77-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="8be77-131">5007</span><span class="sxs-lookup"><span data-stu-id="8be77-131">5007</span></span> | <span data-ttu-id="8be77-132">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="8be77-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="8be77-133">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="8be77-133">Event when settings are changed</span></span> |
|<span data-ttu-id="8be77-134">1125</span><span class="sxs-lookup"><span data-stu-id="8be77-134">1125</span></span> | <span data-ttu-id="8be77-135">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="8be77-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="8be77-136">ネットワーク接続が監査された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="8be77-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="8be77-137">1126</span><span class="sxs-lookup"><span data-stu-id="8be77-137">1126</span></span> | <span data-ttu-id="8be77-138">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="8be77-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="8be77-139">ネットワーク接続がブロックされた場合のイベント</span><span class="sxs-lookup"><span data-stu-id="8be77-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="8be77-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="8be77-140">See also</span></span>

* [<span data-ttu-id="8be77-141">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="8be77-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="8be77-142">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="8be77-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="8be77-143">ネットワーク保護のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8be77-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
