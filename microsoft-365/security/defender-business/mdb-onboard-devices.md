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
- m365solution-mdb-setup
ms.openlocfilehash: 6894b4a936af81cbd51dad34bbf6edf704e910a7
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969422"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>デバイスをMicrosoft Defender for Businessにオンボードする

Defender for Business では、会社のデバイスのオンボードから選択できるオプションがいくつかあります。 この記事では、これらのオプションについて説明し、オンボードのしくみの概要を説明します。

## <a name="what-to-do"></a>操作

1. タブを選択します。 
   - **Windows 10と 11**
   - **Mac**
   - **サーバー** (NEW! Windows Server または Linux Server)
   - **モバイル** (iOS/iPadOS または Android デバイスの場合)
2. オンボード オプションを表示し、選択したタブのガイダンスに従います。
3. 次の手順に進みます。

## <a name="windows-10-and-11"></a>[**Windows 10と 11**](#tab/Windows10and11)

## <a name="windows-10-and-11"></a>Windows 10と 11

Windows クライアント デバイスを Defender for Business にオンボードするには、次のいずれかのオプションを選択します。

- [ローカル スクリプト](#local-script-for-windows-10-and-11) (Microsoft 365 Defender ポータルで手動でデバイスをオンボードする場合)
- [グループ ポリシー](#group-policy-for-windows-10-and-11) (組織内でグループ ポリシーを既に使用している場合)
- [Microsoft Intune](#intune-for-windows-10-and-11) ([Microsoft 365 Business Premium](../../business-premium/index.md)に含まれています)

### <a name="local-script-for-windows-10-and-11"></a>Windows 10と 11 のローカル スクリプト

ローカル スクリプトを使用して、Windows クライアント デバイスをオンボードできます。 デバイスでオンボード スクリプトを実行すると、その信頼がまだ存在しない場合は、Azure Active Directory との信頼が作成されます。デバイスがまだ登録されていない場合は、デバイスをMicrosoft Intuneに登録し、Defender for Business にオンボードします。 ローカル スクリプト メソッドは、現在Intuneがない場合でも機能します。これは Defender for Business のお客様に推奨される方法です。

> [!TIP]
> ローカル スクリプト メソッドを使用する場合は、一度に最大 10 台のデバイスをオンボードすることをお勧めします。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで [**設定**]  >  [**エンドポイント**] を選択し、[**デバイス管理**] で [**オンボード**] を選択します。

3. **Windows 10と 11** を選択し、[**展開方法**] セクションで [**ローカル スクリプト**] を選択します。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボード パッケージをリムーバブル ドライブに保存することをお勧めします。

5. Windows デバイスで、構成パッケージの内容をデスクトップ フォルダーなどの場所に展開します。 という名前 `WindowsDefenderATPLocalOnboardingScript.cmd`のファイルが必要です。 

6. 管理者としてコマンド プロンプトを開きます。

7. スクリプト ファイルの場所を入力します。 たとえば、ファイルをデスクトップ フォルダーにコピーした場合は、次のように入力 `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`し、Enter キーを押します (または **[OK**] を選択します)。

8. スクリプトの実行後、 [検出テストを実行](#run-a-detection-test-on-a-windows-10-or-11-device)します。

### <a name="group-policy-for-windows-10-and-11"></a>Windows 10と 11 のグループ ポリシー

グループ ポリシーを使用して Windows クライアントをオンボードする場合は、「[グループ ポリシーを使用して Windows デバイスをオンボード](../defender-endpoint/configure-endpoints-gp.md)する」のガイダンスに従ってください。 この記事では、Microsoft Defender for Endpointにオンボードする手順について説明します。 Defender for Business にオンボードする手順は似ています。

### <a name="intune-for-windows-10-and-11"></a>Windows 10と 11 のIntune

サブスクリプションにIntuneが含まれている場合は、Microsoft エンドポイント マネージャー管理センター ()[https://endpoint.microsoft.com](https://endpoint.microsoft.com) で Windows クライアントやその他のデバイスをオンボードできます。 たとえば、[Microsoft 365 Business Premium](../../business/index.yml)がある場合は、サブスクリプションの一部として既にIntuneがあり、Intuneを使用してデバイスをオンボードできます。  

Intuneにデバイスを登録するには、いくつかの方法があります。 次のいずれかの方法を使用することをお勧めします。

- 会社所有または会社が管理するデバイスの [Windows 自動登録を有効にする](/mem/intune/enrollment/windows-enroll)
- [Intuneに自分のWindows 10/11 デバイスを登録するようにユーザーに依頼する](/mem/intune/user-help/enroll-windows-10-device)

#### <a name="to-enable-automatic-enrollment-for-windows-10-and-11"></a>Windows 10と 11 の自動登録を有効にするには

自動登録を設定すると、ユーザーは自分の職場アカウントをデバイスに追加します。 バックグラウンドでは、デバイスは Azure Active Directory (Azure AD) を登録して参加し、Intuneに登録されます。

1. Azure portal ([https://portal.azure.com/](https://portal.azure.com/)) に移動し、サインインします。

2. **Azure Active Directory** > **Mobility (MDM と MAM)** > **Microsoft Intune** を選択します。

3. **MDM ユーザー スコープ** と **MAM ユーザー スコープ** を構成します。

   :::image type="content" source="media/mem-mam-scope-azure-ad.png" alt-text="Intuneで MDM ユーザー スコープと MAM ユーザー スコープを設定するスクリーンショット。":::

   - MDM ユーザー スコープでは、すべてのユーザーが Windows デバイスを自動的に登録できるように、[ **すべて** ] を選択することをお勧めします。
   - MAM ユーザー スコープ セクションでは、URL に対して次の既定値をお勧めします。

       - **MDM 使用条件 URL**
       - **MDM 探索 URL**
       - **MDM 準拠 URL**

4. [**保存**] を選択します。

5. デバイスがIntuneに登録されたら、Defender for Business のデバイス グループにデバイスを追加できます。 [Defender for Business のデバイス グループの詳細については、こちらを参照してください](mdb-create-edit-device-groups.md)。

> [!TIP]
> 詳細については、「 [Windows 自動登録を有効にする」を](/mem/intune/enrollment/windows-enroll)参照してください。

#### <a name="to-have-users-enroll-their-own-windows-10-and-11-devices"></a>ユーザーが自分のWindows 10と 11 台のデバイスを登録するには

1. 登録のしくみについては、次のビデオをご覧ください。<br/><br/>

   > [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]  

2. この記事を組織内のユーザーと共有する:[Intuneに Windows 10/11 デバイスを登録します](/mem/intune/user-help/enroll-windows-10-device)。

3. デバイスがIntuneに登録されたら、Defender for Business のデバイス グループにデバイスを追加できます。 [Defender for Business のデバイス グループの詳細については、こちらを参照してください](mdb-create-edit-device-groups.md)。

### <a name="run-a-detection-test-on-a-windows-10-or-11-device"></a>Windows 10または 11 台のデバイスで検出テストを実行する

Windows デバイスを Defender for Business にオンボードしたら、デバイスで検出テストを実行して、すべてが正しく動作していることを確認できます。

1. Windows デバイスで、フォルダーを作成します: `C:\test-MDATP-test`。

2. 管理者としてコマンド プロンプトを開きます。

3. コマンド プロンプト ウィンドウで、次の PowerShell コマンドを実行します:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、コマンド プロンプト ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスのMicrosoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分間で新しいアラートが表示されます。

## <a name="view-a-list-of-onboarded-devices"></a>オンボードされたデバイスの一覧を表示する

Defender for Business にオンボードされているデバイスの一覧を表示するには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動します。 ナビゲーション ウィンドウの [ **エンドポイント**] で、[ **デバイス インベントリ**] を選択します。

## <a name="next-steps"></a>次の手順

- オンボードする他のデバイスがある場合は、それらのデバイス ([Windows 10 と 11、Mac、サーバー、またはモバイル デバイス](#what-to-do)) のタブを選択し、そのタブのガイダンスに従います。
- デバイスのオンボードが完了したら、「[手順 5: Defender for Business でセキュリティ設定とポリシーを構成](mdb-configure-security-settings.md)する」に進んでください。
- [「Defender for Business の使用を開始する」を](mdb-get-started.md)参照してください。

## <a name="mac"></a>[**Mac**](#tab/mac)

## <a name="mac"></a>Mac

> [!NOTE]
> Mac をオンボードするには、 [ローカル スクリプトを](#local-script-for-mac)使用することをお勧めします。 [Intuneを使用して Mac の登録を設定](/mem/intune/enrollment/macos-enroll)できますが、ローカル スクリプトは、Mac を Defender for Business にオンボードするための最も簡単な方法です。 

Mac をオンボードするには、次のいずれかのオプションを選択します。

- [Mac 用のローカル スクリプト](#local-script-for-mac) (*推奨*)
- [Mac 用Intune](#intune-for-mac)

### <a name="local-script-for-mac"></a>Mac 用のローカル スクリプト

Mac でローカル スクリプトを実行すると、その信頼がまだ存在しない場合は、Azure Active Directory との信頼が作成されます。Mac がまだ登録されていない場合は、mac をMicrosoft Intuneに登録し、その Mac を Defender for Business にオンボードします。 ローカル スクリプト メソッドは、現在Intuneがない場合でも機能します。 この方法を使用して、一度に最大 10 台のデバイスをオンボードすることをお勧めします。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで [**設定**]  >  [**エンドポイント**] を選択し、[**デバイス管理**] で [**オンボード**] を選択します。

3. **macOS** を選択します。 **[展開方法]** セクションで、[**ローカル スクリプト**] を選択します。 

4. [ **オンボード パッケージのダウンロード**] を選択し、リムーバブル ドライブに保存します。 [ **インストール パッケージのダウンロード**] も選択し、リムーバブル デバイスに保存します。

5. Mac で、インストール パッケージをローカル ディレクトリに `wdav.pkg` 保存します。

6. オンボード パッケージを、インストール パッケージ `WindowsDefenderATPOnboardingPackage.zip` に使用したのと同じディレクトリに保存します。

7. Finder を使用して保存したファイルに `wdav.pkg` 移動し、開きます。

8. [ **続行]** を選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。

9. Microsoft からのドライバーのインストールを許可するように求めるメッセージが表示されます ("システム拡張機能がブロックされました" または "インストールが保留中"、またはその両方)。 ドライバーのインストールを許可する必要があります。[ **セキュリティ環境設定を開く]** または [ **システム環境設定** > **のセキュリティ&プライバシー** を開く] を選択し、[ **許可**] を選択します。

10. Bash で次の Python コマンドを使用して、オンボード パッケージを実行します。 `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.sh`

Mac がIntuneに登録されたら、デバイス グループに追加できます。 [Defender for Business のデバイス グループの詳細については、こちらを参照してください](mdb-create-edit-device-groups.md)。

### <a name="intune-for-mac"></a>Mac 用Intune

サブスクリプションにMicrosoft Intuneが含まれている場合は、Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) で Mac をオンボードできます。 たとえば、[Microsoft 365 Business Premium](../../business/index.yml)がある場合は、サブスクリプションの一部として既にIntuneがあります。  

mac をIntuneに登録するには、いくつかの方法があります。 次のいずれかの方法をお勧めします。

- [会社所有の Mac のオプションを選択する](#options-for-company-owned-mac)
- [ユーザーに自分の Mac をIntuneに登録するように依頼する](#ask-users-to-enroll-their-own-mac-in-intune)

#### <a name="options-for-company-owned-mac"></a>会社所有の Mac のオプション

会社が管理する Mac デバイスをIntuneに登録するには、次のいずれかのオプションを選択します。

| オプション  | 説明  |
|---------|---------|
| Apple 自動デバイス登録 |  この方法を使用して、Apple Business Manager または Apple School Manager を通じて購入したデバイスでの登録を自動化します。 自動デバイス登録では、登録プロファイルが "無線で" デプロイされるため、デバイスに物理的にアクセスする必要はありません。 <br/><br/>[「Apple Business Manager または Apple School Manager で Mac を自動的に登録](/mem/intune/enrollment/device-enrollment-program-enroll-macos)する」を参照してください。 |
| デバイス登録マネージャー (DEM)  |  大規模なデプロイや、組織内に登録のセットアップに役立つ複数のユーザーがいる場合は、この方法を使用します。 デバイス登録マネージャー (DEM) アカウントを使用して、1 つの Azure Active Directory アカウントで最大 1,000 台のデバイスを登録できます。 このメソッドは、ポータル サイトまたは Microsoft Intune を使用してデバイスを登録します。 自動デバイス登録を使用してデバイスを登録するには、DEM アカウントを使用できません。<br/><br/> デバイス[登録マネージャー アカウントを使用してデバイスをIntuneに登録する](/mem/intune/enrollment/device-enrollment-manager-enroll)方法に関する説明を参照してください。  |
| 直接登録  | 直接登録では、ユーザー アフィニティのないデバイスが登録されるため、この方法は、1 人のユーザーに関連付けられていないデバイスに最適です。 このメソッドでは、登録する Mac に物理的にアクセスする必要があります。 <br/><br/>[Mac 用の直接登録を使用する方法に関する説明を](/mem/intune/enrollment/device-enrollment-direct-enroll-macos)参照してください。      |

#### <a name="ask-users-to-enroll-their-own-mac-in-intune"></a>ユーザーに自分の Mac をIntuneに登録するように依頼する

ビジネスでユーザーに自分のデバイスをIntuneに登録させる場合は、ユーザーに次の手順に従うように指示します。

1. ポータル サイト Web サイト ([https://portal.manage.microsoft.com/](https://portal.manage.microsoft.com/)) に移動し、サインインします。

2. ポータル サイト Web サイトの指示に従ってデバイスを追加します。

3. ポータル サイト アプリをインストール[https://aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac)し、アプリの指示に従います。

### <a name="confirm-that-a-mac-is-onboarded"></a>Mac がオンボードされていることを確認する

1. デバイスが会社に関連付けられていることを確認するには、Bash で次の Python コマンドを使用します。

   `mdatp health --field org_id`.

2. macOS 10.15 (Catalina) 以降を使用している場合は、Defender for Business にデバイスを保護するための同意を付与します。 **[システム環境設定****] の [セキュリティ] & [プライバシー** > **のフル** > **ディスク アクセス**]  >  に移動します。 ダイアログの下部にあるロック アイコンを選択して変更を加え、**Microsoft Defender for Business** (表示されている場合は **Defender for Endpoint**) を選択します。

3. デバイスがオンボードされていることを確認するには、Bash で次のコマンドを使用します。

   `mdatp health --field real_time_protection_enabled`

デバイスがIntuneに登録されたら、デバイス グループに追加できます。 [Defender for Business のデバイス グループの詳細については、こちらを参照してください](mdb-create-edit-device-groups.md)。

## <a name="view-a-list-of-onboarded-devices"></a>オンボードされたデバイスの一覧を表示する

Defender for Business にオンボードされているデバイスの一覧を表示するには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動します。 ナビゲーション ウィンドウの [ **エンドポイント**] で、[ **デバイス インベントリ**] を選択します。

## <a name="next-steps"></a>次の手順

- オンボードする他のデバイスがある場合は、それらのデバイス ([Windows 10 と 11、Mac、サーバー、またはモバイル デバイス](#what-to-do)) のタブを選択し、そのタブのガイダンスに従います。
- デバイスのオンボードが完了したら、「 [手順 5: Defender for Business でセキュリティ設定とポリシーを構成](mdb-configure-security-settings.md)する」に進んでください。
- [「Defender for Business の使用を開始する」を](mdb-get-started.md)参照してください。

## <a name="servers"></a>[**Servers**](#tab/Servers)

## <a name="servers"></a>サーバー

> [!NOTE]
> **現在、サーバーをオンボードする機能はプレビュー段階です**。

サーバーのオペレーティング システムを選択します。

- [Windows Server](#windows-server)
- [Linux Server](#linux-server)

## <a name="windows-server"></a>Windows Server

> [!IMPORTANT]
> **Windows Server エンドポイントをオンボードする機能は現在プレビュー段階です**。 Windows Server エンドポイントをオンボードする前に、次の要件を満たしていることを確認してください。
> - **[プレビュー機能]** 設定がオンになっています。 Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、**[設定]** > **[エンドポイント]** > **[全般]** > **[高度な機能]****[プレビュー機能]** >  の順に移動します。
> - Windows Server の強制範囲がオンになっています。 **[設定]** > **[エンドポイント]** > **[構成管理]** > **[強制範囲]** の順に移動します。 **[MDE を使用して MEM からセキュリティ構成設定を適用する]** を選択し、  **[Windows Server]** を選択してから、**[保存]** を選択します。

ローカル スクリプトを使用して、Windows Server のインスタンスを Defender for Business にオンボードできます。

### <a name="local-script-for-windows-server"></a>Windows Server のローカル スクリプト

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで [**設定**]  >  [**エンドポイント**] を選択し、[**デバイス管理**] で [**オンボード**] を選択します。

3. **Windows Server 1803、2019、2022** などのオペレーティング システムを選択し、[**展開方法]** セクションで [**ローカル スクリプト**] を選択します。 

   **R2 と 2016 Windows Server 2012** 選択した場合は、インストール パッケージとオンボード パッケージの 2 つのパッケージをダウンロードして実行できます。 インストール パッケージには、Defender for Business エージェントをインストールする MSI ファイルが含まれています。 オンボード パッケージには、Windows Server エンドポイントを Defender for Business にオンボードするためのスクリプトが含まれています。

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボード パッケージをリムーバブル ドライブに保存することをお勧めします。

   **R2 と 2016 Windows Server 2012** 選択した場合は、[**インストール パッケージのダウンロード**] も選択し、パッケージをリムーバブル ドライブに保存します

5. Windows Server エンドポイントで、インストール/オンボード パッケージの内容をデスクトップ フォルダーなどの場所に抽出します。 という名前 `WindowsDefenderATPLocalOnboardingScript.cmd`のファイルが必要です。 

   R2 またはWindows Server 2016 Windows Server 2012オンボードする場合は、最初にインストール パッケージを展開します。

6. 管理者としてコマンド プロンプトを開きます。

7. Windows Server 2012R2 またはWindows Server 2016をオンボードする場合は、次のコマンドを実行します。

   `Msiexec /i md4ws.msi /quiet` 

   Windows Server 1803、2019、または 2022 をオンボードする場合は、この手順をスキップし、手順 8 に進みます。

8. スクリプト ファイルの場所を入力します。 たとえば、ファイルをデスクトップ フォルダーにコピーした場合は、次のように入力 `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`し、Enter キーを押します (または **[OK**] を選択します)。

9. [Windows Server で検出テストを実行するに移動します](#run-a-detection-test-on-windows-server)。

### <a name="run-a-detection-test-on-windows-server"></a>Windows Server で検出テストを実行する

Windows Server エンドポイントを Defender for Business にオンボードした後、検出テストを実行して、すべてが正しく動作していることを確認できます。

1. Windows Server デバイスで、フォルダーを作成します `C:\test-MDATP-test`。

2. 管理者としてコマンド プロンプトを開きます。

3. コマンド プロンプト ウィンドウで、次の PowerShell コマンドを実行します:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、コマンド プロンプト ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスのMicrosoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分間で新しいアラートが表示されます。

## <a name="linux-server"></a>Linux Server

> [!IMPORTANT]
> **Linux Server エンドポイントをオンボードする機能は現在プレビュー段階です**。 Linux Server エンドポイントをオンボードする前に、次の要件を満たしていることを確認してください。
> - **[プレビュー機能]** 設定がオンになっています。 Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、**[設定]** > **[エンドポイント]** > **[全般]** > **[高度な機能]****[プレビュー機能]** >  の順に移動します。
> - [Linux でのMicrosoft Defender for Endpointの前提条件を](../defender-endpoint/microsoft-defender-endpoint-linux.md#prerequisites)満たしています。

### <a name="onboard-linux-server-endpoints"></a>Linux Server エンドポイントをオンボードする

次の方法を使用して、Linux Server のインスタンスを Defender for Business にオンボードできます。

- **ローカル スクリプト:**[Linux でのMicrosoft Defender for Endpointの手動デプロイに関する記事を](../defender-endpoint/linux-install-manually.md)参照してください。
- **アンシブル：**[Ansible を使用した Linux へのMicrosoft Defender for Endpointのデプロイに関する記事を](../defender-endpoint/linux-install-with-ansible.md)参照してください。
- **シェフ：**[Chef を使用した Linux 上の Defender for Endpoint のデプロイに関する](../defender-endpoint/linux-deploy-defender-for-endpoint-with-chef.md)記事を参照してください。
- **人形：**[Puppet を使用した Linux でのMicrosoft Defender for Endpointのデプロイに関する記事を](../defender-endpoint/linux-install-with-puppet.md)参照してください。

> [!NOTE]
> Linux Server のインスタンスを Defender for Business にオンボードすることは、[Linux 上のMicrosoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint-linux.md)へのオンボードと同じです。

## <a name="view-a-list-of-onboarded-devices"></a>オンボードされたデバイスの一覧を表示する

Defender for Business にオンボードされているデバイスの一覧を表示するには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動します。 ナビゲーション ウィンドウの [ **エンドポイント**] で、[ **デバイス インベントリ**] を選択します。

## <a name="next-steps"></a>次の手順

- オンボードする他のデバイスがある場合は、それらのデバイス ([Windows 10 と 11、Mac、サーバー、またはモバイル デバイス](#what-to-do)) のタブを選択し、そのタブのガイダンスに従います。
- デバイスのオンボードが完了したら、「 [手順 5: Defender for Business でセキュリティ設定とポリシーを構成](mdb-configure-security-settings.md)する」に進んでください。
- [「Defender for Business の使用を開始する」を](mdb-get-started.md)参照してください。

## <a name="mobile-devices"></a>[**モバイル デバイス**](#tab/mobiles)

## <a name="mobile-devices"></a>モバイル デバイス

Android や iOS/iPadOS デバイスなどのモバイル デバイスをオンボードするには、Microsoft Intuneが必要です。 [Microsoft 365 Business Premium](../../business/index.yml)がある場合は、Intune。 

これらのデバイスをIntuneに登録する方法については、次のリソースを参照してください。

- [Android デバイスを登録する](/mem/intune/enrollment/android-enroll)
- [iOS または iPadOS デバイスを登録する](/mem/intune/enrollment/ios-enroll)

デバイスがIntuneに登録されたら、デバイス グループに追加できます。 [Defender for Business のデバイス グループの詳細については、こちらを参照してください](mdb-create-edit-device-groups.md)。

## <a name="next-steps"></a>次の手順

- オンボードする他のデバイスがある場合は、それらのデバイス ([Windows 10 と 11、Mac、サーバー、またはモバイル デバイス](#what-to-do)) のタブを選択し、そのタブのガイダンスに従います。
- デバイスのオンボードが完了したら、「 [手順 5: Defender for Business でセキュリティ設定とポリシーを構成](mdb-configure-security-settings.md)する」に進んでください。
- [「Defender for Business の使用を開始する」を](mdb-get-started.md)参照してください。
