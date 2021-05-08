---
title: Microsoft Defender ウイルス対策の診断データを収集する
description: ツールを使用してデータを収集し、Microsoft Defender ウイルス対策のトラブルシューティングを行う
keywords: トラブルシューティング、エラー、修正、更新コンプライアンス、oms、モニター、レポート、Microsoft Defender av、グループ ポリシー オブジェクト、設定、診断データ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccf6da0e1bc91a29865868305b5333f7ef9c47cc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274786"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="77447-104">Microsoft Defender AV 診断データの収集</span><span class="sxs-lookup"><span data-stu-id="77447-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="77447-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="77447-105">**Applies to:**</span></span>

- [<span data-ttu-id="77447-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77447-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="77447-107">この記事では、Microsoft Defender AV を使用するときに発生する可能性がある問題のトラブルシューティングに役立つ Microsoft サポートチームとエンジニアリング チームが使用できる診断データを収集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77447-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="77447-108">調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。</span><span class="sxs-lookup"><span data-stu-id="77447-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="77447-109">次の方法: デバイスから [調査パッケージを収集します](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)。</span><span class="sxs-lookup"><span data-stu-id="77447-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="77447-110">同じ問題が発生している少なくとも 2 つのデバイスで、次.cabを実行して診断ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="77447-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="77447-111">次のように、管理者レベルのバージョンのコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="77447-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="77447-112">a.</span><span class="sxs-lookup"><span data-stu-id="77447-112">a.</span></span> <span data-ttu-id="77447-113">[スタート] **メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="77447-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="77447-114">b.</span><span class="sxs-lookup"><span data-stu-id="77447-114">b.</span></span> <span data-ttu-id="77447-115">cmd **と入力します**。</span><span class="sxs-lookup"><span data-stu-id="77447-115">Type **cmd**.</span></span> <span data-ttu-id="77447-116">[コマンド プロンプト] を右 **クリックし、[** 管理者として **実行] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="77447-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="77447-117">c.</span><span class="sxs-lookup"><span data-stu-id="77447-117">c.</span></span> <span data-ttu-id="77447-118">管理者の資格情報を入力するか、プロンプトを承認します。</span><span class="sxs-lookup"><span data-stu-id="77447-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="77447-119">Microsoft Defender ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="77447-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="77447-120">既定では `C:\Program Files\Windows Defender` です。</span><span class="sxs-lookup"><span data-stu-id="77447-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="77447-121">更新された Microsoft [Defender プラットフォーム](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)バージョンを実行している場合は、次の `MpCmdRun` 場所から実行してください `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 。</span><span class="sxs-lookup"><span data-stu-id="77447-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="77447-122">次のコマンドを入力し、Enter キーを **押します。**</span><span class="sxs-lookup"><span data-stu-id="77447-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="77447-123">さまざまな.cabを含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="77447-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="77447-124">ファイルの場所は、コマンド プロンプトの出力で指定されます。</span><span class="sxs-lookup"><span data-stu-id="77447-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="77447-125">既定では、場所は `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="77447-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="77447-126">cab ファイルを別のパスまたは UNC 共有にリダイレクトするには、次のコマンドを使用します。 `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="77447-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="77447-127">詳細については、「診断データ [を UNC 共有にリダイレクトする」を参照してください](#redirect-diagnostic-data-to-a-unc-share)。</span><span class="sxs-lookup"><span data-stu-id="77447-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="77447-128">これらのファイル.cab、Microsoft サポートからアクセスできる場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="77447-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="77447-129">たとえば、パスワードで保護された OneDrive フォルダーを使用して共有できます。</span><span class="sxs-lookup"><span data-stu-id="77447-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="77447-130">更新コンプライアンスに問題がある場合は、更新コンプライアンス サポート メール<a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>テンプレートを使用して電子メールを送信し、テンプレートに次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="77447-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="77447-131">診断データを UNC 共有にリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="77447-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="77447-132">中央リポジトリの診断データを収集するには、SupportLogLocation パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="77447-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="77447-133">診断データを指定したパスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="77447-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="77447-134">パスを指定しない場合、診断データはサポート ログの場所構成で指定された場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="77447-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="77447-135">SupportLogLocation パラメーターを使用すると、次のようなフォルダー構造が移動先パスに作成されます。</span><span class="sxs-lookup"><span data-stu-id="77447-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="77447-136">フィールド</span><span class="sxs-lookup"><span data-stu-id="77447-136">field</span></span>  | <span data-ttu-id="77447-137">説明</span><span class="sxs-lookup"><span data-stu-id="77447-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="77447-138">path</span><span class="sxs-lookup"><span data-stu-id="77447-138">path</span></span> | <span data-ttu-id="77447-139">コマンド ラインで指定されたパス、または構成から取得されたパス</span><span class="sxs-lookup"><span data-stu-id="77447-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="77447-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="77447-140">MMDD</span></span> | <span data-ttu-id="77447-141">診断データが収集された月と日 (たとえば、0530)</span><span class="sxs-lookup"><span data-stu-id="77447-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="77447-142">ホスト名</span><span class="sxs-lookup"><span data-stu-id="77447-142">hostname</span></span> | <span data-ttu-id="77447-143">診断データが収集されたデバイスのホスト名</span><span class="sxs-lookup"><span data-stu-id="77447-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="77447-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="77447-144">HHMM</span></span> | <span data-ttu-id="77447-145">診断データが収集された時間と分 (たとえば、1422)</span><span class="sxs-lookup"><span data-stu-id="77447-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="77447-146">ファイル共有を使用する場合は、診断パッケージの収集に使用されるアカウントが共有への書き込みアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="77447-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="77447-147">診断データの作成場所を指定する</span><span class="sxs-lookup"><span data-stu-id="77447-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="77447-148">グループ ポリシー オブジェクト (GPO) を使用.cabファイルを作成する場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="77447-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="77447-149">ローカル グループ ポリシー エディターを開き、SupportLogLocation GPO を次の場所で検索します。 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="77447-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="77447-150">[サポート **ログ ファイルをコピーするディレクトリ パスを定義する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="77447-150">Select **Define the directory path to copy support log files**.</span></span>

    ![ローカル グループ ポリシー エディターのスクリーンショット](images/GPO1-SupportLogLocationDefender.png)  
        
     ![ログ ファイルの定義パス設定のスクリーンショット](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="77447-153">ポリシー エディター内で、[有効] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="77447-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="77447-154">サポート ログ ファイルをコピーするディレクトリ パスを [オプション] フィールドに **指定** します。</span><span class="sxs-lookup"><span data-stu-id="77447-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="77447-155">![有効なディレクトリ パスのカスタム設定のスクリーンショット](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="77447-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="77447-156">**[OK] または [** 適用]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="77447-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="77447-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="77447-157">See also</span></span>

- [<span data-ttu-id="77447-158">Microsoft Defender ウイルス対策レポートのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="77447-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)