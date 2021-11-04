---
title: Configuration Manager を使用した Windows 10 デバイスのオンボード
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
search.appverid:
- MET150
description: Configuration Manager を使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 1d551f0411910f1a8db99ee76a61204c8c475348
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754757"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Configuration Manager を使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- System Center 2012 R2 Configuration Manager

### <a name="onboard-devices-using-system-center-configuration-manager"></a>デバイスを使用したオンボード System Center Configuration Manager

1. サービス オンボーディング ウィザードからダウンロード *.zipファイル*(DeviceComplianceOnboardingPackage.zip) の Configuration Manager 構成パッケージを開きます。 パッケージは、次のファイルから取得<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター。</a>

2. ナビゲーション ウィンドウで、[デバイス オンボーディング オン <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**ボーディング] 設定**</a>  >  **を**  >  **選択します**。

3. [展開 **方法] フィールド** で、[Microsoft Endpoint Configuration Manager **2012/2012 R2/1511/1602] を選択します**。

4. [ **パッケージのダウンロード]** を選択し、ファイルを.zipします。

5. パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。 *DeviceComplianceOnboardingScript.cmd という名前のファイルが必要です*。

6. [2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))の「パッケージとプログラム」の記事の手順に従ってSystem Centerパッケージを展開します。

7. パッケージを展開する定義済みのデバイス コレクションを選択します。

> [!NOTE]
> Microsoft 365エンドポイントのデータ損失防止では、アウトオブボックス エクスペリエンス[(OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)フェーズのオンボーディングはサポートされていません。 インストールまたはアップグレードの実行後にユーザーが OOBE をWindows確認します。

> [!TIP]
> デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)。
>
> Configuration Manager アプリケーションで検出ルールを作成して、デバイスがオンボードされた場合に継続的にチェックを行える点に注意してください。 アプリケーションは、パッケージやプログラムとは異なる種類のオブジェクトです。
> デバイスがまだオンボードされていない場合 (保留中の OOBE の完了その他の理由により)、Configuration Manager は、ルールが状態の変更を検出するまで、デバイスのオンボードを再試行します。
>
> この動作は、"OnboardingState" レジストリ値 (タイプ REG_DWORD) が 1 の場合に検出ルールチェックを作成することで実現できます。
> このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" の下にあります。
詳細については[、「Configure Detection Methods in System Center 2012 R2 Configuration Manager」を参照してください](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)。

### <a name="configure-sample-collection-settings"></a>サンプル コレクション設定の構成

デバイスごとに構成値を設定して、Microsoft Defender セキュリティ センター から詳細分析用にファイルを送信する要求が行われたときに、デバイスからサンプルを収集できるかどうかを示します。

> [!NOTE]
> これらの構成設定は、通常、Configuration Manager を介して行われます。

Configuration Manager で構成アイテムのコンプライアンス ルールを設定して、デバイスのサンプル共有設定を変更できます。

このルールは、対象デバイスのレジストリ キーの値を設定して、苦情を確実に受け取るコンプライアンス ルール構成項目を修復する必要があります。

構成は、次のレジストリ キー エントリを使用して設定されます。

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
ここで、<br>
キーの種類は D-WORD です。 <br>
使用可能な値は次のとおりです。
- 0 - このデバイスからのサンプル共有を許可しない
- 1 - このデバイスからすべての種類のファイルを共有できます

レジストリ キーが存在しない場合の既定値は 1 です。

コンプライアンスの詳細については、「System Center Configuration Manager [System Center 2012 R2](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))Configuration Manager のコンプライアンス設定の概要」を参照してください。


## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定
デバイスをサービスにオンボーディングした後、以下の推奨構成設定でデバイスを有効にすることで、含まれている脅威保護機能を活用することが重要です。

### <a name="device-collection-configuration"></a>デバイス コレクションの構成
バージョン 2002 以降のエンドポイント構成マネージャーを使用している場合は、展開を拡大してサーバーまたはダウンレベルのクライアントを含める方法を選択できます。


### <a name="next-generation-protection-configuration"></a>次世代の保護構成

次の構成設定をお勧めします。

**スキャン**

- USB ドライブなどのリムーバブル 記憶域デバイスをスキャンする: はい

**リアルタイム保護**

- 動作監視を有効にする: はい
- ダウンロード時およびインストール前に望ましくない可能性があるアプリケーションに対する保護を有効にする: はい

