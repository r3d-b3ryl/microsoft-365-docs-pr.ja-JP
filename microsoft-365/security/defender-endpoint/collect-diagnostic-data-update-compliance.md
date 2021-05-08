---
title: 更新コンプライアンスと更新プログラムの診断データをWindows Defender Microsoft Defender ウイルス対策
description: ツールを使用してデータを収集し、更新プログラムのコンプライアンスに関する問題のトラブルシューティングを行う場合は、Microsoft Defender ウイルス対策を使用します。
keywords: トラブルシューティング、エラー、修正、更新コンプライアンス、oms、モニター、レポート、Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2aaf3d1c650713a7f6cfb7b9abb9f2232013d6db
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274798"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="dfb73-104">Microsoft Defender AV 評価の更新コンプライアンス診断データを収集する</span><span class="sxs-lookup"><span data-stu-id="dfb73-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dfb73-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dfb73-105">**Applies to:**</span></span>

- [<span data-ttu-id="dfb73-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dfb73-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dfb73-107">この記事では、Microsoft サポートチームとエンジニアリング チームが使用できる診断データを収集して、更新コンプライアンス アドインの Microsoft Defender AV Assessment セクションを使用するときに発生する可能性がある問題のトラブルシューティングに役立つ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfb73-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="dfb73-108">このプロセスを試す前に、「レポートのトラブルシューティング」[を](troubleshoot-reporting.md)Microsoft Defender ウイルス対策、すべての必須コンポーネントを満たしていることを確認し、その他の推奨されるトラブルシューティング手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="dfb73-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="dfb73-109">Update Compliance でレポートまたは表示されていない少なくとも 2 つのデバイスで、次の手順を実行して、.cab診断ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="dfb73-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="dfb73-110">次のように、管理者レベルのバージョンのコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="dfb73-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="dfb73-111">a.</span><span class="sxs-lookup"><span data-stu-id="dfb73-111">a.</span></span> <span data-ttu-id="dfb73-112">[スタート] **メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="dfb73-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="dfb73-113">b.</span><span class="sxs-lookup"><span data-stu-id="dfb73-113">b.</span></span> <span data-ttu-id="dfb73-114">cmd **と入力します**。</span><span class="sxs-lookup"><span data-stu-id="dfb73-114">Type **cmd**.</span></span> <span data-ttu-id="dfb73-115">[コマンド プロンプト] を右 **クリックし、[** 管理者として **実行] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dfb73-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="dfb73-116">c.</span><span class="sxs-lookup"><span data-stu-id="dfb73-116">c.</span></span> <span data-ttu-id="dfb73-117">管理者の資格情報を入力するか、プロンプトを承認します。</span><span class="sxs-lookup"><span data-stu-id="dfb73-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="dfb73-118">ディレクトリに移動Windows Defenderします。</span><span class="sxs-lookup"><span data-stu-id="dfb73-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="dfb73-119">既定では `C:\Program Files\Windows Defender` です。</span><span class="sxs-lookup"><span data-stu-id="dfb73-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="dfb73-120">次のコマンドを入力し、Enter キーを **押します。**</span><span class="sxs-lookup"><span data-stu-id="dfb73-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="dfb73-121">さまざまな.cabを含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dfb73-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="dfb73-122">ファイルの場所は、コマンド プロンプトの出力で指定されます。</span><span class="sxs-lookup"><span data-stu-id="dfb73-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="dfb73-123">既定では、場所は `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="dfb73-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="dfb73-124">これらのファイル.cab、Microsoft サポートからアクセスできる場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfb73-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="dfb73-125">たとえば、パスワードで保護されたフォルダー OneDrive共有できるフォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="dfb73-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="dfb73-126">[コンプライアンスの更新] サポート メール テンプレートを使用して電子メールを <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">送信し</a>、テンプレートに次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfb73-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="dfb73-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfb73-127">See also</span></span>

- [<span data-ttu-id="dfb73-128">レポートのWindows Defender Microsoft Defender ウイルス対策トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dfb73-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)