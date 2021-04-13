---
title: Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する
description: Microsoft Defender Antivirus が保護と製品の更新プログラムを受け取る方法を管理します。
keywords: 更新プログラム、セキュリティ 基準、保護、更新のスケジュール、強制的な更新、モバイル更新、wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690981"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。

- セキュリティ インテリジェンスの更新プログラム
- 製品の更新

> [!IMPORTANT]
> Microsoft Defender ウイルス対策を最新の状態に保つことは、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するために重要です。  
> Microsoft Defender Antivirus がパッシブ モードで実行されている場合でも、ウイルス対策保護を [更新してください](./microsoft-defender-antivirus-compatibility.md)。
> 
> 最新のエンジン、プラットフォーム、署名の日付を確認するには、Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

## <a name="security-intelligence-updates"></a>セキュリティ インテリジェンスの更新プログラム

Microsoft Defender Antivirus は、 [クラウド](cloud-protection-microsoft-defender-antivirus.md) 配信の保護 (Microsoft Advanced Protection Service または MAPS とも呼ばれる) を使用し、セキュリティ インテリジェンス更新プログラムを定期的にダウンロードして保護を提供します。

> [!NOTE]
> 更新プログラムは、次の KB 番号の下でリリースされます。  
> Microsoft Defender ウイルス対策: KB2267602  
> System Center Endpoint Protection: KB2461484

クラウドによる保護は常にオンであり、インターネットへのアクティブな接続が機能する必要があります。 セキュリティ インテリジェンスの更新は、スケジュールされたケイデンス (ポリシーを介して構成可能) で行われます。 詳細については [、「Use Microsoft cloud-provided protection in Microsoft Defender Antivirus」を参照してください](cloud-protection-microsoft-defender-antivirus.md)。 

