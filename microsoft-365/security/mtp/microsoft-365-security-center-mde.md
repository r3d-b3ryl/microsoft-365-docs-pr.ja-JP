---
title: Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint
description: Microsoft Defender セキュリティ センターから Microsoft 365 セキュリティ センターへの変更点について説明します。
keywords: Microsoft 365 セキュリティ センター、OATP、MDATP、MDO、MDE、単一ウィンドウ のガラス、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: e33a38ae1b5b6bd341d8a274b56c0da44ec1017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910896"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Office 365](../office-365-security/office-365-atp.md)

強化された [Microsoft 365](overview-security-center.md) セキュリティ センターは、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能を組み合 [https://security.microsoft.com](https://security.microsoft.com) わせたもの。 このセキュリティ センターは、Microsoft Defender セキュリティ センターやコンプライアンス センターの Office 365 セキュリティ &など、既存の Microsoft セキュリティ ポータルの機能を統合します。

Microsoft Defender セキュリティ センターについて理解している場合、この記事では、強化された Microsoft 365 セキュリティ センターの変更点と改善点の一部について説明します。 ただし、注意が必要な新しい要素と更新された要素があります。

これまで [、Microsoft Defender セキュリティ センターは](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) Microsoft Defender for Endpoint のホームでした。 エンタープライズ セキュリティ チームは、高度な永続的な脅威アクティビティやデータ侵害の可能性に関するアラートの監視と対応に使用しています。 ポータルの数を減らすのに役立つ Microsoft 365 セキュリティ センターは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。

Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は[、Microsoft Defender](mssp-access.md)セキュリティ センターでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセス許可をサポートしています。


> [!IMPORTANT]
> Microsoft 365 セキュリティ センターに表示される内容は、現在のサブスクリプションによって異なります。 たとえば、Microsoft Defender for Office 365 のライセンスをお持ちではない場合、[メール & コラボレーション] セクションは表示されません。

>[!Note]
>新しい統合ポータルは、次の場合は使用できません。
>- 米国政府機関コミュニティ クラウド (GCC)
>- US Government Community Cloud High (GCC High)
>- 米国国防総省
>- 商用ライセンスを持つすべての米国政府機関

改善された Microsoft 365 セキュリティ センターを見 [https://security.microsoft.com](https://security.microsoft.com) てみろ。

メリットの詳細: Microsoft [365](overview-security-center.md)セキュリティ センターの概要

## <a name="whats-changed"></a>変更内容

次の表は、Microsoft Defender セキュリティ センターと Microsoft 365 セキュリティ センターの間の変更点の簡単な参照です。

### <a name="alerts-and-actions"></a>アラートとアクション

|**領域**  |**変更の説明**  |
|---------|---------|
| [インシデント&アラート](incidents-overview.md)  | Microsoft 365 セキュリティ センターでは、すべてのエンドポイント、電子メール、および ID でインシデントとアラートを管理できます。 関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスを統合しました。 詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。   |
| [検索](advanced-hunting-overview.md)  |  Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含め、自動的に Microsoft 365 Defender に移動します。 対応するアラートは Microsoft 365 Defender にも表示されます。 これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)。 <br><br>高度 `DeviceAlertEvents` な検索の表は、Microsoft 365 Defender では使用できません。 Microsoft 365 Defender でデバイス固有のアラート情報を照会するには、テーブルとテーブルを使用して、さまざまなソース セットからのさらに多くの情報に `AlertInfo` `AlertEvidence` 対応できます。 [DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)なしで書き込みクエリを実行して、次のデバイス関連のクエリを作成します。|
|[アクション センター](mtp-action-center.md)    | 自動調査と修復アクションに続いて実行された保留中のアクションと完了したアクションを一覧表示します。 以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行される修復アクションの保留中および完了したアクションが一覧表示され、自動調査ではアラートと状態が一覧表示されました。 強化された Microsoft 365 セキュリティ センターでは、アクション センターでは、電子メール、デバイス、およびユーザー間の修復アクションと調査を 1 つの場所にまとめます。  |
| [脅威の分析](threat-analytics.md) |  ナビゲーション バーの上部に移動し、検出と使用を容易にします。 エンドポイントと電子メールとコラボレーションの両方に関する脅威情報が含まれる。    |

### <a name="endpoints"></a>エンドポイント

|**領域**  |**変更の説明**  |
|---------|---------|
|検索   |  見出しの代わりに、Microsoft Defender for Endpoint 検索バーが [エンドポイント] セクションの下を移動しています。 引き続きデバイス、ファイル、ユーザー、URL、IPs、脆弱性、ソフトウェア、推奨事項を検索できます。  |
|[ダッシュボード](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  これは、セキュリティ操作ダッシュボードです。 アクティブなアラートがトリガーされた数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、およびユーザーの重大度レベルの概要を参照してください。 また、センサーの問題が発生したデバイス、サービス全体の正常性、未解決のアラートが検出された方法も確認できます。 |
|デバイス一覧 | 変更はありません。 |
|[脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    ナビゲーション ウィンドウに収まる名前が短縮されました。 脅威と脆弱性の管理セクションと同じで、すべてのページが下に表示されます。     |
| パートナーと API | 変更はありません。 |
| 評価&チュートリアル    |     新しいテストと学習機能。     |
| 構成管理環境   |  変更はありません。  |

> [!NOTE]
> **自動調査と修復** は、インシデントの一部です。 [インシデントの調査] タブには、[自動調査と修復イベント> **確認** できます。

### <a name="access-and-reporting"></a>アクセスとレポート

|**領域**  |**変更の説明**  |
|---------|---------|
| レポート  | 脅威の保護、デバイスの正常性とコンプライアンス、脆弱な&など、エンドポイントと電子メール のコラボレーションに関するレポートを参照してください。 |
| 正常性  |  現在、Microsoft 365 管理センターの [サービス正常性] [ページにリンクしています](https://admin.microsoft.com/)。 |
| 設定 |  Microsoft 365 セキュリティ センター、Microsoft 365 Defender、Endpoints、Email &コラボレーション、ID、デバイス検出の設定を管理します。   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365 のセキュリティ ナビゲーションと機能

左側のナビゲーション、またはクイック起動バーは見慣れたものに見えます。 ただし、このセキュリティ センターには、いくつかの新しい要素と更新された要素があります。

### <a name="incidents-and-alerts"></a>インシデントとアラート

電子メール、デバイス、および ID 間でインシデントとアラートの管理をまとめます。 アラート ページは、攻撃信号を組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。 新しい統合エクスペリエンスにより、ワークロード全体で一貫したアラートの表示が実現されました。 すばやくトリアージ、調査、効果的なアクションを実行できます。

- [インシデントの詳細](incidents-overview.md)
- [アラートの管理の詳細](investigate-alerts.md)

![[アラートとアクション] クイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>検索

高度なハンティング クエリを使用して、エンドポイント全体の脅威、マルウェア、悪意のあるアクティビティ、Office 365 メールボックスなど、積極的に [検索します](advanced-hunting-overview.md)。 これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方について脅威インジケーターとエンティティを見つけて確認できます。

[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤った構成済みデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。


### <a name="action-center"></a>アクション センター

アクション センターには、自動調査と対応機能によって作成された調査が表示されます。 Microsoft 365 Defender のこの自動自己修復は、セキュリティ チームが特定のイベントに自動的に応答することで役立ちます。

[アクション センターの詳細](mtp-action-center.md)

### <a name="threat-analytics"></a>Threat Analytics

Microsoft の専門家のセキュリティ研究者から脅威インテリジェンスを取得します。 Threat Analytics は、新たな脅威に直面する際にセキュリティ チームの効率を向上するのに役立ちます。 Threat Analytics には、次の機能が含まれます。

- Microsoft Defender からの電子メール関連の検出と軽減策 (Office 365) これは、Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えてです。
- インシデント ビューは、脅威に関連します。
- レポート内のアクション可能な情報をすばやく識別して使用するための拡張エクスペリエンス。

脅威分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーから、または組織の上位の脅威を示す専用のダッシュボード カードからアクセスできます。

脅威分析を使用して新たな脅威を追跡して対応する [方法の詳細](./threat-analytics.md)

### <a name="endpoints-section"></a>[エンドポイント] セクション

組織のエンドポイントのセキュリティを表示および管理します。 Microsoft Defender セキュリティ センターを使用している場合は、よく知られているものに見えます。

![Endpoints のクイック 起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>アクセスとレポート

レポートの表示、設定の変更、ユーザー ロールの変更を行います。

![[アクセスとレポート] クイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API 接続

Defender for [Endpoint SIEM API を使用する場合](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)は、引き続き実行できます。 Microsoft 365 セキュリティ ポータルのアラート ページまたはインシデント ページをポイントする新しいリンクが API ペイロードに追加されました。 新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。 詳細については、「アカウントを Microsoft Defender for Endpoint から [Microsoft 365 セキュリティ センターにリダイレクトする」を参照してください](./microsoft-365-security-mde-redirection.md)。

### <a name="email-alerts"></a>電子メール通知

Defender for Endpoint の電子メール 通知は引き続き使用できます。 Microsoft 365 セキュリティ センターのアラート ページまたはインシデント ページを指す新しいリンクがメールに追加されました。 詳細については、「アカウントを Microsoft Defender for Endpoint から [Microsoft 365 セキュリティ センターにリダイレクトする」を参照してください](./microsoft-365-security-mde-redirection.md)。

## <a name="related-information"></a>関連情報

- [Microsoft 365 セキュリティ センター](overview-security-center.md)
- [Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする](microsoft-365-security-mde-redirection.md)