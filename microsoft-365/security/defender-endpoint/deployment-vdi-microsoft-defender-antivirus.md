---
title: Microsoft Defender ウイルス対策仮想デスクトップ インフラストラクチャ展開ガイド
description: 保護とパフォーマンスの最適なバランスを保つには、仮想デスクトップ環境に Microsoft Defender ウイルス対策を展開する方法について説明します。
keywords: vdi、hyper-v、vm、仮想マシン、Windows Defender、ウイルス対策、av、仮想デスクトップ、rds、リモート デスクトップ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: fed66586dc0607989e407ecd790d2af8c40e2939
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765733"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

標準のオンプレミスまたはハードウェア構成に加えて、リモート デスクトップ (RDS) または仮想デスクトップ インフラストラクチャ (VDI) 環境でも Microsoft Defender Antivirus を使用できます。

[Microsoft リモート デスクトップ サービスと](/azure/virtual-desktop)VDI のサポートの詳細については、「Windows Virtual Desktop のドキュメント」を参照してください。

Azure ベースの仮想マシンについては [、「Install Endpoint Protection in Azure Defender」を参照してください](/azure/security-center/security-center-install-endpoint-protection)。

VDIs で実行されている VM に更新プログラムを簡単に展開する機能により、このガイドを短縮して、コンピューターの更新プログラムをすばやく簡単に取得する方法に焦点を当ててください。 更新プログラムはホスト サーバー上のコンポーネント ビットに展開され、有効になったときに VM に直接ダウンロードされるので、定期的にゴールデン イメージを作成してシールする必要がなくなりました。

このガイドでは、最適な保護とパフォーマンスを実現するために VM を構成する方法について説明します。これには、次の方法が含まれています。