**クラウド保護サービス**

- Cloud Protection Service メンバーシップの種類: 高度なメンバーシップ

**攻撃表面の縮小** 使用可能なすべてのルールを [監査] に構成します。

> [!NOTE]
> これらのアクティビティをブロックすると、正当なビジネス プロセスが中断される可能性があります。 最善の方法は、すべてを監査に設定し、有効にしても安全な設定を特定し、誤検知検出を持つエンドポイントでこれらの設定を有効にします。

**ネットワーク保護**

監査モードまたはブロック モードでネットワーク保護を有効にする前に、サポート ページから入手できるマルウェア対策プラットフォーム更新プログラムがインストール [されていることを確認してください](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)。


**制御されたフォルダー アクセス**

監査モードで機能を 30 日以上有効にします。 この期間が終了した後、検出を確認し、保護されたディレクトリへの書き込みを許可するアプリケーションの一覧を作成します。

詳細については、「管理フォルダー アクセス [の評価」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)。


## <a name="offboard-devices-using-configuration-manager"></a>Configuration Manager を使用したオフボード デバイス

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>現在のブランチを使用Microsoft Endpoint Configuration Managerオフボード デバイス

現在のブランチでMicrosoft Endpoint Configuration Manager場合は、「[オフボード構成ファイルを作成する」を参照してください](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>2012 R2 Configuration Manager System Centerを使用するオフボード デバイス

1. 次の方法でオフボード<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">パッケージを取得Microsoft 365 コンプライアンス センター。</a>

2. ナビゲーション ウィンドウで、[デバイスオンボーディング <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**設定**</a>  >   **オフボード]** >  **を選択します**。

3. オペレーティング システムWindows 10を選択します。

4. [展開 **方法] フィールド** で、[Microsoft Endpoint Configuration Manager **2012/2012 R2/1511/1602] を選択します**。

5. [ **パッケージのダウンロード]** を選択し、ファイルを.zipします。

6. パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。 *-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。

7. [2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))の「パッケージとプログラム」の記事の手順に従ってSystem Centerパッケージを展開します。

8. パッケージを展開する定義済みのデバイス コレクションを選択します。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。


## <a name="monitor-device-configuration"></a>デバイス構成の監視

現在のブランチでMicrosoft Endpoint Configuration Manager場合は、Configuration Manager コンソールの組み込みの Microsoft Defender for Endpoint ダッシュボードを使用します。 詳細については [、「Microsoft Defender Advanced Threat Protection - Monitor」を参照してください](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。

2012 R2 Configuration Manager System Center使用している場合、監視は次の 2 つの部分で構成されます。

1. 構成パッケージが正しく展開され、ネットワーク内のデバイスで実行 (または正常に実行) されていることを確認します。

2. デバイスが Microsoft 365 Endpoint データ損失防止サービスに準拠しているのを確認します (これにより、デバイスはオンボーディング プロセスを完了し、引き続きサービスにデータを報告できます)。

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>構成パッケージが正しく展開されていることを確認する

1. Configuration Manager コンソールで、ナビゲーション ウィンドウ **の** 下部にある [監視] をクリックします。

2. [概要 **] を選択** し、[ **展開] を選択します**。

3. パッケージ名を使用して展開を選択します。

4. [完了統計] と [コンテンツ **の状態] の下の** 状態インジケーター **を確認します**。

    失敗した展開 (エラー、要件が満たされていないデバイス、または失敗した状態) がある場合は、デバイスのトラブルシューティングが必要な場合があります。  詳細については、「Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング [」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。

    ![エラーがない展開が成功した構成マネージャー。](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>デバイスがエンドポイント データ損失防止サービスMicrosoft 365準拠しているを確認する

2012 R2 Configuration Manager で構成アイテムのコンプライアンス System Center設定して、展開を監視できます。

> [!NOTE]
> この手順とレジストリ エントリは、エンドポイント DLP および Advanced Threat Protection に適用されます。

このルールは *、対象となる* デバイスのレジストリ キーの値を監視する、修復されていないコンプライアンス ルール構成アイテムである必要があります。

次のレジストリ キー エントリを監視します。
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
詳細については[、「2012 R2](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))Configuration Manager のコンプライアンスSystem Center概要」を参照してください。

## <a name="related-topics"></a>関連トピック
- [グループ ポリシー Windows 10デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](dlp-configure-endpoints-vdi.md)
- [新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)