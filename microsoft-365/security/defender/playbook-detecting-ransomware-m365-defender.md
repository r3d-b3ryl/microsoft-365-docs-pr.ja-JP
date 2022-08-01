---
title: Microsoft 365 Defender による人間によるランサムウェア攻撃の検出
description: この記事では、Microsoft 365 Defender ポータルを使用して、人間が操作する新しいランサムウェア攻撃または進行中のランサムウェア攻撃を事前に検出する方法について説明します
search.appverid: MET150
author: nic-name
ms.author: noriordan
manager: dolmont
audience: ITPro
ms.topic: article
ms.date: 05/30/2022
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection: M365-security-compliance.
f1.keywords: NOCSH
ms.openlocfilehash: 95e916c02bc01a2e3e84d05efe4e5f5e66d3d491
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107087"
---
# <a name="detecting-human-operated-ransomware-attacks-with-microsoft-365-defender"></a>Microsoft 365 Defender による人間によるランサムウェア攻撃の検出

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ランサムウェアは、ファイルやフォルダーを破壊または暗号化し、重要なデータへのアクセスや重要なビジネス システムの中断を防ぐ一種の強要攻撃です。 ランサムウェアには次の 2 種類があります。

* コモディティ ランサムウェアは、フィッシングやデバイス間で拡散し、身代金を要求する前にファイルを暗号化するマルウェアです。
* 人間が操作するランサムウェアは、複数の攻撃方法を採用するアクティブなサイバー犯罪者による計画的で協調的な攻撃です。 多くの場合、組織に侵入し、強要する価値のある資産やシステムを見つけて身代金を要求するために、既知の手法とツールが使用されます。 ネットワークを侵害すると、攻撃者は、暗号化または強要できる資産とシステムの偵察を実行します。 その後、攻撃者は身代金を要求する前にデータを暗号化または流出します。

この記事では、次のセキュリティ サービスの拡張検出と応答 (XDR) ソリューションであるMicrosoft 365 Defender ポータルを使用して、人間が操作する新しいランサムウェア攻撃または進行中のランサムウェア攻撃をプロアクティブに検出する方法について説明します。

* Microsoft Defender for Endpoint
* Microsoft Defender for Office 365
* Microsoft Defender for Identity
* Microsoft Defender for Cloud Apps (アプリ ガバナンス アドオンを含む)
* Microsoft Azure AD Identity Protection
* Microsoft Defender for IoT
* Microsoft 365 Business Premium
* Microsoft Defender for Business

ランサムウェア攻撃の防止については、「 [ランサムウェアや強要から迅速に保護する](/security/compass/protect-against-ransomware-phase3)」を参照してください。

## <a name="the-importance-of-proactive-detection"></a>プロアクティブ検出の重要性

人間が操作するランサムウェアは通常、最も貴重なデータやシステムにリアルタイムで侵入して検出する手順を実行している可能性があるアクティブな攻撃者によって実行されるため、ランサムウェア攻撃を検出するために要した時間は非常に重要です。

身代金前アクティビティが迅速に検出されると、重大な攻撃を受ける可能性が低くなります。 通常、身代金前ステージには、初期アクセス、偵察、資格情報の盗難、横移動、永続性という手法が含まれます。 これらの手法は、最初は無関係に見え、多くの場合、レーダーの下を飛ぶ可能性があります。 これらの手法が身代金ステージにつながる場合、多くの場合、手遅れになります。 Microsoft 365 Defenderは、大規模なランサムウェア キャンペーンの一部として、これらの小規模で一見無関係なインシデントを特定するのに役立ちます。

* 身代金前の段階で検出された場合、感染したデバイスやユーザー アカウントの分離などの小規模な軽減策を使用して、攻撃を中断および修復できます。
* ファイルの暗号化に使用されるマルウェアがデプロイされている場合など、後の段階で検出が行われる場合は、ダウンタイムを引き起こす可能性のあるより積極的な修復手順を使用して、攻撃を中断して修復する必要があります。

