---
title: Microsoft Defender for Endpoint のファイルに対して応答アクションを実行する
description: ファイルを停止して quarantining したり、ファイルをブロックしたり、アクティビティの詳細を確認したりして、ファイル関連のアラートに対して応答アクションを実行します。
keywords: 応答、停止と検疫、ファイルのブロック、深い分析
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1f189956d65e6d08d8e00272ba0d8db3ba59f6d4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844072"
---
# <a name="take-response-actions-on-a-file"></a><span data-ttu-id="e1264-104">ファイルの対応措置を講じる</span><span class="sxs-lookup"><span data-stu-id="e1264-104">Take response actions on a file</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e1264-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e1264-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1264-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e1264-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> <span data-ttu-id="e1264-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e1264-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e1264-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e1264-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

<span data-ttu-id="e1264-109">検出された攻撃に迅速に対応するには、ファイルを停止および検出するか、ファイルをブロックします。</span><span class="sxs-lookup"><span data-stu-id="e1264-109">Quickly respond to detected attacks by stopping and quarantining files or blocking a file.</span></span> <span data-ttu-id="e1264-110">ファイルに対してアクションを実行した後、アクション センターでアクティビティの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-110">After taking action on files, you can check activity details in the Action center.</span></span>

<span data-ttu-id="e1264-111">応答アクションは、ファイルの詳細なプロファイル ページで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-111">Response actions are available on a file's detailed profile page.</span></span> <span data-ttu-id="e1264-112">このページに移動すると、新しい [ファイル] ページを切り替えて、新しいページ レイアウトと古いページ レイアウト **を切り替えることができます**。</span><span class="sxs-lookup"><span data-stu-id="e1264-112">Once on this page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="e1264-113">この記事の残りの部分では、新しいページ レイアウトについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e1264-113">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="e1264-114">応答アクションは、ファイル ページの上部に沿って実行され、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1264-114">Response actions run along the top of the file page, and include:</span></span>

- <span data-ttu-id="e1264-115">ファイルの停止と検疫</span><span class="sxs-lookup"><span data-stu-id="e1264-115">Stop and Quarantine File</span></span>
- <span data-ttu-id="e1264-116">インジケーターの追加</span><span class="sxs-lookup"><span data-stu-id="e1264-116">Add Indicator</span></span>
- <span data-ttu-id="e1264-117">ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e1264-117">Download file</span></span>
- <span data-ttu-id="e1264-118">脅威のエキスパートに相談する</span><span class="sxs-lookup"><span data-stu-id="e1264-118">Consult a threat expert</span></span>
- <span data-ttu-id="e1264-119">アクション センター</span><span class="sxs-lookup"><span data-stu-id="e1264-119">Action center</span></span>

<span data-ttu-id="e1264-120">ファイルを詳細分析用に送信して、セキュリティで保護されたクラウド サンドボックスでファイルを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1264-120">You can also submit files for deep analysis, to run the file in a secure cloud sandbox.</span></span> <span data-ttu-id="e1264-121">分析が完了すると、ファイルの動作に関する情報を提供する詳細なレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-121">When the analysis is complete, you'll get a detailed report that provides information about the behavior of the file.</span></span> <span data-ttu-id="e1264-122">[詳細分析] タブを選択すると、詳細分析用のファイルを送信し、過去のレポート **を読み取** ることもできます。ファイル情報カードの下に位置します。</span><span class="sxs-lookup"><span data-stu-id="e1264-122">You can submit files for deep analysis and read past reports by selecting the **Deep analysis** tab. It's located below the file information cards.</span></span>

<span data-ttu-id="e1264-123">一部のアクションでは、特定のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1264-123">Some actions require certain permissions.</span></span> <span data-ttu-id="e1264-124">次の表では、ポータブル実行可能ファイル (PE) および非 PE ファイルに対して特定のアクセス許可が実行できるアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e1264-124">The following table describes what action certain permissions can take on portable executable (PE) and non-PE files:</span></span>

