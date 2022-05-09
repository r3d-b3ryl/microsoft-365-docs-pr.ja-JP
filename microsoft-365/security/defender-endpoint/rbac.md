---
title: ロールベースのアクセス制御を使用して、Microsoft 365 Defender ポータルへのきめ細かなアクセスを許可する
description: セキュリティ操作内にロールとグループを作成して、ポータルへのアクセスを許可します。
keywords: rbac, role, based, access, control, groups, control, tier, aad
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8c1ff743aa6c9c215c3894185a4096c9a35a16e0
ms.sourcegitcommit: 6b24f65c987e5ca06e6d5f4fc10804cdbe68b034
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2021
ms.locfileid: "61320829"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>ロールベースのアクセス制御を使用してポータル アクセスを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Azure Active Directory
- Office 365

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

ロールベースのアクセス制御 (RBAC) を使用して、セキュリティ運用チーム内にロールとグループを作成して、ポータルへの適切なアクセスを許可できます。 作成するロールとグループに基づいて、ポータルにアクセスできるユーザーが表示および実行できる操作をきめ細かく制御できます。 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bJ2a]

大規模な geo 分散セキュリティ運用チームは、通常、セキュリティ ポータルへのアクセスを割り当て、承認するための階層ベースのモデルを採用します。 一般的なレベルには、次の 3 つのレベルがあります。

階層|説明|
:---|:---|
階層 1|**ローカル セキュリティ運用チーム / IT チーム** <br> このチームは通常、位置情報に含まれるアラートをトリアージして調査し、アクティブな修復が必要な場合は階層 2 にエスカレートします。|
階層 2|**地域のセキュリティ運用チーム** <br> このチームは、リージョンのすべてのデバイスを表示し、修復アクションを実行できます。|
階層 3|**グローバル セキュリティ運用チーム** <br> このチームは、セキュリティの専門家で構成され、ポータルからのすべてのアクションを表示および実行する権限が与えられます。|

> [!NOTE]
> レベル 0 資産については、セキュリティ管理者向けの[Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-configure)を参照して、Microsoft Defender for EndpointとMicrosoft 365 Defenderをより細かく制御します。  

Defender for Endpoint RBAC は、選択した階層ベースまたはロールベースのモデルをサポートするように設計されており、表示できるロール、アクセスできるデバイス、実行できるアクションをきめ細かく制御できます。 RBAC フレームワークは、次のコントロールを中心にしています。

- **特定のアクションを実行できるユーザーを制御する**
  - カスタム ロールを作成し、きめ細かくアクセスできる Defender for Endpoint 機能を制御します。
- **特定のデバイス グループまたはグループに関する情報を表示できるユーザーを制御する**
  - 名前、タグ、ドメインなどの特定の条件で[デバイス グループを作成](machine-groups.md)し、特定のAzure Active Directory (Azure AD) ユーザー グループを使用して、デバイス グループへのロール アクセスを許可します。

ロールベースのアクセスを実装するには、管理者ロールを定義し、対応するアクセス許可を割り当て、ロールに割り当てられたユーザー グループAzure AD割り当てる必要があります。

### <a name="before-you-begin"></a>開始する前に

RBAC を使用する前に、アクセス許可を付与できるロールと RBAC を有効にした結果を理解しておくことが重要です。

> [!WARNING]
> この機能を有効にする前に、Azure ADにグローバル管理者ロールまたはセキュリティ管理者ロールがあり、Azure AD グループを用意して、ポータルからロックアウトされるリスクを軽減することが重要です。 

Microsoft 365 Defender ポータルに初めてログインすると、フル アクセスまたは読み取り専用アクセスが付与されます。 フル アクセス権は、Azure ADのセキュリティ管理者またはグローバル管理者ロールを持つユーザーに付与されます。 読み取り専用アクセス権は、Azure ADのセキュリティ 閲覧者ロールを持つユーザーに付与されます。 

Defender for Endpoint グローバル管理者 ロールを持つユーザーは、デバイス グループの関連付けとAzure ADユーザー グループの割り当てに関係なく、すべてのデバイスに無制限にアクセスできます。

> [!WARNING]
> 最初は、グローバル管理者またはセキュリティ管理者権限Azure AD持つユーザーのみが、Microsoft 365 Defender ポータルでロールを作成および割り当てることができるため、適切なグループをAzure ADで準備しておくことが重要です。
>
> **ロールベースのアクセス制御を有効にすると、読み取り専用アクセス許可を持つユーザー (Azure ADセキュリティ リーダー ロールに割り当てられたユーザーなど) は、ロールに割り当てられるまでアクセスできなくなります。** 
>
>管理者アクセス許可を持つユーザーには、完全なアクセス許可を持つ既定の組み込みの Defender for Endpoint グローバル管理者ロールが自動的に割り当てられます。 RBAC の使用をオプトインした後、グローバル管理者またはセキュリティ管理者にAzure ADされていない追加のユーザーを Defender for Endpoint グローバル管理者ロールに割り当てることができます。 
>
> RBAC の使用をオプトインした後は、ポータルに初めてログインしたときのように初期ロールに戻すことはできません。

## <a name="related-topic"></a>関連トピック

- [RBAC ロール](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [Microsoft Defender for Endpointでデバイス グループを作成および管理する](machine-groups.md)
