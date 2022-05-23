---
title: DLP ポリシーで名前付きエンティティを使用する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: データ損失防止ポリシーで名前付きエンティティを利用するには、次の手順を使用します。
ms.openlocfilehash: 85d3d11704ea238f6c1acff64193d8aaba8994b8
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637188"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies"></a>データ損失防止ポリシーで名前付きエンティティを使用する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

名前付きエンティティの使用を開始する前に、 [名前付きエンティティの詳細](named-entities-learn.md) を確認してください。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

完全なライセンスの詳細については、 [サービスの説明を](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)参照してください。

### <a name="permissions"></a>アクセス許可

データ損失防止 (DLP) ポリシーの作成と編集に使用するアカウントには、 **DLP コンプライアンス管理** ロールのアクセス許可が必要です。 詳細については、「[Office 365 コンプライアンス センターへのアクセス権をユーザーに付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。


## <a name="supported-locations"></a>サポートされている場所

名前付きエンティティ SIT と強化されたポリシーを使用して、次の場所の機密アイテムを検出して保護できます。

- SharePoint サイト
- OneDrive アカウント
- Teams チャットおよびチャネル メッセージ
- デバイス (Windows 10、11 個のエンドポイント デバイス)
- Exchange メールボックス
- Microsoft Defender for Cloud Apps

名前付きエンティティの SIT と強化されたポリシーは、次ではサポートされていません。

- オンプレミスのリポジトリ
- Power BI

## <a name="create-and-edit-enhanced-policies"></a>強化されたポリシーを作成および編集する

DLP ポリシーを作成または編集するには、「DLP ポリシーの [作成、テスト、および調整](create-test-tune-dlp-policy.md)」の手順を使用します。

## <a name="workloads-and-services-that-support-named-entities"></a>名前付きエンティティをサポートするワークロードとサービス

- **Microsoft 365電子情報開示** では、Entity サービスでの名前付きエンティティの使用がサポートされます。
- **Microsoft Defender for Cloud Appsでは、** Defender for Cloud アプリ ポータルの Defender for Cloud Apps ポリシーでの名前付きエンティティの使用がサポートされます。
- **Insider Risk Management** では、Entity サービスでの名前付きエンティティの使用がサポートされています。
- **レコード管理** では、名前付きエンティティの使用がサポートされます。
- **厳密なデータ一致の機密情報の種類** では、名前付きエンティティの使用がサポートされます。
<!--- **Communication Compliance** doesn't support the use of named entities in Exchange transport rules and data-at-rest.
- **Microsoft Information Governance** (MIG) doesn't support the use of named entities in Exchange transport rules and data-at-rest.-->
 
### <a name="unified-dlp"></a>統合 DLP

|ワークロード/サービス  |名前付きエンティティのサポート  |
|---------|---------|
|Office Win32 クライアント ポリシー ヒント    |非サポート  |
|Office WAC クライアント ポリシー ヒント    |サポート         |
|OWA ポリシーのヒント     |非サポート         |
|Outlook ポリシーヒント     |サポート対象外 |
|エンドポイント (Windows 10、11 台のデバイス)     |サポート  |
|Exchange トランスポート ルール     |サポート |
|保存データをOneDrive for Businessする     |サポート         |
|SharePoint Online data-at-rest     |サポート         |
|保存データをTeamsする     |サポート         |
|電子メール メッセージの保存時データ     |プライバシー サービス プランを使用するテナントでサポートされている         |
|Microsoft Defender for Cloud Apps     |サポート         |

### <a name="autolabeling"></a>自動ラベル付け

|ワークロード/サービス |名前付きエンティティのサポート  |
|---------|---------|
|Office Win32 クライアントをオフラインにする   |サポートされている、ユーザーはラベルを選択し、手動で適用する必要があります |
|オンライン Office Win32 クライアントオンライン|以前の信頼スキームでサポートされている |
|オンラインでOutlookする   |以前の信頼スキームでサポートされている  |
|WAC クライアントOffice     |サポート |
|OWA     |サポート |
|Exchangeトランスポート     |サポート |
|保存データをOneDrive for Businessする     |サポート |
|SharePoint Online data-at-rest|サポート|
|Azure Information Protection (AIP) スキャナー|サポート対象外|

## <a name="known-issues"></a>既知の問題

|問題  |影響  |
|---------|---------|
|DLP ポリシーのヒント (OWA、Outlook、Office Win32 クライアント)     |   エンティティの条件を含むポリシー ヒントは、"一致しない" 結果になります      |
| 人名のアジア言語サポート (中国語、日本語、韓国語)    | 人物名のラテン語ベースの文字セットでのみサポートされている名前付きエンティティ (つまり、漢字はサポートされていません)        |
|オンプレミスのリポジトリ    | ワークロードとしてサポートされていません|
|Power BI (プレビュー) | サポート対象外

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="best-practices-for-using-named-entity-sits"></a>名前付きエンティティ SIT を使用するためのベスト プラクティス

名前付きエンティティ SIT を使用するポリシーを作成または編集するときに使用できるいくつかのプラクティスを次に示します。

- スプレッドシート内のデータを探すときに低いインスタンス数 (3 から 5) を使用し、そのデータに SIT で必要なキーワードは列ヘッダーにのみ含まれます。 たとえば、米国社会保障番号を探していて、キーワード `Social Security Number` は列ヘッダーでのみ発生するとします。 値 (裏付けとなる証拠) は下のセルにあるため、最初の少数のインスタンスのみが検出されるキーワードに十分近い可能性があります。  

- 名前付きエンティティ SIT (All Full Names など) を使用して米国社会保障番号を見つけるのに役立つ場合は、10 や 50 などのより大きなインスタンス数を使用します。 その後、人物名と SAN の両方が一緒に検出されると、真の陽性が得られる可能性が高くなります。

- [自動ラベル付けシミュレーションを](apply-sensitivity-label-automatically.md#learn-about-simulation-mode)使用して、名前付きエンティティ SIT の精度をテストできます。 名前付きエンティティ SIT を使用してシミュレーションを実行し、ポリシーに一致する項目を確認します。 この情報を使用すると、カスタム ポリシーまたは強化されたテンプレート条件でインスタンス数と信頼レベルを調整することで、精度を微調整できます。 運用環境で名前付きエンティティを含む DLP ポリシーまたは自動ラベル付けポリシーをデプロイする前に、シミュレーションを精度が目的の場所になるまで反復処理できます。 フローの概要を次に示します。

1. シミュレーション モードでテストする SIT または SIT の組み合わせを特定します (カスタムまたは複製、編集)。
1. 自動ラベル付けポリシーで、Exchange、SharePoint サイト、またはOneDrive アカウントで一致するものが見つかると、適用する秘密度ラベルを特定または作成します。
1. 手順 1 の SIT を使用し、DLP ポリシーで使用されるのと同じ条件と例外を使用する秘密度自動ラベル付けポリシーを作成する
1. ポリシー シミュレーションを実行する
1. 結果を表示する
1. 偽陽性を減らすには、SIT またはポリシーとインスタンス数と信頼レベルを調整します。
1. 目的の精度の結果が得られるまで繰り返します。


## <a name="for-further-information"></a>詳細については、次の情報を参照してください。
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [名前付きエンティティについて説明します](named-entities-learn.md)。
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
