---
title: Microsoft 365 Defender の Microsoft Defender for Endpoint
description: Microsoft Defender セキュリティ センターからMicrosoft 365 Defenderへの変更について説明します
keywords: Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、セキュリティ ポータル、Defender セキュリティ ポータルの概要
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: bac70dd864e1ab72fae5fbefa2a8da12cce4f6e7
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667232"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a>Microsoft 365 Defender の Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a>クイック リファレンス

次の図と表は、Microsoft Defender セキュリティ センターとMicrosoft 365 Defender間のナビゲーションの変更を示しています。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/mde-m3d-security-center.png" alt-text="Microsoft 365 Defender ポータルの新しい場所" lightbox="../../media/mde-m3d-security-center.png":::

| Microsoft Defender セキュリティ センター | Microsoft 365 Defender |
|---------|---------|
| ダッシュ ボード <ul><li>セキュリティ操作</li><li>脅威の分析</li></ul>  |Home <ul><li>脅威の分析</li></ul>   |
| インシデント | インシデントとアラート |
| デバイス一覧 | デバイス一覧 |
| アラート キュー | インシデントとアラート |
| 自動化された調査 | アクション センター |
| 高度な追及 | 検索 |
| レポート | レポート |
| パートナー& API | パートナー& API |
| 脅威&脆弱性管理 | 脆弱性管理 |
| 評価とチュートリアル | 評価&チュートリアル |
| 構成管理環境 | 構成管理環境 |
| Settings | Settings | 