| <span data-ttu-id="e1264-125">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e1264-125">Permission</span></span>             | <span data-ttu-id="e1264-126">PE ファイル</span><span class="sxs-lookup"><span data-stu-id="e1264-126">PE files</span></span> | <span data-ttu-id="e1264-127">PE 以外のファイル</span><span class="sxs-lookup"><span data-stu-id="e1264-127">Non-PE files</span></span> |
| :--------------------- | :------: | :----------: |
| <span data-ttu-id="e1264-128">データの表示</span><span class="sxs-lookup"><span data-stu-id="e1264-128">View data</span></span>              |     <span data-ttu-id="e1264-129">X</span><span class="sxs-lookup"><span data-stu-id="e1264-129">X</span></span>    |       <span data-ttu-id="e1264-130">○</span><span class="sxs-lookup"><span data-stu-id="e1264-130">X</span></span>      |
| <span data-ttu-id="e1264-131">アラートの調査</span><span class="sxs-lookup"><span data-stu-id="e1264-131">Alerts investigation</span></span>   | <span data-ttu-id="e1264-132">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="e1264-132">&#x2611;</span></span> |       <span data-ttu-id="e1264-133">○</span><span class="sxs-lookup"><span data-stu-id="e1264-133">X</span></span>      |
| <span data-ttu-id="e1264-134">ライブ応答の基本</span><span class="sxs-lookup"><span data-stu-id="e1264-134">Live response basic</span></span>    |     <span data-ttu-id="e1264-135">X</span><span class="sxs-lookup"><span data-stu-id="e1264-135">X</span></span>    |       <span data-ttu-id="e1264-136">○</span><span class="sxs-lookup"><span data-stu-id="e1264-136">X</span></span>      |
| <span data-ttu-id="e1264-137">ライブ応答の詳細設定</span><span class="sxs-lookup"><span data-stu-id="e1264-137">Live response advanced</span></span> | <span data-ttu-id="e1264-138">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="e1264-138">&#x2611;</span></span> |   <span data-ttu-id="e1264-139">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="e1264-139">&#x2611;</span></span>   |

