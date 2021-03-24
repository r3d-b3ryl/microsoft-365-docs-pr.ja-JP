---
title: フォルダー アクセスの制御を評価する
description: フォルダー アクセスの制御によって、悪意のあるアプリによってファイルが変更されるのを保護する方法について説明します。
keywords: エクスプロイト保護、Windows 10、Windows Defender、ランサムウェア、保護、評価、テスト、デモ、試す
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e5da8ec3e4555af062aad1a4ebfa96d972bee23b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065875"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="1adbc-104">フォルダー アクセスの制御を評価する</span><span class="sxs-lookup"><span data-stu-id="1adbc-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1adbc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1adbc-105">**Applies to:**</span></span>
- [<span data-ttu-id="1adbc-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1adbc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1adbc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1adbc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1adbc-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1adbc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1adbc-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="1adbc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="1adbc-110">[フォルダー アクセスの制御は](controlled-folders.md) 、疑わしいアプリや悪意のあるアプリによる変更からドキュメントやファイルを保護する機能です。</span><span class="sxs-lookup"><span data-stu-id="1adbc-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="1adbc-111">フォルダー アクセスの制御は、Windows Server 2019 および Windows 10 クライアントでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="1adbc-112">特に、ファイルを暗号化して人質[](https://www.microsoft.com/wdsi/threats/ransomware)に保持しようとするランサムウェアから保護する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="1adbc-113">この記事では、フォルダー アクセスの制御を評価するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="1adbc-114">監査モードを有効にして、組織で機能を直接テストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1adbc-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="1adbc-115">また、Microsoft Defender for Endpoint のデモ シナリオ web サイト demo.wd.microsoft.com 機能 [が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、動作を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="1adbc-116">監査モードを使用して影響を測定する</span><span class="sxs-lookup"><span data-stu-id="1adbc-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="1adbc-117">監査モードで管理フォルダー アクセスを有効にして、完全に有効にした場合に何が起こったかのレコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="1adbc-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="1adbc-118">組織で機能がどのように機能されるかをテストして、その機能が業務上のアプリに影響を与えなかねない方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="1adbc-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="1adbc-119">また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="1adbc-120">監査モードを有効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1adbc-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="1adbc-121">組織でフォルダー アクセスの制御方法を完全に監査する場合は、管理ツールを使用して、ネットワーク内のデバイスにこの設定を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1adbc-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="1adbc-122">また、グループ ポリシー、Intune、モバイル デバイス管理 (MDM)、または Microsoft Endpoint Manager を使用して、メインの管理フォルダー アクセス トピックで説明したように、設定を構成および [展開することもできます](controlled-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="1adbc-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="1adbc-123">Windows イベント ビューアーでフォルダー アクセスの制御イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="1adbc-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="1adbc-124">次の制御されたフォルダー アクセス イベントは、Microsoft/Windows/Windows Defender/操作フォルダーの下の Windows イベント ビューアーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="1adbc-125">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1adbc-125">Event ID</span></span> | <span data-ttu-id="1adbc-126">説明</span><span class="sxs-lookup"><span data-stu-id="1adbc-126">Description</span></span>
-|-
 <span data-ttu-id="1adbc-127">5007</span><span class="sxs-lookup"><span data-stu-id="1adbc-127">5007</span></span> | <span data-ttu-id="1adbc-128">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="1adbc-128">Event when settings are changed</span></span>
 <span data-ttu-id="1adbc-129">1124</span><span class="sxs-lookup"><span data-stu-id="1adbc-129">1124</span></span> | <span data-ttu-id="1adbc-130">監査されたフォルダー アクセス イベント</span><span class="sxs-lookup"><span data-stu-id="1adbc-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="1adbc-131">1123</span><span class="sxs-lookup"><span data-stu-id="1adbc-131">1123</span></span> | <span data-ttu-id="1adbc-132">ブロックされたフォルダー アクセス イベント</span><span class="sxs-lookup"><span data-stu-id="1adbc-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="1adbc-133">Windows イベント転送サブスクリプション [を構成して、](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) ログを一中心に収集できます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-133">You can configure a [Windows Event Forwarding subscription](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="1adbc-134">保護されたフォルダーとアプリをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1adbc-134">Customize protected folders and apps</span></span>

<span data-ttu-id="1adbc-135">評価中に、保護されたフォルダーの一覧に追加したり、特定のアプリでファイルを変更したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1adbc-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="1adbc-136">グループ [ポリシー](controlled-folders.md) 、PowerShell、MDM 構成サービス プロバイダー (CSP) などの管理ツールを使用して機能を構成するには、「フォルダー アクセスを制御した重要なフォルダーを保護する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1adbc-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="1adbc-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="1adbc-137">See also</span></span>

* [<span data-ttu-id="1adbc-138">フォルダー アクセスを制御して重要なフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="1adbc-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="1adbc-139">エンドポイントに対する Microsoft Defender の評価</span><span class="sxs-lookup"><span data-stu-id="1adbc-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-atp.md)
* [<span data-ttu-id="1adbc-140">監査モードの使用</span><span class="sxs-lookup"><span data-stu-id="1adbc-140">Use audit mode</span></span>](audit-windows-defender.md)