最近のセキュリティ インテリジェンス更新プログラムの一覧については、「Microsoft Defender Antivirus および他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム」 [を参照してください](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

エンジンの更新プログラムは、セキュリティ インテリジェンスの更新プログラムに含まれており、毎月リリースされます。

## <a name="product-updates"></a>製品の更新

Microsoft Defender ウイルス対策では、月次更新[プログラム (KB4052623) (](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)プラットフォーム更新プログラムと呼ばれる) が必要であり、Windows 10 リリースと共に主要な機能更新プログラムを受け取る予定です。 

更新プログラムの配布は、次のいずれかの方法で管理できます。 

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- ネットワーク内のエンドポイントに Microsoft および Windows の更新プログラムを展開するために使用する通常の方法。

詳細については [、「Microsoft Defender ウイルス対策保護更新プログラムのソースを管理する」を参照してください](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

> [!NOTE]
> 月次更新プログラムは段階的にリリースされ、Window Server Update Services に複数のパッケージ [が表示されます](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。

## <a name="monthly-platform-and-engine-versions"></a>月次プラットフォームとエンジンのバージョン

プラットフォーム更新プログラムを更新またはインストールする方法については [、「Update for Windows Defenderマルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。

すべての更新プログラムに含まれるもの 
- パフォーマンスの向上。
- サービスの改善。そして 
- 統合の改善 (クラウド、Microsoft 365 Defender)。
<br/><br/>

<details>
<summary> 2021 年 3 月 (プラットフォーム: 4.18.2103.7 |エンジン: 1.1.18000.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.335.36.0**  
&ensp;リリース: **2021** 年 4 月 1 日  
&ensp;プラットフォーム: **4.19.2103.7**  
&ensp;エンジン: **1.1.18000.5**  
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**
    
### <a name="whats-new"></a>新機能

- 動作監視エンジンの改善 
- ネットワークブルートフォース攻撃の軽減策の拡張 
- タンパープロテクションが有効な場合の改ざん試行イベント [の追加](prevent-changes-to-security-settings-with-tamper-protection.md) 生成に失敗しました

### <a name="known-issues"></a>既知の問題
既知の問題はありません  
<br/>
</details><details>
<summary> 2021 年 2 月 (プラットフォーム: 4.18.2102.3 |エンジン: 1.1.17900.7)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.333.7.0**  
&ensp;リリース: **2021** 年 3 月 9 日  
&ensp;プラットフォーム: **4.19.2102.3**  
&ensp;エンジン: **1.1.17900.7**  
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**
    
### <a name="whats-new"></a>新機能

- 改ざん防止によるサービス [回復の改善](prevent-changes-to-security-settings-with-tamper-protection.md)
- 改ざん防止スコープの拡張

### <a name="known-issues"></a>既知の問題
既知の問題はありません  
<br/>
</details><details>
<summary> 2021 年 1 月 (プラットフォーム: 4.18.2101.9 |エンジン: 1.1.17800.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**  
&ensp;リリース: **2021 年 2 月 2 日**  
&ensp;プラットフォーム: **4.18.2101.9**  
&ensp;エンジン: **1.1.17800.5**  
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**
    
### <a name="whats-new"></a>新機能

- シェルコードの悪用検出の改善
- 資格情報の盗用の試行の可視性の向上
- Microsoft Defender ウイルス対策サービスのスパム対策機能の改善点
- x64 エミュレーションのARM強化
- 修正: EDR ブロック通知は、リアルタイム保護が初期検出を実行した後も脅威の履歴に残ります

### <a name="known-issues"></a>既知の問題
既知の問題はありません  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>以前のバージョンの更新プログラム: 技術アップグレードのサポートのみ

新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。 このセクションに記載されているバージョンより古いバージョンで、テクニカル アップグレード のサポートにのみ提供されます。 
<br/><br/>
<details>
<summary> 2020 年 11 月 (プラットフォーム: 4.18.2011.6 |エンジン: 1.1.17700.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.1854.0**  
&ensp;リリース日: **2020 年 12 月 3 日**  
&ensp;プラットフォーム: **4.18.2011.6**  
&ensp;エンジン: **1.1.17700.4**  
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**
    
### <a name="whats-new"></a>新機能

- SmartScreen [の状態サポートログ](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません  
<br/>
</details><details>
<summary> 2020 年 10 月 (プラットフォーム: 4.18.2010.7 |エンジン: 1.1.17600.5)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.327.7.0**  
&ensp;リリース: **2020 年 10 月 29 日**  
&ensp;プラットフォーム: **4.18.2010.7**  
&ensp;エンジン: **1.1.17600.5**  
&ensp;サポート フェーズ: **セキュリティと重要な更新プログラム**
    
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

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.325.10.0**  
&ensp;リリース: **2020 年 10 月 1 日**  
&ensp;プラットフォーム: **4.18.2009.7**  
&ensp;エンジン: **1.1.17500.4**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
    
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

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.323.9.0**  
&ensp;リリース: **2020 年 8 月 27 日**  
&ensp;プラットフォーム: **4.18.2008.9**  
&ensp;エンジン: **1.1.17400.5**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**

### <a name="whats-new"></a>新機能

- テレメトリ イベントの追加
- スキャン イベントの利用統計情報の向上
- メモリ スキャンの動作監視の改善
- マクロ ストリームのスキャンの改善
- `AMRunningMode`PowerShell コマンドレットGet-MpComputerStatus追加
- [DisableAntiSpyware は](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 無視されます。 Microsoft Defender ウイルス対策は、別のウイルス対策プログラムを検出すると自動的に無効になります。


### <a name="known-issues"></a>既知の問題
既知の問題はありません  
<br/>
</details>

<details>
<summary> 2020 年 7 月 (プラットフォーム: 4.18.2007.8 |エンジン: 1.1.17300.4)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.321.30.0**  
&ensp;リリース日: **2020 年 7 月 28 日**  
&ensp;プラットフォーム: **4.18.2007.8**  
&ensp;エンジン: **1.1.17300.4**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
    
### <a name="whats-new"></a>新機能

- BITS の利用統計情報の改善
- Authenticode コード署名証明書の検証の改善

### <a name="known-issues"></a>既知の問題
既知の問題はありません  
<br/>
</details>

<details>
<summary> 2020 年 6 月 (プラットフォーム: 4.18.2006.10 |エンジン: 1.1.17200.2)</summary>

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.319.20.0**  
&ensp;リリース日: **2020 年 6 月 22 日**  
&ensp;プラットフォーム: **4.18.2006.10**  
&ensp;エンジン: **1.1.17200.2**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
    
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

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.317.20.0**  
&ensp;リリース: **2020 年 5 月 26 日**  
&ensp;プラットフォーム: **4.18.2005.4**  
&ensp;エンジン: **1.1.17100.2**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
    
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

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.315.12.0**  
&ensp;リリース: **2020 年 4 月 30 日**  
&ensp;プラットフォーム: **4.18.2004.6**  
&ensp;エンジン: **1.1.17000.2**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
    
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

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.313.8.0**  
&ensp;リリース: **2020 年 3 月 24 日**  
&ensp;プラットフォーム: **4.18.2003.8**  
&ensp;エンジン: **1.1.16900.4**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
    
### <a name="whats-new"></a>新機能

- MPCmdRun に追加された [CPU 調整オプション](./command-line-arguments-microsoft-defender-antivirus.md)
- 診断機能の向上
- セキュリティ インテリジェンス のタイムアウトを減らす (5 分)
- AMSI エンジンの内部ログ機能を拡張する
- プロセスブロックの通知を改善する
   
### <a name="known-issues"></a>既知の問題
[**固定**]Microsoft Defender ウイルス対策は、スキャンを実行するときにファイルをスキップしています。

<br/>
</details>

<details>

<summary> 2020 年 2 月 ~2020 年 (プラットフォーム: - |エンジン: 1.1.16800.2)</summary>
  

&ensp;セキュリティ インテリジェンス更新プログラムのバージョン: **1.311.4.0**   
&ensp;リリース: **2020 年 2 月 25 日**  
&ensp;プラットフォーム/クライアント: **-**  
&ensp;エンジン: **1.1.16800.2**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
     
### <a name="whats-new"></a>新機能

  
### <a name="known-issues"></a>既知の問題
既知の問題はありません
<br/>
</details>

<details>
<summary> 2020 年 1 月 (プラットフォーム: 4.18.2001.10 |エンジン: 1.1.16700.2)</summary>
  

セキュリティ インテリジェンス更新プログラムのバージョン: **1.309.32.0**  
リリース: **2020 年 1 月 30 日**  
プラットフォーム/クライアント: **4.18.2001.10**  
エンジン: **1.1.16700.2**  
&ensp;サポート フェーズ: **テクニカル アップグレード のサポート (のみ)**
     
### <a name="whats-new"></a>新機能

- Exchange を使用した WS2016 の固定 BSOD
- TMP がネットワーク パスにリダイレクトされる場合のプラットフォームの更新をサポートする
- プラットフォームとエンジンのバージョンが [WDSI に追加される](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- 緊急署名の更新をパッシブ モード [に拡張する](./microsoft-defender-antivirus-compatibility.md)
- Fix 4.18.1911.3 ハング
   
### <a name="known-issues"></a>既知の問題

[**固定**] 最新の [](/windows-hardware/design/device-experiences/modern-standby)スタンバイ モードを利用するデバイスでは、保護のギャップWindows Defenderフィルター ドライバーでハングが発生する可能性があります。  影響を受けるコンピューターは、最新のマルウェア対策プラットフォームに更新されていないと顧客に表示されます。  
<br/>
> [!IMPORTANT]
> この更新プログラムは次の場合です。
> - SHA2 をサポートするために、より低いバージョンのプラットフォームを実行している RS1 デバイスが必要とします。
> - ハングの問題があるシステムの再起動フラグがあります。
> - は 2020 年 4 月に再リリースされ、将来の可用性を維持するために新しい更新プログラムに置き換えされません。  
> - は、再起動要件による更新プログラムとして分類されます。そして
> - は Windows Update でのみ [提供されます](https://support.microsoft.com/help/4027667/windows-10-update)。
<br/>
</details>

<details>
<summary> 2019 年 11 月 (プラットフォーム: 4.18.1911.3 |エンジン: 1.1.16600.7)</summary>

セキュリティ インテリジェンス更新プログラムのバージョン: **1.307.13.0**  
リリース日: **2019 年 12** 月 7 日  
プラットフォーム: **4.18.1911.3**  
エンジン: **1.1.17000.7**  
サポート フェーズ: **サポートなし**  
     
### <a name="whats-new"></a>新機能

- 固定 MpCmdRun トレース レベル
- WDFilter のバージョン情報を修正しました
- 通知の改善 (PUA)
- MRT ログをサポート ファイルに追加する
   
### <a name="known-issues"></a>既知の問題
この更新プログラムがインストールされている場合、最新のプラットフォーム バージョンに更新するには、ジャンプ パッケージ 4.10.2001.10 が必要です。
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender ウイルス対策プラットフォームのサポート
プラットフォームとエンジンの更新プログラムは、毎月提供されます。 完全にサポートするには、最新のプラットフォーム更新プログラムを最新の状態に保つ必要があります。 サポート構造は動的で、最新のプラットフォーム バージョンの可用性に応じて 2 つのフェーズに進化しています。

- **セキュリティと重要な更新** プログラムのサービス フェーズ - 最新のプラットフォーム バージョンを実行すると、マルウェア対策プラットフォームに対するセキュリティ更新プログラムと重要な更新プログラムの両方を受け取る資格があります。
 
- **テクニカル サポート (のみ)** フェーズ - 新しいプラットフォーム バージョンがリリースされると、以前のバージョン (N-2) のサポートはテクニカル サポートにのみ減少します。 N-2 より古いプラットフォーム バージョンはサポートされなくなりました。*

\* Windows 10 リリース バージョン (Windows [10](#platform-version-included-with-windows-10-releases)リリースに含まれるプラットフォーム バージョンを参照) から最新のプラットフォーム バージョンへのアップグレードについては、引き続きテクニカル サポートが提供されます。

テクニカル サポート (のみ) フェーズでは、Microsoft Customer Service & サポートと Microsoft のマネージ サポートサービス (プレミア サポートなど) を通じて、商業的に合理的なサポート インシデントが提供されます。 サポート インシデントで、さらなるガイダンスのために開発へのエスカレーションが必要な場合、セキュリティ以外の更新プログラムが必要な場合、またはセキュリティ更新プログラムが必要な場合は、最新のプラットフォーム バージョンまたは中間更新プログラム (*)へのアップグレードを求める要求が表示されます。

### <a name="platform-version-included-with-windows-10-releases"></a>Windows 10 リリースに含まれるプラットフォームのバージョン
次の表に、最新の Windows 10 リリースに同梱されている Microsoft Defender ウイルス対策プラットフォームとエンジン のバージョンを示します。    

|Windows 10 リリース  |プラットフォームのバージョン  |エンジンのバージョン |サポート フェーズ |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | テクニカル アップグレード のサポート (のみ) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | テクニカル アップグレード のサポート (のみ) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | テクニカル アップグレード のサポート (のみ) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | テクニカル アップグレード のサポート (のみ) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | テクニカル アップグレード のサポート (のみ) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | テクニカル アップグレード のサポート (のみ) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | テクニカル アップグレード のサポート (のみ) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | テクニカル アップグレード のサポート (のみ) |  

Windows 10 リリース情報については、「Windows ライフサイクル ファクト シート [」を参照してください](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>展開イメージのサービスと管理 (DISM) の更新プログラム

Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 OS インストール イメージを最新のウイルス対策およびマルウェア対策更新プログラムで更新することをお勧めします。 OS のインストール イメージを最新の状態に保つことは、保護のギャップを回避するのに役立ちます。 

詳細については、「Microsoft Defender update for Windows オペレーティング システム [インストール イメージ」を参照してください](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。

<details>
<summary>1.1.2104.01</summary>

&ensp;パッケージのバージョン: **1.1.2104.01**    
&ensp;プラットフォーム のバージョン: **4.18.2102.4**   
&ensp;エンジンのバージョン: **1.1.18000.5**  
&ensp;署名バージョン: **1.335.232.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- なし  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;パッケージのバージョン: **1.1.2103.01**    
&ensp;プラットフォーム バージョン: **4.18.2101.9**   
&ensp;エンジンのバージョン: **1.1.17800.5**  
&ensp;署名バージョン: **1.331.2302.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- なし  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;パッケージのバージョン: **1.1.2102.03**    
&ensp;プラットフォーム バージョン: **4.18.2011.6**   
&ensp;エンジンのバージョン: **1.1.17800.5**  
&ensp;署名バージョン: **1.331.174.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- なし  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;パッケージ のバージョン: **1.1.2101.02**    
&ensp;プラットフォーム バージョン: **4.18.2011.6**   
&ensp;エンジンのバージョン: **1.1.17700.4**  
&ensp;署名バージョン: **1.329.1796.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- なし  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;パッケージのバージョン: **1.1.2012.01**    
&ensp;プラットフォーム のバージョン: **4.18.2010.7**   
&ensp;エンジンのバージョン: **1.1.17600.5**  
&ensp;署名バージョン: **1.327.1991.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- なし  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;パッケージ のバージョン: **1.1.2011.02**    
&ensp;プラットフォーム のバージョン: **4.18.2010.7**   
&ensp;エンジンのバージョン: **1.1.17600.5**  
&ensp;署名バージョン: **1.327.658.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- Microsoft Defender ウイルス対策署名の更新  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;パッケージ のバージョン: **1.1.2011.01**    
&ensp;プラットフォーム バージョン: **4.18.2009.7**  
&ensp;エンジンのバージョン: **1.1.17600.5**  
&ensp;署名バージョン: **1.327.344.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- なし  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;パッケージ のバージョン: **1.1.2011.01**    
&ensp;プラットフォーム バージョン: **4.18.2008.9**   
&ensp;エンジンのバージョン: **1.1.17400.5**  
&ensp;署名バージョン: **1.327.2216.0**    
    
### <a name="fixes"></a>修正プログラム
- なし

### <a name="additional-information"></a>追加情報
- Windows 10 RS1 以降の OS インストール イメージのサポートが追加されました。  
<br/>
</details>

## <a name="additional-resources"></a>その他のリソース

| 記事 | 説明  |
|:---|:---|
|[Windows オペレーティング システムのインストール イメージ用の Microsoft Defender 更新プログラム](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | OS インストール イメージ (WIM ファイルと VHD ファイル) のマルウェア対策更新プログラム パッケージを確認します。 Windows 10 (Enterprise、Pro、および Home エディション)、Windows Server 2019、および Windows Server 2016 インストール イメージの Microsoft Defender ウイルス対策更新プログラムを取得します。  |
|[保護更新プログラムのダウンロードと適用方法を管理する](manage-protection-updates-microsoft-defender-antivirus.md) | 保護更新プログラムは、多くのソースを介して配信できます。 |
|[保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md) | 保護更新プログラムをダウンロードするスケジュールを設定できます。 |
|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md) | エンドポイントが更新またはスケジュールされたスキャンを見逃した場合は、ユーザーが次回サインインする場合に、強制的に更新またはスキャンを実行できます。 |
|[イベントベースの強制的な更新の管理](manage-event-based-updates-microsoft-defender-antivirus.md) | 保護更新プログラムは、起動時または特定のクラウド配信の保護イベントの後にダウンロードする設定できます。 |
|[モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| モバイル デバイスや仮想マシンに特に役立つ、バッテリーの電源で更新を行う必要があるかどうかなどの設定を指定できます。 |
