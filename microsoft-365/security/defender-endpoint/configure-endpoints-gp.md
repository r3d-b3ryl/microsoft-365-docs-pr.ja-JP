---
title: グループ ポリシーを使用して Windows 10 デバイスを Microsoft Defender ATP にオンボードする
description: グループ ポリシーを使用して、構成パッケージを Windows 10 デバイスに展開して、サービスにオンボードします。
keywords: グループ ポリシーを使用したデバイスの構成、デバイス管理、Windows ATP デバイスの構成、Microsoft Defender for Endpoint デバイスのオンボード、グループ ポリシー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: fc4b17ef96e85d3bacd4e83c2de3f4bb7fbfa5c3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166173"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>グループ ポリシーを使用した Windows 10 デバイスのオンボード 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- グループ ポリシー
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、グループ ポリシー以降Windows Server 2008 R2必要があります。
> 
> Windows Server 2019 では、グループ ポリシーの基本設定で作成される XML ファイルの NT AUTHORITY\Well-Known-System-Account を NT AUTHORITY\SYSTEM に置き換える必要があります。

## <a name="onboard-devices-using-group-policy"></a>グループ ポリシーを使用したオンボード デバイス

[![さまざまな展開パスを示す PDF のイメージ](images/onboard-gp.png)](images/onboard-gp.png#lightbox)

PDF または[Visio を参照](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)[して、Defender](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) for Endpoint の展開のさまざまなパスを確認してください。 



1. サービス オンボーディング ウィザードからダウンロードした GP *構成パッケージ*.zip ファイル (WindowsDefenderATPOnboardingPackage.zip) を開きます。 Microsoft Defender セキュリティ センターからパッケージ [を取得できます](https://securitycenter.windows.com/)。
 
    1. ナビゲーション ウィンドウで、[設定オンボーディング]  >  **を選択します**。

    1. オペレーティング システムとして [Windows 10] を選択します。
    
    1. [展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。
    
    1. [パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。

2. .zip ファイルの内容を、デバイスがアクセスできる共有の読み取り専用の場所に展開します。 *OptionalParamsPolicy* というフォルダーと *WindowsDefenderATPOnboardingScript.cmd というファイルが必要です*。

3. グループ ポリシー [管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。

4. グループ ポリシー **管理エディターで、[****コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。

5. [スケジュールされたタスク **] を** 右クリックし、[新規] をポイントし、[イミディエイト タスク] (少なくとも Windows **7) をクリックします**。

6. 開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[****ユーザーまたはグループの変更**] をクリックし、[SYSTEM] と入力し、[名前の確認] をクリック **して** **[OK] をクリックします**。 NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。

7. [ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。

8. [操作] タブ **に移動し** 、[新規] **をクリックします。** [アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。 共有 *WindowsDefenderATPOnboardingScript.cmd* ファイルのファイル名と場所を入力します。

9. **[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。

>[!TIP]
> デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行 [する」を参照してください](run-detection-test.md)。

## <a name="additional-defender-for-endpoint-configuration-settings"></a>エンドポイントの追加の Defender 構成設定
各デバイスについて、Microsoft Defender Security Center を介して詳細な分析用のファイルを提出する要求が行われたときに、デバイスからサンプルを収集できるかどうかを指定できます。

グループ ポリシー (GP) を使用して、ディープ分析機能で使用されるサンプル共有の設定などの設定を構成できます。

### <a name="configure-sample-collection-settings"></a>サンプル コレクション設定の構成
1.  GP 管理デバイスで、構成パッケージから次のファイルをコピーします。

    - _AtpConfiguration.admx を_ _C: Windows \\ \\ PolicyDefinitions にコピーする_

    - _AtpConfiguration.adml を_ _C: Windows \\ \\ PolicyDefinitions \\ ja-US にコピーする_

    グループ ポリシー管理用テンプレートに [セントラル ストア](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)を使用している場合は、構成パッケージから次のファイルをコピーします。
    
    - SysVol ポリシー _\\ \\ \<forest.root\> \\ \\ \<forest.root\> \\ \\ PolicyDefinitions に AtpConfiguration.admx をコピーする_

    - _AtpConfiguration.adml を_ _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ ポリシー \\ PolicyDefinitions \\ en-US にコピーする_

2.  グループ ポリシー [管理コンソールを開き](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)、構成する GPO を右クリックし、[編集] を **クリックします**。

3.  グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

4.  [ポリシー **] をクリックし**、[管理 **用テンプレート] をクリックします**。

5.  [Windows **コンポーネント] をクリック** し **、[ATP] Windows Defenderクリックします**。

6.  デバイスからのサンプル共有を有効または無効にする場合に選択します。

>[!NOTE]
> 値を設定しない場合、既定値はサンプル コレクションを有効にします。


## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定

### <a name="update-endpoint-protection-configuration"></a>エンドポイント保護構成の更新

オンボーディング スクリプトを構成したら、同じグループ ポリシーの編集を続けてエンドポイント保護構成を追加します。 Windows 10 または Server 2019 を実行しているシステムからグループ ポリシーの編集を実行して、必要なすべての Microsoft Defender ウイルス対策機能を確実に使用します。 Defender ATP 構成設定を登録するには、グループ ポリシー オブジェクトを閉じて再度開く必要がある場合があります。

すべてのポリシーは 、 の下に位置します `Computer Configuration\Policies\Administrative Templates` 。

**ポリシーの場所:** \Windows Components\Windows Defender ATP

ポリシー | Setting 
:---|:---
Enable\Disable Sample collection|   [有効] - [コンピューターでサンプル コレクションを有効にする] チェック ボックスをオンにします。

<br/>

**ポリシーの場所:**  \Windows Components\Windows Defender ウイルス対策

ポリシー | Setting 
:---|:---
望ましくない可能性があるアプリケーションの検出を構成する | 有効、ブロック

<br/>

**ポリシーの場所:** \Windows Components\Windows Defender ウイルス対策\MAPS

ポリシー | Setting 
:---|:---
Microsoft MAPS に参加する | 有効、高度なマップ
詳細な分析が必要な場合にファイル サンプルを送信する | 有効、安全なサンプルの送信

<br/>

**ポリシーの場所:** \Windows Components\Windows Defenderウイルス対策\リアルタイム保護

ポリシー | Setting 
:---|:---
リアルタイム保護をオフにする|無効
動作の監視を有効にする|有効
ダウンロードしたファイルと添付ファイルをスキャンする|有効
コンピューター上のファイルとプログラムのアクティビティを監視する|有効

<br/>

**ポリシーの場所:**  \Windows Components\Windows Defenderウイルス対策\スキャン

これらの設定は、エンドポイントの定期的なスキャンを構成します。 毎週のクイック スキャンを実行することをお勧めします。パフォーマンスが許容されます。

ポリシー | Setting 
:---|:---
スケジュールされたスキャンを実行する前に、最新のウイルスとスパイウェアのセキュリティ インテリジェンスを確認する |有効


<br/>

**ポリシーの場所:** \Windows Components\Windows Defender ウイルス対策\Windows Defender Exploit Guard\Attack Surface Reduction

[攻撃表面の縮小ルールのカスタマイズ] から攻撃表面の縮小 GUID [の現在のリストを取得する](customize-attack-surface-reduction.md)

1. [攻撃表面 **縮小の構成] ポリシーを開** きます。

1. **[有効]** を選択します。

1. [表示] **ボタンを** 選択します。

1. [値の名前] フィールドに **、値が** 2 の各 GUID を追加します。

   これにより、監査専用に設定されます。

   ![攻撃表面の縮小構成のイメージ](images/asr-guid.png)



ポリシー | Setting 
:---|:---
フォルダー アクセスの制御を構成する| 有効、監査モード



## <a name="offboard-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオフボードする
セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. Microsoft Defender セキュリティ センターからオフボード パッケージ [を取得します](https://securitycenter.windows.com/)。

    1. ナビゲーション ウィンドウで、[設定] [**オフボード]**  >  **を選択します**。

    1. オペレーティング システムとして [Windows 10] を選択します。
    
    1. [展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。

    1. [パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。

2. .zip ファイルの内容を、デバイスがアクセスできる共有の読み取り専用の場所に展開します。 *-MM-DD.cmd WindowsDefenderATPOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。

3. グループ ポリシー [管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。

4. グループ ポリシー **管理エディターで、[****コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。

5. [スケジュールされたタスク] **を右クリック** し、[新規] をポイント **し**、[イミディエイト タスク] **をクリックします**。

6. 開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ オプション] の [ローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) **を選択します**。

7. [ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **]** チェック ボックスをオンにします。

8. [アクション] タブ **に移動し** 、[ **新規...] をクリックします**。[アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。 共有ファイルのファイル名と場所を  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd ファイルを入力* します。

9. **[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。


## <a name="monitor-device-configuration"></a>デバイス構成の監視
グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。 監視は、ポータルまたはさまざまな展開ツールを使用して直接実行できます。

## <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する
1. [Microsoft [Defender セキュリティ センター] に移動します](https://securitycenter.windows.com/)。
2. [デバイス **] リストをクリックします**。
3. デバイスが表示されているのを確認します。

> [!NOTE]
> デバイスが [デバイス] リストに表示を開始するには、数日 **かかる場合があります**。 これには、ポリシーがデバイスに配布される時間、ユーザーがログオンする前にかかる時間、エンドポイントがレポートを開始するのにかかる時間が含まれます。


## <a name="related-topics"></a>関連項目
- [Microsoft Endpoint Configuration Manager を使用した Windows 10 デバイスのオンボード](configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
- [新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](troubleshoot-onboarding.md)
