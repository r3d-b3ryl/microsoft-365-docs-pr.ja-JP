---
title: ネットワーク保護を有効にする
description: グループ ポリシー、PowerShell、またはモバイル デバイス管理と構成マネージャーを使用してネットワーク保護を有効にします。
keywords: ANetwork の保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン、有効化、有効にする
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c7a2d943ec1813623065e70330b914a3911d1eb
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2021
ms.locfileid: "51769000"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="d62ba-104">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="d62ba-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d62ba-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d62ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="d62ba-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d62ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d62ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d62ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="d62ba-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d62ba-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d62ba-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d62ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d62ba-110">[ネットワーク保護](network-protection.md) は、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d62ba-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="d62ba-111">テスト環境 [でネットワーク保護](evaluate-network-protection.md) を監査して、ブロックするアプリを確認してから有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d62ba-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="d62ba-112">ネットワーク フィルター構成オプションの詳細</span><span class="sxs-lookup"><span data-stu-id="d62ba-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="d62ba-113">ネットワーク保護が有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="d62ba-113">Check if network protection is enabled</span></span>

<span data-ttu-id="d62ba-114">レジストリ エディターを使用して、ローカル デバイスでネットワーク保護が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="d62ba-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="d62ba-115">タスク バーの **[スタート** ] ボタンを選択し **、「regedit」と入力して** レジストリ エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d62ba-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="d62ba-116">サイド **メニュー HKEY_LOCAL_MACHINE** を選択する</span><span class="sxs-lookup"><span data-stu-id="d62ba-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="d62ba-117">入れ子になったメニューから **ソフトウェア** ポリシーへの移動 Microsoft  >  **Windows Defender Windows Defender**  >    >    >  **Exploit Guard**  >  **ネットワーク保護**</span><span class="sxs-lookup"><span data-stu-id="d62ba-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>

4. <span data-ttu-id="d62ba-118">デバイス上のネットワーク保護の現在の状態を表示するには **、[EnableNetworkProtection]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d62ba-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="d62ba-119">0 または **Off**</span><span class="sxs-lookup"><span data-stu-id="d62ba-119">0, or **Off**</span></span>
    * <span data-ttu-id="d62ba-120">1、または **On**</span><span class="sxs-lookup"><span data-stu-id="d62ba-120">1, or **On**</span></span>
    * <span data-ttu-id="d62ba-121">2、または **監査** モード</span><span class="sxs-lookup"><span data-stu-id="d62ba-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="d62ba-123">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="d62ba-123">Enable network protection</span></span>

<span data-ttu-id="d62ba-124">次の方法を使用してネットワーク保護を有効にする。</span><span class="sxs-lookup"><span data-stu-id="d62ba-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="d62ba-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d62ba-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="d62ba-126">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="d62ba-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="d62ba-127">Microsoft Endpoint Manager / Intune</span><span class="sxs-lookup"><span data-stu-id="d62ba-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="d62ba-128">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="d62ba-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="d62ba-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d62ba-129">PowerShell</span></span>

1. <span data-ttu-id="d62ba-130">[ **スタート] メニューに「powershell」** と入力し、[管理者 **Windows PowerShellを右** クリックし、[管理者として **実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="d62ba-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="d62ba-131">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="d62ba-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="d62ba-132">オプション: 次のコマンドレットを使用して監査モードで機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d62ba-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="d62ba-133">機能 `Disabled` の代わりに、 `AuditMode` または `Enabled` 機能をオフにする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d62ba-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="d62ba-134">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="d62ba-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="d62ba-135">[./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)構成サービス プロバイダー (CSP) を使用して、ネットワーク保護を有効または無効にするか、監査モードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d62ba-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="d62ba-136">Microsoft Endpoint Manager (旧 Intune)</span><span class="sxs-lookup"><span data-stu-id="d62ba-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="d62ba-137">Microsoft Endpoint Manager 管理センターにサインインします (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d62ba-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="d62ba-138">エンドポイント保護構成プロファイル [の作成または編集](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="d62ba-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="d62ba-139">プロファイル **フローの [構成** 設定] で **、[Microsoft Defender Exploit Guard Network** filtering Network protection Enable or Audit  >    >    >   only] に **移動します。**</span><span class="sxs-lookup"><span data-stu-id="d62ba-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="d62ba-140">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="d62ba-140">Group Policy</span></span>

<span data-ttu-id="d62ba-141">ドメインに参加しているコンピューターまたはスタンドアロン コンピューターでネットワーク保護を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d62ba-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="d62ba-142">スタンドアロン コンピューターで、[スタート] に移動 **し、[グループ** ポリシーの編集] を入力して **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d62ba-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="d62ba-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="d62ba-143">*-Or-*</span></span>

    <span data-ttu-id="d62ba-144">ドメインに参加しているグループ ポリシー管理コンピューターで、グループ [](https://technet.microsoft.com/library/cc731212.aspx)ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d62ba-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="d62ba-145">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d62ba-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="d62ba-146">ツリーを Windows コンポーネント **の Microsoft** Defender Antivirus  >  **Windows Defender** Exploit  >  **Guard ネットワーク保護に**  >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="d62ba-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="d62ba-147">以前のバージョンの Windows では、グループ ポリシー パスに "Microsoft Defender ウイルス対策" の代わりにWindows Defenderウイルス対策プログラムが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d62ba-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="d62ba-148">[ユーザーとアプリによる **危険** な Web サイトへのアクセスを防止する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="d62ba-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="d62ba-149">[オプション] セクションで、次のいずれかのオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d62ba-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="d62ba-150">**ブロック** - ユーザーが悪意のある IP アドレスとドメインにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="d62ba-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="d62ba-151">**無効 (既定)** - ネットワーク保護機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="d62ba-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="d62ba-152">ユーザーが悪意のあるドメインにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="d62ba-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="d62ba-153">**監査モード** - ユーザーが悪意のある IP アドレスまたはドメインにアクセスすると、Windows イベント ログにイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="d62ba-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="d62ba-154">ただし、ユーザーはアドレスへのアクセスをブロックされません。</span><span class="sxs-lookup"><span data-stu-id="d62ba-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d62ba-155">ネットワーク保護を完全に有効にするには、[グループ ポリシー] オプションを[有効]に設定し、[オプション] ドロップダウン メニューの [ブロック] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d62ba-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="d62ba-156">レジストリ エディターを使用して、ローカル コンピューターでネットワーク保護が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="d62ba-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="d62ba-157">[スタート **] を** 選択し **、「regedit」と** 入力してレジストリ **エディターを開きます**。</span><span class="sxs-lookup"><span data-stu-id="d62ba-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="d62ba-158">[ファイル] に **移動HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="d62ba-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="d62ba-159">**[EnableNetworkProtection] を選択し**、値を確認します。</span><span class="sxs-lookup"><span data-stu-id="d62ba-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="d62ba-160">0=Off</span><span class="sxs-lookup"><span data-stu-id="d62ba-160">0=Off</span></span>
   * <span data-ttu-id="d62ba-161">1=On</span><span class="sxs-lookup"><span data-stu-id="d62ba-161">1=On</span></span>
   * <span data-ttu-id="d62ba-162">2=Audit</span><span class="sxs-lookup"><span data-stu-id="d62ba-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="d62ba-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="d62ba-163">See also</span></span>

* [<span data-ttu-id="d62ba-164">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="d62ba-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="d62ba-165">ネットワーク保護を評価する</span><span class="sxs-lookup"><span data-stu-id="d62ba-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="d62ba-166">ネットワーク保護のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d62ba-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