- [セキュリティ インテリジェンス更新プログラム用に専用の VDI ファイル共有をセットアップする](#set-up-a-dedicated-vdi-file-share)
- [スケジュールされたスキャンをランダム化する](#randomize-scheduled-scans)
- [クイック スキャンの使用](#use-quick-scans)
- [通知を防止する](#prevent-notifications)
- [更新後にスキャンを無効にする](#disable-scans-after-an-update)
- [しばらくオフラインだった古いコンピューターまたはコンピューターをスキャンする](#scan-vms-that-have-been-offline)
- [除外を適用する](#exclusions)

また、新しい共有セキュリティ インテリジェンス更新機能を参照する仮想デスクトップ インフラストラクチャ上のホワイトペーパー [Microsoft Defender Antivirus](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)をダウンロードし、独自の VDI でウイルス対策のパフォーマンスをテストする方法に関するパフォーマンス テストとガイダンスを参照できます。

> [!IMPORTANT]
> VDI は Windows Server 2012 または Windows Server 2016 でホストすることができますが、以前のバージョンの Windows では使用できない保護テクノロジと機能が強化されたので、仮想マシン (VM) は少なくとも Windows 10、1607 を実行している必要があります。<br/>Windows 10 Insider Preview の仮想マシンで Microsoft Defender AV が動作する方法には、パフォーマンスと機能の改善点があります。ビルド 18323 (以降)。 Insider Preview ビルドを使用する必要がある場合は、このガイドで確認します。指定されていない場合、最適な保護とパフォーマンスを実現するために必要な最小バージョンは Windows 10 1607 です。

## <a name="set-up-a-dedicated-vdi-file-share"></a>専用の VDI ファイル共有をセットアップする

Windows 10 バージョン 1903 では、共有セキュリティ インテリジェンス機能が導入され、ダウンロードしたセキュリティ インテリジェンス更新プログラムのアンパック処理がホスト コンピューターにオフロードされ、以前の CPU、ディスク、メモリ リソースが個々のコンピューターに保存されました。 この機能はバックポートされ、Windows 10 バージョン 1703 以上で動作します。 この機能は、グループ ポリシーまたは PowerShell で設定できます。

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>グループ ポリシーを使用して、共有セキュリティ インテリジェンス機能を有効にします。

1. グループ ポリシー管理コンピューターで、グループ ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを Windows コンポーネントの Microsoft Defender ウイルス **対策**  >  **セキュリティ**  >  **インテリジェンス更新プログラムに展開します**。

5. [VDI クライアント **のセキュリティ インテリジェンスの場所** を定義する] をダブルクリックし、オプションを [有効] に **設定します**。 フィールドが自動的に表示されます。

6. Enter `\\<sharedlocation\>\wdav-update` (この値のヘルプについては、「ダウンロードとアンパック [」を参照してください](#download-and-unpackage-the-latest-updates))。

7. **[OK]** をクリックします。

8. テストする VM に GPO を展開します。

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>PowerShell を使用して共有セキュリティ インテリジェンス機能を有効にする

この機能を有効にするには、次のコマンドレットを使用します。 通常、PowerShell ベースの構成ポリシーを VM にプッシュする場合は、これをプッシュする必要があります。

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

詳細については [、「ダウンロードとアンパック](#download-and-unpackage-the-latest-updates) 」セクション \<shared location\> を参照してください。

## <a name="download-and-unpackage-the-latest-updates"></a>最新の更新プログラムをダウンロードして開梱する

これで、新しい更新プログラムのダウンロードとインストールを開始できます。 以下に、サンプルの PowerShell スクリプトを作成しました。 このスクリプトは、新しい更新プログラムをダウンロードして VM の準備を整える最も簡単な方法です。 その後、スケジュールされたタスクを使用して管理マシン上で一定の時間に実行するようにスクリプトを設定する必要があります (または、Azure、Intune、または SCCM で PowerShell スクリプトを使用する場合は、これらのスクリプトを使用することもできます)。

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

スケジュールされたタスクを 1 日 1 回実行して、パッケージをダウンロードして開梱するたびに VM が新しい更新プログラムを受け取るのを設定できます。 1 日 1 回から始める方法をお勧めしますが、影響を理解するために頻度を増やしたり減らしたりして試す必要があります。 

通常、セキュリティ インテリジェンス パッケージは 3 ~ 4 時間に 1 回発行されます。 頻度を 4 時間より短く設定すると、管理マシンのネットワーク オーバーヘッドが増加し、利益が得らないのでお勧めしません。

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>PowerShell スクリプトを実行するスケジュールされたタスクを設定する

1. 管理マシンで、[スタート] メニューを開き、[タスク スケジューラ] **と入力します**。 それを開き、[タスクの **作成...] を選択します。** をサイド パネルに表示します。

2. 名前をセキュリティ インテリジェンス **アンパックとして入力します**。 [トリガー] タブ **に移動** します。[ **新規...] を選択します。** > **[日**] を選択し **、[OK] を選択します**。

3. [操作] タブ **に移動** します。[ **新規...] を選択します。** [ **プログラム/スクリプト]** フィールドに **「PowerShell」と入力** します。 [ `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` 引数の追加 **] フィールドに入力** します。 **[OK]** を選択します。

4. 必要に応じて、追加の設定を構成できます。

5. **[OK] を** 選択して、スケジュールされたタスクを保存します。
 
タスクを右クリックして [実行] をクリックすると、手動で更新を開始 **できます**。

### <a name="download-and-unpackage-manually"></a>手動でダウンロードして開梱する

すべてを手動で実行する場合は、スクリプトの動作をレプリケートするために実行する操作を次に示します。

1. インテリジェンス更新プログラムを格納するために呼び出されるシステム ルートに新しいフォルダーを作成します。たとえば、 `wdav_update` フォルダーを作成します `c:\wdav_update` 。

2. GUID 名を *持つ* wdav_updateサブフォルダーを作成します。 `{00000000-0000-0000-0000-000000000000}`

例を次に示します。 `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > スクリプトでは、GUID の最後の 12 桁が、ファイルがダウンロードされた年、月、日、および時刻として設定し、その度に新しいフォルダーが作成されます。 これを変更して、ファイルを同じフォルダーにダウンロードできます。

3. セキュリティ インテリジェンス パッケージを [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  GUID フォルダーにダウンロードします。 ファイルの名前を指定する必要があります `mpam-fe.exe` 。

4. cmd プロンプト ウィンドウを開き、作成した GUID フォルダーに移動します。 **/X 抽出コマンドを** 使用して、たとえばファイルを抽出します `mpam-fe.exe /X` 。

   > [!NOTE]
   > VM は、抽出された更新パッケージを使用して新しい GUID フォルダーが作成されるたびに、または既存のフォルダーが新しい抽出されたパッケージで更新されるたびに、更新されたパッケージを取得します。

## <a name="randomize-scheduled-scans"></a>スケジュールされたスキャンをランダム化する

スケジュールされたスキャンは、リアルタイムの保護 [とスキャンに加えて実行されます](configure-real-time-protection-microsoft-defender-antivirus.md)。

スキャン自体の開始時刻は、スケジュールされたスキャン ポリシー **(ScheduleDay、ScheduleTime、****および** **ScheduleQuickScanTime) に基づいて引き続き実行されます**。 ランダム化によって、Microsoft Defender Antivirus は、スケジュールされたスキャンに設定された時間から 4 時間以内に各コンピューターでスキャンを開始します。

「スケジュール [されたスキャンで](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 使用できるその他の構成オプションについては、スキャンをスケジュールする」を参照してください。

## <a name="use-quick-scans"></a>クイック スキャンの使用

スケジュールされたスキャン中に実行するスキャンの種類を指定できます。 クイック スキャンは、マルウェアをアクティブにする必要があるすべての場所を検索するように設計された、優先的な方法です。 次の手順では、グループ ポリシーを使用してクイック スキャンを設定する方法について説明します。

1. グループ ポリシー エディターで、[管理用テンプレート] Windows **コンポーネント**  >    >  **[Microsoft Defender ウイルス対策スキャン] に**  >  **移動します**。

2. [ **スケジュールされたスキャンに使用するスキャンの種類を指定する] を選択** し、ポリシー設定を編集します。

3. ポリシーを [有効] **に設定し**、[オプション] で **[クイック** スキャン]  **を選択します**。

4. **[OK]** を選択します。 

5. グループ ポリシー オブジェクトは、通常と同じ方法で展開します。

## <a name="prevent-notifications"></a>通知を防止する

Microsoft Defender ウイルス対策通知が複数のセッションに送信または保持される場合があります。 この問題を最小限に抑えるために、Microsoft Defender ウイルス対策ユーザー インターフェイスをロックダウンできます。 次の手順では、グループ ポリシーを使用して通知を抑制する方法について説明します。

1. グループ ポリシー エディターで **、[Windows** コンポーネント]  >  **[Microsoft Defender ウイルス対策クライアント** インターフェイス]  >  **に移動します**。

2. [すべての **通知を非表示にする] を** 選択し、ポリシー設定を編集します。 

3. ポリシーを [有効]**に設定し****、[OK] を選択します**。

4. グループ ポリシー オブジェクトは、通常と同じ方法で展開します。

通知を抑制すると、スキャンが行われたり、修復アクションが実行された場合、Microsoft Defender Antivirus からの通知が Windows 10 のアクション センターに表示されません。 ただし、セキュリティ運用チームは、スキャンの結果を Microsoft Defender セキュリティ センター () に表示します [https://securitycenter.windows.com](https://securitycenter.windows.com) 。

> [!TIP]
> Windows 10 でアクション センターを開く場合は、次のいずれかの手順を実行します。
> - タスク バーの右側にある [アクション センター] アイコンを選択します。
> - Windows ロゴ キー ボタン + A を押します。
> - タッチスクリーン デバイスで、画面の右端からスワイプします。

## <a name="disable-scans-after-an-update"></a>更新後にスキャンを無効にする

更新後にスキャンを無効にすると、更新プログラムを受信した後にスキャンが発生しなくなります。 クイック スキャンも実行している場合は、基本イメージの作成時にこの設定を適用できます。 これにより、新しく更新された VM がスキャンを再度実行し(ベース イメージの作成時に既にスキャン済み) のを防ぐことが可能です。

> [!IMPORTANT]
> 更新後にスキャンを実行すると、最新のセキュリティ インテリジェンス更新プログラムで VM が保護されます。 このオプションを無効にすると、VM の保護レベルが低下し、基本イメージを最初に作成または展開するときにのみ使用する必要があります。

1. グループ ポリシー エディターで **、[Windows** コンポーネント]  >  **[Microsoft Defender ウイルス対策セキュリティ** インテリジェンス更新プログラム  >  **] に移動します**。

2. [ **セキュリティ インテリジェンスの更新後にスキャンを有効にする] を選択** し、ポリシー設定を編集します。

3. ポリシーを [無効] に **設定します**。

4. **[OK]** を選択します。

5. グループ ポリシー オブジェクトは、通常と同じ方法で展開します。

このポリシーは、更新後すぐにスキャンが実行されるのを防ぐためです。

## <a name="scan-vms-that-have-been-offline"></a>オフラインの VM をスキャンする

1. グループ ポリシー エディターで **、[Windows コンポーネント] [Microsoft** Defender ウイルス対策スキャン]  >  **に**  >  **移動します**。

2. [ **キャッチアップ クイック スキャンを有効にする] を選択** し、ポリシー設定を編集します。

3. ポリシーを [有効] に **設定します**。

4. **[OK]** を選択します。

5. 通常と同じ方法でグループ ポリシー オブジェクトを展開します。

このポリシーは、VM が 2 つ以上の連続したスケジュールされたスキャンを見逃した場合にスキャンを強制的に実行します。

## <a name="enable-headless-ui-mode"></a>ヘッドレス UI モードを有効にする

1. グループ ポリシー エディターで **、[Windows** コンポーネント]  >  **[Microsoft Defender ウイルス対策クライアント** インターフェイス]  >  **に移動します**。

2. [ヘッド **レス UI モードを有効にする] を選択** し、ポリシーを編集します。

3. ポリシーを [有効] に **設定します**。

4. **[OK]** をクリックします。

5. 通常と同じ方法でグループ ポリシー オブジェクトを展開します。
 
このポリシーは、組織内のエンド ユーザーから Microsoft Defender ウイルス対策ユーザー インターフェイス全体を非表示にします。

## <a name="exclusions"></a>除外

除外は、ニーズに合わせて追加、削除、またはカスタマイズできます。

詳細については [、「Windows Server で Microsoft Defender ウイルス対策の除外を構成する」を参照してください](configure-exclusions-microsoft-defender-antivirus.md)。

## <a name="additional-resources"></a>その他のリソース

- [Tech Community Blog: 非永続的な VDI マシン用の Microsoft Defender ウイルス対策の構成](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [リモート デスクトップ サービスと VDI の TechNet フォーラム](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell スクリプト](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)