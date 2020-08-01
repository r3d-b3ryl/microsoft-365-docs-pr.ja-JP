---
title: 管理ポータルにアクセスする
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 420cdaabb607eacf0d7a7109827fe5437e2f999c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530225"
---
# <a name="access-the-admin-portal"></a>管理ポータルにアクセスする

Microsoft Managed Desktop service へのゲートウェイは、Microsoft [Azure portal](https://portal.azure.com)です。 Azure ポータルを使用してカスタマイズする方法の詳細については、「 [azure portal のドキュメント](https://docs.microsoft.com/azure/azure-portal/)」を参照してください。 プレビューでは、microsoft[エンドポイントマネージャー](https://endpoint.microsoft.com/)で Microsoft Managed Desktop を検索することもできます。 このポータルのデバイス管理の機能についてよく知らない場合は、 [Microsoft エンドポイントマネージャーのドキュメント](https://docs.microsoft.com/mem/)を参照してください。

管理アカウントには、Microsoft Managed Desktop 管理ポータルにアクセスするための特定のアクセス許可が必要です。 役割ベースのアクセス制御 (RBAC) を使用して、組織内のこれらの機能への管理者アクセスを管理することができます。 Azure Active Directory ロールの詳細については、「 [Azure Active directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。

アクセスを確実にするために、管理者ユーザーアカウントに次の役割のいずれかを割り当てます。

|Azure AD の役割  |Microsoft マネージドデスクトップのアクセス許可  |
|---------|---------|
|グローバル管理者     | この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対する**読み取りおよび書き込みアクセス許可**を持ちます。         |
|グローバル閲覧者     | この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対して**読み取り専用のアクセス許可**を持ちます。         |
|Intune サービス管理者     |  この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対する**読み取りおよび書き込みアクセス許可**を持ちます。       |
|サービスサポート管理者     | この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対する**読み取りおよび書き込みアクセス許可**を持ちます。         |

> [!IMPORTANT]
> グローバル管理者の役割のみが、Microsoft マネージドデスクトップに組織を*登録*するために必要なアクセス許可を持っています。 Azure Active Directory の役割によって、ユーザーアカウントにさまざまな Microsoft サービスの権限が付与されることに注意してください。 Microsoft マネージドデスクトップでの登録を完了した後は、他のタスクを実行するために必要な*最低限*の特権を持つ役割を常に使用する必要があります。

## <a name="assigning-roles-to-administrators"></a>管理者への役割の割り当て

Azure Active Directory の役割の割り当てに関するヘルプが必要な場合は、「 [Azure Active directory の管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。
