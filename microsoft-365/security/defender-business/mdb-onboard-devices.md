---
title: デバイスをMicrosoft Defender for Businessにオンボードする
description: デバイスを Defender for Business にオンボードし、初日からデバイスを保護する方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ce3c458013a96f845da528104997b63360879c56
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174060"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>デバイスをMicrosoft Defender for Businessにオンボードする

Microsoft Defender for Businessを使用すると、会社のデバイスのオンボードから選択できるオプションがいくつかあります。 この記事では、オプションについて説明し、オンボードのしくみの概要について説明します。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="what-to-do"></a>操作

1. オペレーティング システムのタブ (**Windows クライアント**、**macOS コンピューター**、**モバイル デバイス**) を選択します。
2. オンボード オプションを表示し、選択したタブのガイダンスに従います。
3. 次の手順に進みます。

## <a name="windows-clients"></a>[**Windows クライアント**](#tab/WindowsClientDevices)

## <a name="windows-clients"></a>Windows クライアント

次のいずれかのオプションを選択して、Windowsクライアント デバイスを Defender for Business にオンボードします。

- [ローカル スクリプト](#local-script-for-windows-clients) (Microsoft 365 Defender ポータルで手動でデバイスをオンボードする場合)
- [グループ ポリシー](#group-policy-for-windows-clients) (組織内でグループ ポリシーを既に使用している場合)
- [Microsoft Intune](#microsoft-intune-for-windows-clients) ([Microsoft 365 Business Premium](../../business-premium/index.md)に含まれています)


### <a name="local-script-for-windows-clients"></a>Windows クライアントのローカル スクリプト

ローカル スクリプトを使用して、Windowsクライアント デバイスをオンボードできます。 デバイスでオンボード スクリプトを実行すると、Azure Active Directoryを使用して信頼が作成され (その信頼がまだ存在しない場合)、デバイスがMicrosoft Intuneに登録され (まだ登録されていない場合)、デバイスが Defender for Business にオンボードされます。 ローカル スクリプト メソッドは、現在Intuneがない場合でも機能します。 この方法を使用して、一度に最大 10 台のデバイスをオンボードすることをお勧めします。

> [!TIP]
> ローカル スクリプト メソッドを使用する場合は、一度に最大 10 台のデバイスをオンボードすることをお勧めします。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで [**設定**]  >  [**エンドポイント**] を選択し、[**デバイス管理**] で [**オンボード**] を選択します。

3. **Windows 10や 11** などのオペレーティング システムを選択し、[**展開方法]** セクションで [**ローカル スクリプト**] を選択します。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボード パッケージをリムーバブル ドライブに保存することをお勧めします。

5. Windows デバイスで、構成パッケージの内容をデスクトップ フォルダーなどの場所に展開します。 という名前 `WindowsDefenderATPLocalOnboardingScript.cmd`のファイルが必要です。 

6. 管理者としてコマンド プロンプト ウィンドウを開きます。

7. スクリプト ファイルの場所を入力します。 たとえば、ファイルをデスクトップ フォルダーにコピーした場合は、次のように入力 `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`し、Enter キーを押します (または **[OK**] を選択します)。

8. スクリプトの実行後、 [検出テストの実行](#running-a-detection-test-on-a-windows-client)に進みます。

### <a name="group-policy-for-windows-clients"></a>Windows クライアントのグループ ポリシー

グループ ポリシーを使用してWindows クライアントをオンボードする場合は、「グループ ポリシーを[使用したデバイスのオンボードWindows](../defender-endpoint/configure-endpoints-gp.md)」のガイダンスに従います。 この記事では、Microsoft Defender for Endpointにオンボードする手順について説明しますが、Defender for Business にオンボードする手順は似ています。

### <a name="microsoft-intune-for-windows-clients"></a>Windows クライアントのMicrosoft Intune

サブスクリプションにIntuneが含まれている場合は、Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) でWindowsクライアントとその他のデバイスをオンボードできます。 たとえば、[Microsoft 365 Business Premium](../../business/index.yml)がある場合は、サブスクリプションの一部としてIntuneがあります。  

Intuneにデバイスを登録するには、いくつかの方法があります。 次のいずれかの方法から始めることをお勧めします。

- 会社所有または会社が管理するデバイスの[自動登録Windows有効にする](/mem/intune/enrollment/windows-enroll)
- [Intuneに自分のWindows 10/11 デバイスを登録するようにユーザーに依頼する](/mem/intune/user-help/enroll-windows-10-device)

#### <a name="to-enable-automatic-enrollment-for-windows-devices"></a>Windows デバイスの自動登録を有効にするには

自動登録を設定すると、ユーザーは自分の職場アカウントをデバイスに追加します。 バックグラウンドでは、デバイスはAzure Active Directory (Azure AD) を登録して参加し、Intuneに登録されます。

1. Azure portal ([https://portal.azure.com/](https://portal.azure.com/)) に移動し、サインインします。 

2. **Azure Active Directory** >  **Mobility (MDM と MAM)** > **Microsoft Intune** を選択します。

3. **MDM ユーザー スコープ** と **MAM ユーザー スコープ** を構成します。

   :::image type="content" source="media/mem-mam-scope-azure-ad.png" alt-text="Intuneで MDM ユーザー スコープと MAM ユーザー スコープを設定するスクリーンショット。":::

   - MDM ユーザー スコープでは、すべてのユーザーがWindowsデバイスを自動的に登録できるように、[**すべて**] を選択することをお勧めします。
   - MAM ユーザー スコープ セクションでは、URL に次の既定値を使用することをお勧めします。

       - **MDM 使用条件 URL**
       - **MDM 探索 URL**
       - **MDM 準拠 URL**

4. **[保存]** を選択します。

5. デバイスがIntuneに登録されたら、デバイス グループに追加できます。 [Microsoft Defender for Businessのデバイス グループの詳細について説明](mdb-create-edit-device-groups.md)します。


> [!TIP]
> 自動登録の詳細については、「自動登録[Windows有効にする](/mem/intune/enrollment/windows-enroll)」を参照してください。

#### <a name="to-have-users-enroll-their-own-windows-devices"></a>ユーザーに独自のWindows デバイスを登録させるには

1. 登録のしくみについては、次のビデオをご覧ください。 <br/><br/>

   > [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]  

2. この記事を組織内のユーザーと共有する:[Intuneに Windows 10/11 デバイスを登録します](/mem/intune/user-help/enroll-windows-10-device)。

3. デバイスがIntuneに登録されたら、デバイス グループに追加できます。 [Microsoft Defender for Businessのデバイス グループの詳細について説明](mdb-create-edit-device-groups.md)します。

### <a name="running-a-detection-test-on-a-windows-client"></a>Windows クライアントで検出テストを実行する

Windowsデバイスを Defender for Business にオンボードしたら、Windows デバイスで検出テストを実行して、すべてが正しく動作していることを確認できます。

1. Windows デバイスで、フォルダーを作成します: `C:\test-MDATP-test`。

2. 管理者としてコマンド プロンプト ウィンドウを開きます。

3. コマンド プロンプト ウィンドウで、次の PowerShell コマンドを実行します:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、コマンド プロンプト ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスのMicrosoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分間で新しいアラートが表示されます。

## <a name="view-a-list-of-onboarded-devices"></a>オンボードされたデバイスの一覧を表示する

Defender for Business にオンボードされているデバイスの一覧を表示するには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、ナビゲーション ウィンドウの [**エンドポイント**] で [**デバイス インベントリ**] を選択します。

## <a name="next-steps"></a>次の手順

- オンボードする他のデバイスがある場合は、デバイス [(Windows クライアント、Windows サーバー、macOS、モバイル デバイス](#what-to-do)) のオペレーティング システムに対応するタブを選択し、そのタブのガイダンスに従います。
- デバイスのオンボードが完了したら、「[手順 5: Microsoft Defender for Businessでセキュリティ設定とポリシーを構成する」に](mdb-configure-security-settings.md)進みます。
- [Microsoft Defender for Businessを使用した概要を](mdb-get-started.md)参照してください。

## <a name="macos"></a>[**macOS**](#tab/macOSdevices)

## <a name="macos-computers"></a>macOS コンピューター

> [!NOTE]
> - ローカル スクリプトを使用して [macOS デバイスをオンボード](#local-script-for-macos)することをお勧めします。 [Intuneで macOS デバイスの登録を設定](/mem/intune/enrollment/macos-enroll)できますが、ローカル スクリプトは、MacOS デバイスを Defender for Business にオンボードするための最も簡単な方法です。 

macOS デバイスをオンボードするには、次のいずれかのオプションを選択します。

- [macOS 用のローカル スクリプト](#local-script-for-macos) (*推奨*)
- [macOS のIntune](#microsoft-intune-for-macos)

### <a name="local-script-for-macos"></a>macOS 用のローカル スクリプト

macOS デバイスでローカル スクリプトを実行すると、Azure Active Directoryを使用して信頼が作成され (その信頼がまだ存在しない場合)、Microsoft Intuneにデバイスが登録され (まだ登録されていない場合)、デバイスが Defender for Business にオンボードされます。 ローカル スクリプト メソッドは、現在Intuneがない場合でも機能します。 この方法を使用して、一度に最大 10 台のデバイスをオンボードすることをお勧めします。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで [**設定**]  >  [**エンドポイント**] を選択し、[**デバイス管理**] で [**オンボード**] を選択します。

3. **macOS** を選択し、[**展開方法]** セクションで [**ローカル スクリプト**] を選択します。 

4. [ **オンボード パッケージのダウンロード**] を選択し、リムーバブル ドライブに保存します。 [ **インストール パッケージのダウンロード**] も選択し、リムーバブル デバイスに保存します。

5. macOS デバイスで、インストール パッケージ `wdav.pkg` をローカル ディレクトリに保存します。

6. オンボード パッケージを、インストール パッケージ `WindowsDefenderATPOnboardingPackage.zip` に使用したのと同じディレクトリに保存します。

7. Finder を使用して保存したファイルに `wdav.pkg` 移動し、開きます。

8. [ **続行]** を選択し、ライセンス条項に同意し、入力を求められたらパスワードを入力します。

9. Microsoft のドライバーのインストールを許可するように求めるメッセージが表示されます ("システム拡張機能がブロックされました" または "インストールは保留中"、またはその両方です)。 ドライバーのインストールを許可する必要があります。 インストールを許可するには、[**セキュリティ環境設定を開く]** または [**Open System PreferencesSecurity** >  **& Privacy**] を選択し、[**許可**] を選択します。

10. Bash で次の Python コマンドを使用して、オンボード パッケージを実行します。 `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py`

11. デバイスがIntuneに登録されたら、デバイス グループに追加できます。 [Microsoft Defender for Businessのデバイス グループの詳細について説明](mdb-create-edit-device-groups.md)します。

### <a name="microsoft-intune-for-macos"></a>macOS のMicrosoft Intune

サブスクリプションにMicrosoft Intuneが含まれている場合は、Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) で macOS デバイスをオンボードできます。 たとえば、[Microsoft 365 Business Premium](../../business/index.yml)がある場合は、サブスクリプションの一部としてIntuneがあります。  

Intuneにデバイスを登録するには、いくつかの方法があります。 次のいずれかの方法から始めることをお勧めします。

- [会社所有の macOS デバイスのオプションを選択する](#options-for-company-owned-macos-devices)
- [ユーザーに自分の macOS デバイスをIntuneに登録するように依頼する](#ask-users-to-enroll-their-own-macos-devices-in-intune)

#### <a name="options-for-company-owned-macos-devices"></a>会社所有の macOS デバイスのオプション

次の表のいずれかのオプションを選択して、会社が管理する macOS デバイスをIntuneに登録します。

| オプション  | 説明  |
|---------|---------|
| Apple 自動デバイス登録 |  この方法を使用して、Apple Business Manager または Apple School Manager を通じて購入したデバイスでの登録エクスペリエンスを自動化します。 自動デバイス登録では、登録プロファイルが OTA で登録されるため、デバイスに物理的にアクセスする必要はありません。 <br/><br/>[「Apple Business Manager または Apple School Manager で macOS デバイスを自動的に登録](/mem/intune/enrollment/device-enrollment-program-enroll-macos)する」を参照してください。 |
| デバイス登録マネージャー (DEM)  |  大規模なデプロイや、組織内に登録のセットアップに役立つ複数のユーザーがいる場合は、この方法を使用します。 デバイス登録マネージャー (DEM) アカウントを使用して、1 つの Azure Active Directory アカウントで最大 1,000 台のデバイスを登録できます。 このメソッドは、ポータル サイトまたは Microsoft Intune を使用してデバイスを登録します。 自動デバイス登録を使用してデバイスを登録するには、DEM アカウントを使用できません。<br/><br/> デバイス[登録マネージャー アカウントを使用してデバイスをIntuneに登録する](/mem/intune/enrollment/device-enrollment-manager-enroll)方法に関する説明を参照してください。  |
| 直接登録  | 直接登録では、ユーザー アフィニティのないデバイスが登録されるため、この方法は、1 人のユーザーに関連付けられていないデバイスに最適です。 このメソッドでは、登録する Mac に物理的にアクセスする必要があります。 <br/><br/>[macOS デバイスに直接登録を使用する方法に関する](/mem/intune/enrollment/device-enrollment-direct-enroll-macos)説明を参照してください。      |

#### <a name="ask-users-to-enroll-their-own-macos-devices-in-intune"></a>ユーザーに自分の macOS デバイスをIntuneに登録するように依頼する

ビジネスでユーザーに自分のデバイスをIntuneに登録させる場合は、次の手順に従うようにユーザーに依頼します。

1. ポータル サイト Web サイト ([https://portal.manage.microsoft.com/](https://portal.manage.microsoft.com/)) に移動し、サインインします。

2. ポータル サイト Web サイトの指示に従ってデバイスを追加します。

3. ポータル サイト アプリをインストール[https://aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac)し、アプリの指示に従います。

### <a name="confirm-that-a-macos-device-is-onboarded"></a>macOS デバイスがオンボードされていることを確認する

1. デバイスが会社に関連付けられていることを確認するには、Bash で次の Python コマンドを使用します `mdatp health --field org_id`。

2. macOS 10.15 (Catalina) 以降を使用している場合は、Defender for Business にデバイスを保護するための同意を付与します。 **System PreferencesSecurity** >  **&** **PrivacyPrivacyFull** >  >  **Disk Access に移動** します。 ロック アイコンを選択して変更を加え (ダイアログ ボックスの下部)、**Microsoft Defender for Business** (表示されている場合は **Defender for Endpoint**) を選択します。

3. デバイスがオンボードされていることを確認するには、Bash で次のコマンドを使用します。 `mdatp health --field real_time_protection_enabled`

4. デバイスがIntuneに登録されたら、デバイス グループに追加できます。 [Microsoft Defender for Businessのデバイス グループの詳細について説明](mdb-create-edit-device-groups.md)します。

## <a name="view-a-list-of-onboarded-devices"></a>オンボードされたデバイスの一覧を表示する

Defender for Business にオンボードされているデバイスの一覧を表示するには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、ナビゲーション ウィンドウの [**エンドポイント**] で [**デバイス インベントリ**] を選択します。

## <a name="next-steps"></a>次の手順

- オンボードする他のデバイスがある場合は、デバイス ([Windows クライアント、Windows サーバー、macOS、モバイル デバイス](#what-to-do)) のオペレーティング システムに対応するタブを選択し、そのタブのガイダンスに従います。
- デバイスのオンボードが完了したら、「[手順 5: Microsoft Defender for Businessでセキュリティ設定とポリシーを構成する」に](mdb-configure-security-settings.md)進みます。
- [Microsoft Defender for Businessを使用した概要を](mdb-get-started.md)参照してください。

## <a name="mobile-devices"></a>[**モバイル デバイス**](#tab/mobiles)

## <a name="mobile-devices"></a>モバイル デバイス

Android や iOS/iPadOS デバイスなどのモバイル デバイスをオンボードするには、Microsoft Intuneが必要です。 [Microsoft 365 Business Premium](../../business/index.yml)がある場合は、Intune。 

これらのデバイスをIntuneに登録する方法については、次のリソースを参照してください。

- [Android デバイスを登録する](/mem/intune/enrollment/android-enroll)
- [iOS または iPadOS デバイスを登録する](/mem/intune/enrollment/ios-enroll)

デバイスがIntuneに登録されたら、デバイス グループに追加できます。 [Microsoft Defender for Businessのデバイス グループの詳細について説明](mdb-create-edit-device-groups.md)します。

## <a name="next-steps"></a>次の手順

- オンボードする他のデバイスがある場合は、デバイス ([Windows クライアント、Windows サーバー、macOS、モバイル デバイス](#what-to-do)) のオペレーティング システムに対応するタブを選択し、そのタブのガイダンスに従います。
- デバイスのオンボードが完了したら、「[手順 5: Microsoft Defender for Businessでセキュリティ設定とポリシーを構成する」に](mdb-configure-security-settings.md)進みます。
- [Microsoft Defender for Businessを使用した概要を](mdb-get-started.md)参照してください。