強化された[Microsoft 365 Defender](microsoft-365-defender.md#the-microsoft-365-defender-portal)<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>は、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能を組み合わせたものです。 これにより、Microsoft Defender セキュリティ センターやOffice 365 セキュリティ & コンプライアンス センターなど、既存の Microsoft セキュリティ ポータルの機能がまとめられます。

Microsoft Defender セキュリティ センターに慣れている場合は、この記事では、Microsoft 365 Defenderの変更と機能強化の一部について説明するのに役立ちます。 ただし、注意すべき新しい要素と更新された要素がいくつかあります。

これまで、[Microsoft Defender セキュリティ センター](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)はMicrosoft Defender for Endpointのホームでした。 Enterpriseセキュリティ チームは、セキュリティ チームを使用して、潜在的な高度な永続的な脅威アクティビティまたはデータ侵害のアラートの監視と対応を支援してきました。 ポータルの数を減らすために、Microsoft 365 Defenderは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するためのホームになります。

Microsoft 365 DefenderのMicrosoft Defender for Endpointでは、Microsoft Defender セキュリティ センターでアクセスが許可されるのと同じ方法で[マネージド セキュリティ サービス プロバイダー (MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) [へのアクセスを許可](mssp-access.md)できます。

> [!IMPORTANT]
> Microsoft 365 Defenderに表示される内容は、現在のサブスクリプションによって異なります。 たとえば、Microsoft Defender for Office 365のライセンスがない場合、[電子メール & コラボレーション] セクションは表示されません。

> [!Note]
> Microsoft 365 Defenderは次の目的では使用できません。
>- 米国Government Community Cloud (GCC)
>- US Government Community Cloud High (GCC High)
>- 米国国防総省
>- 商用ライセンスを持つすべての米国政府機関

Microsoft 365 Defenderを見てみましょう<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>。

利点の詳細を確認する: [Microsoft 365 Defenderの概要](microsoft-365-defender.md)

## <a name="whats-changed"></a>変更内容

この表は、Microsoft Defender セキュリティ センターとMicrosoft 365 Defenderの間の変更のクイック リファレンスです。

### <a name="alerts-and-actions"></a>アラートとアクション

| 分野 | 変更の説明 |
|---------|---------|
| [インシデント&アラート](incidents-overview.md)  | Microsoft 365 Defenderでは、すべてのエンドポイント、電子メール、ID でインシデントとアラートを管理できます。 関連するイベントをより簡単に見つけられるように、エクスペリエンスを集約しました。 詳細については、「 [インシデントの概要](incidents-overview.md)」を参照してください。   |
| [検索](advanced-hunting-overview.md)  |  id テーブルと電子メール テーブルを含めるためにMicrosoft Defender for Endpointで作成されたカスタム検出ルールを変更すると、自動的にMicrosoft 365 Defenderに移動されます。 対応するアラートは、Microsoft 365 Defenderにも表示されます。 これらの変更の詳細については、「 [カスタム検出規則の移行」](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)を参照してください。 <br><br>高度なハンティングのテーブルは`DeviceAlertEvents`、Microsoft 365 Defenderでは使用できません。 Microsoft 365 Defenderでデバイス固有のアラート情報にクエリを実行するには、さまざまなソースのセットからさらに多くの情報に対応するために、テーブルと`AlertEvidence`テーブルを使用`AlertInfo`します。 [DeviceAlertEvents を使用せずに書き込みクエリに従って、次のデバイス関連のクエリを作成します](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)。|
|[アクション センター](m365d-action-center.md)    | 自動調査と修復アクションの後に実行された保留中のアクションと完了したアクションを一覧表示します。 以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行された修復アクションの保留中と完了のアクションが一覧表示され、自動調査ではアラートと状態が一覧表示されました。 改善されたMicrosoft 365 Defenderでは、アクション センターは、電子メール、デバイス、ユーザー全体にわたる修復アクションと調査をすべて 1 つの場所にまとめます。  |
| [脅威分析](threat-analytics.md) |  ナビゲーション バーの上部に移動し、検出と使用を容易にします。 エンドポイントと電子メールとコラボレーションの両方の脅威情報が含まれるようになりました。    |

### <a name="endpoints"></a>エンドポイント

| 分野 | 変更の説明 |
|---------|---------|
|検索   |  検索バーはページの上部にあります。 入力時に提案が提供されます。 Defender for Endpoint と Defender for Identity では、次のエンティティを検索できます。 <br><br> - **デバイス** - Defender for Endpoint と Defender for Identity の両方でサポートされます。 たとえば、"contains" を使用してホスト名の一部を検索するなど、検索演算子を使用することもできます。 <br><br> - **ユーザー** - Defender for Endpoint と Defender for Identity の両方でサポートされています。 <br><br> - **ファイル、IP、URL** - Defender for Endpoint と同じ機能。 <br> 注: *IP と URL の検索は完全に一致し、検索結果ページには表示されません。エンティティ ページに直接移動します。  <br><br> - **TVM** - Defender for Endpoint と同じ機能 (脆弱性、ソフトウェア、推奨事項)。 <br><br>  強化された検索結果ページでは、すべてのエンティティからの結果が一元化されます。  |
|[ダッシュボード](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  これはセキュリティ操作ダッシュボードです。 アクティブなアラートの数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているか、アラート、デバイス、ユーザーの重大度レベルの概要を確認します。 センサーの問題、サービスの全体的な正常性、未解決のアラートが検出された方法についても確認できます。 |
|デバイス一覧 | 変更はありません。 |
|[脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    ナビゲーション ウィンドウに収まるように名前が短くされました。 脅威と脆弱性の管理 セクションと同じで、下のすべてのページが表示されます。     |
| パートナーと API | 変更はありません。 |
| 評価&チュートリアル    |     新しいテストと学習機能。     |
| 構成管理環境   |  変更はありません。  |

> [!NOTE]
> **自動調査と修復** がインシデントの一部になりました。 [ **インシデント** >調査] タブに自動調査と修復イベントが表示されます。

> [!TIP]
> デバイス検索は、Endpoints > Search から実行されます。

### <a name="access-and-reporting"></a>アクセスとレポート

| 分野 | 変更の説明 |
|---------|---------|
| レポート  | 脅威の保護、デバイスの正常性とコンプライアンス、脆弱なデバイスなど、エンドポイントと電子メール &コラボレーションのレポートを参照してください。 |
| 正常性  |  現在、Microsoft 365 管理センターの [サービス正常性] [ページにリンク](https://admin.microsoft.com/)しています。 |
| Settings |  Microsoft 365 Defender、エンドポイント、電子メール &コラボレーション、ID、デバイス検出の設定を管理します。   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365セキュリティ ナビゲーションと機能

左側のナビゲーションまたはクイック起動バーは見慣れたものに見えます。 ただし、Microsoft 365 Defender ポータルには、いくつかの新しい要素と更新された要素があります。 

### <a name="incidents-and-alerts"></a>インシデントと警告

メール、デバイス、ID 全体でインシデントと通知の管理を 1 か所で行います。 アラート ページでは、攻撃信号を組み合わせて詳細なストーリーを構築することで、アラートに対する完全なコンテキストを提供します。 新しく統合されたエクスペリエンスにより、さまざまなワークロード全体で一貫した警告が表示されます。 トリアージ、調査、効果的なアクションをすばやく実行できます。

- [インシデントの詳細](incidents-overview.md)
- [通知の管理に関するその他の情報](investigate-alerts.md)

:::image type="content" source="../../media/converge-1-alerts-and-actions.png" alt-text="Microsoft 365 Defender ポータルの [アラートとアクション] クイック起動バー" lightbox="../../media/converge-1-alerts-and-actions.png":::

### <a name="hunting"></a>検索

エンドポイント、Office 365 メールボックスなどに対する脅威、マルウェア、悪意のあるアクティビティを積極的に検索するために、[高度な検索クエリ](advanced-hunting-overview.md)を使用します。 これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方の脅威インジケーターとエンティティを見つけて確認できます。

[カスタム検出ルール](custom-detection-rules.md) は、高度なハンティング クエリから構築でき、侵害アクティビティや不適切な構成されたデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。


### <a name="action-center"></a>アクション センター

アクション センターには、自動調査と自動応答機能によって作成された調査が表示されます。 この Microsoft 365 Defender の自動自己修復機能は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。

[アクション センターの詳細については、こちらを参照してください](m365d-action-center.md)。

### <a name="threat-analytics"></a>脅威の分析

専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。 脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。 脅威の分析には以下が含まれます。

- Microsoft Defender for Office 365 からのメール関連の検出と移行。 これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。
- 脅威に関連するインシデントが表示されます。
- レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。

脅威分析には、Microsoft 365 Defenderの左上のナビゲーション バーから、または組織のトップ脅威を示す専用ダッシュボード カードからアクセスできます。

脅威分析を使用して [、新たな脅威を追跡して対応する](./threat-analytics.md)方法の詳細を確認します。

### <a name="endpoints-section"></a>[エンドポイント] セクション

組織内のエンドポイントのセキュリティを表示および管理します。 Microsoft Defender セキュリティ センターを使用した場合は、使い慣れた外観になります。

:::image type="content" source="../../media/converge-2-endpoints.png" alt-text="Microsoft 365 Defender ポータルの [Endpoints] クイック起動バー" lightbox="../../media/converge-2-endpoints.png":::

### <a name="access-and-reports"></a>アクセスとレポート

レポートの表示、設定の変更、およびユーザーの役割変更を行います。

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Microsoft 365 Defender ポータルの [アクセスとレポート] クイック起動バー" lightbox="../../media/converge-4-access-and-reporting-new.png":::

### <a name="siem-api-connections"></a>SIEM API 接続

[Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md) を使用する場合は、引き続き実行できます。 アラート ページまたは Microsoft 365 セキュリティ ポータルのインシデント ページを指す新しいリンクが API ペイロードに追加されました。 新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。 詳細については、「[Microsoft Defender for EndpointからMicrosoft 365 Defenderへのアカウントのリダイレクト」を](./microsoft-365-security-mde-redirection.md)参照してください。

### <a name="email-alerts"></a>電子メール アラート

Defender for Endpoint には引き続き電子メール アラートを使用できます。 アラート ページまたはMicrosoft 365 Defenderのインシデント ページを指す新しいリンクが電子メールに追加されました。 詳細については、「[Microsoft Defender for EndpointからMicrosoft 365 Defenderへのアカウントのリダイレクト」を](./microsoft-365-security-mde-redirection.md)参照してください。

### <a name="managed-security-service-providers-mssp"></a>マネージド セキュリティ サービス プロバイダー (MSSP)

同じ閲覧セッションで同時に複数のテナントにログインすることは、現在、統合ポータルではサポートされていません。 [以前のMicrosoft Defender for Endpoint ポータルに戻](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)すことで、自動リダイレクトをオプトアウトして、問題が解決するまでこの機能を維持できます。

## <a name="related-information"></a>関連情報

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [Microsoft Defender for EndpointからMicrosoft 365 Defenderへのアカウントのリダイレクト](microsoft-365-security-mde-redirection.md)
