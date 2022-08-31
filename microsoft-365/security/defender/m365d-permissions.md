---
title: Microsoft 365 Defender ポータルでMicrosoft 365 Defender データへのアクセスを管理する
description: Microsoft 365 Defenderでデータに対するアクセス許可を管理する方法について説明します
keywords: access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, スコープ, RBAC
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 76101b7dc082786fb7c3054aef8a938402bbb0a8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470995"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Azure Active Directory グローバル ロールを使用してMicrosoft 365 Defenderへのアクセスを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defenderへのアクセスを管理するには、次の 2 つの方法があります。
- **グローバル Azure Active Directory (AD) ロール**
- **カスタム ロール へのアクセス**

次の **グローバル Azure Active Directory (AD) ロール** が割り当てられたアカウントは、Microsoft 365 Defender機能とデータにアクセスできます。
- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

これらのロールを持つアカウントを確認するには、[Microsoft 365 Defender ポータルでアクセス許可を表示します](https://security.microsoft.com/permissions)。

**カスタム ロール** アクセスは、Microsoft 365 Defenderの新機能であり、Microsoft 365 Defenderの特定のデータ、タスク、および機能へのアクセスを管理できます。 カスタム ロールは、グローバル Azure AD ロールよりも制御を提供し、ユーザーに必要なアクセス権のみを必要な最小許容ロールで提供します。  カスタム ロールは、グローバル Azure AD ロールに加えて作成できます。 [カスタム ロールの詳細については、こちらを参照してください](custom-roles.md)。

> [!NOTE]
> この記事は、グローバル Azure Active Directory ロールの管理にのみ適用されます。 カスタム ロールベースのアクセス制御の使用の詳細については、「ロールベースのアクセス制御[のカスタム ロール](custom-roles.md)」を参照してください。

## <a name="access-to-functionality"></a>機能へのアクセス
特定の機能へのアクセスは、[Azure AD でのロール](/azure/active-directory/roles/permissions-reference)によって決まります。 ユーザーまたはユーザー グループに新しい役割を割り当てる必要がある場合は、グローバル管理者にお問い合わせください。

### <a name="approve-pending-automated-tasks"></a>保留中の自動化タスクを承認する
「[調査と修復の自動化](m365d-autoir-actions.md)」 は、調査中に見つかったメール、転送ルール、ファイル、持続性機構など、その他の成果物に対処できます。 明示的な承認が必要な保留中のアクションを承認または拒否するには、Microsoft 365 に特定の役割が割り当てられている必要があります。 詳細については、「[アクションセンターの権限](m365d-action-center.md#required-permissions-for-action-center-tasks)」をご覧ください。

## <a name="access-to-data"></a>データへのアクセス
Microsoft 365 Defender データへのアクセスは、ロールベースのアクセス制御 (RBAC) でユーザー グループに割り当てられたスコープMicrosoft Defender for Endpoint使用して制御できます。 Defender for Endpoint の特定のデバイス セットに対するアクセスのスコープが設定されていない場合は、Microsoft 365 Defender内のデータにフル アクセスできます。 ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。

たとえば、Microsoft Defender for Endpoint ロールを持つ 1 つのユーザー グループにのみ属していて、そのユーザー グループに販売デバイスへのアクセス権のみが付与されている場合、Microsoft 365 Defenderの販売デバイスに関するデータのみが表示されます。 [Microsoft Defender for Endpointの RBAC 設定の詳細](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-defender-for-cloud-apps-access-controls"></a>Microsoft Defender for Cloud Appsアクセス制御
プレビュー期間中、Microsoft 365 Defenderは Defender for Cloud Apps の設定に基づくアクセス制御を適用しません。 Microsoft 365 Defender データへのアクセスは、これらの設定の影響を受けられません。

## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defenderのロールベースのアクセス制御のカスタム ロール](custom-roles.md)
- [Azure AD 組み込みロール](/azure/active-directory/roles/permissions-reference)
- [RBAC のMicrosoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Defender for Cloud Apps ロール](/cloud-app-security/manage-admins)
