---
title: Microsoft 365 セキュリティ センターで Microsoft Threat Protection データへのアクセスを管理する
description: Microsoft Threat Protection でデータへのアクセス許可を管理する方法について説明します。
keywords: アクセス、アクセス許可、MTP、Microsoft Threat Protection、M365、セキュリティ、MCAS、MDATP、Cloud App Security、Microsoft Defender Advanced Threat Protection、スコープ、スコーピング、RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: ca9d6320d7ba13b2af4200e5f270c9480d8336fd
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808572"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Microsoft Threat Protection へのアクセスを管理する

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

次の Azure Active Directory (AD) のロールが割り当てられているアカウントは、Microsoft Threat Protection の機能とデータにアクセスできます。
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
Microsoft Threat Protection のデータへのアクセスは、Microsoft Defender ATP の役割ベースのアクセス制御 (RBAC) でユーザーグループに割り当てらているスコープを使用して制御できます。 アクセスが Microsoft Defender ATP の特定のデバイス セットに限定されていない場合は、Microsoft Threat Protection のデータにフル アクセスできます。 ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。

たとえば、Microsoft Defender ATP ロールが割り当てられている 1 つのユーザー グループのみに属していて、そのユーザーグループに販売デバイスのみへのアクセス権が付与されている場合は、Microsoft Threat Protection には販売デバイスに関するデータのみが表示されます。 [Microsoft Defender ATP の RBAC 設定についての詳細情報を参照します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security のアクセス制御
プレビュー中、Microsoft Threat Protection は、クラウド アプリのセキュリティ設定に基づくアクセス制御を適用しません。 これらの設定は、Microsoft Threat Protection のデータへのアクセスに影響しません。

## <a name="related-topics"></a>関連項目

- [Azure AD ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender ATP RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security roles](https://docs.microsoft.com/cloud-app-security/manage-admins)