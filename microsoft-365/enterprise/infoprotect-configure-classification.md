---
title: '手順 2: 環境の分類を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 組織内のデータを分類するさまざまな方法について理解し、構成します。
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869197"
---
# <a name="step-2-configure-classification-for-your-environment"></a>手順 2: 環境の分類を構成する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

この手順では、法務/コンプライアンス チームと連携して組織のデータの分類方法を定義します。

## <a name="microsoft-classifications"></a>Microsoft の分類方法

Microsoft 365 には、次の 3 種類の分類方法があります。

- Office 365 の機密情報タイプ
- Office 365 のラベル
- Azure Information Protection のラベルと保護

### <a name="sensitive-information-types-for-office-365"></a>Office 365 の機密情報タイプ

Office 365 の機密情報タイプでは、検索などの自動プロセスで特定の種類の情報 (医療サービス番号、クレジットカード番号など) を認識する方法が定義されます。機密情報タイプを使用して、機密データを検出し、データ損失防止ルールおよびポリシーを適用してこのデータを保護します。詳細については、「[データ損失防止ポリシーの概要](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)」を参照してください。たとえば、機密情報タイプは、一般データ保護規則 (GDPR) などのコンプライアンスや規制の要件に準拠する際に特に役立ちます。

### <a name="office-365-labels"></a>Office 365 のラベル
個人データや、SharePoint Online と OneDrive for Business に保存されている高度な規制を実施する企業秘密ファイルには、Office 365 のラベルを使用できます。ラベルの作成方法などの詳細については、「[ラベルの概要](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)」を参照してください。

Office 365 のラベルを使用する場合は、保護レベルごとに 1 つ以上のラベルを構成する必要があります。たとえば、以下の 3 種類のラベルを作成します。

- 基準
- 機密
- 高度な規制

### <a name="azure-information-protection-labels-and-protection"></a>Azure Information Protection のラベルと保護

Azure Information Protection のラベルを使用して、組織内の文書やメールを分類し、オプションで保護できます。これらのラベルは、Office 365 外部に保存されている文書にも適用できます。管理者がルールや条件を定義してラベルを自動的に適用するか、ユーザーがラベルを手動で適用するか、あるいは推奨される場合はこれらを組み合わせて適用できます。

Azure Information Protection のラベルと保護を計画および展開するには、次の手順を実行します。

1. [Azure Information Protection の要件](https://docs.microsoft.com/information-protection/get-started/requirements)を確認します。
2. 「[分類、ラベル付け、保護のデプロイ ロードマップ](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)」に従います。

詳細については、「[Azure Information Protection のドキュメント](https://docs.microsoft.com/information-protection/)」を参照してください。

## <a name="classification-for-gdpr"></a>GDPR の分類

GDPR の個人データを含む分類方法の例については、「[個人データの分類スキーマを設計する](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: データの分類](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step3)を確認してください。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Office 365 のセキュリティ強化を構成する](infoprotect-configure-increased-security-office-365.md)|

