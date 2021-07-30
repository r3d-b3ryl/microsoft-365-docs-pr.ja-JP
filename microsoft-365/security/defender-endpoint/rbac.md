---
title: 役割ベースのアクセス制御を使用して、ポータルへのきめ細かなアクセスMicrosoft 365 Defenderする
description: セキュリティ操作内に役割とグループを作成して、ポータルへのアクセスを許可します。
keywords: rbac、 role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3c97151adac40e457439e07c1cb1c7dbcc84632
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53652709"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>役割ベースのアクセス制御を使用してポータル アクセスを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Azure Active Directory
- Office 365

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

役割ベースのアクセス制御 (RBAC) を使用して、セキュリティ運用チーム内に役割とグループを作成して、ポータルへの適切なアクセスを許可できます。 作成する役割とグループに基づいて、ポータルにアクセスできるユーザーが表示および実行できる操作を詳細に制御できます。 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bJ2a]

大規模な地域分散セキュリティ運用チームは、通常、階層ベースのモデルを採用して、セキュリティ ポータルへのアクセスを割り当て、承認します。 一般的な層には、次の 3 つのレベルがあります。

階層|説明
:---|:---
階層 1|**ローカル セキュリティ運用チーム / IT チーム** <br> このチームは通常、地理的位置内に含まれるアラートをトリアージして調査し、アクティブな修復が必要な場合は階層 2 にエスカレートします。
階層 2|**地域のセキュリティ運用チーム** <br> このチームは、地域のすべてのデバイスを表示し、修復アクションを実行できます。
階層 3|**グローバル セキュリティ運用チーム** <br> このチームはセキュリティ専門家で構成され、ポータルからすべてのアクションを表示して実行する権限があります。

Defender for Endpoint RBAC は、階層ベースまたは役割ベースの選択モデルをサポートするように設計され、表示できる役割、アクセスできるデバイス、実行できるアクションを詳細に制御できます。 RBAC フレームワークは、次のコントロールを中心にしています。

- **特定のアクションを実行できるユーザーを制御する**
  - カスタム ロールを作成し、詳細にアクセスできる Defender for Endpoint 機能を制御します。
- **特定のデバイス グループまたはグループに関する情報を表示できるユーザーを制御する**
  - [名前、タグ](machine-groups.md)、ドメインなど、特定の条件でデバイス グループを作成し、特定の Azure Active Directory (Azure AD) ユーザー グループを使用して、そのグループにロール アクセス権を付与します。

役割ベースのアクセスを実装するには、管理者ロールを定義し、対応するアクセス許可を割り当て、役割に割り当てられた Azure ADグループを割り当てる必要があります。

### <a name="before-you-begin"></a>はじめに

RBAC を使用する前に、アクセス許可を付与できる役割と RBAC をオンにした結果を理解することが重要です。

> [!WARNING]
> 機能を有効にする前に、Azure AD でグローバル管理者の役割またはセキュリティ管理者の役割を持ち、ポータルからロックアウトされるリスクを軽減するために Azure AD グループを準備することが重要です。 

ポータルに最初にログインするとMicrosoft 365 Defenderアクセス権または読み取り専用アクセス権が付与されます。 Azure 管理者のセキュリティ管理者またはグローバル管理者の役割を持つユーザーには、完全なアクセス権AD。 読み取り専用アクセスは、Azure のセキュリティ リーダー ロールを持つユーザーに付与AD。 

Defender for Endpoint Global 管理者の役割を持つユーザーは、デバイス グループの関連付けと Azure AD グループの割り当てに関係なく、すべてのデバイスに無制限にアクセスできます。

> [!WARNING]
> 最初は、Azure AD グローバル管理者またはセキュリティ管理者の権限を持つユーザーだけが、Microsoft 365 Defender ポータルで役割を作成して割り当てることができます。そのため、Azure AD で適切なグループを準備することが重要です。
>
> **ロール ベースのアクセス制御を有効にすると、読み取り専用アクセス許可を持つユーザー (たとえば、Azure AD セキュリティ リーダー ロールに割り当てられたユーザー) は、ロールに割り当てられるまでアクセス権を失います。** 
>
>管理者アクセス許可を持つユーザーには、完全なアクセス許可を持つ既定の組み込みの Defender for Endpoint グローバル管理者ロールが自動的に割り当てられます。 RBAC の使用をオプトインした後、Azure AD グローバル管理者またはセキュリティ管理者ではない追加のユーザーを Defender for Endpoint グローバル管理者ロールに割り当てることができます。 
>
> RBAC の使用をオプトインした後は、最初にポータルにログインした場合と同様に、最初の役割に戻す必要があります。

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Endpoint でデバイス グループを作成および管理する](machine-groups.md)
