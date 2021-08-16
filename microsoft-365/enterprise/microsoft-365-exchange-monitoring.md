---
title: Microsoft 365 の Exchange Online の監視
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Exchange Online の監視を使用して、Microsoft 365 でのメールのインシデントや勧告の情報について確認します。
ms.openlocfilehash: 0b6eaf85c1f5f8c892bc382cb7656dac6bbbb550
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58355990"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>Microsoft 365 の Exchange Online の監視

Microsoft 365 管理センターで Exchange Online の監視を使用して、組織の Microsoft 365 サブスクリプションの Exchange サービスの正常性を監視できます。 Exchange Online の監視は、以下のカテゴリに収集されたインシデントと勧告についての情報を提供します。

- **インフラストラクチャ**: 定期的な更新を提供し、問題を解決するために Microsoft が所有する Microsoft 365 のインフラストラクチャで問題が検出されます。 たとえば、Exchange または他の Microsoft 365 のクラウド インフラストラクチャの問題のため、ユーザーが Exchange Online にアクセスできない場合などです。
- **サードパーティのインフラストラクチャ**: 組織が依存関係にあるサードパーティのインフラストラクチャで問題が検出され、解決するには所属の組織によるアクションが必要です。 たとえば、ユーザー認証のトランザクションが、ユーザーが Exchange Online にアクセスできないようにするサードパーティのセキュリティ トークン サービス (STS) プロバイダーによって調整される場合などです。
- **顧客のインフラストラクチャ**: 組織のインフラストラクチャで問題が検出され、解決するには所属の組織によるアクションが必要です。 たとえば、組織によってホストされている STS プロバイダーから承認トークンを取得できないため、ユーザーが Exchange Online にアクセスできない場合などです。

以下は、Microsoft 365 管理センターの **[サービス正常性]** ページの例です。これは、**[正常性] > [サービス正常性]** から利用できます。

