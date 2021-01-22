---
title: Microsoft 365 セキュリティ センターで Microsoft 365 Defender データへのアクセスを管理する
description: Microsoft 365 Defender でデータへのアクセス許可を管理する方法について説明します。
keywords: アクセス、アクセス許可、MTP、Microsoft Threat Protection、M365、セキュリティ、MCAS、MDATP、Cloud App Security、Microsoft Defender Advanced Threat Protection、スコープ、スコーピング、RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930140"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Microsoft 365 Defender へのアクセスを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

次の Azure Active Directory (AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。
- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

これらのロールを持つアカウントを確認するには、[Microsoft 365 セキュリティ センターで権限を表示](https://security.microsoft.com/permissions)します。

## <a name="access-to-functionality"></a>機能へのアクセス
特定の機能へのアクセスは、[Azure AD でのロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)によって決まります。 ユーザーまたはユーザー グループに新しい役割を割り当てる必要がある場合は、グローバル管理者にお問い合わせください。

### <a name="approve-pending-automated-tasks"></a>保留中の自動化タスクを承認する
「[調査と修復の自動化](mtp-autoir-actions.md)」 は、調査中に見つかったメール、転送ルール、ファイル、持続性機構など、その他の成果物に対処できます。 明示的な承認が必要な保留中のアクションを承認または拒否するには、Microsoft 365 に特定の役割が割り当てられている必要があります。 詳細については、「[アクションセンターの権限](mtp-action-center.md#required-permissions-for-action-center-tasks)」をご覧ください。

## <a name="access-to-data"></a>データへのアクセス
Microsoft 365 Defender データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) のユーザー グループに割り当てられたスコープを使用して制御できます。 エンドポイント用 Defender の特定のデバイス セットにアクセスのスコープが設定されていない場合は、Microsoft 365 Defender のデータにフル アクセスできます。 ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。

たとえば、Microsoft Defender for Endpoint の役割を持つ 1 つのユーザー グループにのみ属し、そのユーザー グループに販売デバイスへのアクセス権だけが与えられた場合、Microsoft 365 Defender の販売デバイスに関するデータだけが表示されます。 [Microsoft Defender for Endpoint の RBAC 設定の詳細](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security のアクセス制御
プレビュー中、Microsoft 365 Defender は Cloud App Security の設定に基づいてアクセス制御を適用します。 Microsoft 365 Defender データへのアクセスは、これらの設定の影響を受け取る必要があります。

## <a name="related-topics"></a>関連項目

- [Azure AD ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender for Endpoint RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security roles](https://docs.microsoft.com/cloud-app-security/manage-admins)
