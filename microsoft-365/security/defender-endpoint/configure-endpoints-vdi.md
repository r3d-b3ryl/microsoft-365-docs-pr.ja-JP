---
title: 非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスに展開して、Microsoft Defender for Endpoint サービスにオンボードします。
keywords: 仮想デスクトップ インフラストラクチャ (VDI) デバイス、vdi、デバイス管理の構成、エンドポイント用 Microsoft Defender の構成、エンドポイント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: d7e4d2d9813081785f3883c11a3a4ae8e8420855
ms.sourcegitcommit: a0452cef05f2322b74967add41fd84ac4d07fe5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2021
ms.locfileid: "58378061"
---
# <a name="onboarding-non-persistent-virtual-desktop-infrastructure-devices"></a>非永続的な仮想デスクトップ インフラストラクチャ デバイスのオンボーディング


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 仮想デスクトップ インフラストラクチャ (VDI) デバイス
- Windows 10、Windows Server 2019、Windows Server 2008R2/2012R2/2016

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード

Defender for Endpoint は、永続的でない VDI セッションオンボーディングをサポートします。 

VDIs をオンボーディングする際に関連する課題が生じ得る場合があります。 このシナリオの一般的な課題は次のとおりです。

- 短命セッションの即時早期オンボーディング。実際のプロビジョニングの前に Defender for Endpoint にオンボードする必要があります。
- 通常、デバイス名は新しいセッションに再利用されます。

VDI デバイスは、Defender for Endpoint ポータルに次のように表示できます。

- デバイスごとに 1 つのエントリ。

  > [!NOTE]
  > この場合、セッションの作成 *時* に、無人応答ファイルを使用する場合など、同じデバイス名を構成する必要があります。

- デバイスごとに複数のエントリ (セッションごとに 1 つ)。

次の手順では、VDI デバイスのオンボードについて説明し、単一エントリと複数エントリの手順を強調表示します。

>[!WARNING]
> リソース構成が低い環境では、VDI ブート手順によって Defender for Endpoint センサーのオンボーディングが遅くなる可能性があります。 


### <a name="for-windows-10-or-windows-server-2019"></a>サーバー Windows 10またはWindowsサーバー 2019 の場合

1.  サービス オンボーディング ウィザードから.zipした VDI *構成パッケージ*(WindowsDefenderATPOnboardingPackage.zip) を開きます。 パッケージは、次のポータルから[Microsoft 365 Defenderすることもできます](https://security.microsoft.com/)。

    1. ナビゲーション ウィンドウで、[エンドポイント **デバイス設定**  >    >  **オンボーディング]**  >  **を選択します**。

    1. オペレーティング システムWindows 10を選択します。

    1.  [展開方法 **] フィールドで** 、[永続的でないエンドポイントの VDI オンボーディング **スクリプト] を選択します**。

    1. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

2. .zip ファイルから抽出された WindowsDefenderATPOnboardingPackage フォルダーから、パスの下にあるゴールデン/マスター イメージにファイルをコピーします `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。 

    1. 各デバイスに複数のエントリ (セッションごとに 1 つ) を実装する場合は、WindowsDefenderATPOnboardingScript.cmd をコピーします。

    1. デバイスごとに 1 つのエントリを実装する場合は、windowsDefenderATPOnboardingScript.cmd と windowsDefenderATPOnboardingScript.cmd の両方Onboard-NonPersistentMachine.ps1コピーします。
    
    > [!NOTE]
    > フォルダーが表示しない場合 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` は、非表示になる可能性があります。 エクスプローラーから [非表示のファイル **とフォルダーを** 表示する] オプションを選択する必要があります。

3. [ローカル グループ ポリシー エディター] ウィンドウを開き、[コンピューター **の構成**] Windows 設定  >    >  **に**  >  **移動します**。

   > [!NOTE]
   > ドメイン グループ ポリシーは、永続的でない VDI デバイスのオンボーディングにも使用できます。

4. 実装するメソッドに応じて、適切な手順に従います。

    - デバイスごとに 1 つのエントリの場合:
   
         **[PowerShell スクリプト]** タブを選択し、[追加] **(Windows** オンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます) をクリックします。 PowerShell スクリプトのオンボーディングに移動します `Onboard-NonPersistentMachine.ps1` 。 他のファイルは自動的にトリガーされますので、指定する必要はありません。
   
    - 各デバイスの複数のエントリの場合:
   
         [スクリプト **] タブを** 選択し、[追加]**をクリック** します (Windows、以前にオンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます)。 オンボーディング bash スクリプトに移動します `WindowsDefenderATPOnboardingScript.cmd` 。

5. ソリューションをテストします。

   1. 1 つのデバイスでプールを作成します。
      
   1. デバイスにログオンします。
      
   1. デバイスからログオフします。

   1. 別のユーザーと一緒にデバイスにログオンします。
      
   1. 実装するメソッドに応じて、適切な手順に従います。

   - デバイスごとに 1 つのエントリの場合: 

     ポータルで 1 つのエントリMicrosoft 365 Defenderします。

   - 各デバイスの複数のエントリの場合: 

     ポータルで複数のエントリMicrosoft 365 Defenderします。


6. [ナビゲーション **] ウィンドウの [** デバイス] リストをクリックします。

7. デバイス名を入力して検索機能を使用し、[検索の種類として **デバイス]** を選択します。


## <a name="for-downlevel-skus-windows-server-2008-r22012-r22016"></a>ダウンレベル SKU の場合 (Windows Server 2008 R2/2012 R2/2016)

> [!NOTE]
> 次のレジストリは、目的が "デバイスごとに 1 つのエントリ" を達成する場合にのみ関連します。

1. レジストリ値を次に設定します。

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    またはコマンド ラインを使用する:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. サーバーのオン [ボーディング プロセスに従います](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>非永続的仮想デスクトップ インフラストラクチャ (VDI) イメージの更新
ベスト プラクティスとして、オフライン サービス ツールを使用してゴールデン/マスター イメージにパッチを適用することをお勧めします。<br>
たとえば、次のコマンドを使用して、イメージがオフラインのままで更新プログラムをインストールできます。

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

DISM コマンドとオフライン サービスの詳細については、以下の記事を参照してください。
- [DISM を使用Windowsイメージを変更する](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM イメージ管理Command-Lineオプション](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [オフライン イメージ内のコンポーネント ストアのサイズを小Windowsする](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

非永続的な VDI 環境でオフライン サービスが実行可能なオプションでない場合は、一貫性とセンサーの正常性を確保するために次の手順を実行する必要があります。

1. オンライン サービスまたは修正プログラムのマスター イメージを起動した後、オフボード スクリプトを実行して Defender for Endpoint センサーをオフにします。 詳細については、「ローカル スクリプトを [使用したオフボード デバイス」を参照してください](configure-endpoints-script.md#offboard-devices-using-a-local-script)。

2. CMD ウィンドウで以下のコマンドを実行して、センサーが停止した状態を確認します。

   ```console
   sc query sense
   ```

3. 必要に応じてイメージをサービスします。

4. 次のコマンドを PsExec.exe を使用して実行します (起動後にセンサーが蓄積した可能性があるサイバー フォルダーの内容をクリーンアップするためにダウンロード https://download.sysinternals.com/files/PSTools.zip) できます。

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 通常と同じ方法で、ゴールデン/マスター イメージを再シールします。

## <a name="related-topics"></a>関連項目
- [グループ ポリシー Windows 10デバイスのオンボード](configure-endpoints-gp.md)
- [デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](configure-endpoints-script.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](troubleshoot-onboarding.md)
