---
title: 顧客およびクラウド パートナー エンタープライズ ビジネス継続性の責任
author: chrfox
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
description: サービス インシデントの発生時に Microsoft が何を行っているかを理解し、ビジネス継続性プランをより適切に準備できるようにします。
ms.openlocfilehash: 9bbf73c736a4391a51edd451db7d23869aa36603
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122347"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>エンタープライズ ビジネス継続性管理の顧客とクラウド パートナーの責任

ユーザーに Microsoft 365 クラウド サービスを提供することは、組織と Microsoft とのパートナーシップです。 Microsoft はサービスを提供します。顧客は、クライアント エンドポイントの接続、ID とアクセスの管理、およびそれらのサービスの使用方法について責任を負います。 ID やディレクトリ インフラストラクチャなどの責任も共有されます。 この記事では、サービス インシデントが発生した場合にビジネスを機能させるために注意する必要のある重要な項目をいくつか取り上げ、Microsoft がサービス インシデントの発生時に何をするかに関する期待を設定するのに役立ちます。

## <a name="transparency-during-service-incidents"></a>サービス インシデントの発生時の透明性

信頼できるパートナーとして、Microsoft は復元力の高いクラウド サービスを構築し、構造化された手順に従ってサービス インシデントを解決します。 サービス インシデントが発生したときには、**タイムリー**で**対象範囲の限定された****高可用性**の通信が、顧客にとって不可欠であることを Microsoft は認識しています。

## <a name="timely"></a>タイムリー
Microsoft は、Microsoft 365 管理ポータルでテナント固有のサービス正常性ダッシュボード (SHD) を更新することで、Microsoft 365 管理者への通知を実施します。 サービス インシデントの更新は通常、1 時間ごとに提供されます。 また、別の時間設定が必要な場合は、SHD 通信投稿の変更をお知らせします。

## <a name="targeted"></a>対象範囲の限定
ほとんどの場合、監視システムが問題を検出すると、影響を受けた顧客ベースを 1 つの顧客から地域またはそれ以上まで特定し、必要な通信をそれらの顧客に送信できます。 これにより、ビジネスに必要な情報を把握でき、影響のないノイズ通知に煩わされることはありません。 たとえば、特定のメールボックス データベースが影響を受ける場合、影響を受けるインフラストラクチャにユーザーがいるかどうかを正確に特定し、そのユーザーとの通信範囲を設定できます。 インシデントの影響範囲が明確でない場合、影響を受ける可能性のある最も幅広い顧客グループに通信を拡大します。

## <a name="highly-avaliable"></a>高可用性
Microsoft は、顧客が使用できるサービス状態通信用の複数のチャネルを維持しています。

- 管理センターまたは管理センター内のサービス正常性ダッシュボードが使用できない場合、[バックアップ サイト](https://status.office365.com/)を使用してサービス状態を監視できます。
- Twitter アカウント [@MSFT365Status](https://twitter.com/msft365status?lang=en) を維持し、SHD の影響に関する報告と投稿の更新に対応します。
- Microsoft 365 テナント管理者向けの管理アプリには、外出先で組織の Microsoft 365 サービスの状態に接続する機能が設けられています。 テナントの管理者は、モバイル デバイスにサービス正常性の情報とメンテナンス状態の更新情報を表示できます。 詳細については、「[管理アプリ FAQ](https://docs.microsoft.com/ja-JP/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide)」を参照してください。
- [Microsoft 365 サービス通信 API](https://docs.microsoft.com/ja-JP/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api) を使用すると、サービス通信にアクセスできるため、環境をより簡単に監視できます。 API に接続し、リアルタイムのサービス正常性データを受信し、内部ダッシュボードで情報を公開して、エンタープライズ ユーザーにインシデントを通知できます。 内部に情報を配信すると、停止中のヘルプデスクのトラフィックを減らすことができます。
- 重大なインシデントについては、Microsoft は管理センター内の SHD にインシデントの事後レビュー (PIR) を公開します。 PIR には、停止の性質を理解できる重要なインシデント情報が含まれています。 通常、次のセクションが含まれます。
    - ユーザーへの影響
    - 影響の範囲
    - インシデントの開始終了日時
    - 根本原因
    - 実行された処理
    - 次の手順
- Microsoft 365 メッセージ センターでは、今後の変更、新機能、計画的なメンテナンスの通知などの補助的な通信を利用できます。
- 詳細については、「[サービス正常性と継続性ガイド](https://docs.microsoft.com/ja-JP/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)」を参照し、さまざまな通信チャネルとサービス正常性を監視する方法の詳細について確認してください。
 
Microsoft 365 オンライン サービスへのアクセスを提供することは、組織と Microsoft とのパートナーシップです。 次の図は、サービス インシデントの発生時および通常の運用時の Microsoft と顧客の両方の責任のバランスについてまとめたものです。

![顧客と Microsoft の責任のバランス](media\ebcm\responsibilities.png)

## <a name="your-environment---service-continuity"></a>環境 - サービス継続性
継続計画について考えるときは、組織に影響を与える可能性のあるイベントと、全体的な通信の能力に注意してください。 高レベルでは、ビジネスに影響を与える可能性のある 3 つの要因があります。

### <a name="people"></a>複数のユーザー
自然災害やパンデミックなど、従業員に影響を与えるイベントを検討します。 これは見過ごされがちです。従業員が広範囲に分散している場合、大規模な影響が生じる可能性が低いためです。 しかし、多くの従業員がオフラインだった場合、ビジネスは継続しますか? どのようにそれを軽減しますか?

### <a name="location"></a>場所
多くの組織では、エンタープライズ システムとクラウド サービスに接続するために、従業員が特定の物理的またはネットワークの場所にいる必要があります。  
Microsoft は、クラウド リソースへのネットワーク接続を設定するためのベスト プラクティスを企業に説明する「[ネットワーク接続の原則](https://docs.microsoft.com/ja-JP/office365/enterprise/office-365-network-connectivity-principles)」を公開しています。 最適化の例には、スプリット トンネル VPN の実装が含まれ、VPN トンネル経由ではなくユーザーのネットワークから直接接続できるようになります。  これらの接続の原則は、接続の遅延を低く維持するために重要ですが、サービスの復元力には、一般的なコラボレーションのために企業リソースに接続する代替方法が必要です。

### <a name="systems"></a>システム
多くのコラボレーション ソリューションは、企業のワイド エリア ネットワーク (WAN) などのシステムに依存しています。 これらのシステムが利用できない場合、組織はどのように対応しますか?
この図は、複数の領域に影響を与える可能性のある問題を表しています。 添付の表は、考慮すべき例を示す

![ベン図](media\ebcm\venn-diagram.png)

継続計画では、これらの各領域を考慮する必要があります。 例: ユーザーを企業ネットワークに接続する必要があり、吹雪の場合、それらのユーザーはどのようにして主要なリソースにアクセスできますか? 雪がオフィスへの移動を妨げ、サービス エンジニアが企業ネットワークに接続する必要がある場合、自宅に会社のノートパソコンを持ち込むことを義務付けるポリシーがありますか?
