---
title: Enterprise ビジネス継続性管理計画に関する考慮事項
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: クラウド対応のビジネス継続性計画を立てる際の考慮事項。
ms.openlocfilehash: f8518a96461d33093b9d736f890f6166dc6b3c97
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601094"
---
# <a name="developing-your-continuity-plan"></a>継続性計画を立てる

このトピックでは、Microsoft 365 の依存関係を考慮に入れたビジネス継続性計画の策定に関するガイダンスを提供します。 ここでは、事業上の機能を分析し、Microsoft 365 サービスに依存する機能を特定するための方法を提案します。 この分析は、サービスに不具合が発生することを想定し、その可能性に備えるために行うものです。

大まかには、ビジネス継続性計画の策定には、評価、計画、機能の検証、および通信と調整という 4 つの側面があります。

## <a name="assessment"></a>評価
まずは、組織の事業上の機能およびそれらをサポートしているサービスとプロセスを特定する必要があります。 これには、事業影響分析の実施が含まれます。この分析では、各事業機能をそれぞれの重要度に応じてランク付けし、各機能が依存しているプロセスとサービスを特定します。 評価を開始する際に参考になるサンプルの表を下に示します。

**サンプル事業影響分析 (BIA)**

これは `name of the service, system, process, or function` に関する BIA ドキュメントです。 

|BIA フィールド|説明|
|---------|---------|
|BIA の種類|`is it a business process or technology, service or system?`|
|BIA 名|`name of the service/system/function/process`|
|サービスの説明|`give a full description of the service, process, or function`|
|事業機能|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|会計年度|`the current fiscal year, re-evaluate these on a regular basis`|
|重要度|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|部署|`name of the business unit that owns this business function`|
|プロセス (サービス、機能)|`the name of the process, service, or feature`|
|業務グループの担当上司|`the name and contact information of the senior leader of the business group that owns this business process`|
|このテクノロジには、確立された**内部** SLA または OLA はありますか?|`please explain in as much detail as possible`|
|このテクノロジには、確立された**外部** SLA または OLA はありますか?|`please explain in as much detail as possible`|
|このテクノロジには、特定のプロセス SLA を牽引する既知の取締役命令はありますか? 「はい」の場合は、詳細を説明します。|`details here`|
|このサービスに関連するデータの破損または侵害が発生した場合、重大な事故を誘発しますか? 「はい」の場合は、詳細を説明します。|`details here`|
|このサービスには、主要機能の一部またはすべての代わりとなる回避策や代替方法が用意されていますか? 「はい」の場合は、詳細を説明します。|`details here`|
|サービスは、個人を特定できる情報 (PII) などの顧客データを処理、保存、または送信しますか? 「はい」の場合は、詳細を説明します。|`details here`|
|BIA の状態|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|完了日|`the date this BIA was completed`|
|BIA ファシリテータ|`name of the person or group who is responsible for developing and maintaining this BIA`|
|BIA 承認|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|共同作成者|`optional list of the people who helped develop this BIA and their contact information`|
|BIA 承認の保管場所|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>計画

次に、ビジネス プロセス全体を調べ、何らかの連鎖的依存関係が存在する箇所を特定します。 その結果に応じて復旧計画の優先順位付けと策定を行い、それらの計画を支援する標準業務手順書を作成します。

