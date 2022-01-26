---
title: Microsoft 365 Defender の新機能
description: 新しい機能の一覧を表示Microsoft 365 Defender
keywords: 新しい機能、Microsoft 365 Defender、一般提供、機能、利用可能、新しい
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ce81edf38eed82deec6e112070b7137fca21dc03
ms.sourcegitcommit: f3c912780bbcf5a5b47de192202adb3afbd5952b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2022
ms.locfileid: "62218899"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。

次の機能は、プレビュー版または一般公開 (GA) の最新リリースMicrosoft 365 Defender。

RSS フィード: ご自身のフィード リーダーに次の URL をコピーして貼り付けると、このページの更新時に通知を受け取ることができます。

```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

他の Microsoft Defender セキュリティ製品の新機能の詳細については、以下を参照してください。

- [Microsoft Defender for Office 365 の新機能](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Microsoft Defender for Endpoint の新機能](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Microsoft Defender for Identity の新機能](/defender-for-identity/whats-new)
- [新しい機能Microsoft Cloud App Security](/cloud-app-security/release-notes)

また、メッセージ センターから製品の更新や重要な通知を [取得することもできます](https://admin.microsoft.com/Adminportal/Home#/MessageCenter)。 

## <a name="december-2021"></a>2021 年 12 月

- (GA)このテーブルは、高度な検索で短期的に追加され、デバイスで特定のソフトウェアが検出された場所の証拠 `DeviceTvmSoftwareEvidenceBeta` を確認できます。

## <a name="november-2021"></a>2021 年 11 月

- (プレビュー)Defender for Cloud Apps のアプリケーション ガバナンス アドオン機能が、Microsoft 365 Defender で利用Microsoft 365 Defender。 アプリ ガバナンスは、Microsoft のセキュリティ API を介してデータにアクセスする OAuth が有効なアプリ用に設計Microsoft 365ポリシー管理機能Graph提供します。 アプリ ガバナンスは、実用的な分析情報と自動化されたポリシー アラートおよびアクションを通して、これらのアプリとそのユーザーが Microsoft 365 に保存されている機密データにアクセスし、使用し、共有する方法について、完全な可視性、修復、およびガバナンスを提供します。 [アプリケーション ガバナンスの詳細を参照してください](/cloud-app-security/app-governance-manage-app-governance)。
- (プレビュー)高度 [な](advanced-hunting-overview.md) 検索ページには、複数タブのサポート、スマート スクロール、合理化されたスキーマ タブ、クエリのクイック編集オプション、クエリ リソースの使用状況インジケーター、その他の機能強化が追加され、クエリの円滑化と微調整が容易になりました。
- (プレビュー)インシデント機能へのリンクを[](advanced-hunting-link-to-incident.md)使用して、高度な検索クエリ結果のイベントまたはレコードを、調査中の新規または既存のインシデントに含めることができます。

## <a name="october-2021"></a>2021 年 10 月

- (GA)高度な検索では [、CloudAppEvents](advanced-hunting-cloudappevents-table.md) テーブルにさらに列が追加されました。 これで、クエリ `AccountType` に `IsExternalUser` `IsImpersonated` 、、、、、 `IPTags` `IPCategory` `UserAgentTags` を含めできます。

## <a name="september-2021"></a>2021 年 9 月

- (GA)Microsoft Defender for Office 365イベント データは、イベント ストリーミング API Microsoft 365 Defender使用できます。 イベントの種類の可用性と状態は、ストリーミング API のサポートされるイベントMicrosoft 365 Defender[で確認できます](supported-event-types.md)。
- (GA)高度なOffice 365利用可能なデータの Microsoft Defender が一般提供されています。
- (GA)インシデントとアラートをユーザー アカウントに割り当てる

  インシデントに関連付けられているすべてのアラートを、インシデントの [インシデントの管理] ウィンドウまたはアラートの [管理] アラート ウィンドウの[割り当て] からユーザー アカウントに割り当てできます。 

## <a name="august-2021"></a>2021 年 8 月

- (プレビュー)Microsoft Defender for Office 365高度な検索で利用可能なデータ

  電子メール テーブルの新しい列は、高度な検索を使用してより詳細な調査を行う電子メール ベースの脅威に関するより多くの洞察を提供できます。 この列は `AuthenticationDetails` [、EmailEvents、EmailAttachmentInfo、](./advanced-hunting-emailevents-table.md) `FileSize` [および](./advanced-hunting-emailattachmentinfo-table.md) `ThreatTypes` `DetectionMethods` [EmailPostDeliveryEvents テーブルに含](./advanced-hunting-emailpostdeliveryevents-table.md) める必要があります。

- (プレビュー)インシデント グラフ

  **インシデントの [Graph]** タブの新しい [セキュリティ] タブには、攻撃の全範囲、攻撃がネットワーク経由で時間の間にどのように広がったか、開始した場所、攻撃者がどこまで攻撃を行ったかが表示されます。

## <a name="july-2021"></a>2021 年 7 月

- [Professional サービス カタログ](https://sip.security.microsoft.com/interoperability/professional_services)

  サポートされているパートナー接続を使用して、プラットフォームの検出、調査、および脅威インテリジェンス機能を強化します。

## <a name="june-2021"></a>2021 年 6 月

- (プレビュー) [脅威タグごとにレポートを表示する](threat-analytics.md#view-reports-per-threat-tags)

  脅威タグは、特定の脅威カテゴリに集中し、最も関連性の高いレポートを確認するのに役立ちます。

- (プレビュー) [ストリーミング API](../defender-endpoint/raw-data-export.md)

  Microsoft 365 Defenderは、高度なハンティングを通じて利用可能なすべてのイベントをイベント ハブや Azure ストレージ アカウントにストリーミングできます。

- (プレビュー) [高度な検索でアクションを実行する](advanced-hunting-take-action.md)

  高度な狩猟で見つけた脅威を迅速に含むか、侵害された資産 [に対処します](advanced-hunting-overview.md)。

- (プレビュー) [ポータル内スキーマ参照](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)

  セキュリティ センターで高度な検索スキーマ テーブルに関する情報を直接取得します。 テーブルと列の説明に加えて、この参照には、サポートされているイベントの種類 ( `ActionType` 値) とサンプル クエリが含まれます。

- (プレビュー) [DeviceFromIP() 関数](advanced-hunting-devicefromip-function.md)

  特定の時間範囲で特定の IP アドレスまたはアドレスが割り当てられているデバイスに関する情報を取得します。

## <a name="may-2021"></a>2021 年 5 月

- [新しいアラート ページ (Microsoft 365 Defender ポータル)](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243)

  攻撃にコンテキストの拡張情報を提供します。 現在のアラートを引き起こした他のトリガーされたアラート、およびファイル、ユーザー、メールボックスなど、攻撃に関連する影響を受けるすべてのエンティティとアクティビティを確認できます。 詳細については [、「アラートの](/microsoft-365/security/defender/investigate-alerts) 調査」を参照してください。

- [ポータル内のインシデントとアラートのMicrosoft 365 Defenderグラフ](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425)

  1 つのインシデントに対して複数のアラートが発生するか、組織が複数の異なるインシデントで攻撃を受け取っているかどうかを判断します。 詳細については [、「インシデントの優先順位付](/microsoft-365/security/defender/incident-queue) け」を参照してください。

## <a name="april-2021"></a>2021 年 4 月

- Microsoft 365 Defender

  改善[されたMicrosoft 365 Defenderポータル](https://security.microsoft.com)が利用可能になります。 この新しいエクスペリエンスでは、Defender for Endpoint、Defender for endpoint、defender for Office 365 Id、その他を 1 つのポータルにまとめます。 これは、セキュリティコントロールを管理するための新しいホームです。 [新機能について説明します](./microsoft-365-defender.md#the-microsoft-365-defender-portal)。

- [Microsoft 365 Defender分析レポート](threat-analytics.md)

  脅威分析は、アクティブな攻撃に対応し、影響を最小限に抑えるのに役立ちます。 また、セキュリティ ソリューションによってブロックされる攻撃の試みMicrosoft 365 Defender、さらなる暴露のリスクを軽減し、回復性を高める予防措置を講じてください。 統合セキュリティ エクスペリエンスの一環として、Microsoft Defender for Endpoint および Microsoft Defender では、E5 ライセンス所有者向Office利用できます。

## <a name="march-2021"></a>2021 年 3 月

- [CloudAppEvents テーブル](advanced-hunting-cloudappevents-table.md)

  さまざまなクラウド アプリとサービスのイベントに関する情報を、Microsoft Cloud App Security。 この表には、以前に表で使用できる情報も含 `AppFileEvents` まれています。

## <a name="february-2021"></a>2021 年 2 月

- (プレビュー)拡張された[Microsoft 365 Defenderポータル ( https://security.microsoft.com) ](https://security.microsoft.com)がパブリック プレビューで利用可能になります。 この新しいエクスペリエンスにより、Defender for Endpoint と Defender for Office 365が中央に表示されます。 [変更点についての詳細情報](microsoft-365-defender.md#the-microsoft-365-defender-portal) はこちらを参照してください。

- **[(プレビュー) Microsoft 365 Defender](api-overview.md)** API - トップ レベルの Microsoft 365 Defender API を使用すると、共有インシデントテーブルと高度なハンティング テーブルに基づいてワークフローを自動化できます。
