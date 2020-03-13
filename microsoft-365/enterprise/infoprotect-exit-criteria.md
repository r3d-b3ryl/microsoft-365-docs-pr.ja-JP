---
title: 情報保護インフラストラクチャの終了条件
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
description: 情報保護ベースのサービスとインフラストラクチャの条件を調べ、構成が Microsoft 365 Enterprise の要件を満たしていることを確認します。
ms.openlocfilehash: 28eff02ea870dcfca7e2e32580ed6a3a9e8a9484
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544166"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>情報保護インフラストラクチャの終了条件

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

情報保護インフラストラクチャが次の必須基準を満たすとともに、オプションの基準も考慮されていることをご確認ください。

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必須: 組織のセキュリティおよび情報の保護レベルが定義されている

組織に必要なセキュリティ レベルを計画し、決定している。これらのレベルでは、機密情報とそれに伴う必須データ セキュリティの最小限のセキュリティ レベルと強化するための追加のレベルが定義されます。

少なくとも 3 種類のセキュリティ レベルを使用します。

- 基準
- 機密
- 高度な規制

必要に応じて、[手順 1](infoprotect-define-sec-infoprotect-levels.md) がこの必須条件を満たす上で役立ちます。 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>必須: Microsoft 365 のセキュリティ強化が構成済み

次の [Office 365 セキュリティの強化](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)の設定が構成されています:

- Microsoft 365 セキュリティセンターの脅威管理ポリシー
- その他の Exchange Online テナント レベルの設定
- SharePoint Online 管理センターでのテナント全体の共有ポリシー
- Azure Active Directory (Azure AD) の設定

[SharePoint、OneDrive、Microsoft Teams 用の Office 365 Advanced Threat Protection (ATP) を有効にする](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)ことも行いました。

必要に応じて、[手順 3](infoprotect-configure-increased-security-office-365.md) がこの必須条件を満たす上で役立ちます。 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>省略可能: 環境全体で分類方法が構成されている

法務/コンプライアンス チームと協力して、組織のデータのガバナンスとセキュリティ ポリシーの適切な分類方法とラベリング方法を策定しています。 

これらのポリシーは、次の構成および展開に対応しています: 

- 機密性の高いデータ タイプ
- 保持ラベル
- 機密ラベル
- Azure Information Protection のラベル

必要に応じて、[手順 2](infoprotect-configure-classification.md) がこの必須条件を満たすのに役立ちます。 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>オプション: 環境全体に Windows Information Protection が展開されている

登録されている Windows 10 Enterprise デバイスには、次の項目を定義する Intune ポリシーが展開および適用されています。

- 保護するアプリ。
- 保護レベル。
- 保護の範囲。

必要に応じて、[手順 4](infoprotect-deploy-windows-information-protection.md) がこの必須条件を満たす上で役立ちます。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>オプション: Office 365 データ損失防止 (DLP) が展開されている

顧客やその他の種類の非公開データを保護し、業界や地域の規制や要件を順守するために組織が必要とする一連の DLP ポリシー (場所や規則、条件やアクションを含む) を分析し、テストしてから展開しました。

データ コンプライアンスとセキュリティ スタッフは、Office 365 のセキュリティとコンプライアンスのダッシュボードを使用して DLP インシデントを監視しています。

必要に応じて、[手順 5](infoprotect-data-loss-prevention.md) がこの必須条件を満たす上で役立ちます。 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>省略可能: 電子メールの暗号化が構成されている

必要に応じて、組織に次の電子メールの暗号化を構成しています。

|||
|:-------|:-----|
| **暗号化方法** | **送信した電子メール関連** |
| [Office 365 Message Encryption (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | 暗号化を使用する組織外 |
| [Information Rights Management (IRM)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | 暗号化とアクセス許可の両方とも |
| [Secure/Multipurpose Internet Mail Extensions (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | 公開キー暗号を使用する暗号化とデジタル署名の両方とも |
|||

必要な場合、[手順 6](infoprotect-email-encryption.md) がこの必須条件を満たす上で役立ちます。

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>省略可能: Office 365 での特権アクセス管理の構成。

[Office 365 での特権アクセス管理を設定する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)トピックにある情報を使用して、特権アクセスを有効にし、組織内に 1 つまたは複数の特権アクセス ポリシーを作成しました。 これらのポリシーを構成して、機密データへのアクセスや重要な構成設定へのアクセスのために just-in-time アクセスが有効にされました。

必要に応じて、[手順 7](infoprotect-configure-privileged-access-management.md) がこの必須条件を満たすのに役立ちます。 

## <a name="results-and-next-steps"></a>結果と次の手順

Microsoft 365 Enterprise の情報保護インフラストラクチャでは、定義されたセキュリティ レベル、Office 365 のセキュリティ強化、機密データの種類とラベルを使用した分類、Windows 情報保護、データ損失防止、電子メールの暗号化、および特権アクセスの管理が使用されます。

Microsoft 365 Enterprise のエンド ツー エンドの展開に従っている場合、[ワークロードとシナリオ](deploy-workloads.md)で基盤インフラストラクチャのすべての機能と構成を活用することができます。
