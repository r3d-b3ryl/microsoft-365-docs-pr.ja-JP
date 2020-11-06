---
title: Microsoft 365 セキュリティ/コンプライアンス センターのアクセス許可
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 セキュリティ センターまたは Microsoft 365 コンプライアンス センターを使用すると、セキュリティまたはコンプライアンスに関連するすべてのタスクについて、アクセス許可を一元的に管理できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f7dcddd7070f95ae61b17b9623dfcbab4a62e5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920634"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのアクセス許可

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


組織は、すべての Microsoft 365 サービスに関するセキュリティとコンプライアンスのシナリオを管理する必要があります。 また、組織の IT グループ内の適切なユーザーに、適切な管理者権限を付与する柔軟性も必要です。 Microsoft 365 セキュリティ センターまたは Microsoft 365 コンプライアンス センターを使用すると、セキュリティまたはコンプライアンスに関連するすべてのタスクについて、アクセス許可を一元的に管理できます。

全体管理者がこれらの管理者のロールを割り当てると、管理者は、Microsoft 365 セキュリティ センター、Microsoft 365 コンプライアンス センター、Azure、Office 365、Enterprise Mobility + Security など、Microsoft 365 のすべてのサービスに及ぶ機能やデータにアクセスできます。

## <a name="what-the-microsoft-365-roles-are"></a>Microsoft 365 のロール

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターには、Azure Active Directory のロールが表示されます。 これらのロールは、組織の IT グループの職務に合わせて設計されており、仕事を遂行するために必要なすべての権限をユーザーに簡単に付与できます。

****

|役割|内容|
|---|---|
|**全体管理者**|このロールを持つユーザーは、すべての Microsoft 365 サービスのすべての管理機能にアクセスできます。 他の管理者ロールを割り当てることができるのは全体管理者だけです。|
|**コンプライアンス データ管理者**|このロールを持つユーザーは、Microsoft 365 全体の組織のデータを追跡し、保護されていることを確認し、あらゆる問題を把握してリスクを軽減することができます。|
|**コンプライアンス管理者**|このロールを持つユーザーは、組織が規制要件を遵守し続けること、電子情報開示ケースを管理すること、および Microsoft 365 の場所、ID、アプリ全体のデータ ガバナンス ポリシーを維持することを支援できます。|
|**セキュリティ オペレーター**|このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示、調査、および対処できます。|
|**セキュリティ閲覧者**|このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示と調査ができますが、セキュリティ オペレーターとは異なり、アクションを実行するアクセス許可はありません。|
|**セキュリティ管理者**|このロールを持つユーザーは、セキュリティ ポリシーを管理し、Microsoft 365 製品全体のセキュリティ分析とレポートを確認し、脅威の情勢を十分に把握し続けることで、組織の全体的なセキュリティを制御できます。|
|

## <a name="what-the-microsoft-365-roles-have-access-to"></a>Microsoft 365 のロールのアクセス

ここでは、使用可能なロールとロールに割り当てられたユーザーができることを説明します。

### <a name="global-administrator"></a>全体管理者

このロールが割り当てられたユーザーは、Azure Active Directory のすべての管理機能と、Azure Active Directory の ID を使用するサービス (Microsoft 365 セキュリティ センター、Microsoft 365 コンプライアンス センター、Exchange Online、SharePoint Online、Skype for Business Online など) にアクセスできます。 Azure Active Directory テナントにサインアップしたユーザーが全体管理者になります。 他の管理者ロールを割り当てることができるのは全体管理者だけです。 会社に複数の全体管理者が存在してかまいません。 すべてのユーザーと他のすべての管理者のパスワードをリセットできます。

### <a name="compliance-administrator"></a>コンプライアンス管理者

このロールのユーザーには、Microsoft 365 コンプライアンス センター、Microsoft 365 管理センター、Azure、およびセキュリティ/コンプライアンス センターのコンプライアンス関連の機能を管理する権限があります。 また、ユーザーは、Exchange 管理センター、Teams および Skype for Business の管理センター内のすべての機能を管理したり、Azure および Microsoft 365 のサポート チケットを作成したりすることもできます。

