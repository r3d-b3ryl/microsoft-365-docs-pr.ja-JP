---
title: Microsoft Defender for Endpoint の問題のトラブルシューティング
description: デバイスまたはMicrosoft Defender for Endpoint サービスのオンボード中に発生する可能性がある問題のトラブルシューティングを行います。
keywords: オンボード、オンボードの問題、イベント ビューアー、データ収集とプレビュー ビルド、センサー データと診断のトラブルシューティング
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 9813857bffe62ab26d377d49b2830f55d0f38f93
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473521"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a>Microsoft Defender for Endpoint の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

問題が発生した場合は、Microsoft Defender for Endpointオンボード プロセスのトラブルシューティングが必要になる場合があります。
このページでは、展開ツールの 1 つと、デバイスで発生する可能性がある一般的なエラーを使用して展開するときに発生する可能性があるオンボードの問題をトラブルシューティングする詳細な手順について説明します。

オンボード ツールに関する問題のトラブルシューティングを開始する前に、デバイスをサービスにオンボードするための最小要件が満たされているかどうかを確認することが重要です。 [デバイスをサービスにオンボードするためのライセンス、ハードウェア、ソフトウェアの要件について説明します](minimum-requirements.md)。

## <a name="troubleshoot-issues-with-onboarding-tools"></a>オンボード ツールに関する問題のトラブルシューティング

オンボード プロセスを完了し、1 時間後に [デバイスの一覧にデバイス](investigate-machines.md) が表示されない場合は、オンボードまたは接続の問題を示している可能性があります。

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a>グループ ポリシーを使用してデプロイするときのオンボードのトラブルシューティング

グループ ポリシーを使用したデプロイは、デバイスでオンボード スクリプトを実行することによって行われます。 グループ ポリシー コンソールでは、デプロイが成功したかどうかは示されません。

