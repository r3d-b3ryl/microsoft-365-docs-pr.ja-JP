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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 構成マネージャーを使用して、サービスに利用するように構成パッケージをデバイスに展開します。
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769477"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Configuration Manager を使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- System Center 2012 R2 構成マネージャー

### <a name="onboard-devices-using-system-center-configuration-manager"></a>System Center Configuration Manager を使用しているオンボードデバイス

1. サービスオンボードウィザードからダウンロードした Configuration Manager 構成パッケージ .zip ファイル ( *DeviceComplianceOnboardingPackage.zip* ) を開きます。 [Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)からパッケージを取得することもできます。

2. ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオン** ボードオンボード] を選択し  >  **Onboarding** ます。

3. [ **展開方法** ] フィールドで、[ **Microsoft エンドポイント構成マネージャー 2012/2012 R2/1511/1602** ] を選択します。
 
4. [ **パッケージのダウンロード** ] を選択し、.zip ファイルを保存します。

5. .Zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。 *Devicecompli/Onbookingscript* という名前のファイルが必要です。

6. [System Center 2012 R2 Configuration Manager 記事の「パッケージとプログラム](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))」に記載されている手順に従って、パッケージを展開します。

7. パッケージを展開する定義済みのデバイスコレクションを選択します。

> [!NOTE]
> Microsoft 365 エンドポイントのデータ損失防止は、 [標準の状態 (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) フェーズでのオンボードをサポートしていません。 Windows のインストールまたはアップグレードを実行した後、ユーザーが OOBE を完了していることを確認します。

>[!TIP]
> デバイスをオンにした後、検出テストを実行して、デバイスがサービスに適切に利用ていることを確認できます。 詳細については、「 [新規利用 Microsoft DEFENDER ATP デバイスで検出テストを実行](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)する」を参照してください。
>
> 構成マネージャーアプリケーションで検出ルールを作成して、デバイスが利用されているかどうかを継続的にチェックすることができます。 アプリケーションは、パッケージとプログラムとは別の種類のオブジェクトです。
> デバイスがまだ利用 (保留中の OOBE の完了またはその他の理由により) になっていない場合、構成マネージャーは、ルールによって状態の変更が検出されるまでデバイスの onboard を再試行します。
> 
> この動作は、"OnboardingState" レジストリ値 (型 REG_DWORD) が1であるかどうかを検出する検出ルールを作成することによって実現できます。
> このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\ 状態" の下にあります。
詳細については、「 [System Center 2012 R2 構成マネージャーでの検出方法の構成](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)」を参照してください。

### <a name="configure-sample-collection-settings"></a>サンプルコレクションの設定を構成する

デバイスごとに、Microsoft Defender セキュリティセンターから要求が行われたときにデバイスからサンプルを収集して、詳細な分析のためにファイルを送信できるかどうかを示す構成値を設定できます。

>[!NOTE]
>これらの構成設定は、通常、Configuration Manager によって実行されます。 

構成マネージャーの構成項目のコンプライアンス規則を設定して、デバイスの共有設定のサンプルを変更できます。

このルールは、対象デバイス上のレジストリキーの値を設定して、苦情があることを確認する *修復* コンプライアンスルール構成アイテムである必要があります。

構成は、次のレジストリキーエントリで設定されます。

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
ここで、<br>
キーの種類は D 語です。 <br>
使用可能な値は次のいずれかです。
- 0-このデバイスからのサンプルの共有を許可しません。
- 1-このデバイスからのすべてのファイルの種類の共有を許可します。

レジストリキーが存在しない場合の既定値は1です。

System Center Configuration Manager の準拠の詳細については、「 [System center 2012 R2 構成マネージャーのコンプライアンス設定に](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))ついて」を参照してください。


## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定
サービスにデバイスを移動した後は、次の推奨構成設定でそれらを有効にすることによって、含まれている脅威保護機能を活用することが重要です。

### <a name="device-collection-configuration"></a>デバイスコレクションの構成
エンドポイント構成マネージャー (バージョン2002以降) を使用している場合は、サーバーまたはダウンレベルクライアントを含めるように展開を広げることができます。


### <a name="next-generation-protection-configuration"></a>次世代の保護構成

次の構成設定をお勧めします。

**スキャン**

- リムーバブル記憶域デバイス (USB ドライブなど) をスキャンする: はい

**リアルタイム保護**

- 動作監視を有効にする: はい
- ダウンロード時およびインストール前に、望ましくない可能性があるアプリケーションに対する保護を有効にする: はい

**クラウド保護サービス**

- クラウド保護サービスのメンバーシップの種類: 上級メンバーシップ

**攻撃対象領域の削減** 利用可能なすべてのルールを監査に構成します。