ランサムウェア攻撃に対応する場合、業務の中断が発生する可能性があります。 ランサムウェア攻撃の最終段階は、多くの場合、大きなリスクを持つ攻撃者によって引き起こされるダウンタイムか、ネットワークの安全性を確保し、完全に調査する時間を与えるためにダウンタイムを制御するかの選択です。 身代金の支払いはお勧めしません。 ランサムウェア復号化キーを取得するためにサイバー犯罪者に支払うと、暗号化されたデータが復元される保証はありません。 ランサムウェア [の応答 - Microsoft セキュリティ ブログ](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)を参照してください。

ランサムウェア攻撃の影響と、検出なしで応答する時間と、プロアクティブな検出と対応の時間の定性的な関係を次に示します。

![ランサムウェア攻撃の影響と、検出なしで対応する時間と、プロアクティブな検出と応答の質的な関係により、ビジネスへの影響が減少し、対応が速くなります。](../../media/defender/playbook-detecting-ransomware-m365-defender-qualitative-diagram.png)

### <a name="proactive-detection-via-common-malware-tools-and-techniques"></a>一般的なマルウェア ツールと手法を使用したプロアクティブな検出

多くの場合、人間が操作するランサムウェア攻撃者は、フィッシング、ビジネス メール侵害 (BEC)、資格情報の盗難など、よく知られた、フィールドテストされたマルウェアの戦術、手法、ツール、手順を使用します。 セキュリティ アナリストは、攻撃者が一般的なマルウェアやサイバー攻撃の方法を使用して組織の足掛かりを得る方法について理解し、理解する必要があります。

ランサムウェア攻撃が一般的なマルウェアで開始される方法の例については、次のリソースを参照してください。

