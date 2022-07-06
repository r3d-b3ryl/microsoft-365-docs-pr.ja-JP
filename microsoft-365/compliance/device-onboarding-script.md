---
title: ローカル スクリプトを使用した Windows 10 および Windows 11 デバイスのオンボード
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
description: ローカル スクリプトを使用して、構成パッケージをデバイスに展開して、サービスにオンボードします。
ms.openlocfilehash: 840573794b447162f917fed162bb1f869585286e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634425"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-a-local-script"></a>ローカル スクリプトを使用した Windows 10 および Windows 11 デバイスのオンボード

**適用対象:**

- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)

また、個々のデバイスを Microsoft 365 に手動でオンボードすることもできます。 これは、ネットワーク内のすべてのデバイスのオンボードにコミットする前に、サービスをテストするときに最初に行う必要がある場合があります。

> [!IMPORTANT]
> このスクリプトは、最大 10 台のデバイスで使用できるように最適化されています。
>
> 大規模にデプロイするには、 [他のデプロイ オプションを使用します](device-onboarding-overview.md)。 たとえば、オンボード スクリプトを運用環境の 10 台を超えるデバイスにデプロイできます。このスクリプトは[、グループ ポリシーを使用してオンボード Windows 10 デバイス](device-onboarding-gp.md)で使用できます。

## <a name="onboard-devices"></a>デバイスのオンボード
 
1. Microsoft Purview コンプライアンス ポータルから構成パッケージ .zip ファイル (*DeviceComplianceOnboardingPackage.zip*) パッケージ [を取得する](https://compliance.microsoft.com)

2. ナビゲーション ウィンドウで、[デバイスの **オンボード**<a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**の設定]**</a> >  を選択します。

3. [ **展開方法]** フィールドで、[ **ローカル スクリプト**] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。
  
5. 構成パッケージの内容を、オンボードするデバイス上の場所 (デスクトップなど) に抽出します。 *DeviceOnboardingScript.cmd* という名前のファイルが必要です。

6. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

7. **[スタート]** をクリックし、「**cmd**」と入力します。

8. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

    ![[管理者として実行] をポイントするウィンドウの [スタート] メニュー。](../media/dlp-run-as-admin.png)

9. スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は、「*%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd」と* 入力します。

10. **Enter** キーを押すか、[**OK**] をクリックします。

デバイスが準拠していることを手動で検証し、センサー データを正しく報告する方法については、「 [Microsoft Defender Advanced Threat Protection のオンボードに関する問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)」を参照してください。

## <a name="offboard-devices-using-a-local-script"></a>ローカル スクリプトを使用してデバイスをオフボードする

セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>からオフボード パッケージを取得します。

2. ナビゲーション ウィンドウで、[デバイス **のオフボード**<a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**の設定]**</a> >  を選択します。

3. [ **展開方法]** フィールドで、[ **ローカル スクリプト**] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. デバイスからアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* という名前のファイルが必要です。

6. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

7. **[スタート]** をクリックし、「**cmd**」と入力します。

8. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

    ![[管理者として実行] をポイントするウィンドウの [スタート] メニュー。](../media/dlp-run-as-admin.png)

9. スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は、「*%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd」* と入力します。

10. **Enter** キーを押すか、[**OK**] をクリックします。

> [!IMPORTANT]
> オフボーディングにより、デバイスはセンサー データのポータルへの送信を停止します。

## <a name="monitor-device-configuration"></a>デバイス構成を監視する

[オンボードの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) のさまざまな検証手順に従って、スクリプトが正常に完了し、エージェントが実行されていることを確認できます。

監視は、ポータルで直接行うことも、さまざまなデプロイ ツールを使用して行うこともできます。

### <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する

1. Microsoft Purview コンプライアンス ポータルに移動[します](https://compliance.microsoft.com)。

2. [デバイス **の** > オンボードデバイス **の設定]** >  を選択 **します**。

1. Microsoft Purview コンプライアンス ポータルに移動し、[**デバイスのオンボード** > デバイス <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**の設定]**</a> >  を選択 **します**。

1. デバイスが表示されていることを確認します。

## <a name="related-topics"></a>関連トピック
- [グループ ポリシーを使用してWindows 10デバイスとWindows 11 デバイスをオンボードする](device-onboarding-gp.md)
- [Microsoft Endpoint Configuration Managerを使用してWindows 10デバイスとWindows 11 デバイスをオンボードする](device-onboarding-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード](device-onboarding-mdm.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md)
- [新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection のオンボードに関する問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
