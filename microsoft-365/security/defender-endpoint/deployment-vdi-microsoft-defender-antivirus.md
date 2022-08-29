---
title: Microsoft Defender ウイルス対策仮想デスクトップ インフラストラクチャの展開ガイド
description: 保護とパフォーマンスのバランスを最適にするために、仮想デスクトップ環境に Microsoft Defender ウイルス対策をデプロイする方法について説明します。
keywords: vdi, hyper-v, vm, 仮想マシン, Windows Defender, ウイルス対策, av, 仮想デスクトップ, rds, リモート デスクトップ
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: ba24bcac58ce814282b56244d530858a1c3bdea1
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387619"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

標準のオンプレミスまたはハードウェア構成に加えて、リモート デスクトップ (RDS) または非永続的仮想デスクトップ インフラストラクチャ (VDI) 環境で Microsoft Defender ウイルス対策を使用できます。 VDI で実行されている VM に更新プログラムを簡単にデプロイできるため、コンピューター上の更新プログラムを迅速かつ簡単に入手できます。 更新プログラムがホスト サーバー上のコンポーネント ビットに展開され、オンになると VM に直接ダウンロードされるため、ゴールデン イメージを定期的に作成してシールする必要はなくなりました。

このガイドでは、次の方法を含め、最適な保護とパフォーマンスを実現するために VM を構成する方法について説明します。

