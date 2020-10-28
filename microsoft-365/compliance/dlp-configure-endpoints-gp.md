---
title: グループポリシーを使用した Windows 10 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: グループポリシーを使用して、サービスに利用されるように Windows 10 デバイスに構成パッケージを展開します。
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769447"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>グループポリシーを使用した Windows 10 デバイスのオンボード 

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- グループ ポリシー

> [!NOTE]
> グループポリシー (GP) の更新プログラムを使用してパッケージを展開するには、Windows Server 2008 R2 以降のバージョンである必要があります。

> Windows Server 2019 では、NT AUTHORITY\Well-Known-System-Account を、グループポリシー設定によって作成された XML ファイルの NT AUTHORITY\SYSTEM に置き換える必要がある場合があります。

## <a name="onboard-devices-using-group-policy"></a>グループポリシーを使用しているオンボードデバイス

1. サービスオンボードウィザードからダウンロードした GP 構成パッケージ .zip ファイル ( *DeviceComplianceOnboardingPackage.zip* ) を開きます。 [Microsoft コンプライアンスセンター](https://compliance.microsoft.com/compliancesettings/deviceonboarding)からパッケージを取得することもできます。

2. ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオンボード** ] を選択します。

3. [ **展開方法** ] フィールドで、[ **グループポリシー** ] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. .Zip ファイルの内容を、デバイスからアクセスできる共有の読み取り専用の場所に抽出します。 *OptionalParamsPolicy* という名前のフォルダーと、ファイル *Devicecompliofflocalonbookscript. cmd* が必要です。

6. [グループポリシー管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)(GPMC) を開き、構成するグループポリシーオブジェクト (GPO) を右クリックして、[ **編集** ] をクリックします。

7. **グループポリシー管理エディター** で、[コンピューターの **構成** ]、[ **環境** 設定]、[ **コントロールパネルの設定** ] の順に移動します。

8. [ **タスク** ] を右クリックし、[ **新規** ] をポイントして、[ **即時タスク] (少なくとも Windows 7 以降)** をクリックします。

9. 開いた **タスク** ウィンドウで、 **[全般** ] タブに移動します。[ **セキュリティオプション** ] で、[ **ユーザーまたはグループの変更** ] をクリックし、「SYSTEM」と入力して、[ **名前の確認** ] をクリックし、[ **OK]** [NT AUTHORITY\SYSTEM] は、タスクを実行するユーザーアカウントとして表示されます。

10. [ **ユーザーがログオンしているかどうかにかかわらず実行する** ] を選択し、[ **最上位の特権で実行** する] チェックボックスをオンにします。

11. [ **操作** ] タブに移動し、[ **新規** ] をクリックします。[ **アクション** ] フィールドで [ **プログラムの開始** ] が選択されていることを確認します。 共有されている *WindowsDefenderATPOnboardingScript* ファイルのファイル名と場所を入力します。

12. [ **OK]** をクリックし、開いているすべての GPMC ウィンドウを閉じます。


## <a name="offboard-devices-using-group-policy"></a>グループポリシーを使用したオフボードデバイス
セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。 有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。 オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。

> [!NOTE]
> オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com/compliancesettings/deviceonboarding)からオフボードパッケージを取得します。

2. ナビゲーションウィンドウで、[ **設定** /デバイスのオンボードオフボード] を選択し  >  **//Device onboarding**  >  **Offboarding** ます。

3. [ **展開方法** ] フィールドで、[ **グループポリシー** ] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. .Zip ファイルの内容を、デバイスからアクセスできる共有の読み取り専用の場所に抽出します。 *DeviceComplianceOffboardingScript_valid_until_YYYY* という名前のファイルが必要です。

6. [グループポリシー管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)(GPMC) を開き、構成するグループポリシーオブジェクト (GPO) を右クリックして、[ **編集** ] をクリックします。

7. **グループポリシー管理エディター** で、[コンピューターの **構成]、** [ **環境** 設定]、[ **コントロールパネルの設定** ] の順に移動します。

8. [ **タスク** ] を右クリックし、[ **新規** ] をポイントして、[ **即時タスク** ] をクリックします。

9. 開いた **タスク** ウィンドウで、 **[全般** ] タブに移動します。[ **セキュリティオプション** ] で、[ローカルシステム] ユーザーアカウント (BUILTIN\SYSTEM) を選択します。

10. [ **ユーザーがログオンしているかどうかにかかわらず実行する** ] を選択し、[ **最上位の特権で実行** する] チェックボックスをオンにします。

11. [ **操作** ] タブに移動し、[ **新規** ] をクリックします。[ **アクション** ] フィールドで [ **プログラムの開始** ] が選択されていることを確認します。 共有された  *DeviceComplianceOffboardingScript_valid_until_YYYY* のファイル名と場所を入力します。

12. [ **OK]** をクリックし、開いているすべての GPMC ウィンドウを閉じます。

> [!IMPORTANT]
> オフボードは、デバイスがポータルへのセンサーデータの送信を停止しますが、デバイスからデータを送信します。


## <a name="monitor-device-configuration"></a>デバイス構成の監視
グループポリシーを使用すると、デバイスにポリシーの展開を監視するオプションはありません。 監視は、ポータル上で直接実行することも、さまざまな展開ツールを使用して行うこともできます。

## <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する
1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)に移動します。
2. [ **デバイス** リスト] をクリックします。
3. デバイスが表示されていることを確認します。

> [!NOTE]
> デバイス **リスト** にデバイスが表示されるまでに数日かかる場合があります。 これには、ポリシーがデバイスに配布されるまでの時間、ユーザーがログオンするまでにかかる時間、およびエンドポイントがレポートを開始するのにかかる時間が含まれます。


## <a name="related-topics"></a>関連項目
- [Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-sccm.md)
- [モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [ローカルスクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス](dlp-configure-endpoints-vdi.md)
- [新しく利用 Microsoft Defender ATP デバイスで検出テストを実行する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
