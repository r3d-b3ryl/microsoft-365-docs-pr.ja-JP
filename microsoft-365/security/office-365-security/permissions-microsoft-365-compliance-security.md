---
title: Microsoft 365 セキュリティ/コンプライアンス センターのアクセス許可
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 セキュリティ センターまたは Microsoft 365 コンプライアンス センターを使用すると、セキュリティまたはコンプライアンスに関連するすべてのタスクについて、アクセス許可を一元的に管理できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55030813ecddedd5661602fddea59f6bf3a8b03a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290789"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのアクセス許可

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

組織は、すべての Microsoft 365 サービスに関するセキュリティとコンプライアンスのシナリオを管理する必要があります。 また、組織の IT グループ内の適切なユーザーに、適切な管理者権限を付与する柔軟性も必要です。 Microsoft 365 セキュリティ センターまたは Microsoft 365 コンプライアンス センターを使用すると、セキュリティまたはコンプライアンスに関連するすべてのタスクについて、アクセス許可を一元的に管理できます。

全体管理者がこれらの管理者のロールを割り当てると、管理者は、Microsoft 365 セキュリティ センター、Microsoft 365 コンプライアンス センター、Azure、Office 365、Enterprise Mobility + Security など、Microsoft 365 のすべてのサービスに及ぶ機能やデータにアクセスできます。

## <a name="what-the-microsoft-365-roles-are"></a>Microsoft 365 のロール

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターには、Azure Active Directory のロールが表示されます。 これらのロールは、組織の IT グループの職務に合わせて設計されており、仕事を遂行するために必要なすべての権限をユーザーに簡単に付与できます。

****

|役割|内容|
|---|---|
|**全体管理者**|Microsoft 365 サービスのすべての管理機能にアクセスできます。 他の管理者ロールを割り当てることができるのは全体管理者だけです。 詳細については、「[グローバル管理者または会社の管理者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)」を参照してください。|
|**コンプライアンス データ管理者**|Microsoft 365 全体の組織のデータを追跡し、保護されていることを確認し、あらゆる問題を把握して分析しリスクを軽減する手伝いをします。 詳細については、「[コンプライアンス データ管理者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#compliance-data-administrator)」を参照してください。|
|**コンプライアンス管理者**|組織が規制要件を遵守し続けること、電子情報開示ケースを管理すること、および Microsoft 365 の使用場所、ID、アプリ全体のデータ ガバナンス ポリシーを維持します。 詳細については、「[コンプライアンス管理者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#compliance-administrator)」を参照してください。|
|**セキュリティ オペレーター**|このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示、調査、および対処します。 詳細については、「[セキュリティ オペレーター](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-operator)」を参照してください。|
|**セキュリティ閲覧者**|このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示、調査ができますが、セキュリティ オペレーターとは異なり、アクションを実行するアクセス許可はありません。 詳細については、「[セキュリティ 閲覧者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-reader)」を参照してください。|
|**セキュリティ管理者**|このロールを持つユーザーは、セキュリティ ポリシーを管理し、Microsoft 365 製品全体のセキュリティ分析とレポートを確認し、脅威の情勢を十分に把握し迅速に対処して、組織の全体的なセキュリティを制御します。 詳細については、「[セキュリティ 管理者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-administrator)」を参照してください。|
|**グローバル閲覧者**|読み取り専用バージョンの **グローバル閲覧者** のロール。 Microsoft 365 のすべての設定と管理情報を表示します。 詳細については、「[グローバル閲覧者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#global-reader)」を参照してください。|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>全体管理者は Azure Active Directory のロール管理が可能

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターでロールを選択すると、その割り当てを表示できます。 割り当てを管理するには、Azure Active Directory に移動する必要があります。

詳しくは、「[Azure Active Directory で管理者ロールを表示して割り当てる](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」をご覧ください。

![Azure Active Directory のアクセス許可管理へのリンク](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Azure Active Directory の代わりにサービスのロールを管理する

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターに表示されるロールは、アクセス許可を持つサービスにも表示されます。 たとえば、これらのロールはセキュリティ/コンプライアンス センターで確認できます。

![セキュリティ/コンプライアンス センターのロール](../../media/m365-roles-in-o365-scc.png)

セキュリティ/コンプライアンス センターのこれらの役割の詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

### <a name="breaking-inheritance"></a>継承の解除

Azure Active Directoryでこれらのロールを管理するときは、**すべて** の Microsoft 365 サービスを一元的に管理しているということを理解しておくことが重要です。 ただし、セキュリティ/コンプライアンス センターなどの特定のサービスでロールを管理する場合は、その特定のサービスにおけるロール **のみ** を管理しています。 サービスにおけるロールの割り当てとアクセス許可は、Azure Active Directory のロールに与えられているアクセス許可より優先されます。

これは便利な場合もあります。 たとえば、セキュリティ管理者ロールに割り当てられているユーザーは、インシデントを管理するためのアクセス許可を持っていません。 ただし、Microsoft Defender for Endpoint のアクセス許可を使用して、そのサービスのインシデント管理に特定のアクセス許可を付与することができます。

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Microsoft 365 の各サービスのロール情報の場所

ユーザーを Microsoft 365 のコンプライアンス管理者またはセキュリティ管理者のロールのいずれかに割り当てると、そのユーザーには さまざまな Microsoft 365 サービスへのアクセス許可が与えられます。 各サービスのロールについての詳細情報については、以下のリンクを参照してください。

****

|Microsoft 365 サービス|ロール情報|
|---|---|
|Office 365 と Microsoft 365 for business での管理者ロール|[Microsoft 365 管理者ロール](../../admin/add-users/about-admin-roles.md)|
|Azure Active Directory (Azure AD) および Azure AD Identity Protection|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Identity|[Microsoft Defender for Identity の役割グループ](https://docs.microsoft.com/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|コンプライアンス マネージャー|[コンプライアンス マネージャー](../../compliance/compliance-manager-setup.md#set-user-permissions-and-assign-roles)|
|Exchange Online|[Exchange のロール ベースのアクセス制御](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)|
|Intune|[Intune のロール ベースのアクセス制御](https://docs.microsoft.com/intune/role-based-access-control)|
|管理対象デスクトップ|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[ロールベースのアクセス制御](https://docs.microsoft.com/cloud-app-security/manage-admins)|
|セキュリティ/コンプライアンス センター|[Microsoft 365 管理者ロール](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|セキュリティ スコア|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Office 365 での SharePoint 管理者ロールについて](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)|
|Teams/Skype for Business|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Endpoint|[Microsoft Defender for Endpoint の役割ベースのアクセス制御](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>近日対応予定

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのアクセス許可については準備中です。 現時点では、次の機能のサポートに取り組んでいます。

- Azure Active Directory に移動せずに、Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターで、ロールを管理する。
- 特定のアクセス許可を追加または削除して、ロールをカスタマイズする。
- 選択したアクセス許可を持つカスタム ロールを作成する。
