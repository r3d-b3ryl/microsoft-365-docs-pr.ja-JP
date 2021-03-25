---
title: フォルダー アクセスの制御をカスタマイズする
description: フォルダー アクセスを制御して保護する必要がある他のフォルダーを追加するか、重要なファイルへの変更を誤ってブロックしているアプリを許可します。
keywords: フォルダー アクセスの制御、Windows 10、Windows Defender、ランサムウェア、保護、ファイル、フォルダー、カスタマイズ、フォルダーの追加、アプリの追加、許可、実行可能ファイルの追加
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199915"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="b31c6-104">フォルダー アクセスの制御をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b31c6-104">Customize controlled folder access</span></span>

<span data-ttu-id="b31c6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b31c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="b31c6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b31c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b31c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b31c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b31c6-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b31c6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b31c6-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b31c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="b31c6-110">フォルダー アクセスの制御により、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="b31c6-111">フォルダー アクセスの制御は、Windows Server 2019 および Windows 10 クライアントでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="b31c6-112">この記事では、フォルダー アクセスの制御機能をカスタマイズする方法について説明し、次のセクションを示します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="b31c6-113">追加のフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="b31c6-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="b31c6-114">保護されたフォルダーへのアクセスを許可する必要がありますアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="b31c6-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="b31c6-115">署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="b31c6-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="b31c6-116">通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b31c6-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="b31c6-117">フォルダー アクセスの制御により、悪意のあるアクティビティが検出されたアプリが監視されます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="b31c6-118">場合によっては、正当なアプリがファイルに変更を加えるのをブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b31c6-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="b31c6-119">フォルダー アクセスの制御が組織の生産性に影響を与える場合は、監査モード[](audit-windows-defender.md)でこの機能を実行して、その影響を完全に評価することもできます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="b31c6-120">追加のフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="b31c6-120">Protect additional folders</span></span>

