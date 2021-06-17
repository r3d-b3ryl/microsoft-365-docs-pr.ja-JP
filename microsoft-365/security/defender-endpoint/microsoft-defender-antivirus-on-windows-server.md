---
title: Windows Server 上の Microsoft Defender ウイルス対策
description: Windows Server 2016 および Windows Server 2019 上のMicrosoft Defender ウイルス対策を有効にして構成する方法について説明します。
keywords: Windows Defender、サーバー、scep、System Center Endpoint 保護、Server 2016、Current Branch、Server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/13/2021
ms.openlocfilehash: 1a1083d15698eb5bbdf2f6080b152b6f326c689a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539277"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="24570-104">Windows Server 上の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="24570-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24570-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="24570-105">**Applies to:**</span></span>

- [<span data-ttu-id="24570-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="24570-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="24570-107">Microsoft Defender ウイルス対策は、次のエディション/バージョンの Windows Server で利用できます。</span><span class="sxs-lookup"><span data-stu-id="24570-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="24570-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="24570-108">Windows Server 2019</span></span>
- <span data-ttu-id="24570-109">Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="24570-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="24570-110">Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="24570-110">Windows Server 2016.</span></span> 

<span data-ttu-id="24570-111">場合によっては、Microsoft Defender ウイルス対策は *Endpoint Protection* と呼ばることもありますが、保護エンジンは同じです。</span><span class="sxs-lookup"><span data-stu-id="24570-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="24570-112">機能、構成、および管理は、[Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md) とほとんど同じですが、Windows Server には一部の重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="24570-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="24570-113">Windows Server では、[自動除外](configure-server-exclusions-microsoft-defender-antivirus.md) が定義によるサーバー ロールに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="24570-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="24570-114">Windows Server では、Microsoft 以外のウイルス対策/マルウェア対策ソリューションを実行している場合、Microsoft Defender ウイルス対策はパッシブ モードまたは無効モードに自動的に移行しません。</span><span class="sxs-lookup"><span data-stu-id="24570-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="24570-115">ただし、Microsoft Defender ウイルス対策を手動でパッシブ モードまたは無効モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="24570-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="24570-116">Windows Server 上の Microsoft Defender ウイルス対策の設定</span><span class="sxs-lookup"><span data-stu-id="24570-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="24570-117">サーバー プラットフォームで Microsoft Defender ウイルス対策を設定して実行するプロセスには、いくつかの手順があります:</span><span class="sxs-lookup"><span data-stu-id="24570-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="24570-118">[インターフェイスを有効にします](#enable-the-user-interface-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="24570-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="24570-119">[Microsoft Defender ウイルス対策をインストールします](#install-microsoft-defender-antivirus-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="24570-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="24570-120">[実行中の Microsoft Defender を確認します](#verify-microsoft-defender-antivirus-is-running)。</span><span class="sxs-lookup"><span data-stu-id="24570-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="24570-121">[マルウェア対策セキュリティ インテリジェンスを更新します](#update-antimalware-security-intelligence)。</span><span class="sxs-lookup"><span data-stu-id="24570-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="24570-122">(必要に応じて) [サンプルを送信します](#submit-samples)。</span><span class="sxs-lookup"><span data-stu-id="24570-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="24570-123">(必要に応じて) [自動除外を構成します](#configure-automatic-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="24570-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="24570-124">(必要な場合のみ) [Microsoft Defender ウイルス対策 をパッシブ モードに設定します](#need-to-set-microsoft-defender-antivirus-to-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="24570-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="24570-125">Windows Server でユーザー インターフェイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="24570-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="24570-126">既定では、Microsoft Defender ウイルス対策が Windows Server にインストールされており機能することになっています。</span><span class="sxs-lookup"><span data-stu-id="24570-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="24570-127">場合によっては、ユーザー インターフェイス (GUI) が既定でインストールされていることがありますが、GUI は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="24570-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="24570-128">PowerShell、グループ ポリシー、またはその他のメソッドを使用して、Microsoft Defender ウイルス対策を管理できます。</span><span class="sxs-lookup"><span data-stu-id="24570-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="24570-129">GUI がサーバーにインストールされておらず、インストールを希望する場合は、 **役割と機能の追加ウィザード** または PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24570-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="24570-130">役割と機能の追加ウィザードを使用して GUI を有効にする</span><span class="sxs-lookup"><span data-stu-id="24570-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="24570-131">[役割と機能の追加ウィザードを使用して役割、役割サービス、および機能をインストールする](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard) を参照してから、**役割と機能の追加ウィザード** を使用します。</span><span class="sxs-lookup"><span data-stu-id="24570-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="24570-132">ウィザードの **機能** ステップにアクセスし、**Windows Defender 機能** で **Windows Defender 用 GUI** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24570-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="24570-133">Windows Server 2016 では、**役割と機能の追加ウィザード** は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="24570-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![役割と機能の追加ウィザードで Windows Defender 用 GUI オプションが表示されています](images/server-add-gui.png)

   <span data-ttu-id="24570-135">Windows Server 2019 でも、**役割と機能の追加ウィザード** は同じようになります。</span><span class="sxs-lookup"><span data-stu-id="24570-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="24570-136">PowerShell を使用して GUI を有効にする</span><span class="sxs-lookup"><span data-stu-id="24570-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="24570-137">次の PowerShell コマンドレットを使用すると、インターフェイスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="24570-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="24570-138">Windows Server 上の Microsoft Defender ウイルス対策をインストールする</span><span class="sxs-lookup"><span data-stu-id="24570-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="24570-139">Windows Server に Microsoft Defender ウイルス対策をインストールまたは再インストールする必要がある場合は、**役割と機能の追加ウィザード** または PowerShell を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="24570-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="24570-140">役割と機能の追加ウィザードを使用して Microsoft Defender ウイルス対策をインストールする</span><span class="sxs-lookup"><span data-stu-id="24570-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="24570-141">[この記事](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)を参照してから、**役割と機能の追加ウィザード** を使用します。</span><span class="sxs-lookup"><span data-stu-id="24570-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="24570-142">ウィザードの **機能** ステップにアクセスし、Microsoft Defender ウイルス対策オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24570-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="24570-143">**Windows Defender 用 GUI** オプションも選択します。</span><span class="sxs-lookup"><span data-stu-id="24570-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="24570-144">PowerShell を使用して Microsoft Defender ウイルス対策をインストールする</span><span class="sxs-lookup"><span data-stu-id="24570-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="24570-145">PowerShell を使用して Microsoft Defender ウイルス対策をインストールするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="24570-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="24570-146">Microsoft Defender ウイルス対策に含まれるマルウェア対策エンジンのイベント メッセージも、[Microsoft Defender ウイルス対策イベント](troubleshoot-microsoft-defender-antivirus.md) で検出されることがあります。</span><span class="sxs-lookup"><span data-stu-id="24570-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="24570-147">実行中の Microsoft Defender を確認する</span><span class="sxs-lookup"><span data-stu-id="24570-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="24570-148">Microsoft Defender ウイルス対策をインストールしたら、次のステップで実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24570-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="24570-149">Windows Server エンドポイントで、次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="24570-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="24570-150">ファイアウォール保護が有効になっていることを確認するには、次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="24570-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="24570-151">PowerShell の代わりに、コマンド プロンプトを使用して、Microsoft Defender ウイルス対策が実行できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="24570-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="24570-152">これを行うには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24570-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="24570-153">`sc query` コマンドは、Microsoft Defender ウイルス対策 サービスに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="24570-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="24570-154">Microsoft Defender ウイルス対策を実行中は、`STATE` の値に `RUNNING`が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24570-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="24570-155">マルウェア対策セキュリティ インテリジェンスを更新する</span><span class="sxs-lookup"><span data-stu-id="24570-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="24570-156">更新されたマルウェア対策セキュリティ インテリジェンスを取得するには、Windows Update サービスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24570-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="24570-157">Windows Server Update Services (WSUS) などの更新管理サービスを使用する場合は、Microsoft Defender ウイルス対策 セキュリティ インテリジェンスへの更新プログラムが管理するコンピューターに対して承認されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24570-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="24570-158">既定では Windows Update で Windows Server 2019 または Windows Server 2016 への更新プログラムを自動的にダウンロードしてインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="24570-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="24570-159">この構成を変更するには、以下のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="24570-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="24570-160">メソッド</span><span class="sxs-lookup"><span data-stu-id="24570-160">Method</span></span>  |<span data-ttu-id="24570-161">説明</span><span class="sxs-lookup"><span data-stu-id="24570-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="24570-162">コントロール パネルにある **Windows Update**</span><span class="sxs-lookup"><span data-stu-id="24570-162">**Windows Update** in Control Panel</span></span>     | <span data-ttu-id="24570-163">**更新プログラムを自動的にインストールする** と、Windows Defender セキュリティ インテリジェンス更新プログラムを含むすべての更新プログラムが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="24570-163">**Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <p><span data-ttu-id="24570-164">**更新プログラムをダウンロードし、自分でインストールを決定する** に設定すると、Windows Defender でセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできますが、他の更新プログラムが自動的にインストールされることはありません。</span><span class="sxs-lookup"><span data-stu-id="24570-164">**Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="24570-165">**グループ ポリシー**</span><span class="sxs-lookup"><span data-stu-id="24570-165">**Group Policy**</span></span>     | <span data-ttu-id="24570-166">次のパスでグループ ポリシー内で使用できる設定を利用して、Windows Updateを設定、管理できます: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span><span class="sxs-lookup"><span data-stu-id="24570-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="24570-167">**AUOptions** レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="24570-167">The **AUOptions** registry key</span></span>     | <span data-ttu-id="24570-168">次の 2 つの値を使用すると、Windows Update でセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="24570-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <p><span data-ttu-id="24570-169">**4** - **更新プログラムを自動的にインストールします**。</span><span class="sxs-lookup"><span data-stu-id="24570-169">**4** - **Install updates automatically**.</span></span> <span data-ttu-id="24570-170">この値を使用すると、Windows Defender セキュリティ インテリジェンス更新プログラムを含むすべての更新プログラムを自動的にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="24570-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <p><span data-ttu-id="24570-171">**3** - **更新プログラムをダウンロードし、自分でインストールを決定します**。</span><span class="sxs-lookup"><span data-stu-id="24570-171">**3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="24570-172">この値を使用すると Windows Defender でセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできますが、他の更新プログラムが自動的にインストールされることはありません。</span><span class="sxs-lookup"><span data-stu-id="24570-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="24570-173">マルウェアからの保護を維持できるようにするには、次のサービスを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24570-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="24570-174">Windows エラー報告サービス</span><span class="sxs-lookup"><span data-stu-id="24570-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="24570-175">Windows Update サービス</span><span class="sxs-lookup"><span data-stu-id="24570-175">Windows Update service</span></span>

<span data-ttu-id="24570-176">次の表は、Microsoft Defender ウイルス対策のサービスと依存サービスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="24570-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="24570-177">サービス名</span><span class="sxs-lookup"><span data-stu-id="24570-177">Service Name</span></span>|<span data-ttu-id="24570-178">[ファイルの場所]</span><span class="sxs-lookup"><span data-stu-id="24570-178">File Location</span></span>|<span data-ttu-id="24570-179">説明</span><span class="sxs-lookup"><span data-stu-id="24570-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="24570-180">Windows Defender サービス (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="24570-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="24570-181">これは、常に実行する必要がある主な Microsoft Defender ウイルス対策 サービスです。</span><span class="sxs-lookup"><span data-stu-id="24570-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="24570-182">Windows エラー報告サービス (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="24570-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="24570-183">このサービスは、エラー レポートを Microsoft に返送します。</span><span class="sxs-lookup"><span data-stu-id="24570-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="24570-184">Windows Defender ファイアウォール (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="24570-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="24570-185">Windows Defender ファイアウォール サービスは有効のままにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24570-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="24570-186">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="24570-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="24570-187">セキュリティ インテリジェンスの更新プログラムとマルウェア対策エンジンの更新プログラムを取得するには、Windows Update が必要です</span><span class="sxs-lookup"><span data-stu-id="24570-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="24570-188">サンプルを送信する</span><span class="sxs-lookup"><span data-stu-id="24570-188">Submit samples</span></span>

<span data-ttu-id="24570-189">サンプルの送信で、Microsoft が悪意のある可能性のあるソフトウェアのサンプルを収集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="24570-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="24570-190">継続的かつ最新の保護を提供できるように、Microsoft 専門家がこれらのサンプルを使用して疑わしいアクティビティを分析し、マルウェア対策セキュリティ インテリジェンスの更新プログラムを生成しています。</span><span class="sxs-lookup"><span data-stu-id="24570-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="24570-191">Microsoft では.exe ファイルや .dll ファイルなどのプログラム実行可能ファイルを収集しています。</span><span class="sxs-lookup"><span data-stu-id="24570-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="24570-192">Microsoft Word ドキュメントや PDF ファイルなど、個人データを含むファイルは収集していません。</span><span class="sxs-lookup"><span data-stu-id="24570-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="24570-193">ファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="24570-193">Submit a file</span></span>

1. <span data-ttu-id="24570-194">[送信ガイド](/windows/security/threat-protection/intelligence/submission-guide) を確認します。</span><span class="sxs-lookup"><span data-stu-id="24570-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="24570-195">[サンプル送信ポータル](https://www.microsoft.com/wdsi/filesubmission)にアクセスし、ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="24570-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="24570-196">サンプルの自動送信を有効にする</span><span class="sxs-lookup"><span data-stu-id="24570-196">Enable automatic sample submission</span></span>

<span data-ttu-id="24570-197">サンプルの自動送信を有効にするには、管理者として Windows PowerShell コンソールを起動し、次のいずれかの設定に従って **SubmitSamplesConsent** 値データを設定します。</span><span class="sxs-lookup"><span data-stu-id="24570-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="24570-198">Setting</span><span class="sxs-lookup"><span data-stu-id="24570-198">Setting</span></span>  |<span data-ttu-id="24570-199">説明</span><span class="sxs-lookup"><span data-stu-id="24570-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="24570-200">**0** - **常にプロンプトを表示する**</span><span class="sxs-lookup"><span data-stu-id="24570-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="24570-201">Microsoft Defender ウイルス対策 サービスで、必要なすべてのファイルの送信を確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24570-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="24570-202">これは Microsoft Defender ウイルス対策の既定の設定ですが、GUI を使用せずに Windows Server 2016 または Windows Server 2019 にインストールすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="24570-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="24570-203">**1**  - **安全なサンプルを自動的に送信する**</span><span class="sxs-lookup"><span data-stu-id="24570-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="24570-204">Microsoft Defender ウイルス対策 サービスで "安全" とマークされたすべてのファイルが送信され、その他のファイルにはプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24570-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="24570-205">**2** - **送信しない**</span><span class="sxs-lookup"><span data-stu-id="24570-205">**2** - **Never send**</span></span>      |<span data-ttu-id="24570-206">Microsoft Defender ウイルス対策 サービスではプロンプトが表示されず、すべてのファイルが送信されません。</span><span class="sxs-lookup"><span data-stu-id="24570-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="24570-207">**3** - **すべてのサンプルを自動的に送信する**</span><span class="sxs-lookup"><span data-stu-id="24570-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="24570-208">Microsoft Defender ウイルス対策 サービスでは確認を行うプロンプトが表示されず、すべてのファイルが送信されます。</span><span class="sxs-lookup"><span data-stu-id="24570-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="24570-209">自動除外を構成する</span><span class="sxs-lookup"><span data-stu-id="24570-209">Configure automatic exclusions</span></span>

<span data-ttu-id="24570-210">セキュリティとパフォーマンスを確保できるように、Windows Server 2016 または Windows Server 2019 での Microsoft Defender ウイルス対策使用時に、インストールする役割と機能に基づいて特定の除外が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="24570-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="24570-211">詳細については、「[Windows Server 上の Microsoft Defender ウイルス対策で除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24570-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="24570-212">Microsoft Defender ウイルス対策 をパッシブ モードに設定する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="24570-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="24570-213">Windows Server 上のプライマリ ウイルス対策ソリューションとして Microsoft 以外のウイルス対策製品を使用している場合は、Microsoft Defender ウイルス対策をパッシブ モードまたは無効モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24570-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="24570-214">バージョン 1803 以降の Windows Server、または Windows Server 2019 では、Microsoft Defender ウイルス対策をパッシブ モードに設定してください。</span><span class="sxs-lookup"><span data-stu-id="24570-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="24570-215">Windows Server 2016 では、Microsoft Defender ウイルス対策は Microsoft 以外のウイルス対策/マルウェア対策製品と一緒にサポートできません。</span><span class="sxs-lookup"><span data-stu-id="24570-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="24570-216">このような場合は、Microsoft Defender ウイルス対策を無効モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24570-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="24570-217">レジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定する</span><span class="sxs-lookup"><span data-stu-id="24570-217">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="24570-218">バージョン 1803 の Windows Server、または Windows Server 2019 では、次のレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="24570-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="24570-219">パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="24570-219">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="24570-220">名前: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="24570-220">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="24570-221">種類: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="24570-221">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="24570-222">値: `1`</span><span class="sxs-lookup"><span data-stu-id="24570-222">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="24570-223">役割と機能の削除ウィザードを使用して Microsoft Defender ウイルス対策を無効にする</span><span class="sxs-lookup"><span data-stu-id="24570-223">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="24570-224">「[役割のインストールまたはアンインストール、役割サービス、または機能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)」 を参照してから、**役割と機能の削除ウィザード** を使用します。</span><span class="sxs-lookup"><span data-stu-id="24570-224">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="24570-225">ウィザードの **機能** ステップにアクセスし、**Windows Defender 機能** オプションを解除します。</span><span class="sxs-lookup"><span data-stu-id="24570-225">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="24570-226">**Windows Defender** を単独で **Windows Defender 機能** セクションで解除すると、インターフェイス オプションの **Windows Defender 用 GUI** を削除するように求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24570-226">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="24570-227">Microsoft Defender ウイルス対策はユーザー インターフェイスなしで正常に実行することはできますが、主な **Windows Defender** 機能を無効にしていると、ユーザー インターフェイスを有効にすることができません。</span><span class="sxs-lookup"><span data-stu-id="24570-227">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="24570-228">PowerShell を使用して Microsoft Defender ウイルス対策ユーザー インターフェイスをオフにする</span><span class="sxs-lookup"><span data-stu-id="24570-228">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="24570-229">Microsoft Defender ウイルス対策 GUI をオフにするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24570-229">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="24570-230">Windows Server 2016 を使用していますか?</span><span class="sxs-lookup"><span data-stu-id="24570-230">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="24570-231">Windows Server 2016 と一緒に Microsoft が提供または開発を行っていないサード パーティのマルウェア対策/ウイルス対策製品を使用している場合は、Microsoft Defender ウイルス対策を無効またはアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="24570-231">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="24570-232">Windows セキュリティ アプリをアンインストールすることはできませんが、次の手順でインターフェイスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="24570-232">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="24570-233">次の PowerShell コマンドレットで、Windows Server 2016 上の Microsoft Defender ウイルス対策をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="24570-233">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="24570-234">Windows Server 2016 で Microsoft Defender ウイルス対策を無効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24570-234">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="24570-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="24570-235">See also</span></span>

- [<span data-ttu-id="24570-236">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="24570-236">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="24570-237">Microsoft Defender ウイルス対策互換性</span><span class="sxs-lookup"><span data-stu-id="24570-237">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
