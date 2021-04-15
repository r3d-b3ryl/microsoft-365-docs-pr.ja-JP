---
title: Microsoft Defender AV 保護更新プログラムを最新のエンドポイントに適用する
description: しばらく更新されていないエンドポイントに対して更新プログラムを適用する時間と方法を定義します。
keywords: 更新プログラム、保護、古い、キャッチアップ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 81c7fb2bb7cd20fea3f343097811078ed744c3eb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765373"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="8cbd2-104">Microsoft Defender ウイルス対策の更新プログラムを管理し、最新のエンドポイントをスキャンする</span><span class="sxs-lookup"><span data-stu-id="8cbd2-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8cbd2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8cbd2-105">**Applies to:**</span></span>

- [<span data-ttu-id="8cbd2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8cbd2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8cbd2-107">Microsoft Defender Antivirus を使用すると、エンドポイントが更新を回避できる期間や、更新とスキャンが必要になる前に見逃す可能性があるスキャンの数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="8cbd2-108">これは、デバイスが企業ネットワークや外部ネットワークに接続されがちな環境、または毎日使用されていないデバイスで特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="8cbd2-109">たとえば、特定の PC を使用する従業員は 3 日間休憩中で、その間は PC にログオンできません。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="8cbd2-110">ユーザーが作業に戻り、PC にログオンすると、Microsoft Defender ウイルス対策は直ちに最新の保護更新プログラムを確認してダウンロードし、スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="8cbd2-111">しばらく更新していないエンドポイントのキャッチアップ保護更新プログラムを設定する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="8cbd2-112">Microsoft Defender Antivirus が指定した期間保護更新プログラムをダウンロードしなかった場合は、次のログオン時に最新の更新プログラムを自動的に確認してダウンロードする設定を行います。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="8cbd2-113">これは、起動時に自動更新の [ダウンロードをグローバルに無効にしている場合に便利です](manage-event-based-updates-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8cbd2-114">Configuration Manager を使用してキャッチアップ保護更新プログラムを構成する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="8cbd2-115">Microsoft Endpoint Manager コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを [Overview  >  **Endpoint Protection**  >  **Antimalware Policies]** に展開します)。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="8cbd2-116">[セキュリティ インテリジェンスの **更新プログラム] セクションに移動** し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="8cbd2-117">クライアント **コンピューターがオフラインの場合は、2** つ以上の連続したスケジュールされた更新プログラムを [はい] に設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="8cbd2-118">[If  **Configuration Manager]** をセキュリティ インテリジェンス更新プログラムのソースとして使用します。。Configuration Manager によって配信される保護更新プログラムが古いとみなされる時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="8cbd2-119">これにより、定義されたフォールバック ソースの順序に基づいて、次の更新場所 [が使用されます](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="8cbd2-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-120">Click **OK**.</span></span>

4.  <span data-ttu-id="8cbd2-121">[更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="8cbd2-122">グループ ポリシーを使用してキャッチアップ更新機能を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="8cbd2-123">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8cbd2-124">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8cbd2-125">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="8cbd2-126">Microsoft Defender ウイルス対策と **署名更新プログラム> Windows コンポーネントにツリー>展開します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="8cbd2-127">[キャッチアップ セキュリティ **インテリジェンスの** 更新が必要な日数を定義する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8cbd2-128">Microsoft Defender AV で最新の保護更新プログラムを確認してダウンロードする日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="8cbd2-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8cbd2-130">PowerShell コマンドレットを使用してキャッチアップ保護更新プログラムを構成する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="8cbd2-131">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="8cbd2-132">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8cbd2-133">キャッチアップ保護更新プログラムを構成するには、Windows 管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="8cbd2-134">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="8cbd2-135">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8cbd2-136">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="8cbd2-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="8cbd2-137">保護が古いとして報告される前の日数を設定する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="8cbd2-138">また、Microsoft Defender ウイルス対策保護が古いまたは古いと見なされる日数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="8cbd2-139">指定した日数を過ごした後、クライアントはそれ自体を古い日付として報告し、PC のユーザーにエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="8cbd2-140">また、WSUS または Microsoft Update を最初のソースとして設定した後でセカンダリ ソースとして MMPC を使用する場合など、Microsoft Defender Antivirus が他のソースから (定義済みのフォールバック ソースの順序に基 [づいて)](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)更新プログラムをダウンロードしようとする場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="8cbd2-141">グループ ポリシーを使用して、保護が古いと見なされる日数を指定する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="8cbd2-142">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="8cbd2-143">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="8cbd2-144">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="8cbd2-145">Microsoft Defender **Antivirus >署名更新プログラム>に** ツリーを展開し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="8cbd2-146">[スパイウェア定義 **が** 古いと見なされる日数を定義する] をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="8cbd2-147">Microsoft Defender AV でスパイウェア セキュリティ インテリジェンスを古い日付と見なす日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="8cbd2-148">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="8cbd2-149">[ウイルス定義 **が** 古いと見なされる日数を定義する] をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="8cbd2-150">Microsoft Defender AV でウイルス セキュリティ インテリジェンスを古い日付と見なす日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="8cbd2-151">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="8cbd2-152">しばらくスキャンされていないエンドポイントのキャッチアップ スキャンを設定する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="8cbd2-153">Microsoft Defender ウイルス対策が強制的にスキャンを実行する前に、見逃す可能性がある連続するスケジュールされたスキャンの数を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="8cbd2-154">この機能を有効にするプロセスは次の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="8cbd2-155">少なくとも 1 つのスケジュールされたスキャンをセットアップします (「スケジュール スキャン [」を参照](scheduled-catch-up-scans-microsoft-defender-antivirus.md) )。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="8cbd2-156">キャッチアップ スキャン機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="8cbd2-157">キャッチアップ スキャンが発生する前にスキップできるスキャンの数を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="8cbd2-158">この機能は、フル スキャンとクイック スキャンの両方で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="8cbd2-159">グループ ポリシーを使用してキャッチアップ スキャン機能を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="8cbd2-160">少なくとも 1 つのスケジュールされたスキャンがセットアップ済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="8cbd2-161">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="8cbd2-162">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="8cbd2-163">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="8cbd2-164">Microsoft Defender **ウイルス** 対策ソフトウェア の Windows >にツリー>展開し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="8cbd2-165">スケジュールされたクイック スキャンを設定している場合は、[キャッチアップクイック スキャンを有効にする] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="8cbd2-166">スケジュールされたフル スキャンを設定している場合は、[キャッチアップフル スキャンを有効にする] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8cbd2-167">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-167">Click **OK**.</span></span>
    3. <span data-ttu-id="8cbd2-168">[キャッチアップ **スキャンを** 強制する日数を定義する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="8cbd2-169">次にユーザーが PC にログオンするときにスキャンが自動的に実行される前に見逃す可能性があるスキャンの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="8cbd2-170">実行されるスキャンの種類は、[スケジュールされたスキャンに使用するスキャンの種類を指定する] **によって** 決まります (「スキャンのスケジュール」 [トピックを参照](scheduled-catch-up-scans-microsoft-defender-antivirus.md) )。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="8cbd2-171">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="8cbd2-172">グループ ポリシー設定のタイトルは、日数を参照します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="8cbd2-173">ただし、この設定は、キャッチアップ スキャンが実行される前のスキャン数 (日数ではなく) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="8cbd2-174">PowerShell コマンドレットを使用してキャッチアップ スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="8cbd2-175">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="8cbd2-176">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を[](/powershell/module/defender/)使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策および Defender コマンドレットを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="8cbd2-177">キャッチアップ スキャンを構成するには、Windows 管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="8cbd2-178">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="8cbd2-179">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8cbd2-180">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="8cbd2-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="8cbd2-181">Configuration Manager を使用してキャッチアップ スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="8cbd2-182">Microsoft Endpoint Manager コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを [Overview  >  **Endpoint Protection**  >  **Antimalware Policies]** に展開します)。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="8cbd2-183">[スケジュールされたスキャン **] セクションに移動** し、クライアント コンピューターがオフラインの場合は、選択したスキャンの種類を強制的にスキャンします **。[** はい] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="8cbd2-184">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-184">Click **OK**.</span></span>

4.  <span data-ttu-id="8cbd2-185">[更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="8cbd2-186">関連記事</span><span class="sxs-lookup"><span data-stu-id="8cbd2-186">Related articles</span></span>

- [<span data-ttu-id="8cbd2-187">Microsoft Defender ウイルス対策の展開</span><span class="sxs-lookup"><span data-stu-id="8cbd2-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cbd2-188">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cbd2-189">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="8cbd2-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cbd2-190">イベントベースの強制的な更新の管理</span><span class="sxs-lookup"><span data-stu-id="8cbd2-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cbd2-191">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="8cbd2-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cbd2-192">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="8cbd2-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)