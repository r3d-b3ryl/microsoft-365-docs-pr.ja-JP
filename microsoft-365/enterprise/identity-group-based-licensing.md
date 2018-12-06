---
title: '手順 12: 自動ライセンスをセットアップする'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD グループのグループベースのライセンスについて理解し、構成します。
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868981"
---
# <a name="step-12-set-up-automatic-licensing"></a>手順 12: 自動ライセンスをセットアップする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、一連のサブスクリプションのライセンスをグループのすべてのメンバーに自動的に割り当てるため、Azure AD でセキュリティ グループを構成します。これは*グループベースのライセンス* と呼ばれます。グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。

Microsoft 365 Enterprise では、次の両方のライセンスを割り当てる Azure AD セキュリティ グループを構成します。

- Office 365 Enterprise E3 または E5
- Enterprise Mobility + Security (EMS) E3 または E5

手順 2 で指定したグループを使用して、グループ内のすべてのユーザーに Office 365 と EMS の両方のライセンスが割り当てられている必要があるアカウントのリストが含まれているグループを検索します。すべてのグループ メンバーに割り当てることができる十分な数のライセンスがあることを確認します。ライセンスが不足すると、ライセンスが使用可能になるまで、新しいユーザーにライセンスが割り当てらません。

>[!Note]
>Azure B2B (企業間) アカウントが含まれているグループに対しては*グループベースのライセンス*を構成しないでください。
>

「[Azure Active Directory のグループベースのライセンスの基礎](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)」にある追加情報を参照してください。

「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」を参照してください。

この手順の結果は次のとおりです。

- グループベースのライセンスに適したセキュリティ グループを特定している。
- グループベースのライセンスに対応してこれらのグループを構成している。

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-group-license)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [テナントとサインイン アクティビティを監視する](identity-azure-ad-access-usage-reporting.md) |

