---
title: ユーザー アクセスをユーザー に割り当Microsoft Defender セキュリティ センター
description: Microsoft Defender for Endpoint ポータルへの読み取りおよび書き込みまたは読み取り専用アクセスを割り当てる。
keywords: ユーザー ロールの割り当て、読み取りおよび書き込みアクセスの割り当て、読み取り専用アクセスの割り当て、ユーザー、ユーザー の役割、役割
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 3cb6aaecd0578af26baf00aa34edbba37d6835fe
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648413"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>ユーザー アクセスをユーザー に割り当Microsoft Defender セキュリティ センター

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- Azure Active Directory
- Office 365
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint では、アクセス許可を管理する 2 つの方法がサポートされています。

- **基本的なアクセス許可の管理**: アクセス許可をフル アクセスまたは読み取り専用に設定します。
- **役割ベースのアクセス制御 (RBAC)**: 役割を定義し、Azure AD ユーザー グループをロールに割り当て、ユーザー グループにデバイス グループへのアクセス権を付与することで、詳細なアクセス許可を設定します。 RBAC の詳細については、「役割ベースのアクセス [制御を使用してポータル アクセスを管理する」を参照してください](rbac.md)。

> [!NOTE]
> 基本的なアクセス許可が既に割り当てられている場合は、いつでも RBAC に切り替えられます。 スイッチを作成する前に、次の点を考慮してください。
> 
> - フル アクセスを持つユーザー (Azure AD のグローバル管理者またはセキュリティ管理者ディレクトリ ロールが割り当てられているユーザー) には、既定の Defender for Endpoint 管理者ロールが自動的に割り当てられます。また、フル アクセス権も持っています。 RBAC に切りAD後、追加の Azure ユーザー グループを Defender for Endpoint 管理者ロールに割り当てることができます。  Defender for Endpoint 管理者ロールに割り当てられたユーザーだけが、RBAC を使用してアクセス許可を管理できます。 
> - 読み取り専用アクセス権 (Security Readers) を持つユーザーは、役割が割り当てられるまでポータルへのアクセスを失います。 RBAC の下で役割AD割り当てできるのは Azure ユーザー グループのみです。
> - RBAC に切り替えても、基本的なアクセス許可管理を使用して切り替えすることはできません。

## <a name="related-topics"></a>関連項目

- [基本的なアクセス許可を使用してポータルにアクセスする](basic-permissions.md)
- [RBAC を使用してポータル アクセスを管理する](rbac.md)
