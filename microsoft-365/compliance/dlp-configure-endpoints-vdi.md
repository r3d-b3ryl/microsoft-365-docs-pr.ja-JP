---
title: オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 仮想デスクトップインフラストラクチャ (VDI) デバイスに構成パッケージを展開して、それらが Microsoft 365 エンドポイントのデータ損失防止サービスに利用されるようにします。
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769452"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス

**適用対象:**
- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

- 仮想デスクトップインフラストラクチャ (VDI) デバイス

>[!WARNING]
> Microsoft 365 エンドポイントのデータ損失防止サポート Windows 仮想デスクトップは1つのセッションシナリオをサポートしています。 Windows 仮想デスクトップ上のマルチセッションシナリオは現在サポートされていません。

## <a name="onboard-vdi-devices"></a>オンボード VDI デバイス

Microsoft 365 エンドポイントのデータ損失防止は、非永続的な VDI セッションのオンボードをサポートします。 

>[!Note]
>非永続的な VDI セッションをオンボードにするには、VDI デバイスが Windows 10 1809 以上である必要があります。

オンボード VDIs の場合、課題が関連付けられている可能性があります。 このシナリオの一般的な課題は次のとおりです。

- 短時間セッションの早期の初期処理。これは、実際のプロビジョニング前に Microsoft 365 エンドポイントのデータ損失防止に利用する必要があります。
- デバイス名は、通常、新しいセッションに再利用されます。

VDI デバイスは、次のいずれかの方法で Microsoft 365 コンプライアンスセンターに表示できます。

- デバイスごとに1つのエントリ。  
この場合は、セッションの作成時に、無人応答ファイルを使用するなど、 *同じ* デバイス名を構成する必要があることに注意してください。
- 各デバイスの複数のエントリ。セッションごとに1つ。

次の手順では、オンボード VDI デバイスについて説明し、単一および複数のエントリのステップを強調表示します。

>[!WARNING]
> リソース構成が少ない環境では、VDI のブート手順により、Microsoft 365 エンドポイントのデータ損失防止のオンボードが遅くなる可能性があります。 

1.  サービスオンボードウィザードからダウンロードした VDI 構成パッケージ .zip ファイル ( *DeviceCompliancePackage.zip* ) を開きます。

2.  ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオン** ボードオンボード] を選択し  >  **Onboarding** ます。

3. [ **展開方法** ] フィールドで、 **非永続エンドポイントの VDI オンボードスクリプト** を選択します。

5. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

6. .Zip ファイルから抽出された DeviceCompliancePackage フォルダーからパスの下の画像にファイルをコピーし `golden/master` `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ます。 

7. 各デバイスに対して単一のエントリを実装していない場合は、Devicecompliare On掲示板をコピーします。

8. 各デバイスに対して単一のエントリを実装する場合は、Onboard-NonPersistentMachine.ps1 と Devicecompliare On掲示用の両方をコピーします。
    
    > [!NOTE]
    > フォルダーが表示されていない場合は `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 、非表示になっている可能性があります。 [ファイルエクスプローラー] の [ **非表示のファイルとフォルダーを表示** する] オプションを選択する必要があります。

9. ローカルグループポリシーエディターウィンドウを開き、[ **コンピューターの構成** ]  >  **Windows の設定**  >  **スクリプト** のスタートアップに移動し  >  **Startup** ます。

   > [!NOTE]
   > ドメイングループポリシーは、非永続的な VDI デバイスのオンボードにも使用できます。

4. 実装する方法に応じて、適切な手順を実行します。

   **各デバイスの単一エントリの場合**
   
   [ **PowerShell スクリプト** ] タブを選択し、[ **追加** ] をクリックします (前の手順を実行した後、前の手順で開始した開始位置のパスで、Windows Explorer が直接開きます)。 オンボード PowerShell スクリプトに移動 `Onboard-NonPersistentMachine.ps1` します。
   
   **各デバイスの複数のエントリの場合** :
   
   [ **スクリプト** ] タブを選択し、[ **追加** ] をクリックします (前の手順を実行した後、前の手順で開始したパスで、Windows Explorer が直接開きます)。 オンボード bash スクリプトに移動し `DeviceComplianceOnboardingScript.cmd` ます。

5. ソリューションをテストします。

   1. 1つのデバイスでプールを作成します。
      
   1. デバイスへのログオン。
      
   1. デバイスからログオフします。

   1. 別のユーザーとデバイスにログオンします。
      
   1. **各デバイスの単一エントリの場合** : Microsoft Defender セキュリティセンターの1つのエントリのみをチェックします。<br>
      **各デバイスの複数のエントリについて** : Microsoft Defender セキュリティセンターの複数のエントリをチェックします。

6. ナビゲーションウィンドウの [ **デバイス] リスト** をクリックします。

7. デバイス名を入力して search 関数を使用し、検索の種類として [ **デバイス** ] を選択します。

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>非永続仮想デスクトップインフラストラクチャ (VDI) の画像を更新する
ベストプラクティスとして、オフラインサービスツールを使用してゴールデン/マスタイメージにパッチを適用することをお勧めします。<br>
たとえば、次のコマンドを使用して更新プログラムをインストールし、画像はオフラインのままにしておくことができます。

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

DISM コマンドとオフラインサービスの詳細については、以下の記事を参照してください。
- [DISM を使用して Windows イメージを変更する](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM イメージ管理 Command-Line オプション](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [オフライン Windows イメージのコンポーネントストアのサイズを小さくする](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

オフラインサービスが非永続的な VDI 環境に対して有効なオプションではない場合は、一貫性とセンサーの正常性を確保するために、次の手順を実行する必要があります。

1. オンラインサービスまたはパッチを適用するためにマスターイメージを起動した後、オフボードスクリプトを実行して、Microsoft 365 エンドポイントのデータ損失防止センサーをオフにします。 詳細については、「 [Offboard devices using local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)」を参照してください。

2. CMD ウィンドウで以下のコマンドを実行して、センサーが停止していることを確認します。

   ```console
   sc query sense
   ```

3. 必要に応じて、画像を処理します。

4. PsExec.exe を使用して以下のコマンドを実行します (からダウンロードして、 https://download.sysinternals.com/files/PSTools.zip) センサーがブート後に蓄積したサイバーフォルダーの内容をクリーンアップすることができます)。

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 通常どおり、ゴールデン/マスターイメージを再シールします。

## <a name="related-topics"></a>関連項目
- [グループポリシーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-sccm.md)
- [モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [ローカルスクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
