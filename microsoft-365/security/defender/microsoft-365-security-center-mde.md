---
title: Microsoft Defender for Endpoint in <DICT__Microsoft⚐365⚐Defender>Microsoft 365 Defender</DICT__Microsoft⚐365⚐Defender>
description: '[変更点] から [Microsoft Defender セキュリティ センター] Microsoft 365 Defender'
keywords: Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 8c808bd8c742666c407a59cc6a3bc654d96257b3
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58569911"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a>Microsoft Defender for Endpoint in <DICT__Microsoft⚐365⚐Defender>Microsoft 365 Defender</DICT__Microsoft⚐365⚐Defender>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a>クイック リファレンス

次の図と表に、ナビゲーションの変更点を示Microsoft Defender セキュリティ センターとMicrosoft 365 Defender。

> [!div class="mx-imgBorder"]
> ![どこに移動したのかの画像。](../../media/mde-m3d-security-center.png)

| Microsoft Defender セキュリティ センター | Microsoft 365 Defender |
|---------|---------|
| ダッシュボード <ul><li>セキュリティ操作</li><li>脅威の分析</li></ul>  |ホーム <ul><li>脅威の分析</li></ul>   |
| インシデント | インシデントとアラート |
| デバイス一覧 | デバイス一覧 |
| アラート キュー | インシデントとアラート |
| 自動化された調査 | アクション センター |
| 高度な検出 | 検索 |
| レポート | レポート |
| パートナー& API | パートナー& API |
| 脅威&の管理 | 脆弱性管理 |
| 評価とチュートリアル | 評価&チュートリアル |
| 構成管理環境 | 構成管理環境 |
| 設定 | 設定 | 

