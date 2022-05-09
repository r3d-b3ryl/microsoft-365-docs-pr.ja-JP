---
title: ローカル スクリプトを使用した Windows デバイスのオンボード
description: ローカル スクリプトを使用してデバイスに構成パッケージを展開し、デバイスのサービスへのオンボードを有効にします。
keywords: ローカル スクリプトを使用してデバイスを構成する、デバイスを管理する、Microsoft Defender for Endpointデバイスを構成する
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1ea1661a89585d46aa5fc234f6f88be66512c1be
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468701"
---
# <a name="onboard-windows-devices-using-a-local-script"></a>ローカル スクリプトを使用した Windows デバイスのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

また、個々のデバイスを Defender for Endpoint に手動でオンボードすることもできます。 これは、ネットワーク内のすべてのデバイスのオンボードにコミットする前に、サービスをテストするときに最初に行う必要がある場合があります。

> [!IMPORTANT]
> このスクリプトは、最大 10 台のデバイスで使用できるように最適化されています。
> ローカル スクリプトは、Microsoft Defender for Endpointを評価するための特別なオンボード方法です。
> データ レポートの頻度は、ローカル スクリプトを使用してオンボードするときに、他のオンボード方法よりも高く設定されます。
> この設定は評価用であり、通常は運用環境のデプロイでは使用されません。 このため、環境への影響が懸念されるため、ローカル スクリプトを使用するデプロイの数を 10 に制限することをお勧めします。
> 前述のように運用環境にデプロイする場合は、グループ ポリシーやMicrosoft Endpoint Configuration Managerなどの[他のデプロイ オプション](configure-endpoints.md)を使用します。

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) または[Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)を確認して、Defender for Endpoint のデプロイに関するさまざまなパスを確認してください。 

## <a name="onboard-devices"></a>デバイスのオンボード 

1.  サービスオンボード ウィザードからダウンロードした GP 構成パッケージ .zip ファイル (*WindowsDefenderATPOnboardingPackage.zip*) を開きます。 また、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>からパッケージを取得することもできます。

    1. ナビゲーション ウィンドウで、**設定** > **EndpointsDevice** >  **managementOnboarding** >  を選択します。


[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) または[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)を確認して、Defender for Endpoint のデプロイに関するさまざまなパスを確認してください。

1. サービスオンボード ウィザードからダウンロードした GP 構成パッケージ .zip ファイル (*WindowsDefenderATPOnboardingPackage.zip*) を開きます。 また、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>からパッケージを取得することもできます。
    1. ナビゲーション ウィンドウで、**設定[Endpoints** \> Device management **Onboarding**]\ **(**\>エンドポイント **デバイス管理**\>オンボード\) を選択します。
    2. オペレーティング システムとしてWindows 10またはWindows 11を選択します。
    3. [ **展開方法]** フィールドで、[ **ローカル スクリプト**] を選択します。
    4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

2. 構成パッケージの内容を、オンボードするデバイス上の場所 (デスクトップなど) に抽出します。 *WindowsDefenderATPLocalOnboardingScript.cmd* という名前のファイルが必要です。

3. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。
   1. **[スタート]** をクリックし、「**cmd**」と入力します。
   2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

    :::image type="content" source="images/run-as-admin.png" alt-text="管理者として実行を指すウィンドウ スタート メニュー" lightbox="images/run-as-admin.png":::

4.  スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は、「*%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd」と* 入力します。

5.  **Enter** キーを押すか、[**OK**] をクリックします。

デバイスが準拠していることを手動で検証し、センサー データを正しく報告する方法については、「[オンボードの問題Microsoft Defender for Endpointトラブルシューティング](troubleshoot-onboarding.md)する」を参照してください。

> [!TIP]
> デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「[新しくオンボードされたMicrosoft Defender for Endpoint エンドポイントで検出テストを実行](run-detection-test.md)する」を参照してください。

## <a name="configure-sample-collection-settings"></a>サンプル コレクションの設定を構成する

デバイスごとに、詳細な分析のためにファイルを送信する要求がMicrosoft 365 Defenderによって行われたときに、デバイスからサンプルを収集できるかどうかを示す構成値を設定できます。

*regedit* を使用するか、*.reg* ファイルを作成して実行することで、デバイスでサンプル共有設定を手動で構成できます。

構成は、次のレジストリ キー エントリを使用して設定されます。

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

ここで、名前の種類は D-WORD です。 使用可能な値は次のとおりです。

- 0 - このデバイスからのサンプル共有を許可しない
- 1 - このデバイスからのすべてのファイルの種類の共有を許可する

レジストリ キーが存在しない場合の既定値は 1 です。

## <a name="run-a-detection-test-to-verify-onboarding"></a>検出テストを実行してオンボードを検証する

デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「[新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)」 を参照してください。

## <a name="offboard-devices-using-a-local-script"></a>ローカル スクリプトを使用してデバイスをオフボードする

セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

1. ポータルからオフボード パッケージ<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>取得します。
    1. ナビゲーション ウィンドウで、[**エンドポイント** \> **デバイス管理** \> **オフボード****設定**\>] を選択します。
    2. オペレーティング システムとしてWindows 10またはWindows 11を選択します。
    3. [ **展開方法]** フィールドで、[ **ローカル スクリプト**] を選択します。
    4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

2. デバイスからアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* という名前のファイルが必要です。

3. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。
   1. **[スタート]** をクリックし、「**cmd**」と入力します。
   2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

      :::image type="content" source="images/run-as-admin.png" alt-text="管理者として実行オプションを指すWindows スタート メニュー" lightbox="images/run-as-admin.png":::

4. スクリプト ファイルの場所を入力します。 ファイルをデスクトップにコピーした場合は、「*%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd」* と入力します。

5. **Enter** キーを押すか、[**OK**] をクリックします。

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

## <a name="monitor-device-configuration"></a>デバイス構成を監視する

[「オンボードの問題のトラブルシューティング](troubleshoot-onboarding.md)」のさまざまな確認手順に従って、スクリプトが正常に完了し、エージェントが実行されていることを確認できます。

監視は、ポータルで直接行うことも、さまざまなデプロイ ツールを使用して行うこともできます。

### <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動します。
2. [ **デバイス インベントリ]** をクリックします。
3. デバイスが表示されていることを確認します。

## <a name="related-topics"></a>関連項目
- [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows デバイスのオンボード](configure-endpoints-mdm.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
- [新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