<span data-ttu-id="b31c6-121">フォルダー アクセスの制御は、ドキュメント、ピクチャ、ムービーなどのフォルダーを含む、多くのシステムフォルダーと既定の場所 **に適用されます**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="b31c6-122">保護するフォルダーを追加できますが、既定の一覧で既定のフォルダーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b31c6-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="b31c6-123">フォルダー アクセスの制御に他のフォルダーを追加すると、既定の Windows ライブラリにファイルを保存しない場合や、ライブラリの既定の場所を変更した場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="b31c6-124">ネットワーク共有とマップされたドライブを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="b31c6-125">環境変数とワイルドカードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b31c6-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="b31c6-126">ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="b31c6-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="b31c6-127">Windows セキュリティ アプリ、グループ ポリシー、PowerShell コマンドレット、またはモバイル デバイス管理構成サービス プロバイダーを使用して、追加の保護されたフォルダーを追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="b31c6-128">Windows セキュリティ アプリを使用して追加のフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="b31c6-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="b31c6-129">タスク バーでシールド アイコンを選択するか、スタート メニューの [セキュリティ] を検索して、Windows セキュリティ アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="b31c6-130">[ **ウイルス対策&保護] を** 選択し、[ランサムウェア保護] セクション **まで下にスクロール** します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="b31c6-131">[ランサムウェア **保護の管理] を** 選択して **、[ランサムウェア保護] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="b31c6-132">[フォルダー アクセス **の制御] セクションで** 、[保護された **フォルダー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="b31c6-133">[ユーザー **アクセス制御** ] プロンプト **で [はい] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="b31c6-134">[ **保護されたフォルダー] ウィンドウ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="b31c6-135">[ **保護されたフォルダーの追加] を選択** し、プロンプトに従ってフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="b31c6-136">グループ ポリシーを使用して追加のフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="b31c6-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="b31c6-137">グループ ポリシー管理コンピューターで、グループ [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="b31c6-138">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="b31c6-139">ツリーを Windows コンポーネント **の Microsoft** Defender Antivirus  >  **Windows Defender**  >  **に** 展開  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="b31c6-140">[構成済みの **保護されたフォルダー] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="b31c6-141">[表示 **] を** 選択し、各フォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="b31c6-142">PowerShell を使用して追加のフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="b31c6-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="b31c6-143">[**スタート] メニューに「PowerShell」** と入力し、[管理者として実行 **Windows PowerShellを右\*\*\*\*クリックし、[管理者として実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="b31c6-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="b31c6-144">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="b31c6-145">保護するフォルダーを追加するまで、手順 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="b31c6-146">追加されたフォルダーは、Windows セキュリティ アプリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![上記のコマンドレットが入力された PowerShell ウィンドウのスクリーンショット](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="b31c6-148">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="b31c6-149">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="b31c6-150">MDM CSP を使用して追加のフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="b31c6-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="b31c6-151">アプリが保護されたフォルダーに変更を加えるのを許可するには [、./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="b31c6-152">特定のアプリが管理フォルダーに変更を加えるのを許可する</span><span class="sxs-lookup"><span data-stu-id="b31c6-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="b31c6-153">特定のアプリが常に安全と見なされる場合を指定し、保護されたフォルダー内のファイルへの書き込みアクセス権を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="b31c6-154">アプリを許可すると、特定のアプリが、管理されたフォルダー アクセス機能によってブロックされている場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="b31c6-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b31c6-155">既定では、Windows は許可されたリストに対して使い分け可能と見なされるアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="b31c6-156">自動的に追加されるアプリは、Windows セキュリティ アプリに表示される一覧や、関連付けられた PowerShell コマンドレットを使用して記録されません。</span><span class="sxs-lookup"><span data-stu-id="b31c6-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="b31c6-157">ほとんどのアプリを追加する必要はない必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31c6-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="b31c6-158">アプリがブロックされている場合にのみアプリを追加し、信頼度を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="b31c6-159">アプリを追加する場合は、アプリの場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31c6-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="b31c6-160">その場所のアプリだけが、保護されたフォルダーへのアクセスを許可されます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="b31c6-161">(同じ名前の) アプリが別の場所にある場合、アプリは許可リストに追加されません。フォルダー アクセスの制御によってブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b31c6-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="b31c6-162">許可されているアプリケーションまたはサービスは、開始後にのみ、制御フォルダーへの書き込みアクセス権を持つ。</span><span class="sxs-lookup"><span data-stu-id="b31c6-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="b31c6-163">たとえば、更新サービスは、イベントが停止して再起動されるまで、イベントが許可された後も引き続きトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="b31c6-164">特定のアプリWindows Defenderを許可するには、セキュリティ アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="b31c6-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="b31c6-165">[セキュリティ] のスタート メニューを検索して、Windows セキュリティ アプリを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="b31c6-166">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護の管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="b31c6-167">[フォルダー アクセス **の制御] セクションで** 、[フォルダー アクセス **の制御によるアプリの許可] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="b31c6-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="b31c6-168">[ **許可されたアプリを追加する] を選択** し、プロンプトに従ってアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="許可されたアプリ ボタンを追加する":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="b31c6-170">グループ ポリシーを使用して特定のアプリを許可する</span><span class="sxs-lookup"><span data-stu-id="b31c6-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="b31c6-171">グループ ポリシー管理デバイスで、グループ ポリシー [管理](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="b31c6-172">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="b31c6-173">ツリーを Windows コンポーネント **の Microsoft** Defender Antivirus  >  **Windows Defender**  >  **に** 展開  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="b31c6-174">[許可されたアプリケーションの **構成] 設定をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="b31c6-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b31c6-175">[表示 **] を** 選択し、各アプリを入力します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="b31c6-176">PowerShell を使用して特定のアプリを許可する</span><span class="sxs-lookup"><span data-stu-id="b31c6-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="b31c6-177">[**スタート] メニューに「PowerShell」** と入力し、[管理者として実行 **Windows PowerShellを右\*\*\*\*クリックし、[管理者として実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="b31c6-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="b31c6-178">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="b31c6-179">たとえば *、C:\apps* フォルダーtest.exe実行可能ファイルを追加するには、コマンドレットは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b31c6-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="b31c6-180">引き続き使用 `Add-MpPreference -ControlledFolderAccessAllowedApplications` して、リストにアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="b31c6-181">このコマンドレットを使用して追加されたアプリは、Windows セキュリティ アプリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="アプリを許可する PowerShell コマンドレット":::

> [!IMPORTANT]
> <span data-ttu-id="b31c6-183">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="b31c6-184">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="b31c6-185">MDM CSP を使用して特定のアプリを許可する</span><span class="sxs-lookup"><span data-stu-id="b31c6-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="b31c6-186">アプリが保護されたフォルダーを変更するには [、./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c6-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="b31c6-187">署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="b31c6-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="b31c6-188">Microsoft Defender for Endpoint 証明書とファイル インジケーターを使用すると、署名された実行可能ファイルが保護されたフォルダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b31c6-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="b31c6-189">実装の詳細については、「証明書に [基づいてインジケーターを作成する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)。</span><span class="sxs-lookup"><span data-stu-id="b31c6-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="b31c6-190">これは、Powershell を含むスクリプト エンジンには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b31c6-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="b31c6-191">通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b31c6-191">Customize the notification</span></span>

<span data-ttu-id="b31c6-192">ルールがトリガーされ、アプリまたはファイルをブロックするときに通知をカスタマイズする方法の詳細については、「Configure alert [notification in Microsoft Defender for Endpoint」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)。</span><span class="sxs-lookup"><span data-stu-id="b31c6-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="b31c6-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="b31c6-193">See also</span></span>

- [<span data-ttu-id="b31c6-194">フォルダー アクセスを制御して重要なフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="b31c6-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="b31c6-195">フォルダー アクセスの制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="b31c6-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="b31c6-196">攻撃表面の縮小ルールを評価する</span><span class="sxs-lookup"><span data-stu-id="b31c6-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
