---
title: Microsoft Defender for Endpoint サービスに関する問題のトラブルシューティング
description: サービスにアクセスしようとするときにサーバー エラーなどの既知の問題に対する解決策と回避策を見つける。
keywords: Microsoft Defender for Endpoint のトラブルシューティング、サーバー エラー、アクセス拒否、無効な資格情報、データなし、ダッシュボード ポータル、許可、イベント ビューアー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 8aaea65c617300a16f99a9a3e3a62d94b7983198
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538353"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="c60f3-104">サービスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c60f3-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c60f3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c60f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="c60f3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c60f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c60f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c60f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c60f3-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c60f3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c60f3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c60f3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="c60f3-110">このセクションでは、Microsoft Defender for Endpoint サービスを使用する際に発生する可能性のある問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="c60f3-110">This section addresses issues that might arise as you use the Microsoft Defender for Endpoint service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="c60f3-111">サーバー エラー - 無効な資格情報が原因でアクセスが拒否されました</span><span class="sxs-lookup"><span data-stu-id="c60f3-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="c60f3-112">サービスにアクセスしようとするときにサーバー エラーが発生した場合は、ブラウザーの Cookie 設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c60f3-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="c60f3-113">Cookie を許可するブラウザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c60f3-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="c60f3-114">ポータルに存在する要素またはデータ</span><span class="sxs-lookup"><span data-stu-id="c60f3-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="c60f3-115">一部の要素やデータがMicrosoft Defender セキュリティ センタープロキシ設定によってブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c60f3-115">If some elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="c60f3-116">プロキシ許可リスト `*.securitycenter.windows.com` が含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="c60f3-116">Make sure that `*.securitycenter.windows.com` is included the proxy allowlist.</span></span>


> [!NOTE]
> <span data-ttu-id="c60f3-117">次のエンドポイントを追加する場合は、HTTPS プロトコルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c60f3-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="c60f3-118">Microsoft Defender for Endpoint Service は、イベント ビューアーにイベント ログまたはエラー ログを表示します。</span><span class="sxs-lookup"><span data-stu-id="c60f3-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="c60f3-119">Microsoft [](event-error-codes.md) Defender for Endpoint サービスによって報告されるイベントの一覧については、「イベント ビューアーを使用してイベントとエラーを確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c60f3-119">See [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="c60f3-120">この記事には、イベント エラーのトラブルシューティング手順も含まれています。</span><span class="sxs-lookup"><span data-stu-id="c60f3-120">The article also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="c60f3-121">Microsoft Defender for Endpoint service が再起動後に開始に失敗し、エラー 577 が表示される</span><span class="sxs-lookup"><span data-stu-id="c60f3-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="c60f3-122">デバイスのオンボードが正常に完了したが、再起動後に Microsoft Defender for Endpoint が起動し、エラー 577 が表示される場合は、Windows Defender がポリシーによって無効にされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="c60f3-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="c60f3-123">詳細については、「ポリシーによって[無効Microsoft Defender ウイルス対策を確認する」を参照してください](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="c60f3-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="c60f3-124">地域の形式に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="c60f3-124">Known issues with regional formats</span></span>

<span data-ttu-id="c60f3-125">**日付と時刻の形式**</span><span class="sxs-lookup"><span data-stu-id="c60f3-125">**Date and time formats**</span></span><br>
<span data-ttu-id="c60f3-126">時刻と日付の形式にはいくつかの既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="c60f3-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="c60f3-127">次の日付形式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c60f3-127">The following date formats are supported:</span></span>
- <span data-ttu-id="c60f3-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="c60f3-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="c60f3-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="c60f3-129">dd/MM/yyyy</span></span>

<span data-ttu-id="c60f3-130">現在、次の日付と時刻の形式はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c60f3-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="c60f3-131">日付形式 yyyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="c60f3-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="c60f3-132">日付形式 dd/MM/yyy</span><span class="sxs-lookup"><span data-stu-id="c60f3-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="c60f3-133">yy の日付形式。</span><span class="sxs-lookup"><span data-stu-id="c60f3-133">Date format with yy.</span></span> <span data-ttu-id="c60f3-134">yyyy のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="c60f3-134">Will only show yyyy.</span></span>
- <span data-ttu-id="c60f3-135">時間形式 HH:mm:ss はサポートされていません (12 時間 AM/PM 形式はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="c60f3-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="c60f3-136">24 時間形式だけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c60f3-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="c60f3-137">**コンマを使用して千を示す**</span><span class="sxs-lookup"><span data-stu-id="c60f3-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="c60f3-138">数値の区切り記号としてコンマを使用するサポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c60f3-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="c60f3-139">数字がコンマで区切られ、1000 を示す領域では、ドットが区切り記号としてのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60f3-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="c60f3-140">たとえば、15,5K は 15.5K と表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60f3-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="c60f3-141">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="c60f3-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c60f3-142">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c60f3-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="c60f3-143">Microsoft Defender for Endpoint テナントがヨーロッパで自動的に作成されました</span><span class="sxs-lookup"><span data-stu-id="c60f3-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="c60f3-144">Azure Defender を使用してサーバーを監視すると、Microsoft Defender for Endpoint テナントが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c60f3-144">When you use Azure Defender to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="c60f3-145">Microsoft Defender for Endpoint データは、既定でヨーロッパに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c60f3-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="c60f3-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="c60f3-146">Related topics</span></span>
- [<span data-ttu-id="c60f3-147">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c60f3-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="c60f3-148">イベント ビューアーを使用してイベントとエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="c60f3-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
