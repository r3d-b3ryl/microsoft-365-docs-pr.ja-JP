---
title: 既存のデバイスをj自分で登録する
description: 再利用されたデバイスを登録します。これにより、Microsoft マネージドデスクトップで管理できるようになります。
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101487"
---
# <a name="register-existing-devices-yourself"></a>既存のデバイスをj自分で登録する

>[!NOTE]
>このトピックでは、既に所有しているデバイスを再利用して、Microsoft マネージドデスクトップで登録する手順について説明します。 新しいデバイスを使用している場合は、代わりに「 [Microsoft Managed Desktop で新しいデバイスを登録](register-devices-self.md)する」の手順に従います。

パートナーのプロセスは、パートナーが[デバイスを登録する手順](register-devices-partner.md)に記載されています。

Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。 Microsoft Managed Desktop 管理ポータルを使用してデバイスを登録できます。

## <a name="prepare-to-register-existing-devices"></a>既存のデバイスを登録するための準備


既存のデバイスを登録するには、次の手順を実行します。

1. [各デバイスのハードウェアハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュデータを結合する](#merge-hash-data)
3. [Microsoft マネージドデスクトップにデバイスを登録](#register-devices)します。
4. [画像が正しいことをもう一度確認してください。](#check-the-image)
5. [デバイスを配信する](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>ハードウェアハッシュを取得する

Microsoft マネージドデスクトップは、ハードウェアハッシュを参照して各デバイスを一意に識別します。 既に使用しているデバイスからこの情報を取得するには、次の4つのオプションがあります。

- ハードウェアハッシュを含む自動操縦登録ファイルについては、OEM サプライヤーにお問い合わせください。
- [構成マネージャー](#configuration-manager)でカスタムレポートを作成します。
- [Active Directory](#active-directory-powershell-script-method)を使用するか、または各デバイスで[手動](#manual-powershell-script-method)で Windows PowerShell スクリプトを実行して、ファイルに結果を収集します。
- 各デバイスを開始しますが、Windows セットアップの動作を完了せず[に、リムーバブルフラッシュドライブでハッシュを収集](#flash-drive-method)します。

#### <a name="configuration-manager"></a>Configuration Manager

Microsoft エンドポイント構成マネージャーを使用して、Microsoft マネージドデスクトップに登録する既存のデバイスからハードウェアハッシュを収集できます。

> [!IMPORTANT]
> この情報を取得するデバイスには、Windows 10、バージョン1703以降が実行されている必要があります。 構成マネージャー (Current Branch) サイトに接続されている構成マネージャークライアントのデバイスも必要です。 また、SQL Server Reporting Services が有効になっている環境で、レポートポイントサイトシステムの役割が設定されている必要もあります。 

これらの前提条件をすべて満たしている場合は、次の手順を実行して情報を収集する準備ができています。

1. 構成マネージャーコンソールで、[**監視**] を選択します。 
2. [監視] ワークスペースで、[**レポート**] を展開し、[**レポート**] を選択します。 
3. [**ホーム**] タブの [**作成**] セクションで、[**レポート**の作成] を選択して、レポートの作成ウィザードを開きます。 
4. [**情報**] ページで、次の設定を行います。 
    - **Name:** レポートの名前を指定します。 
    - **説明:** レポートの説明を指定します。 
    - **サーバー:** このレポートを作成するレポートサーバーの名前を表示します。 
    - **パス:**[**参照**] を選択して、レポートを保存するフォルダーを指定します。 
5. **[次へ]** を選択します。 
6. [**概要**] ページで、設定を確認します。 [**前**へ] を選択して設定を変更するか、[**次へ**] を選択して、構成マネージャーでレポートを作成します。 
7. [**完了**] ページで、[**閉じる**] を選択してウィザードを終了し、レポート**ビルダー**を開いてレポート設定を入力します。 メッセージが表示されたら、ユーザーアカウントとパスワードを入力し、[OK] を選択し**ます。** レポートビルダーがデバイスにインストールされていない場合は、インストールするように求めるメッセージが表示されます。 レポートを変更および作成するために必要な**レポートビルダーをインストールするに**は、[実行] を選択します。 


**Microsoft レポートビルダーで**、レポート用の SQL ステートメントを入力し、次の手順を実行します。

1. 左側のウィンドウで、[**データセット**] を選択し、右クリックして**データセットを追加**します。
2. [**クエリ**] タブに移動し、 *DataSet0*という名前を入力します。 
3. [**レポートに埋め込まれたデータセットを使用する**] を選択します。レポートビルダーが開きます。
4. **レポートビルダー**で、[**データソース:**] を選択します。 "AutoGen" で始まる既定のデータソースを選択します。 
5. [**クエリの種類**] をテキストとして選択し、次のクエリを入力します。




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. [**フィールド**] タブに移動します。**フィールド名**と**フィールドソース**の値は既に入力されています。 入力されていない場合は、[**追加**] を選択し、[**クエリフィールド**] を選択します。 **フィールド名**と**フィールドソース**を入力します。
6. 次の各値に対して、次の手順を繰り返します。 
    - 製造 
    - モデル 
    - Serial_Number 
    - ハードウェアハッシュ
7. [**OK**] を選択します。

**次に、** 次の手順に従ってレポートの表示を定義し、レポートを作成します。

1. **テーブルまたはマトリックス**を選択します。新しいウィザードが開きます。
2. [**データセットの選択**] で、[**このレポート内の既存のデータセットを選択する] または [共有データセット**] を選択します。  
3. **DataSet0** (既定値) を選択し、[**次へ**] を選択します。
4. [**製造元**]、[**モデル**]、および [**シリアル番号**] を [**行グループ**] ボックスにドラッグします。 [**ハードウェアハッシュ**] を [**値**] ボックスにドラッグし、[**次へ**] を選択します。
5. [**小計と総計を表示する]** と [**グループを展開/折りたたみ**する] のチェックボックスをオフにします。 **[次へ]** を選択します。
6. **[完了]** を選択します。
7. [**実行**] を選択してレポートを実行します。 レポートが期待する情報を提供していることを確認します。 必要に応じて、[**デザイン**] を選択して、レポートを変更するためのデザインビューに戻ります。
8. レポートをレポートサーバーに保存するには、[**保存**] を選択します。 [監視ワークスペースのレポートノードで新しいレポートを実行できます。 

**最後に、** 次の手順に従ってレポートをエクスポートし、それを使用してデバイスを登録します。 (前の手順の後に移動した場合は、このセクションの手順1と2に従う必要があります)。

1. 構成マネージャーコンソールで、[**監視**] を選択します。
2. [**監視**] で、[**レポート**] を展開し、[**レポート**] を選択します。
3. 前に作成した名前を使用してレポートを検索します。
4. このレポートを右クリックし、[**実行**] を選択します。
5. 開いたダイアログで、[**エクスポート**] を選択し、[ **CSV として保存**] を選択します。
6. このバージョンのレポートは、構成マネージャーが通信するすべての Windows 10 デバイスからハッシュを抽出します。 Microsoft マネージドデスクトップに登録する予定のデバイスのみに結果をフィルター処理する必要があります。


> [!IMPORTANT]
> 構成マネージャーのクエリは、エクスポートされた列名にスペースを使用できません。そのため、手順で「Serial_Number」と「ハードウェアハッシュ」と入力する必要があります。 エクスポートされた CSV ファイルがあるので、デバイスの登録を続行する前に、ここに示すようにレポートヘッダーを編集して*シリアル番号*と*ハードウェアハッシュ*を読み取る必要があります。

これで[、管理ポータルを使用してデバイスを登録](#register-devices-by-using-the-admin-portal)する手順に進むことができます。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell スクリプトメソッド

Active Directory 環境では、PowerShell コマンドレットを使用して、 `Get-MMDRegistrationInfo` WinRM を使用して Active Directory グループ内のデバイスから情報をリモートで収集できます。 また、この `Get-AD Computer` コマンドレットを使用して、カタログに含まれている特定のハードウェアモデル名のフィルター結果を取得することもできます。 これを行うには、まずこれらの前提条件を確認してから、次の手順に進みます。

- WinRM は有効になっています。
- 登録するデバイスがネットワーク上でアクティブになっている (つまり、切断されていないかオフになっている)。
- デバイス上でリモートで実行するためのアクセス許可を持つ domain credential パラメーターがあることを確認してください。
- Windows ファイアウォールが WMI へのアクセスを許可していることを確認します。 そのためには、次の手順を実行します。
    1. **Windows Defender ファイアウォール**コントロールパネルを開き、[ **Windows defender ファイアウォール経由でアプリまたは機能を許可**する] を選択します。
    2. 一覧で [ **Windows Management Instrumentation (WMI)** ] を見つけ、[**プライベートとパブリック**] の両方で有効にして、[ **OK]** を選択します。

1.  管理者権限を持つ PowerShell プロンプトを開きます。
2.  次*のいずれかのスクリプトを実行*します。
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. デバイスのエントリが存在する可能性があるディレクトリにアクセスします。 Windows Server Active Directory ドメインサービスと Azure Active Directory を含む、*すべて*のディレクトリから各デバイスのエントリを削除します。 この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。
4. デバイスのエントリが存在する可能性があるアクセス管理サービス。 Microsoft エンドポイント構成マネージャー、Microsoft Intune、Windows 自動操縦など、*すべて*の管理サービスから各デバイスのエントリを削除します。 この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。

これで、デバイスの[登録](#register-devices)に進むことができます。

#### <a name="manual-powershell-script-method"></a>PowerShell スクリプトの手動メソッド

1.  管理者権限を持つ PowerShell プロンプトを開きます。
2.  `Install-Script -Name Get-MMDRegistrationInfo` を実行します。
3.  `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4. [ハッシュデータを結合します。](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash drive メソッド

1. 登録している以外のデバイスに USB ドライブを挿入します。
2. 管理者権限を持つ PowerShell プロンプトを開きます。
3. `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>` を実行します。
4. 登録するデバイスを有効にしますが、*セットアップの操作は開始*しないでください。 セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。
5. USB ドライブを挿入して、SHIFT + F10 キーを押します。
6. 管理者権限で PowerShell プロンプトを開き、を実行し `cd <pathToUsb>` ます。
7. `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。
8. `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。
9. USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。`shutdown -s -t 0`
10. [ハッシュデータを結合します。](#merge-hash-data)

>[!IMPORTANT]
>登録が完了するまでは、デバイスの電源を入れないでください。 



### <a name="merge-hash-data"></a>ハッシュデータを結合する

手動の PowerShell または flash drive メソッドによってハードウェアハッシュデータを収集した場合は、CSV ファイル内のデータを1つのファイルにまとめて登録を完了する必要があります。 これを簡単にするためのサンプル PowerShell スクリプトを次に示します。

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

ハッシュデータを1つの CSV ファイルに結合すると、[デバイスの登録](#register-devices)に進むことができるようになります。

### <a name="register-devices"></a>デバイスを登録する

CSV ファイルは、登録用に特定の形式である必要があります。 前の手順でデータを自分で収集した場合は、ファイルが正しい形式になっている必要があります。業者からファイルを取得する場合は、形式を調整する必要があります。

>[!NOTE]
>便宜上、この CSV ファイルの[テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)をダウンロードすることができます。

ファイルには、サンプル 1 (製造元、モデルなど) と**まったく同じ列見出し**を含める必要がありますが、その他の行については独自のデータを含める必要があります。 テンプレートを使用している場合は、メモ帳などのテキスト編集ツールでそのテンプレートを開き、行1のみにデータを入力し、2行以下にデータを入力することを検討します。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>サンプルデータの変更を忘れると、登録は失敗します。

#### <a name="register-devices-by-using-the-admin-portal"></a>管理ポータルを使用してデバイスを登録する

Microsoft Managed Desktop[管理ポータル](https://aka.ms/mmdportal)で、左側のナビゲーションウィンドウで [**デバイス**] を選択します。 [ **+ デバイスの登録**] を選択します。フライインが開きます。

[![[デバイスの登録] を選択した後のフライイン、割り当てられたユーザーの列が含まれているデバイスを一覧表示する、シリアル番号、状態、最終確認日、および保存期間](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (残念ながら、これは当てはまりません。このメモを削除することはできますが、それについてお客様がチャットできるようになるまで、そのままにしておきます。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


次の手順を実行します。

1. [**ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。
2. 必要に応じて、独自の追跡目的のために、**注文 id**または**購買 id**を追加することもできます。 これらの値に書式の要件はありません。
3. [**デバイスの登録**] を選択します。 システムによってデバイス**ブレード**上のデバイスの一覧にデバイスが追加され、[**登録保留中**] としてマークされます。 通常、登録にかかる時間は10分未満で、成功した場合、デバイスは**ユーザーのための準備**完了として表示され、エンドユーザーが使用を開始するのを待っています。


メインの**Microsoft Managed Desktop-Devices**ページでのデバイス登録の進行状況を監視できます。 報告される状態は次のとおりです。

| State | 説明 |
|---------------|-------------|
| 登録保留中 | 登録はまだ行われていません。 後でもう一度確認してください。 |
| 登録の失敗 | 登録を完了できませんでした。 詳細については、「 [device registration のトラブルシューティング](#troubleshooting-device-registration)」を参照してください。 |
| ユーザーの準備完了 | 登録が成功し、デバイスをエンドユーザーに配信する準備ができました。 Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。 |
| Active | デバイスはエンドユーザーに配信され、テナントに登録されています。 これは、デバイスを定期的に使用していることも示しています。 |
| 未使用 | デバイスはエンドユーザーに配信され、テナントに登録されています。 しかし、最近7日間ではデバイスを使用していません。  | 

#### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
|---------------|-------------|
| デバイスが見つかりません | 提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。 これらの値は、デバイスの提供元に確認してください。 |
| ハードウェアハッシュが無効です | このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。 ハードウェアハッシュをもう一度確認してから再送信します。 |
| デバイスは既に登録されています | このデバイスは既に組織に登録されています。 その他のアクションは必要ありません。 |
| 別の組織によって要求されるデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスサプライヤーに確認します。 |
| 予期しないエラーです | 要求は自動的に処理されませんでした。 サポートに連絡して、要求 ID を提供します。<requestId> |

### <a name="check-the-image"></a>画像を確認する

デバイスが Microsoft マネージドデスクトップパートナーのサプライヤーからのものである場合は、イメージが正しいことを確認してください。

また、必要に応じて、自分で画像を適用することも歓迎しています。 開始するには、作業している Microsoft の担当者に連絡して、イメージを適用するための場所と手順を提供します。

### <a name="deliver-the-device"></a>デバイスを配信する

> [!IMPORTANT]
> ユーザーにデバイスを渡す前に、そのユーザーの[適切なライセンス](../get-ready/prerequisites.md)を取得して適用していることを確認してください。

すべてのライセンスが適用されている場合は、[デバイスを使用する準備](get-started-devices.md)ができたら、ユーザーはデバイスを起動して、Windows セットアップ操作を続行することができます。









