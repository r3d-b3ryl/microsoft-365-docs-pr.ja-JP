---
title: ポータルでMicrosoft 365 DefenderデータへのアクセスをMicrosoft 365 Defenderする
description: データに対するアクセス許可を管理する方法については、Microsoft 365 Defender
keywords: Access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7a4176e5b375c32edb1e1fae3ab74f0760f28366
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189211"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>グローバル ロールを使用Microsoft 365 DefenderアクセスAzure Active Directory管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

ユーザーへのアクセスを管理する方法は 2 Microsoft 365 Defender
- **グローバル Azure Active Directory (AD) の役割**
- **カスタム ロール アクセス**

次のグローバル ユーザー **(Azure Active Directory) AD割** り当てられたアカウントは、Microsoft 365 Defender機能とデータにアクセスできます。
- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

これらの役割を持つアカウントを確認するには、[ポータルの [アクセス許可Microsoft 365 Defender表示します](https://security.microsoft.com/permissions)。

**カスタム ロール アクセス** は、Microsoft Defender 365 Microsoft 365 Defenderの新しい機能であり、特定のデータ、タスク、および機能へのアクセスを管理できます。 カスタム ロールは、グローバル Azure ADロールよりも多くの制御を提供し、必要な最小限の役割で必要なアクセスのみをユーザーに提供します。  カスタム ロールは、グローバル Azure ロールとカスタム ロールにADできます。 [カスタム ロールの詳細を参照してください](custom-roles.md)。

> [!NOTE]
> この記事は、グローバル ロールの管理にのみAzure Active Directoryします。 カスタムの役割ベースのアクセス制御の使用の詳細については、「役割ベースのアクセス制御のカスタム [ロール」を参照してください。](custom-roles.md)

## <a name="access-to-functionality"></a>機能へのアクセス
特定の機能へのアクセスは、[Azure AD でのロール](/azure/active-directory/roles/permissions-reference)によって決まります。 ユーザーまたはユーザー グループに新しい役割を割り当てる必要がある場合は、グローバル管理者にお問い合わせください。

### <a name="approve-pending-automated-tasks"></a>保留中の自動化タスクを承認する
「[調査と修復の自動化](m365d-autoir-actions.md)」 は、調査中に見つかったメール、転送ルール、ファイル、持続性機構など、その他の成果物に対処できます。 明示的な承認が必要な保留中のアクションを承認または拒否するには、Microsoft 365 に特定の役割が割り当てられている必要があります。 詳細については、「[アクションセンターの権限](m365d-action-center.md#required-permissions-for-action-center-tasks)」をご覧ください。

## <a name="access-to-data"></a>データへのアクセス
Microsoft Defender for Endpoint Microsoft 365 Defenderアクセス制御 (RBAC) のユーザー グループに割り当てられたスコープを使用して、データへのアクセスを制御できます。 Defender for Endpoint の特定のデバイス セットにアクセスの範囲が設定されていない場合は、エンドポイント内のデータにフル アクセスMicrosoft 365 Defender。 ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。

たとえば、Microsoft Defender for Endpoint の役割を持つ 1 つのユーザー グループにのみ属し、そのユーザー グループに販売デバイスへのアクセス権が与えられた場合、Microsoft 365 Defender の販売デバイスに関するデータだけが表示されます。 [Microsoft Defender for Endpoint の RBAC 設定の詳細](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security のアクセス制御
プレビュー中に、Microsoft 365 Defender設定に基づいてアクセス制御をCloud App Security行う必要があります。 これらの設定Microsoft 365 Defenderデータへのアクセスは影響されません。

## <a name="related-topics"></a>関連項目
- [ユーザーの役割ベースのアクセス制御のカスタム ロールMicrosoft 365 Defender](custom-roles.md)
- [Azure AD組み込みロール](/azure/active-directory/roles/permissions-reference)
- [エンドポイント RBAC 用 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security roles](/cloud-app-security/manage-admins)
