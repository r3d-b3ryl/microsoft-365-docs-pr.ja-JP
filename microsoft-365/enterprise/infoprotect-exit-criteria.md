---
title: 情報保護インフラストラクチャの終了条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 情報保護ベースのサービスとインフラストラクチャの条件を調べ、構成が Microsoft 365 Enterprise の要件を満たしていることを確認します。
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869527"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>情報保護インフラストラクチャの終了条件

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

基礎インフラストラクチャを完了する前に、情報保護インフラストラクチャが次の条件を満たしていることを確認します。 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必須: 組織のセキュリティおよび情報の保護レベルが定義されている

組織に必要なセキュリティ レベルを計画し、決定している。これらのレベルでは、機密情報とそれに伴う必須データ セキュリティの最小限のセキュリティ レベルと強化するための追加のレベルが定義されます。

少なくとも 3 種類のセキュリティ レベルを使用します。

- 基準
- 機密
- 高度な規制

必要に応じて、[手順 1](infoprotect-define-sec-infoprotect-levels.md) がこの必須条件を満たす上で役立ちます。 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>必須: Office 365 のセキュリティ強化が構成されている

「[セキュリティ強化のために Office 365 テナントを構成する](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)」の内容に基づいて、セキュリティの強化のために次の設定を構成している。

- Office 365 セキュリティ/コンプライアンス センターの脅威管理ポリシー
- その他の Exchange Online テナント レベルの設定
- SharePoint 管理センターでのテナント レベルでの共有ポリシー
- Azure Active Directory の設定

[Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton) も有効にしている。

必要に応じて、[手順 3](infoprotect-configure-increased-security-office-365.md) がこの必須条件を満たす上で役立ちます。 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>省略可能: 環境全体で分類方法が構成されている

法務/コンプライアンス チームと協力して、次のような、組織のデータの適切な分類方法とラベリング方法を策定している。

- 機密性の高いデータ タイプ
- Office 365 のラベル
- Azure Information Protection のラベル

必要に応じて、[手順 2](infoprotect-configure-classification.md) がこの必須条件を満たすのに役立ちます。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>省略可能: Office 365 での特権アクセス管理の構成。

お客様は、トピック「[Office 365 での特権アクセス管理の構成](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」での説明を使用して、Office 365 をお使いの組織で特権アクセスの有効化と特権アクセスポリシーの作成を行いました。こうしたポリシーを構成し、機密データへのアクセスまたは重要な構成設定へのアクセスのためにジャスト イン タイムアクセスを有効化しました。

必要に応じて、[手順 4](infoprotect-configure-privileged-access-management.md) がこの必須条件を満たす上で役立ちます。 

## <a name="next-step"></a>次の手順

これで、Microsoft Teams や Exchange Online など、Microsoft 365 Enterprise の基礎インフラストラクチャで稼働する[ワークロードとシナリオ](deploy-workloads.md)を展開する準備ができました。
