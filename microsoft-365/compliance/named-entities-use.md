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
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: データ損失防止ポリシーで名前付きエンティティを利用するには、次の手順を使用します。
ms.openlocfilehash: eec82365e6fb4af4b6ca23896addd491637ec022
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110813"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies-preview"></a>データ損失防止ポリシーで名前付きエンティティを使用する (プレビュー)

> [!IMPORTANT]
> 名前付きエンティティ機能が展開され、テナントが利用可能なときにテナントに表示されます。 コンテンツ エクスプローラーとデータ損失防止 (DLP) ポリシー作成フローでそれらを確認します。 

使用を [開始する前に、名前付きエンティティ (プレビュー)](named-entities-learn.md) について説明します。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

これらのサブスクリプションの 1 つが必要です

- 情報保護とガバナンス
- Microsoft 365 E5 Compliance 
- Office 365 E5
- Microsoft 365 E5

完全なライセンスの詳細については、「サービスの説明 [」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)。

### <a name="permissions"></a>アクセス許可

データ損失防止 (DLP) ポリシーの作成および編集に使用するアカウントには **、DLP コンプライアンス管理の役割のアクセス許可が** 必要です。 詳細については、「ユーザーにコンプライアンス[センターへのアクセス権をOffice 365する」を参照してください。](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)


## <a name="supported-locations"></a>サポートされている場所

名前付きエンティティの SIT と拡張ポリシーを使用して、次の場所の機密アイテムを検出して保護できます。

- SharePoint サイト
- OneDrive アカウント
- Teams チャットおよびチャネル メッセージ

名前付きエンティティの SIT と拡張ポリシーは、次の場合はサポートされていません。

- デバイス (Windows 10 エンドポイント デバイス)
- オンプレミス リポジトリ

## <a name="create-and-edit-enhanced-policies"></a>拡張ポリシーの作成と編集

DLP ポリシーを作成または編集するには、「DLP ポリシーの作成、テスト、および調整」の [手順を使用します](create-test-tune-dlp-policy.md)。

## <a name="workloads-and-services-that-support-named-entities"></a>名前付きエンティティをサポートするワークロードとサービス


- **Microsoft 3655 電子情報開示は、Substrate サービス** での名前付きエンティティの使用をサポートしています。
- **Microsoft Defender for Cloud Apps では、Defender** for Cloud Apps ポリシーでの名前付きエンティティの使用がサポートされています。
- **Insider Risk Management は、Substrate** サービスでの名前付きエンティティの使用をサポートします。
- **通信コンプライアンス** は、トランスポート ルールとデータ保存時のExchangeエンティティの使用をサポートしています。
- **Microsoft Information Governance** (MIG) は、トランスポート ルールと保存データのExchange名前付きエンティティの使用をサポートしています。
 
### <a name="unified-dlp"></a>統合 DLP

|ワークロード/サービス  |名前付きエンティティのパブリック プレビューのサポート  |
|---------|---------|
|Office Win32 クライアント ポリシーヒント    |サポートなし  |
|Office WAC クライアント ポリシーヒント    |サポート対象         |
|OWA ポリシーヒント     |サポートなし         |
|Outlookポリシーヒント     |サポートなし |
|エンドポイント (Windows 10デバイス)     |サポートなし  |
|Exchange トランスポート ルール     |サポートなし |
|OneDrive for Business保存時のデータ     |サポート対象         |
|SharePointオンライン データの保存     |サポート対象         |
|Teams保存時のデータ     |サポート対象         |
|電子メール メッセージの保存時のデータ     |サポートなし         |
|Microsoft Defender for Cloud Apps     |サポート対象         |

### <a name="autolabeling"></a>自動ラベル付け

|ワークロード/サービス |名前付きエンティティのパブリック プレビューのサポート  |
|---------|---------|
|Office Win32 クライアントをオフラインにする   |サポートされている場合、ユーザーはラベルを選択して手動で適用する必要があります |
|オンライン Office Win32 クライアント|古い信頼度スキームでサポートされる |
|Outlookオンライン   |古い信頼度スキームでサポートされる  |
|Office WAC クライアント     |サポート対象 |
|OWA     |サポート対象 |
|Exchangeトランスポート     |サポートなし |
|OneDrive for Business保存時のデータ     |サポート対象 |
|SharePointオンライン データの保存|サポート対象|
|Azure Information Protection (AIP) スキャナー|サポートなし|

## <a name="known-issues"></a>既知の問題

|問題  |影響  |
|---------|---------|
|DLP ポリシーのヒント (OWA、Outlook、Office Win32 クライアント)     |   エンティティ条件を含むポリシー ヒントでは、"一致しない" という結果になります。      |
| 人名のアジア言語サポート (中国語、日本語、韓国語)    | ユーザー名に対してラテンベースの文字セットでのみサポートされる名前付きエンティティ (つまり、漢字はサポートされていません)        |
|デバイスのワークロード (エンドポイント)     | ワークロードとしてサポートされていません 。 名前付きエンティティを使用したポリシーの作成は許可されません        |
|オンプレミス リポジトリ    | ワークロードとしてサポートされていません|

## <a name="for-further-information"></a>詳細については、次の情報を参照してください。
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [名前付きエンティティ (プレビュー) について説明します](named-entities-learn.md)。
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