![Microsoft 365 管理センターの [サービス正常性] ページ](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

**[状態]** 列の値は、サービスが正常な状態にあるか、Microsoft が維持するクラウド サービスに基づいて勧告やインシデントがあるかどうかを示します。 

**[組織とサード パーティの問題]** 列の値は、組織のインフラストラクチャまたはサードパーティ製のソフトウェアが、Exchange Online のユーザーのサービス正常性のエクスペリエンスに影響を与えるかどうかを示します。 勧告やインシデントを解決するには、*ユーザー* のアクションが必要です。

以下は、Microsoft 365 管理センターの **Exchange Online** の監視ページです。これは、**[正常性] > [サービス正常性] > [Exchange Online]** から利用できます。

![Microsoft 365 管理センターの Exchange Online の監視ページ](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

**Exchange Online** の監視ページで、Exchange Online サービスが正常な状態かどうか、関連するインシデントや勧告がないかどうかを確認できます。 Exchange Online の監視で、特定のメールのシナリオにおけるサービス正常性を確認し、リアルタイムに近い信号を表示してシナリオごとに影響を特定できます。 

## <a name="requirements"></a>要件

このプレビューは、次の要件を満たしているお客様に対して有効になっています。 

- 組織に Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 の製品のいずれか 1 つまたは組み合わせから 5,000 個以上のライセンス数が必要です。 

  たとえば、組織は Office 365 E3 のライセンスを 3,000 個と Microsoft 365 E5 のライセンスを 2,500 個持つことで、条件を満たす製品から合計 5,500 個のライセンスを持つことができます。

- 組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。

Exchange Online の監視で、次のメール クライアントの正常性をメールの読み取りアクティビティに基づいて表示できます。

- Outlook デスクトップ
- Outlook on the Web
- iOS と Android のネイティブのメール クライアント 
- iOS と Android の Outlook モバイル アプリ 
- Outlook Mac クライアント

これらのクライアントについては、メールを読んでいるユーザーに基づいて過去 30 分間のアクティブ ユーザー数を表示すると共に、ダッシュボードのインシデントと勧告の数も表示できます。 問題がないか確認するため、このデータは前週と同じ間隔と比較されます。 

>[!Note]
> アクティブ ユーザー数は、ユーザーがメールを読むときなど、1 つのアクティビティによって測定されます。 過去 30 分間のアクティビティだけを把握しています。
>

また、次のシナリオでも Exchange Online の正常性を監視することができます。

- **メール フロー**: メッセージが Microsoft 365 ネットワークに配信された後に直ちに受信トレイに送信されたメッセージの数。 
- **基本認証と先進認証**: Exchange Online サービスで正常に検証されたユーザー数。

![メール配信における Exchange の正常性を監視する例](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

これらすべてのシナリオにおいて、鍵となる数字はメイン ダッシュボードでの過去 30 分間のものです。 これらの各シナリオの詳細表示には、7 日間のほぼリアルタイムの傾向が、前週との比較された 30 分間の集計関数と共に表示されます。 

## <a name="send-us-feedback"></a>フィードバックを送信する

フィードバックは 2 つの方法でお寄せいただけます。

- Microsoft 365 管理センターのすべてのページに表示されている **[フィードバックの送信]** オプションを使用します。
- 特定のインシデントや勧告の場合、**[この投稿は役に立ちましたか?]** のリンクを使用してフィードバックを送信します。

![特定のインシデントや勧告の場合に使用する [この投稿は役に立ちましたか?] リンク](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a>1. Microsoft 365 管理センターの [正常性] で [Exchange Online の監視] が表示されないのはなぜですか? 

まず、Microsoft 365 管理センターの **[ホーム]** ページで新しい管理センターが有効になっていることを確認してください。 

次に、次の両方の要件を満たしていることを確認してください。 

- 組織に Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 の製品のいずれか 1 つまたは組み合わせから 5,000 個以上のライセンス数が必要です。 
- 組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。

組織のライセンス数が 5,000 ユーザー未満であり、月間アクティブ ユーザー数が 50 未満である場合、この要件が満たされるまで Exchange Online の監視は有効になりません。

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>2. 各クライアントのダッシュボードのアクティブ ユーザー数が少なく表示されます。 しかし、多くの有効なライセンスがユーザーにアサインされています。 これはどういうことですか? 

監視に表示されるアクティブ ユーザー数は、機能が呼び出したアクティビティをユーザーが実行した 30 分間のウィンドウに基づいています。 これは、使用数とは異なることに注意してください。 使用数を表示するには、Microsoft 365 管理センターでアクティビティ レポートを使用してください (**[レポート] > [使用状況]**)。

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a>3. Teams や SharePoint などの他のサービスに対する他の監視シナリオは追加されますか? 

Microsoft は、このエクスペリエンスを Microsoft 365 管理センターのサービス正常性ダッシュボード内に直接統合しています。 これにより、Microsoft は監視シナリオを他のサービスにも拡張できるようになります。お知らせするニュースがある場合は発表されます。 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a>4. このエクスペリエンスの一般提供予定について教えてください。 

Microsoft は、Exchange Online の監視を Microsoft 365 管理センターの **[サービス正常性]** ダッシュボードに直接統合しました。 

新しくなった統合エクスペリエンスにより、Microsoft はユーザーからのフィードバックを収集し、一般提供の計画を定義する予定です。

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a>5. この機能は無料 (ライセンス付属) と有料 (追加コンテンツ) のどちらですか? 

この機能はパブリック プレビューの段階にあり、質問 1 での要件を満たしたユーザーのみ利用できます。

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a>6. フィードバックを送信するにはどうすればいいですか? 

一般的なフィードバックについては、**Exchange Online** の監視ページの右下隅にある **[フィードバックの送信]** アイコンを使用してください。 

インシデントや勧告のフィードバックについては、**[この投稿は役に立ちましたか?]** リンクを使用します。

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>7. アクティビティの傾向を示すシナリオのインストルメント化されたデータはどこにありますか?

データは Exchange Online サービスにインストルメント化されています。要求が Exchange Online に到達する前に障害が発生するか、Exchange Online に障害がある場合、アクティビティ信号の降下が確認できます。
