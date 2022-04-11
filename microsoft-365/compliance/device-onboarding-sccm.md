---
title: Windows 10を使用してデバイスをオンボードし、デバイスをWindows 11 Configuration Manager
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
description: Configuration Managerを使用して構成パッケージをデバイスに展開し、サービスにオンボードします。
ms.openlocfilehash: 2cca9cc073ca08c7fabb19511a4253e4a682057a
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760715"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-configuration-manager"></a>Windows 10を使用してデバイスをオンボードし、デバイスをWindows 11 Configuration Manager

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

### <a name="onboard-devices-using-system-center-configuration-manager"></a>System Center Configuration Managerを使用してデバイスをオンボードする

1. [Microsoft コンプライアンス センター](https://compliance.microsoft.com/)から構成パッケージ .zip ファイル (*DeviceComplianceOnboardingPackage.zip*) を取得します。

2. ナビゲーション ウィンドウで、<a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**設定**</a> > **Device OnboardingOnboarding** >  を選択します。

3. **[展開方法]** フィールドで、**Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** を選択します。

4. [ **パッケージのダウンロード**] を選択し、.zip ファイルを保存します。

5. パッケージを展開するネットワーク管理者がアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *DeviceComplianceOnboardingScript.cmd* という名前のファイルが必要です。

6. System Center [2012 R2 Configuration Managerの記事の「パッケージとプログラム」の手順に従って、パッケージを](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))展開します。

7. パッケージをデプロイする定義済みのデバイス コレクションを選択します。

> [!NOTE]
> Microsoft 365情報保護では、[Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) フェーズ中のオンボードはサポートされません。 インストールまたはアップグレードWindows実行した後、ユーザーが OOBE を完了していることを確認します。

> [!TIP]
> デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「[新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)」 を参照してください。
>
> デバイスがオンボードされているかどうかを継続的に確認するために、Configuration Manager アプリケーションに検出ルールを作成できます。 アプリケーションは、パッケージやプログラムとは異なる種類のオブジェクトです。
> デバイスがまだオンボードされていない場合 (保留中の OOBE の完了またはその他の理由により)、Configuration Managerは、ルールが状態変更を検出するまでデバイスのオンボードを再試行します。
>
> この動作は、(種類 REG_DWORDの) "OnboardingState" レジストリ値が 1 かどうかを確認する検出規則を作成することによって実現できます。
> このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" の下にあります。
詳細については、「[System Center 2012 R2 Configuration Managerでの検出方法の構成](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)」を参照してください。

### <a name="configure-sample-collection-settings"></a>サンプル コレクションの設定を構成する

デバイスごとに、詳細な分析のためにファイルを送信する要求がMicrosoft Defender セキュリティ センターによって行われたときに、デバイスからサンプルを収集できるかどうかを示す構成値を設定できます。

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

ここで、

キーの種類は D-WORD です。

使用可能な値は次のとおりです。

- 0 - このデバイスからのサンプル共有を許可しない
- 1 - このデバイスからのすべてのファイルの種類の共有を許可する

レジストリ キーが存在しない場合の既定値は 1 です。

System Center Configuration Managerコンプライアンスの詳細については、「[System Center 2012 R2 Configuration Managerのコンプライアンス設定の概要](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))」を参照してください。


## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定

デバイスをサービスにオンボードした後は、次の推奨構成設定で有効にすることで、付属の脅威保護機能を利用することが重要です。

### <a name="device-collection-configuration"></a>デバイス コレクションの構成

エンドポイント Configuration Managerバージョン 2002 以降を使用している場合は、サーバーまたは下位レベルのクライアントを含めるために展開を広げることを選択できます。

### <a name="next-generation-protection-configuration"></a>次世代の保護構成

次の構成設定をお勧めします。

**スキャン**

- USB ドライブなどのリムーバブル ストレージ デバイスをスキャンする: はい

**リアルタイム保護**

- 動作監視を有効にする: はい
- ダウンロード時およびインストール前に望ましくない可能性があるアプリケーションに対する保護を有効にする: はい

**Cloud Protection Service**

- Cloud Protection Service メンバーシップの種類: 高度なメンバーシップ

**攻撃面の縮小** 監査に使用できるすべてのルールを構成します。

> [!NOTE]
> これらのアクティビティをブロックすると、正当なビジネス プロセスが中断される可能性があります。 最善の方法は、すべてを監査に設定し、有効にしても安全なものを特定し、誤検知検出がないエンドポイントでこれらの設定を有効にすることです。

