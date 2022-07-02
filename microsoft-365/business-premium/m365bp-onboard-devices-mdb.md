---
title: 組織のデバイスを Microsoft Defender for Business にオンボードする
description: 組織のデバイスを Microsoft Defender for Business にオンボードする
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 70be4a5b7991d038dd1e34c00778de6bb3a67b84
ms.sourcegitcommit: 85799f0efc06037c1ff309fe8e609bbd491f9b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66573971"
---
# <a name="onboard-enrolled-devices-to-microsoft-defender-for-business"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

Microsoft 365 Business Premium には、中小企業向けのエンドポイント セキュリティ ソリューションである Microsoft Defender for Business が含まれます。 Defender for Business は、企業用のデバイスに対して、次世代の保護 (ウイルス対策、マルウェア対策、クラウド配信保護)、ファイアウォール保護、Web コンテンツ フィルタリングなどを提供します。 デバイスのオンボード時に保護が適用されます。 

デバイスをオンボードするには、いくつかのオプションから選択できます:

- [Microsoft Intune に登録されている Windows デバイスの自動オンボード](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune)
- [ローカル スクリプトで Windowsデバイスと macOS デバイスを Defender for Business にオンボードする](#use-a-local-script-to-onboard-windows-and-macos-devices-to-defender-for-business)
- [Intune をモバイル デバイス (Windows、macOS、iOS、Android) などのデバイスに登録](#use-intune-to-enroll-devices)し、それらのデバイスに Defender for Business ポリシーを適用する

この文書には、以下の内容が含まれます:

- [Windows デバイスで検出テストを実行する方法](#run-a-detection-test-on-a-windows-device)
- [デバイスを段階的にオンボードする方法](#onboard-devices-gradually)
- デバイスが交換された場合、または他のユーザーが組織を離れた場合に[デバイスをオフボードする方法](#offboard-a-device)

> [!IMPORTANT]
> 問題が発生し、オンボード プロセスが失敗した場合は、「[Microsoft Defender for Business トラブルシューティング](../security/defender-business/mdb-troubleshooting.yml)」を参照してください。

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune"></a>Intune に既に登録されている Windows デバイスの自動オンボードを使用する

これらのデバイスが既に Intune に登録されている場合は、Windows デバイスを Defender for Business に自動的にオンボードできます。 Defender for Business は、Intune に登録されている Windows クライアント デバイスを検出し、それらのデバイスを自動的にオンボードするかどうかを選択するように求められます。 その後、Defender for Business のセキュリティ ポリシーと設定がそれらのデバイスに適用されます。 このプロセスを *自動オンボード* と呼びます。 自動オンボード オプションは、Windows デバイスにのみ適用されることに注意してください。 自動オンボードは、次の条件が満たされている場合に使用できます:

- Defender for Business を取得する前に、組織は既に Intune で Microsoft エンドポイント マネージャー、Microsoft Intune、モバイル デバイス管理 (MDM) を使用していました ( Microsoft 365 Business Premium をお使いのお客様は既に Microsoft Intune をお持ちです)。
- Intune に Windowsデバイスが既に登録されています。

> [!TIP]
> 自動オンボードを使用するように求められたら、"すべてのデバイスが登録されました" オプションを選択することをお勧めします。 そうすれば、後で Windowsデバイスが Intune に登録されると、自動的に Defender for Business にオンボードされます。

自動オンボードの詳細については、「[ウィザードを使用して Microsoft Defender for Business を設定する](../security/defender-business/mdb-use-wizard.md)」を参照してください。

## <a name="use-a-local-script-to-onboard-windows-and-macos-devices-to-defender-for-business"></a>ローカル スクリプトを使用して Windowsデバイスと macOS デバイスを Defender for Business にオンボードする

ローカル スクリプトを使用して、Windowsデバイスと Mac デバイスをオンボードできます。 デバイスでオンボード スクリプトを実行すると、Azure Active Directory で信頼が作成され (信頼がまだ存在しない場合)、デバイスが Intune に登録され (まだ登録されていない場合)、デバイスが Defender for Business にオンボードされます。 一度に最大 10 台のローカル スクリプトを使用するデバイスをオンボードできます。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで [**設定**]  >  [**エンドポイント**] を選択し、[**デバイス管理**] で [**オンボード**] を選択します。

3. **Windows 10、11**、**macOS** などのオペレーティング システムを選択し、[**展開方法**] セクションで [**ローカル スクリプト**] を選択します。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボード パッケージをリムーバブル ドライブに保存することをお勧めします。 (**macOS** を選択した場合は、[**インストール パッケージのダウンロード**] も選択し、リムーバブル デバイスに保存します)。

5. 次のガイダンスを使用します:

   - Windows デバイス: [ローカル スクリプトを使用した Windows デバイスのオンボード](../security/defender-endpoint/configure-endpoints-script.md#onboard-windows-devices-using-a-local-script)
   - macOS デバイス: [macOS での Microsoft Defender for Endpoint の手動展開](../security/defender-endpoint/mac-install-manually.md#download-installation-and-onboarding-packages)

## <a name="use-intune-to-enroll-devices"></a>Intune を使用してデバイスを登録する

デバイスを登録するには、自分で登録するか、ユーザーにポータル サイトにサインインしてもらい、必要なアプリを登録してインストールしてもらいます。 

Intune とモバイル デバイス管理を既に使用していた場合は、Defender for Business を入手する前に、Intune を使用して組織のデバイスをオンボードし続けることができます。 Intune を使用すると、iOS や Android デバイスを含むコンピューター、タブレット、スマートフォンをオンボードできます。

「[Microsoft Intune のデバイス登録に関する説明](/mem/intune/enrollment/device-enrollment)」を参照してください。 

## <a name="run-a-detection-test-on-a-windows-device"></a>新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行する

Windowsデバイスを Defender for Business にオンボードしたら、Windows デバイスで検出テストを実行して、すべてが正しく動作していることを確認できます。

1. Windows デバイスで、フォルダーを作成します: `C:\test-MDATP-test`。

2. 管理者としてコマンド プロンプト ウィンドウを開きます。

3. コマンド プロンプト ウィンドウで、次の PowerShell コマンドを実行します:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、コマンド プロンプト ウィンドウが自動的に閉じます。成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスの Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分で新しいアラートが表示されます。

## <a name="onboard-devices-gradually"></a>デバイスを段階的にオンボードする

段階的にデバイスをオンボードする (*段階的なデバイス オンボード* といいます) 場合には、次の手順に従います: 

1. オンボードするデバイスのセットを特定します。

2. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

3. ナビゲーション ウィンドウで [**設定**]  >  [**エンドポイント**] を選択し、[**デバイス管理**] で [**オンボード**] を選択します。

4. オペレーティング システム (**Windows 10 や 11** など) を選択し、オンボード方法 (**ローカル スクリプト** など) を選択します。選択した方法に関して提供されているガイダンスに従います。

5. オンボードするデバイスのセットごとに、このプロセスを繰り返します。 

> [!TIP]
> デバイスをオンボードするたびに、同じオンボード パッケージを使用する必要はありません。 例えば、ローカル スクリプトで一部のデバイスをオンボードし、後で別の方法を選択してより多くのデバイスをオンボードすることができます。

## <a name="offboard-a-device"></a>デバイスのオフボード

デバイスをオフボードにする場合は、次のいずれかの手順を使用します:

1. ナビゲーション ウィンドウで、[**設定**] を選択し、[**エンドポイント**] を選択します。

2. [**デバイス管理**] で、[**オフボード**] を選択します。

3. **Windows 10 や 11** などのオペレーティング システムを選択し、[**デバイスのオフボード**] の [**展開方法**] セクションで [**ローカル スクリプト**] を選択します。 

4. 確認画面で情報を確認し、[**ダウンロード**] を選択して続行します。

5. [**オフボード パッケージのダウンロード**] を選択します。オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。

6. オフボードする各デバイスでスクリプトを実行します。 このタスクに関するヘルプが必要ですか? 以下のリソースを参照してください。   

   - Windows デバイス: [ローカル スクリプトを使用したWindows デバイスのオフロード](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script) 
   - macOS デバイス: [macOS でのアンインストール](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business へのデータの送信を停止します。 ただし、オフボードの前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-objective"></a>次の目標

[Windows デバイスの保護を設定する](m365bp-protection-settings-for-windows-10-devices.md)。
