---
title: Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する
description: Microsoft Defender ウイルス対策が保護と製品の更新プログラムを受け取る方法を管理します。
keywords: 更新プログラム, セキュリティ ベースライン, 保護, 更新プログラムのスケジュール, 強制的な更新, モバイル更新プログラム, WSUS
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.date: 08/15/2022
audience: ITPro
ms.topic: reference
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska, v-vutrieu
manager: dansimp
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: c3856209c510c67bb9054e9567f78ff8ed978b2b
ms.sourcegitcommit: 57e6a8e42b41376c4f4021754c918502bf52d209
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2022
ms.locfileid: "67427248"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する

> [!IMPORTANT]
> 2022 年 3 月の Microsoft Defender エンジン更新プログラム (**1.1.19100.5**) を適用したお客様は、高いリソース使用率 (CPU またはメモリ) が発生した可能性があります。 Microsoft は、以前のバージョンで導入されたバグを解決する更新プログラム (**1.1.19200.5**) をリリースしました。 お客様は、ウイルス対策エンジン (**1.1.19200.5**) のこの新しいエンジン ビルド以上に更新することをお勧めします。 パフォーマンスの問題が完全に修正されるようにするには、更新プログラムを適用した後にマシンを再起動することをお勧めします。 [月次プラットフォームとエンジンのバージョン](#monthly-platform-and-engine-versions) (この記事の内容) を参照してください。

**適用対象:**
- [Microsoft Defender for Endpoint プラン 1 と 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策を最新の状態に保つことは、新しいマルウェアや攻撃手法から保護するために必要な最新のテクノロジと機能をデバイスに確実に提供するために不可欠です。 Microsoft Defender ウイルス対策が[パッシブ モード](microsoft-defender-antivirus-compatibility.md)で実行されている場合でも、ウイルス対策保護を更新してください。 Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。

- [セキュリティ インテリジェンスの更新プログラム](#security-intelligence-updates)
- [製品の更新プログラム](#product-updates)

> [!TIP]
> 最新のエンジン、プラットフォーム、署名の日付を確認するには、「[Microsoft Defender ウイルス対策とその他の Microsoft マルウェア対策のためのセキュリティ インテリジェンスの更新プログラム](https://www.microsoft.com/en-us/wdsi/defenderupdates)」にアクセスしてください

## <a name="security-intelligence-updates"></a>セキュリティ インテリジェンスの更新プログラム

Microsoft Defender ウイルス対策は、[クラウド提供の保護](cloud-protection-microsoft-defender-antivirus.md) (Microsoft Advanced Protection Service または MAPS とも呼ばれます) を使用し、動的なセキュリティ インテリジェンス更新プログラムを定期的にダウンロードして追加の保護を提供します。 これらの動的更新プログラムは、セキュリティ インテリジェンス更新プログラム KB2267602 を介した通常のセキュリティ インテリジェンス更新プログラムに代わるものではありません。

> [!NOTE]
> 更新プログラムは、次の KB でリリースされます。
> - Microsoft Defender ウイルス対策: KB2267602
> - System Center Endpoint Protection: KB2461484

クラウド提供の保護は常にオンであり、機能するにはインターネットへのアクティブな接続が必要です。 セキュリティ インテリジェンスの更新は、スケジュールされた間隔で行われます (ポリシーを使用して構成できます)。 詳細については、「[Microsoft Defender ウイルス対策で Microsoft クラウド提供の保護を使用する](cloud-protection-microsoft-defender-antivirus.md)」を参照してください。

最近のセキュリティ インテリジェンス更新プログラムの一覧については、「[Microsoft Defender ウイルス対策とその他の Microsoft マルウェア対策のためのセキュリティ インテリジェンスの更新プログラム](https://www.microsoft.com/en-us/wdsi/defenderupdates)」を参照してください。

エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。

## <a name="product-updates"></a>製品の更新プログラム

Microsoft Defender ウイルス対策には、*プラットフォーム更新プログラム* と呼ばれる [月次更新プログラム (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) が必要です。

更新プログラムの配布は、次のいずれかの方法で管理できます。

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Microsoft および Windows の更新プログラムをネットワーク内のエンドポイントに展開するために使用する通常の方法。

詳細については、「[Microsoft Defender ウイルス対策保護更新プログラムのソースを管理する](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)」を参照してください。

> [!NOTE]
> - 月次更新プログラムは段階的にリリースされるため、[Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) に複数のパッケージが表示されます。
> - この記事では、広範なリリース チャネルに含まれる変更の一覧を示します。 [こちらで最新の広範なチャネルのリリースをご覧ください](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)。
> - 段階的なロールアウト プロセスの詳細と次のリリースの詳細については、「[Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理する](manage-gradual-rollout.md)」を参照してください。
> - セキュリティ インテリジェンスの更新プログラムの詳細については、「[Microsoft Defender ウイルス対策とその他の Microsoft マルウェア対策のためのセキュリティ インテリジェンスの更新プログラム](https://www.microsoft.com/en-us/wdsi/defenderupdates)」を参照してください。
> - Microsoft Defender プロセスの一覧を探している場合は、**[mde-urls ブックをダウンロードして](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)**、"**Microsoft Defender Processes**" シートを選択します。 mde-urls ブックには、「[プロキシ サーバーで Microsoft Defender for Endpoint サービス URL へのアクセスを有効にする](configure-proxy-internet.md)」で説明されているように、ネットワークで接続できる必要があるサービスと関連付けられた URL もリストされています。

## <a name="monthly-platform-and-engine-versions"></a>月次プラットフォームとエンジンのバージョン

プラットフォーム更新プログラムを更新またはインストールする方法については、「[Windows Defender マルウェア対策プラットフォーム更新プログラム](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)」を参照してください。

すべての更新プログラムに含まれるもの

- パフォーマンスの強化
- サービス性の改善
- 統合の改善 (クラウド、[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender))
<br/><br/>
<details>
<summary>2022 年 7 月から 2022 年 7 月 (プラットフォーム: 4.18.2207.5 |エンジン: 1.1.19500.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.373.219.0**<br/>
&ensp;リリース日: **2022 年 8 月 15** 日<br/>
&ensp;プラットフォーム: **4.18.2207.5**<br/>
&ensp;エンジン: **1.1.19500.2**<br/>
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**<br/>

エンジンバージョン: 1.1.19300.2<br/>
セキュリティ インテリジェンス更新プログラムのバージョン: 1.373.219.0 <br/>

### <a name="whats-new"></a>新機能

- Microsoft Defender ウイルス対策がアクティブな場合の[ハイブリッド スリープ](/windows-hardware/customize/power-settings/sleep-settings-hybrid-sleep)遅延のパフォーマンスの向上 
- [侵害の指標をブロックするカスタム証明書](indicator-certificates.md)に関連するクライアント検出動作を修正しました 
- [AntiMalware Scan Interface (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal) キャッシュのパフォーマンスの向上 
- [Microsoft Visual Basic for Applications](/office/vba/language/concepts/getting-started/64-bit-visual-basic-for-applications-overview) (VBA) 関連のマクロの検出と修復の改善 
- AMSI 除外の処理の改善 
- Host Intrusion Prevention System (HIPS) ルール処理でのデッドロック検出が修正されました。 (HIPS および Defender for Endpoint の詳細については、「[サードパーティの HIPS から ASR ルールへの移行](migrating-asr-rules.md)」を参照してください。) 
- `MsMpEng.exe` がプライベート バイトを消費していたメモリ リークを修正しました。 (高い CPU 使用率も問題である場合は、「[Microsoft Defender ウイルス対策による高い CPU 使用率](troubleshooting-mode-scenarios.md)」を参照してください) 
- [動作の監視](configure-real-time-protection-microsoft-defender-antivirus.md)によるデッドロックを修正しました 
- 信頼検証の改善 
- レガシ オペレーティング プラットフォームでのエンジン クラッシュの問題を修正しました 
- Performance Analyzer v3 の更新プログラム: トップ パス サポート、スキャン スキップ情報、OnDemand スキャン サポートを追加しました。 「[Microsoft Defender ウイルス対策用のパフォーマンス アナライザー](tune-performance-defender-antivirus.md)」を参照してください。 
- ファイル コピー操作中の Defender パフォーマンスの向上
- [トラブルシューティング モード](enable-troubleshooting-mode.md)の機能強化を追加しました  
- 更新/再起動間での Defender WINEVT チャネルの修正を追加しました。 (WINEVT の詳細については [、Windows イベント ログ](/windows/win32/api/_wes/) を参照してください)。
- 起動時/更新中の [Defender WMI 管理](use-wmi-microsoft-defender-antivirus.md) バグの修正を追加しました 
- [Windows イベント ビューアー操作イベント](troubleshoot-microsoft-defender-antivirus.md)で 2010/2011 を複製する修正プログラムを追加しました 
- [Defender for Endpoint](microsoft-defender-endpoint.md) Stack プロセストークンのセキュリティ強化のサポートが追加されました 


### <a name="known-issues"></a>既知の問題

- プラットフォーム更新プログラム 4.18.2207.5 を展開しているお客様は、アプリケーションに影響を与える可能性のあるネットワーク パフォーマンスの低下が発生する可能性があります。

<br/><br/>
</details><details>
<summary>2022 年 5 月 (プラットフォーム: 4.18.2205.7 | エンジン: 1.1.19300.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.369.88.0**<br/>
&ensp;リリース日: **2022 年 6 月 22 日**<br/>
&ensp;プラットフォーム: **4.18.2205.7**<br/>
&ensp;エンジン: **1.1.19300.2**<br/>
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**<br/>

エンジンバージョン: 1.1.19300.2<br/>
セキュリティ インテリジェンス更新プログラムのバージョン: 1.369.88.0<br/>

### <a name="whats-new"></a>新機能

- 更新プログラムの ETW チャネル構成の修正プログラムを追加しました 
- より具体的な除外ターゲット設定を可能にする、コンテキストの除外に関するサポートを追加しました 
- 固定コンテキストの最大サイズ
- [ASR LSASS 検出](attack-surface-reduction-rules-reference.md)の修正プログラムを追加しました
- SHSetKnownFolder にルール除外ロジックの修正プログラムを追加しました
- 履歴ストアの AMSI ディスク使用制限を追加しました
- 署名の更新を受け入れることを拒否する Defender サービスの修正を追加しました

### <a name="known-issues"></a>既知の問題

既知の問題はありません

<br/><br/>
</details><details>
<summary>2022 年 3 月 *更新プログラム* (プラットフォーム: 4.18.2203.5 | エンジン: 1.1.19200.5)</summary>

*2022 年 3 月の Microsoft Defender エンジン更新プログラム (**1.1.19100.5**) を適用したお客様は、高いリソース使用率 (CPU またはメモリ) が発生した可能性があります。Microsoft は、以前のバージョンで導入されたバグを解決する更新プログラム (**1.1.19200.5**) をリリースしました。お客様は、ウイルス対策エンジン (**1.1.19200.5**) のこの新しいエンジン ビルド以上に更新することをお勧めします。パフォーマンスの問題が完全に修正されるようにするには、更新プログラムを適用した後にマシンを再起動することをお勧めします。*

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.363.817.0**<br/>
&ensp;リリース日: **2022 年 4 月 22 日**<br/>
&ensp;プラットフォーム: **4.18.2203.5**<br/>
&ensp;エンジン: **1.1.19200.5**<br/>
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**<br/>

エンジン バージョン: 1.1.19200.5 <br/>
セキュリティ インテリジェンス更新プログラムのバージョン: 1.363.817.0<br/>

### <a name="whats-new"></a>新機能

- 2022 年 3 月以前の Microsoft Defender エンジン更新プログラム (1.1.19100.5) に関連する高いリソース使用率 (CPU またはメモリ) に関する問題を解決します

### <a name="known-issues"></a>既知の問題

既知の問題はありません

<br/><br/>
</details><details>
<summary>2022 年 3 月 (プラットフォーム: 4.18.2203.5 | エンジン: 1.1.19100.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.361.1449.0**<br/>
&ensp;リリース日: **2022 年 4 月 7 日**<br/>
&ensp;プラットフォーム: **4.18.2203.5**<br/>
&ensp;エンジン: **1.1.19100.5**<br/>
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**<br/>

エンジンのバージョン: 1.1.19100.5 <br/>
セキュリティ インテリジェンス更新プログラムのバージョン: 1.361.1449.0<br/>

### <a name="whats-new"></a>新機能

- Outlook アドインをブロックした [attack surface reduction rule](attack-surface-reduction.md) の修正プログラムを追加しました 
- [behavior monitoring](configure-protection-features-microsoft-defender-antivirus.md) の短いライブ プロセスに関連するパフォーマンスの問題の修正プログラムを追加しました 
- [AMSI](/windows/win32/amsi/antimalware-scan-interface-portal) 除外の修正プログラムを追加しました 
- 強化された [改ざん防止](prevent-changes-to-security-settings-with-tamper-protection.md) 機能 
- [real-time protection](configure-protection-features-microsoft-defender-antivirus.md) が `SharedSignaturesPath` config を使用している場合に無効になる修正プログラムを追加しました。`SharedSignaturesPath` パラメーターの詳細については、[Set-MpPreference](/powershell/module/defender/set-mppreference) を参照してください。

### <a name="known-issues"></a>既知の問題

- リソース使用率 (CPU またはメモリ) が高くなる可能性があります。 2022 年 3 月のプラットフォーム 4.18.2203.5 およびエンジン 1.1.19200.5 の更新プログラムを参照してください。

<br/><br/>
</details>


### <a name="previous-version-updates-technical-upgrade-support-only"></a>以前のバージョンの更新プログラム: テクニカル アップグレード サポートのみ

新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートのみに縮小されます。 このセクションに記載されているバージョンより古いバージョンは、テクニカル アップグレード サポートのみ提供されます。<br/><br/>

<details>
<summary>2022 年 2 月 (プラットフォーム: 4.18.2202.4 | エンジン: 1.1.19000.8)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.361.14.0**<br/>
&ensp;リリース日: **2022 年 3 月 14 日**<br/>
&ensp;プラットフォーム: **4.18.2202.4**<br/>
&ensp;エンジン: **1.1.19000.8**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

エンジンのバージョン: 1.1.19000.8 <br/>
セキュリティ インテリジェンス更新プログラムのバージョン: 1.361.14.0 <br/>

### <a name="whats-new"></a>新機能

- 検出と動作監視ロジックの改善
- 攻撃面の減少検出をトリガーする誤検知を修正しました
- EDR と高度な追求検出アラートの忠実性を向上する修正を追加しました
- Defender では、トースト ポップアップのカスタム通知がサポートされなくなりました。 この変更を反映するように GPO/Intune/SCCM とドキュメントを変更しました。
- リムーバブル ストレージに書き込まれたファイルの情報とコピーの両方をキャプチャするための改善。 詳細については、「[Microsoft Defender for Endpoint デバイス制御のリムーバブル ストレージへのアクセスの制御、リムーバブル ストレージ メディア](device-control-removable-storage-access-control.md)」を参照してください。
- SmartScreen サービスに到達できない場合のトラフィック出力の改善 
- 認証要件を持つプロキシを使用しているお客様の接続性の改善
- ネットワーク FileShares の VDI デバイス更新のバグを修正しました 
- ブロック モードの EDR では、新しい CSP を使用した きめ細かいデバイス ターゲット設定がサポートされるようになりました。 「[ブロック モードのエンドポイントでの検出と対応 (EDR)](edr-in-block-mode.md)」を参照してください。

### <a name="known-issues"></a>既知の問題

既知の問題はありません

<br/><br/>
</details><details>
<summary>2022 年 1 月 (プラットフォーム: 4.18.2201.10 | エンジン: 1.1.18900.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.357.8.0**<br/>
&ensp;リリース日: **2022 年 2 月 9 日**<br/>
&ensp;プラットフォーム: **4.18.2201.10**<br/>
&ensp;エンジン: **1.1.18900.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

エンジンのバージョン: 1.1.18900.2 <br/>
セキュリティ インテリジェンス更新プログラムのバージョン: 1.357.8.0 <br/>

### <a name="whats-new"></a>新機能

- フィルター処理のパフォーマンスにおける動作監視の改善
- TrustedInstaller のセキュリティ強化
- 改ざん防止の改善
- `ScanScheduleTime` を、[Set-MpPreference](/powershell/module/defender/set-mppreference) の新しい `ScanScheduleOffest` コマンドレットに置き換えました。このポリシーは、スケジュールされたスキャンを実行するために、午前 0 時以降の分数を構成します。
- `-ServiceHealthReportInterval` の設定を [Set-MpPreference](/powershell/module/defender/set-mppreference) に追加しました。このポリシーは、スケジュールされたスキャンを実行する時間間隔 (分単位) を構成します。
- `AllowSwitchToAsyncInspection` の設定を [Set-MpPreference](/powershell/module/defender/set-mppreference) に追加しました。このポリシーを使用すると、同期的に検査されたネットワーク フローを、チェックと検証の完了後に非同期検査に切り替えられるようにパフォーマンスの最適化を図ることができます。
- Performance Analyzer v2 の更新プログラム: リモート PowerShell と PowerShell 7.x のサポートを追加しました。 「[Microsoft Defender ウイルス対策用のパフォーマンス アナライザー](tune-performance-defender-antivirus.md)」を参照してください。
- Microsoft Defender ウイルス対策ネットワーク検査システム ドライバーの重複する可能性があるパケットバグを修正しました。

### <a name="known-issues"></a>既知の問題

既知の問題はありません

<br/><br/>
</details><details>
<summary>2021 年 11 月 (プラットフォーム: 4.18.2111.5 | エンジン: 1.1.18800.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.355.2.0**<br/>
&ensp;リリース日: **2021 年 12 月 9 日**<br/>
&ensp;プラットフォーム: **4.18.2111.5**<br/>
&ensp;エンジン: **1.1.18800.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

エンジンのバージョン: 1.1.18800.4 セキュリティ インテリジェンス更新プログラムのバージョン: 1.355.2.0

### <a name="whats-new"></a>新機能

- Exchange サーバーでの特定の集中的なシナリオの CPU 使用効率の改善
- Defender PowerShell モジュールの Get-MpComputerStatus の下に新しいデバイス制御の状態フィールドを追加しました。 詳細については、「[Microsoft Defender for Endpoint デバイス制御のリムーバブル ストレージへのアクセスの制御](device-control-removable-storage-access-control.md)」を参照してください。
- PowerShell で設定したときに `SharedSignatureRoot` 値を削除できないバグを修正しました
- Microsoft Defender for Endpoint で改ざん防止が有効になっていると示されていても、[改ざん防止](prevent-changes-to-security-settings-with-tamper-protection.md)が有効にならなかったバグを修正しました
- Microsoft Defender ウイルス対策用パフォーマンス アナライザー ツールにサポートとバグ修正を追加しました。 詳細については、「[Microsoft Defender ウイルス対策用のパフォーマンス アナライザー](tune-performance-defender-antivirus.md)」を参照してください。   
   - `New-MpPerformanceRecording` に PowerShell ISE のサポートを追加しました
   - `Get-MpPerformanceReport -TopFilesPerProcess` のバグ エラーを修正しました
   - PowerShell 7.x、リモート セッション、PowerShell ISE で `New-MpPerformanceRecording` を使用する場合のパフォーマンス記録セッション リークを修正しました


### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 10 月 (プラットフォーム: 4.18.2110.6 | エンジン: 1.1.18700.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.353.3.0**<br/>
&ensp;リリース日: **2021 年 10 月 28 日**<br/>
&ensp;プラットフォーム: **4.18.2110.6**<br/>
&ensp;エンジン: **1.1.18700.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

エンジンのバージョン: 1.1.18700.4 セキュリティ インテリジェンス更新プログラムのバージョン: 1.353.3.0

### <a name="whats-new"></a>新機能

- ファイル転送プロトコル (FTP) ネットワーク トラフィック カバレッジの改善
- Windows Server 2016 で実行されている Exchange Server での Microsoft Defender の CPU 使用率を低減するための修正
- スキャンの中断の修正
- ブロックされた改ざんの試行がセキュリティ センターに表示されない場合のアラートの修正
- Microsoft Defender サービスの改ざん防御の改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 9 月 (プラットフォーム: 4.18.2109.6 | エンジン: 1.1.18600.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.351.7.0**<br/>
&ensp;リリース日: **2021 年 10 月 7 日**<br/>
&ensp;プラットフォーム: **4.18.2109.6**<br/>
&ensp;エンジン: **1.1.18600.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

エンジンのバージョン: 1.1.18600.4 セキュリティ インテリジェンス更新プログラムのバージョン: 1.351.7.0

### <a name="whats-new"></a>新機能
- Microsoft Defender ウイルス対策のエンジンとプラットフォームの更新プログラムの新しい遅延リング。 このリングにオプトインしたデバイスは、48 時間の遅延で更新プログラムを受信します。 新しい遅延リングは、重要な環境にのみ推奨されます。 「[Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理する](manage-gradual-rollout.md)」を参照してください。
- Microsoft Defender 更新プログラムの段階的なロールアウト プロセスの改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 8 月 (プラットフォーム: 4.18.2108.7 | エンジン: 1.1.18500.10)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.349.22.0**<br/>
&ensp;リリース日: **2021 年 9 月 2 日**<br/>
&ensp;プラットフォーム: **4.18.2108.7**<br/>
&ensp;エンジン: **1.1.18500.10**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- 動作監視エンジンの改善
- 新しい [Microsoft Defender ウイルス対策用のパフォーマンス アナライザー](tune-performance-defender-antivirus.md)をリリースしました
- 悪意のある DLL の読み込みに対する Microsoft Defender ウイルス対策の強化
- TrustedInstaller バイパスに対する Microsoft Defender ウイルス対策の強化
- 人手によるランサムウェア (HumOR) に関するより多くのデータを含めるためのファイル変更通知の拡張

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 7 月 (プラットフォーム: 4.18.2107.4 | エンジン: 1.1.18400.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.345.13.0**<br/>
&ensp;リリース日: **2021 年 8 月 5 日**<br/>
&ensp;プラットフォーム: **4.18.2107.4**<br/>
&ensp;エンジン: **1.1.18400.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- Windows ポータブル デバイスのデバイス制御のサポートを追加しました
- 望ましくない可能性のあるアプリケーション (PUA) 保護は、コンシューマーに対して既定でオンになっています (「[Microsoft Defender ウイルス対策で望ましくない可能性のあるアプリケーションをブロックする](/microsoft-365/security/defender-endpoint/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)」を参照してください。)
- グループ ポリシー オブジェクトで管理されているシステムのスケジュールされたスキャンは、ユーザーが構成したスキャンの時間に従います
- 動作監視エンジンの改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません

<br/>
</details><details>
<summary> 2021 年 6 月 (プラットフォーム: 4.18.2106.5 | エンジン: 1.1.18300.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.343.17.0**<br/>
&ensp;リリース日: **2021 年 6 月 28 日**<br/>
&ensp;プラットフォーム: **4.18.2106.5**<br/>
&ensp;エンジン: **1.1.18300.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール。 「[Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理する](manage-gradual-rollout.md)」を参照してください。
- 動作監視エンジンの改善
- マルウェア対策定義のロールアウトの改善
- 境界ネットワーク イベント検査の拡張

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 5 月 (プラットフォーム: 4.18.2105.4 | エンジン: 1.1.18200.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**<br/>
&ensp;リリース日: **2021 年 6 月 3 日**<br/>
&ensp;プラットフォーム: **4.18.2105.4**<br/>
&ensp;エンジン: **1.1.18200.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- [動作監視](client-behavioral-blocking.md)の改善
- [ネットワーク保護](network-protection.md)の通知フィルター機能を修正しました

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 4 月 (プラットフォーム: 4.18.2104.14 | エンジン: 1.1.18100.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**<br/>
&ensp;リリース日: **2021 年 4 月 26 日**  (エンジン: 1.1.18100.6 リリース日 2021 年 5 月 5 日)<br/>
&ensp;プラットフォーム: **4.18.2104.14**<br/>
&ensp;エンジン: **1.1.18100.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- その他の動作監視ロジック
- カーネル モードのキー ロガー検出を改善しました
- [Microsoft Defender 更新プログラム](manage-gradual-rollout.md)の段階的なロールアウト プロセスを管理するための新しいコントロールを追加しました


### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 3 月 (プラットフォーム: 4.18.2103.7 | エンジン: 1.1.18000.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**<br/>
&ensp;リリース日: **2021 年 4 月 2 日**<br/>
&ensp;プラットフォーム: **4.18.2103.7**<br/>
&ensp;エンジン: **1.1.18000.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- 動作監視エンジンの改善
- ネットワーク ブルートフォース攻撃の軽減策の拡張
- [改ざん防止](prevent-changes-to-security-settings-with-tamper-protection.md)が有効になっているときの改ざん試行イベント生成の失敗が増えました

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 2 月 (プラットフォーム: 4.18.2102.3 | エンジン: 1.1.17900.7)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**<br/>
&ensp;リリース日: **2021 年 3 月 9 日**<br/>
&ensp;プラットフォーム: **4.18.2102.3**<br/>
&ensp;エンジン: **1.1.17900.7**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- [改ざん防止](prevent-changes-to-security-settings-with-tamper-protection.md)によるサービスの回復を改善しました
- 改ざん防止の範囲を拡張します

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 1 月 (プラットフォーム: 4.18.2101.9 | エンジン: 1.1.17800.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**<br/>
&ensp;リリース日: **2021 年 2 月 2 日**<br/>
&ensp;プラットフォーム: **4.18.2101.9**<br/>
&ensp;エンジン: **1.1.17800.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- シェルコードのエクスプロイト検出の改善
- 資格情報の盗用の試行の可視性の向上
- Microsoft Defender ウイルス対策サービスの改ざん対策機能の改善
- ARM x64 エミュレーションのサポートの改善
- 修正: リアルタイム保護で最初の検出が実行された後も、EDR ブロック通知が脅威の履歴に残る

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2020 年 11 月 (プラットフォーム: 4.18.2011.6 | エンジン: 1.1.17700.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**<br/>
&ensp;リリース日: **2020 年 12 月 3 日**<br/>
&ensp;プラットフォーム: **4.18.2011.6**<br/>
&ensp;エンジン: **1.1.17700.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の状態サポート ログの改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2020 年 10 月 (プラットフォーム: 4.18.2010.7 | エンジン: 1.1.17600.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**<br/>
&ensp;リリース日: **2020 年 10 月 29 日**<br/>
&ensp;プラットフォーム: **4.18.2010.7**<br/>
&ensp;エンジン: **1.1.17600.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- 特別な脅威カテゴリの新しい説明
- エミュレーション機能の改善
- ホスト アドレスの許可/ブロック機能の改善
- ローカル ユーザー除外のマージを無視するための Defender CSP の新しいオプション

### <a name="known-issues"></a>既知の問題

既知の問題はありません
<br/>
</details><details>
<summary> 2020 年 9 月 (プラットフォーム: 4.18.2009.7 | エンジン: 1.1.17500.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**<br/>
&ensp;リリース日: **2020 年 10 月 1 日**<br/>
&ensp;プラットフォーム: **4.18.2009.7**<br/>
&ensp;エンジン: **1.1.17500.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- 検疫内のファイルを復元するには、管理者のアクセス許可が必要になります
- XML 形式のイベントがサポートされるようになりました
- 除外マージを無視する CSP のサポート
- 以下の新しい管理インターフェイス
   - UDP 検査
   - Server 2019 のネットワーク保護
   - ネットワーク保護の IP アドレスの除外
- TPM 測定値の可視性を改善しました
- Office VBA モジュールのスキャンを改善しました

### <a name="known-issues"></a>既知の問題

既知の問題はありません
<br/>
</details>
<details>
<summary> 2020 年 8 月 (プラットフォーム: 4.18.2008.9 | エンジン: 1.1.17400.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**<br/>
&ensp;リリース日: **2020 年 8 月 27 日**<br/>
&ensp;プラットフォーム: **4.18.2008.9**<br/>
&ensp;エンジン: **1.1.17400.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- より多くのテレメトリ イベントの追加
- スキャン イベント テレメトリの改善
- メモリ スキャンの動作監視の改善
- マクロ ストリームのスキャンの改善
- `AMRunningMode` を Get-MpComputerStatus PowerShell コマンドレットに追加しました
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) は無視されます。Microsoft Defender ウイルス対策は、別のウイルス対策プログラムを検出すると自動的にオフになります。


### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 7 月 (プラットフォーム: 4.18.2007.8 | エンジン: 1.1.17300.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**<br/>
&ensp;リリース日: **2020 年 7 月 28 日**<br/>
&ensp;プラットフォーム: **4.18.2007.8**<br/>
&ensp;エンジン: **1.1.17300.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- BITS のテレメトリの改善
- Authenticode コード署名証明書の検証の改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 6 月 (プラットフォーム: 4.18.2006.10 | エンジン: 1.1.17200.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**<br/>
&ensp;リリース日: **2020 年 6 月 22 日**<br/>
&ensp;プラットフォーム: **4.18.2006.10**<br/>
&ensp;エンジン: **1.1.17200.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- [サポート ログの場所](./collect-diagnostic-data.md)を指定する可能性
- パッシブ モードでの積極的なキャッチアップ スキャンのスキップ。
- 従量制課金接続で Defender を更新できます
- キャッシュが無効な場合のパフォーマンス調整を修正しました
- レジストリ クエリを修正しました
- ADMX でのスキャン時間のランダム化を修正しました

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 5 月 (プラットフォーム: 4.18.2005.4 | エンジン: 1.1.17100.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**<br/>
&ensp;リリース日: **2020 年 5 月 26 日**<br/>
&ensp;プラットフォーム: **4.18.2005.4**<br/>
&ensp;エンジン: **1.1.17100.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- スキャン イベントのログ記録を改善しました
- ユーザー モードのクラッシュ処理を改善しました。
- 改ざん防止用のイベント トレースを追加しました
- AMSI サンプルの送信を修正しました
- AMSI クラウドのブロックを修正しました
- セキュリティ更新プログラムのインストール ログを修正しました

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 4 月 (プラットフォーム: 4.18.2004.6 | エンジン: 1.1.17000.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**<br/>
&ensp;リリース日: **2020 年 4 月 30 日**<br/>
&ensp;プラットフォーム: **4.18.2004.6**<br/>
&ensp;エンジン: **1.1.17000.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- WDfilter の改善
- 攻撃面の減少検出イベントに、よりアクション可能なイベント データを追加します
- 診断データと WMI のバージョン情報を修正しました
- プラットフォーム更新後の UI の間違ったプラットフォームのバージョンを修正しました
- ファイルレス脅威保護用の動的 URL インテリジェンス
- UEFI スキャン機能
- 更新プログラムのログ記録を拡張します

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 3 月 (プラットフォーム: 4.18.2003.8 | エンジン: 1.1.16900.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**<br/>
&ensp;リリース日: **2020 年 3 月 24 日**<br/>
&ensp;プラットフォーム: **4.18.2003.8**<br/>
&ensp;エンジン: **1.1.16900.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- [MPCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) に CPU 調整オプションを追加しました
- 診断機能の改善
- セキュリティ インテリジェンスのタイムアウトを減らします (5 分)
- AMSI エンジンの内部ログ機能を拡張します
- プロセスのブロックに関する通知を改善します

### <a name="known-issues"></a>既知の問題
[**修正済み**] Microsoft Defender ウイルス対策実行時にファイルをスキップする。

<br/>
</details>

<details>

<summary> 2020 年 2 月 (プラットフォーム: - | エンジン: 1.1.16800.2)</summary>


&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0**<br/>
&ensp;リリース日: **2020 年 2 月 25 日**<br/>
&ensp;プラットフォーム/クライアント: **-**<br/>
&ensp;エンジン: **1.1.16800.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能


### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 1 月 (プラットフォーム: 4.18.2001.10 | エンジン: 1.1.16700.2)</summary>


セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**<br/>
リリース日: **2020 年 1 月 30 日**<br/>
プラットフォーム/クライアント: **4.18.2001.10**<br/>
エンジン: **1.1.16700.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード サポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- Exchange を実行している WS2016 での BSOD を修正しました
- TMP がネットワーク パスにリダイレクトされたときにプラットフォームの更新をサポートします
- プラットフォームとエンジンのバージョンが [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) に追加されます <!-- The preceding URL must include "/en-us" -->
- 緊急署名の更新を[パッシブ モード](./microsoft-defender-antivirus-compatibility.md)に拡張します
- 4.18.1911.3 ハングの修正

### <a name="known-issues"></a>既知の問題

[**修正済み**] [モダン スタンバイ モード](/windows-hardware/design/device-experiences/modern-standby)を使用しているデバイスでは、フィルター ドライバーでハングが発生し、保護のギャップが発生する可能性があります。  顧客には、影響を受けるコンピューターが最新のマルウェア対策プラットフォームに更新されていないように見えます。
<br/>
> [!IMPORTANT]
> この更新プログラムの説明:
> - SHA2 をサポートするために、より下位のバージョンのプラットフォームを実行している RS1 デバイスで必要になります。
> - ハングの問題があるシステムの再起動フラグがあります。
> - 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えられる予定はありません。
> - 再起動の要件により更新プログラムとして分類されます。
> - [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update) でのみ提供されます。
<br/>
</details>

<details>
<summary> 2019 年 11 月 (プラットフォーム: 4.18.1911.3 | エンジン: 1.1.16600.7)</summary>

セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**<br/>
リリース日: **2019 年 12 月 7 日**<br/>
プラットフォーム: **4.18.1911.3**<br/>
エンジン: **1.1.17000.7**<br/>
サポート フェーズ: **サポートなし**<br/>

### <a name="whats-new"></a>新機能

- MpCmdRun のトレース レベルを修正しました
- WDFilter のバージョン情報を修正しました
- 通知の改善 (PUA)
- MRT ログをサポート ファイルに追加します

### <a name="known-issues"></a>既知の問題
この更新プログラムをインストールすると、デバイスを最新のプラットフォームのバージョンに更新するために、ジャンプ パッケージ 4.18.2001.10 が必要になります。
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender ウイルス対策プラットフォームのサポート

プラットフォームとエンジンの更新プログラムは、毎月提供されます。 完全なサポートを受けるには、最新のプラットフォーム更新プログラムで最新の状態に保つ必要があります。 サポート構造は動的であり、最新のプラットフォームのバージョンの可用性に応じて、次の 2 つのフェーズに進化しています。

- **セキュリティと重要な更新プログラムのサービス フェーズ** - 最新のプラットフォームのバージョンを実行している場合、マルウェア対策プラットフォームのセキュリティと重要な更新プログラムの両方を受け取ることができます。

- **テクニカル サポート (のみ) のフェーズ** - 新しいプラットフォームのバージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートのみに縮小されます。 N-2 より前のプラットフォームのバージョンはサポートされなくなります。*

\* テクニカル サポートは、Windows 10 リリース バージョン (「[Windows 10 リリースに含まれるプラットフォームのバージョン](#platform-version-included-with-windows-10-releases)」を参照してください) から最新のプラットフォームのバージョンへのアップグレードに対して引き続き提供されます。

テクニカル サポート (のみ) のフェーズでは、Microsoft カスタマー サービスとサポートと Microsoft の管理サポート サービス (Premier サポートなど) により、商習慣上妥当なサポート インシデントが提供されます。 サポート インシデントで、追加ガイダンスのための開発部門へのエスカレーション、セキュリティ以外の更新プログラム、またはセキュリティ更新プログラムが必要な場合、お客様は完全にサポートされている Service Pack へのアップグレードが求められます。

> [!NOTE]
> Microsoft Defender ウイルス対策プラットフォーム更新プログラムを手動で展開する場合、またはスクリプトまたは Microsoft 以外の管理製品を使用して Microsoft Defender ウイルス対策プラットフォーム更新プログラムを展開する場合は、最新バージョンのプラットフォーム更新プログラム (N-2) をインストールする前に、[Microsoft Update カタログ](https://www.catalog.update.microsoft.com/Search.aspx?q=4.18.2001.10)からバージョン `4.18.2001.10` がインストールされていることを確認してください。

### <a name="platform-version-included-with-windows-10-releases"></a>Windows 10 リリースに含まれるプラットフォームのバージョン

次の表に、最新の Windows 10 リリースに付属する Microsoft Defender ウイルス対策プラットフォームとエンジンのバージョンを示します。<br/><br/>

|Windows 10 リリース  |プラットフォームのバージョン  |エンジンのバージョン |サポート フェーズ |
|:---|:---|:---|:---|
|2004  (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | テクニカル アップグレード サポート (のみ) |
|1909  (19H2) |4.18.1902.5 |1.1.16700.3 | テクニカル アップグレード サポート (のみ) |
|1903  (19H1) |4.18.1902.5 |1.1.15600.4 | テクニカル アップグレード サポート (のみ) |
|1809  (RS5) |4.18.1807.18075 |1.1.15000.2 | テクニカル アップグレード サポート (のみ) |
|1803  (RS4) |4.13.17134.1 |1.1.14600.4 | テクニカル アップグレード サポート (のみ) |
|1709  (RS3) |4.12.16299.15 |1.1.14104.0 | テクニカル アップグレード サポート (のみ) |
|1703  (RS2) |4.11.15603.2 |1.1.13504.0 | テクニカル アップグレード サポート (のみ) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | テクニカル アップグレード サポート (のみ) |

Windows 10 リリース情報については、「[Windows ライフサイクル ファクト シート」](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)」を参照してください。

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>展開イメージのサービスと管理 (DISM) の更新

最新のウイルス対策およびマルウェア対策の更新プログラムを使用して、Windows 10 (Enterprise、Pro、Home エディション)、Windows Server 2019、Windows Server 2022、および Windows Server 2016 OS のインストール イメージを更新することをお勧めします。OS インストール イメージを最新の状態に保つことは、保護の空白を回避するのに役立ちます。

詳細については、「[Windows オペレーティング システムのインストール イメージ用の Microsoft Defender 更新プログラム](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)」を参照してください。

<details>
<summary>20220802.1</summary>

&ensp;パッケージ バージョン: **20220802.1**<br/>
&ensp;プラットフォームのバージョン: **4.18.2205.7**<br/>
&ensp;エンジンバージョン: **1.1.19400.3**<br/>
&ensp;署名バージョン: **1.371.1205.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし

<br/>
</details><details>
<summary>20220629.5</summary>

&ensp;パッケージのバージョン: **20220629.5**<br/>
&ensp;プラットフォームのバージョン: **4.18.2205.7**<br/>
&ensp;エンジンのバージョン: **1.1.19300.2**<br/>
&ensp;署名のバージョン: **1.369.220.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし

<br/>
</details><details>
<summary>20220603.3</summary>

&ensp;パッケージのバージョン: **20220603.3**<br/>
&ensp;プラットフォームのバージョン: **4.18.2203.5**<br/>
&ensp;エンジンのバージョン: **1.1.19200.6**<br/>
&ensp;署名のバージョン: **1.367.1009.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし

<br/>
</details><details>
<summary>20220506.6</summary>

&ensp;パッケージのバージョン: **20220506.6**<br/>
&ensp;プラットフォームのバージョン: **4.18.2203.5**<br/>
&ensp;エンジンのバージョン: **1.1.19200.5**<br/>
&ensp;署名のバージョン: **1.363.1436.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし

<br/>
</details><details>
<summary>20220321.1</summary>

&ensp;パッケージのバージョン: **20220321.1**<br/>
&ensp;プラットフォームのバージョン: **4.18.2202.4**<br/>
&ensp;エンジンのバージョン: **1.1.19000.8**<br/>
&ensp;署名のバージョン: **1.351.337.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし

<br/>
</details><details>
<summary>20220305.1</summary>

&ensp;パッケージのバージョン: **20220305.1**<br/>
&ensp;プラットフォームのバージョン: **4.18.2201.10**<br/>
&ensp;エンジンのバージョン: **1.1.18900.3**<br/>
&ensp;署名のバージョン: **1.359.1405.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし

<br/>
</details><details>
<summary>20220203.1</summary>

&ensp;パッケージのバージョン: **20220203.1**<br/>
&ensp;プラットフォームのバージョン: **4.18.2111.5**<br/>
&ensp;エンジンのバージョン: **1.1.18900.2**<br/>
&ensp;署名のバージョン: **1.357.32.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>20220105.1</summary>

&ensp;パッケージのバージョン: **20220105.1**<br/>
&ensp;プラットフォームのバージョン: **4.18.2111.5**<br/>
&ensp;エンジンのバージョン: **1.1.18800.4**<br/>
&ensp;署名のバージョン: **1.355.1482.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2112.01</summary>

&ensp;パッケージのバージョン: **1.1.2112.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2110.6**<br/>
&ensp;エンジンのバージョン: **1.1.18700.4**<br/>
&ensp;署名のバージョン: **1.353.2283.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2111.02</summary>

&ensp;パッケージのバージョン: **1.1.2111.02**<br/>
&ensp;プラットフォームのバージョン: **4.18.2110.6**<br/>
&ensp;エンジンのバージョン: **1.1.18700.4**<br/>
&ensp;署名のバージョン: **1.353.613.0**<br/>

### <a name="fixes"></a>修正プログラム
- ローカライズ ファイルに関する問題を修正しました

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2110.01</summary>

&ensp;パッケージのバージョン: **1.1.2110.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2109.6**<br/>
&ensp;エンジンのバージョン: **1.1.18500.10**<br/>
&ensp;署名のバージョン: **1.349.2103.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2109.01</summary>

&ensp;パッケージのバージョン: **1.1.2109.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2107.4**<br/>
&ensp;エンジンのバージョン: **1.1.18400.5**<br/>
&ensp;署名のバージョン: **1.347.891.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2108.01</summary>

&ensp;パッケージのバージョン: **1.1.2108.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2107.4**<br/>
&ensp;エンジンのバージョン: **1.1.18300.4**<br/>
&ensp;署名のバージョン: **1.343.2244.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2107.02</summary>

&ensp;パッケージのバージョン: **1.1.2107.02**<br/>
&ensp;プラットフォームのバージョン: **4.18.2105.5**<br/>
&ensp;エンジンのバージョン: **1.1.18300.4**<br/>
&ensp;署名のバージョン: **1.343.658.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2106.01</summary>

&ensp;パッケージのバージョン: **1.1.2106.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2104.14**<br/>
&ensp;エンジンのバージョン: **1.1.18100.6**<br/>
&ensp;署名のバージョン: **1.339.1923.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;パッケージのバージョン: **1.1.2105.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2103.7**<br/>
&ensp;エンジンのバージョン: **1.1.18100.6**<br/>
&ensp;署名のバージョン: **1.339.42.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;パッケージのバージョン: **1.1.2104.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2102.4**<br/>
&ensp;エンジンのバージョン: **1.1.18000.5**<br/>
&ensp;署名のバージョン: **1.335.232.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;パッケージのバージョン: **1.1.2103.01**<br/>
&ensp;プラットフォームのバージョン **4.18.2101.9**<br/>
&ensp;エンジンのバージョン: **1.1.17800.5**<br/>
&ensp;署名のバージョン: **1.331.2302.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;パッケージのバージョン: **1.1.2102.03**<br/>
&ensp;プラットフォームのバージョン: **4.18.2011.6**<br/>
&ensp;エンジンのバージョン: **1.1.17800.5**<br/>
&ensp;署名のバージョン: **1.331.174.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;パッケージのバージョン: **1.1.2101.02**<br/>
&ensp;プラットフォームのバージョン: **4.18.2011.6**<br/>
&ensp;エンジンのバージョン: **1.1.17700.4**<br/>
&ensp;署名のバージョン: **1.329.1796.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;パッケージのバージョン: **1.1.2012.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2010.7**<br/>
&ensp;エンジンのバージョン: **1.1.17600.5**<br/>
&ensp;署名のバージョン: **1.327.1991.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;パッケージのバージョン: **1.1.2011.02**<br/>
&ensp;プラットフォームのバージョン: **4.18.2010.7**<br/>
&ensp;エンジンのバージョン: **1.1.17600.5**<br/>
&ensp;署名のバージョン: **1.327.658.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- Microsoft Defender ウイルス対策の署名を更新しました
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;パッケージのバージョン: **1.1.2011.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2009.7**<br/>
&ensp;エンジンのバージョン: **1.1.17600.5**<br/>
&ensp;署名のバージョン: **1.327.344.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;パッケージのバージョン: **1.1.2011.01**<br/>
&ensp;プラットフォームのバージョン: **4.18.2008.9**<br/>
&ensp;エンジンのバージョン: **1.1.17400.5**<br/>
&ensp;署名のバージョン: **1.327.2216.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- Windows 10 RS1 以降の OS インストール イメージのサポートを追加しました。
<br/>
</details>

## <a name="more-resources"></a>その他のリソース

| 記事 | 説明  |
|:---|:---|
|[Windows オペレーティング システムのインストール イメージ用の Microsoft Defender 更新プログラム](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | 自分の OS インストール イメージ (WIM と VHD ファイル) に適したマルウェア対策更新プログラム パッケージを確認します。 Windows 10 (Enterprise、Pro、Home エディション)、Windows Server 2019、Windows Server 2022、および Windows Server 2016 のインストール イメージ用の Microsoft Defender ウイルス対策更新プログラムを入手します。  |
|[保護更新プログラムをダウンロードして適用する方法を管理する](manage-protection-updates-microsoft-defender-antivirus.md) | 保護更新プログラムは、多くのソースを介して配信されます。 |
|[保護更新プログラムをダウンロードして適用するタイミングを管理する](manage-protection-update-schedule-microsoft-defender-antivirus.md) | 保護更新プログラムをダウンロードするタイミングをスケジュールできます。 |
|[最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md) | エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインするときに、強制的に更新またはスキャンすることができます。 |
|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md) | 保護更新プログラムは、起動時または特定のクラウド配信保護イベントの後にダウンロードされるように設定できます。 |
|[モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| バッテリー電源で更新を行う必要があるかどうかなど、モバイル デバイスや仮想マシンに特に役立つ設定を指定できます。 |
| [EDR センサー用の Microsoft Defender for Endpoint 更新プログラム](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) | 2021 年にリリースされた新しい Microsoft Defender for Endpoint 統合ソリューション パッケージに含まれている EDR センサー (MsSense.exe) を更新できます。   |

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
