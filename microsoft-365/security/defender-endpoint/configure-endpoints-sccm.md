---
title: Configuration Managerを使用してWindowsデバイスをオンボードする
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
ms.openlocfilehash: d67a4ca067f16d74b15a1d7ece5c47d563f1a941
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471915"
---
# <a name="onboard-windows-devices-using-configuration-manager"></a>Configuration Managerを使用してWindowsデバイスをオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 現在のブランチMicrosoft Endpoint Configuration Manager
- System Center 2012 R2 Configuration Manager

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)


Configuration Managerを使用して、エンドポイントをMicrosoft Defender for Endpoint サービスにオンボードできます。 

Configuration Managerを使用してデバイスをオンボードするために使用できるオプションがいくつかあります。
- [System Center Configuration Managerを使用してデバイスをオンボードする](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [テナントのアタッチ](/mem/configmgr/tenant-attach/)



Windows Server 2012 R2 とWindows Server 2016の場合は、オンボード手順を完了したら、[System Center Endpoint Protection クライアントを構成して更新](onboard-downlevel.md#configure-and-update-system-center-endpoint-protection-clients)する必要があります。

> [!NOTE]
> Defender for Endpoint では、 [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) フェーズ中のオンボードはサポートされません。 インストールまたはアップグレードWindows実行した後、ユーザーが OOBE を完了していることを確認します。
>
> デバイスがオンボードされているかどうかを継続的に確認するために、Configuration Manager アプリケーションに検出ルールを作成できます。 アプリケーションは、パッケージやプログラムとは異なる種類のオブジェクトです。
> デバイスがまだオンボードされていない場合 (保留中の OOBE の完了またはその他の理由により)、Configuration Managerは、ルールが状態変更を検出するまでデバイスのオンボードを再試行します。
>
> この動作は、(種類 REG_DWORDの) "OnboardingState" レジストリ値が 1 かどうかを確認する検出規則を作成することによって実現できます。
> このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" の下にあります。
詳細については、「[System Center 2012 R2 Configuration Managerでの検出方法の構成](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)」を参照してください。

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

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>現在のブランチを使用Microsoft エンドポイント マネージャーオフボード デバイス

現在のブランチMicrosoft エンドポイント マネージャー使用する場合は、「[オフボード構成ファイルを作成する](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)」を参照してください。

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>System Center 2012 R2 Configuration Managerを使用するオフボード デバイス

1. ポータルからオフボード パッケージ<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>取得します。
    1. ナビゲーション ウィンドウで、[**エンドポイント** \> **デバイス管理**\>**オフボード****設定**\>] を選択します。  
    1. オペレーティング システムとしてWindows 10またはWindows 11を選択します。
    1. **[展開方法]** フィールドで、**System Center Configuration Manager 2012/2012 R2/1511/1602** を選択します。
    1. [ **パッケージのダウンロード**] を選択し、.zip ファイルを保存します。

2. パッケージを展開するネットワーク管理者がアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* という名前のファイルが必要です。

3. System Center [2012 R2 Configuration Managerの記事の「パッケージとプログラム」の手順に従って、パッケージを](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))展開します。

   パッケージをデプロイする定義済みのデバイス コレクションを選択します。

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

## <a name="monitor-device-configuration"></a>デバイス構成を監視する

現在のブランチMicrosoft エンドポイント マネージャー使用している場合は、Configuration Manager コンソールで組み込みの Defender for Endpoint ダッシュボードを使用します。 詳細については、「 [Defender for Endpoint - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)」を参照してください。

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

System Center 2012 R2 Configuration Managerで構成項目のコンプライアンス規則を設定して、デプロイを監視できます。

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