>[!NOTE]
> これらのアクティビティをブロックすると、正当なビジネスプロセスが中断することがあります。 最善の方法は、監査対象をすべて設定し、有効にすることが安全なエンドポイントを特定し、誤検知が誤検知されないエンドポイントでそれらの設定を有効にすることです。

**ネットワーク保護**

監査モードまたはブロックモードでネットワーク保護を有効にする前に、「 [サポート」ページ](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)から入手できる、マルウェア対策プラットフォームの更新プログラムがインストールされていることを確認してください。


**フォルダーアクセスの制御**

少なくとも30日間は、この機能を監査モードで有効にします。 この期間が経過したら、検出を確認し、保護されたディレクトリへの書き込みが許可されているアプリケーションの一覧を作成します。

詳細については、「制御された [フォルダーアクセスを評価](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)する」を参照してください。


## <a name="offboard-devices-using-configuration-manager"></a>構成マネージャーを使用した offboard デバイス

セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。 有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。 オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。

> [!NOTE]
> オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Microsoft エンドポイント構成マネージャーの現在のブランチを使用した offboard デバイス

Microsoft エンドポイント構成マネージャーの現在のブランチを使用する場合は、「オフ [ボード構成ファイルを作成](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)する」を参照してください。

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>System Center 2012 R2 構成マネージャーを使用するオフボードデバイス

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)からオフボードパッケージを取得します。

2. ナビゲーションウィンドウで、[ **設定** ] [デバイスのオンボードオフボード] を選択し  >   **Device onboarding** >  **Offboarding** ます。

3. オペレーティングシステムとして [Windows 10] を選択します。

4. [ **展開方法** ] フィールドで、[ **Microsoft エンドポイント構成マネージャー 2012/2012 R2/1511/1602** ] を選択します。
    
5. [ **パッケージのダウンロード** ] を選択し、.zip ファイルを保存します。

6. .Zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。 *DeviceComplianceOffboardingScript_valid_until_YYYY* という名前のファイルが必要です。

7. [System Center 2012 R2 Configuration Manager 記事の「パッケージとプログラム](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))」に記載されている手順に従って、パッケージを展開します。

8. パッケージを展開する定義済みのデバイスコレクションを選択します。

> [!IMPORTANT]
> オフボードを使用すると、デバイスはポータルへのセンサーデータの送信を停止しますが、デバイスからのデータは、必要なアラートへの参照も含めて最大6か月保持されます。


## <a name="monitor-device-configuration"></a>デバイス構成の監視

Microsoft エンドポイント構成マネージャーの現在のブランチを使用している場合は、Configuration Manager コンソールの組み込みの Microsoft Defender ATP ダッシュボードを使用します。 詳細については、「 [Microsoft Defender Advanced Threat Protection-Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)」を参照してください。

System Center 2012 R2 構成マネージャーを使用している場合、監視は2つの部分で構成されます。

1. 構成パッケージが正しく展開されており、ネットワークのデバイス上で実行されていることを確認します (または正常に実行されています)。

2. デバイスが Microsoft 365 エンドポイントのデータ損失防止サービスに準拠していることを確認します (これにより、デバイスがオンボードプロセスを完了し、サービスへのデータのレポートを続行できることが保証されます)。

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>構成パッケージが正しく展開されたことを確認する

1. 構成マネージャーコンソールで、ナビゲーションウィンドウの下部にある [ **監視** ] をクリックします。

2. [ **概要** ] を選択し、[ **展開** ] を選択します。

3. パッケージ名を使用して展開上でを選択します。

4. [ **完了統計** ] と [コンテンツの **状態** ] の下にあるステータスインジケーターを確認します。

    失敗した展開 ( **エラー** 、 **要件が満たされていない** 、または失敗した **状態** ) がある場合は、デバイスのトラブルシューティングが必要になることがあります。 詳細については、「 [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)」を参照してください。

    ![エラーなしで展開が成功したことを示す構成マネージャー](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>デバイスが Microsoft 365 エンドポイントのデータ損失防止サービスに準拠していることを確認する

System Center 2012 R2 構成マネージャーの構成アイテムのコンプライアンスルールを設定して、展開を監視することができます。

> [!NOTE]
> この手順とレジストリエントリは、エンドポイント DLP だけでなく、Advanced Threat Protection にも適用されます。

このルールは、対象デバイス上のレジストリキーの値を監視する、 *修復以外* のコンプライアンスルール構成項目である必要があります。

次のレジストリキーエントリを監視します。
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
詳細については、「 [System Center 2012 R2 構成マネージャーのコンプライアンス設定に](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))ついて」を参照してください。

## <a name="related-topics"></a>関連項目
- [グループポリシーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [ローカルスクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス](dlp-configure-endpoints-vdi.md)
- [新しく利用 Microsoft Defender ATP デバイスで検出テストを実行する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
