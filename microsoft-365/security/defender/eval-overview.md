---
title: XDR ソリューションであるMicrosoft 365 Defenderの評価とパイロット
description: XDR セキュリティとは Microsoft 365 Defenderで Microsoft XDR を評価するにはどうすればよいですか? このブログ シリーズを使用して、デバイス、ID、データ、およびアプリケーションを保護するように設計されたセキュリティ ソリューションをテストおよびパイロットするためのMicrosoft 365 Defender試用版ラボまたはパイロット環境を計画します。 ここで XDR のサイバー セキュリティ体験を開始し、そのテストを運用環境に移行します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 06/25/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f7830bb25f2572c43d665d059e0a36bc1fdaa172
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500785"
---
# <a name="evaluate-and-pilot-microsoft-365-defender"></a>Microsoft 365 Defender の評価とパイロット

**適用対象:**

- Microsoft 365 Defender

## <a name="how-this-article-series-works"></a>この記事シリーズのしくみ

この一連の記事は、試用版 XDR 環境をエンドツーエンドで設定するプロセス全体 *を* ステップ実行するように設計されているため、Microsoft 365 Defenderの機能と機能を評価し、準備ができたら評価環境を運用環境に直接昇格することもできます。

XDR について初めて考える場合は、これらの 7 つのリンクされた記事をスキャンして、ソリューションの包括的さを感じ取ることができます。

- [環境を作成する方法](eval-create-eval-environment.md)
- この Microsoft XDR の各テクノロジを設定または学習する
  - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
  - [Microsoft Defender for Office](eval-defender-office-365-overview.md)
  - [Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)
  - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [この XDR を使用して調査して応答する方法](eval-defender-investigate-respond.md)
- [試用版環境を運用環境に昇格させる](eval-defender-promote-to-production.md)

## <a name="microsoft-365-defender-is-a-microsoft-xdr-cyber-security-solution"></a>Microsoft 365 Defenderは Microsoft XDR サイバー セキュリティ ソリューションです

Microsoft 365 Defenderは、*エンドポイント、電子メール、アプリケーション、ID* など、Microsoft 365環境 *全体* のシグナル、脅威、アラート データを自動的に収集、関連付け、分析する **eXtended 検出と応答 (XDR) ソリューション** です。 人工知能 (AI) と自動化を利用して、攻撃を *自動的に* 停止し、影響を受ける資産を安全な状態に修復します。

XDR は、セキュリティの次のステップと考え、エンドポイント (エンドポイントでの検出と対応またはEDR)、電子メール、アプリ、ID セキュリティを 1 か所で統合します。

## <a name="microsoft-recommendations-for-evaluating-microsoft-365-defender"></a>Microsoft 365 Defenderを評価するための Microsoft の推奨事項

Microsoft では、Office 365の既存の運用サブスクリプションで評価を作成することをお勧めします。 これにより、すぐに実際の分析情報を取得し、環境内の現在の脅威に対して動作するように設定を調整できます。 経験を積み、プラットフォームに慣れた後は、各コンポーネントを一度に 1 つずつ運用環境に昇格するだけです。

## <a name="the-anatomy-of-a-cyber-security-attack"></a>サイバー セキュリティ攻撃の構造

Microsoft 365 Defenderは、クラウドベース、統合、侵害前、侵害後のエンタープライズ防御スイートです。 エンドポイント、ID、アプリ、電子メール、コラボレーション アプリケーション、およびすべてのデータにわたる *防止*、 *検出*、 *調査*、 *および対応* を調整します。

この図では、攻撃が進行中です。 フィッシングメールは、組織内の従業員の受信トレイに届きます。メールの添付ファイルを知らずに開きます。 これによりマルウェアがインストールされ、機密データの盗難で終わる可能性のある一連のイベントが発生します。 ただし、この場合、Defender for Office 365が動作しています。

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="さまざまな攻撃の試行" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

この図について:

- **Microsoft Defender for Office 365** の一部であるExchange Online Protectionは、フィッシングメールを検出し、メール フロー ルールを使用して受信トレイに届かないことを確認できます。
- **安全** な添付ファイルDefender for Office 365添付ファイルをテストし、有害であると判断します。そのため、到着したメールはユーザーが操作できないか、ポリシーによってメールがまったく届かないようにします。
- **Defender for Endpoint は** 、企業ネットワークに接続するデバイスを管理し、悪用される可能性があるデバイスとネットワークの脆弱性を検出します。
- **Defender for Identity** では、特権エスカレーションや危険度の高い横移動などの突然のアカウント変更をメモします。 また、セキュリティ チームによる修正のために、制約のない Kerberos 委任などの簡単に悪用された ID の問題についても報告します。
- **Microsoft Defender for Cloud Apps** は、不可能な移動、資格情報アクセス、異常なダウンロード、ファイル共有、メール転送アクティビティなどの異常な動作に気付き、これらをセキュリティ チームに報告します。

