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
ms.openlocfilehash: 5adb410689e597395f1b13152ed62af75fa111d6
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525223"
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

完全なライセンスの詳細については、「サービスの [説明」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)。

### <a name="permissions"></a>アクセス許可

データ損失防止 (DLP) ポリシーの作成および編集に使用するアカウントには、 **DLP コンプライアンス管理の役割のアクセス許可が** 必要です。 詳細については、「ユーザーにコンプライアンス [センターへのアクセス権を与Office 365する」を参照してください。](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)


## <a name="supported-locations"></a>サポートされている場所

名前付きエンティティの SIT と拡張ポリシーを使用して、次の場所の機密アイテムを検出して保護できます。

- SharePoint サイト
- OneDrive アカウント
- Teams チャットおよびチャネル メッセージ
- デバイス (Windows 10 エンドポイント デバイス)

名前付きエンティティの SIT と拡張ポリシーは、次の場合はサポートされていません。


- オンプレミス リポジトリ
- Power BI

## <a name="create-and-edit-enhanced-policies"></a>拡張ポリシーの作成と編集

DLP ポリシーを作成または編集するには、「DLP ポリシーの作成、テスト、および調整」 [の手順を使用します](create-test-tune-dlp-policy.md)。

## <a name="workloads-and-services-that-support-named-entities"></a>名前付きエンティティをサポートするワークロードとサービス


- **Microsoft 3655 電子情報開示は、Substrate サービス** での名前付きエンティティの使用をサポートしています。
- **Microsoft Defender for Cloud Apps では、** Defender for Cloud Apps ポリシーでの名前付きエンティティの使用がサポートされています。
- **Insider Risk Management は、** Substrate サービスでの名前付きエンティティの使用をサポートします。
- **通信コンプライアンス** は、トランスポート ルールとデータの保存時Exchange名前付きエンティティの使用をサポートしています。
- **Microsoft Information Governance** (MIG) では、トランスポート ルールとデータ保存時の名前付Exchangeの使用はサポートされていません。
 
### <a name="unified-dlp"></a>統合 DLP

|ワークロード/サービス  |名前付きエンティティのパブリック プレビューのサポート  |
|---------|---------|
|Office Win32 クライアント ポリシーヒント    |サポートなし  |
|Office WAC クライアント ポリシーヒント    |サポートされる         |
|OWA ポリシーヒント     |サポートなし         |
|Outlookヒント     |サポートなし |
|エンドポイント (Windows 10デバイス)     |サポートされる  |
|Exchange トランスポート ルール     |サポートなし |
|OneDrive for Business保存時のデータ     |サポートされる         |
|SharePointオンライン データの保存     |サポートされる         |
|Teams保存時のデータ     |サポートされる         |
|電子メール メッセージの保存時のデータ     |サポートなし         |
|Microsoft Defender for Cloud Apps     |サポートされる         |

### <a name="autolabeling"></a>自動ラベル付け

|ワークロード/サービス |名前付きエンティティのパブリック プレビューのサポート  |
|---------|---------|
|Office Win32 クライアントをオフラインにする   |サポートされている場合、ユーザーはラベルを選択して手動で適用する必要があります |
|オンライン Office Win32 クライアント|古い信頼度スキームでサポートされる |
|Outlookオンライン   |古い信頼度スキームでサポートされる  |
|Office WAC クライアント     |サポートされる |
|OWA     |サポート対象 |
|Exchangeトランスポート     |サポートなし |
|OneDrive for Business保存時のデータ     |サポートされる |
|SharePointオンライン データの保存|サポートされる|
|Azure Information Protection (AIP) スキャナー|サポートなし|

## <a name="known-issues"></a>既知の問題

|問題  |影響  |
|---------|---------|
|DLP ポリシーのヒント (OWA、Outlook、Office Win32 クライアント)     |   エンティティ条件を含むポリシー ヒントでは、"一致しない" という結果になります。      |
| 人名のアジア言語サポート (中国語、日本語、韓国語)    | ユーザー名に対してラテンベースの文字セットでのみサポートされる名前付きエンティティ (つまり、漢字はサポートされていません)        |
|オンプレミス リポジトリ    | ワークロードとしてサポートされていません|

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="for-further-information"></a>詳細については、次の情報を参照してください。
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [名前付きエンティティ (プレビュー) について説明します](named-entities-learn.md)。
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
