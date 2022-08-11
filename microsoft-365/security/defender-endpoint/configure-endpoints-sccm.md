---
title: Configuration Managerを使用して Windows デバイスをオンボードする
description: Configuration Managerを使用してデバイスに構成パッケージを展開し、Defender for Endpoint サービスにオンボードします。
keywords: sccm を使用したデバイスのオンボード、デバイス管理、Microsoft Defender for Endpointデバイスの構成
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
ms.date: 09/22/2021
ms.technology: mde
ms.openlocfilehash: 6a311d0fb1edeff8e8eb72148ffc08dfb945cbbe
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "67280831"
---
# <a name="onboard-windows-devices-using-configuration-manager"></a>Configuration Managerを使用して Windows デバイスをオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Endpoint Configuration Manager現在のブランチ
- System Center 2012 R2 Configuration Manager

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)


Configuration Managerを使用して、エンドポイントをMicrosoft Defender for Endpoint サービスにオンボードできます。 

Configuration Managerを使用してデバイスをオンボードするために使用できるオプションがいくつかあります。
- [System Center Configuration Managerを使用してデバイスをオンボードする](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [テナントのアタッチ](/mem/configmgr/tenant-attach/)



Windows Server 2012 R2 とWindows Server 2016の場合は、オンボード手順を完了したら、[System Center Endpoint Protection クライアントを構成して更新](onboard-downlevel.md#configure-and-update-system-center-endpoint-protection-clients)する必要があります。

> [!NOTE]
> Defender for Endpoint では、 [Out-Of-Box Experience (OOBE)](/windows-hardware/test/assessments/out-of-box-experience) フェーズ中のオンボードはサポートされません。 Windows のインストールまたはアップグレードを実行した後、ユーザーが OOBE を完了していることを確認します。
>
> デバイスがオンボードされているかどうかを継続的に確認するために、Configuration Manager アプリケーションに検出ルールを作成できます。 アプリケーションは、パッケージやプログラムとは異なる種類のオブジェクトです。
> デバイスがまだオンボードされていない場合 (保留中の OOBE の完了またはその他の理由により)、Configuration Managerは、ルールが状態変更を検出するまでデバイスのオンボードを再試行します。
>
> この動作は、(種類 REG_DWORDの) "OnboardingState" レジストリ値が 1 かどうかを確認する検出規則を作成することによって実現できます。
> このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" の下にあります。
詳細については、「[System Center 2012 R2 Configuration Managerで検出方法を構成する](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)」を参照してください。

### <a name="configure-sample-collection-settings"></a>サンプル コレクションの設定を構成する

デバイスごとに、詳細な分析のためにファイルを送信する要求がMicrosoft 365 Defenderによって行われたときに、デバイスからサンプルを収集できるかどうかを示す構成値を設定できます。

> [!NOTE]
> これらの構成設定は通常、Configuration Managerを使用して行われます。

Configuration Managerで構成項目のコンプライアンス規則を設定して、デバイスのサンプル共有設定を変更できます。

このルールは、対象となるデバイスのレジストリ キーの値を設定して、苦情が発生していることを確認する *修復* コンプライアンス規則構成項目である必要があります。

構成は、次のレジストリ キー エントリを使用して設定されます。

```text
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

ここで、キーの種類は D-WORD です。 使用可能な値は次のとおりです。

- 0: このデバイスからのサンプル共有を許可しない
- 1: このデバイスからのすべてのファイルの種類の共有を許可する

レジストリ キーが存在しない場合の既定値は 1 です。

System Center Configuration Managerコンプライアンスの詳細については、「[System Center 2012 R2 Configuration Managerのコンプライアンス設定の概要](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))」を参照してください。

## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定

デバイスをサービスにオンボードした後は、次の推奨構成設定で有効にすることで、付属の脅威保護機能を利用することが重要です。

### <a name="device-collection-configuration"></a>デバイス コレクションの構成

エンドポイント Configuration Managerバージョン 2002 以降を使用している場合は、サーバーまたは下位レベルのクライアントを含めるために展開を広げることを選択できます。

### <a name="next-generation-protection-configuration"></a>次世代の保護構成

次の構成設定をお勧めします。

#### <a name="scan"></a>スキャン

- USB ドライブなどのリムーバブル ストレージ デバイスをスキャンする: はい

#### <a name="real-time-protection"></a>リアルタイム保護

- 動作監視を有効にする: はい
- ダウンロード時およびインストール前に望ましくない可能性があるアプリケーションに対する保護を有効にする: はい

#### <a name="cloud-protection-service"></a>Cloud Protection Service

- Cloud Protection Service メンバーシップの種類: 高度なメンバーシップ

#### <a name="attack-surface-reduction"></a>攻撃面の縮小

監査に使用できるすべてのルールを構成します。

> [!NOTE]
> これらのアクティビティをブロックすると、正当なビジネス プロセスが中断される可能性があります。 最善の方法は、すべてを監査に設定し、有効にしても安全なものを特定し、誤検知検出がないエンドポイントでこれらの設定を有効にすることです。

Microsoft System Center Configuration Manager (SCCM) を介して AV および ASR ポリシーを展開するには、次の手順に従います。

- Endpoint Protection を有効にし、カスタム クライアント設定を構成します。
- コマンド プロンプトから Endpoint Protection クライアントをインストールします。
- Endpoint Protection クライアントのインストールを確認します。

##### <a name="enable-endpoint-protection-and-configure-custom-client-settings"></a>Endpoint Protection を有効にし、カスタム クライアント設定を構成する
次の手順に従って、カスタム クライアント設定のエンドポイント保護と構成を有効にします。

1. Configuration Manager コンソールで、[管理] をクリックします **。**
1. **[管理**] ワークスペースで、[**クライアント設定] をクリックします。**
1. [**ホーム**] タブの [**作成**] グループで、[**カスタム クライアント デバイス設定の作成**] をクリックします。
1. [**カスタム クライアント デバイス設定の作成]** ダイアログ ボックスで、設定のグループの名前と説明を入力し、**Endpoint Protection** を選択します。
1. 必要な Endpoint Protection クライアント設定を構成します。 構成できる Endpoint Protection クライアント設定の完全な一覧については、「クライアント設定について」の「Endpoint Protection」セクションを参照してください [。](/mem/configmgr/core/clients/deploy/about-client-settings#endpoint-protection)

    > [!IMPORTANT]
    > Endpoint Protection のクライアント設定を構成する前に、Endpoint Protection サイト システムの役割をインストールします。

1. [ **OK] を** クリックして、[ **カスタム クライアント デバイス設定の作成]** ダイアログ ボックスを閉じます。 新しいクライアント設定は、[**管理**] ワークスペースの **[クライアント設定]** ノードに表示されます。
1. 次に、カスタム クライアント設定をコレクションにデプロイします。 展開するカスタム クライアント設定を選択します。 [ **ホーム** ] タブの [ **クライアント設定]** グループで、[展開] をクリック **します。**
1. [ **コレクションの選択** ] ダイアログ ボックスで、クライアント設定を展開するコレクションを選択し、[OK] をクリック **します。** 新しいデプロイは、詳細ウィンドウの [ **展開]** タブに表示されます。

クライアントは、次にクライアント ポリシーをダウンロードするときに、これらの設定で構成されます。 詳細については、「[Configuration Manager クライアントのポリシーの取得を開始する」を参照してください。](/mem/configmgr/core/clients/manage/manage-clients)


##### <a name="installation-of-endpoint-protection-client-from-a-command-prompt"></a>コマンド プロンプトからの Endpoint Protection クライアントのインストール
コマンド プロンプトからエンドポイント保護クライアントのインストールを完了するには、次の手順に従います。

1. **Configuration Manager** インストール フォルダーのクライアント フォルダーから、Endpoint Protection **クライアント** ソフトウェアをインストールするコンピューターにscepinstall.exeをコピーします。
1. 管理者としてコマンド プロンプトを開きます。 インストーラーを使用してディレクトリをフォルダーに変更します。 次に、必要な追加のコマンド ライン プロパティを追加して実行 ```scepinstall.exe```します。

     |**プロパティ**  |**説明**  |
     |---------|---------|
     |```/s```      |インストーラーをサイレント モードで実行する|
     |```/q```      |セットアップ ファイルをサイレント モードで展開する|
     |```/i```      |インストーラーを通常どおりに実行する|
     |```/policy``` |インストール中にクライアントを構成するマルウェア対策ポリシー ファイルを指定する|
     |```/sqmoptin```|Microsoft カスタマー エクスペリエンス向上プログラム (CEIP) へのオプトイン|

1. 画面の指示に従って、クライアントのインストールを完了します。
1. 最新の更新プログラム定義パッケージをダウンロードした場合は、パッケージをクライアント コンピューターにコピーし、定義パッケージをダブルクリックしてインストールします。

     > [!NOTE]
     > Endpoint Protection クライアントのインストールが完了すると、クライアントは定義の更新チェックを自動的に実行します。 この更新プログラムのチェックが成功した場合は、最新の定義更新プログラム パッケージを手動でインストールする必要はありません。

**例: マルウェア対策ポリシーを使用してクライアントをインストールする**

```scepinstall.exe /policy <full path>\<policy file>```

##### <a name="verify-the-endpoint-protection-client-installation"></a>Endpoint Protection クライアントのインストールを確認する

参照コンピューターに Endpoint Protection クライアントをインストールした後、クライアントが正しく動作していることを確認します。

1. 参照コンピューターで、Windows 通知領域から **System Center Endpoint Protection** を開きます。
1. **[System Center Endpoint Protection**] ダイアログ ボックスの [**ホーム**] タブで、[**リアルタイム保護**] が **[オン]** に設定されていることを確認します。
1. **ウイルスとスパイウェアの定義****に対して最新** の状態が表示されていることを確認します。
1. 参照コンピューターでイメージングの準備が整っていることを確認するには、[**スキャン オプション**] で [**完全**] を選択し、[**今すぐスキャン**] をクリックします。


#### <a name="network-protection"></a>ネットワーク保護

監査モードまたはブロック モードでネットワーク保護を有効にする前に、 [サポート ページ](https://support.microsoft.com/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)から取得できるマルウェア対策プラットフォームの更新プログラムがインストールされていることを確認してください。

#### <a name="controlled-folder-access"></a>コントロールされたフォルダー アクセス

監査モードで少なくとも 30 日間機能を有効にします。 この期間を過ぎると、検出を確認し、保護されたディレクトリへの書き込みを許可されているアプリケーションの一覧を作成します。

詳細については、「 [制御されたフォルダー アクセスの評価」を](evaluate-controlled-folder-access.md)参照してください。

## <a name="run-a-detection-test-to-verify-onboarding"></a>検出テストを実行してオンボードを検証する

デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「[新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)」 を参照してください。

## <a name="offboard-devices-using-configuration-manager"></a>構成マネージャーを使用してデバイスをオフボードする

セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>Microsoft エンドポイント マネージャー現在のブランチを使用するオフボード デバイス

Microsoft エンドポイント マネージャー現在のブランチを使用する場合は、「[オフボード構成ファイルを作成する](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)」を参照してください。

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>System Center 2012 R2 Configuration Managerを使用したオフボード デバイス

1. ポータルからオフボード パッケージ<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>取得します。
    1. ナビゲーション ウィンドウで、[設定 **エンドポイント** \> **デバイス管理**\>**オフボーディング****]** \> を選択します。  
    1. オペレーティング システムとしてWindows 10またはWindows 11を選択します。
    1. **[展開方法]** フィールドで、**System Center Configuration Manager 2012/2012 R2/1511/1602** を選択します。
    1. [ **パッケージのダウンロード**] を選択し、.zip ファイルを保存します。

2. パッケージを展開するネットワーク管理者がアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* という名前のファイルが必要です。

3. [System Center 2012 R2 のパッケージとプログラム](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))のConfiguration Manager記事の手順に従って、パッケージを展開します。

   パッケージをデプロイする定義済みのデバイス コレクションを選択します。

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

## <a name="monitor-device-configuration"></a>デバイス構成を監視する

Microsoft エンドポイント マネージャー現在のブランチを使用している場合は、Configuration Manager コンソールで組み込みの Defender for Endpoint ダッシュボードを使用します。 詳細については、「 [Defender for Endpoint - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)」を参照してください。

System Center 2012 R2 Configuration Managerを使用している場合、監視は次の 2 つの部分で構成されます。

1. 構成パッケージが正しくデプロイされ、ネットワーク内のデバイスで実行 (または正常に実行されました) されていることを確認します。

2. デバイスが Defender for Endpoint サービスに準拠していることを確認します (これにより、デバイスはオンボード プロセスを完了でき、サービスにデータをレポートし続けることができます)。

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>構成パッケージが正しくデプロイされたことを確認する

1. Configuration Manager コンソールで、ナビゲーション ウィンドウの下部にある [**監視**] をクリックします。

2. [ **概要** ] を選択し、[ **デプロイ] を選択します**。

3. パッケージ名を含むデプロイを選択します。

4. **[完了の統計**] と [コンテンツの **状態] で状態** インジケーターを確認します。

    展開に失敗した場合 ( **エラー**、 **要件が満たされていない**、または **失敗した状態** のデバイス)、デバイスのトラブルシューティングが必要になる場合があります。 詳細については、「[Microsoft Defender for Endpointオンボードの問題のトラブルシューティング」を](troubleshoot-onboarding.md)参照してください。

    :::image type="content" source="images/sccm-deployment.png" alt-text="エラーなしで正常にデプロイされたことを示すConfiguration Manager" lightbox="images/sccm-deployment.png":::

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>デバイスがMicrosoft Defender for Endpoint サービスに準拠していることを確認する

System Center 2012 R2 Configuration Managerで構成項目のコンプライアンス規則を設定して、展開を監視できます。

この規則は、ターゲット デバイス *上の* レジストリ キーの値を監視する修復しないコンプライアンス規則構成項目である必要があります。

次のレジストリ キー エントリを監視します。

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

詳細については、「[System Center 2012 R2 Configuration Managerのコンプライアンス設定の概要](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))」を参照してください。

## <a name="related-topics"></a>関連項目
- [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
- [モバイル デバイス管理ツールを使用した Windows デバイスのオンボード](configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
- [新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