### <a name="microsoft-365-defender-components-secure-devices-identity-data-and-applications"></a>Microsoft 365 Defender コンポーネントは、デバイス、ID、データ、およびアプリケーションをセキュリティで保護します

Microsoft 365 Defenderは、これらのセキュリティ テクノロジで構成され、連携して動作します。 XDR とMicrosoft 365 Defenderの機能の恩恵を受けるために、これらのコンポーネントをすべて必要とすることはありません。 1 つまたは 2 つを使用することで、利益と効率を実現できます。

|コンポーネント|説明|参考資料|
|---|---|---|
|Microsoft Defender for Identity|Microsoft Defender for Identityでは、Active Directory シグナルを使用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダー アクションを特定、検出、調査します。|[Microsoft Defender for Identity とは?](/defender-for-identity/what-is)|
|Exchange Online Protection|Exchange Online Protectionは、スパムやマルウェアから組織を保護するのに役立つネイティブクラウドベースの SMTP リレーとフィルター処理サービスです。|[Exchange Online Protection (EOP) の概要 - Office 365](../office-365-security/overview.md)|
|Microsoft Defender for Office 365|Microsoft Defender for Office 365は、電子メール メッセージ、リンク (URL)、コラボレーション ツールによってもたらされる悪意のある脅威から組織を保護します。|[Microsoft Defender for Office 365 - Office 365](../office-365-security/overview.md)|
|Microsoft Defender for Endpoint|Microsoft Defender for Endpointは、デバイス保護、違反後の検出、自動調査、推奨される対応のための統合プラットフォームです。|[Microsoft Defender for Endpoint - Windows セキュリティ](../defender-endpoint/microsoft-defender-endpoint.md)|
|Microsoft Defender for Cloud Apps|Microsoft Defender for Cloud Appsは包括的なクロス SaaS ソリューションであり、クラウド アプリに対する可視性、強力なデータ制御、強化された脅威保護を実現します。|[Defender for Cloud Apps とは](/cloud-app-security/what-is-cloud-app-security)|
|Azure AD Identity Protection|Azure AD Identity Protection は、数十億回のサインイン試行のリスク データを評価し、このデータを使用して、環境への各サインインのリスクを評価します。 このデータは、条件付きアクセス ポリシーの構成方法に応じて、アカウントへのアクセスを許可または禁止するためにAzure ADによって使用されます。 Azure AD Identity Protection は、Microsoft 365 Defenderとは別にライセンスされています。 Azure Active Directory Premium P2に含まれています。|[Identity Protection とは](/azure/active-directory/identity-protection/overview-identity-protection)|
||||

## <a name="microsoft-365-defender-architecture"></a>Microsoft 365 Defender アーキテクチャ

次の図は、主要なMicrosoft 365 Defenderコンポーネントと統合のアーキテクチャの概要を示しています。 各 Defender コンポーネントの *詳細な* アーキテクチャとユース ケース シナリオについては、この一連の記事を通じて説明します。

:::image type="content" source="../../media/defender/m365-defender-eval-architecture.png" alt-text="Microsoft 365 Defender ポータルの高度なアーキテクチャ" lightbox="../../media/defender/m365-defender-eval-architecture.png":::

この図について:

- Microsoft 365 Defenderは、すべての Defender コンポーネントからの信号を結合して、ドメイン間で拡張検出と応答 (XDR) を提供します。 これには、統合インシデント キュー、攻撃を停止するための自動応答、自己復旧 (侵害されたデバイス、ユーザー ID、メールボックスの場合)、クロス脅威ハンティング、脅威分析が含まれます。
- Microsoft Defender for Office 365 は、電子メール メッセージ、リンク (URL) や共同作業ツールによって生じる悪意のある脅威から組織を保護します。 これらのアクティビティに起因するシグナルをMicrosoft 365 Defenderと共有します。 Exchange Online Protection (EOP) は、受信メールと添付ファイルのエンドツーエンド保護を提供するために統合されています。
- Microsoft Defender for Identityは、Active Directory フェデレーション サービス (AD FS) と オンプレミスの Active Directory Domain Services (AD DS) を実行しているサーバーからの信号を収集します。 これらのシグナルを使用して、侵害されたアカウントを使用してオンプレミス環境内のワークステーション間を横方向に移動するハッカーから保護するなど、ハイブリッド ID 環境を保護します。
- Microsoft Defender for Endpointは、組織で使用されるデバイスからシグナルを収集し、保護します。
- Microsoft Defender for Cloud Appsは、組織によるクラウド アプリの使用からのシグナルを収集し、承認されたクラウド アプリと承認されていないクラウド アプリの両方を含め、環境とこれらのアプリの間を流れるデータを保護します。
- Azure AD Identity Protection は、数十億回のサインイン試行のリスク データを評価し、このデータを使用して、環境への各サインインのリスクを評価します。 このデータは、条件付きアクセス ポリシーの構成方法に応じて、アカウントへのアクセスを許可または禁止するためにAzure ADによって使用されます。 Azure AD Identity Protection は、Microsoft 365 Defenderとは別にライセンスされています。 Azure Active Directory Premium P2に含まれています。

