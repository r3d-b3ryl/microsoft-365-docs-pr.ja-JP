---
title: ローカル スクリプトWindows 10使用Windows 11 台のデバイスをオンボードおよびインストールする
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: ローカル スクリプトを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 14412e782cffd597786a4d2c322fe2b8fc20e5ca
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950887"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-a-local-script"></a>ローカル スクリプトWindows 10使用Windows 11 台のデバイスをオンボードおよびインストールする

**適用対象:**

- [Microsoft 365 エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [Insider リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

また、個々のデバイスを手動でオンボードしてMicrosoft 365。 ネットワーク内のすべてのデバイスのオンボーディングにコミットする前に、サービスをテストするときに最初にこれを行う必要があります。

> [!IMPORTANT]
> このスクリプトは、最大 10 台のデバイスで使用するために最適化されています。
>
> 大規模に展開するには、他の [展開オプションを使用します](device-onboarding-overview.md)。 たとえば、オンボーディング スクリプトを 10 台以上のデバイスに展開し、グループ ポリシーを使用してオンボード Windows 10 デバイスで使用[できます](device-onboarding-gp.md)。

## <a name="onboard-devices"></a>デバイスのオンボード
 
1. Microsoft コンプライアンス センターから.zip *(DeviceComplianceOnboardingPackage.zip)* パッケージ [を取得する](https://compliance.microsoft.com)

2. ナビゲーション ウィンドウで、[デバイス <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**オンボーディング**</a>設定  >  **選択します**。

3. [展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip保存します。
  
5. 構成パッケージの内容を、オンボードするデバイスの場所 (デスクトップなど) に展開します。 *DeviceOnboardingScript.cmd という名前のファイルが必要です*。

6. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

7. **[スタート]** をクリックし、「**cmd**」と入力します。

8. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

    ![[管理者スタート メニュー実行] をポイントするウィンドウ のウィンドウ です。](../media/dlp-run-as-admin.png)

9. スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd」と入力します。*

10. Enter キーを **押** するか **、[OK] をクリックします**。

デバイスが準拠し、センサー データが正しく報告されていることを手動で検証する方法については [、「Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)オンボーディングの問題のトラブルシューティング」を参照してください。

## <a name="offboard-devices-using-a-local-script"></a>ローカル スクリプトを使用してデバイスをオフボードする

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. オフボード パッケージを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">次の</a>Microsoft 365 コンプライアンス センター。

2. ナビゲーション ウィンドウで、[デバイスのオフボード <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**設定**</a>  >  **選択します**。

3. [展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

5. デバイスがアクセスできる共有.zipファイルの内容を読み取り専用の場所に抽出します。 *-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。

6. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

7. **[スタート]** をクリックし、「**cmd**」と入力します。

8. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

    ![[管理者スタート メニュー実行] をポイントするウィンドウ のウィンドウ です。](../media/dlp-run-as-admin.png)

9. スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd」と入力します。*

10. Enter キーを **押** するか **、[OK] をクリックします**。

> [!IMPORTANT]
> オフボードにより、デバイスはポータルへのセンサー データの送信を停止します。

## <a name="monitor-device-configuration"></a>デバイス構成の監視

[オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)の異なる検証手順に従って、スクリプトが正常に完了し、エージェントが実行されたことを確認できます。

監視は、ポータルまたはさまざまな展開ツールを使用して直接実行することもできます。

### <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する

1. [コンプライアンス センター [Microsoft 365] に移動します](https://compliance.microsoft.com)。

2. [デバイス **設定**  >  **オンボーディング デバイス] を**  >  **選択します**。

1. [デバイスのオンMicrosoft 365 コンプライアンス センター] に移動し、[デバイスオン <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**ボーディング 設定**</a>  >  **デバイス] を**  >  **選択します**。

1. デバイスが表示されているのを確認します。

## <a name="related-topics"></a>関連項目
- [グループ ポリシー Windows 10使用Windows 11 台のデバイスをオンボードおよび管理する](device-onboarding-gp.md)
- [デバイスWindows 10使用Windows 11 台のデバイスをオンボードMicrosoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [モバイル Windows 10ツールWindows使用して 11 台のデバイスをオンボードおよびインストールする](device-onboarding-mdm.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md)
- [新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)