****

|このサービスにおいて|コンプライアンス管理者ができること|
|---|---|
|[**Microsoft 365 コンプライアンス センター**](https://compliance.microsoft.com/)|Microsoft 365 サービス全体での組織のデータの保護および管理。 <br/><br/> コンプライアンス アラートの管理。|
|[**コンプライアンス マネージャー**](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager)|組織の法令遵守活動の追跡、割り当て、確認。|
|[**セキュリティ/コンプライアンス センター**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|データ ガバナンスの管理。 <br/><br/> 法律およびデータ調査の実行。 <br/><br/> データ主体の要求の管理。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Intune のすべての監査データの表示。|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|読み取り専用アクセス許可があり、アラートを管理できる。 <br/><br/> ファイル ポリシーの作成と変更、ファイル ガバナンス アクションの許可。 <br/><br/> データ管理下のすべての組み込みレポートの表示。|
|

### <a name="compliance-data-administrator"></a>コンプライアンス データ管理者

この役割を持つユーザーは、Microsoft 365 コンプライアンス センター、Microsoft 365 管理センター、Azure のデータを保護し、追跡するアクセス許可を持ちます。 また、ユーザーは、Exchange 管理センター、コンプライアンス マネージャー、Teams および Skype for Business の管理センター内のすべての機能を管理したり、Azure および Microsoft 365 のサポート チケットを作成したりすることもできます。

****

|このサービスにおいて|コンプライアンス データ管理者ができること|
|---|---|
|[**Microsoft 365 コンプライアンス センター**](https://compliance.microsoft.com/)|Microsoft 365 サービス全体での組織のデータの保護および管理。 <br/><br/> コンプライアンス アラートの管理。 <br/><br/> 機密ラベルの管理。|
|[**コンプライアンス マネージャー**](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager)|組織の法令遵守活動の追跡、割り当て、確認。|
|[**セキュリティ/コンプライアンス センター**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|データ ガバナンスの管理。 <br/><br/> 法律およびデータ調査の実行。 <br/><br/> データ主体の要求の管理。 <br/><br/> 機密ラベルの管理。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control) (準備中)|Intune のすべての監査データの表示。|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|読み取り専用アクセス許可を使用して情報を表示する。 <br/>通知の管理。 <br/><br/> ファイル ポリシーの作成と変更、ファイル ガバナンス アクションの許可。 <br/><br/> データ管理下のすべての組み込みレポートの表示。|
|

### <a name="security-administrator"></a>セキュリティ管理者

このロールが割り当てられたユーザーは、Microsoft 365 セキュリティ センター、Azure Active Directory Identity Protection、Azure Information Protection、およびセキュリティ/コンプライアンス センターのセキュリティ関連機能を管理するアクセス許可を持ちます。

****

|このサービスにおいて|セキュリティ管理者ができること|
|---|---|
|[**Microsoft 365 セキュリティ センター**](https://security.microsoft.com/)|Microsoft 365 サービス全体のセキュリティ関連ポリシーの監視。 <br/><br/>  セキュリティの脅威とアラートの管理。 <br/><br/> レポートの表示。 <br/><br/> 機密ラベルの管理。|
|**Identity Protection Center**|セキュリティ閲覧者ロールができるすべてのことに加え、パスワードの再設定以外のすべての Identity Protection Center の操作の実行。|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|セキュリティ閲覧者ロールができるすべてのこと。 <br/><br/> Azure AD ロールの割り当てまたは設定を管理することは **できません** 。|
|[**セキュリティ/コンプライアンス センター**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|セキュリティ ポリシーの管理。 <br/><br/> セキュリティの脅威の表示、調査、対応 <br/><br/> レポートの表示。 <br/><br/> 機密ラベルの管理。|
|**Microsoft Defender for Identity**|疑わしいセキュリティ アクティビティの監視と対応。|
|**Microsoft Defender for Endpoint および EDR**|ロールの割り当て。 <br/><br/> コンピューター グループの管理。 <br/><br/> エンドポイントの脅威の検出と自動修復の構成。 <br/><br/> アラートの表示、調査、対応。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|ユーザー、デバイス、登録、構成、アプリケーション情報の表示。 <br/><br/> Intune に変更を加えることは **できません** 。|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|管理者の追加、ポリシーと設定の追加、ログのアップロード、ガバナンス アクションの実行。|
|[**Azure Defender**](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles) (近日公開)|セキュリティ ポリシーの表示、セキュリティ状態の表示、セキュリティ ポリシーの編集、アラートと推奨事項の表示、アラートと推奨事項の却下。|
|[**Office 365 サービス正常性**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Office 365 サービスの正常性の表示。|
|

### <a name="security-operator"></a>セキュリティ オペレーター

このロールのユーザーはアラートを管理することができ、Microsoft 365 セキュリティ センター、Azure Active Directory、Identity Protection、Privileged Identity Management におけるすべての情報を含むセキュリティ関連機能への読み取り専用グローバル アクセス権に加えて、Azure Active Directory サインイン レポートと監査ログ、およびセキュリティ/コンプライアンス センターで閲覧する権限があります。

****

|このサービスにおいて|セキュリティ オペレーターができること|
|---|---|
|[**Microsoft 365 セキュリティ センター**](https://security.microsoft.com/)|セキュリティ閲覧者ロールができるすべてのこと。 <br/><br/> セキュリティの警告の表示、調査、対応。|
|**Identity Protection Center** (近日対応予定)|セキュリティ閲覧者ロールができるすべてのこと。|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|セキュリティ閲覧者ロールができるすべてのこと。|
|[**セキュリティ/コンプライアンス センター**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|セキュリティ閲覧者ロールができるすべてのこと。 <br/><br/> セキュリティの脅威の表示、調査、対応|
|**Microsoft Defender for Endpoint および EDR**|セキュリティ閲覧者ロールができるすべてのこと。 <br/><br/> アラートの表示、調査、対応。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|ユーザー、デバイス、登録、構成、アプリケーション情報の表示。 <br/><br/> Intune に変更を加えることは **できません** 。|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|セキュリティ閲覧者ロールができるすべてのことに加え、アラートの表示および破棄。|
|[**Office 365 サービス正常性**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Office 365 サービスの正常性の表示。|
|

### <a name="security-reader"></a>セキュリティ閲覧者

このロールのユーザーには、Microsoft 365 セキュリティ センター、Azure Active Directory、Identity Protection、Privileged Identity Management におけるすべての情報を含むセキュリティ関連機能への読み取り専用グローバル アクセス権に加えて、Azure Active Directory サインイン レポートと監査ログ、およびセキュリティ/コンプライアンス センターで閲覧する権限があります。

****

|このサービスにおいて|セキュリティ閲覧者ができること|
|---|---|
|[**Microsoft 365 セキュリティ センター**](https://security.microsoft.com/)|Microsoft 365 サービス全体のセキュリティ関連ポリシーの表示。 <br/><br/> セキュリティの脅威とアラートの表示。 <br/><br/> レポートの表示。|
|**Identity Protection Center**|各セキュリティ機能の全セキュリティ レポートと設定情報の閲覧: スパム対策、暗号化、データ損失防止 (DLP)、マルウェア対策、Defender for Office 365、フィッシング詐欺対策、メール フロー ルール (トランスポート ルールとも呼ばれる)。|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|読み取り専用アクセスを使用した Azure AD PIM に記載されているすべての情報の表示: Azure AD ロールの割り当てに関するポリシーとレポート、セキュリティレビュー、および将来的には Azure AD ロールの割り当て以外のシナリオでのポリシー データとレポート。 <br/><br/> Azure AD PIM へのサインアップおよび Azure AD PIM の変更を行うことは **できません** 。 このロールのユーザーは、追加のロール (グローバル管理者や特権ロール管理者など) の資格がある場合、PIM ポータルまたは PowerShell からそれらのロールを有効化することができます。|
|[**セキュリティ/コンプライアンス センター**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|セキュリティ ポリシーの表示。 <br/><br/> セキュリティの脅威の表示および調査。 <br/><br/> レポートの表示。|
|**Microsoft Defender for Endpoint および EDR**|アラートの表示と調査。|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|ユーザー、デバイス、登録、構成、アプリケーション情報の表示。 <br/><br/> Intune に変更を加えることは **できません** 。|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|読み取り専用アクセス許可を使用して情報を表示する。 <br/><br/> 通知の管理。|
|[**Azure Defender**](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles)|推奨事項とアラートの表示。 <br/><br/> セキュリティ ポリシーの表示。 <br/><br/> セキュリティの状態を表示することはできますが、変更することはできません。|
|[**Office 365 サービス正常性**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Office 365 サービスの正常性の表示。|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>全体管理者は Azure Active Directory のロール管理が可能

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターでロールを選択すると、その割り当てを表示できます。 割り当てを管理するには、Azure Active Directory に移動する必要があります。

詳しくは、「[Azure Active Directory で管理者ロールを表示して割り当てる](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」をご覧ください。

![Azure Active Directory のアクセス許可管理へのリンク](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Azure Active Directory の代わりにサービスのロールを管理する

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターに表示されるロールは、アクセス許可を持つサービスにも表示されます。 たとえば、これらのロールはセキュリティ/コンプライアンス センターで確認できます。

![セキュリティ/コンプライアンス センターのロール](../../media/m365-roles-in-o365-scc.png)

### <a name="breaking-inheritance"></a>継承の解除

Azure Active Directoryでこれらのロールを管理するときは、 **すべて** の Microsoft 365 サービスを一元的に管理しているということを理解しておくことが重要です。 ただし、セキュリティ/コンプライアンス センターなどの特定のサービスでロールを管理する場合は、その特定のサービスにおけるロール **のみ** を管理しています。 サービスにおけるロールの割り当てとアクセス許可は、Azure Active Directory のロールに与えられているアクセス許可より優先されます。

これは、たとえば、セキュリティ管理者ロールに割り当てられているユーザーが、インシデントを管理するためのアクセス許可を持っていない場合に便利です。 ただし、Microsoft Defender for Endpoint でアクセス許可を使用して、そのサービスのインシデント管理に特定のアクセス許可を与えることができます。

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Microsoft 365 の各サービスのロール情報の場所

ユーザーを Microsoft 365 のコンプライアンス管理者またはセキュリティ管理者のロールのいずれかに割り当てると、そのユーザーには さまざまな Microsoft 365 サービスへのアクセス許可が与えられます。 各サービスのロールについての詳細情報については、以下のリンクを参照してください。

****

|Microsoft 365 サービス|ロール情報|
|---|---|
|Office 365 と Microsoft 365 for business での管理者ロール|[Microsoft 365 管理者ロール](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)|
|Azure Active Directory (Azure AD) および Azure AD Identity Protection|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Identity|[Microsoft Defender for Identity の役割グループ](https://docs.microsoft.com/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|コンプライアンス マネージャー|[コンプライアンス マネージャー](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager-setup#set-user-permissions-and-assign-roles)|
|Exchange Online|[Exchange のロール ベースのアクセス制御](https://docs.microsoft.com/exchange/understanding-role-based-access-control-exchange-2013-help)|
|Intune|[Intune のロール ベースのアクセス制御](https://docs.microsoft.com/intune/role-based-access-control)|
|管理対象デスクトップ|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[ロールベースのアクセス制御](https://docs.microsoft.com/cloud-app-security/manage-admins)|
|セキュリティ/コンプライアンス センター|[Microsoft 365 管理者ロール](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|セキュリティ スコア|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <br/><br/> [Office 365 での SharePoint 管理者ロールについて](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)|
|Teams/Skype for Business|[Azure AD 管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Endpoint|[Microsoft Defender for Endpoint の役割ベースのアクセス制御](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="what-is-coming-soon"></a>まもなく提供される機能

Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのアクセス許可については準備中です。 現時点では、次の機能のサポートに取り組んでいます。

- Azure Active Directory に移動せずに、Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターで、ロールを管理する。

- 特定のアクセス許可を追加または削除して、ロールをカスタマイズする。

- 選択したアクセス許可を持つカスタム ロールを作成する。