オンボード プロセスを完了し、1 時間後に [デバイスの一覧にデバイス](investigate-machines.md) が表示されない場合は、デバイスでスクリプトの出力を確認できます。 詳細については、「 [スクリプトを使用してデプロイするときのオンボードのトラブルシューティング](#troubleshoot-onboarding-when-deploying-with-a-script)」を参照してください。

スクリプトが正常に完了した場合は、「 [デバイスのオンボードに関する問題のトラブルシューティング](#troubleshoot-onboarding-issues-on-the-device) 」を参照して、発生する可能性があるその他のエラーについて説明します。

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Managerを使用してデプロイするときのオンボードの問題のトラブルシューティング

次のバージョンのConfiguration Managerを使用してデバイスをオンボードする場合:

- Microsoft Endpoint Configuration Manager
- System Center 2012 Configuration Manager
- System Center 2012 R2 Configuration Manager

上記のバージョンのConfiguration Managerを使用した展開は、デバイスでオンボード スクリプトを実行することによって行われます。 Configuration Manager コンソールでデプロイを追跡できます。

展開に失敗した場合は、デバイスでスクリプトの出力を確認できます。

オンボードが正常に完了したが、デバイスが 1 時間後に **デバイスの一覧** に表示されない場合は、「デバイス [のオンボードの問題のトラブルシューティング](#troubleshoot-onboarding-issues-on-the-device) 」を参照して、発生する可能性があるその他のエラーについて説明します。

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a>スクリプトを使用してデプロイするときのオンボードのトラブルシューティング

**デバイスでスクリプトの結果を確認します。**

1. [**スタート] を** クリック **し、「イベント ビューアー**」と入力して Enter キーを押 **します**。

2. **Windows ログ** **アプリケーション** に移動します\>。

3. **WDATPOnboarding** イベント ソースからイベントを探します。

スクリプトが失敗し、イベントがエラーである場合は、次の表のイベント ID を確認して、問題のトラブルシューティングに役立てることができます。

> [!NOTE]
> 次のイベント ID は、オンボード スクリプトのみに固有です。

<br>

****

|イベント ID|エラーの種類|解決手順|
|:---:|---|---|
|`5`|オフボード データが見つかりましたが、削除できませんでした|レジストリに対するアクセス許可を確認します。具体的には <p> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.|
|`10`|オンボード データをレジストリに書き込めませんでした|レジストリに対するアクセス許可を確認します。具体的には <p> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`. <p> スクリプトが管理者として実行されたことを確認します。|
|`15`|SENSE サービスの開始に失敗しました|サービスの正常性を確認します (`sc query sense` コマンド)。 中間状態 (*'Pending_Stopped'*、 *'Pending_Running'*) でないことを確認し、(管理者権限を持つ) スクリプトをもう一度実行してください。 <p> デバイスがWindows 10バージョン 1607 を実行していて、コマンド`sc query sense`を実行している場合は、`START_PENDING`デバイスを再起動します。 デバイスを再起動しても問題が解決しない場合は、KB4015217 にアップグレードして、もう一度オンボードしてみてください。|
|`15`|SENSE サービスの開始に失敗しました|エラーのメッセージが次の場合:システム エラー 577 またはエラー 1058 が発生した場合は、Microsoft Defender ウイルス対策 ELAM ドライバーを有効にする必要があります。手順については、[ポリシーによってMicrosoft Defender ウイルス対策が無効になっていないことを確認](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)するを参照してください。|
|`30`|スクリプトは、サービスの実行を開始するまで待機できませんでした|サービスの開始に時間がかかったり、開始中にエラーが発生したりする可能性があります。 SENSE に関連するイベントとエラーの詳細については、「 [イベント ビューアーを使用してイベントとエラーを確認する」](event-error-codes.md)を参照してください。|
|`35`|スクリプトが必要なオンボード状態レジストリ値を見つけることができませんでした|SENSE サービスが初めて開始されると、オンボード状態がレジストリの場所に書き込まれます。 <p> `HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`. <p> 数秒後にスクリプトが見つかりませんでした。 手動でテストし、そこにあるかどうかを確認できます。 SENSE に関連するイベントとエラーの詳細については、「 [イベント ビューアーを使用してイベントとエラーを確認する」](event-error-codes.md)を参照してください。|
|`40`|SENSE サービスのオンボード状態が **1** に設定されていない|SENSE サービスが正しくオンボードできませんでした。 SENSE に関連するイベントとエラーの詳細については、「 [イベント ビューアーを使用してイベントとエラーを確認する」](event-error-codes.md)を参照してください。|
|`65`|権限が不十分|管理者特権でスクリプトをもう一度実行します。|
|

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a>Microsoft Intuneを使用したオンボードの問題のトラブルシューティング

Microsoft Intuneを使用してエラー コードを確認し、問題の原因のトラブルシューティングを試みることができます。

Intuneでポリシーを構成していて、デバイスに反映されていない場合は、MDM の自動登録を構成する必要がある場合があります。

オンボード中に発生する可能性のある問題の原因を理解するには、次の表を使用します。

- エラー コードとOMA-URIs テーブルをMicrosoft Intuneする
- 準拠していないテーブルに関する既知の問題
- モバイル デバイス管理 (MDM) イベント ログ テーブル

イベント ログとトラブルシューティング手順がいずれも機能しない場合は、ポータルの **[デバイス管理** ] セクションからローカル スクリプトをダウンロードし、管理者特権のコマンド プロンプトで実行します。

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a>エラー コードとOMA-URIsをMicrosoft Intuneする

<br>

****

|エラー コード 16 進数|エラー コード 12 月|エラーの説明|OMA-URI|考えられる原因とトラブルシューティングの手順|
|:---:|---|---|---|---|
|0x87D1FDE8|-2016281112|修復に失敗しました|オンボード <p> オフボード|**考えられる原因:** 間違った BLOB でオンボードまたはオフボーディングが失敗しました。署名が正しくないか、PreviousOrgIds フィールドが見つかりません。 <p> **トラブルシューティングの手順:** <p> デバイス イベント ログ セクションのエージェント [オンボード エラーの表示でイベント](#view-agent-onboarding-errors-in-the-device-event-log) ID を確認します。 <p> 次の表の MDM イベント ログを確認するか、「[Windowsで MDM エラーを診断する」の手順に](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)従います。|
||||オンボード <p> オフボード <p> SampleSharing|**考えられる原因:** Microsoft Defender for Endpoint ポリシー レジストリ キーが存在しないか、OMA DM クライアントに書き込みアクセス許可がありません。 <p> **トラブルシューティングの手順:** 次のレジストリ キーが存在することを確認します。 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <p> 存在しない場合は、管理者特権でコマンドを開き、キーを追加します。|
||||SenseIsRunning <p> OnboardingState <p> Orgid|**考えられる原因:** 読み取り専用プロパティによる修復の試み。 オンボードに失敗しました。 <p> **トラブルシューティングの手順:** デバイスのオンボードの問題の [トラブルシューティングに関するページ](#troubleshoot-onboarding-issues-on-the-device)のトラブルシューティング手順を確認します。 <p> 次の表の MDM イベント ログを確認するか、「[Windowsで MDM エラーを診断する」の手順に](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)従います。|
||||すべて|**考えられる原因:** サポートされていない SKU/プラットフォーム (特に Holographic SKU) にMicrosoft Defender for Endpointをデプロイします。 <p> 現在サポートされているプラットフォーム: <p> Enterprise、教育機関、およびProfessional。<p> サーバーはサポートされていません。|
|0x87D101A9|-2016345687|SyncML(425): 送信者に受信者に対する適切なアクセス制御アクセス許可 (ACL) がないため、要求されたコマンドが失敗しました。|すべて|**考えられる原因:** サポートされていない SKU/プラットフォーム (特に Holographic SKU) にMicrosoft Defender for Endpointをデプロイします。<p> 現在サポートされているプラットフォーム: <p> Enterprise、教育機関、およびProfessional。|
|

#### <a name="known-issues-with-non-compliance"></a>コンプライアンス違反に関する既知の問題

次の表は、コンプライアンス違反に関する問題と、問題に対処する方法に関する情報を示しています。

<br>

****

|ケース|現象|考えられる原因とトラブルシューティングの手順|
|:---:|---|---|
|`1`|デバイスは SenseIsRunning OMA-URI に準拠しています。 ただし、OrgId、Onboarding、OnboardingState OMA-URI では非準拠です。|**考えられる原因:** インストールまたはアップグレード後にユーザーが OOBE に合格Windows確認します。 OOBE オンボード中は完了できませんでしたが、SENSE は既に実行されています。 <p> **トラブルシューティングの手順:** OOBE が完了するまで待ちます。|
|`2`|デバイスは OrgId、オンボード、および OnboardingState OMA-URI に準拠していますが、SenseIsRunning OMA-URI では非準拠です。|**考えられる原因:** Sense Service のスタートアップの種類は、"遅延開始" に設定されます。 これにより、システムの起動時に DM セッションが発生したときに、Microsoft Intune サーバーが SenseIsRunning によって非準拠としてデバイスを報告することがあります。 <p> **トラブルシューティングの手順:** この問題は、24 時間以内に自動的に修正する必要があります。|
|`3`|デバイスが非準拠である|**トラブルシューティングの手順:** オンボード ポリシーとオフボード ポリシーが同じデバイスに同時にデプロイされていないことを確認します。|
|

#### <a name="mobile-device-management-mdm-event-logs"></a>モバイル デバイス管理 (MDM) イベント ログ

MDM イベント ログを表示して、オンボード中に発生する可能性がある問題のトラブルシューティングを行います。

ログ名: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider

チャネル名: 管理者

<br>

****

|ID|重要度|イベントの説明|トラブルシューティングの手順|
|---|---|---|---|
|1819|Error|Microsoft Defender for Endpoint CSP: ノードの値を設定できませんでした。 NodeId: (%1)、TokenName: (%2)、結果: (%3)。|[Windows 10、1607 の累積的な更新プログラム](https://go.microsoft.com/fwlink/?linkid=829760)をダウンロードします。|
|

## <a name="troubleshoot-onboarding-issues-on-the-device"></a>デバイスのオンボードに関する問題のトラブルシューティング

使用される展開ツールがオンボード プロセスでエラーを示すのではなく、デバイスが 1 時間以内にデバイスの一覧に表示されない場合は、次の検証トピックに従って、Microsoft Defender for Endpoint エージェントでエラーが発生したかどうかを確認します。

- [デバイス イベント ログでエージェントのオンボード エラーを表示する](#view-agent-onboarding-errors-in-the-device-event-log)
- [診断データ サービスが有効になっていることを確認する](#ensure-the-diagnostics-service-is-enabled)
- [サービスが開始するように設定されていることを確認する](#ensure-the-service-is-set-to-start)
- [デバイスにインターネット接続があることを確認する](#ensure-the-device-has-an-internet-connection)
- [ポリシーによってMicrosoft Defender ウイルス対策が無効になっていないことを確認する](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a>デバイス イベント ログでエージェントのオンボード エラーを表示する

1. [**スタート] を** クリック **し、「イベント ビューアー**」と入力して Enter キーを押 **します**。

2. **イベント ビューアー (ローカル)** ウィンドウで、[**アプリケーションとサービス ログ**\>] **Microsoft** \> **Windows** \> **SENSE** を展開します。

   > [!NOTE]
   > SENSE は、Microsoft Defender for Endpoint を動作させる動作センサーを指して使用される内部名です。

3. [ **操作]** を選択してログを読み込みます。

4. **[操作**] ウィンドウで、[**現在のログのフィルター処理**] をクリックします。

5. [ **フィルター** ] タブの [ **イベント レベル]** で、[ **重大]**、[ **警告]**、[ **エラー**] の順に選択し、[OK] をクリック **します**。

   :::image type="content" source="images/filter-log.png" alt-text="イベント ビューアー ログ フィルター" lightbox="images/filter-log.png":::

6. 問題を示す可能性のあるイベントが **[操作]** ウィンドウに表示されます。 次の表のソリューションに基づいて、トラブルシューティングを試みることができます。

   <br>

   ****

   |イベント ID|メッセージ|解決手順|
   |:---:|---|---|
   |`5`|Microsoft Defender for Endpointサービスが _変数_ でサーバーに接続できませんでした|[デバイスにインターネット にアクセスできることを確認します](#ensure-the-device-has-an-internet-connection)。|
   |`6`|Microsoft Defender for Endpoint サービスがオンボードされておらず、オンボード パラメーターが見つかりませんでした。 エラー コード: _変数_|[オンボード スクリプトをもう一度実行します](configure-endpoints-script.md)。|
   |`7`|Microsoft Defender for Endpoint サービスがオンボード パラメーターを読み取れませんでした。 エラー コード: _変数_|[デバイスにインターネット アクセスがあることを確認](#ensure-the-device-has-an-internet-connection)してから、オンボード プロセス全体をもう一度実行します。|
   |`9`|Microsoft Defender for Endpoint サービスが開始の種類を変更できませんでした。 エラー コード: 変数|オンボード中にイベントが発生した場合は、再起動してオンボード スクリプトの実行を再試行します。 詳細については、「 [オンボード スクリプトをもう一度実行する](configure-endpoints-script.md)」を参照してください。 <br><br>オフボード中にイベントが発生した場合は、サポートにお問い合わせください。|
   |`10`|Microsoft Defender for Endpoint サービスがオンボーディング情報を保持できませんでした。 エラー コード: 変数|オンボード中にイベントが発生した場合は、オンボード スクリプトの実行を再試行します。 詳細については、「 [オンボード スクリプトをもう一度実行する](configure-endpoints-script.md)」を参照してください。 <br><br>問題が解決しない場合は、サポートにお問い合わせください。|
   |`15`|MICROSOFT DEFENDER FOR ENDPOINTは、URL: _variable_ を使用してコマンド チャネルを開始できません|[デバイスにインターネット にアクセスできることを確認します](#ensure-the-device-has-an-internet-connection)。|
   |`17`|Microsoft Defender for Endpoint サービスが接続ユーザー エクスペリエンスとテレメトリ サービスの場所を変更できませんでした。 エラー コード: 変数|[オンボード スクリプトをもう一度実行します](configure-endpoints-script.md)。 問題が解決しない場合は、サポートにお問い合わせください。|
   |`25`|Microsoft Defender for Endpoint サービスがレジストリ内の正常性状態をリセットできませんでした。 エラー コード: _変数_|サポートに問い合わせてください。|
   |`27`|Windows DefenderでMicrosoft Defender for Endpoint モードを有効にできませんでした。 オンボーディング プロセスに失敗しました。 エラー コード: 変数|サポートに問い合わせてください。|
   |`29`|オフボーディング パラメーターを読み取れませんでした。 エラーの種類: %1、エラー コード: %2、説明: %3|デバイスにインターネット アクセスがあることを確認し、オフボーディング プロセス全体をもう一度実行してください。|
   |`30`|Microsoft Defender for Endpointで $(build.sense.productDisplayName) モードを無効にできませんでした。 エラー コード: %1|サポートに問い合わせてください。|
   |`32`|$(build.sense.productDisplayName) サービスは、オフボード プロセス後にそれ自体の停止を要求できませんでした。 エラー コード: %1|サービスの開始の種類が手動であることを確認し、デバイスを再起動します。|
   |`55`|セキュリティで保護された ETW 自動ロガーの作成に失敗しました。 エラー コード: %1|デバイスを再起動します。|
   |`63`|外部サービスの開始の種類を更新しています。 名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4|前述のサービスの開始の種類の変更の原因を特定します。 終了コードが 0 でない場合は、開始の種類を手動で想定される開始の種類に修正します。|
   |`64`|停止した外部サービスを開始します。 名前: %1、終了コード: %2|イベントが再表示され続ける場合は、サポートにお問い合わせください。|
   |`68`|予期しないサービスの開始の種類です。 サービス名: %1、実際の開始の種類: %2、予期される開始の種類: %3|開始の種類の変更の原因を特定します。 前述のサービス開始の種類を修正しました。|
   |`69`|サービスが停止しています。 サービス名: %1|前述のサービスを開始します。 解決しない場合は、サポートにお問い合わせください。|
   |

デバイスには、Microsoft Defender for Endpoint エージェントが適切に機能するために依存する追加のコンポーネントがあります。 Microsoft Defender for Endpoint エージェント イベント ログにオンボード関連のエラーがない場合は、次の手順に進み、追加のコンポーネントが正しく構成されていることを確認します。

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a>診断データ サービスが有効になっていることを確認する

デバイスが正しく報告されていない場合は、Windows診断データ サービスが自動的に起動し、デバイスで実行されていることを確認する必要があります。 サービスが他のプログラムまたはユーザー構成の変更によって無効になっている可能性があります。

まず、Windowsの起動時にサービスが自動的に開始するように設定されていることを確認する必要があります。次に、サービスが現在実行されていることを確認する必要があります (そうでない場合は開始します)。

### <a name="ensure-the-service-is-set-to-start"></a>サービスが開始するように設定されていることを確認する

**コマンド ラインを使用して、Windows診断データ サービスのスタートアップの種類を確認します**。

1. デバイスで管理者特権のコマンド ライン プロンプトを開きます。

   a.  [ **スタート] を** クリックし、「 **cmd」** と入力して Enter キーを押 **します**。

   b. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter キー** を押します。

   ```console
   sc qc diagtrack
   ```

   サービスが有効になっている場合、結果は次のスクリーンショットのようになります。

   :::image type="content" source="images/windefatp-sc-qc-diagtrack.png" alt-text="diagtrack の sc クエリ コマンドの結果" lightbox="images/windefatp-sc-qc-diagtrack.png":::

   が `START_TYPE` 設定 `AUTO_START`されていない場合は、サービスを自動的に開始するように設定する必要があります。

**コマンド ラインを使用して、Windows診断データ サービスを自動的に開始するように設定します。**

1. デバイスで管理者特権のコマンド ライン プロンプトを開きます。

   a.  [ **スタート] を** クリックし、「 **cmd」** と入力して Enter キーを押 **します**。

   b. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter キー** を押します。

   ```console
   sc config diagtrack start=auto
   ```

3. 成功メッセージが表示されます。次のコマンドを入力して変更を確認し、**Enterキー** を押します。

   ```console
   sc qc diagtrack
   ```

4. サービスを開始します。 コマンド プロンプトで、次のコマンドを入力し、 **Enter** キーを押します。

   ```console
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a>デバイスにインターネット接続があることを確認する

Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。

WinHTTP は、インターネット閲覧プロキシ設定やその他のユーザー コンテキスト アプリケーションとは無関係であり、特定の環境で使用可能なプロキシ サーバーを検出できる必要があります。

センサーにサービス接続があることを確認するには、「Microsoft Defender for Endpoint [サービス URL へのクライアント接続を確認する](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)」トピックで説明されている手順に従います。

検証が失敗し、環境でプロキシを使用してインターネットに接続している場合は、「 [プロキシとインターネット接続の設定の構成](configure-proxy-internet.md) 」トピックで説明されている手順に従います。

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a>ポリシーによってMicrosoft Defender ウイルス対策が無効になっていないことを確認する

> [!IMPORTANT]
> 次は、2020 年 8 月 (バージョン 4.18.2007.8) の更新プログラムをMicrosoft Defender ウイルス対策にまだ受け取 **っていない** デバイスにのみ適用されます。
>
> この更新プログラムにより、システム ポリシーを使用してクライアント デバイスでMicrosoft Defender ウイルス対策をオフにすることはできません。

**問題**: Microsoft Defender for Endpoint サービスはオンボード後に開始されません。

**現象**: オンボードは正常に完了しますが、サービスを開始しようとするとエラー 577 またはエラー 1058 が表示されます。

**解決策**: デバイスでサードパーティのマルウェア対策クライアントが実行されている場合、Microsoft Defender for Endpoint エージェントで早期起動マルウェア対策 (ELAM) ドライバーを有効にする必要があります。 システム ポリシーによって無効になっていないことを確認する必要があります。

- ポリシーの実装に使用するツールに応じて、次のWindows Defender ポリシーがクリアされていることを確認する必要があります。

  - DisableAntiSpyware
  - DisableAntiVirus

  たとえば、グループ ポリシーでは、次の値などのエントリは存在しない必要があります。

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> この設定は`disableAntiSpyware`廃止され、Microsoft Defender ウイルス対策に更新された 2020 年 8 月 (バージョン 4.18.2007.8) 以降、すべてのWindows 10 デバイスでは無視されます。

- ポリシーをクリアしたら、オンボード手順をもう一度実行します。

- 前のレジストリ キーの値を確認して、レジストリ `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`キーを開いてポリシーが無効になっていることを確認することもできます。

  :::image type="content" source="images/atp-disableantispyware-regkey.png" alt-text="Microsoft Defender ウイルス対策のレジストリ キー" lightbox="images/atp-disableantispyware-regkey.png":::

   > [!NOTE]
   > すべてのWindows Defender サービス (wdboot、wdfilter、wdnisdrv、wdnissvc、windefend) は既定の状態である必要があります。 これらのサービスの起動を変更することはサポートされておらず、システムのイメージを再作成することが強制される場合があります。
   >
   > WdBoot と WdFilter の既定の構成の例:
   >
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues"></a>オンボーディングに関する問題のトラブルシューティング 

> [!NOTE]
> 次のトラブルシューティング ガイダンスは、Windows Server 2016以下にのみ適用されます。

サーバーのオンボード中に問題が発生した場合は、次の確認手順に従って、考えられる問題に対処します。


- [Microsoft Monitoring Agent (MMA) がインストールされ、センサー データをサービスに報告するように構成されていることを確認する](configure-server-endpoints.md)
- [サーバー プロキシとインターネット接続の設定が正しく構成されていることを確認する](configure-server-endpoints.md)

また、次のことを確認する必要がある場合もあります。

- **タスク マネージャー** の [プロセス] タブでMicrosoft Defender for Endpoint サービス **が** 実行されていることを確認します。 例:

  :::image type="content" source="images/atp-task-manager.png" alt-text="Microsoft Defender for Endpoint サービスが実行されているプロセス ビュー" lightbox="images/atp-task-manager.png":::

- **アプリケーションとサービス ログ** \> **操作マネージャー****イベント ビューアー**\>確認して、エラーがないかどうかを確認します。

- **サービス** で、**Microsoft Monitoring Agent** がサーバーで実行されているかどうかを確認します。 例えば、

  :::image type="content" source="images/atp-services.png" alt-text="サービス" lightbox="images/atp-services.png":::

- **Microsoft Monitoring Agent** \> **Azure Log Analytics (OMS)** で、ワークスペースを確認し、状態が実行されていることを確認します。

  :::image type="content" source="images/atp-mma-properties.png" alt-text="Microsoft Monitoring Agent プロパティ" lightbox="images/atp-mma-properties.png":::

- ポータルの [デバイス] **一覧にデバイス** が反映されていることを確認します。

## <a name="confirming-onboarding-of-newly-built-devices"></a>新しく構築されたデバイスのオンボードの確認

オンボードが新しく構築されたデバイスにデプロイされているが完了していない場合があります。

次の手順では、次のシナリオのガイダンスを提供します。

- オンボード パッケージは、新しく構築されたデバイスに展開されます
- 既定のエクスペリエンス (OOBE) または最初のユーザー ログオンが完了していないため、センサーが起動しない
- エンド ユーザーが最初のログオンを実行する前にデバイスがオフまたは再起動される
- このシナリオでは、オンボード パッケージがデプロイされた場合でも、SENSE サービスは自動的に開始されません。

> [!NOTE]
> 2021 年 4 月 22 日の[更新プログラムロールアップ](https://support.microsoft.com/kb/5001384)を使用して、WINDOWS 10 VERSION 1809または Windows Windows Server 2022、または Windows Server 2022 の各バージョンで SENSE サービスを開始するには、OOBE 後のユーザー ログオンは不要になりました。 Windows 10、バージョン 1909 と [2021 年 4 月の更新プログラムのロールアップ](https://support.microsoft.com/kb/5001396)。 Windows 10、バージョン 2004/20H2、[2021 年 4 月 28 日更新プログラムロールアップ](https://support.microsoft.com/kb/5001391)。 


> [!NOTE]
> 次の手順は、Microsoft Endpoint Configuration Managerを使用する場合にのみ関連します。 Microsoft Endpoint Configuration Managerを使用したオンボードの詳細については、「[Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection)」を参照してください。

1. Microsoft Endpoint Configuration Managerでアプリケーションを作成します。

   :::image type="content" source="images/mecm-1.png" alt-text="Microsoft Endpoint Configuration Manager構成-1" lightbox="images/mecm-1.png":::

2. [ **手動でアプリケーション情報を指定する] を選択します**。

   :::image type="content" source="images/mecm-2.png" alt-text="Microsoft Endpoint Configuration Manager構成-2" lightbox="images/mecm-2.png":::

3. アプリケーションに関する情報を指定し、[ **次へ**] を選択します。

   :::image type="content" source="images/mecm-3.png" alt-text="Microsoft Endpoint Configuration Manager構成-3" lightbox="images/mecm-3.png":::

4. ソフトウェア センターに関する情報を指定し、[ **次へ**] を選択します。

   :::image type="content" source="images/mecm-4.png" alt-text="Microsoft Endpoint Configuration Manager構成-4" lightbox="images/mecm-4.png":::

5. **[展開の種類]** で [**追加**] を選択します。

   :::image type="content" source="images/mecm-5.png" alt-text="Microsoft Endpoint Configuration Manager構成-5" lightbox="images/mecm-5.png":::

6. [ **手動で展開の種類情報を指定する**] を選択し、[ **次へ**] を選択します。

   :::image type="content" source="images/mecm-6.png" alt-text="Microsoft Endpoint Configuration Manager構成-6" lightbox="images/mecm-6.png":::

7. デプロイの種類に関する情報を指定し、[ **次へ**] を選択します。

   :::image type="content" source="images/mecm-7.png" alt-text="Microsoft Endpoint Configuration Manager構成-7" lightbox="images/mecm-7.png":::

8. **コンテンツ** \> **インストール プログラム** で、次のコマンドを指定します`net start sense`。

   :::image type="content" source="images/mecm-8.png" alt-text="Microsoft Endpoint Configuration Manager構成-8" lightbox="images/mecm-8.png":::

9. **検出方法** で、[**ルールの構成] を選択してこの展開の種類の存在を検出** し、[**句の追加**] を選択します。

   :::image type="content" source="images/mecm-9.png" alt-text="Microsoft Endpoint Configuration Manager構成-9" lightbox="images/mecm-9.png":::

10. 次の検出規則の詳細を指定し、[OK] を選択 **します**。

    :::image type="content" source="images/mecm-10.png" alt-text="Microsoft Endpoint Configuration Manager構成-10" lightbox="images/mecm-10.png":::

11. **[検出方法**] で [**次へ**] を選択します。

    :::image type="content" source="images/mecm-11.png" alt-text="Microsoft Endpoint Configuration Manager構成-11" lightbox="images/mecm-11.png":::

12. **ユーザー エクスペリエンス** で、次の情報を指定し、[**次へ**] を選択します。

    :::image type="content" source="images/mecm-12.png" alt-text="Microsoft Endpoint Configuration Manager構成-12" lightbox="images/mecm-12.png":::

13. [ **要件**] で、[ **次へ**] を選択します。

    :::image type="content" source="images/mecm-13.png" alt-text="Microsoft Endpoint Configuration Manager構成-13" lightbox="images/mecm-13.png":::

14. **[依存関係]** で、[**次へ**] を選択します。

    :::image type="content" source="images/mecm-14.png" alt-text="Microsoft Endpoint Configuration Manager構成-14" lightbox="images/mecm-14.png":::

15. [ **概要] で**、[ **次へ**] を選択します。

    :::image type="content" source="images/mecm-15.png" alt-text="Microsoft Endpoint Configuration Manager構成-15" lightbox="images/mecm-15.png":::

16. **[完了]** で [**閉じる**] を選択します。

    :::image type="content" source="images/mecm-16.png" alt-text="Microsoft Endpoint Configuration Manager構成-16" lightbox="images/mecm-16.png":::

17. **[展開の種類]** で、[**次へ**] を選択します。

    :::image type="content" source="images/mecm-17.png" alt-text="Microsoft Endpoint Configuration Manager構成-17" lightbox="images/mecm-17.png":::

18. [ **概要] で**、[ **次へ**] を選択します。

    :::image type="content" source="images/mecm-18.png" alt-text="Microsoft Endpoint Configuration Manager構成-18" lightbox="images/mecm-18.png":::

    次に、状態が表示されます::::image type="content" source="images/mecm-19.png" alt-text="Microsoft Endpoint Configuration Manager configuration-19" lightbox="images/mecm-19.png":::

19. **[完了]** で [**閉じる**] を選択します。

    :::image type="content" source="images/mecm-20.png" alt-text="Microsoft Endpoint Configuration Manager構成-20" lightbox="images/mecm-20.png":::

20. これで、アプリを右クリックして [デプロイ] を選択することで、アプリケーションを **デプロイ** できます。

    :::image type="content" source="images/mecm-21.png" alt-text="Microsoft Endpoint Configuration Manager構成-21" lightbox="images/mecm-21.png":::

21. [ **全般** ] で、[ **依存関係のコンテンツを自動的に配布** する] と **[参照**] を選択します。

    :::image type="content" source="images/mecm-22.png" alt-text="Microsoft Endpoint Configuration Manager構成-22" lightbox="images/mecm-22.png":::

22. **[コンテンツ**] で [**次へ**] を選択します。

    :::image type="content" source="images/mecm-23.png" alt-text="Microsoft Endpoint Configuration Manager構成-23" lightbox="images/mecm-23.png":::

23. **[展開の設定]** で、[**次へ**] を選択します。

    :::image type="content" source="images/mecm-24.png" alt-text="Microsoft Endpoint Configuration Manager構成-24" lightbox="images/mecm-24.png":::

24. **[スケジュール]** で、**使用可能な時間の後にできるだけ早く** 選択し、[**次へ**] を選択します。

    :::image type="content" source="images/mecm-25.png" alt-text="Microsoft Endpoint Configuration Manager構成-25" lightbox="images/mecm-25.png":::

25. **ユーザー エクスペリエンス****で、期限またはメンテナンス期間中に変更をコミットする (再起動が必要)** を選択し、[**次へ**] を選択します。

    :::image type="content" source="images/mecm-26.png" alt-text="Microsoft Endpoint Configuration Manager構成-26" lightbox="images/mecm-26.png":::

26. **[アラート]** で [**次へ**] を選択します。

    :::image type="content" source="images/mecm-27.png" alt-text="Microsoft Endpoint Configuration Manager構成-27" lightbox="images/mecm-27.png":::

27. [ **概要] で**、[ **次へ**] を選択します。

    :::image type="content" source="images/mecm-28.png" alt-text="Microsoft Endpoint Configuration Manager構成-28" lightbox="images/mecm-28.png":::
      

    次に、状態が表示される :::image type="content" source="images/mecm-29.png" alt-text="Microsoft Endpoint Configuration Manager configuration-29" lightbox="images/mecm-29.png":::

28. **[完了]** で [**閉じる**] を選択します。

    :::image type="content" source="images/mecm-30.png" alt-text="Microsoft Endpoint Configuration Manager構成-30" lightbox="images/mecm-30.png":::

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint のトラブルシューティング](troubleshoot-mdatp.md)
- [デバイスのオンボード](onboard-configure.md)
- [デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
