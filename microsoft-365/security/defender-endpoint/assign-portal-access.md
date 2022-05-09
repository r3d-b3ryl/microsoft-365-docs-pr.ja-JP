---
title: Microsoft Defender セキュリティ センターにユーザー アクセスを割り当てる
description: Microsoft Defender for Endpoint ポータルに読み取りおよび書き込みまたは読み取り専用アクセス権を割り当てます。
keywords: ユーザー ロールの割り当て、読み取りおよび書き込みアクセスの割り当て、読み取り専用アクセスの割り当て、ユーザー、ユーザー ロール、ロール
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: fa0157a37cf25efcdcf1b578473b4dc2f6deb10d
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166964"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Microsoft Defender セキュリティ センターにユーザー アクセスを割り当てる

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- Azure Active Directory
- Office 365
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint では、アクセス許可を管理する 2 つの方法がサポートされています。

- **基本的なアクセス許可管理**: アクセス許可をフル アクセスまたは読み取り専用に設定します。
- **ロールベースのアクセス制御 (RBAC)**: ロールを定義し、Azure ADユーザー グループをロールに割り当て、ユーザー グループにデバイス グループへのアクセス権を付与することで、きめ細かなアクセス許可を設定します。 RBAC の詳細については、「 [ロールベースのアクセス制御を使用したポータル アクセスの管理](rbac.md)」を参照してください。

> [!NOTE]
> 基本的なアクセス許可が既に割り当てられている場合は、いつでも RBAC に切り替えることができます。 切り替えを行う前に、次のことを検討してください。
>
> - フル アクセス権を持つユーザー (Azure ADでグローバル管理者またはセキュリティ管理者ディレクトリ ロールが割り当てられているユーザー) には、既定の Defender for Endpoint 管理者ロールが自動的に割り当てられます。また、フル アクセス権も持ちます。 RBAC に切り替えた後、追加のAzure ADユーザー グループを Defender for Endpoint 管理者ロールに割り当てることができます。 RBAC を使用してアクセス許可を管理できるのは、Defender for Endpoint 管理者ロールに割り当てられたユーザーだけです。 
> - 読み取り専用アクセス権 (Security Reader) を持つユーザーは、ロールが割り当てられるまでポータルにアクセスできなくなります。 RBAC でロールを割り当てることができるのはAzure ADユーザー グループのみです。
> - RBAC に切り替えた後は、基本的なアクセス許可管理を使用するように切り替えることができません。

## <a name="related-topics"></a>関連項目

- [基本的なアクセス許可を使用してポータルにアクセスする](basic-permissions.md)
- [RBAC を使用してポータル アクセスを管理する](rbac.md)
