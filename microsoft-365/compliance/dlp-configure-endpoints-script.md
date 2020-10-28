---
title: ローカルスクリプトを使用した Windows 10 デバイスのオンボード
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
description: ローカルスクリプトを使用して、サービスに利用するように構成パッケージをデバイスに展開します。
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769472"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>ローカルスクリプトを使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

個別のデバイスを手動で Microsoft 365 エンドポイントのデータ損失防止にオンボードすることもできます。 ネットワーク内のすべてのデバイスをオンボードにする前に、サービスをテストするときに最初にこの操作を実行することをお勧めします。

> [!IMPORTANT]
> このスクリプトは最大10台のデバイスで使用するように最適化されています。
>
> スケールで展開するには、 [他の展開オプション](dlp-configure-endpoints.md)を使用します。 たとえば、 [グループポリシーを使用して Windows 10 デバイス](dlp-configure-endpoints-gp.md)で使用可能なスクリプトを使用して、オンボードスクリプトを運用環境の10台以上のデバイスに展開することができます。

## <a name="onboard-devices"></a>オンボードデバイス
 
1.  サービスオンボードウィザードからダウンロードした GP 構成パッケージ .zip ファイル ( *DeviceComplianceOnboardingPackage.zip* ) を開きます。 [Microsoft コンプライアンスセンター](https://compliance.microsoft.com)からパッケージを取得することもできます。

2. ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオンボード** ] を選択します。

3. [ **展開方法** ] フィールドで、[ **ローカルスクリプト** ] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。
  
5. 構成パッケージの内容を、展開するデバイス上の場所 (たとえば、デスクトップ) に抽出します。 *Deviceonboardingscript* という名前のファイルが必要です。

6.  デバイス上で管理者特権のコマンドラインプロンプトを開き、次のスクリプトを実行します。

7.  [ **スタート** ] に移動し、「 **cmd** 」と入力します。

8.  [ **コマンドプロンプト** ] を右クリックし、[ **管理者として実行** ] を選択します。

![[管理者として実行] をポイントする [スタート] メニュー](../media/dlp-run-as-admin.png)

9.  スクリプトファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は、次のように入力します。 *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Enter キーを押すか、[ **OK]****を** クリックします。

デバイスが準拠しており、センサーデータを正しく報告するかどうかを手動で検証する方法については、 [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)を行う方法を参照してください。

## <a name="offboard-devices-using-a-local-script"></a>ローカルスクリプトを使用した offboard デバイス
セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。 有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。 オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。

> [!NOTE]
> オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com)からオフボードパッケージを取得する

2. ナビゲーションウィンドウで、[ **設定** とデバイスのオフボード] を選択し  >  **Device offboarding** ます。

3. [ **展開方法** ] フィールドで、[ **ローカルスクリプト** ] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. .Zip ファイルの内容を、デバイスからアクセスできる共有の読み取り専用の場所に抽出します。 *DeviceComplianceOffboardingScript_valid_until_YYYY* という名前のファイルが必要です。

6.  デバイス上で管理者特権のコマンドラインプロンプトを開き、次のスクリプトを実行します。

7.  [ **スタート** ] に移動し、「 **cmd** 」と入力します。

8.  [ **コマンドプロンプト** ] を右クリックし、[ **管理者として実行** ] を選択します。

![[管理者として実行] をポイントする [スタート] メニュー](../media/dlp-run-as-admin.png)

9.  スクリプトファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は、次のように入力します。 *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY mmmm*

10.  Enter キーを押すか、[ **OK]****を** クリックします。

> [!IMPORTANT]
> オフボードは、デバイスがポータルへのセンサーデータの送信を停止させます。


## <a name="monitor-device-configuration"></a>デバイス構成の監視
[トラブルシューティングの問題のトラブルシューティング] (( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) スクリプトが正常に完了し、エージェントが実行されていることを確認する) にある、さまざまな検証手順を実行できます。

また、ポータル上で、またはさまざまな展開ツールを使用して、監視を直接実行することもできます。

### <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する
1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)に移動します。

2. [ **設定**  >  **デバイスのオンボード** デバイス] を選択し  >  **Devices** ます。

3. デバイスが表示されていることを確認します。


## <a name="related-topics"></a>関連項目
- [グループポリシーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-sccm.md)
- [モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス](dlp-configure-endpoints-vdi.md)
- [新しく利用 Microsoft Defender ATP デバイスで検出テストを実行する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
