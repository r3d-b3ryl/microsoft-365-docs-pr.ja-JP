---
title: 更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する
description: 保護と製品Microsoft Defender ウイルス対策受け取る方法を管理します。
keywords: 更新プログラム、セキュリティ 基準、保護、更新のスケジュール、強制的な更新、モバイル更新、wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 09/08/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 5745e5ee7604636b3ae3595ba907e055b86cc012
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491339"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

最新Microsoft Defender ウイルス対策維持は、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。 パッシブ モードで実行されている場合でも、ウイルス対策Microsoft Defender ウイルス対策[更新してください。](microsoft-defender-antivirus-compatibility.md) 更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。

- セキュリティ インテリジェンスの更新プログラム
- 製品の更新

> [!TIP]
> 最新のエンジン、プラットフォーム、署名の日付を確認するには、セキュリティ インテリジェンスの更新プログラム[(Microsoft Defender ウイルス対策その他の Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)マルウェア対策に関するページをご覧ください。

## <a name="security-intelligence-updates"></a>セキュリティ インテリジェンスの更新プログラム

Microsoft Defender ウイルス対策[は、](cloud-protection-microsoft-defender-antivirus.md)クラウド配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。

> [!NOTE]
> 更新プログラムは、次の KB 番号の下でリリースされます。
>
> - Microsoft Defender ウイルス対策: KB2267602
> - System Center Endpoint Protection: KB2461484

クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。 セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。 詳細については、「Microsoft クラウド提供の保護を使用する」を参照[Microsoft Defender ウイルス対策。](cloud-protection-microsoft-defender-antivirus.md)

最近のセキュリティ インテリジェンス更新プログラムの一覧については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。

## <a name="product-updates"></a>製品の更新

Microsoft Defender ウイルス対策プラットフォーム更新 [プログラムと呼ばれる月次更新プログラム (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *が必要です*。

更新プログラムの配布は、次のいずれかの方法で管理できます。

- [Windowsサーバー更新サービス (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Microsoft を展開し、ネットワーク内のエンドポイントWindows更新プログラムを展開するために使用する通常の方法です。

詳細については、「保護更新プログラム[のソースを管理するMicrosoft Defender ウイルス対策を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

> [!NOTE]
>
> - 月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。
> - この記事では、広範なリリース チャネルに含まれる変更の一覧を示します。 [最新の広範なチャネル リリースについては、こちらを参照してください](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)。
> - 段階的なロールアウト プロセスの詳細、および次のリリースの詳細については、「Microsoft Defender 更新プログラムの段階的なロールアウト プロセスの管理」 [を参照してください](manage-gradual-rollout.md)。
> - セキュリティ インテリジェンスの更新プログラムの詳細については、「セキュリティ インテリジェンスの更新プログラム 」および「Microsoft Defender ウイルス対策 Microsoft マルウェア対策」[を参照してください](https://www.microsoft.com/wdsi/defenderupdates)。

## <a name="monthly-platform-and-engine-versions"></a>月次プラットフォームとエンジンのバージョン

プラットフォーム更新プログラムを更新またはインストールする方法については[、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。

すべての更新プログラムに含まれるもの

- パフォーマンスの向上。
- サービスの改善。そして
- 統合の改善 (クラウド[、Microsoft 365 Defender)。](/microsoft-365/security/defender/microsoft-365-defender)
<br/>
<details>
<summary> 2021 年 8 月 (プラットフォーム: 4.18.2108.7 |エンジン: 1.1.18500.10)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.349.22.0**<br/>
&ensp;リリース日: **2021** 年 9 月 2 日<br/>
&ensp;プラットフォーム: **4.18.2108.7**<br/>
&ensp;エンジン: **1.1.18500.10**<br/>
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**<br/>

### <a name="whats-new"></a>新機能
- 動作監視エンジンの機能強化
- 新しい[パフォーマンス アナライザーをリリースMicrosoft Defender ウイルス対策](tune-performance-defender-antivirus.md)
- Microsoft Defender ウイルス対策 DLL の読み込みに対する強化
- Microsoft Defender ウイルス対策 TrustedInstaller バイパスに対して強化される
- ルールごとの攻撃表面縮小ルールの除外を構成 [するためのサポートが追加されました](customize-attack-surface-reduction.md)
- ファイル変更通知を拡張して、ランサムウェア (HumOR) Human-Operatedデータを含める

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 7 月 (プラットフォーム: 4.18.2107.4 |エンジン: 1.1.18400.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.345.13.0**<br/>
&ensp;リリース日: **2021** 年 8 月 5 日<br/>
&ensp;プラットフォーム: **4.18.2107.4**<br/>
&ensp;エンジン: **1.1.18400.4**<br/>
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**<br/>

### <a name="whats-new"></a>新機能
- ポータブル デバイスのデバイス制御Windows追加
- 望ましくない可能性のあるアプリケーション (PUA) 保護は、コンシューマーに対して既定で有効になっています (「望ましくない可能性のあるアプリは既定でブロックされる」[を参照)](https://support.microsoft.com/windows/potentially-unwanted-apps-will-be-blocked-by-default-b9f53cb9-7f1e-40bb-8c6b-a17e0ab6289e)
- グループ ポリシー オブジェクト管理システムのスケジュールされたスキャンは、ユーザーが構成したスキャン時間に従います
- 動作監視エンジンの機能強化

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 6 月 (プラットフォーム: 4.18.2106.5 |エンジン: 1.1.18300.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.343.17.0**<br/>
&ensp;リリース: **2021 年 6 月 28 日**<br/>
&ensp;プラットフォーム: **4.18.2106.5**<br/>
&ensp;エンジン: **1.1.18300.4**<br/>
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**<br/>

### <a name="whats-new"></a>新機能
- Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール。 [「Microsoft Defender 更新プログラムの段階的なロールアウト プロセスの管理」を参照してください](manage-gradual-rollout.md)。
- 動作監視エンジンの改善
- マルウェア対策定義のロールアウトの改善
- 拡張エッジ ネットワーク イベント検査

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ

新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。 このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。
<details>
<summary> May-2021 (プラットフォーム: 4.18.2105.4 |エンジン: 1.1.18200.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.341.8.0**<br/>
&ensp;リリース: **2021 年 6** 月 3 日<br/>
&ensp;プラットフォーム: **4.18.2105.4**<br/>
&ensp;エンジン: **1.1.18200.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- 動作監視 [の改善](client-behavioral-blocking.md)
- 固定 [ネットワーク保護通知](network-protection.md) フィルター機能

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 4 月 (プラットフォーム: 4.18.2104.14 |エンジン: 1.1.18100.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.337.2.0**<br/>
&ensp;リリース: **2021**  年 4 月 26 日 (エンジン: 1.1.18100.6 リリース 2021 年 5 月 5 日)<br/>
&ensp;プラットフォーム: **4.18.2104.14**<br/>
&ensp;エンジン: **1.1.18100.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- その他の動作監視ロジック
- カーネル モードのキー ロガー検出の改善
- Microsoft Defender 更新プログラムの段階的なロールアウト プロセスを管理するための新しいコントロール [が追加されました](manage-gradual-rollout.md)


### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**<br/>
&ensp;リリース: **2021 年 4 月 2 日**<br/>
&ensp;プラットフォーム: **4.18.2103.7**<br/>
&ensp;エンジン: **1.1.18000.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- 動作監視エンジンの改善
- ネットワークブルートフォース攻撃の軽減策の拡張
- タンパープロテクションが有効な場合の改ざん試行イベント [の生成に](prevent-changes-to-security-settings-with-tamper-protection.md) 失敗する回数が多い

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**<br/>
&ensp;リリース: **2021** 年 3 月 9 日<br/>
&ensp;プラットフォーム: **4.18.2102.3**<br/>
&ensp;エンジン: **1.1.17900.7**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- 改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)
- 改ざん防止スコープの拡張

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**<br/>
&ensp;リリース: **2021 年 2 月 2 日**<br/>
&ensp;プラットフォーム: **4.18.2101.9**<br/>
&ensp;エンジン: **1.1.17800.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- シェルコードの悪用検出の改善
- 資格情報の盗用の試行の可視性の向上
- サービスのスパム対策機能Microsoft Defender ウイルス対策強化
- x64 エミュレーションのARM強化
- 修正: EDRの保護が最初の検出を実行した後、ブロック通知が脅威履歴に残る

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**<br/>
&ensp;リリース日: **2020 年 12 月 3 日**<br/>
&ensp;プラットフォーム: **4.18.2011.6**<br/>
&ensp;エンジン: **1.1.17700.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details><details>
<summary> 2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**<br/>
&ensp;リリース: **2020 年 10 月 29 日**<br/>
&ensp;プラットフォーム: **4.18.2010.7**<br/>
&ensp;エンジン: **1.1.17600.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- 特別な脅威カテゴリの新しい説明
- エミュレーション機能の強化
- ホスト アドレスの許可/ブロック機能の強化
- ローカル ユーザーの除外のマージを無視する Defender CSP の新しいオプション

### <a name="known-issues"></a>既知の問題

既知の問題はありません
<br/>
</details><details>
<summary> 2020 年 9 月 (プラットフォーム: 4.18.2009.7 |エンジン: 1.1.17500.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**<br/>
&ensp;リリース: **2020 年 10 月 1 日**<br/>
&ensp;プラットフォーム: **4.18.2009.7**<br/>
&ensp;エンジン: **1.1.17500.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- 検疫内のファイルを復元するには、管理者のアクセス許可が必要です
- XML 形式のイベントがサポートされる
- 除外マージを無視する CSP のサポート
- 次の新しい管理インターフェイス
   - UDP 検査
   - Server 2019 のネットワーク保護
   - ネットワーク保護の IP アドレスの除外
- TPM 測定値の可視性の向上
- VBA Officeスキャンの改善

### <a name="known-issues"></a>既知の問題

既知の問題はありません
<br/>
</details>
<details>
<summary> 2020 年 8 月 (プラットフォーム: 4.18.2008.9 |エンジン: 1.1.17400.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**<br/>
&ensp;リリース: **2020 年 8 月 27 日**<br/>
&ensp;プラットフォーム: **4.18.2008.9**<br/>
&ensp;エンジン: **1.1.17400.5**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- テレメトリ イベントの追加
- スキャン イベントの利用統計情報の向上
- メモリ スキャンの動作監視の改善
- マクロ ストリームのスキャンの改善
- `AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加
- [DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。 Microsoft Defender ウイルス対策ウイルス対策プログラムが検出されると、自動的にオフになります。


### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**<br/>
&ensp;リリース日: **2020 年 7 月 28 日**<br/>
&ensp;プラットフォーム: **4.18.2007.8**<br/>
&ensp;エンジン: **1.1.17300.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- BITS の利用統計情報の改善
- Authenticode コード署名証明書の検証の改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**<br/>
&ensp;リリース日: **2020 年 6 月 22 日**<br/>
&ensp;プラットフォーム: **4.18.2006.10**<br/>
&ensp;エンジン: **1.1.17200.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- サポート ログの場所 [を指定する可能性](./collect-diagnostic-data.md)
- パッシブ モードで積極的なキャッチアップ スキャンをスキップする。
- 測定された接続で Defender が更新を許可する
- キャッシュが無効な場合のパフォーマンス調整が修正されました
- レジストリ クエリの修正
- ADMX でのスキャンタイムランダム化の修正

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> May-2020 (プラットフォーム: 4.18.2005.4 |エンジン: 1.1.17100.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**<br/>
&ensp;リリース: **2020 年 5 月 26 日**<br/>
&ensp;プラットフォーム: **4.18.2005.4**<br/>
&ensp;エンジン: **1.1.17100.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- スキャン イベントのログ記録の改善
- ユーザー モードのクラッシュ処理が改善されました。
- タンパープロテクション用のイベント トレースを追加しました
- 固定 AMSI サンプル申請
- AMSI クラウドのブロックを修正しました
- 固定セキュリティ更新プログラムのインストール ログ

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> April-2020 (プラットフォーム: 4.18.2004.6 |エンジン: 1.1.17000.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**<br/>
&ensp;リリース: **2020 年 4 月 30 日**<br/>
&ensp;プラットフォーム: **4.18.2004.6**<br/>
&ensp;エンジン: **1.1.17000.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能
- WDfilter の機能強化
- アクション可能なイベント データを追加して、表面の縮小検出イベントを攻撃する
- 診断データと WMI の固定バージョン情報
- プラットフォーム更新後の UI のプラットフォーム バージョンが正しくないのを修正しました
- ファイルレス脅威保護用の動的 URL intel
- UEFI スキャン機能
- 更新プログラムのログを拡張する

### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 3 月 (プラットフォーム: 4.18.2003.8 |エンジン: 1.1.16900.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**<br/>
&ensp;リリース: **2020 年 3 月 24 日**<br/>
&ensp;プラットフォーム: **4.18.2003.8**<br/>
&ensp;エンジン: **1.1.16900.4**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)
- 診断機能の向上
- セキュリティ インテリジェンス のタイムアウトを減らす (5 分)
- AMSI エンジンの内部ログ機能を拡張する
- プロセスブロックの通知を改善する

### <a name="known-issues"></a>既知の問題
[**固定**]Microsoft Defender ウイルス対策実行中にファイルをスキップしている場合。

<br/>
</details>

<details>

<summary> 2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</summary>


&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0**<br/>
&ensp;リリース: **2020 年 2 月 25 日**<br/>
&ensp;プラットフォーム/クライアント: **-**<br/>
&ensp;エンジン: **1.1.16800.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能


### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</summary>


セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**<br/>
リリース: **2020 年 1 月 30 日**<br/>
プラットフォーム/クライアント: **4.18.2001.10**<br/>
エンジン: **1.1.16700.2**<br/>
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**<br/>

### <a name="whats-new"></a>新機能

- WS2016 の固定 BSOD とExchange
- TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする
- プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- 緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)
- Fix 4.18.1911.3 ハング

### <a name="known-issues"></a>既知の問題

[**固定**] モダン [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。  影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。
<br/>
> [!IMPORTANT]
> この更新プログラムは次の場合です。
> - SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。
> - ハングの問題があるシステムの再起動フラグがあります。
> - は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。
> - は、再起動要件による更新プログラムとして分類されます。そして
> - は、更新プログラムでのみ[Windowsされます](https://support.microsoft.com/help/4027667/windows-10-update)。
<br/>
</details>

<details>
<summary> 2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</summary>

セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**<br/>
リリース日: **2019 年 12** 月 7 日<br/>
プラットフォーム: **4.18.1911.3**<br/>
エンジン: **1.1.17000.7**<br/>
サポート フェーズ: **サポートなし**<br/>

### <a name="whats-new"></a>新機能

- 固定 MpCmdRun トレース レベル
- WDFilter のバージョン情報を修正しました
- 通知の改善 (PUA)
- MRT ログをサポート ファイルに追加する

### <a name="known-issues"></a>既知の問題
この更新プログラムをインストールすると、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.18.2001.10 が必要です。
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender ウイルス対策サポート

プラットフォームとエンジンの更新プログラムは、毎月提供されます。 完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。 サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。

- **セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。

- **テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。 N-2 より古いプラットフォーム バージョンはサポートされなくなりました。*

\*Windows 10 リリース バージョン (Windows 10 リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引[き続き](#platform-version-included-with-windows-10-releases)テクニカル サポートが提供されます。

テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。 サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (*)へのアップグレードを求める要求が表示されます。

### <a name="platform-version-included-with-windows-10-releases"></a>プラットフォームのバージョンは、Windows 10リリースに含まれています

次の表に、最新Microsoft Defender ウイルス対策リリースに同梱されているプラットフォームとエンジンのWindows 10示します。<br/><br/>

|Windows 10リリース  |プラットフォームのバージョン  |エンジンのバージョン |サポート フェーズ |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | テクニカル アップグレード のサポート (のみ) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | テクニカル アップグレード のサポート (のみ) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | テクニカル アップグレード のサポート (のみ) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | テクニカル アップグレード のサポート (のみ) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | テクニカル アップグレード のサポート (のみ) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | テクニカル アップグレード のサポート (のみ) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | テクニカル アップグレード のサポート (のみ) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | テクニカル アップグレード のサポート (のみ) |

リリースWindows 10については、「ライフサイクル ファクト[シートWindowsを参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>展開イメージのサービスと管理 (DISM) の更新プログラム

Windows 10 (Enterprise、Pro、ホーム エディション)、Windows Server 2019、Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。 OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。

詳細については、「Microsoft Defender update for Windows オペレーティング システムのインストール[イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。

<details>
<summary>1.1.2109.01</summary>

&ensp;パッケージのバージョン: **1.1.2109.01**<br/>
&ensp;プラットフォーム バージョン: **4.18.2107.4**<br/>
&ensp;エンジンのバージョン: **1.1.18400.5**<br/>
&ensp;署名バージョン: **1.347.891.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2108.01</summary>

&ensp;パッケージのバージョン: **1.1.2108.01**<br/>
&ensp;プラットフォーム バージョン: **4.18.2107.4**<br/>
&ensp;エンジンのバージョン: **1.1.18300.4**<br/>
&ensp;署名バージョン: **1.343.2244.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2107.02</summary>

&ensp;パッケージのバージョン: **1.1.2107.02**<br/>
&ensp;プラットフォーム のバージョン: **4.18.2105.5**<br/>
&ensp;エンジンのバージョン: **1.1.18300.4**<br/>
&ensp;署名バージョン: **1.343.658.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2106.01</summary>

&ensp;パッケージ のバージョン: **1.1.2106.01**<br/>
&ensp;プラットフォーム のバージョン: **4.18.2104.14**<br/>
&ensp;エンジンのバージョン: **1.1.18100.6**<br/>
&ensp;署名バージョン: **1.339.1923.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;パッケージのバージョン: **1.1.2105.01**<br/>
&ensp;プラットフォーム のバージョン: **4.18.2103.7**<br/>
&ensp;エンジンのバージョン: **1.1.18100.6**<br/>
&ensp;署名バージョン: **1.339.42.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;パッケージのバージョン: **1.1.2104.01**<br/>
&ensp;プラットフォーム のバージョン: **4.18.2102.4**<br/>
&ensp;エンジンのバージョン: **1.1.18000.5**<br/>
&ensp;署名バージョン: **1.335.232.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;パッケージのバージョン: **1.1.2103.01**<br/>
&ensp;プラットフォーム バージョン: **4.18.2101.9**<br/>
&ensp;エンジンのバージョン: **1.1.17800.5**<br/>
&ensp;署名バージョン: **1.331.2302.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;パッケージのバージョン: **1.1.2102.03**<br/>
&ensp;プラットフォーム バージョン: **4.18.2011.6**<br/>
&ensp;エンジンのバージョン: **1.1.17800.5**<br/>
&ensp;署名バージョン: **1.331.174.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;パッケージ のバージョン: **1.1.2101.02**<br/>
&ensp;プラットフォーム バージョン: **4.18.2011.6**<br/>
&ensp;エンジンのバージョン: **1.1.17700.4**<br/>
&ensp;署名バージョン: **1.329.1796.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;パッケージのバージョン: **1.1.2012.01**<br/>
&ensp;プラットフォーム のバージョン: **4.18.2010.7**<br/>
&ensp;エンジンのバージョン: **1.1.17600.5**<br/>
&ensp;署名バージョン: **1.327.1991.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;パッケージ のバージョン: **1.1.2011.02**<br/>
&ensp;プラットフォーム のバージョン: **4.18.2010.7**<br/>
&ensp;エンジンのバージョン: **1.1.17600.5**<br/>
&ensp;署名バージョン: **1.327.658.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- 更新されたMicrosoft Defender ウイルス対策署名
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;パッケージ のバージョン: **1.1.2011.01**<br/>
&ensp;プラットフォーム バージョン: **4.18.2009.7**<br/>
&ensp;エンジンのバージョン: **1.1.17600.5**<br/>
&ensp;署名バージョン: **1.327.344.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- なし
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;パッケージ のバージョン: **1.1.2011.01**<br/>
&ensp;プラットフォーム バージョン: **4.18.2008.9**<br/>
&ensp;エンジンのバージョン: **1.1.17400.5**<br/>
&ensp;署名バージョン: **1.327.2216.0**<br/>

### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>その他の情報
- RS1 以降の OS Windows 10インストール イメージのサポートが追加されました。
<br/>
</details>

## <a name="more-resources"></a>その他のリソース

| 記事 | 説明  |
|:---|:---|
|[Microsoft Defender のオペレーティング システムインストール イメージWindows更新プログラム](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。 Microsoft Defender ウイルス対策 (Enterprise Windows 10、Pro、およびホーム エディション)、Windows Server 2019、およびインストール イメージWindows Server 2016更新プログラムを取得します。  |
|[保護更新プログラムのダウンロードと適用方法を管理する](manage-protection-updates-microsoft-defender-antivirus.md) | 保護更新プログラムは、多くのソースを介して配信できます。 |
|[保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md) | 保護更新プログラムをダウンロードするスケジュールを設定できます。 |
|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md) | エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。 |
|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md) | 保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。 |
|[モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。 |
