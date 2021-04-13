---
title: Microsoft Defender for Endpoint のライブ応答の問題のトラブルシューティング
description: Microsoft Defender for Endpoint でライブ応答を使用するときに発生する可能性のある問題のトラブルシューティング
keywords: ライブ応答、ライブ、応答、ロック、ファイルのトラブルシューティング
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
ms.openlocfilehash: 2601001687fc22da98ca3cd81010237d12705ea4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687413"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="58115-104">Microsoft Defender for Endpoint のライブ応答の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="58115-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="58115-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="58115-105">**Applies to:**</span></span>
- [<span data-ttu-id="58115-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="58115-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="58115-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58115-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="58115-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="58115-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="58115-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="58115-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="58115-110">このページでは、ライブ応答の問題をトラブルシューティングするための詳細な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="58115-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="58115-111">ライブ応答セッション中にファイルにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="58115-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="58115-112">ライブ応答セッション中にアクションを実行しようとしている場合は、ファイルにアクセスできないというエラー メッセージが表示される場合は、以下の手順を使用して問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58115-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="58115-113">次のスクリプト コード スニペットをコピーし、PS1 ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="58115-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="58115-114">スクリプトをライブ応答ライブラリに追加します。</span><span class="sxs-lookup"><span data-stu-id="58115-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="58115-115">コピーするファイルのファイル パスという 1 つのパラメーターでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="58115-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="58115-116">TEMP フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="58115-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="58115-117">コピーしたファイルに対して実行するアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="58115-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="58115-118">ライブ応答セッションが遅い、または初期接続中の遅延</span><span class="sxs-lookup"><span data-stu-id="58115-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="58115-119">ライブ応答は、Windows の WNS サービスを使用した Defender for Endpoint センサー登録を活用します。</span><span class="sxs-lookup"><span data-stu-id="58115-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="58115-120">ライブ応答で接続の問題が発生している場合は、次の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="58115-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="58115-121">`notify.windows.com` 環境でブロックされません。</span><span class="sxs-lookup"><span data-stu-id="58115-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="58115-122">詳細については、「デバイス プロキシと [インターネット接続の設定を構成する」を参照してください](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="58115-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="58115-123">WpnService (Windows プッシュ通知システム サービス) は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="58115-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="58115-124">WpnService サービスの動作と要件を完全に理解するには、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58115-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="58115-125">Windows プッシュ Notification Services (WNS) の概要</span><span class="sxs-lookup"><span data-stu-id="58115-125">Windows Push Notification Services (WNS) overview</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="58115-126">WNS トラフィックをサポートするエンタープライズ ファイアウォールとプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="58115-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="58115-127">Microsoft プッシュ通知サービス (MPNS) パブリック IP 範囲</span><span class="sxs-lookup"><span data-stu-id="58115-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

