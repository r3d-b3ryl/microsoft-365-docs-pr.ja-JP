---
title: グループ Windows経由で Microsoft Defender for Endpoint にデバイスをオンボードする
description: グループ ポリシーを使用して、サービスにオンボードWindowsデバイスに構成パッケージを展開します。
keywords: グループ ポリシーを使用したデバイスの構成、デバイス管理、エンドポイント デバイス用 Microsoft Defender の構成、Microsoft Defender for Endpoint デバイスのオンボード、グループ ポリシー
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
ms.topic: article
ms.date: 09/16/2021
ms.technology: mde
ms.openlocfilehash: fd6453c245a5d7320518c2dc500ed4718568857c
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703263"
---
# <a name="onboard-windows-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオンボードする 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用対象:**

- グループ ポリシー
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、サーバー 2008 R2 以降Windowsする必要があります。
>
> Windows Server 2019 および Windows Server 2022 では、グループ ポリシーの基本設定で作成される XML ファイルの NT AUTHORITY\Well-Known-System-Account を NT AUTHORITY\SYSTEM に置き換える必要があります。

> [!NOTE]
> Windows Server 2012 R2 および 2016 の新しい統合 Microsoft Defender for Endpoint ソリューションを使用している場合は、中央ストアで最新の ADMX ファイルを使用して、適切な Microsoft Defender for Endpoint ポリシー オプションにアクセスしてください。 「グループ [ポリシー管理](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)用中央ストア管理用テンプレートを作成および管理する方法」を参照し、Windows で使用する最新のファイルをダウンロード **Windows 10。** 

[[](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)エンドポイント用 Defender [Visio展開](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)] のさまざまなパスを確認するには、PDF またはドキュメントを参照してください。


