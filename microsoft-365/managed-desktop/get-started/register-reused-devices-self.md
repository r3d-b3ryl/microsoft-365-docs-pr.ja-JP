---
title: 既存のデバイスをj自分で登録する
description: 再利用されたデバイスを登録します。これにより、Microsoft マネージドデスクトップで管理できるようになります。
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 6c241894ab50b6b1341b06f47c107c8945fb6e8c
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104572"
---
# <a name="register-existing-devices-yourself"></a>既存のデバイスをj自分で登録する

>[!NOTE]
>このトピックでは、既に所有しているデバイスを再利用して、Microsoft マネージドデスクトップで登録する手順について説明します。 新しいデバイスを使用している場合は、代わりに「 [Microsoft Managed Desktop で新しいデバイスを登録](register-devices-self.md) する」の手順に従います。

パートナーのプロセスは、パートナーが [デバイスを登録する手順](register-devices-partner.md)に記載されています。

Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。 Microsoft マネージドデスクトップにデバイスを登録するには、Microsoft エンドポイントマネージャーポータルを使用します。

## <a name="prepare-to-register-existing-devices"></a>既存のデバイスを登録するための準備


既存のデバイスを登録するには、次の手順を実行します。

1. [各デバイスのハードウェアハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュデータを結合する](#merge-hash-data)
3. [Microsoft マネージドデスクトップにデバイスを登録](#register-devices-by-using-the-admin-portal)します。
4. [画像が正しいことをもう一度確認してください。](#check-the-image)
5. [デバイスを配信する](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>ハードウェアハッシュを取得する

Microsoft マネージドデスクトップは、ハードウェアハッシュを参照して各デバイスを一意に識別します。 既に使用しているデバイスからこの情報を取得するには、次の4つのオプションがあります。

- ハードウェアハッシュを含む自動操縦登録ファイルについては、OEM サプライヤーにお問い合わせください。
- [Microsoft エンドポイント構成マネージャー](#microsoft-endpoint-configuration-manager)で情報を収集します。
- [Active Directory](#active-directory-powershell-script-method)を使用するか、または各デバイスで[手動](#manual-powershell-script-method)で Windows PowerShell スクリプトを実行して、ファイルに結果を収集します。
- 各デバイスを開始しますが、Windows セットアップの動作を完了せず [に、リムーバブルフラッシュドライブでハッシュを収集](#flash-drive-method)します。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Microsoft エンドポイント構成マネージャーを使用して、Microsoft マネージドデスクトップに登録する既存のデバイスからハードウェアハッシュを収集できます。

> [!IMPORTANT]
> この情報を取得するデバイスには、Windows 10、バージョン1703以降が実行されている必要があります。 

これらの前提条件をすべて満たしている場合は、次の手順を実行して情報を収集する準備ができています。

1. 構成マネージャーコンソールで、[ **監視**] を選択します。 
2. [監視] ワークスペースで、[ **レポート** ] ノードを展開し、[ **レポート**] を展開して、[ **ハードウェア-全般** ] ノードを選択します。 
3. レポート、 **Windows 自動操縦デバイス情報**を実行し、結果を表示します。
4. レポートビューアーで [ **エクスポート** ] アイコンを選択し、[ **CSV (コンマ区切り)** ] オプションを選択します。
5. ファイルを保存した後で、Microsoft マネージドデスクトップに登録する予定のデバイスのみに結果をフィルター処理し、Microsoft マネージドデスクトップにデータをアップロードする必要があります。 Microsoft エンドポイントマネージャーを開き、[ **デバイス** ] メニューに移動して、[Microsoft Managed Desktop] セクションを探し、[ **デバイス**] を選択します。 [ **+ Register devices** ] を選択して、新しいデバイスを登録するためのフライインを開きます。


詳細については [、「管理者ポータルを使用してデバイスを登録](#register-devices-by-using-the-admin-portal) する」を参照してください。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell スクリプトメソッド

Active Directory 環境では、PowerShell コマンドレットを使用して、 `Get-WindowsAutoPilotInfo` WinRM を使用して Active Directory グループ内のデバイスから情報をリモートで収集できます。 また、この `Get-AD Computer` コマンドレットを使用して、カタログに含まれている特定のハードウェアモデル名のフィルター結果を取得することもできます。 これを行うには、まずこれらの前提条件を確認してから、次の手順に進みます。

- WinRM は有効になっています。
- 登録するデバイスがネットワーク上でアクティブになっている (つまり、切断されていないかオフになっている)。
- デバイス上でリモートで実行するためのアクセス許可を持つ domain credential パラメーターがあることを確認してください。
- Windows ファイアウォールが WMI へのアクセスを許可していることを確認します。 そのためには、次の手順を実行します。

    1. **Windows Defender ファイアウォール**コントロールパネルを開き、[ **Windows defender ファイアウォール経由でアプリまたは機能を許可**する] を選択します。
    
    2. 一覧で [ **Windows Management Instrumentation (WMI)** ] を見つけ、[ **プライベートとパブリック**] の両方で有効にして、[ **OK]** を選択します。

1.  管理者権限を持つ PowerShell プロンプトを開きます。

2.  次 *のいずれかのスクリプトを実行* します。

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. デバイスのエントリが存在する可能性があるディレクトリにアクセスします。 Windows Server Active Directory ドメインサービスと Azure Active Directory を含む、 *すべて* のディレクトリから各デバイスのエントリを削除します。 この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。

4. デバイスのエントリが存在する可能性があるアクセス管理サービス。 Microsoft エンドポイント構成マネージャー、Microsoft Intune、Windows 自動操縦など、 *すべて* の管理サービスから各デバイスのエントリを削除します。 この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。

これで、デバイスの [登録](#register-devices-by-using-the-admin-portal)に進むことができます。

#### <a name="manual-powershell-script-method"></a>PowerShell スクリプトの手動メソッド

1.  管理者権限を持つ PowerShell プロンプトを開きます。
2.  `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3.  `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4. [ハッシュデータを結合します。](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash drive メソッド

1. 登録している以外のデバイスに USB ドライブを挿入します。
2. 管理者権限を持つ PowerShell プロンプトを開きます。
3. `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。
4. 登録するデバイスを有効にしますが、 *セットアップの操作は開始*しないでください。 セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。
5. USB ドライブを挿入して、SHIFT + F10 キーを押します。
6. 管理者権限で PowerShell プロンプトを開き、を実行し `cd <pathToUsb>` ます。
7. `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。
8. `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
9. USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。 `shutdown -s -t 0`
10. [ハッシュデータを結合します。](#merge-hash-data)

>[!IMPORTANT]
>登録が完了するまでは、デバイスの電源を入れないでください。 



### <a name="merge-hash-data"></a>ハッシュデータを結合する

手動の PowerShell または flash drive メソッドによってハードウェアハッシュデータを収集した場合は、CSV ファイル内のデータを1つのファイルにまとめて登録を完了する必要があります。 これを簡単にするためのサンプル PowerShell スクリプトを次に示します。

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

ハッシュデータを1つの CSV ファイルに結合すると、 [デバイスの登録](#register-devices-by-using-the-admin-portal)に進むことができるようになります。


#### <a name="register-devices-by-using-the-admin-portal"></a>管理ポータルを使用してデバイスを登録する

[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)で、左側のナビゲーションウィンドウの [**デバイス**] を選択します。 メニューの [Microsoft Managed Desktop] セクションを探し、[ **デバイス**] を選択します。 [Microsoft Managed Desktop Devices] ワークスペースで、[ **+ デバイスの登録** ] を選択して、新しいデバイスを登録するためのフライインを開きます。

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


次の手順を実行します。

1. [ **ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。

1. [ **デバイスの登録**] を選択します。 デバイスは、 **AutopilotRegistrationRequested**としてマークされているデバイス**ブレード**上のデバイスの一覧に追加されます。 通常、登録にかかる時間は10分未満で、成功した場合、デバイスは **ユーザーのための** 準備完了として表示され、ユーザーが使用を開始するのを待っています。


メインページでのデバイス登録の進行状況を監視できます。 報告される状態は次のとおりです。

| State | 説明 |
|---------------|-------------|
| AutopilotRegistrationRequested | 登録はまだ行われていません。 後でもう一度確認してください。 |
| 登録の失敗 | 登録を完了できませんでした。 詳細については、「 [device registration のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。 |
| ユーザーの準備完了 | 登録が成功し、デバイスをユーザーに配信する準備ができました。 Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。 |
| Active | デバイスはユーザーに配信され、テナントに登録されています。 これは、デバイスを定期的に使用していることも示しています。 |
| 未使用 | デバイスはユーザーに配信され、テナントに登録されています。 しかし、最近7日間ではデバイスを使用していません。  | 

#### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
|---------------|-------------|
| デバイスが見つかりません | 提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。 これらの値は、デバイスの提供元に確認してください。 |
| ハードウェアハッシュが無効です | このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。 ハードウェアハッシュをもう一度確認してから再送信します。 |
| デバイスは既に登録されています | このデバイスは既に組織に登録されています。 その他のアクションは必要ありません。 |
| 別の組織によって要求されるデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスサプライヤーに確認します。 |
| 予期しないエラーです | 要求は自動的に処理されませんでした。 サポートに連絡して、要求 ID を提供します。 <requestId> |

### <a name="check-the-image"></a>画像を確認する

デバイスが Microsoft マネージドデスクトップパートナーのサプライヤーからのものである場合は、イメージが正しいことを確認してください。

また、必要に応じて、自分で画像を適用することも歓迎しています。 開始するには、作業している Microsoft の担当者に連絡して、イメージを適用するための場所と手順を提供します。

### <a name="deliver-the-device"></a>デバイスを配信する

> [!IMPORTANT]
> ユーザーにデバイスを渡す前に、そのユーザーの [適切なライセンス](../get-ready/prerequisites.md) を取得して適用していることを確認してください。

すべてのライセンスが適用されている場合は、 [デバイスを使用する準備](get-started-devices.md)ができたら、ユーザーはデバイスを起動して、Windows セットアップ操作を続行することができます。