<span data-ttu-id="e1264-140">役割の詳細については、「役割ベースのアクセス制御の役割の作成と管理 [」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e1264-140">For more information on roles, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="stop-and-quarantine-files-in-your-network"></a><span data-ttu-id="e1264-141">ネットワーク内のファイルを停止して検疫する</span><span class="sxs-lookup"><span data-stu-id="e1264-141">Stop and quarantine files in your network</span></span>

<span data-ttu-id="e1264-142">悪意のあるプロセスを停止し、検出されたファイルを quarantining することで、組織内に攻撃を含めできます。</span><span class="sxs-lookup"><span data-stu-id="e1264-142">You can contain an attack in your organization by stopping the malicious process and quarantining the file where it was observed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1264-143">このアクションは、次の場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-143">You can only take this action if:</span></span>
>
> - <span data-ttu-id="e1264-144">アクションを実行しているデバイスがバージョン 1703 以降Windows 10を実行している</span><span class="sxs-lookup"><span data-stu-id="e1264-144">The device you're taking the action on is running Windows 10, version 1703 or later</span></span>
> - <span data-ttu-id="e1264-145">ファイルが信頼できるサード パーティ発行元に属していないか、Microsoft によって署名されていない</span><span class="sxs-lookup"><span data-stu-id="e1264-145">The file does not belong to trusted third-party publishers or not signed by Microsoft</span></span>
> - <span data-ttu-id="e1264-146">Microsoft Defender ウイルス対策パッシブ モードで実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-146">Microsoft Defender Antivirus must at least be running on Passive mode.</span></span> <span data-ttu-id="e1264-147">詳細については、「互換性」[をMicrosoft Defender ウイルス対策してください](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="e1264-147">For more information, see [Microsoft Defender Antivirus compatibility](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

<span data-ttu-id="e1264-148">[ **ファイルの停止と検疫]** アクションには、実行中のプロセスの停止、ファイルの検疫、レジストリ キーなどの永続的なデータの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1264-148">The **Stop and Quarantine File** action includes stopping running processes, quarantining the files, and deleting persistent data such as registry keys.</span></span>

<span data-ttu-id="e1264-149">このアクションは、過去 30 日間Windows 10バージョン 1703 以降のデバイスで有効になります。</span><span class="sxs-lookup"><span data-stu-id="e1264-149">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="e1264-150">いつでも検疫からファイルを復元できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-150">You’ll be able to restore the file from quarantine at any time.</span></span>

### <a name="stop-and-quarantine-files"></a><span data-ttu-id="e1264-151">ファイルの停止と検疫</span><span class="sxs-lookup"><span data-stu-id="e1264-151">Stop and quarantine files</span></span>

1. <span data-ttu-id="e1264-152">停止して検疫するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1264-152">Select the file you want to stop and quarantine.</span></span> <span data-ttu-id="e1264-153">次のビューからファイルを選択するか、[検索] ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1264-153">You can select a file from any of the following views or use the Search box:</span></span>

   - <span data-ttu-id="e1264-154">**アラート** - 成果物タイムラインの [説明] または [詳細] から対応するリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1264-154">**Alerts** - click the corresponding links from the Description or Details in the Artifact timeline</span></span>
   - <span data-ttu-id="e1264-155">**[検索]** ボックス - **ドロップダウン** メニューから [ファイル] を選択し、ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1264-155">**Search box** - select **File** from the drop–down menu and enter the file name</span></span>

   > [!NOTE]
   > <span data-ttu-id="e1264-156">[ファイルの停止と検疫] アクションは、最大 1000 台のデバイスに制限されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-156">The stop and quarantine file action is limited to a maximum of 1000 devices.</span></span> <span data-ttu-id="e1264-157">より多くのデバイスでファイルを停止するには、「ファイルをブロックまたは許可する [インジケーターを追加する」を参照してください](#add-indicator-to-block-or-allow-a-file)。</span><span class="sxs-lookup"><span data-stu-id="e1264-157">To stop a file on a larger number of devices, see [Add indicator to block or allow file](#add-indicator-to-block-or-allow-a-file).</span></span>

2. <span data-ttu-id="e1264-158">トップ バーに移動し、[ファイルの停止 **と検疫] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e1264-158">Go to the top bar and select **Stop and Quarantine File**.</span></span>

   ![ファイルの停止と検疫の操作のイメージ](images/atp-stop-quarantine-file.png)

3. <span data-ttu-id="e1264-160">理由を指定し、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e1264-160">Specify a reason, then select **Confirm**.</span></span>

   ![停止ファイルと検疫ファイルのモーダル ウィンドウのイメージ](images/atp-stop-quarantine.png)

   <span data-ttu-id="e1264-162">アクション センターには、申請情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-162">The Action center shows the submission information:</span></span>
   
   ![ファイルの停止と検疫のアクション センターのイメージ](images/atp-stopnquarantine-file.png)

   - <span data-ttu-id="e1264-164">**申請時間** - アクションが送信された時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="e1264-164">**Submission time** - Shows when the action was submitted.</span></span>
   - <span data-ttu-id="e1264-165">**成功** - ファイルが停止して検疫されているデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="e1264-165">**Success** - Shows the number of devices where the file has been stopped and quarantined.</span></span>
   - <span data-ttu-id="e1264-166">**Failed** - アクションが失敗したデバイスの数と、エラーに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="e1264-166">**Failed** - Shows the number of devices where the action failed and details about the failure.</span></span>
   - <span data-ttu-id="e1264-167">**Pending** - ファイルがまだ停止および検疫されていないデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="e1264-167">**Pending** - Shows the number of devices where the file is yet to be stopped and quarantined from.</span></span> <span data-ttu-id="e1264-168">これは、デバイスがオフラインまたはネットワークに接続されていない場合に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-168">This can take time for cases when the device is offline or not connected to the network.</span></span>

4. <span data-ttu-id="e1264-169">アクションの詳細を表示するには、状態インジケーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1264-169">Select any of the status indicators to view more information about the action.</span></span> <span data-ttu-id="e1264-170">たとえば、[失敗] **を選択して** 、アクションが失敗した場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="e1264-170">For example, select **Failed** to see where the action failed.</span></span>

<span data-ttu-id="e1264-171">**デバイス ユーザーの通知**:</span><span class="sxs-lookup"><span data-stu-id="e1264-171">**Notification on device user**:</span></span></br>
<span data-ttu-id="e1264-172">ファイルがデバイスから削除されると、次の通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-172">When the file is being removed from a device, the following notification is shown:</span></span>

![デバイス ユーザーの通知のイメージ](images/atp-notification-file.png)

<span data-ttu-id="e1264-174">デバイスタイムラインでは、ファイルが停止して検疫されたデバイスごとに新しいイベントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-174">In the device timeline, a new event is added for each device where a file was stopped and quarantined.</span></span>

<span data-ttu-id="e1264-175">組織全体で広く使用されているファイルに対してアクションが実装される前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-175">A warning is shown before the action is implemented for files widely used throughout an organization.</span></span> <span data-ttu-id="e1264-176">操作が意図されているのを検証します。</span><span class="sxs-lookup"><span data-stu-id="e1264-176">It's to validate that the operation is intended.</span></span>

## <a name="restore-file-from-quarantine"></a><span data-ttu-id="e1264-177">検疫からファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="e1264-177">Restore file from quarantine</span></span>

<span data-ttu-id="e1264-178">調査後にファイルがクリーンだと判断した場合は、ファイルをロールバックして検疫から削除できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-178">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="e1264-179">ファイルが検疫された各デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1264-179">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="e1264-180">デバイスで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e1264-180">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="e1264-181">**[スタート]** をクリックし、「_cmd_」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e1264-181">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="e1264-182">[コマンド プロンプト] を **右クリックし、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e1264-182">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="e1264-183">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="e1264-183">Enter the following command, and press **Enter**:</span></span>

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> <span data-ttu-id="e1264-184">シナリオによっては **、ThreatName は** EUS:Win32/CustomEnterpriseBlock!cl のように表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-184">In some scenarios, the **ThreatName** may appear as: EUS:Win32/CustomEnterpriseBlock!cl.</span></span>
>
> <span data-ttu-id="e1264-185">Defender for Endpoint は、過去 30 日間にこのデバイスで検疫されたカスタム ブロックされたファイルを復元します。</span><span class="sxs-lookup"><span data-stu-id="e1264-185">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1264-186">潜在的なネットワーク脅威として検疫されたファイルは、回復できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-186">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="e1264-187">検疫後にユーザーがファイルを復元しようとすると、そのファイルにアクセスできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-187">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="e1264-188">これは、システムがファイルにアクセスするためのネットワーク資格情報を持たなくなった場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-188">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="e1264-189">通常、これはシステムまたは共有フォルダーに一時的にログオンし、アクセス トークンの有効期限が切れた結果です。</span><span class="sxs-lookup"><span data-stu-id="e1264-189">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="download-or-collect-file"></a><span data-ttu-id="e1264-190">ファイルをダウンロードまたは収集する</span><span class="sxs-lookup"><span data-stu-id="e1264-190">Download or collect file</span></span>

<span data-ttu-id="e1264-191">応答アクション **から [ファイル** のダウンロード] を選択すると、ファイルを含むローカルのパスワードで保護された.zipをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e1264-191">Selecting **Download file** from the response actions allows you to download a local, password-protected .zip archive containing your file.</span></span> <span data-ttu-id="e1264-192">ファイルをダウンロードする理由を記録し、パスワードを設定できるフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-192">A flyout will appear where you can record a reason for downloading the file, and set a password.</span></span>

<span data-ttu-id="e1264-193">既定では、検疫中のファイルをダウンロードできない。</span><span class="sxs-lookup"><span data-stu-id="e1264-193">By default, you will not be able to download files that are in quarantine.</span></span>

![ダウンロード ファイルアクションのイメージ](images/atp-download-file-action.png)

### <a name="collect-files"></a><span data-ttu-id="e1264-195">ファイルの収集</span><span class="sxs-lookup"><span data-stu-id="e1264-195">Collect files</span></span>

<span data-ttu-id="e1264-196">ファイルが Microsoft Defender for Endpoint によってまだ保存されていない場合は、ダウンロードできません。</span><span class="sxs-lookup"><span data-stu-id="e1264-196">If a file is not already stored by Microsoft Defender for Endpoint, you can't download it.</span></span> <span data-ttu-id="e1264-197">代わりに、同じ場所に **[ファイル** の収集] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-197">Instead, you'll see a **Collect file** button in the same location.</span></span> <span data-ttu-id="e1264-198">過去 30 日間に組織でファイルが表示されていない場合、ファイルの収集 **は** 無効になります。</span><span class="sxs-lookup"><span data-stu-id="e1264-198">If a file hasn't been seen in the organization in the past 30 days, **Collect file** will be disabled.</span></span>
> [!Important]
> <span data-ttu-id="e1264-199">潜在的なネットワーク脅威として検疫されたファイルは、回復できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-199">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="e1264-200">検疫後にユーザーがファイルを復元しようとすると、そのファイルにアクセスできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-200">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="e1264-201">これは、システムがファイルにアクセスするためのネットワーク資格情報を持たなくなった場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-201">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="e1264-202">通常、これはシステムまたは共有フォルダーに一時的にログオンし、アクセス トークンの有効期限が切れた結果です。</span><span class="sxs-lookup"><span data-stu-id="e1264-202">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="add-indicator-to-block-or-allow-a-file"></a><span data-ttu-id="e1264-203">ファイルをブロックまたは許可するインジケーターを追加する</span><span class="sxs-lookup"><span data-stu-id="e1264-203">Add indicator to block or allow a file</span></span>

<span data-ttu-id="e1264-204">悪意のある可能性のあるファイルやマルウェアの疑いを禁止することで、組織での攻撃の伝播をさらに防ぐ。</span><span class="sxs-lookup"><span data-stu-id="e1264-204">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="e1264-205">悪意のある可能性のあるポータブル実行可能ファイル (PE) ファイルが分かっている場合は、そのファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="e1264-205">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="e1264-206">この操作によって、組織内のデバイスで読み取り、書き込み、または実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="e1264-206">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="e1264-207">この機能は、組織でクラウド配信Microsoft Defender ウイルス対策が有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-207">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud–delivered protection is enabled.</span></span> <span data-ttu-id="e1264-208">詳細については、「クラウド提供の [保護を管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="e1264-208">For more information, see [Manage cloud–delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
>
> - <span data-ttu-id="e1264-209">マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-209">The Antimalware client version must be 4.18.1901.x or later.</span></span>
> - <span data-ttu-id="e1264-210">この機能は、疑わしいマルウェア (または悪意のある可能性のあるファイル) が Web からダウンロードされるのを防ぐために設計されています。</span><span class="sxs-lookup"><span data-stu-id="e1264-210">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="e1264-211">現在、ポータブル実行可能ファイル (PE) ファイルがサポートされています 。このファイルには、.exe _ファイル.dll__があります。_</span><span class="sxs-lookup"><span data-stu-id="e1264-211">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="e1264-212">対象範囲は時間の長い期間延長されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-212">The coverage will be extended over time.</span></span>
> - <span data-ttu-id="e1264-213">この応答アクションは、バージョン 1703 以降Windows 10デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-213">This response action is available for devices on Windows 10, version 1703 or later.</span></span>
> - <span data-ttu-id="e1264-214">許可またはブロックアクションの前にファイルの分類がデバイスのキャッシュに存在する場合、許可またはブロック関数をファイルに対して実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="e1264-214">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action.</span></span>

> [!NOTE]
> <span data-ttu-id="e1264-215">このアクションを実行するには、PE ファイルがデバイスのタイムラインに含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-215">The PE file needs to be in the device timeline for you to be able to take this action.</span></span>
>
> <span data-ttu-id="e1264-216">アクションが実行され、実際のファイルがブロックされる時間の間に、数分間の待機時間が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-216">There may be a couple of minutes of latency between the time the action is taken and the actual file being blocked.</span></span>

### <a name="enable-the-block-file-feature"></a><span data-ttu-id="e1264-217">ブロック ファイル機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="e1264-217">Enable the block file feature</span></span>

<span data-ttu-id="e1264-218">ファイルのブロックを開始するには、最初に[](advanced-features.md)ブロックまたは許可機能を有効にする必要設定。</span><span class="sxs-lookup"><span data-stu-id="e1264-218">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
### <a name="allow-or-block-file"></a><span data-ttu-id="e1264-219">ファイルを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="e1264-219">Allow or block file</span></span>

<span data-ttu-id="e1264-220">ファイルのインジケーター ハッシュを追加すると、組織内のデバイスがファイルの実行を試みるたびに、アラートを発生してファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="e1264-220">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="e1264-221">インジケーターによって自動的にブロックされたファイルは、ファイルのアクション センターには表示されませんが、アラートはアラート キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-221">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

<span data-ttu-id="e1264-222">ファイルの [ブロックとアラートの](manage-indicators.md) 発生の詳細については、「インジケーターの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1264-222">See [manage indicators](manage-indicators.md) for more details on blocking and raising alerts on files.</span></span>

<span data-ttu-id="e1264-223">ファイルのブロックを停止するには、インジケーターを削除します。</span><span class="sxs-lookup"><span data-stu-id="e1264-223">To stop blocking a file, remove the indicator.</span></span> <span data-ttu-id="e1264-224">これを行うには、ファイルの **プロファイル ページの** [インジケーターの編集] アクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1264-224">You can do so via the **Edit Indicator** action on the file's profile page.</span></span> <span data-ttu-id="e1264-225">このアクションは、インジケーターを追加する前に、[インジケーターの追加] アクションと同じ位置に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-225">This action will be visible in the same position as the **Add Indicator** action, before you added the indicator.</span></span>

<span data-ttu-id="e1264-226">[ルールインジケーター] の **[設定ページから** インジケーター **を編集**  >  **することもできます**。</span><span class="sxs-lookup"><span data-stu-id="e1264-226">You can also edit indicators from  the **Settings** page, under **Rules** > **Indicators**.</span></span> <span data-ttu-id="e1264-227">インジケーターは、ファイルのハッシュによってこの領域に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-227">Indicators are listed in this area by their file's hash.</span></span>

## <a name="consult-a-threat-expert"></a><span data-ttu-id="e1264-228">脅威のエキスパートに相談する</span><span class="sxs-lookup"><span data-stu-id="e1264-228">Consult a threat expert</span></span>

<span data-ttu-id="e1264-229">潜在的に侵害されたデバイス、または既に侵害されているデバイスに関する詳細な分析情報については、Microsoft の脅威の専門家に問い合してください。</span><span class="sxs-lookup"><span data-stu-id="e1264-229">Consult a Microsoft threat expert for more insights on a potentially compromised device, or already compromised devices.</span></span> <span data-ttu-id="e1264-230">Microsoft 脅威エキスパート、迅速かつ正確な対応のために、Microsoft Defender セキュリティ センター内から直接関与します。</span><span class="sxs-lookup"><span data-stu-id="e1264-230">Microsoft Threat Experts are engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="e1264-231">専門家は、侵害される可能性のあるデバイスに関する分析情報を提供し、複雑な脅威や標的型攻撃通知を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e1264-231">Experts provide insights on a potentially compromised device and help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="e1264-232">また、ポータル ダッシュボードに表示されるアラートや脅威インテリジェンス コンテキストに関する情報を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1264-232">They can also provide information about the alerts or a threat intelligence context that you see on your portal dashboard.</span></span>

<span data-ttu-id="e1264-233">詳細 [については、「Microsoft Threat Expert」を](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1264-233">See [Consult a Microsoft Threat Expert](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) for details.</span></span>

## <a name="check-activity-details-in-action-center"></a><span data-ttu-id="e1264-234">アクション センターでアクティビティの詳細を確認する</span><span class="sxs-lookup"><span data-stu-id="e1264-234">Check activity details in Action center</span></span>

<span data-ttu-id="e1264-235">アクション **センターは、** デバイスまたはファイルで実行されたアクションに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e1264-235">The **Action center** provides information on actions that were taken on a device or file.</span></span> <span data-ttu-id="e1264-236">次の詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-236">You can view the following details:</span></span>

- <span data-ttu-id="e1264-237">調査パッケージ コレクション</span><span class="sxs-lookup"><span data-stu-id="e1264-237">Investigation package collection</span></span>
- <span data-ttu-id="e1264-238">ウイルス対策スキャン</span><span class="sxs-lookup"><span data-stu-id="e1264-238">Antivirus scan</span></span>
- <span data-ttu-id="e1264-239">アプリの制限</span><span class="sxs-lookup"><span data-stu-id="e1264-239">App restriction</span></span>
- <span data-ttu-id="e1264-240">デバイスの分離</span><span class="sxs-lookup"><span data-stu-id="e1264-240">Device isolation</span></span>

<span data-ttu-id="e1264-241">送信日時、ユーザーの送信、アクションが成功または失敗した場合など、他のすべての関連する詳細も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-241">All other related details are also shown, such as submission date/time, submitting user, and if the action succeeded or failed.</span></span>

![情報を含むアクション センターのイメージ](images/action-center-details.png)

## <a name="deep-analysis"></a><span data-ttu-id="e1264-243">詳細分析</span><span class="sxs-lookup"><span data-stu-id="e1264-243">Deep analysis</span></span>

<span data-ttu-id="e1264-244">通常、サイバーセキュリティの調査はアラートによってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="e1264-244">Cyber security investigations are typically triggered by an alert.</span></span> <span data-ttu-id="e1264-245">アラートは、多くの場合、新しいファイルまたは不明な 1 つ以上の監視ファイルに関連しています。</span><span class="sxs-lookup"><span data-stu-id="e1264-245">Alerts are related to one or more observed files that are often new or unknown.</span></span> <span data-ttu-id="e1264-246">ファイルを選択すると、ファイル ビューにアクセスして、ファイルのメタデータを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-246">Selecting a file takes you to the file view where you can see the file's metadata.</span></span> <span data-ttu-id="e1264-247">ファイルに関連するデータを強化するには、ファイルを送信して詳細な分析を行います。</span><span class="sxs-lookup"><span data-stu-id="e1264-247">To enrich the data related to the file, you can submit the file for deep analysis.</span></span>

<span data-ttu-id="e1264-248">ディープ分析機能は、セキュリティで保護された完全にインストルメント化されたクラウド環境でファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1264-248">The Deep analysis feature executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="e1264-249">詳細な分析結果は、ファイルのアクティビティ、観察された動作、およびドロップされたファイル、レジストリの変更、および AP との通信など、関連する成果物を示します。</span><span class="sxs-lookup"><span data-stu-id="e1264-249">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IPs.</span></span>
<span data-ttu-id="e1264-250">現在、詳細な分析では、ポータブル実行可能ファイル (PE) ファイル (ファイルの _.exe、.dll__サポートしています_。</span><span class="sxs-lookup"><span data-stu-id="e1264-250">Deep analysis currently supports extensive analysis of portable executable (PE) files (including _.exe_ and _.dll_ files).</span></span>

<span data-ttu-id="e1264-251">ファイルの詳細な分析には数分かかります。</span><span class="sxs-lookup"><span data-stu-id="e1264-251">Deep analysis of a file takes several minutes.</span></span> <span data-ttu-id="e1264-252">ファイル分析が完了すると、[詳細分析] タブが更新され、利用可能な最新の結果の概要と日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-252">Once the file analysis is complete, the Deep Analysis tab will update to display a summary and the date and time of the latest available results.</span></span>

<span data-ttu-id="e1264-253">詳細な分析の概要には、観察された動作の一覧が含まれます。その一部は悪意のあるアクティビティを示し、監視可能な情報 (接続された IPs やディスク上に作成されたファイルを含む) を示します。</span><span class="sxs-lookup"><span data-stu-id="e1264-253">The deep analysis summary includes a list of observed *behaviors*, some of which can indicate malicious activity, and *observables*, including contacted IPs and files created on the disk.</span></span> <span data-ttu-id="e1264-254">何も見つからなかった場合、これらのセクションには簡単なメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-254">If nothing was found, these sections will display a brief message.</span></span>

<span data-ttu-id="e1264-255">詳細な分析の結果は脅威インテリジェンスと一致し、一致すると適切なアラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-255">Results of deep analysis are matched against threat intelligence and any matches will generate appropriate alerts.</span></span>

<span data-ttu-id="e1264-256">ディープ分析機能を使用して、通常、アラートの調査中、または悪意のある動作が疑われるその他の理由で、ファイルの詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="e1264-256">Use the deep analysis feature to investigate the details of any file, usually during an investigation of an alert or for any other reason where you suspect malicious behavior.</span></span> <span data-ttu-id="e1264-257">この機能は、ファイルのプロファイル **ページ** の [詳細分析] タブで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-257">This feature is available within the **Deep analysis** tab, on the file's profile page.</span></span><br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

<span data-ttu-id="e1264-258">**詳細分析用** の送信は、Defender for Endpoint バックエンド サンプル コレクションでファイルが使用できる場合、またはディープ分析への送信をサポートする Windows 10 デバイスでファイルが観察された場合に有効になります。</span><span class="sxs-lookup"><span data-stu-id="e1264-258">**Submit for deep analysis** is enabled when the file is available in the Defender for Endpoint backend sample collection, or if it was observed on a Windows 10 device that supports submitting to deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="e1264-259">自動的に収集できるのはWindows 10のファイルのみです。</span><span class="sxs-lookup"><span data-stu-id="e1264-259">Only files from Windows 10 can be automatically collected.</span></span>

<span data-ttu-id="e1264-260">ファイルが Windows 10 デバイスで観察されなかった場合は[、Microsoft セキュリティ](https://www.microsoft.com/security/portal/submission/submit.aspx)センター ポータルからサンプルを送信し、[詳細な分析]ボタンが使用可能になるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="e1264-260">You can also submit a sample through the [Microsoft Security Center Portal](https://www.microsoft.com/security/portal/submission/submit.aspx) if the file wasn't observed on a Windows 10 device, and wait for **Submit for deep analysis** button to become available.</span></span>

> [!NOTE]
> <span data-ttu-id="e1264-261">Microsoft Security Center Portal のバックエンド処理フローにより、Defender for Endpoint のディープ分析機能のファイル送信と可用性の間に最大 10 分の待機時間が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-261">Due to backend processing flows in the Microsoft Security Center Portal, there could be up to 10 minutes of latency between file submission and availability of the deep analysis feature in Defender for Endpoint.</span></span>

<span data-ttu-id="e1264-262">サンプルが収集されると、Defender for Endpoint は安全な環境でファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1264-262">When the sample is collected, Defender for Endpoint runs the file in a secure environment.</span></span> <span data-ttu-id="e1264-263">次に、デバイスにドロップされたファイル、AP への通信、レジストリの変更など、観察された動作と関連するアーティファクトの詳細なレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1264-263">It then creates a detailed report of observed behaviors and associated artifacts, such as files dropped on devices, communication to IPs, and registry modifications.</span></span>

### <a name="submit-files-for-deep-analysis"></a><span data-ttu-id="e1264-264">詳細分析用にファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="e1264-264">Submit files for deep analysis</span></span>

1. <span data-ttu-id="e1264-265">詳細分析のために提出するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1264-265">Select the file that you want to submit for deep analysis.</span></span> <span data-ttu-id="e1264-266">次のビューからファイルを選択または検索できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-266">You can select or search a file from any of the following views:</span></span>

    - <span data-ttu-id="e1264-267">アラート - 成果物タイムラインの [説明] または **[\*\*\*\*詳細]** からファイル リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1264-267">Alerts - select the file links from the **Description** or **Details** in the Artifact timeline</span></span>
    - <span data-ttu-id="e1264-268">**[デバイス]** リスト - [組織のデバイス] セクションの **[説明** ] または **[詳細** ] **からファイル リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="e1264-268">**Devices list** - select the file links from the **Description** or **Details** in the **Device in organization** section</span></span>
    - <span data-ttu-id="e1264-269">[検索] ボックス - **ドロップダウン** メニューから [ファイル] を選択し、ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1264-269">Search box - select **File** from the drop–down menu and enter the file name</span></span>

2. <span data-ttu-id="e1264-270">ファイル ビューの **[深い分析** ] タブで、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e1264-270">In the **Deep analysis** tab of the file view, select **Submit**.</span></span>

   ![PE ファイルの提出は、[ファイルの詳細] セクションでのみ実行できます。](images/submit-file.png)

   > [!NOTE]
   > <span data-ttu-id="e1264-272">PE ファイルのみをサポートします。このファイルには、.exeファイル _.dll_ があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-272">Only PE files are supported, including _.exe_ and _.dll_ files.</span></span>

<span data-ttu-id="e1264-273">進行状況バーが表示され、分析の異なるステージに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-273">A progress bar is displayed and provides information on the different stages of the analysis.</span></span> <span data-ttu-id="e1264-274">分析が完了したら、レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-274">You can then view the report when the analysis is done.</span></span>

> [!NOTE]
> <span data-ttu-id="e1264-275">デバイスの可用性に応じて、サンプルの収集時間は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-275">Depending on device availability, sample collection time can vary.</span></span> <span data-ttu-id="e1264-276">サンプル コレクションには 3 時間のタイムアウトがあります。</span><span class="sxs-lookup"><span data-stu-id="e1264-276">There is a 3–hour timeout for sample collection.</span></span> <span data-ttu-id="e1264-277">コレクションは失敗し、その時点でデバイスレポートにオンライン のWindows 10操作が中止されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-277">The collection will fail and the operation will abort if there is no online Windows 10 device reporting at that time.</span></span> <span data-ttu-id="e1264-278">ファイルを再送信して詳細な分析を行い、ファイルの新しいデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-278">You can re–submit files for deep analysis to get fresh data on the file.</span></span>

### <a name="view-deep-analysis-reports"></a><span data-ttu-id="e1264-279">詳細な分析レポートの表示</span><span class="sxs-lookup"><span data-stu-id="e1264-279">View deep analysis reports</span></span>

<span data-ttu-id="e1264-280">提供された詳細分析レポートを表示して、提出したファイルに関する詳細な分析情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e1264-280">View the provided deep analysis report to see more in-depth insights on the file you submitted.</span></span> <span data-ttu-id="e1264-281">この機能は、ファイル ビュー コンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-281">This feature is available in the file view context.</span></span>

<span data-ttu-id="e1264-282">次のセクションの詳細を示す包括的なレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e1264-282">You can view the comprehensive report that provides details on the following sections:</span></span>

- <span data-ttu-id="e1264-283">Behaviors</span><span class="sxs-lookup"><span data-stu-id="e1264-283">Behaviors</span></span>
- <span data-ttu-id="e1264-284">オブザーブル</span><span class="sxs-lookup"><span data-stu-id="e1264-284">Observables</span></span>

<span data-ttu-id="e1264-285">提供される詳細は、潜在的な攻撃の兆候がある場合の調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e1264-285">The details provided can help you investigate if there are indications of a potential attack.</span></span>

1. <span data-ttu-id="e1264-286">詳細分析のために提出したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1264-286">Select the file you submitted for deep analysis.</span></span>
2. <span data-ttu-id="e1264-287">[詳細分析 **] タブを選択** します。以前のレポートがある場合は、レポートの概要がこのタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1264-287">Select the **Deep analysis** tab. If there are any previous reports, the report summary will appear in this tab.</span></span>

    ![詳細分析レポートには、複数のカテゴリの詳細情報が表示されます。](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a><span data-ttu-id="e1264-289">詳細な分析のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e1264-289">Troubleshoot deep analysis</span></span>

<span data-ttu-id="e1264-290">ファイルを送信しようとするときに問題が発生した場合は、次のトラブルシューティングの各手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="e1264-290">If you come across a problem when trying to submit a file, try each of the following troubleshooting steps.</span></span>

1. <span data-ttu-id="e1264-291">問題のファイルが PE ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-291">Ensure that the file in question is a PE file.</span></span> <span data-ttu-id="e1264-292">PE ファイルには、 _通常_ 、.exeまたは _.dll_ (実行可能プログラムまたはアプリケーション) があります。</span><span class="sxs-lookup"><span data-stu-id="e1264-292">PE files typically have _.exe_ or _.dll_ extensions (executable programs or applications).</span></span>
2. <span data-ttu-id="e1264-293">サービスがファイルへのアクセス権を持ち、ファイルがまだ存在し、破損または変更されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="e1264-293">Ensure the service has access to the file, that it still exists, and hasn't been corrupted or modified.</span></span>
3. <span data-ttu-id="e1264-294">しばらく待って、もう一度ファイルを送信してみてください。</span><span class="sxs-lookup"><span data-stu-id="e1264-294">Wait a short while and try to submit the file again.</span></span> <span data-ttu-id="e1264-295">キューが満たされている可能性があります。または一時的な接続または通信エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e1264-295">The queue may be full, or there was a temporary connection or communication error.</span></span>
4. <span data-ttu-id="e1264-296">サンプル コレクション ポリシーが構成されていない場合、既定の動作はサンプル コレクションを許可します。</span><span class="sxs-lookup"><span data-stu-id="e1264-296">If the sample collection policy isn't configured, then the default behavior is to allow sample collection.</span></span> <span data-ttu-id="e1264-297">構成されている場合は、ファイルを再度送信する前に、ポリシー設定でサンプル コレクションが許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1264-297">If it's configured, then verify the policy setting allows sample collection before submitting the file again.</span></span> <span data-ttu-id="e1264-298">サンプル コレクションが構成されている場合は、次のレジストリ値を確認します。</span><span class="sxs-lookup"><span data-stu-id="e1264-298">When sample collection is configured, then check the following registry value:</span></span>

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. <span data-ttu-id="e1264-299">グループ ポリシーを使用して組織単位を変更します。</span><span class="sxs-lookup"><span data-stu-id="e1264-299">Change the organizational unit through the Group Policy.</span></span> <span data-ttu-id="e1264-300">詳細については、「グループ ポリシーで [構成する」を参照してください](configure-endpoints-gp.md)。</span><span class="sxs-lookup"><span data-stu-id="e1264-300">For more information, see [Configure with Group Policy](configure-endpoints-gp.md).</span></span>
1. <span data-ttu-id="e1264-301">これらの手順で問題が解決しない場合は、 [次の](mailto:winatp@microsoft.com)winatp@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e1264-301">If these steps do not resolve the issue, contact [winatp@microsoft.com](mailto:winatp@microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e1264-302">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1264-302">Related topics</span></span>

- [<span data-ttu-id="e1264-303">デバイスの対応措置を講じる</span><span class="sxs-lookup"><span data-stu-id="e1264-303">Take response actions on a device</span></span>](respond-machine-alerts.md)
- [<span data-ttu-id="e1264-304">ファイルの調査</span><span class="sxs-lookup"><span data-stu-id="e1264-304">Investigate files</span></span>](investigate-files.md)