[Microsoft Service Map](https://docs.microsoft.com/azure/azure-monitor/insights/service-map) を使用すると、このマッピング作業に役立ちます。 Microsoft Service Map では、Windows および Linux システムのアプリケーション コンポーネントが自動的に検出され、すべての TCP 依存関係がマッピングされ、アプリが依存する接続およびリモートのサード パーティ システムが特定されます。 また、ネットワーク内の、これまでは依存関係のマッピングがされてこなかった場所 (Active Directory など) に対する依存関係もマッピングされます。

土台として使用できる依存関係解析 (DA) のサンプルを下に示します。 依存関係解析 (DA) では、プロセスの依存関係を特定し、確認します。 従業員、サプライヤー、顧客、パートナーシップ、施設を必ず含めます。 この分析のデータは、プロセスの回復要件とそれをサポートする依存関係の回復機能との間の隔たりを特定するために使用されます。


|フィールド|説明|
|---------|---------|
|プロセスの種類|         |
|ファシリテータ|         |
|分析担当者|         |
|完了日|         |
|共同作成者|         |
  
## <a name="capability-validation"></a>機能の検証

ビジネス プロセスのインベントリを作成し、他のプロセスやテクノロジとの関係のマッピングを行ったら、すべてのプロセスについて検証シナリオを作成する必要があります。 ビジネス プロセスの継続性計画を検証する方法を見つけることが中心になります。 おそらく、プロセスにより重要度が異なることが判明します。そのため、プロセスの優先順位付けを行う必要があります。
計画の策定後は、インシデント対応および持続性対策に関して定期的に従業員のトレーニングを行うことが重要である点を忘れないでください。 各検証またはテストから得た内容を取り込んで復旧計画を強化するために、インシデント後のレビューを活用する必要があります。

## <a name="incident-coordination-and-communication"></a>インシデントの調整と通信

サービス インシデントの発生時は、通常の通信チャネルが影響を受けたり機能が低下したりする場合があります。そのため、インシデント発生時も組織内の連絡を維持できるように、代替方法を事前に準備する必要があります。 通信チャネルを確立し、セキュリティとコンプライアンスに関する検証を行い、実際に中断が発生する前に使用方法に関するトレーニングをチャネルの使用者に提供することが重要です。 危機の発生中に場当たり的な、未経験の解決方法をユーザーが模索することに比べ、既知の状態に問題があった場合は別の既知の状態に移行する方法の方がはるかに望ましいからです。

Microsoft では、各サービス チームで代替の内部通信チャネルが確立されており、通常の通信チャネルを利用できない場合でも調整作業を行えるようにしています。 これらのチャネルには、バックアップ テレフォニーおよび電話会議ソリューション、Yammer グループ、Teams グループ、内部サービス正常性ダッシュボード、および内部インシデント管理ソフトウェアが含まれます。

事業影響分析と依存関係分析を行う際は、重要プロセスおよびそれらが依存しているテクノロジやサービスをマッピングします。 計画のこのフェーズ内でのコミュニケーションには特に注意を向け、代替方法を検討するようにします。 以下にいくつかの例を示します。

- ユーザーや関係者への情報伝達方法として主に電子メールを使用している場合にメール サービスの機能が低下したり使用不能になったりした場合、バックアップとして Microsoft Teams や Yammer などの他のサービスまたは他のサード パーティ製サービスを使用できます。 重要な点は、これらを事前に確立し、どこにアクセスすればよいかについてユーザーのトレーニングを行うことです。 Yammer のスレッドがあったとしても、その存在を誰も知らず、誰もそのブックマークを残しておいていない場合は、役に立ちません。  
- 内部インシデント管理プロセスでの応答の調整が音声通信に依存している場合、危機が発生した際に使用する代替のテレフォニー ソリューションを確立します。 このソリューションはメインのサービスと完全に同等である必要はありませんが、ビジネス継続性およびインシデント管理チームの調整のための最小限の共同作業環境を提供する必要があります。 また、ユーザーに各自の携帯電話番号をグローバル アドレス一覧で公開することを依頼することで、極端なケースが発生した場合の代替コミュニケーションの選択肢を広げられます。
- インシデント発生時に状況の更新を提供できるよう、カスタムのサービス正常性ダッシュボードまたはそれに似た他のサイトを作成することを推奨します。 ユーザーに対して情報の入手場所に関するトレーニングを事前に行うことで、ヘルプ デスクへの不必要な呼び出しを減らし、ユーザーに自信を植え付けることができます。これにより、状況への対処が迅速かつ効率的になります。 O365 サービス通信 API を使用してこれを M365 に結びつけると、可視性がさらに高まります。  
- ビジネス継続性計画および標準業務手順書の保管場所が広く認知されていることが重要です。 SharePoint Online または OneDrive for Business でローカル デバイスへの自動同期を構成するなどして、重要ドキュメントのコピーをオンラインとオフラインの両方で維持することをお勧めします。 復旧のために絶対不可欠なサービス オペレーション センターまたはネットワーク オペレーション センターおよび他の同様のチームの場合、緊急事態の発生時に使用できるようにハードコピーを維持することをお勧めします。

## <a name="know-your-external-points-of-integration"></a>外部との統合点を把握する

ビジネス モデルに関わらず、どの会社にも顧客、パートナー、ベンダーとの統合点があります。 ビジネス バリュー サプライ チェーンは、外部エンティティとの統合の上に構築されています。 サービス中断発生時のビジネス継続性を強化するには、各統合点の考察と保護を行う必要があります。  
サプライ チェーンを分析する際は、内部通信を分析するのと同じ方法で外部通信を評価する必要があります。 顧客は、お客様の組織への唯一の連絡方法として Exchange Online サーバーに依存していますか? 稼働時間が影響を受けている際に使用する代替通信方法を確立し、そのことをサプライヤーに通知しましたか? 次のサンプルの表では、考慮点を整理する方法を提案しています。

|外部エンティティ名|影響を受けるインシデント シナリオ|統合されている Microsoft 365 サービス|代替方法|
|---------|---------|---------|---------|
|`vendor name`|メール フロー|Exchange Online は、Contoso と通信する唯一の方法です。|外部の Microsoft Teams チャネルまたはサード パーティ製の共同作業ソフトウェアを設定します。          |
|`service supplier name`|チャット|Microsoft Teams|サード パーティ製インスタント メッセージング|
|`partner name`|音声|Microsoft Teams|携帯電話または公衆 PSTN (公衆交換電話網)      |
|`supplier name`|ファイル共有|外部共有されている SharePoint サイトと OneDrive|サード パーティ製ファイル共有         |
