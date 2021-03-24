---
title: Microsoft Defender ATP for Mac でのカーネル拡張機能の問題のトラブルシューティング
description: Microsoft Defender ATP for Mac のカーネル拡張機能に関連する問題のトラブルシューティングを行います。
keywords: microsoft、 defender, atp, mac, kernel, extension
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
ms.openlocfilehash: ee6f34a16c4c924bbc73af89029c529dfc766568
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064075"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="0b430-104">Microsoft Defender for Endpoint for Mac でのカーネル拡張機能の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0b430-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0b430-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0b430-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b430-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="0b430-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="0b430-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b430-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="0b430-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b430-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0b430-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="0b430-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0b430-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="0b430-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="0b430-111">この記事では、Microsoft Defender for Endpoint for Mac の一部としてインストールされているカーネル拡張機能に関する問題をトラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b430-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="0b430-112">macOS High Sierra (10.13) から、macOS では、デバイスでの実行を許可する前に、すべてのカーネル拡張機能を明示的に承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b430-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they are allowed to run on the device.</span></span>

<span data-ttu-id="0b430-113">Microsoft Defender for Endpoint for Mac の展開/インストール中にカーネル拡張機能を承認しなかった場合、アプリケーションはバナーを表示して有効にするように求めます。</span><span class="sxs-lookup"><span data-stu-id="0b430-113">If you did not approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint for Mac, the application displays a banner prompting you to enable it:</span></span>

   ![RTP が無効なスクリーンショット](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-32-main-app-fix)

<span data-ttu-id="0b430-115">また、実行できます ```mdatp health``` 。</span><span class="sxs-lookup"><span data-stu-id="0b430-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="0b430-116">リアルタイム保護が有効になっているが使用できない場合に報告されます。</span><span class="sxs-lookup"><span data-stu-id="0b430-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="0b430-117">これは、カーネル拡張機能がデバイスでの実行が承認されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="0b430-117">This indicates that the kernel extension is not approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="0b430-118">次のセクションでは、Microsoft Defender for Endpoint for Mac の展開に使用した方法に応じて、この問題に対処する方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b430-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint for Mac.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="0b430-119">管理された展開</span><span class="sxs-lookup"><span data-stu-id="0b430-119">Managed deployment</span></span>

<span data-ttu-id="0b430-120">製品の展開に使用した管理ツールに対応する手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b430-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="0b430-121">JAMF ベースの展開</span><span class="sxs-lookup"><span data-stu-id="0b430-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="0b430-122">Microsoft Intune ベースの展開</span><span class="sxs-lookup"><span data-stu-id="0b430-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="0b430-123">手動展開</span><span class="sxs-lookup"><span data-stu-id="0b430-123">Manual deployment</span></span>

<span data-ttu-id="0b430-124">製品のインストールから 30 分未満経過した場合は **、[System Preferences** Security & Privacy] に移動し、開発者  >  "Microsoft Corporation" のシステム ソフトウェアを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b430-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="0b430-125">このプロンプトが表示されない場合は、30 分以上経過し、カーネル拡張機能がデバイスでの実行が承認されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0b430-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![プロンプトの有効期限が切れたスクリーンショットの後のセキュリティとプライバシーのウィンドウ](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-33-securityprivacysettings-noprompt)

<span data-ttu-id="0b430-127">この場合、承認フローを再度トリガーするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b430-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="0b430-128">ターミナルで、ドライバーのインストールを試みる。</span><span class="sxs-lookup"><span data-stu-id="0b430-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="0b430-129">カーネル拡張機能がデバイスでの実行を承認されていないので、次の操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="0b430-129">The following operation will fail, because the kernel extension was not approved to run on the device.</span></span> <span data-ttu-id="0b430-130">ただし、承認フローが再びトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="0b430-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="0b430-131">メニュー **から [System Preferences**  >  **Security &プライバシー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="0b430-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="0b430-132">(開いている場合は、最初に閉じます)。</span><span class="sxs-lookup"><span data-stu-id="0b430-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="0b430-133">**開発者** からのシステム ソフトウェアの許可 "Microsoft Corporation"</span><span class="sxs-lookup"><span data-stu-id="0b430-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="0b430-134">ターミナルで、ドライバーを再度インストールします。</span><span class="sxs-lookup"><span data-stu-id="0b430-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="0b430-135">この時間は、操作が成功します。</span><span class="sxs-lookup"><span data-stu-id="0b430-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="0b430-136">バナーは Defender アプリケーションから消え、リアルタイム保護が有効で使用可能になっている ```mdatp health``` と報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b430-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
