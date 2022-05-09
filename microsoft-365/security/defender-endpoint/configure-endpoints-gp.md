---
title: グループ ポリシーを使用してWindowsデバイスをMicrosoft Defender for Endpointにオンボードする
description: グループ ポリシーを使用して、Windows デバイスに構成パッケージを展開し、サービスにオンボードします。
keywords: グループ ポリシー、デバイス管理を使用してデバイスを構成する、Microsoft Defender for Endpoint デバイスを構成する、Microsoft Defender for Endpoint デバイスをオンボードする、グループ ポリシー
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
ms.date: 12/07/2021
ms.technology: mde
ms.openlocfilehash: e05927829ec680a303972090dc050514c31cdbc6
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468967"
---
# <a name="onboard-windows-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオンボードする 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用対象:**

- グループ ポリシー
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、Windows Server 2008 R2 以降である必要があります。
>
> Windows Server 2019 および Windows Server 2022 の場合は、NT AUTHORITY\Well-Known-System-Account を、グループ ポリシー 基本設定で作成される XML ファイルの NT AUTHORITY\SYSTEM に置き換える必要がある場合があります。

> [!NOTE]
> Windows Server 2012 R2 と 2016 に新しい統合Microsoft Defender for Endpoint ソリューションを使用している場合は、中央ストアで最新の ADMX ファイルを使用して、正しいMicrosoft Defender for Endpoint ポリシー オプションにアクセスしていることを確認してください。 [Windowsで グループ ポリシー 管理用のセントラル ストアを作成および管理する方法と、Windows 10](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)**で使用する** 最新のファイルをダウンロードする方法を参照してください。

[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) または[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)を確認して、Defender for Endpoint のデプロイに関するさまざまなパスを確認してください。

1. サービス オンボード ウィザードからダウンロードした GP 構成パッケージ ファイル (`WindowsDefenderATPOnboardingPackage.zip`) を開きます。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>からパッケージを取得することもできます。

    1. ナビゲーション ウィンドウで、**設定** > **EndpointsDevice** >  **managementOnboarding**  >  を選択します。

    1. オペレーティング システムを選択します。

    1. [ **展開方法]** フィールドで、[ **グループ ポリシー**] を選択します。

    1. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

2. デバイスからアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *OptionalParamsPolicy* という名前のフォルダーと *、WindowsDefenderATPOnboardingScript.cmd* ファイルが必要です。

