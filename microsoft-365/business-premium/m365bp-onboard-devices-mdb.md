---
title: 組織のデバイスをオンボードしてMicrosoft Defender for Business
description: 組織のデバイスをオンボードしてMicrosoft Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: e9810b453136025e094ef8a0e88bff526f2c5a51
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634781"
---
# <a name="onboard-managed-devices-to-microsoft-defender-for-business"></a>管理対象デバイスをオンボードしてMicrosoft Defender for Business

デバイスをオンボードMicrosoft Defender for Business保護 (ウイルス対策、マルウェア対策、クラウド配信の保護)、ファイアウォール保護、Web コンテンツ フィルターなどによってデバイスを保護します。 

デバイスをオンボードするには、いくつかのオプションから選択できます。

- [デバイスに既に登録Windowsデバイスの自動オンボーディングを使用Microsoft エンドポイント マネージャー](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager)

- [ローカル スクリプトを使用して、Windows macOS デバイスをオンボードする](#use-a-local-script-to-onboard-windows-and-macos-devices)

- [デバイスエンドポイント マネージャー](#use-microsoft-endpoint-manager-to-enroll-devices) (Windows macOS、iOS、Android) を登録し、そのデバイスに Defender for Business ポリシーを適用するには、このポリシーを使用します。

この記事には、次の内容も含まれています。

- [デバイスで検出テストを実行するWindowsする](#run-a-detection-test-on-a-windows-device)

- [デバイスを段階的にオンボードする方法](#onboard-devices-gradually)

- [デバイスが置き換えられた場合、](#offboard-a-device) または誰かが組織を離れる場合にデバイスをオフボードする方法

> [!IMPORTANT]
> 問題が発生し、オンボーディング プロセスが失敗した場合は、「トラブルシューティング[Microsoft Defender for Business参照してください](../security/defender-business/mdb-troubleshooting.yml)。

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager"></a>デバイスに既に登録Windowsデバイスの自動オンボーディングを使用Microsoft エンドポイント マネージャー

自動オンボーディング オプションは、デバイスWindows適用されます。 Defender for Business を使用する前に、組織が Microsoft Intune で Microsoft エンドポイント マネージャー、Microsoft Intune、またはモバイル デバイス管理 (MDM) を既に使用し、Windows デバイスが既に登録されている場合は、自動オンボーディングを使用できます。でエンドポイント マネージャー。 

Windowsデバイスが エンドポイント マネージャー に既に登録されている場合、Defender for Business は、Defender for Business のセットアップおよび構成中にそれらのデバイスを検出します。 すべてのデバイスまたは一部のデバイスに対して自動オンボーディングを使用Windowsされます。 すべてのデバイスを一度Windowsしたり、最初に特定のデバイスを選択したり、後でデバイスを追加したりできます。

自動オンボーディングの詳細については、「手順 2 in Use the wizard to set up the wizard」[を参照](../security/defender-business/mdb-use-wizard.md)Microsoft Defender for Business。

## <a name="use-a-local-script-to-onboard-windows-and-macos-devices"></a>ローカル スクリプトを使用して、Windows macOS デバイスをオンボードする

ローカル スクリプトを使用して、ローカル Windows macOS デバイスをオンボードできます。 デバイスでオンボード スクリプトを実行すると、Azure Active Directory との信頼が作成されます (その信頼が存在しない場合)、Microsoft エンドポイント マネージャー にデバイスを登録し (まだ登録されていない場合)、デバイスを Defender for Business にオンボードします。 

この方法では、一度に最大 10 台のデバイスをオンボードできます。

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

2. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

3. オペレーティング システム (Windows 10 および **11** など) を選択し、[デバイスのオンボード] の [展開方法] セクションで、[ローカル  スクリプト] を **選択します**。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボーディング パッケージをリムーバブル ドライブに保存することをお勧めします。

5. 次の記事のガイダンスに従います。

   - Windows: [ローカル スクリプトをWindowsデバイスをオンボードする](../security/defender-endpoint/configure-endpoints-script.md#onboard-windows-devices-using-a-local-script)

   - macOS デバイス: [macOS でのMicrosoft Defender for Endpointの手動展開](../security/defender-endpoint/mac-install-manually.md#download-installation-and-onboarding-packages)

## <a name="use-microsoft-endpoint-manager-to-enroll-devices"></a>デバイスMicrosoft エンドポイント マネージャー登録する

Defender for Business を使用する前に エンドポイント マネージャー (Microsoft Intune とモバイル デバイス管理 を含む) を既に使用していた場合は、引き続き エンドポイント マネージャー を使用して組織のデバイスをオンボードできます。 このエンドポイント マネージャー、iOS デバイスや Android デバイスを含むコンピューター、タブレット、電話をオンボードできます。

組織で Android デバイスを使用している場合は、このメソッドを使用します。

「[デバイスの登録」を参照Microsoft Intune](/mem/intune/enrollment/device-enrollment)。


## <a name="run-a-detection-test-on-a-windows-device"></a>デバイスで検出テストをWindowsする

Defender for Business に Windowsデバイスをオンボードした後、Windows デバイスで検出テストを実行して、すべてが正しく動作するようにすることができます。

1. デバイスでWindowsフォルダーを作成します。 `C:\test-MDATP-test`

2. 管理者としてコマンド プロンプトを開きます。

3. [コマンド プロンプト] ウィンドウで、次の PowerShell コマンドを実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスの新しいアラートが Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分で表示されます。

## <a name="onboard-devices-gradually"></a>オンボード デバイスの段階的な使用

段階的なデバイスオンボーディングと呼ばれる段階的なデバイスのオンボードを希望する場合は *、次の* 手順を実行します。 

1. オンボードするデバイスのセットを識別します。

2. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

3. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

4. オペレーティング システム (Windows 10 **11 など) を** 選択し、オンボーディング方法 (ローカル スクリプトなど) **を選択します**。 選択した方法のガイダンスに従います。

5. オンボードするデバイスのセットごとにこのプロセスを繰り返します。 

> [!TIP]
> デバイスをオンボードする度に同じオンボーディング パッケージを使用する必要はない。 たとえば、ローカル スクリプトを使用して一部のデバイスをオンボードし、後で別の方法を選択して、より多くのデバイスをオンボードできます。

## <a name="offboard-a-device"></a>デバイスのオフボード

デバイスをオフボードする場合は、次の手順を実行します。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[エンドポイント] を **設定** し、[エンドポイント] **を選択します**。

3. [ **デバイスの管理] で**、[ **オフボード] を選択します**。

4. オペレーティング システム (Windows 10 および **11** など) を選択し、[デバイスのオフボード] の [展開方法] セクションで、[ローカル  スクリプト] **を選択します**。 

5. 確認画面で情報を確認し、[ダウンロード] を選択 **して** 続行します。

6. [オフ **ボード パッケージのダウンロード] を選択します**。 オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。

7. オフボードする各デバイスでスクリプトを実行します。 このタスクに関するヘルプが必要ですか? 以下のリソースを参照してください。   

   - Windows: [ローカル スクリプトをWindowsオフボード デバイス](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   
   - macOS デバイス: [macOS でのアンインストール](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business へのデータの送信を停止します。 ただし、オフボード前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-steps"></a>次の手順

[[修復アクションの確認] Microsoft 365 Business Premium](m365bp-review-remediation-actions-devices.md)