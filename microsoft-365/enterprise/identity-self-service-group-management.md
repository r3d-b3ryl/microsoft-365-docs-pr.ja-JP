---
title: '手順 14: ユーザーが各自のグループを作成および管理できるようにする'
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
description: Azure AD のセルフ サービスによるグループ管理について理解し、構成します。
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869328"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>手順 14: ユーザーが各自のグループを作成および管理できるようにする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、IT 管理者ではなくグループの所有者が管理できる Azure Active Directory (AD) グループを指定します。*セルフ サービスによるグループ管理*と呼ばれるこの機能では、管理者ロールが割り当てられていないグループ所有者がセキュリティ グループを作成および管理できるようになります。 

ユーザーがセキュリティ グループのメンバーシップを要求できます。この要求は IT 管理者ではなくグループ所有者に送られます。これにより、グループ メンバーシップの日常的な管理が、業務でのグループの用途を理解してグループのメンバーシップを管理できるチーム所有者、プロジェクト所有者、またはビジネス所有者に委任されます。

>[!Note]
>セルフサービスによるグループ管理は、Azure AD セキュリティと Office 365 のグループでのみ使用できます。メール対応グループ、配布リスト、またはオンプレミス Windows Server Active Directory (AD) から同期されているグループには使用できません。
>

詳細については、「[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)」を参照してください。

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-self-service-groups)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [動的グループ メンバーシップをセットアップする](identity-automatic-group-membership.md) |
