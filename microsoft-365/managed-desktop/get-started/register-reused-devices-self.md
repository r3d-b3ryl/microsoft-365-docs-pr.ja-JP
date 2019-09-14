---
title: 既存のデバイスを自分で登録する
description: 再利用されたデバイスを登録します。これにより、Microsoft マネージドデスクトップで管理できるようになります。
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2527b18c422d53060398f90b7470db8b4959afa
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982950"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="5abf9-103">既存のデバイスを自分で登録する</span><span class="sxs-lookup"><span data-stu-id="5abf9-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="5abf9-104">このトピックでは、既に所有しているデバイスを再利用して、Microsoft マネージドデスクトップで登録する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="5abf9-105">新しいデバイスを使用している場合は、代わりに「 [Microsoft Managed Desktop で新しいデバイスを登録](register-devices-self.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5abf9-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="5abf9-106">パートナーのプロセスは、パートナーが[デバイスを登録する手順](register-devices-partner.md)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="5abf9-107">Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="5abf9-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="5abf9-108">Azure Portal で Microsoft Managed Desktop を使用してデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-108">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="5abf9-109">既存のデバイスを登録するための準備</span><span class="sxs-lookup"><span data-stu-id="5abf9-109">Prepare to register existing devices</span></span>


<span data-ttu-id="5abf9-110">既存のデバイスを登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="5abf9-111">各デバイスのハードウェアハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="5abf9-112">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="5abf9-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="5abf9-113">[Microsoft マネージドデスクトップにデバイスを登録](#register-devices)します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="5abf9-114">画像が正しいことをもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="5abf9-115">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="5abf9-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="5abf9-116">ハードウェアハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="5abf9-116">Obtain the hardware hash</span></span>

<span data-ttu-id="5abf9-117">Microsoft マネージドデスクトップは、ハードウェアハッシュを参照して各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="5abf9-118">既に使用しているデバイスからこの情報を取得するには、次の4つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="5abf9-119">ハードウェアハッシュを含む自動操縦登録ファイルについては、OEM サプライヤーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="5abf9-120">[構成マネージャー](#configuration-manager)でカスタムレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="5abf9-121">[Active Directory](#active-directory-powershell-script-method)を使用するか、または各デバイスで[手動](#manual-powershell-script-method)で Windows PowerShell スクリプトを実行して、ファイルに結果を収集します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="5abf9-122">各デバイスを開始しますが、Windows セットアップの動作を完了せず[に、リムーバブルフラッシュドライブでハッシュを収集](#flash-drive-method)します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="5abf9-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5abf9-123">Configuration Manager</span></span>

<span data-ttu-id="5abf9-124">System Center Configuration Manager を使用して、Microsoft マネージドデスクトップに登録する既存のデバイスからハードウェアハッシュを収集できます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-124">You can use System Center Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5abf9-125">この情報を取得するデバイスには、Windows 10、バージョン1703以降が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="5abf9-126">また、System Center の現在のブランチサイトに接続されている構成マネージャークライアントのデバイスも必要です。</span><span class="sxs-lookup"><span data-stu-id="5abf9-126">You also need a device that is a Configuration Manager client connected to System Center Current Branch site.</span></span> <span data-ttu-id="5abf9-127">また、SQL Server Reporting Services が有効になっている環境で、レポートポイントサイトシステムの役割が設定されている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="5abf9-128">これらの前提条件をすべて満たしている場合は、次の手順を実行して情報を収集する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="5abf9-129">構成マネージャーコンソールで、[**監視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="5abf9-130">[監視] ワークスペースで、[**レポート**] を展開し、[**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="5abf9-131">[**ホーム**] タブの [**作成**] セクションで、[**レポート**の作成] を選択して、レポートの作成ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="5abf9-132">[**情報**] ページで、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="5abf9-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="5abf9-133">**Name:** レポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="5abf9-134">**説明:** レポートの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="5abf9-135">**サーバー:** このレポートを作成するレポートサーバーの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="5abf9-136">**パス:**[**参照**] を選択して、レポートを保存するフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="5abf9-137">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-137">Select **Next**.</span></span> 
6. <span data-ttu-id="5abf9-138">[**概要**] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="5abf9-139">[**前**へ] を選択して設定を変更するか、[**次へ**] を選択して、構成マネージャーでレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="5abf9-140">[**完了**] ページで、[**閉じる**] を選択してウィザードを終了し、レポート**ビルダー**を開いてレポート設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="5abf9-141">メッセージが表示されたら、ユーザーアカウントとパスワードを入力し、[OK] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="5abf9-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="5abf9-142">レポートビルダーがデバイスにインストールされていない場合は、インストールするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="5abf9-143">レポートを変更および作成するために必要な**レポートビルダーをインストールするに**は、[実行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="5abf9-144">**Microsoft レポートビルダーで**、レポート用の SQL ステートメントを入力し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="5abf9-145">左側のウィンドウで、[**データセット**] を選択し、右クリックして**データセットを追加**します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="5abf9-146">[**クエリ**] タブに移動し、 *DataSet0*という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="5abf9-147">[**レポートに埋め込まれたデータセットを使用する**] を選択します。レポートビルダーが開きます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="5abf9-148">**レポートビルダー**で、[**データソース:**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="5abf9-149">"AutoGen" で始まる既定のデータソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="5abf9-150">[**クエリの種類**] をテキストとして選択し、次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-150">Choose **Query type as Text**, and then enter this query:</span></span>

```

SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp  
       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid


```
5. <span data-ttu-id="5abf9-151">[**フィールド**] タブに移動します。**フィールド名**と**フィールドソース**の値は既に入力されています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="5abf9-152">入力されていない場合は、[**追加**] を選択し、[**クエリフィールド**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="5abf9-153">**フィールド名**と**フィールドソース**を入力します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="5abf9-154">次の各値に対して、次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="5abf9-155">製造</span><span class="sxs-lookup"><span data-stu-id="5abf9-155">Manufacturer</span></span> 
    - <span data-ttu-id="5abf9-156">モデル</span><span class="sxs-lookup"><span data-stu-id="5abf9-156">Model</span></span> 
    - <span data-ttu-id="5abf9-157">求め</span><span class="sxs-lookup"><span data-stu-id="5abf9-157">Serial_Number</span></span> 
    - <span data-ttu-id="5abf9-158">ハードウェアハッシュ</span><span class="sxs-lookup"><span data-stu-id="5abf9-158">HardwareHash</span></span>
7. <span data-ttu-id="5abf9-159">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-159">Select **OK**.</span></span>

<span data-ttu-id="5abf9-160">**次に、** 次の手順に従ってレポートの表示を定義し、レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="5abf9-161">**テーブルまたはマトリックス**を選択します。新しいウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="5abf9-162">[**データセットの選択**] で、[**このレポート内の既存のデータセットを選択する] または [共有データセット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="5abf9-163">**DataSet0** (既定値) を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="5abf9-164">[**製造元**]、[**モデル**]、および [**シリアル番号**] を [**行グループ**] ボックスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5abf9-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="5abf9-165">[**ハードウェアハッシュ**] を [**値**] ボックスにドラッグし、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="5abf9-166">[**小計と総計を表示する]** と [**グループを展開/折りたたみ**する] のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5abf9-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="5abf9-167">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-167">Select **Next**.</span></span>
6. <span data-ttu-id="5abf9-168">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-168">Select **Finish**.</span></span>
7. <span data-ttu-id="5abf9-169">[**実行**] を選択してレポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-169">Select **Run** to run your report.</span></span> <span data-ttu-id="5abf9-170">レポートが期待する情報を提供していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="5abf9-171">必要に応じて、[**デザイン**] を選択して、レポートを変更するためのデザインビューに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="5abf9-172">レポートをレポートサーバーに保存するには、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="5abf9-173">[監視ワークスペースのレポートノードで新しいレポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="5abf9-174">**最後に、** 次の手順に従ってレポートをエクスポートし、それを使用してデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="5abf9-175">(前の手順の後に移動した場合は、このセクションの手順1と2に従う必要があります)。</span><span class="sxs-lookup"><span data-stu-id="5abf9-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="5abf9-176">構成マネージャーコンソールで、[**監視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="5abf9-177">[**監視**] で、[**レポート**] を展開し、[**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="5abf9-178">前に作成した名前を使用してレポートを検索します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="5abf9-179">このレポートを右クリックし、[**実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="5abf9-180">開いたダイアログで、[**エクスポート**] を選択し、[ **CSV として保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="5abf9-181">このバージョンのレポートは、構成マネージャーが通信するすべての Windows 10 デバイスからハッシュを抽出します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="5abf9-182">Microsoft マネージドデスクトップに登録する予定のデバイスのみに結果をフィルター処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="5abf9-183">構成マネージャーのクエリは、エクスポートされた列名にスペースを使用できません。そのため、「シリアル」と「ハードウェアハッシュ」を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="5abf9-184">エクスポートされた CSV ファイルがあるので、デバイスの登録を続行する前に、ここに示すようにレポートヘッダーを編集して*シリアル番号*と*ハードウェアハッシュ*を読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="5abf9-185">[Azure ポータルを使用してデバイスを登録](#register-devices-by-using-the-azure-portal)するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-185">Now you can proceed to [Register devices by using the Azure Portal](#register-devices-by-using-the-azure-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="5abf9-186">Active Directory PowerShell スクリプトメソッド</span><span class="sxs-lookup"><span data-stu-id="5abf9-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="5abf9-187">Active Directory 環境では、 `Get-MMDRegistrationInfo` PowerShell コマンドレットを使用して、WinRM を使用して Active directory グループ内のデバイスから情報をリモートで収集できます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="5abf9-188">また、 `Get-AD Computer`このコマンドレットを使用して、カタログに含まれている特定のハードウェアモデル名のフィルター結果を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="5abf9-189">これを行うには、まずこれらの前提条件を確認してから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="5abf9-190">WinRM は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-190">WinRM is enabled.</span></span>
- <span data-ttu-id="5abf9-191">登録するデバイスがネットワーク上でアクティブになっている (つまり、切断されていないかオフになっている)。</span><span class="sxs-lookup"><span data-stu-id="5abf9-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="5abf9-192">デバイス上でリモートで実行するためのアクセス許可を持つ domain credential パラメーターがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="5abf9-193">Windows ファイアウォールが WMI へのアクセスを許可していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="5abf9-194">そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="5abf9-195">**Windows Defender ファイアウォール**コントロールパネルを開き、[ **Windows defender ファイアウォール経由でアプリまたは機能を許可**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="5abf9-196">一覧で [ **Windows Management Instrumentation (WMI)** ] を見つけ、[**プライベートとパブリック**] の両方で有効にして、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="5abf9-197">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="5abf9-198">次*のいずれかのスクリプトを実行*します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="5abf9-199">デバイスのエントリが存在する可能性があるディレクトリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5abf9-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="5abf9-200">Windows Server Active Directory ドメインサービスと Azure Active Directory を含む、*すべて*のディレクトリから各デバイスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="5abf9-201">この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="5abf9-202">デバイスのエントリが存在する可能性があるアクセス管理サービス。</span><span class="sxs-lookup"><span data-stu-id="5abf9-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="5abf9-203">System Center Configuration manager、Microsoft Intune、Windows 自動操縦など、*すべて*の管理サービスから各デバイスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-203">Remove entries for each device from *all* management services, including System Center Configuration Manger, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="5abf9-204">この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="5abf9-205">これで、デバイスの[登録](#register-devices)に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="5abf9-206">PowerShell スクリプトの手動メソッド</span><span class="sxs-lookup"><span data-stu-id="5abf9-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="5abf9-207">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="5abf9-208">`Install-Script -Name Get-MMDRegistrationInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="5abf9-209">`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="5abf9-210">ハッシュデータを結合します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="5abf9-211">Flash drive メソッド</span><span class="sxs-lookup"><span data-stu-id="5abf9-211">Flash drive method</span></span>

1. <span data-ttu-id="5abf9-212">登録している以外のデバイスに USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="5abf9-213">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="5abf9-214">`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="5abf9-215">登録するデバイスを有効にしますが、*セットアップの操作は開始*しないでください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="5abf9-216">セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="5abf9-217">USB ドライブを挿入して、SHIFT + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="5abf9-218">管理者権限で PowerShell プロンプトを開き、を実行`cd <pathToUsb>`します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="5abf9-219">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="5abf9-220">`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="5abf9-221">USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="5abf9-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="5abf9-222">ハッシュデータを結合します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="5abf9-223">登録が完了するまでは、デバイスの電源を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="5abf9-224">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="5abf9-224">Merge hash data</span></span>

<span data-ttu-id="5abf9-225">手動の PowerShell または flash drive メソッドによってハードウェアハッシュデータを収集した場合は、CSV ファイル内のデータを1つのファイルにまとめて登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="5abf9-226">これを簡単にするためのサンプル PowerShell スクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-226">Here's a sample PowerShell script to make this easy:</span></span>

`Get-ChildItem -Filter *.csv |Select-Object -expandproperty FullName | Import-Csv |ConvertTo-Csv -NoTypeInformation | %{$_.Replace('"','')}| Out-File -Append .\joinedcsv\aggregatedDevices.csv`

<span data-ttu-id="5abf9-227">ハッシュデータを1つの CSV ファイルに結合すると、[デバイスの登録](#register-devices)に進むことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="5abf9-228">デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="5abf9-228">Register devices</span></span>

<span data-ttu-id="5abf9-229">CSV ファイルは、登録用に特定の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="5abf9-230">前の手順でデータを自分で収集した場合は、ファイルが正しい形式になっている必要があります。業者からファイルを取得する場合は、形式を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="5abf9-231">便宜上、この CSV ファイルの[テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="5abf9-232">ファイルには、サンプル 1 (製造元、モデルなど) と**まったく同じ列見出し**を含める必要がありますが、その他の行については独自のデータを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abf9-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="5abf9-233">テンプレートを使用している場合は、メモ帳などのテキスト編集ツールでそのテンプレートを開き、行1のみにデータを入力し、2行以下にデータを入力することを検討します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="5abf9-234">サンプルデータの変更を忘れると、登録は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="5abf9-235">Azure ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="5abf9-235">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="5abf9-236">Microsoft マネージドデスクトップの[Azure ポータル](https://aka.ms/mmdportal)で、左側のナビゲーションウィンドウの [**デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-236">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="5abf9-237">[ **+ デバイスの登録**] を選択します。フライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="5abf9-238">[![[デバイスの登録] を選択した後のフライイン](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="5abf9-238">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (残念ながら、これは当てはまりません。このメモを削除することはできますが、それについてお客様がチャットできるようになるまで、そのままにしておきます。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="5abf9-240">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-240">Follow these steps:</span></span>

1. <span data-ttu-id="5abf9-241">[**ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="5abf9-242">必要に応じて、独自の追跡目的のために、**注文 id**または**購買 id**を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="5abf9-243">これらの値に書式の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="5abf9-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="5abf9-244">[**デバイスの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-244">Select **Register devices**.</span></span> <span data-ttu-id="5abf9-245">システムによってデバイス**ブレード**上のデバイスの一覧にデバイスが追加され、[**登録保留中**] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="5abf9-246">通常、登録にかかる時間は10分未満で、成功した場合、デバイスは**ユーザーのための準備**完了として表示され、エンドユーザーが使用を開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="5abf9-247">メインの**Microsoft Managed Desktop-Devices**ページでのデバイス登録の進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="5abf9-248">報告される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5abf9-248">Possible states reported there include:</span></span>

| <span data-ttu-id="5abf9-249">State</span><span class="sxs-lookup"><span data-stu-id="5abf9-249">State</span></span> | <span data-ttu-id="5abf9-250">説明</span><span class="sxs-lookup"><span data-stu-id="5abf9-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="5abf9-251">登録保留中</span><span class="sxs-lookup"><span data-stu-id="5abf9-251">Registration pending</span></span> | <span data-ttu-id="5abf9-252">登録はまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="5abf9-252">Registration is not done yet.</span></span> <span data-ttu-id="5abf9-253">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-253">Check back later.</span></span> |
| <span data-ttu-id="5abf9-254">登録の失敗</span><span class="sxs-lookup"><span data-stu-id="5abf9-254">Registration failed</span></span> | <span data-ttu-id="5abf9-255">登録を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5abf9-255">Registration could not be completed.</span></span> <span data-ttu-id="5abf9-256">詳細については、「 [device registration のトラブルシューティング](#troubleshooting-device-registration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="5abf9-257">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="5abf9-257">Ready for user</span></span> | <span data-ttu-id="5abf9-258">登録が成功し、デバイスをエンドユーザーに配信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5abf9-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="5abf9-259">Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5abf9-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="5abf9-260">アクティブ</span><span class="sxs-lookup"><span data-stu-id="5abf9-260">Active</span></span> | <span data-ttu-id="5abf9-261">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="5abf9-262">これは、デバイスを定期的に使用していることも示しています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="5abf9-263">未使用</span><span class="sxs-lookup"><span data-stu-id="5abf9-263">Inactive</span></span> | <span data-ttu-id="5abf9-264">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="5abf9-265">しかし、最近7日間ではデバイスを使用していません。</span><span class="sxs-lookup"><span data-stu-id="5abf9-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="5abf9-266">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5abf9-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="5abf9-267">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="5abf9-267">Error message</span></span> | <span data-ttu-id="5abf9-268">詳細</span><span class="sxs-lookup"><span data-stu-id="5abf9-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="5abf9-269">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="5abf9-269">Device not found</span></span> | <span data-ttu-id="5abf9-270">提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5abf9-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="5abf9-271">これらの値は、デバイスの提供元に確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="5abf9-272">ハードウェアハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="5abf9-272">Hardware hash not valid</span></span> | <span data-ttu-id="5abf9-273">このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="5abf9-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="5abf9-274">ハードウェアハッシュをもう一度確認してから再送信します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="5abf9-275">デバイスは既に登録されています</span><span class="sxs-lookup"><span data-stu-id="5abf9-275">Device already registered</span></span> | <span data-ttu-id="5abf9-276">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-276">This device is already registered to your organization.</span></span> <span data-ttu-id="5abf9-277">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5abf9-277">No further action required.</span></span> |
| <span data-ttu-id="5abf9-278">別の組織によって要求されるデバイス</span><span class="sxs-lookup"><span data-stu-id="5abf9-278">Device claimed by another organization</span></span> | <span data-ttu-id="5abf9-279">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="5abf9-280">デバイスサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="5abf9-281">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="5abf9-281">Unexpected error</span></span> | <span data-ttu-id="5abf9-282">要求は自動的に処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="5abf9-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="5abf9-283">サポートに連絡して、要求 ID を提供します。<requestId></span><span class="sxs-lookup"><span data-stu-id="5abf9-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="5abf9-284">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="5abf9-284">Check the image</span></span>

<span data-ttu-id="5abf9-285">デバイスが Microsoft マネージドデスクトップパートナーのサプライヤーからのものである場合は、イメージが正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="5abf9-286">また、必要に応じて、自分で画像を適用することも歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="5abf9-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="5abf9-287">開始するには、作業している Microsoft の担当者に連絡して、イメージを適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="5abf9-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="5abf9-288">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="5abf9-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5abf9-289">ユーザーにデバイスを渡す前に、そのユーザーの[適切なライセンス](../get-ready/prerequisites.md)を取得して適用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abf9-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="5abf9-290">すべてのライセンスが適用されている場合は、[デバイスを使用する準備](get-started-devices.md)ができたら、ユーザーはデバイスを起動して、Windows セットアップ操作を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="5abf9-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