1. サービス オンボーディング ウィザードから.zipした GP 構成パッケージ ファイル *(WindowsDefenderATPOnboardingPackage. zip)* を開きます。 また、次のポータルから[パッケージをMicrosoft 365 Defenderすることもできます](https://security.microsoft.com/)。
 
    1. ナビゲーション ウィンドウで、[エンドポイント **デバイス設定**  >    >  **オンボーディング]**   >  **を選択します**。

    1. オペレーティング システムを選択します。
    
    1. [展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。

    1. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

     

2. デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。 *OptionalParamsPolicy* というフォルダーと *WindowsDefenderATPOnboardingScript.cmd というファイルが必要です*。

3. 新しい GPO を作成するには、グループ ポリシー [管理](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)コンソール (GPMC)を開き、構成するグループ ポリシー オブジェクトを右クリックし、[新規] をクリック **します**。 表示されるダイアログ ボックスに新しい GPO の名前を入力し **、[OK] をクリックします**。

4. グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。

5. グループ ポリシー **管理エディターで、[****コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。

6. [スケジュールされたタスク **] を** 右クリックし、[新規] をポイントし、[イミディエイト タスク] (少なくとも Windows **7) をクリックします**。

7. 開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[****ユーザーまたはグループの変更**] をクリックし、[SYSTEM] と入力し、[名前の確認] をクリック **して** **[OK] をクリックします**。 NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。

8. [ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。

9. [名前] フィールドに、スケジュールされたタスクの適切な名前 (Defender for Endpoint Deployment など) を入力します。

10. [操作] タブ **に移動し** 、[新規] **を選択します。** [アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。 共有 *WindowsDefenderATPOnboardingScript.cmd* ファイルのファイル サーバーの完全修飾ドメイン名 (FQDN) を使用して、UNC パスを入力します。

11. **[OK] を選択** し、開いている GPMC ウィンドウを閉じます。

12. GPO を組織単位 (OU) にリンクするには、右クリックして [既存の GPO のリンク **] を選択します**。 表示されるダイアログ ボックスで、リンクするグループ ポリシー オブジェクトを選択します。 [**OK**] をクリックします。

> [!TIP]
> デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行 [する」を参照してください](run-detection-test.md)。

## <a name="additional-defender-for-endpoint-configuration-settings"></a>エンドポイントの追加の Defender 構成設定

デバイスごとに、詳細分析用にファイルを送信する要求が行われたときに、デバイスからサンプルをMicrosoft 365 Defenderできるかどうかを指定できます。

グループ ポリシー (GP) を使用して、ディープ分析機能で使用されるサンプル共有の設定などの設定を構成できます。

### <a name="configure-sample-collection-settings"></a>サンプル コレクション設定の構成

1. GP 管理デバイスで、構成パッケージから次のファイルをコピーします。

    - _AtpConfiguration.admx を_ _C: \\ \\ policyDefinitions Windowsコピーする_

    - _AtpConfiguration.adml_ を C: Windows _\\ \\ PolicyDefinitions \\ en-US にコピーする_

    グループ ポリシー管理用テンプレートのセントラル [ストア](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)を使用している場合は、構成パッケージから次のファイルをコピーします。

    - SysVol ポリシー _\\ \\ \<forest.root\> \\ \\ \<forest.root\> \\ \\ PolicyDefinitions に AtpConfiguration.admx をコピーする_

    - _AtpConfiguration.adml を_ _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ ポリシー \\ PolicyDefinitions \\ en-US にコピーする_

2. グループ ポリシー [管理コンソールを開き](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)、構成する GPO を右クリックし、[編集] を **クリックします**。

3. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

4. [ポリシー **] をクリックし**、[管理 **用テンプレート] をクリックします**。

5. [コンポーネント **Windows] をクリック** し **、[ATP] Windows Defenderをクリックします**。

6. デバイスからのサンプル共有を有効または無効にする場合に選択します。

> [!NOTE]
> 値を設定しない場合、既定値はサンプル コレクションを有効にします。

## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定

### <a name="update-endpoint-protection-configuration"></a>エンドポイント保護構成の更新

オンボーディング スクリプトを構成したら、同じグループ ポリシーの編集を続けてエンドポイント保護構成を追加します。 Windows 10 または Server 2019、Windows 11、または Windows Server 2022 を実行しているシステムからグループ ポリシーの編集を実行して、必要なすべての Microsoft Defender ウイルス対策 機能を確実に使用します。 Defender ATP 構成設定を登録するには、グループ ポリシー オブジェクトを閉じて再度開く必要がある場合があります。

すべてのポリシーは 、 の下に位置します `Computer Configuration\Policies\Administrative Templates` 。

**ポリシーの場所:** \Windows コンポーネント\atp Windows Defender

ポリシー|Setting
---|---
Enable\Disable Sample collection|[有効] - [コンピューターでサンプル コレクションを有効にする] チェック ボックスをオンにします。

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
詳細な分析が必要な場合にファイル サンプルを送信する | 有効、安全なサンプルの送信

<br>

**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\リアルタイム保護

ポリシー|Setting
---|---
リアルタイム保護をオフにする|無効
動作の監視を有効にする|Enabled
ダウンロードしたファイルと添付ファイルをスキャンする|Enabled
コンピューター上のファイルとプログラムのアクティビティを監視する|Enabled

<br>

**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\Scan

これらの設定は、エンドポイントの定期的なスキャンを構成します。 毎週のクイック スキャンを実行することをお勧めします。パフォーマンスが許容されます。

ポリシー|Setting
---|---
スケジュールされたスキャンを実行する前に、最新のウイルスとスパイウェアのセキュリティ インテリジェンスを確認する |Enabled

<br>

**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\Microsoft Defender Exploit Guard\Attack Surface Reduction

[攻撃表面の縮小ルールのカスタマイズ] から攻撃表面の縮小 GUID [の現在のリストを取得する](customize-attack-surface-reduction.md)

1. [攻撃表面 **縮小の構成] ポリシーを開** きます。

1. **[有効]** を選択します。

1. [表示] **ボタンを** 選択します。

1. [値の名前] フィールドに **、値が** 2 の各 GUID を追加します。

   これにより、監査専用に設定されます。

   ![攻撃表面の縮小構成のイメージ。](images/asr-guid.png)

ポリシー|Setting
---|---
フォルダー アクセスの制御を構成する| 有効、監査モード

## <a name="run-a-detection-test-to-verify-onboarding"></a>検出テストを実行してオンボーディングを確認する

デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](run-detection-test.md)。

## <a name="offboard-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオフボードする

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. ポータルからオフボード パッケージ[Microsoft 365 Defenderします](https://security.microsoft.com/)。

    1. ナビゲーション ウィンドウで、[エンドポイント **デバイス** 設定  >  **オフ**  >  **ボード]**  >  **を選択します**。

    1. オペレーティング システムを選択します。
    
    1. [展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。

    1. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

2. デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。 *-MM-DD.cmd WindowsDefenderATPOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。

3. グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。

4. グループ ポリシー **管理エディターで、[****コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。

5. [スケジュールされたタスク] **を右クリック** し、[新規] をポイント **し**、[イミディエイト タスク] **をクリックします**。

6. 開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ オプション] の [ローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) **を選択します**。

7. [ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **]** チェック ボックスをオンにします。

8. [名前] フィールドに、スケジュールされたタスクの適切な名前 (Defender for Endpoint Deployment など) を入力します。

9. [アクション] タブ **に移動し** 、[ **新規...] を選択します**。[アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。 ファイル サーバーの完全修飾ドメイン名 (FQDN) を使用して、共有ファイル *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* ファイルの UNC パスを入力します。

10. **[OK] を選択** し、開いている GPMC ウィンドウを閉じます。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

## <a name="monitor-device-configuration"></a>デバイス構成の監視

グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。 監視は、ポータルまたはさまざまな展開ツールを使用して直接実行できます。

## <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する

1. [ポータル] [Microsoft 365 Defender移動します](https://security.microsoft.com/)。
2. [デバイス **インベントリ] をクリックします**。
3. デバイスが表示されているのを確認します。

> [!NOTE]
> デバイスが [デバイス] リストに表示を開始するには、数日 **かかる場合があります**。 これには、ポリシーがデバイスに配布される時間、ユーザーがログオンする前にかかる時間、エンドポイントがレポートを開始するのにかかる時間が含まれます。

## <a name="setup-defender-av-policies"></a>Defender AV ポリシーのセットアップ

新しいグループ ポリシーを作成するか、他のポリシーでこれらの設定をグループ化します。 これは、お客様の環境と、異なる組織単位 (OUs) をターゲットにしたサービスの展開方法に依存します。

1. GP を選択するか、新しい GP を作成した後、GP を編集します。

2. [コンピューター構成 **ポリシー]**  >    >  **[管理用** テンプレートWindows  >  **コンポーネントMicrosoft Defender ウイルス対策**  >    >  **リアルタイム保護] を参照します**。

    :::image type="content" source="images/realtime-protect.png" alt-text="リアルタイム保護。":::

1. [検疫] フォルダーで、検疫フォルダーからアイテムの削除を構成します。

    :::image type="content" source="images/removal-items-quarantine1.png" alt-text="削除アイテムの検疫フォルダー。":::

    :::image type="content" source="images/config-removal-items-quarantine2.png" alt-text="config-removal 検疫。":::

4. [スキャン] フォルダーで、スキャン設定を構成します。

    :::image type="content" source="images/gpo-scans.png" alt-text="gpo スキャン。":::

### <a name="monitor-all-files-in-real-time-protection"></a>リアルタイム保護ですべてのファイルを監視する

[コンピューター構成 **ポリシー]** \>  \> **[管理用** テンプレートWindows \> **コンポーネントMicrosoft Defender ウイルス対策** \>  \> **リアルタイム保護] を参照します**。

:::image type="content" source="images/config-monitor-incoming-outgoing-file-act.png" alt-text="受信送信ファイルアクティビティの監視を構成します。":::

### <a name="configure-windows-defender-smartscreen-settings"></a>SmartScreen Windows Defender構成する

1. SmartScreen Explorer **の**[コンピューター構成 \> **ポリシー** \> **]** \> **[管理用WindowsコンポーネントWindows Defender** \> **参照** \> **します**。

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="config windows Defender スマート スクリーン エクスプローラー。":::
 
2. [コンピューター構成 **ポリシー]**  >    >  **[管理用テンプレート**] Windows  >  **SmartScreen** Windows Defender  >  **を**  >  **参照Microsoft Edge。**

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="config windows Defender スマート スクリーン エッジ。":::

### <a name="configure-potentially-unwanted-applications"></a>望ましくない可能性のあるアプリケーションを構成する

[コンピューター構成 **ポリシー** \> **]** \> **[管理用テンプレート**] Windows \> **を参照Microsoft Defender ウイルス対策。** \> 

:::image type="content" source="images/config-potential-unwanted-apps.png" alt-text="潜在的な不要なアプリを構成します。":::

:::image type="content" source="images/config-potential-unwanted-apps2.png" alt-text="config の可能性。":::

### <a name="configure-cloud-deliver-protection-and-send-samples-automatically"></a>クラウド配信保護を構成し、サンプルを自動的に送信する

[コンピューター構成 **ポリシー]** \>  \> **[管理用テンプレート] Windows** MAPS \> **Microsoft Defender ウイルス対策** \>  \> **参照します**。

:::image type="content" source="images/gpo-maps1.png" alt-text="マップ。":::

:::image type="content" source="images/gpo-maps-block-atfirst-sight.png" alt-text="一目でブロックします。":::

:::image type="content" source="images/gpo-maps-join-ms-maps.png" alt-text="Microsoft マップに参加します。":::

:::image type="content" source="images/send-file-sample-further-analysis-require.png" alt-text="詳細な分析が必要な場合は、ファイル サンプルを送信します。":::

### <a name="check-for-signature-update"></a>署名の更新を確認する

[コンピューター構成 **ポリシー]** \> **[** \> **管理用テンプレート] Windows** \> **署名更新Microsoft Defender ウイルス対策** \>  \> **参照する**

:::image type="content" source="images/signature-update-1.png" alt-text="署名の更新。":::

:::image type="content" source="images/signature-update-2.png" alt-text="署名定義の更新。":::

### <a name="configure-cloud-deliver-timeout-and-protection-level"></a>クラウド配信のタイムアウトと保護レベルを構成する

[コンピューター構成 **ポリシー** \> **]** \> **[管理用テンプレート**] Windows \>  \>  \> **MpEngine Microsoft Defender ウイルス対策参照します**。
クラウド保護レベル のポリシーを既定のポリシーに構成Microsoft Defender ウイルス対策 **ポリシー** をブロックすると、ポリシーが無効になります。 これは、Windows の既定に保護レベルを設定するために必要な情報です。

:::image type="content" source="images/config-extended-cloud-check.png" alt-text="config 拡張クラウド チェック。":::

:::image type="content" source="images/cloud-protection-level.png" alt-text="config クラウド保護レベル。":::

## <a name="related-topics"></a>関連トピック
- [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows デバイスのオンボード](configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
- [新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](troubleshoot-onboarding.md)
