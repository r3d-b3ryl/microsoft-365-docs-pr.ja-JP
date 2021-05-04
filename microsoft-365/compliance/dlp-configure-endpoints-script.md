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
ms.openlocfilehash: e9efa76af72f9169bdec1acf35d72066ac0a776e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893308"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>ローカル スクリプトを使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)

個々のデバイスを手動でオンボードして、エンドポイントMicrosoft 365防止することもできます。 ネットワーク内のすべてのデバイスのオンボーディングにコミットする前に、サービスをテストするときに最初にこれを行う必要があります。

> [!IMPORTANT]
> このスクリプトは、最大 10 台のデバイスで使用するために最適化されています。
>
> 大規模に展開するには、他の [展開オプションを使用します](dlp-configure-endpoints.md)。 たとえば、オンボーディング スクリプトを 10 台以上のデバイスに展開し、グループ ポリシーを使用してオンボード Windows 10 デバイスで使用[できます](dlp-configure-endpoints-gp.md)。

## <a name="onboard-devices"></a>デバイスのオンボード
 
1.  サービス オンボーディング ウィザードから.zipした gp 構成 *パッケージ*(DeviceComplianceOnboardingPackage.zip) を開きます。 また、Microsoft コンプライアンス センターからパッケージ [を取得できます。](https://compliance.microsoft.com)

2. ナビゲーション ウィンドウで、[デバイス **オンボーディング** 設定  >  **選択します**。

3. [展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip保存します。
  
5. 構成パッケージの内容を、オンボードするデバイスの場所 (デスクトップなど) に展開します。 *DeviceOnboardingScript.cmd という名前のファイルが必要です*。

6.  デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

7.  **[スタート]** をクリックし、「**cmd**」と入力します。

8.  **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

    ![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](../media/dlp-run-as-admin.png)

9.  スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd」と入力します。*

10.  Enter キーを **押** するか **、[OK] をクリックします**。

デバイスが準拠し、センサー データが正しく報告されていることを手動で検証する方法については、「トラブルシューティング」を参照Microsoft Defender Advanced Threat Protection[を参照してください](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。

## <a name="offboard-devices-using-a-local-script"></a>ローカル スクリプトを使用してデバイスをオフボードする
セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. Microsoft コンプライアンス センターからオフボード パッケージ [を取得する](https://compliance.microsoft.com)

2. ナビゲーション ウィンドウで、[デバイスのオフボード **設定**  >  **選択します**。

3. [展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

5. デバイスがアクセスできる共有.zipファイルの内容を読み取り専用の場所に抽出します。 *-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。

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
1. [コンプライアンス センター [Microsoft 365] に移動します](https://compliance.microsoft.com)。

2. [デバイス **設定**  >  **オンボーディング デバイス] を**  >  **選択します**。

3. デバイスが表示されているのを確認します。


## <a name="related-topics"></a>関連項目
- [グループ ポリシー Windows 10デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](dlp-configure-endpoints-vdi.md)
- [新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [オンボーディングMicrosoft Defender Advanced Threat Protectionのトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)