* [人間が操作するランサムウェア攻撃: 予防可能な災害](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
* [Microsoft 365 Defender ポータルのランサムウェア脅威分析レポート](https://sip.security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,exposureLevel,MisconfiguredDevices,VulnerableDevices,reportType,createdOn,lastUpdatedOn,tags,flag)

身代金前のマルウェア、ペイロード、アクティビティに精通していることは、攻撃の後の段階を防ぐために何を探すべきかをアナリストが把握するのに役立ちます。

## <a name="human-operated-ransomware-attack-tactics"></a>人間が操作するランサムウェア攻撃の戦術

人間が操作するランサムウェアは既知の攻撃手法とツールを使用できるため、アナリストが既存の攻撃手法とツールを理解し、経験することは、集中型ランサムウェア検出プラクティスのために SecOps チームを準備する際の貴重な資産になります。

### <a name="attack-tactics-and-methods"></a>攻撃の戦術と方法

次の [MITRE ATT&CK](https://attack.mitre.org/tactics/enterprise/) 戦術でランサムウェア攻撃者が使用する一般的な手法とツールを次に示します。

初期アクセス:

* RDP ブルート フォース
* 脆弱なインターネットに接続するシステム
* 脆弱なアプリケーション設定
* フィッシング詐欺メール

資格情報の盗難:

* Mimikatz
* LSA シークレット
* 資格情報コンテナー
* プレーンテキストの資格情報
* サービス アカウントの不正使用

横移動:

* Cobalt Strike
* WMI
* 管理ツールの悪用
* PsExec

固執：

* 新しいアカウント
* GPO の変更
* シャドウ IT ツール
* タスクをスケジュールする
* サービスの登録

防御回避:

* セキュリティ機能を無効にする
* ログ ファイルのクリア
* 攻撃アーティファクト ファイルの削除
* 変更されたファイルのタイムスタンプをリセットする

流出:

* 機密データの流出影響 (財務的な活用):
* インプレースおよびバックアップ内のデータの暗号化
* 配置されたデータとバックアップの削除。これは、前述の流出と組み合わされる可能性があります
* 流出した機密データのパブリック 漏えいの脅威

### <a name="what-to-look-for"></a>探す内容

セキュリティ アナリストにとっての課題は、機密データや重要なシステムを強要することを目的として、アラートが大規模な攻撃チェーンの一部である場合を認識することです。 たとえば、検出されたフィッシング攻撃は次のようになります。

* 組織の財務部門の誰かの電子メール メッセージを一度限り検出する攻撃。
* 侵害されたユーザー アカウントの資格情報を使用してユーザー アカウントで使用可能なリソースを検出し、より高いレベルの特権とアクセス権を持つ他のユーザー アカウントを侵害する攻撃チェーンの身代金前部分。

このセクションでは、一般的な攻撃フェーズと方法、および中央のMicrosoft 365 Defender ポータルにフィードするシグナル ソースについて説明します。これにより、セキュリティ分析に関連する複数のアラートで構成されるアラートとインシデントが作成されます。 場合によっては、攻撃データを表示する別のセキュリティ ポータルがあります。

#### <a name="initial-attacks-to-gain-entry"></a>エントリを取得するための最初の攻撃

攻撃者は、ユーザー アカウント、デバイス、またはアプリを侵害しようとしています。

攻撃方法 |シグナル ソース |代替セキュリティ ポータル
|:---|:---|:---
RDP ブルート フォース|Defender for Endpoint|Defender for Cloud Apps
脆弱なインターネットに接続するシステム|Windows セキュリティ機能、Microsoft Defender for Servers|
脆弱なアプリケーション設定      |Defender for Cloud Apps、Defender for Cloud Apps とアプリ ガバナンス アドオン|Defender for Cloud Apps |
悪意のあるアプリアクティビティ      |Defender for Cloud Apps、Defender for Cloud Apps とアプリ ガバナンス アドオン|Defender for Cloud Apps |
フィッシング詐欺メール        |Defender for Office 365
Azure AD アカウントに対するパスワード スプレー |Defender for Cloud Apps を使用した Azure AD Identity Protection      |Defender for Cloud Apps
オンプレミス アカウントに対するパスワード スプレー |Microsoft Defender for Identity
デバイス侵害       |Defender for Endpoint
資格情報の盗用       |Microsoft Defender for Identity
特権のエスカレーション      |Microsoft Defender for Identity

#### <a name="recent-spike-in-otherwise-typical-behavior"></a>それ以外の場合の一般的な動作の最近の急増

攻撃者は、侵害する追加のエンティティを調査しようとしています。

スパイク カテゴリ        |シグナル ソース                 |代替セキュリティ ポータル
|:---                    |:---                              |:---
サインイン: 失敗した回数が多い、短時間で複数のデバイスにログオンする試み、複数の初回ログオンなど。 |Defender for Cloud Apps を使用した Azure AD Identity Protection (Microsoft Defender for Identity) |Defender for Cloud Apps
最近アクティブなユーザー アカウント、グループ、コンピューター アカウント、アプリ |Defender for Cloud Apps (Azure AD) による Azure AD Identity Protection、Defender for Identity (Active Directory Domain Services [AD DS]) |Defender for Cloud Apps
データ アクセスなどの最近のアプリ アクティビティ |Defender for Cloud Apps とアプリ ガバナンス アドオンを使用するアプリ |Defender for Cloud Apps

#### <a name="new-activity"></a>新しいアクティビティ

攻撃者は、新しいエンティティを作成して、その到達範囲を広げるか、マルウェア エージェントをインストールするか、検出を回避しています。

アクティビティ     |シグナル ソース           |代替セキュリティ ポータル
|:---                |:---                        |:---
インストールされている新しいアプリ |アプリ ガバナンス アドオンを使用した Defender for Cloud Apps |Defender for Cloud Apps
新しいユーザー アカウント    |Azure Identity Protection         |Defender for Cloud Apps
ロールの変更      |Azure Identity Protection        |Defender for Cloud Apps

#### <a name="suspicious-behavior"></a>挙動不審

攻撃者は機密情報をダウンロードしたり、ファイルを暗号化したり、組織の資産を収集したり、損害を与えたりしています。

動作       |シグナル ソース
|:---                  |:---
マルウェアが複数のデバイスに拡散する |Defender for Endpoint
リソース スキャン     |Defender for Endpoint、Defender for Identity
メールボックス転送ルールの変更 |Defender for Office 365
データ流出と暗号化 |Defender for Office 365

**セキュリティを無効にする Adversary の監視** - これは多くの場合、人間が操作するランサムウェア (HumOR) 攻撃チェーンの一部であるため

* **イベント ログクリア** – 特にセキュリティ イベント ログと PowerShell 操作ログ
* **セキュリティ ツール/コントロールの無効化** (一部のグループに関連付けられている)

## <a name="detect-ransomware-attacks-with-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでランサムウェア攻撃を検出する

Microsoft 365 Defender ポータルでは、検出、影響を受けた資産、実行された自動アクション、および関連する証拠の組み合わせに関する情報を一元的に表示できます。

* インシデント キュー。攻撃に関連するアラートをグループ化して、完全な攻撃範囲、影響を受けた資産、自動修復アクションを提供します。
* Microsoft 365 Defenderによって追跡されているすべてのアラートを一覧表示するアラート キュー。

### <a name="incident-and-alert-sources"></a>インシデントとアラートのソース

Microsoft 365 Defender ポータルは、次のシグナルを一元化します。

* Microsoft Defender for Endpoint
* Microsoft Defender for Office 365
* Microsoft Defender for Identity
* Microsoft Defender for Cloud Apps (アプリ ガバナンス アドオンを含む)
* Microsoft Azure AD Identity Protection
* Microsoft Defender for IoT

次の表に、一般的な攻撃と、Microsoft 365 Defenderに対応するシグナル ソースを示します。

攻撃とインシデント           |シグナル ソース
|:---                         |:---
クラウド ID: パスワード スプレー、多数の失敗した試行、短時間で複数のデバイスへのログオンの試行、複数の初回ログオン、最近アクティブなユーザー アカウント |Azure AD Identity Protection
オンプレミス ID (AD DS) の侵害       |Defender for Identity
フィッシング詐欺              |Defender for Office 365
悪意のあるアプリ             |Defender for Cloud Apps または Defender for Cloud Apps with app Governance アドオン
エンドポイント (デバイス) の侵害         |Defender for Endpoint
IoT 対応デバイスの侵害          |Defender for IoT

### <a name="filtering-ransomware-identified-incidents"></a>ランサムウェアで識別されたインシデントをフィルター処理する

ランサムウェアとしてMicrosoft 365 Defender別に分類されたインシデントについては、インシデント キューを簡単にフィルター処理できます。

1. Microsoft 365 Defender ポータルのナビゲーション ウィンドウで、[インシデント **とアラート] > [インシデント**] を選択してインシデント キューに移動します。
2. [ **フィルター] を選択します**。
3. [ **カテゴリ]** で [ **ランサムウェア**] を選択し、[ **適用**] を選択し、[ **フィルター** ] ウィンドウを閉じます。

インシデント キューの各フィルター設定では、後でリンクとして保存してアクセスできる URL が作成されます。 これらの URL は、ブックマークしたり、保存したり、必要に応じて 1 回のクリックで使用したりできます。 たとえば、次のブックマークを作成できます。

* "ランサムウェア" カテゴリを含むインシデント。 対応する [リンク](https://security.microsoft.com/incidents?filters=AlertStatus%3DNew%257CInProgress,category%3Dransomware&page_size=30&fields=expand,name,tags,severity,investigationStates,category,impactedEntities,alertCount,serviceSource,detectionSource,firstEventTime,lastEventTime,sensitivity,status,incidentAssignment,classification,determination,rbacGroup)を次に示します。
* ランサムウェア攻撃が実行されていることがわかっている、指定された **アクター** 名を持つインシデント。
* ランサムウェア攻撃で使用することが知られている、指定 **された関連付けられた脅威** 名を持つインシデント。
* 大規模で協調的なランサムウェア攻撃の一部であることが知られているインシデントに対して SecOps チームが使用するカスタム タグを含むインシデント。

### <a name="filtering-ransomware-identified-threat-analytics-reports"></a>ランサムウェアで識別された脅威分析レポートのフィルター処理

インシデント キュー内のインシデントをフィルター処理する場合と同様に、ランサムウェアを含むレポートの脅威分析レポートをフィルター処理できます。

1. ナビゲーション ウィンドウで、[ **脅威分析**] を選択します。
2. [ **フィルター] を選択します**。
3. [ **脅威タグ**] で [ **ランサムウェア**] を選択し、[ **適用**] を選択して、[ **フィルター** ] ウィンドウを閉じます。

このリンクをクリックすることもできます。

多くの脅威分析レポートの **[検出の詳細** ] セクションから、脅威用に作成されたアラート名の一覧を確認できます。

### <a name="microsoft-365-defender-apis"></a>Microsoft 365 Defender API

また、Microsoft 365 Defender API を使用して、テナント内のMicrosoft 365 Defenderインシデントとアラート データに対するクエリを実行することもできます。 カスタム アプリは、データをフィルター処理し、カスタム設定に基づいてフィルター処理した後、アラートやインシデントへのリンクのフィルターリストを提供できます。このリストを使用すると、そのアラートまたはインシデントに簡単に移動できます。 [Microsoft 365 Defender |のインシデント API を一覧表示するMicrosoft Docs](/api-list-incidents.md)。SIEM と Microsoft Defender を統合することもできます。「[SIEM ツールと Microsoft 365 Defenderを統合する](/configure-siem-defender.md)」を参照してください。

### <a name="microsoft-365-defender-sentinel-integration"></a>Microsoft 365 Defender Sentinel 統合

Microsoft Sentinel のMicrosoft 365 Defenderインシデント統合を使用すると、すべてのMicrosoft 365 Defenderインシデントを Microsoft Sentinel にストリーミングし、両方のポータル間で同期することができます。 インシデントには、関連するすべてのアラート、エンティティ、関連情報が含まれます。 Sentinel に入ると、インシデントはMicrosoft 365 Defenderと双方向に同期され続け、インシデント調査で両方のポータルの利点を利用できます。 [Microsoft Sentinel との統合Microsoft 365 Defender](/azure/sentinel/microsoft-365-defender-sentinel-integration)参照してください。

### <a name="proactive-scanning-with-advanced-hunting"></a>高度なハンティングを使用したプロアクティブ スキャン

[高度な捜索](/advanced-hunting-overview.md) は、ネットワーク内のイベントを探索して検査し、脅威のインジケーターとエンティティを特定できる、クエリベースの脅威検出ツールです。 この柔軟でカスタマイズ可能な分析ツールにより、既知の脅威と潜在的な脅威の両方について制約のない捜索が可能になります。 Microsoft 365 Defenderでは、カスタム クエリを使用して[カスタム検出ルール](/custom-detections-overview.md)を作成することもできます。これにより、クエリに基づいてアラートを作成し、自動的に実行するようにスケジュールできます。

ランサムウェア アクティビティを事前にスキャンするには、ID、エンドポイント、アプリ、データに対して一般的に使用されるランサムウェア攻撃方法に対する高度なハンティング クエリのカタログを組み立てる必要があります。 すぐに使用できる高度なハンティング クエリの主なソースを次に示します。

* [ランサムウェアのハントに関する](/advanced-hunting-find-ransomware.md)記事
* 高度なハンティング クエリ用の GitHub リポジトリ:
  * [ランサムウェア固有の](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware) クエリ
  * [クエリのすべてのカテゴリ](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware)
* 脅威分析レポート
  * ランサムウェアの高度なハンティング セクション [: 広範かつ継続的な脅威](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/analystreport) アナリスト レポート
  * その他のアナリスト レポートの高度なハンティング セクション

### <a name="automated-hunting"></a>自動ハンティング

高度なハンティング クエリを使用して、ランサムウェア攻撃方法の既知の要素 (通常とは異なる PowerShell コマンドの使用など) に基づいてカスタム検出ルールとアクションを作成することもできます。 カスタム検出ルールは、セキュリティ アナリストが見て対処できるアラートを作成します。

カスタム検出ルールを作成するには、高度なハンティング クエリのページから [ **カスタム検出** ルールの作成] を選択します。 作成したら、次の項目を指定できます。

* カスタム検出ルールを実行する頻度
* ルールによって作成されたアラートの重大度
* 作成されたアラートの MITRE 攻撃フェーズ
* 影響を受けたエンティティ
* 影響を受けるエンティティに対して実行するアクション

## <a name="prepare-your-secops-team-for-focused-ransomware-detection"></a>集中ランサムウェア検出のために SecOps チームを準備する

プロアクティブなランサムウェア検出のために SecOps チームを準備するには、次のものが必要です。

* SecOps チームと組織の事前作業
* 必要に応じて、セキュリティ アナリストトレーニング
* セキュリティ アナリストの最新の攻撃と検出エクスペリエンスを組み込む継続的な運用作業

### <a name="pre-work-for-your-secops-team-and-organization"></a>SecOps チームと組織の事前作業

SecOps チームと組織が集中ランサムウェア攻撃防止の準備を整えるには、次の手順を検討してください。

1. [ランサムウェアや強要から迅速に保護](/security/compass/protect-against-ransomware-phase3)するガイダンスを使用して、ランサムウェアの防止のために IT インフラストラクチャとクラウド インフラストラクチャを構成します。 このガイダンスのフェーズとタスクは、次の手順と並行して実行できます。
2. Defender for Endpoint、Defender for Office 365、Defender for Identity、Defender for Cloud Apps、アプリ ガバナンス アドオン、Defender for IoT、Azure AD Identity Protection サービスの適切なライセンスを取得します。
3. 既知のランサムウェア攻撃方法または攻撃フェーズに合わせて調整された高度なハンティング クエリのカタログを組み立てます。
4. スケジュール、アラートの名前付け、自動アクションなど、既知のランサムウェア攻撃方法のアラートを作成する特定の高度なハンティング クエリのカスタム検出ルールのセットを作成します。
5. [カスタム タグ](/manage-incidents.md)または標準のセットを決定して、より大規模で調整されたランサムウェア攻撃の一部であることが知られているインシデントを識別する新しいタグまたは標準を作成します。
6. ランサムウェアインシデントとアラート管理の一連の運用タスクを決定します。 以下に例を示します。

* 階層 1 アナリストが受信インシデントとアラートをスキャンし、調査のために階層 2 アナリストに割り当てるためのプロセス。
* 高度なハンティング クエリとそのスケジュール (毎日、毎週、毎月) を手動で実行します。
* ランサムウェア攻撃の調査と軽減のエクスペリエンスに基づく継続的な変更。

### <a name="security-analyst-training"></a>セキュリティ アナリスト トレーニング

必要に応じて、セキュリティ アナリストに以下の内部トレーニングを提供できます。

* 一般的なランサムウェア攻撃チェーン (MITRE 攻撃戦術と一般的な脅威手法とマルウェア)
* インシデントとアラート、およびMicrosoft 365 Defender ポータルで次を使用してインシデントとアラートを見つけて分析する方法:
  * Microsoft 365 Defenderによって既に作成されたアラートとインシデント
  * Microsoft 365 Defender ポータルの事前スキャンされた URL ベースのフィルター
  * インシデント API を使用してプログラムで実行する
* 使用する高度なハンティング クエリとその手動スケジュール (毎日、毎週、毎月)
* 使用するカスタム検出ルールとその設定
* カスタム インシデント タグ
* Microsoft 365 Defender ポータルのランサムウェア攻撃に関する最新の[脅威分析レポート](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag)

### <a name="ongoing-work-based-on-operational-learning-and-new-threats"></a>運用学習と新しい脅威に基づく継続的な作業

SecOps チームの継続的なツールとプロセスのベスト プラクティスとセキュリティ アナリストのエクスペリエンスの一環として、次のことを行う必要があります。

* 高度なハンティング クエリのカタログを次の方法で更新します。
  * Microsoft 365 Defender ポータルまたは [Advanced Hunting GitHub リポジトリ](<https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware>)の最新の脅威分析レポートに基づく新しいクエリ。
  * 脅威の識別またはアラートの品質を向上させるために最適化するために、既存のものを変更します。
* 新しい、または変更された高度なハンティング クエリに基づいてカスタム検出ルールを更新します。
* ランサムウェア検出の一連の運用タスクを更新します。