**ネットワーク保護**

監査モードまたはブロック モードでネットワーク保護を有効にする前に、 [サポート ページ](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)から取得できるマルウェア対策プラットフォームの更新プログラムがインストールされていることを確認してください。

**制御されたフォルダー アクセス**

監査モードで少なくとも 30 日間機能を有効にします。 この期間を過ぎると、検出を確認し、保護されたディレクトリへの書き込みを許可されているアプリケーションの一覧を作成します。

詳細については、「 [制御されたフォルダー アクセスの評価」を](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)参照してください。

## <a name="offboard-devices-using-configuration-manager"></a>構成マネージャーを使用してデバイスをオフボードする

セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>現在のブランチを使用Microsoft Endpoint Configuration Managerオフボード デバイス

現在のブランチMicrosoft Endpoint Configuration Manager使用する場合は、「[オフボード構成ファイルを作成する](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)」を参照してください。

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>System Center 2012 R2 Configuration Managerを使用するオフボード デバイス

1. オフボード パッケージを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター</a>から取得します。

2. ナビゲーション ウィンドウで、<a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**設定**</a> >  **Device onboardingOffboarding を**> 選択します。

3. オペレーティング システムとしてWindows 10を選択します。

4. **[展開方法]** フィールドで、**Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** を選択します。

5. [ **パッケージのダウンロード**] を選択し、.zip ファイルを保存します。

6. パッケージを展開するネットワーク管理者がアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* という名前のファイルが必要です。

7. System Center [2012 R2 Configuration Managerの記事の「パッケージとプログラム」の手順に従って、パッケージを](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))展開します。

8. パッケージをデプロイする定義済みのデバイス コレクションを選択します。

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

## <a name="monitor-device-configuration"></a>デバイス構成を監視する

現在のブランチMicrosoft Endpoint Configuration Manager使用している場合は、Configuration Manager コンソールで組み込みのMicrosoft Defender for Endpoint ダッシュボードを使用します。 詳細については、「 [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)」を参照してください。

System Center 2012 R2 Configuration Managerを使用している場合、監視は次の 2 つの部分で構成されます。

1. 構成パッケージが正しくデプロイされ、ネットワーク内のデバイスで実行 (または正常に実行されました) されていることを確認します。

2. デバイスがMicrosoft 365デバイスオンボード サービスに準拠していることを確認します (これにより、デバイスがオンボード プロセスを完了し、サービスにデータをレポートし続けることができます)。

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>構成パッケージが正しくデプロイされたことを確認する

1. Configuration Manager コンソールで、ナビゲーション ウィンドウの下部にある [**監視**] をクリックします。

2. [ **概要** ] を選択し、[ **デプロイ] を選択します**。

3. パッケージ名を含むデプロイを選択します。

4. **[完了の統計**] と [コンテンツの **状態] で状態** インジケーターを確認します。

    展開に失敗した場合 ( **エラー**、 **要件が満たされていない**、または **失敗した状態** のデバイス)、デバイスのトラブルシューティングが必要になる場合があります。 詳細については、「 [Microsoft Defender Advanced Threat Protection のオンボードに関する問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)」を参照してください。

    ![Configuration Manager、エラーなしで正常にデプロイされたことを示します。](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>デバイスがMicrosoft 365 エンドポイントデータ損失防止サービスに準拠していることを確認します

System Center 2012 R2 Configuration Managerで構成項目のコンプライアンス規則を設定して、デプロイを監視できます。

> [!NOTE]
> この手順とレジストリ エントリは、Endpoint DLP と Defender for Endpoint に適用されます。

この規則は、ターゲット デバイス *上の* レジストリ キーの値を監視する修復しないコンプライアンス規則構成項目である必要があります。

次のレジストリ キー エントリを監視します。

```text
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

詳細については、「[System Center 2012 R2 Configuration Managerのコンプライアンス設定の概要](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))」を参照してください。

## <a name="related-topics"></a>関連項目

- [グループ ポリシーを使用してWindows 10デバイスとWindows 11 デバイスをオンボードする](device-onboarding-gp.md)
- [モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード](device-onboarding-mdm.md)
- [ローカル スクリプトを使用した Windows 10 および Windows 11 デバイスのオンボード](device-onboarding-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md)
- [新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection のオンボードに関する問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