3. 新しい GPO を作成するには、[グループ ポリシー管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成 **するオブジェクトグループ ポリシー** 右クリックし、[**新規**] をクリックします。 表示されるダイアログ ボックスに新しい GPO の名前を入力し、**［OK］** をクリックします。

4. [グループ ポリシー管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、**［編集］** をクリックします。

5. **［グループ ポリシー管理エディター］** で、**［コンピューター構成］** に移動します。そして **［ユーザー設定］** をし、**［コントロール パネルの設定］** を行ないます。

6. **［スケジュールされたタスク］** を右クリックします。**［新規作成］** をポイントし、**［イミディエイト タスク］ (Windows 7 以上)** をクリックします。

7. **［タスク］** ウィンドウが開いたら、**［一般］** タブに移動します。**［セキュリティ オプション］** で、**［ユーザーまたはグループを変更］** をクリックし、「SYSTEM」と入力します。**［名前を確認］** をクリックし、**［OK］** をクリックします。 NT AUTHORITY\SYSTEM は、タスクを実行するユーザー アカウントとして表示されます。

8. **［ユーザーがログオンしているかどうかに関係なく実行する］** を選択し、**［最高の権限で実行する］** チェックボックスをオンにします。

9. [名前] フィールドに、スケジュールされたタスクの適切な名前 (たとえば Defender for Endpoint Deployment など) を入力します。

10. **［アクション］** タブに移動し、**［新規作成］** を選択し、**［プログラムの開始］** が **［アクション］** フィールドで選択されていることを確認します。 共有 *WindowsDefenderATPOnboardingScript.cmd* ファイルのファイル サーバーの完全修飾ドメイン名 (FQDN) を使用して UNC パスを入力します。

11. **［OK］** を選択し、開いている GPMC ウィンドウをすべて閉じます。

12. GPO を組織単位 (OU) にリンクするには、右クリックして 既存の **［GPO をリンク］** を選択します。 表示されるダイアログ ボックスで、リンクする グループ ポリシー オブジェクトを選択します。 **[OK]** をクリックします。

> [!TIP]
> デバイスをオンボードした後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認することができます。 詳細については、「 [新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行する」を参照してください](run-detection-test.md)。

## <a name="additional-defender-for-endpoint-configuration-settings"></a>その他の Defender for Endpoint 構成設定

デバイスごとに、詳細な分析のためにファイルを送信する要求がMicrosoft 365 Defenderによって行われたときに、デバイスからサンプルを収集できるかどうかを指定できます。

グループ ポリシー (GP) を使用して、詳細分析機能で使用されるサンプル共有の設定などの設定を構成できます。

### <a name="configure-sample-collection-settings"></a>サンプル コレクションの設定を構成する

1. GP 管理デバイスで、構成パッケージから次のファイルをコピーします。

    - _AtpConfiguration.admx_ を _C:\\Windows\\ PolicyDefinitions_ にコピーする

    - _AtpConfiguration.adml_ を _C:\\Windows\\ PolicyDefinitionsen-US\\_ にコピーする

    [グループ ポリシー管理用テンプレートにセントラル ストアを](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)使用している場合は、構成パッケージから次のファイルをコピーします。

    - _AtpConfiguration.admx_ を _SysVolPoliciesPolicyDefinitions\\\\\<forest.root\>\\ に\\\\\<forest.root\>\\コピーする_

    - _AtpConfiguration.adml_ を _SysVolPoliciesPolicyDefinitionsen-US\\\<forest.root\>\\\\\\ に\\\\\<forest.root\>\\_ コピーする

2. [グループ ポリシー管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)を開き、構成する GPO を右クリックし、[編集] をクリック **します**。

3. **グループ ポリシー管理エディター** で、[**コンピューターの構成] に** 移動します。

4. [ **ポリシー]**、[ **管理用テンプレート]** の順にクリックします。

5. **Windowsコンポーネント** をクリックし、**ATP をWindows Defender** します。

6. デバイスからのサンプル共有を有効または無効にします。

> [!NOTE]
> 値を設定しない場合、既定値はサンプル コレクションを有効にするためです。

## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定

### <a name="update-endpoint-protection-configuration"></a>エンドポイント保護の構成を更新する

オンボード スクリプトを構成した後、同じグループ ポリシーの編集を続行して、エンドポイント保護構成を追加します。 Windows 10または Server 2019、Windows 11、またはWindows Server 2022 を実行しているシステムからグループ ポリシーの編集を実行して、必要なすべてのMicrosoft Defender ウイルス対策機能を確実に備えます。 Defender ATP 構成設定を登録するには、グループ ポリシー オブジェクトを閉じてから再度開く必要がある場合があります。

すべてのポリシーは 、 `Computer Configuration\Policies\Administrative Templates`.

**ポリシーの場所:** \Windows Components\Windows Defender ATP

ポリシー|Setting
---|---
Enable\Disable Sample collection|有効 - "コンピューターでサンプル コレクションを有効にする" チェック ボックス

<br>

**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策

ポリシー|Setting
---|---
望ましくない可能性があるアプリケーションの検出を構成する|有効、ブロック

<br>

**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\MAPS

ポリシー|Setting
---|---
Microsoft MAPS に参加する|有効、高度なマップ
さらなる分析が必要な場合にファイル サンプルを送信する | 有効、安全なサンプルの送信

<br>

**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\リアルタイム保護

ポリシー|Setting
---|---
リアルタイム保護を無効にする|無効
動作の監視を有効にする|Enabled
ダウンロードしたすべてのファイルと添付ファイルをスキャンする|Enabled
コンピューター上のファイルとプログラムのアクティビティを監視する|Enabled

<br>

**ポリシーの場所:** \Windows Components\Microsoft Defender ウイルス対策\Scan

これらの設定は、エンドポイントの定期的なスキャンを構成します。 毎週のクイック スキャンを実行することをお勧めします。パフォーマンスは可能です。

ポリシー|Setting
---|---
スケジュールされたスキャンを実行する前に、最新のウイルスとスパイウェアのセキュリティ インテリジェンスを確認する |Enabled

<br>

**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\Microsoft Defender Exploit Guard\攻撃面の縮小

攻撃表面の縮小規則の [展開手順 3: ASR 規則を実装するから、攻撃表面縮小規則](attack-surface-reduction-rules-deployment-implement.md) GUID の現在の一覧を取得します。 ルールの詳細に関する追加の詳細については、「[攻撃面の縮小ルールのリファレンス](attack-surface-reduction-rules-reference.md)」を参照してください。

1. **攻撃面の縮小の構成** ポリシーを開きます。

1. **[有効]** を選択します。

1. [ **表示** ] ボタンを選択します。

1. **[値の名前]** フィールドに値 2 の各 GUID を追加します。

   これにより、各監査のみが設定されます。

   :::image type="content" source="images/asr-guid.png" alt-text="攻撃面の縮小構成" lightbox="images/asr-guid.png":::

ポリシー|Location|Setting
---|---|---
フォルダー アクセスの制御を構成する| \Windows コンポーネント\Microsoft Defender ウイルス対策\Microsoft Defender Exploit Guard\フォルダー アクセスの制御| 有効、監査モード

## <a name="run-a-detection-test-to-verify-onboarding"></a>検出テストを実行してオンボードを検証する

デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「[新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)」 を参照してください。

## <a name="offboard-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオフボードする

セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>からオフボード パッケージを取得します。

    1. ナビゲーション ウィンドウで、**設定** > **EndpointsDevice** >  **managementOffboarding** >  を選択します。

    1. オペレーティング システムを選択します。
    
    1. [ **展開方法]** フィールドで、[ **グループ ポリシー**] を選択します。

    1. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

2. デバイスからアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* という名前のファイルが必要です。

3. [グループ ポリシー管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、**［編集］** をクリックします。

4. **グループ ポリシー管理エディター** で、[**コンピューターの構成]、[****基本設定]**、[**コントロール パネルの設定**] の順に移動します。

5. **[スケジュールされたタスク**] を右クリックし、[**新規**] をポイントして、[**イミディエイト タスク**] をクリックします。

6. 開いた **[タスク** ] ウィンドウで、[ **全般** ] タブに移動します。 **[セキュリティ オプション**] でローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) を選択します。

7. **[ユーザーがログオンしているかどうかを実行** する] を選択し、[**最高の特権で実行**] チェック ボックスをオンにします。

8. [名前] フィールドに、スケジュールされたタスクの適切な名前 (たとえば Defender for Endpoint Deployment など) を入力します。

9. **[アクション]** タブに移動し、[**新規]...** を選択します。**[アクション****] フィールドで [プログラムの開始**] が選択されていることを確認します。 共有 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* ファイルのファイル サーバーの完全修飾ドメイン名 (FQDN) を使用して UNC パスを入力します。

10. **［OK］** を選択し、開いている GPMC ウィンドウをすべて閉じます。

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

## <a name="monitor-device-configuration"></a>デバイス構成を監視する

グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。 監視は、ポータルで直接実行することも、さまざまなデプロイ ツールを使用して行うこともできます。

## <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動します。
2. [ **デバイス インベントリ]** をクリックします。
3. デバイスが表示されていることを確認します。

> [!NOTE]
> デバイスが [デバイス **] の一覧** に表示されるまでに数日かかる場合があります。 これには、ポリシーがデバイスに配布されるまでにかかる時間、ユーザーがログオンするまでにかかる時間、エンドポイントがレポートを開始するまでにかかる時間が含まれます。

## <a name="setup-defender-av-policies"></a>Defender AV ポリシーを設定する

新しいグループ ポリシーを作成するか、これらの設定を他のポリシーとグループ化します。 これは、お客様の環境と、異なる組織単位 (OU) をターゲットにしてサービスを展開する方法に依存します。

1. GP を選択した後、または新しい GP を作成したら、GP を編集します。

2. **Computer** **ConfigurationPoliciesAdministrative** >  >  **Templates** >  **Windows Components** >  **Microsoft Defender ウイルス対策** > **Real-time Protection** に移動します。

    :::image type="content" source="images/realtime-protect.png" alt-text="リアルタイム保護" lightbox="images/realtime-protect.png"::::

1. [検疫] フォルダーで、検疫フォルダーからのアイテムの削除を構成します。

    :::image type="content" source="images/removal-items-quarantine1.png" alt-text="削除アイテムの検疫フォルダー" lightbox="images/removal-items-quarantine1.png":::

    :::image type="content" source="images/config-removal-items-quarantine2.png" alt-text="config-removal 検疫" lightbox="images/config-removal-items-quarantine2.png":::

4. [スキャン] フォルダーで、スキャン設定を構成します。

    :::image type="content" source="images/gpo-scans.png" alt-text="GPO スキャン" lightbox="images/gpo-scans.png":::

### <a name="monitor-all-files-in-real-time-protection"></a>リアルタイム保護ですべてのファイルを監視する

**[コンピューター構成****ポリシー**\>] \> **管理用テンプレート** \> **Windowsコンポーネント** \> **Microsoft Defender ウイルス対策** \> **リアルタイム保護** に移動します。

:::image type="content" source="images/config-monitor-incoming-outgoing-file-act.png" alt-text="受信送信ファイル アクティビティの監視を構成する" lightbox="images/config-monitor-incoming-outgoing-file-act.png":::

### <a name="configure-windows-defender-smartscreen-settings"></a>SmartScreen 設定Windows Defender構成する

1. **SmartScreen** \> エクスプローラー Windows Defender **コンピューター構成** \> **ポリシー** \> **管理用テンプレート** \> Windows **コンポーネント**\>に移動 **します**。

   :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="Windows Defender スマート スクリーン エクスプローラーを構成する" lightbox="images/config-windows-def-smartscr-explorer.png":::
 
2. **Computer** **ConfigurationPoliciesAdministrative** >  >  **Templates** >  **Windows Components** >  **Windows Defender SmartScreen** >  **Microsoft Edge** に移動します。

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="Windows Defender スマート スクリーン エッジを構成する" lightbox="images/config-windows-def-smartscr-explorer.png":::

### <a name="configure-potentially-unwanted-applications"></a>望ましくない可能性があるアプリケーションを構成する

**[コンピューター構成****ポリシー**\>] \> **管理用テンプレート** \> **Windowsコンポーネント** \> **Microsoft Defender ウイルス対策** に移動します。

:::image type="content" source="images/config-potential-unwanted-apps.png" alt-text="不要な可能性があるアプリを構成する" lightbox="images/config-potential-unwanted-apps.png":::

:::image type="content" source="images/config-potential-unwanted-apps2.png" alt-text="構成の可能性" lightbox="images/config-potential-unwanted-apps2.png":::

### <a name="configure-cloud-deliver-protection-and-send-samples-automatically"></a>Cloud Deliver Protection を構成し、サンプルを自動的に送信する

[**コンピューター構成****ポリシー**\>] \> **管理用テンプレート** \> **Windowsコンポーネント** \> **Microsoft Defender ウイルス対策** \> **MAPS に移動** します。

:::image type="content" source="images/gpo-maps1.png" alt-text="マップ" lightbox="images/gpo-maps1.png":::

:::image type="content" source="images/gpo-maps-block-atfirst-sight.png" alt-text="事前ブロック" lightbox="images/gpo-maps-block-atfirst-sight.png":::

:::image type="content" source="images/gpo-maps-join-ms-maps.png" alt-text="Microsoft マップに参加する" lightbox="images/gpo-maps-join-ms-maps.png":::

:::image type="content" source="images/send-file-sample-further-analysis-require.png" alt-text="詳細な分析が必要な場合にファイル サンプルを送信する" lightbox="images/send-file-sample-further-analysis-require.png":::

> [!NOTE]
> **[すべてのサンプルを送信]** オプションを使用すると、バイナリ/スクリプト/ドキュメントの分析が最も多くなり、セキュリティ体制が向上します。
**[安全なサンプルの送信]** オプションでは、分析するバイナリ/スクリプト/ドキュメントの種類が制限され、セキュリティ体制が低下します。 

詳細については、「[Microsoft Defender ウイルス対策でクラウド保護を有効にする」](enable-cloud-protection-microsoft-defender-antivirus.md)と、「Microsoft Defender ウイルス対策[でのクラウド保護とサンプル送信を](cloud-protection-microsoft-antivirus-sample-submission.md)有効にする」を参照してください。

### <a name="check-for-signature-update"></a>署名の更新を確認する

 **セキュリティ インテリジェンス更新プログラム** Microsoft Defender ウイルス対策 **コンポーネント** \> \> Windows **コンピューター構成** \> **ポリシー** \> **管理テンプレート**\>に移動します。

:::image type="content" source="images/signature-update-1.png" alt-text="署名の更新" lightbox="images/signature-update-1.png":::

:::image type="content" source="images/signature-update-2.png" alt-text="署名定義の更新" lightbox="images/signature-update-2.png":::

### <a name="configure-cloud-deliver-timeout-and-protection-level"></a>クラウド配信のタイムアウトと保護レベルを構成する

**MpEngine** Microsoft Defender ウイルス対策 **コンポーネント** \> \> Windows **コンピューター構成** \> **ポリシー** \> **管理テンプレート**\>に移動します。
クラウド保護レベルのポリシーを **既定のMicrosoft Defender ウイルス対策ブロック ポリシー** に構成すると、ポリシーが無効になります。 これは、保護レベルを Windows の既定値に設定するために必要です。

:::image type="content" source="images/config-extended-cloud-check.png" alt-text="config 拡張クラウド チェック" lightbox="images/config-extended-cloud-check.png":::

:::image type="content" source="images/cloud-protection-level.png" alt-text="config cloud protection level" lightbox="images/cloud-protection-level.png":::

## <a name="related-topics"></a>関連項目
- [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows デバイスのオンボード](configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
- [新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