## <a name="microsoft-siem-and-soar-can-use-data-from-microsoft-365-defender"></a>Microsoft SIEM と SOAR は、Microsoft 365 Defenderからのデータを使用できます

この図に含まれていない追加の省略可能なアーキテクチャ コンポーネント:

- **すべてのMicrosoft 365 Defender コンポーネントからの詳細なシグナル データは、Microsoft Sentinel に統合し**、他のログ ソースと組み合わせて、SIEM と SOAR の完全な機能と分析情報を提供できます。
- Microsoft 365 Defenderを XDR として **使用する Azure SIEM Microsoft Sentinel の使用の詳細については、** この [概要記事](/azure/sentinel/microsoft-365-defender-sentinel-integration)と Microsoft Sentinel と Microsoft 365 Defender [統合の手順](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE)を参照してください。
- Microsoft Sentinel の SOAR (Microsoft Sentinel GitHub リポジトリのプレイブックへのリンクを含む) の詳細については、[この記事](/azure/sentinel/automate-responses-with-playbooks)を参照してください。

## <a name="the-evaluation-process-for-microsoft-365-defender-cyber-security"></a>Microsoft 365 Defenderサイバー セキュリティの評価プロセス

次に示す順序で、Microsoft 365のコンポーネントを有効にすることをお勧めします。

:::image type="content" source="../../media/defender/m365-defender-eval-process.png" alt-text="Microsoft 365 Defender ポータルでの高度な評価プロセス" lightbox="../../media/defender/m365-defender-eval-process.png":::

次の表では、この図について説明します。

|  シリアル番号   |手順  |説明  |
|------|---------|---------|
|1     | [評価環境を作成する](eval-create-eval-environment.md)       |この手順では、Microsoft 365 Defenderの試用版ライセンスを確実に取得できます。         |
|2     | [Defender for Identity を有効にする](eval-defender-identity-overview.md)        | アーキテクチャ要件を確認し、評価を有効にし、さまざまな攻撃の種類を特定して修復するためのチュートリアルについて説明します。   |
|3     | [Defender for Office 365を有効にする ](eval-defender-office-365-overview.md)       | アーキテクチャ要件を満たしていることを確認し、評価を有効にしてから、パイロット環境を作成します。 このコンポーネントにはExchange Online Protectionが含まれているため、ここで両方を実際 *に評価します*。      |
|4     | [Defender for Endpoint を有効にする ](eval-defender-endpoint-overview.md)       | アーキテクチャ要件を満たしていることを確認し、評価を有効にしてから、パイロット環境を作成します。         |
|5     | [Microsoft Defender for Cloud Appsを有効にする](eval-defender-mcas-overview.md)        |  アーキテクチャ要件を満たしていることを確認し、評価を有効にしてから、パイロット環境を作成します。        |
|6      | [脅威の調査と対応](eval-defender-investigate-respond.md)        |   攻撃をシミュレートし、インシデント対応機能の使用を開始します。      |
|7      | [試用版を製品版に昇格する](eval-defender-promote-to-production.md)        | Microsoft 365 コンポーネントを 1 つずつ運用環境に昇格させます。        |

これは、通常、機能のデプロイと構成に必要な労力に基づいて、機能の価値を迅速に活用するように設計された一般的に推奨される順序です。 たとえば、Defender for Office 365は、Defender for Endpoint にデバイスを登録するのに要する時間よりも短い時間で構成できます。 もちろん、ビジネス ニーズを満たすためにコンポーネントに優先順位を付ける必要があります。また、これらを別の順序で有効にすることもできます。

## <a name="go-to-the-next-step"></a>次の手順に進む

[Microsoft 365 Defender評価環境の詳細または作成](eval-create-eval-environment.md)
