---
title: Microsoft 365 Defender の新機能
description: Microsoft 365 Defenderの新機能を一覧表示します
keywords: Microsoft 365 Defender、ga、一般公開、機能、利用可能、新規の新機能
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 07/27/2022
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d7a49b76efb824160157b9bf10315562149edb02
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405622"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender の新機能

Microsoft 365 Defenderの新機能を一覧表示します。 

RSS フィード: ご自身のフィード リーダーに次の URL をコピーして貼り付けると、このページの更新時に通知を受け取ることができます。

```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

他の Microsoft Defender セキュリティ製品の新機能の詳細については、次を参照してください。

- [Microsoft Defender for Office 365 の新機能](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Microsoft Defender for Endpoint の新機能](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Microsoft Defender for Identityの新機能](/defender-for-identity/whats-new)
- [Microsoft Defender for Cloud Appsの新機能](/cloud-app-security/release-notes)

メッセージ [センター](https://admin.microsoft.com/Adminportal/Home#/MessageCenter)を通じて、製品の更新と重要な通知を受け取ることもできます。

## <a name="august-2022"></a>2022 年 8 月
- (GA) [ハンティング用の Microsoft Defender エキスパート](defender-experts-for-hunting.md) が一般公開されるようになりました。 堅牢なセキュリティ運用センターを持つMicrosoft 365 Defenderのお客様で、Microsoft Defender データを使用してエンドポイント、Office 365、クラウド アプリケーション、ID 全体で脅威を積極的に検出できるように Microsoft に支援を求める場合は、サービスの適用、設定、および使用の詳細を確認してください。 Defender Experts for Hunting は、他のMicrosoft 365 Defender製品とは別に販売されています。
- (プレビュー) [ガイド付きモード](advanced-hunting-modes.md#get-started-with-guided-hunting-mode) は、高度な捜索でパブリック プレビューで使用できるようになりました。 アナリストは、Kusto 照会言語 *(KQL) を知らなくても*、エンドポイント、ID、電子メール &コラボレーション、クラウド アプリのデータに対するデータベースのクエリを開始できるようになりました。  ガイド モードには、使用可能なフィルターと条件を含むドロップダウン メニューを使用してクエリを作成する、使いやすい文書パーツ スタイルが用意されています。 [クエリ ビルダーの概要に](advanced-hunting-query-builder.md)関する説明を参照してください。

## <a name="july-2022"></a>2022 年 7 月
- (プレビュー)Microsoft Defender Experts for Hunting パブリック プレビュー参加者は、Microsoft 365 Defender製品によって生成されたアラートと共に、ハンティング サービスが環境内で発生した脅威を理解するのに役立つ月次レポートの受信を楽しみにしています。 詳細については、「[Microsoft 365 Defenderの Defender Experts for Hunting レポートについて](defender-experts-report.md)」を参照してください。

## <a name="june-2022"></a>2022 年 6 月
- (プレビュー) [DeviceTvmInfoGathering](advanced-hunting-devicetvminfogathering-table.md) テーブルと [DeviceTvmInfoGatheringKB](advanced-hunting-devicetvminfogatheringkb-table.md) テーブルが、高度なハンティング スキーマで使用できるようになりました。 これらのテーブルを使用して、さまざまな構成の状態やデバイスの攻撃領域の状態など、Defender 脆弱性管理の評価イベントを確認します。

- Microsoft 365 Defender ポータルで新しく導入された自動調査&応答カードには、保留中の修復アクションの概要が示されています。
セキュリティ運用チームは、承認待ちのすべてのアクションと、カード自体でこれらのアクションを承認するための規定された時間を表示できます。 セキュリティ チームは、アクション センターにすばやく移動し、適切な修復アクションを実行できます。 自動調査&応答カードには、[フル オートメーション] ページへのリンクもあります。 これにより、セキュリティ運用チームはアラートを効果的に管理し、タイムリーに修復アクションを完了できます。


## <a name="may-2022"></a>2022 年 5 月
- (プレビュー)Microsoft [Security Experts](https://aka.ms/MicrosoftSecurityExperts) という新しいサービス カテゴリへの最近発表された拡張に合わせて、Microsoft [Defender Experts for Hunting (Defender Experts for Hunting](defenderexpertsforhuntingprev.md) ) のパブリック プレビューの可用性について紹介します。 Defender Experts for Hunting は、堅牢なセキュリティ運用センターを持ち、エンドポイント、Office 365、クラウド アプリケーション、ID など、Microsoft Defender データ全体の脅威を積極的に検出できるように Microsoft に支援を求めるお客様を対象としています。 

## <a name="april-2022"></a>2022 年 4 月
- (プレビュー)これで、検索クエリの結果から直接電子メール メッセージに [対してアクション](advanced-hunting-take-action.md) を実行できるようになりました。 電子メールは、他のフォルダーに移動したり、完全に削除したりできます。 
- (プレビュー)高度な捜索の新しい[`UrlClickEvents`表](advanced-hunting-urlclickevents-table.md)は、メール メッセージ、Microsoft Teams、Office 365 アプリのセーフ リンククリックからの情報に基づいて、フィッシング キャンペーンや不審なリンクなどの脅威を検出するために使用できます。

## <a name="march-2022"></a>2022 年 3 月

- (プレビュー)インシデント キューは、調査に役立ついくつかの機能で強化されています。 機能強化には、ID または名前でインシデントを検索する機能、カスタム時間範囲を指定する機能などがあります。


## <a name="december-2021"></a>2021 年 12 月

- (GA)このテーブルは `DeviceTvmSoftwareEvidenceBeta` 、特定のソフトウェアがデバイス上で検出された場所の証拠を表示できるように、高度な捜索で短期的に追加されました。

## <a name="november-2021"></a>2021 年 11 月

- (プレビュー)Defender for Cloud Apps のアプリケーション ガバナンス アドオン機能は、Microsoft 365 Defenderで利用できるようになりました。 アプリ ガバナンスは、Microsoft Graph API を使用して Microsoft 365 データにアクセスする OAuth 対応アプリ向けに設計されたセキュリティとポリシー管理機能を提供します。 アプリ ガバナンスは、実用的な分析情報と自動化されたポリシー アラートおよびアクションを通して、これらのアプリとそのユーザーが Microsoft 365 に保存されている機密データにアクセスし、使用し、共有する方法について、完全な可視性、修復、およびガバナンスを提供します。 [アプリケーション ガバナンスの詳細については、こちらを参照してください](/cloud-app-security/app-governance-manage-app-governance)。
- (プレビュー) [高度なハンティング](advanced-hunting-overview.md) ページでは、マルチタブのサポート、スマート スクロール、合理化されたスキーマ タブ、クエリのクイック編集オプション、クエリ リソースの使用状況インジケーターなどの機能強化が行われ、クエリのスムーズで微調整が容易になりました。
- (プレビュー) [これで、インシデントへのリンク機能を](advanced-hunting-link-to-incident.md) 使用して、高度な捜索クエリの結果から、調査中の新規または既存のインシデントにイベントまたはレコードを直接含めることができます。

## <a name="october-2021"></a>2021 年 10 月

- (GA)高度な捜索では、 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) テーブルに追加された列が増えました。 これで、クエリを含`AccountType``IPCategory``IsExternalUser``IsImpersonated``IPTags``UserAgentTags`めることができます。

## <a name="september-2021"></a>2021 年 9 月

- (GA)Microsoft Defender for Office 365イベント データは、Microsoft 365 Defender イベント ストリーミング API で使用できます。 [ストリーミング API のサポートされているMicrosoft 365 Defenderイベントの種類で、イベントの種類の](supported-event-types.md)可用性と状態を確認できます。
- (GA)高度な捜索で使用できるMicrosoft Defender for Office 365データが一般公開されるようになりました。
- (GA)ユーザー アカウントにインシデントとアラートを割り当てる

  インシデントとそれに関連付けられているすべてのアラートを、インシデントの **[インシデントの管理**] ウィンドウまたはアラートの [アラートの **管理**] ウィンドウの [**割り当て元]** からユーザー アカウントに割り当てることができます。

## <a name="august-2021"></a>2021 年 8 月

- (プレビュー)高度な捜索で使用できるデータをMicrosoft Defender for Office 365する

  電子メール テーブルの新しい列を使用すると、高度な捜索を使用して詳細な調査を行うために、電子メール ベースの脅威に関するより多くの分析情報を提供できます。 [EmailEvents](./advanced-hunting-emailevents-table.md)、[EmailAttachmentInfo](./advanced-hunting-emailattachmentinfo-table.md)、`FileSize`および `ThreatTypes` `DetectionMethods` [EmailPostDeliveryEvents](./advanced-hunting-emailpostdeliveryevents-table.md) テーブルに列を含`AuthenticationDetails`めるようになりました。

- (プレビュー)インシデント グラフ

  インシデントの **[概要**] タブの新しい **[グラフ**] タブには、攻撃の完全な範囲、時間の経過と共にネットワーク経由で攻撃がどのように拡散したか、開始した場所、攻撃者がどれだけ離れたかを示します。

## <a name="july-2021"></a>2021 年 7 月

- [プロフェッショナル サービス カタログ](https://sip.security.microsoft.com/interoperability/professional_services)

  サポートされているパートナー接続を使用して、プラットフォームの検出、調査、脅威インテリジェンス機能を強化します。

## <a name="june-2021"></a>2021 年 6 月

- (プレビュー) [脅威タグごとのレポートを表示する](threat-analytics.md#view-reports-per-threat-tags)

  脅威タグは、特定の脅威カテゴリに焦点を当て、最も関連性の高いレポートを確認するのに役立ちます。

- (プレビュー) [ストリーミング API](../defender-endpoint/raw-data-export.md)

  Microsoft 365 Defenderでは、Advanced Hunting を通じて使用可能なすべてのイベントを Event Hubs または Azure ストレージ アカウントにストリーミングできます。

- (プレビュー) [高度な捜索でアクションを実行する](advanced-hunting-take-action.md)

  [高度な捜索](advanced-hunting-overview.md)で見つけた脅威を迅速に含めたり、侵害された資産に対処したりできます。

- (プレビュー) [ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)

  高度なハンティング スキーマ テーブルに関する情報をセキュリティ センターで直接取得します。 この参照には、テーブルと列の説明に加えて、サポートされているイベントの種類 (`ActionType` 値) とサンプル クエリが含まれます。

- (プレビュー) [DeviceFromIP() 関数](advanced-hunting-devicefromip-function.md)

  特定の時間範囲で特定の IP アドレスまたはアドレスが割り当てられているデバイスに関する情報を取得します。

## <a name="may-2021"></a>2021 年 5 月

- [Microsoft 365 Defender ポータルの新しいアラート ページ](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243)

  攻撃に対するコンテキストの強化された情報を提供します。 現在のアラートと、攻撃に関連するすべての影響を受けるエンティティとアクティビティ (ファイル、ユーザー、メールボックスなど) の原因となった他のトリガーされたアラートを確認できます。 詳細については、「 [アラートの調査](/microsoft-365/security/defender/investigate-alerts) 」を参照してください。

- [Microsoft 365 Defender ポータルでのインシデントとアラートの傾向グラフ](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425)

  1 つのインシデントに対して複数のアラートがあるか、組織が複数の異なるインシデントで攻撃を受けているかどうかを判断します。 詳細については、「 [インシデントの優先順位付け](/microsoft-365/security/defender/incident-queue) 」を参照してください。

## <a name="april-2021"></a>2021 年 4 月

- Microsoft 365 Defender

  改善された[Microsoft 365 Defender](https://security.microsoft.com)ポータルが利用可能になりました。 この新しいエクスペリエンスにより、Defender for Endpoint、Defender for Office 365、Defender for Identity などが 1 つのポータルにまとめられます。 これは、セキュリティ制御を管理するための新しいホームです。 [新機能について説明します](microsoft-365-defender-portal.md)。

- [Microsoft 365 Defender脅威分析レポート](threat-analytics.md)

  脅威分析は、アクティブな攻撃の影響に対応し、最小限に抑えるのに役立ちます。 また、Microsoft 365 Defender ソリューションによってブロックされた攻撃の試行について学習し、さらなる暴露のリスクを軽減し、回復性を高める予防的なアクションを実行することもできます。 統合セキュリティ エクスペリエンスの一環として、Microsoft Defender for Endpointおよび Microsoft Defender for Office E5 ライセンス所有者向けに脅威分析を利用できるようになりました。

## <a name="march-2021"></a>2021 年 3 月

- [CloudAppEvents テーブル](advanced-hunting-cloudappevents-table.md)

  Microsoft Cloud App Securityの対象となるさまざまなクラウド アプリとサービスのイベントに関する情報を確認します。 この表には、以前にテーブルで `AppFileEvents` 使用できる情報も含まれています。