- [セキュリティ インテリジェンス更新プログラム用に専用の VDI ファイル共有を設定する](#set-up-a-dedicated-vdi-file-share)
- [スケジュールされたスキャンをランダム化する](#randomize-scheduled-scans)
- [クイック スキャンを使用する](#use-quick-scans)
- [通知を禁止する](#prevent-notifications)
- [すべての更新後にスキャンが発生しないようにする](#disable-scans-after-an-update)
- [しばらくオフラインになっている古いマシンまたはマシンをスキャンする](#scan-vms-that-have-been-offline)
- [除外を適用する](#exclusions)

Microsoft リモート デスクトップ サービスと VDI のサポートの詳細については、[Azure Virtual Desktop のドキュメントを参照してください](/azure/virtual-desktop)。

Azure ベースの仮想マシンについては、「 [Microsoft Defender for Cloud への Endpoint Protection のインストール」を](/azure/defender-for-cloud/endpoint-protection-recommendations-technical)参照してください。

> [!IMPORTANT]
> VDI はWindows Server 2012またはWindows Server 2016でホストできますが、以前のバージョンの Windows では利用できない保護機能が強化されているため、仮想マシン (VM) は少なくとも 1607 Windows 10実行されている必要があります。
> Microsoft Defender ウイルス対策がWindows 10 Insider Preview の仮想マシンで動作する方法には、パフォーマンスと機能の向上があります。ビルド 18323 (以降)。 Insider Preview ビルドを使用する必要がある場合は、このガイドで特定します。指定されていない場合は、最適な保護とパフォーマンスに必要な最小バージョンは 1607 Windows 10。

## <a name="set-up-a-dedicated-vdi-file-share"></a>専用の VDI ファイル共有を設定する

Windows 10バージョン 1903 では、ダウンロードしたセキュリティ インテリジェンス更新プログラムのアンパックをホスト マシンにオフロードする共有セキュリティ インテリジェンス機能を導入しました。これにより、個々のマシンで以前の CPU、ディスク、およびメモリ リソースを節約できます。 この機能はバックポートされ、Windows 10 バージョン 1703 以降で機能するようになりました。 この機能は、グループ ポリシーまたは PowerShell で設定できます。

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>グループ ポリシーを使用して、共有セキュリティ インテリジェンス機能を有効にします。

1. グループ ポリシー管理コンピューターで、グループ ポリシー管理コンソールを開き、構成するグループ ポリシーオブジェクトを右クリックして、[編集] をクリック **します**。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. [ **管理用テンプレート]** をクリックします。

4. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> **セキュリティ インテリジェンス 更新** に展開します。

5. **[VDI クライアントのセキュリティ インテリジェンスの場所の定義**] をダブルクリックし、オプションを **[有効]** に設定します。 フィールドが自動的に表示されます。

6. 入力します `\\<sharedlocation\>\wdav-update` (この値のヘルプについては、「 [ダウンロードとパッケージ解除](#download-and-unpackage-the-latest-updates)」を参照してください)。

7. [**OK**] をクリックします。

8. テストする VM に GPO をデプロイします。

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>PowerShell を使用して共有セキュリティ インテリジェンス機能を有効にする

この機能を有効にするには、次のコマンドレットを使用します。 通常は PowerShell ベースの構成ポリシーを VM にプッシュするため、これをプッシュする必要があります。

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

内容については、「 [ダウンロードとパッケージ解除](#download-and-unpackage-the-latest-updates) 」セクションを \<shared location\> 参照してください。

## <a name="download-and-unpackage-the-latest-updates"></a>最新の更新プログラムをダウンロードしてパッケージ化解除する

これで、新しい更新プログラムのダウンロードとインストールを開始できます。 以下に示すサンプル PowerShell スクリプトを作成しました。 このスクリプトは、新しい更新プログラムをダウンロードして VM の準備を整える最も簡単な方法です。 その後、スケジュールされたタスクを使用して管理マシンで特定の時点で実行するようにスクリプトを設定する必要があります (または、Azure、Intune、SCCM で PowerShell スクリプトを使用する場合は、これらのスクリプトを使用することもできます)。

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd /d $vdmpath & mpam-fe.exe /x"
```

スケジュールされたタスクを 1 日に 1 回実行するように設定して、パッケージがダウンロードおよびアンパックされるたびに VM が新しい更新プログラムを受け取るようにすることができます。
1 日に 1 回から始めることをお勧めしますが、影響を理解するために頻度の増減を試す必要があります。

セキュリティ インテリジェンス パッケージは通常、3 時間から 4 時間に 1 回発行されます。 頻度を 4 時間未満に設定しても、管理マシンのネットワーク オーバーヘッドが向上するため、お勧めしません。

また、VM に代わって更新プログラムを一定間隔でフェッチし、使用するためにファイル共有に配置するように、単一のサーバーまたはマシンを設定することもできます。
これは、更新プログラムを取得できるように、デバイスが共有への読み取りアクセス許可と NTFS アクセス許可を持っている場合に可能です。 これを行うには、次の手順を実行します。

 1. SMB/CIFS ファイル共有を作成します。 
 
 2. 次の例を使用して、次の共有アクセス許可を持つファイル共有を作成します。

    ```PowerShell
    PS c:\> Get-SmbShareAccess -Name mdatp$

    Name   ScopeName AccountName AccessControlType AccessRight
    ----   --------- ----------- ----------------- -----------
    mdatp$ *         Everyone    Allow             Read
    ```
   
    > [!NOTE]
    > NTFS アクセス許可は、 **認証されたユーザーに対して追加されます。読み取り:**. 

    この例では、ファイル共有は次のとおりです。

    `\\fileserver.fqdn\mdatp$\wdav-update`

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>PowerShell スクリプトを実行するようにスケジュールされたタスクを設定する

1. 管理マシンで、[スタート] メニューを開き、「 **タスク スケジューラ」** と入力します。 それを開き、サイド パネルで **[タスクの作成]...** を選択します。

2. **セキュリティ インテリジェンス アンパックャー** として名前を入力します。 **[トリガー**] タブに移動します。**[新規]を** 選択します。\>**毎日**、OK を選択 **します**。

3. **[アクション]** タブに移動します。**[新規]** を選択します。**[プログラム/スクリプト**] フィールドに **「PowerShell**」と入力します。 **[引数の追加]** フィールドに入力`-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1`します。 **[OK]** をクリックします。

4. 必要に応じて、追加の設定を構成することもできます。

5. [ **OK] を** 選択して、スケジュールされたタスクを保存します。

タスクを右クリックして [ **実行**] をクリックすると、更新プログラムを手動で開始できます。

### <a name="download-and-unpackage-manually"></a>手動でダウンロードしてパッケージを解除する

すべてを手動で実行する場合は、スクリプトの動作をレプリケートする方法を次に示します。

1. インテリジェンス更新プログラムを格納するために呼び出された `wdav_update` システム ルートに新しいフォルダーを作成します 。たとえば、フォルダーを作成します `c:\wdav_update`。

2. 次のような GUID 名 *を持つwdav_update* の下にサブフォルダーを作成します。 `{00000000-0000-0000-0000-000000000000}`

   例を次に示します。 `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > スクリプトでは、GUID の最後の 12 桁がファイルがダウンロードされた年、月、日、時刻になるように設定し、毎回新しいフォルダーが作成されるようにします。 ファイルが毎回同じフォルダーにダウンロードされるように、これを変更できます。

3. GUID フォルダーにセキュリティ インテリジェンス パッケージ [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  をダウンロードします。 ファイルには名前を付ける `mpam-fe.exe`必要があります。

4. cmd プロンプト ウィンドウを開き、作成した GUID フォルダーに移動します。 たとえば、 **/X** 抽出コマンドを使用してファイル `mpam-fe.exe /X`を抽出します。

   > [!NOTE]
   > VM は、抽出された更新プログラム パッケージを使用して新しい GUID フォルダーが作成されるたびに、または新しい抽出されたパッケージで既存のフォルダーが更新されるたびに、更新されたパッケージを取得します。

## <a name="randomize-scheduled-scans"></a>スケジュールされたスキャンをランダム化する

スケジュールされたスキャンは、 [リアルタイムの保護とスキャン](configure-real-time-protection-microsoft-defender-antivirus.md)に加えて実行されます。

スキャン自体の開始時刻は、スケジュールされたスキャン ポリシー (**ScheduleDay**、 **ScheduleTime**、 **ScheduleQuickScanTime**) に基づいています。 ランダム化すると、Microsoft Defender ウイルス対策は、スケジュールされたスキャンに設定された時間から 4 時間以内に各コンピューターでスキャンを開始します。

[スケジュールされたスキャン](scheduled-catch-up-scans-microsoft-defender-antivirus.md)で使用できるその他の構成オプションについては、スキャンのスケジュールを設定する方法に関するセクションを参照してください。

## <a name="use-quick-scans"></a>クイック スキャンを使用する

スケジュールされたスキャン中に実行する必要があるスキャンの種類を指定できます。 クイック スキャンは、マルウェアをアクティブにする必要があるすべての場所を検索するように設計されているため、推奨されるアプローチです。 次の手順では、グループ ポリシーを使用してクイック スキャンを設定する方法について説明します。

1. グループ ポリシー エディターで、**管理用テンプレート** \> **の Windows コンポーネント** \> **の Microsoft Defender ウイルス対策**\>スキャンに移動 **します**。

2. [ **スケジュールされたスキャンに使用するスキャンの種類を指定** する] を選択し、ポリシー設定を編集します。

3. ポリシーを **[有効]** に設定し、[ **オプション]** で [  **クイック スキャン**] を選択します。

4. **[OK]** を選択します。

5. 通常どおりにグループ ポリシー オブジェクトを展開します。

## <a name="prevent-notifications"></a>通知を禁止する

場合によっては、Microsoft Defender ウイルス対策通知が複数のセッション間で送信または保持されることがあります。 この問題を最小限に抑えるために、Microsoft Defender ウイルス対策ユーザー インターフェイスをロックダウンできます。 次の手順では、グループ ポリシーを使用して通知を抑制する方法について説明します。

1. グループ ポリシー エディターで、**Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** \> **クライアント インターフェイス** に移動します。

2. [ **すべての通知を抑制する]** を選択し、ポリシー設定を編集します。

3. ポリシーを **[有効]** に設定し、[ **OK**] を選択します。

4. 通常どおりにグループ ポリシー オブジェクトを展開します。

通知を抑制すると、Microsoft Defender ウイルス対策からの通知が、スキャンの実行時または修復アクションが実行されたときに、Windows 10のアクション センターに表示されなくなります。 ただし、セキュリティ運用チームは、攻撃の検出と停止中にスキャンの結果を確認します。"初期アクセス アラート" などのアラートがトリガーされ、[Microsoft 365 Defender ポータル](/microsoft-365/security/defender/microsoft-365-defender)に表示されます。

> [!TIP]
> Windows 10またはWindows 11でアクション センターを開くには、次のいずれかの手順を実行します。
> - タスク バーの右端にある [アクション センター] アイコンを選択します。
> - Windows ロゴ キー ボタン + A キーを押します。
> - タッチスクリーン デバイスで、画面の右端からスワイプインします。

## <a name="disable-scans-after-an-update"></a>更新後にスキャンを無効にする

更新後にスキャンを無効にすると、更新プログラムを受信した後にスキャンが発生できなくなります。 クイック スキャンも実行している場合は、基本イメージを作成するときにこの設定を適用できます。 これにより、新しく更新された VM で再びスキャンが実行されないようにすることができます (ベース イメージの作成時に既にスキャンしているため)。

> [!IMPORTANT]
> 更新後にスキャンを実行すると、VM が最新のセキュリティ インテリジェンス更新プログラムで確実に保護されます。 このオプションを無効にすると、VM の保護レベルが低下し、基本イメージを最初に作成またはデプロイする場合にのみ使用する必要があります。

1. グループ ポリシー エディターで、**Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** \> **セキュリティ インテリジェンス 更新** に移動します。

2. [ **セキュリティ インテリジェンスの更新後にスキャンを有効にする** ] を選択し、ポリシー設定を編集します。

3. ポリシーを無効に設定 **します**。

4. **[OK]** を選択します。

5. 通常どおりにグループ ポリシー オブジェクトを展開します。

このポリシーを使用すると、更新直後にスキャンが実行されなくなります。

## <a name="disable-the-scanonlyifidle-option"></a>オプションを `ScanOnlyIfIdle` 無効にする

次のコマンドレットを使用して、デバイスがパッシブ モードの場合にデバイスがアイドル状態になったときに、クイック スキャンまたはスケジュールされたスキャンを停止します。

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled $false
```

ローカルまたはドメイン グループ ポリシーを `ScanOnlyIfIdle` 使用して構成することで、Microsoft Defender ウイルス対策のオプションを無効にすることもできます。 これにより、高密度環境での CPU 競合が大幅に回避されます。

詳細については、「 [コンピューターがオンになっていて使用中でない場合にのみ、スケジュールされたスキャンを開始する」を参照](https://admx.help/?Category=SystemCenterEndpointProtection&Policy=Microsoft.Policies.Antimalware::scan_scanonlyifidle)してください。

## <a name="scan-vms-that-have-been-offline"></a>オフラインになっている VM をスキャンする

1. グループ ポリシー エディターで、**Windows コンポーネント** \> **の Microsoft Defender ウイルス対策**\>スキャンに移動 **します**。

2. [ **キャッチアップ クイック スキャンを有効にする** ] を選択し、ポリシー設定を編集します。

3. ポリシーを **[有効]** に設定します。

4. **[OK]** をクリックします。

5. 通常どおり、グループ ポリシー オブジェクトをデプロイします。

このポリシーは、VM が 2 つ以上の連続したスケジュールされたスキャンを見逃した場合にスキャンを強制します。

## <a name="enable-headless-ui-mode"></a>ヘッドレス UI モードを有効にする

1. グループ ポリシー エディターで、**Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** \> **クライアント インターフェイス** に移動します。

2. [ **ヘッドレス UI モードを有効にする]** を選択し、ポリシーを編集します。

3. ポリシーを **[有効]** に設定します。

4. [**OK**] をクリックします。

5. 通常どおり、グループ ポリシー オブジェクトをデプロイします。

このポリシーは、組織内のエンド ユーザーから Microsoft Defender ウイルス対策ユーザー インターフェイス全体を非表示にします。

## <a name="exclusions"></a>除外

除外は、ニーズに合わせて追加、削除、またはカスタマイズできます。

詳細については、「 [Windows Server で Microsoft Defender ウイルス対策の除外を構成する」を参照してください](configure-exclusions-microsoft-defender-antivirus.md)。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="additional-resources"></a>その他のリソース

- [Tech Community ブログ: 非永続的 VDI マシン用の Microsoft Defender ウイルス対策の構成](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [リモート デスクトップ サービスと VDI に関する TechNet フォーラム](https://social.technet.microsoft.com/Forums/windowsserver/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell スクリプト](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)
