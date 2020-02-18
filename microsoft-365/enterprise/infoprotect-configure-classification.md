---
title: '手順 2: 環境の分類を構成する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 組織内のデータを分類するさまざまな方法について理解し、構成します。
ms.openlocfilehash: e8c40ca4c419edc2d59a060dfd4fe8918cf4e784
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067254"
---
# <a name="step-2-configure-classification-for-your-environment"></a>手順 2: 環境の分類を構成する

*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

この手順では、法務/コンプライアンス チームと連携して組織のデータの分類方法を定義します。

## <a name="microsoft-365-classification-types"></a>Microsoft 365 の分類の種類

Microsoft 365 には、次の 4 種類の分類方法があります。

- 機密情報の種類
- 保持ラベル
- 機密ラベル
- Azure Information Protection のラベルと保護

### <a name="sensitive-information-types"></a>機密情報の種類

Microsoft 365 の機密情報の種類は、検索などの自動化されたプロセスが特定の情報の種類を認識する方法を定義します。 この中には医療サービス番号やクレジット カード番号といった機密性の高い従業員または顧客データが含まれます。 機密情報の種類を使用して、機密データを検索し、データ損失防止 (DLP) ルールおよびポリシーを適用してこのデータを保護します。 詳細については、[DLP ポリシーの内容](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains)を参照してください。 

機密情報の種類は、一般データ保護規制 (GDPR) のようなコンプライアンスや規制の要件を満たすために特に便利です。

### <a name="retention-labels"></a>保持ラベル

データ ガバナンス戦略の定義の一部は組織のポリシーと地域の規制に準拠して特定の種類のドキュメントまたは特定のコンテンツのドキュメントを保持する期間を決定することです。 たとえば、一部の種類のドキュメントは一定の時間を保持した後で削除する必要があり、別の種類のドキュメントは無期限に保持する必要があります。

Microsoft 365 で保存されるドキュメントに関しては、Exchange メールに保存されるドキュメントおよびデータ、SharePoint Online、OneDrive for Business、Teams チャット、チャネル メッセージに保持ラベルを定義して適用します。 

保持ラベルを使用する場合、保持ポリシーを適用する必要があるファイルの各カテゴリのラベルを設定する必要があります。 保持ラベル内に以下の項目を指定できます。

- ファイルの記述子のセット (たとえば、ビジネス部門、ファイルのカテゴリ、または規制別)。
- 保持する時間と保持する時間に到達した後の処理など、保持ラベルが添付されたファイルの保存設定。

SharePoint Online サイトを設定することにより保持ラベルをファイルに自動適用し、サイト内のすべての新しいドキュメントに既定の保持ラベルを適用することもできます。 

詳細については、「[保持ラベルの概要](https://docs.microsoft.com/office365/securitycompliance/labels)」をご覧ください。

### <a name="sensitivity-labels"></a>機密ラベル

特定の種類のドキュメントまたは特定のコンテンツのドキュメントに対するセキュリティの保護と実装の一部は、追加のセキュリティを適用できるようにラベルを使用してマークすることです。 Microsoft 365 の機密ラベルを使用して次のことができます。

- 暗号化、アクセス許可、または透かしの追加といった保護設定を強制適用する。
- Windows Information Protection (WIP) Endpoint Protection を使用して、そのコンテンツがサード パーティ製アプリ (Twitter や Gmail など)、またはリムーバブル記憶域 (USB ドライブなど) にコピーされることを防止する。
- Microsoft Cloud App Security (CAS) を使用してサード パーティ製アプリおよびサービスのコンテンツを保護する。 
- 保護設定を使わずにコンテンツを分類する。

機密ラベルを使用する場合、セキュリティと情報保護レベルごとにラベルを構成する必要があります。 たとえばの以下の 3 つの機密ラベルを作成します。

- 基準
- 機密
- 厳しく規制

SharePoint Online サイトに高度に規制されたデータを含むファイルを保存し、ファイルがサイトから離れる際にそれらのファイルにサイトと同じ権限を持たせるには、サイトと同じ権限を持つ追加の機密ラベルを作成する必要があります。

詳細については、こちらの「[機密ラベルの概要](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels)」をご覧ください。

### <a name="azure-information-protection-labels-and-protection"></a>Azure Information Protection のラベルと保護

Azure Information Protection ラベルを使用して、組織のドキュメントとメールを分類し、必要に応じて保護できます。 これらのラベルは、Microsoft 365 の外部に保存されているドキュメントに適用できます。 これらのラベルは、ルールと条件を定義する管理者が自動で適用するか、ユーザーが手動で適用するか、それらを組み合わせユーザーに推奨事項が提示されて適用できます。

Azure Information Protection のラベルと保護を計画および展開するには、次の手順を実行します。

1. [Azure Information Protection の要件](https://docs.microsoft.com/information-protection/get-started/requirements)を確認します。
2. 「[分類、ラベル付け、保護のデプロイ ロードマップ](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)」に従います。

詳細については、「[Azure Information Protection のドキュメント](https://docs.microsoft.com/information-protection/)」を参照してください。

既存の Azure Information Protection ラベルは機密ラベルとシームレスに連動します。 たとえば、既存の Azure Information Protection ラベルとドキュメントとメールに適用されるラベルを保持できます。

機密ラベルと Azure Information Protection ラベルの両方がある場合、[Azure Information Protection ラベルを機密ラベルに移行する](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels)必要があります。

## <a name="example-classification-for-gdpr"></a>例: GDPR の分類

GDPR の個人データを含む分類スキーマの例については、「[個人データの分類スキーマを設計する](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)」を参照してください。

## <a name="take-it-for-a-test-drive"></a>体験してみる

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: データの分類](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step2)を確認してください。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 3](../media/stepnumbers/Step3.png)|[Office 365 のセキュリティ強化を構成する](infoprotect-configure-increased-security-office-365.md)|

