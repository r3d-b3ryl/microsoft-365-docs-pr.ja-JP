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
ms.openlocfilehash: a619a6ff5256b3b70302d1bef4f0bc21bd7ac3e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927908"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Azure Active Directory グローバル ロールを使用して Microsoft 365 Defender へのアクセスを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender へのアクセスを管理するには、2 つの方法があります。
- **グローバル Azure Active Directory (AD) ロール**
- **カスタム ロール アクセス**

次のグローバル **Azure Active Directory (AD)** ロールが割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。
- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

これらのロールを持つアカウントを確認するには、[Microsoft 365 セキュリティ センターで権限を表示](https://security.microsoft.com/permissions)します。

**カスタム ロール アクセス** は、Microsoft 365 Defender の新機能であり、Microsoft Defender 365 の特定のデータ、タスク、および機能へのアクセスを管理できます。 カスタム ロールは、グローバル Azure ADロールよりも多くの制御を提供し、必要な最小限の役割で必要なアクセスのみをユーザーに提供します。  カスタム ロールは、グローバル Azure ロールとカスタム ロールにADできます。 [カスタム ロールの詳細を参照してください](custom-roles.md)。

> ![メモ]この記事は、グローバル Azure Active Directory ロールの管理にのみ適用されます。 カスタムの役割ベースのアクセス制御の使用の詳細については、「役割ベースのアクセス制御のカスタム [ロール」を参照してください。](custom-roles.md)

## <a name="access-to-functionality"></a>機能へのアクセス
特定の機能へのアクセスは、[Azure AD でのロール](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)によって決まります。 ユーザーまたはユーザー グループに新しい役割を割り当てる必要がある場合は、グローバル管理者にお問い合わせください。

### <a name="approve-pending-automated-tasks"></a>保留中の自動化タスクを承認する
「[調査と修復の自動化](mtp-autoir-actions.md)」 は、調査中に見つかったメール、転送ルール、ファイル、持続性機構など、その他の成果物に対処できます。 明示的な承認が必要な保留中のアクションを承認または拒否するには、Microsoft 365 に特定の役割が割り当てられている必要があります。 詳細については、「[アクションセンターの権限](mtp-action-center.md#required-permissions-for-action-center-tasks)」をご覧ください。

## <a name="access-to-data"></a>データへのアクセス
Microsoft 365 Defender データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) のユーザー グループに割り当てられたスコープを使用して制御できます。 Defender for Endpoint の特定のデバイス セットにアクセスできない場合は、Microsoft 365 Defender のデータにフル アクセスできます。 ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。

たとえば、Microsoft Defender for Endpoint の役割を持つ 1 つのユーザー グループにのみ属し、そのユーザー グループに販売デバイスへのアクセス権が与えられた場合、Microsoft 365 Defender の販売デバイスに関するデータだけが表示されます。 [Microsoft Defender for Endpoint の RBAC 設定の詳細](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security のアクセス制御
プレビュー中、Microsoft 365 Defender は Cloud App Security 設定に基づいてアクセス制御を適用しない。 Microsoft 365 Defender データへのアクセスは、これらの設定の影響を受け取る必要があります。

## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defender の役割ベースのアクセス制御のカスタム ロール](custom-roles.md)
- [Azure AD ロール](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [エンドポイント RBAC 用 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security roles](/cloud-app-security/manage-admins)