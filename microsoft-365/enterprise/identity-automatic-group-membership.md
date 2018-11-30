---
title: '手順 15: 動的グループ メンバーシップをセットアップする'
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
description: アカウントの属性に基づいた自動グループ メンバーシップについて理解し、構成します。
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869515"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>手順 15: 動的グループ メンバーシップをセットアップする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、ユーザー アカウントを Azure AD グループのメンバーとして自動的に追加または削除するための一連のルールを作成します。これは*動的グループ メンバーシップ* と呼ばれます。ルールはユーザー アカウントの属性 (部門や国など) に基づいています。

ルールの適用方法を次に説明します。

- 新しいユーザー アカウントがグループのすべてのルールに一致すると、そのアカウントはメンバーになります。
- ユーザー アカウントがグループのメンバーではないものの、その属性が変更されグループのすべてのルールに一致した場合は、そのグループのメンバーになります。
- ユーザー アカウントがグループのすべてのルールに一致しない場合、そのアカウントはグループに追加されません。
- ユーザー アカウントがグループのメンバーであるものの、その属性が変更されそのグループのすべてのルールに一致しなくなると、グループのメンバーではなくなります。

動的メンバーシップを使用するには、最初に共通のユーザー アカウント属性セットを持つ一連のグループを判別します。たとえば、Sales 部門のすべてのメンバーは、ユーザー アカウントの Department 属性が「Sales」に設定されていることに基づき、Sales Azure AD グループに入れます。

「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」を参照してください。

この手順の結果は次のとおりです。

- 動的メンバーシップを構成できる Azure AD グループのセット
- 各動的グループのルール セット

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-dyn-groups)を確認できます。

## <a name="next-step"></a>次の手順

[ID インフラストラクチャの終了条件](identity-exit-criteria.md)
