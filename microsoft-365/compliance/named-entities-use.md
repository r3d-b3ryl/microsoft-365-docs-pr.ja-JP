---
title: データ損失防止ポリシーで名前付きエンティティを使用する (プレビュー)
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
ms.openlocfilehash: 9b3a8899ef4b64c682289e29df19648a00d4f048
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665164"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies-preview"></a>データ損失防止ポリシーで名前付きエンティティを使用する (プレビュー)

> [!IMPORTANT]
> 名前付きエンティティ機能がロールアウトされ、テナントが使用可能になるとテナントに表示されます。 コンテンツ エクスプローラーとデータ損失防止 (DLP) ポリシー作成フローで確認します。 

[名前付きエンティティの使用を開始する前に、名前付きエンティティ (プレビュー) について学習](named-entities-learn.md)してください。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

これらのサブスクリプションのいずれかを持っている必要があります

- Information Protectionとガバナンス
- Microsoft 365 E5 Compliance 
- Office 365 E5
- Microsoft 365 E5

完全なライセンスの詳細については、 [サービスの説明を](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)参照してください。

### <a name="permissions"></a>アクセス許可

データ損失防止 (DLP) ポリシーの作成と編集に使用するアカウントには、 **DLP コンプライアンス管理** ロールのアクセス許可が必要です。 詳細については、「[Office 365 コンプライアンス センターへのアクセス権をユーザーに付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。


## <a name="supported-locations"></a>サポートされている場所

名前付きエンティティ SIT と強化されたポリシーを使用して、次の場所の機密アイテムを検出して保護できます。

- SharePoint サイト
- OneDrive アカウント
- Teams チャットおよびチャネル メッセージ
- デバイス (Windows 10 エンドポイント デバイス)

名前付きエンティティの SIT と強化されたポリシーは、次ではサポートされていません。


- オンプレミスのリポジトリ
- Power BI

## <a name="create-and-edit-enhanced-policies"></a>強化されたポリシーを作成および編集する

DLP ポリシーを作成または編集するには、「DLP ポリシーの [作成、テスト、および調整](create-test-tune-dlp-policy.md)」の手順を使用します。

## <a name="workloads-and-services-that-support-named-entities"></a>名前付きエンティティをサポートするワークロードとサービス


- **Microsoft 3655 電子情報開示** では、Entity サービスでの名前付きエンティティの使用がサポートされています。
- **Microsoft Defender for Cloud Appsでは、** Defender for Cloud Apps ポリシーでの名前付きエンティティの使用がサポートされます。
- **Insider Risk Management** では、Entity サービスでの名前付きエンティティの使用がサポートされています。
<!--- **Communication Compliance** doesn't support the use of named entities in Exchange transport rules and data-at-rest.
- **Microsoft Information Governance** (MIG) doesn't support the use of named entities in Exchange transport rules and data-at-rest.-->
 
### <a name="unified-dlp"></a>統合 DLP

|ワークロード/サービス  |名前付きエンティティのパブリック プレビューのサポート  |
|---------|---------|
|Office Win32 クライアント ポリシー ヒント    |サポートなし  |
|Office WAC クライアント ポリシー ヒント    |されていません         |
|OWA ポリシーのヒント     |サポートなし         |
|Outlook ポリシーヒント     |サポートなし |
|エンドポイント (Windows 10 デバイス)     |されていません  |
|Exchange トランスポート ルール     |サポートなし |
|保存データをOneDrive for Businessする     |されていません         |
|SharePoint Online data-at-rest     |されていません         |
|保存データをTeamsする     |されていません         |
|電子メール メッセージの保存時データ     |サポートなし         |
|Microsoft Defender for Cloud Apps     |されていません         |

### <a name="autolabeling"></a>自動ラベル付け

|ワークロード/サービス |名前付きエンティティのパブリック プレビューのサポート  |
|---------|---------|
|Office Win32 クライアントをオフラインにする   |サポートされている場合、ユーザーはラベルを選択し、手動で適用する必要があります |
|オンライン Office Win32 クライアントオンライン|以前の信頼スキームでサポートされている |
|オンラインでOutlookする   |以前の信頼スキームでサポートされている  |
|WAC クライアントOffice     |されていません |
|OWA     |サポート対象 |
|Exchangeトランスポート     |サポートなし |
|保存データをOneDrive for Businessする     |されていません |
|SharePoint Online data-at-rest|されていません|
|Azure Information Protection (AIP) スキャナー|サポートなし|

## <a name="known-issues"></a>既知の問題

|問題  |影響  |
|---------|---------|
|DLP ポリシーのヒント (OWA、Outlook、Office Win32 クライアント)     |   エンティティの条件を含むポリシー ヒントは、"一致しない" 結果になります      |
| 人名のアジア言語サポート (中国語、日本語、韓国語)    | 人物名のラテン語ベースの文字セットでのみサポートされている名前付きエンティティ (つまり、漢字はサポートされていません)        |
|オンプレミスのリポジトリ    | ワークロードとしてサポートされていません|

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="for-further-information"></a>詳細については、次の情報を参照してください。
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [名前付きエンティティ (プレビュー) について説明](named-entities-learn.md)します。
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
