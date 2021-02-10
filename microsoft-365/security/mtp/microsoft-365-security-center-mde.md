---
title: Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint
description: Microsoft Defender セキュリティ センターから Microsoft 365 セキュリティ センターへの変更点について説明します。
keywords: Microsoft 365 セキュリティ センター、OATP、MDATP、MDO、MDE、単一ウィンドウ、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
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
ms.openlocfilehash: 03b73901512522edec7fdbc579eaf4073eed5d48
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167465"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

強化された [Microsoft 365](overview-security-center.md) セキュリティ センターは、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能を組み合わせた [https://security.microsoft.com](https://security.microsoft.com) 機能です。 このセキュリティ センターには、Microsoft Defender セキュリティ センターや Office 365 セキュリティ センターコンプライアンス センターなど、既存の Microsoft セキュリティ ポータル&が組み込されています。

Microsoft Defender セキュリティ センターに慣れ親しんだ場合、この記事では、強化された Microsoft 365 セキュリティ センターの変更点と機能強化について説明します。 ただし、注意が必要な新しい要素と更新された要素があります。

従来 [、Microsoft Defender セキュリティ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) センターは、Microsoft Defender for Endpoint のホームでした。 エンタープライズ セキュリティ チームは、この機能を使用して、潜在的な持続的脅威アクティビティやデータ侵害のアラートを監視し、対応しています。 ポータルの数を減らすために、Microsoft 365 セキュリティ センターは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。

> [!IMPORTANT]
> Microsoft 365 セキュリティ センターに表示される内容は、現在のサブスクリプションによって異なります。 たとえば、microsoft Defender for Office 365 のライセンスを持ってない場合、[メールとコラボレーション&は表示されません。

改善された Microsoft 365 セキュリティ センターをご覧ください [https://security.microsoft.com](https://security.microsoft.com) 。

メリットの詳細については[、「Microsoft 365 セキュリティ センターの概要」を参照してください](overview-security-center.md)。

## <a name="whats-changed"></a>変更内容

次の表は、Microsoft Defender セキュリティ センターと Microsoft 365 セキュリティ センターの間の変更点のクイック リファレンスです。

### <a name="alerts-and-actions"></a>アラートとアクション

|**領域**  |**変更の説明**  |
|---------|---------|
| [インシデント&アラート](incidents-overview.md)  | Microsoft 365 セキュリティ センターでは、すべてのエンドポイント、メール、ID でインシデントとアラートを管理できます。 関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスが集約されました。 詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。   |
| [ハンティング](advanced-hunting-overview.md)  |  Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含めるには、自動的に Microsoft 365 Defender に移動します。 対応するアラートは、Microsoft 365 Defender にも表示されます。 これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)。 高度 `DeviceAlertEvents` な検索の表は、Microsoft 365 Defender では使用できません。 Microsoft 365 Defender でデバイス固有のアラート情報をクエリするには、テーブルとテーブルを使用して、さまざまなソースからさらに多くの情報を `AlertInfo` `AlertEvidence` 取り込みます。 DeviceAlertEvents を使用せずに Write クエリに従って、次の [デバイス関連のクエリを作成します](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)。|
|[アクション センター](mtp-action-center.md)    | 自動調査と修復アクションに従って実行された保留中のアクションと完了したアクションを一覧表示します。 以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行された修復アクションの保留中および完了済みアクションが一覧表示され、自動調査ではアラートと状態が一覧表示されました。 強化された Microsoft 365 セキュリティ センターでは、アクション センターによって、メール、デバイス、ユーザー間の修復アクションと調査が 1 か所にまとめらされています。  |
| [脅威分析](threat-analytics.md) |  ナビゲーション バーの上部に移動して、検出と使用を容易にします。 エンドポイントと電子メールとコラボレーションの両方の脅威情報が含まれる。    |

### <a name="endpoints"></a>エンドポイント

|**領域**  |**変更の説明**  |
|---------|---------|
|検索   |  見出しに表示される代わりに、Microsoft Defender for Endpoint の検索バーは [エンドポイント] セクションの下に移動しています。 デバイス、ファイル、ユーザー、URL、IPS、脆弱性、ソフトウェア、推奨事項を引き続き検索できます。  |
|[ダッシュボード](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  これは、セキュリティ操作ダッシュボードです。 トリガーされたアクティブなアラートの数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、ユーザーの重大度レベルの概要を確認します。 また、デバイスにセンサーの問題、サービス全体の正常性、未解決のアラートが検出された方法を確認することもできます。 |
|デバイス一覧 | 変更なし。 |
|[脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    ナビゲーション ウィンドウに収まる名前が短くされました。 すべてのページが下にある脅威と脆弱性の管理セクションと同じです。     |
| パートナーと API | 変更なし。 |
| 評価と&チュートリアル    |     新しいテストおよび学習機能。     |
| 構成管理環境   |  変更なし。  |

> [!NOTE]
> **自動調査と修復** は、インシデントの一部です。 自動調査と修復イベントは、[インシデントの調査] **タブ>確認** できます。

### <a name="access-and-reporting"></a>アクセスとレポート

|**領域**  |**変更の説明**  |
|---------|---------|
| レポート  | 脅威の防止、デバイスの正常性とコンプライアンス&脆弱なデバイスなど、コラボレーションの対象となるエンドポイントと電子メール のレポートをご覧ください。 |
| 正常性  |  現在 [、Microsoft 365](https://admin.microsoft.com/)管理センターの [サービス正常性] ページにリンクしています。 |
| 設定 |  Microsoft 365 セキュリティ センター、Microsoft 365 Defender、エンドポイント、電子メール & コラボレーション、ID、デバイス検出の設定を管理します。   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365 のセキュリティ ナビゲーションと機能

左側のナビゲーションまたはクイック起動バーは使い慣れたものに見えます。 ただし、このセキュリティ センターには、いくつかの新しい要素と更新された要素があります。

### <a name="incidents-and-alerts"></a>インシデントとアラート

電子メール、デバイス、ID 全体にわたってインシデントとアラートの管理をまとめます。 アラート ページは、攻撃シグナルを組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。 新しい統一されたエクスペリエンスにより、ワークロード間で一貫したアラートが表示されます。 迅速にトリアージし、調査し、効果的なアクションを実行できます。

- [インシデントの詳細](incidents-overview.md)
- [アラートの管理について詳しくは、次のリンクを参照してください。](investigate-alerts.md)

![アラートとアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>ハンティング

高度な捜索クエリを使用して、エンドポイント、Office 365 メールボックスなど、脅威、マルウェア、悪意のあるアクティビティを事前に [検索します](advanced-hunting-overview.md)。 これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方に関する脅威インジケーターとエンティティを見つけて確認できます。

[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤構成されたデバイスを示している可能性があるイベントを事前に監視するのに役立ちます。


### <a name="action-center"></a>アクション センター

アクション センターには、自動調査および対応機能によって作成された調査が表示されます。 この Microsoft 365 Defender での自動自動修復は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。

[アクション センターの詳細](mtp-action-center.md)

### <a name="threat-analytics"></a>脅威分析

Microsoft のセキュリティの専門家のリサーチ ャーから脅威インテリジェンスを取得します。 脅威分析は、新たな脅威に直面した場合のセキュリティ チームの効率向上に役立ちます。 脅威分析には以下が含まれます。

- Microsoft Defender for Office 365 からのメール関連の検出と軽減策。 これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えてです。
- インシデントビューは、脅威に関連します。
- レポート内の操作可能な情報をすばやく識別して使用するための強化されたエクスペリエンス。

脅威分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーからアクセスするか、組織の上位の脅威を表示する専用のダッシュボード カードからアクセスできます。

脅威分析を使用して新たな脅威 [を追跡して対応する方法について詳しくは、次のリンクを参照してください。](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)

### <a name="endpoints-section"></a>[エンドポイント] セクション

組織内のエンドポイントのセキュリティを表示および管理します。 Microsoft Defender セキュリティ センターを使ったことがある場合は、使い慣れたものに見えます。

![エンドポイントのクイック起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>アクセスとレポート

レポートの表示、設定の変更、ユーザー ロールの変更を行います。

![アクセスとレポートのクイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API 接続

Defender for [Endpoint SIEM API を](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)使用する場合は、引き続き使用できます。 アラート ページまたは Microsoft 365 セキュリティ ポータルのインシデント ページを指す新しいリンクが API ペイロードに追加されました。 新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。 詳しくは、「Microsoft Defender for Endpoint から [Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)セキュリティ センターへのアカウントのリダイレクト」をご覧ください。

### <a name="email-alerts"></a>電子メール通知

引き続きエンドポイント用 Defender のメール通知を使用できます。 Microsoft 365 セキュリティ センターのアラート ページまたはインシデント ページを指す新しいリンクがメールに追加されました。 詳しくは、「Microsoft Defender for Endpoint から [Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)セキュリティ センターへのアカウントのリダイレクト」をご覧ください。

## <a name="related-information"></a>関連情報

- [Microsoft 365 セキュリティ センター](overview-security-center.md)
- [Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [エンドポイント用 Microsoft Defender から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト](microsoft-365-security-mde-redirection.md)
