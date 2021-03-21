---
title: ローカル スクリプトを使用した Windows 10 デバイスのオンボード
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
description: ローカル スクリプトを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 69a8295b170f9186d14862a7247cac3fb4c4ef3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917973"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>ローカル スクリプトを使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365 Endpoint データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)

また、個々のデバイスを Microsoft 365 Endpoint データ損失防止に手動でオンボードすることもできます。 ネットワーク内のすべてのデバイスのオンボーディングにコミットする前に、サービスをテストするときに最初にこれを行う必要があります。

> [!IMPORTANT]
> このスクリプトは、最大 10 台のデバイスで使用するために最適化されています。
>
> 大規模に展開するには、他の [展開オプションを使用します](dlp-configure-endpoints.md)。 たとえば、グループ ポリシーを使用してオンボード Windows 10 デバイスで使用可能なスクリプトを使用して、オンボーディング スクリプトを実稼働 [環境の 10](dlp-configure-endpoints-gp.md)台以上のデバイスに展開できます。

## <a name="onboard-devices"></a>オンボード デバイス
 
1.  サービス オンボーディング ウィザードからダウンロードした GP *構成パッケージ*.zip ファイル (DeviceComplianceOnboardingPackage.zip) を開きます。 また、Microsoft コンプライアンス センターからパッケージ [を取得できます。](https://compliance.microsoft.com)

2. ナビゲーション ウィンドウで、[設定 **デバイスのオン** ボーディング  >  **] を選択します**。

3. [展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。
  
5. 構成パッケージの内容を、オンボードするデバイスの場所 (デスクトップなど) に展開します。 *DeviceOnboardingScript.cmd という名前のファイルが必要です*。

6.  デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

7.  **[スタート]** をクリックし、「**cmd**」と入力します。

8.  **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](../media/dlp-run-as-admin.png)

9.  スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd」と入力します。*

10.  Enter キーを **押** するか **、[OK] をクリックします**。

デバイスが準拠し、センサー データが正しく報告されていることを手動で検証する方法については [、「Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)オンボーディングの問題のトラブルシューティング」を参照してください。

## <a name="offboard-devices-using-a-local-script"></a>ローカル スクリプトを使用してデバイスをオフボードする
セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. Microsoft コンプライアンス センターからオフボード パッケージ [を取得する](https://compliance.microsoft.com)

2. ナビゲーション ウィンドウで、[設定デバイスの **オフ**  >  **ボード] を選択します**。

3. [展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。

5. .zip ファイルの内容を、デバイスがアクセスできる共有の読み取り専用の場所に展開します。 *-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。

6.  デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

7.  **[スタート]** をクリックし、「**cmd**」と入力します。

8.  **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](../media/dlp-run-as-admin.png)

9.  スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd」と入力します。*

10.  Enter キーを **押** するか **、[OK] をクリックします**。

> [!IMPORTANT]
> オフボードにより、デバイスはポータルへのセンサー データの送信を停止します。


## <a name="monitor-device-configuration"></a>デバイス構成の監視
[オンボードの問題のトラブルシューティング]() の異なる検証手順に従って、スクリプトが正常に完了し、エージェントが https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 実行されたことを確認できます。

監視は、ポータルまたはさまざまな展開ツールを使用して直接実行することもできます。

### <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する
1. [Microsoft [365 コンプライアンス センター] に移動します](https://compliance.microsoft.com)。

2. [デバイス **の**  >  **オンボーディング デバイスの設定]**  >  **を選択します**。

3. デバイスが表示されているのを確認します。


## <a name="related-topics"></a>関連項目
- [グループ ポリシーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager を使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](dlp-configure-endpoints-vdi.md)
- [新しくオンボードされた Microsoft Defender ATP デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)