強化[されたMicrosoft 365 Defender機能](overview-security-center.md)は、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能 [https://security.microsoft.com](https://security.microsoft.com) を組み合わせた機能です。 これにより、既存の Microsoft セキュリティ ポータルの機能が統合され、Microsoft Defender セキュリティ センターコンプライアンス センター Office 365セキュリティ &されます。

この記事では、Microsoft Defender セキュリティ センターの変更点と改善点の一部について説明Microsoft 365 Defender。 ただし、注意が必要な新しい要素と更新された要素があります。

これまで[、Microsoft Defender セキュリティ センターは](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)Microsoft Defender for Endpoint のホームでした。 Enterpriseチームは、セキュリティ チームを使用して、潜在的な高度な永続的な脅威アクティビティやデータ侵害に関するアラートの監視と対応を支援しています。 ポータルの数を減らすのに役立つMicrosoft 365 Defenderは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。

Microsoft Defender for Endpoint in Microsoft 365 Defender では[、Microsoft Defender](mssp-access.md)セキュリティ センターでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセス許可をサポートしています。

> [!IMPORTANT]
> 現在のサブスクリプションにMicrosoft 365 Defender表示される内容は異なります。 たとえば、Microsoft Defender for Office 365 のライセンスを持Office 365場合、[電子メール & コラボレーション] セクションは表示されません。

> [!Note]
> Microsoft 365 Defender次の場合は使用できません。
>- US Government Community Cloud (GCC)
>- 米国 Government Community Cloud高 (GCC高)
>- 米国国防総省
>- 商用ライセンスを持つすべての米国政府機関

次の情報をMicrosoft 365 Defenderします [https://security.microsoft.com](https://security.microsoft.com) 。

利点の詳細: [Microsoft 365 Defender](overview-security-center.md)概要

## <a name="whats-changed"></a>変更内容

次の表は、ユーザーとユーザーの間のMicrosoft Defender セキュリティ センター参照Microsoft 365 Defender。

### <a name="alerts-and-actions"></a>アラートとアクション

| 分野 | 変更の説明 |
|---------|---------|
| [インシデント&アラート](incidents-overview.md)  | このMicrosoft 365 Defender、すべてのエンドポイント、電子メール、および ID でインシデントとアラートを管理できます。 関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスを統合しました。 詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。   |
| [検索](advanced-hunting-overview.md)  |  Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含める場合は、自動的に id テーブルと電子メール テーブルMicrosoft 365 Defender。 対応するアラートは、ユーザーの通知にもMicrosoft 365 Defender。 これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。 <br><br>高度 `DeviceAlertEvents` な検索用のテーブルは、Microsoft 365 Defender。 デバイス固有のアラート情報を Microsoft 365 Defender でクエリするには、テーブルとテーブルを使用して、さまざまなソース セットからのさらに多くの情報に `AlertInfo` `AlertEvidence` 対応できます。 [DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)なしで書き込みクエリを実行して、次のデバイス関連のクエリを作成します。|
|[アクション センター](m365d-action-center.md)    | 自動調査と修復アクションに続いて実行された保留中のアクションと完了したアクションを一覧表示します。 以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行される修復アクションの保留中および完了したアクションが一覧表示され、自動調査にはアラートと状態が一覧表示されました。 改善されたMicrosoft 365 Defenderアクション センターは、電子メール、デバイス、およびユーザー間の修復アクションと調査を 1 つの場所にまとめます。  |
| [脅威の分析](threat-analytics.md) |  ナビゲーション バーの上部に移動し、検出と使用を容易にします。 エンドポイントと電子メールとコラボレーションの両方に関する脅威情報が含まれる。    |

### <a name="endpoints"></a>エンドポイント

| 分野 | 変更の説明 |
|---------|---------|
|検索   |  見出しの代わりに、Microsoft Defender for Endpoint 検索バーが [エンドポイント] セクションの下を移動しています。 引き続きデバイス、ファイル、ユーザー、URL、IPs、脆弱性、ソフトウェア、推奨事項を検索できます。  |
|[ダッシュボード](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  これは、セキュリティ操作ダッシュボードです。 アクティブなアラートがトリガーされた数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、およびユーザーの重大度レベルの概要を参照してください。 また、センサーの問題が発生したデバイス、サービス全体の正常性、未解決のアラートが検出された方法も確認できます。 |
|デバイス一覧 | 変更はありません。 |
|[脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    ナビゲーション ウィンドウに収まる名前が短縮されました。 すべてのページが下にある[脅威と脆弱性の管理]セクションと同じです。     |
| パートナーと API | 変更はありません。 |
| 評価&チュートリアル    |     新しいテストと学習機能。     |
| 構成管理環境   |  変更はありません。  |

> [!NOTE]
> **自動調査と修復** は、インシデントの一部です。 [インシデントの調査] タブには、[自動調査と修復イベント> **確認** できます。

> [!TIP]
> デバイスの検索は、エンドポイントと検索>されます。

### <a name="access-and-reporting"></a>アクセスとレポート

| 分野 | 変更の説明 |
|---------|---------|
| レポート  | 脅威の保護、デバイスの正常性とコンプライアンス、脆弱な&など、エンドポイントと電子メール のコラボレーションに関するレポートを参照してください。 |
| 正常性  |  現在、ページの [サービス正常性] ページに[リンク](https://admin.microsoft.com/)Microsoft 365 管理センター。 |
| 設定 |  グループ、エンドポイント、メール Microsoft 365 Defender、ID、デバイス&の設定を管理します。   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365のナビゲーションと機能

左側のナビゲーションまたはクイック起動バーは見慣れたものに見えます。 ただし、このセキュリティ センターには、いくつかの新しい要素や更新された要素があります。

### <a name="incidents-and-alerts"></a>インシデントと警告

メール、デバイス、ID 全体でインシデントと通知の管理を 1 か所で行います。 アラート ページは、攻撃信号を組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。 新しく統合されたエクスペリエンスにより、さまざまなワークロード全体で一貫した警告が表示されます。 トリアージ、調査、効果的なアクションをすばやく実行できます。

- [インシデントの詳細](incidents-overview.md)
- [通知の管理に関するその他の情報](investigate-alerts.md)

![[アラートとアクション] クイック起動バー。](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>検索

エンドポイント、Office 365 メールボックスなどに対する脅威、マルウェア、悪意のあるアクティビティを積極的に検索するために、[高度な検索クエリ](advanced-hunting-overview.md)を使用します。 これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方について脅威インジケーターとエンティティを見つけて確認できます。

[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤った構成済みデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。


### <a name="action-center"></a>アクション センター

アクション センターには、自動調査と自動応答機能によって作成された調査が表示されます。 この Microsoft 365 Defender の自動自己修復機能は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。

[アクション センターの詳細については、以下を参照してください](m365d-action-center.md)。

### <a name="threat-analytics"></a>脅威の分析

専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。 脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。 脅威の分析には以下が含まれます。

- Microsoft Defender for Office 365 からのメール関連の検出と移行。 これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。
- 脅威に関連するインシデントが表示されます。
- レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。

脅威分析には、Microsoft 365 Defender の左上のナビゲーション バーから、または組織の上位の脅威を示す専用のダッシュボード カードからアクセスできます。

脅威分析を使用して新たな脅威を追跡して対応する [方法について詳しくは、次のページをご覧ください](./threat-analytics.md)。

### <a name="endpoints-section"></a>[エンドポイント] セクション

組織のエンドポイントのセキュリティを表示および管理します。 このファイルを使用したMicrosoft Defender セキュリティ センター見慣れたものに見えます。

![[エンドポイント] クイック起動バー。](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>アクセスとレポート

レポートの表示、設定の変更、およびユーザーの役割変更を行います。

![[アクセスとレポート] クイック起動バー。](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API 接続

Defender for [Endpoint SIEM API を使用する場合](../defender-endpoint/enable-siem-integration.md)は、引き続き実行できます。 API ペイロードに、セキュリティ ポータルのアラート ページまたはインシデント ページをポイントする新しいリンクMicrosoft 365しました。 新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。 詳細については、「アカウントを Microsoft Defender for Endpoint からエンドポイント[にリダイレクトする」を参照](./microsoft-365-security-mde-redirection.md)Microsoft 365 Defender。

### <a name="email-alerts"></a>電子メール通知

Defender for Endpoint の電子メール 通知は引き続き使用できます。 メールに、アラート ページまたはインシデント ページを指す新しいリンクが追加Microsoft 365 Defender。 詳細については、「アカウントを Microsoft Defender for Endpoint からエンドポイント[にリダイレクトする」を参照](./microsoft-365-security-mde-redirection.md)Microsoft 365 Defender。

### <a name="managed-security-service-providers-mssp"></a>Managed Security Service Providers (MSSP)

同じブラウズ セッションで複数のテナントに同時にログインする方法は、統合ポータルでは現在サポートされていません。 自動リダイレクトをオプトアウトするには、元の [Microsoft Defender for Endpoint](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)ポータルに戻して、問題が解決されるまでこの機能を維持できます。

## <a name="related-information"></a>関連情報

- [Microsoft 365 Defender](overview-security-center.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft Defender for Endpoint からアカウントをユーザーにリダイレクトMicrosoft 365 Defender](microsoft-365-security-mde-redirection.md)
