---
title: Windows Server 上の Microsoft Defender ウイルス対策
description: Windows Server 2016 および Windows Server 2019 で Microsoft Defender ウイルス対策を有効にして構成する方法について説明します。
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
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
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269494"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="91e3f-104">Windows Server 上の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="91e3f-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91e3f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="91e3f-105">**Applies to:**</span></span>

- [<span data-ttu-id="91e3f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="91e3f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="91e3f-107">Microsoft Defender ウイルス対策は、Windows Server の次のエディション/バージョンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="91e3f-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="91e3f-108">Windows Server 2019</span></span>
- <span data-ttu-id="91e3f-109">Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="91e3f-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="91e3f-110">Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="91e3f-110">Windows Server 2016.</span></span> 

<span data-ttu-id="91e3f-111">場合によっては、Microsoft Defender ウイルス対策はエンドポイント保護と *呼ばれます*。ただし、保護エンジンは同じです。</span><span class="sxs-lookup"><span data-stu-id="91e3f-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="91e3f-112">[Windows 10](microsoft-defender-antivirus-in-windows-10.md)の Microsoft Defender ウイルス対策の機能、構成、および管理は大きく同じですが、Windows Server にはいくつかの主な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="91e3f-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="91e3f-113">Windows Server では、 [定義済みのサーバーロール](configure-server-exclusions-microsoft-defender-antivirus.md) に基づいて自動除外が適用されます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="91e3f-114">Windows Server では、Microsoft 以外のウイルス対策/マルウェア対策ソリューションを実行している場合、Microsoft Defender Antivirus はパッシブ モードまたは無効モードに自動的には入りません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="91e3f-115">ただし、手動で Microsoft Defender ウイルス対策をパッシブ モードまたは無効モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="91e3f-116">Windows Server での Microsoft Defender ウイルス対策のセットアップ</span><span class="sxs-lookup"><span data-stu-id="91e3f-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="91e3f-117">サーバー プラットフォームで Microsoft Defender Antivirus をセットアップして実行するプロセスには、次のいくつかの手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="91e3f-118">[インターフェイスを有効にします](#enable-the-user-interface-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="91e3f-119">[Microsoft Defender ウイルス対策をインストールします](#install-microsoft-defender-antivirus-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="91e3f-120">[Microsoft Defender ウイルス対策が実行されているを確認します](#verify-microsoft-defender-antivirus-is-running)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="91e3f-121">[マルウェア対策のセキュリティ インテリジェンスを更新します](#update-antimalware-security-intelligence)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="91e3f-122">(必要に応じて) [サンプルを送信します](#submit-samples)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="91e3f-123">(必要に応じて) [自動除外を構成します](#configure-automatic-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="91e3f-124">(必要な場合のみ) [Microsoft Defender ウイルス対策をパッシブ モードに設定します](#need-to-set-microsoft-defender-antivirus-to-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="91e3f-125">Windows Server でユーザー インターフェイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="91e3f-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="91e3f-126">既定では、Microsoft Defender ウイルス対策が Windows Server にインストールされ、機能します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="91e3f-127">場合によっては、ユーザー インターフェイス (GUI) が既定でインストールされますが、GUI は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="91e3f-128">PowerShell、グループ ポリシー、または他の方法を使用して Microsoft Defender ウイルス対策を管理できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="91e3f-129">GUI がサーバーにインストールされていない場合にインストールする場合は、役割と機能の追加ウィザードまたは PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="91e3f-130">次のコマンドを使用して GUI を有効役割と機能の追加ウィザード</span><span class="sxs-lookup"><span data-stu-id="91e3f-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="91e3f-131">「[役割と機能の追加ウィザードを](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)使用して役割、役割サービス、および機能をインストールする」を参照し、次の **役割と機能の追加ウィザード。**</span><span class="sxs-lookup"><span data-stu-id="91e3f-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="91e3f-132">ウィザードの [機能]**ステップに** 進み、[機能] の下の [Windows Defender] の **[GUI] オプションをWindows Defender** します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="91e3f-133">Windows Server 2016 では **、役割と機能の追加ウィザード次** のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![[ユーザーの GUI を表示する役割と機能ウィザードWindows Defenderする](images/server-add-gui.png)

   <span data-ttu-id="91e3f-135">Windows Server 2019 では、役割 **と機能の追加ウィザードは** 似ています。</span><span class="sxs-lookup"><span data-stu-id="91e3f-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="91e3f-136">PowerShell を使用して GUI を有効にする</span><span class="sxs-lookup"><span data-stu-id="91e3f-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="91e3f-137">次の PowerShell コマンドレットを使用すると、インターフェイスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="91e3f-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="91e3f-138">Windows Server に Microsoft Defender ウイルス対策をインストールする</span><span class="sxs-lookup"><span data-stu-id="91e3f-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="91e3f-139">Windows Server に Microsoft Defender ウイルス対策をインストールまたは再インストールする必要がある場合は、Windows サーバーまたは PowerShell を使用 **役割と機能の追加ウィザードできます。**</span><span class="sxs-lookup"><span data-stu-id="91e3f-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="91e3f-140">Microsoft Defender ウイルス役割と機能の追加ウィザードをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="91e3f-141">この記事 [を参照し](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)、次の **役割と機能の追加ウィザード。**</span><span class="sxs-lookup"><span data-stu-id="91e3f-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="91e3f-142">ウィザードの [機能] **ステップに** アクセスしたら、[Microsoft Defender ウイルス対策] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="91e3f-143">また、ユーザー設定 **オプションの GUI Windows Defender** します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="91e3f-144">PowerShell を使用して Microsoft Defender ウイルス対策をインストールする</span><span class="sxs-lookup"><span data-stu-id="91e3f-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="91e3f-145">PowerShell を使用して Microsoft Defender ウイルス対策をインストールするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="91e3f-146">Microsoft Defender ウイルス対策に含まれるマルウェア対策エンジンのイベント メッセージは [、Microsoft Defender AV イベントで確認できます](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="91e3f-147">Microsoft Defender ウイルス対策が実行されているを確認する</span><span class="sxs-lookup"><span data-stu-id="91e3f-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="91e3f-148">Microsoft Defender Antivirus がインストールされた後、次に実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="91e3f-149">Windows Server エンドポイントで、次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="91e3f-150">ファイアウォール保護が有効になっていることを確認するには、次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="91e3f-151">PowerShell の代わりに、コマンド プロンプトを使用して、Microsoft Defender ウイルス対策が実行されているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="91e3f-152">これを行うには、コマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="91e3f-153">この `sc query` コマンドは、Microsoft Defender ウイルス対策サービスに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="91e3f-154">Microsoft Defender ウイルス対策が実行されている場合、値 `STATE` が表示されます `RUNNING` 。</span><span class="sxs-lookup"><span data-stu-id="91e3f-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="91e3f-155">マルウェア対策セキュリティ インテリジェンスの更新</span><span class="sxs-lookup"><span data-stu-id="91e3f-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="91e3f-156">更新されたマルウェア対策セキュリティ インテリジェンスを取得するには、Windows Update サービスを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e3f-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="91e3f-157">Windows Server Update Services (WSUS) などの更新プログラム管理サービスを使用する場合は、管理するコンピューターに対して Microsoft Defender ウイルス対策セキュリティ インテリジェンスの更新プログラムが承認されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e3f-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="91e3f-158">既定では、Windows Update は Windows Server 2019 または Windows Server 2016 で更新プログラムを自動的にダウンロードおよびインストールしません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="91e3f-159">この構成は、次のいずれかの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="91e3f-160">メソッド</span><span class="sxs-lookup"><span data-stu-id="91e3f-160">Method</span></span>  |<span data-ttu-id="91e3f-161">説明</span><span class="sxs-lookup"><span data-stu-id="91e3f-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="91e3f-162">**コントロール パネルの Windows** Update</span><span class="sxs-lookup"><span data-stu-id="91e3f-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="91e3f-163">- **更新プログラムをインストールすると** 、セキュリティ インテリジェンスの更新プログラムを含むすべての更新Windows Defender自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="91e3f-164">- **更新プログラムをダウンロードします** が、セキュリティ インテリジェンス更新プログラムをWindows Defenderインストールできるかどうかを選択しますが、他の更新プログラムは自動的にインストールされません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="91e3f-165">**グループ ポリシー**</span><span class="sxs-lookup"><span data-stu-id="91e3f-165">**Group Policy**</span></span>     | <span data-ttu-id="91e3f-166">グループ ポリシーで使用できる設定を使用して、管理用テンプレート **\Windows コンポーネント\Windows Update\Configure 自動更新** を使用して、Windows Update を設定および管理できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="91e3f-167">**AUOptions** レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="91e3f-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="91e3f-168">次の 2 つの値を使用すると、Windows Update はセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="91e3f-169">- **4**  - **更新プログラムを自動的にインストールします**。</span><span class="sxs-lookup"><span data-stu-id="91e3f-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="91e3f-170">この値を指定すると、セキュリティ インテリジェンス更新プログラムを含むすべての更新Windows Defender自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="91e3f-171">- **3**  - **更新プログラムをダウンロードしますが、インストールするかどうかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="91e3f-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="91e3f-172">この値を使用Windows Defenderセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできますが、他の更新プログラムは自動的にインストールされません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="91e3f-173">マルウェアからの保護を確実に維持するには、次のサービスを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91e3f-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="91e3f-174">Windows エラー報告サービス</span><span class="sxs-lookup"><span data-stu-id="91e3f-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="91e3f-175">Windows Update サービス</span><span class="sxs-lookup"><span data-stu-id="91e3f-175">Windows Update service</span></span>

<span data-ttu-id="91e3f-176">次の表に、Microsoft Defender ウイルス対策サービスと依存サービスの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="91e3f-177">サービス名</span><span class="sxs-lookup"><span data-stu-id="91e3f-177">Service Name</span></span>|<span data-ttu-id="91e3f-178">ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="91e3f-178">File Location</span></span>|<span data-ttu-id="91e3f-179">説明</span><span class="sxs-lookup"><span data-stu-id="91e3f-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="91e3f-180">Windows Defender サービス (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="91e3f-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="91e3f-181">これは、すべての回で実行する必要がある主な Microsoft Defender ウイルス対策サービスです。</span><span class="sxs-lookup"><span data-stu-id="91e3f-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="91e3f-182">Windows エラー報告サービス (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="91e3f-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="91e3f-183">このサービスは、エラー レポートを Microsoft に返します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="91e3f-184">Windows Defender ファイアウォール (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="91e3f-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="91e3f-185">ファイアウォール サービスを有効にWindows Defenderすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91e3f-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="91e3f-186">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="91e3f-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="91e3f-187">Windows Update は、セキュリティ インテリジェンスの更新プログラムとマルウェア対策エンジンの更新プログラムを取得するために必要です。</span><span class="sxs-lookup"><span data-stu-id="91e3f-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="91e3f-188">サンプルの送信</span><span class="sxs-lookup"><span data-stu-id="91e3f-188">Submit samples</span></span>

<span data-ttu-id="91e3f-189">サンプル提出により、Microsoft は悪意のある可能性のあるソフトウェアのサンプルを収集できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="91e3f-190">Microsoft の研究者は、継続的で最新の保護を提供するために、これらのサンプルを使用して疑わしいアクティビティを分析し、更新されたマルウェア対策セキュリティ インテリジェンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="91e3f-191">プログラムの実行可能ファイル (ファイルやファイル.exeなど) を.dllします。</span><span class="sxs-lookup"><span data-stu-id="91e3f-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="91e3f-192">Microsoft Word ドキュメントや PDF ファイルなど、個人データを含むファイルは収集できません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="91e3f-193">ファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="91e3f-193">Submit a file</span></span>

1. <span data-ttu-id="91e3f-194">申請ガイド [を確認します](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="91e3f-195">サンプル提出 [ポータルにアクセスし](https://www.microsoft.com/wdsi/filesubmission)、ファイルを提出します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="91e3f-196">自動サンプル申請を有効にする</span><span class="sxs-lookup"><span data-stu-id="91e3f-196">Enable automatic sample submission</span></span>

<span data-ttu-id="91e3f-197">自動サンプル申請を有効にするには、管理者として Windows PowerShell コンソールを起動し、次のいずれかの設定に従って **SubmitSamplesConsent** 値データを設定します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="91e3f-198">Setting</span><span class="sxs-lookup"><span data-stu-id="91e3f-198">Setting</span></span>  |<span data-ttu-id="91e3f-199">説明</span><span class="sxs-lookup"><span data-stu-id="91e3f-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="91e3f-200">**0**  - **常にプロンプトを表示する**</span><span class="sxs-lookup"><span data-stu-id="91e3f-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="91e3f-201">Microsoft Defender ウイルス対策サービスでは、必要なすべてのファイルの提出を確認するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="91e3f-202">これは Microsoft Defender ウイルス対策の既定の設定ですが、WINDOWS Server 2016 または 2019 のインストールでは GUI を使用しない場合は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="91e3f-203">**1**   - **安全なサンプルを自動的に送信する**</span><span class="sxs-lookup"><span data-stu-id="91e3f-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="91e3f-204">Microsoft Defender ウイルス対策サービスは、"安全" とマークされているすべてのファイルを送信し、残りのファイルを求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="91e3f-205">**2**  - **送信しない**</span><span class="sxs-lookup"><span data-stu-id="91e3f-205">**2** - **Never send**</span></span>      |<span data-ttu-id="91e3f-206">Microsoft Defender ウイルス対策サービスはプロンプトを表示しないし、ファイルも送信しない。</span><span class="sxs-lookup"><span data-stu-id="91e3f-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="91e3f-207">**3**  - **すべてのサンプルを自動的に送信する**</span><span class="sxs-lookup"><span data-stu-id="91e3f-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="91e3f-208">Microsoft Defender ウイルス対策サービスは、確認を求めるメッセージを表示せずにすべてのファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="91e3f-209">自動除外を構成する</span><span class="sxs-lookup"><span data-stu-id="91e3f-209">Configure automatic exclusions</span></span>

<span data-ttu-id="91e3f-210">セキュリティとパフォーマンスを確保するために、Windows Server 2016 または 2019 で Microsoft Defender ウイルス対策を使用するときにインストールする役割と機能に基づいて、特定の除外が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="91e3f-211">「Windows [Server の Microsoft Defender ウイルス対策で除外を構成する」を参照してください](configure-server-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="91e3f-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="91e3f-212">Microsoft Defender ウイルス対策をパッシブ モードに設定する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="91e3f-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="91e3f-213">Windows Server で Microsoft 以外のウイルス対策製品をプライマリ ウイルス対策ソリューションとして使用している場合は、Microsoft Defender Antivirus をパッシブ モードまたは無効モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e3f-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="91e3f-214">Windows Server バージョン 1803 以降、または Windows Server 2019 では、Microsoft Defender ウイルス対策をパッシブ モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="91e3f-215">Windows Server 2016 では、Microsoft Defender ウイルス対策は、Microsoft 以外のウイルス対策/マルウェア対策製品と共にサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="91e3f-216">このような場合は、Microsoft Defender ウイルス対策を無効モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e3f-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="91e3f-217">PowerShell を使用して Microsoft Defender ウイルス対策をパッシブ モードに設定する</span><span class="sxs-lookup"><span data-stu-id="91e3f-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="91e3f-218">Windows Server、バージョン 1803、または Windows Server 2019 を使用している場合は、次の PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="91e3f-219">グループ ポリシーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定する</span><span class="sxs-lookup"><span data-stu-id="91e3f-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="91e3f-220">プロシージャが必要</span><span class="sxs-lookup"><span data-stu-id="91e3f-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="91e3f-221">レジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定する</span><span class="sxs-lookup"><span data-stu-id="91e3f-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="91e3f-222">Windows Server、バージョン 1803、または Windows Server 2019 を使用している場合は、次のレジストリ キーを設定して Microsoft Defender Antivirus をパッシブ モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="91e3f-223">パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="91e3f-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="91e3f-224">名前: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="91e3f-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="91e3f-225">タイプ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="91e3f-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="91e3f-226">値: `1`</span><span class="sxs-lookup"><span data-stu-id="91e3f-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="91e3f-227">役割と機能の削除ウィザードを使用して Microsoft Defender ウイルス対策を無効にする</span><span class="sxs-lookup"><span data-stu-id="91e3f-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="91e3f-228">「 [役割、役割サービス、または機能のインストール](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)またはアンインストール」を参照し、役割と機能の削除 **ウィザードを使用します**。</span><span class="sxs-lookup"><span data-stu-id="91e3f-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="91e3f-229">ウィザードの [機能] **ステップに** アクセスしたら、[機能] オプションのWindows Defender **解除** します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="91e3f-230">[Windows Defender機能] セクションでWindows Defenderをオフにすると、インターフェイス オプション **の GUI** を削除するように求めるメッセージが表示Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="91e3f-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="91e3f-231">Microsoft Defender ウイルス対策は、ユーザー インターフェイスなしでは正常に実行されますが、コア 機能を無効にすると、ユーザー **インターフェイスWindows Defender** できません。</span><span class="sxs-lookup"><span data-stu-id="91e3f-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="91e3f-232">PowerShell を使用して Microsoft Defender ウイルス対策ユーザー インターフェイスをオフにする</span><span class="sxs-lookup"><span data-stu-id="91e3f-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="91e3f-233">Microsoft Defender ウイルス対策 GUI を無効にする場合は、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="91e3f-234">Windows Server 2016 を使用していますか?</span><span class="sxs-lookup"><span data-stu-id="91e3f-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="91e3f-235">Windows Server 2016 および Microsoft によって提供または開発されていないサードパーティのマルウェア対策/ウイルス対策製品を使用している場合は、Microsoft Defender Antivirus を無効またはアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e3f-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="91e3f-236">Windows セキュリティ アプリはアンインストールできますが、次の手順でインターフェイスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="91e3f-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="91e3f-237">次の PowerShell コマンドレットは、Windows Server 2016 で Microsoft Defender ウイルス対策をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="91e3f-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="91e3f-238">Windows Server 2016 で Microsoft Defender ウイルス対策を無効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="91e3f-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="91e3f-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="91e3f-239">See also</span></span>

- [<span data-ttu-id="91e3f-240">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="91e3f-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="91e3f-241">Microsoft Defender ウイルス対策の互換性</span><span class="sxs-lookup"><span data-stu-id="91e3f-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
