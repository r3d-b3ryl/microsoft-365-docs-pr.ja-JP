---
title: Microsoft 365 ライセンスをユーザー アカウントに割り当てる
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Microsoft 365 ライセンスをユーザー アカウントに個別に、またはグループ メンバーシップに基づいて割り当てる方法について説明します。
ms.openlocfilehash: ab9769aa4dee6a9f7982f72f377b0c7e0d3f444e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091415"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Microsoft 365 ライセンスをユーザー アカウントに割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

クラウド専用 ID モデルの場合、作成方法に応じて、作成時にMicrosoft 365ライセンスをユーザー アカウントに割り当てることができます。

ハイブリッド ID モデルの場合、Active Directory Domain Services (AD DS) ユーザー アカウントが初めて同期されると、場所またはMicrosoft 365 ライセンスが自動的に割り当てられません。 **ライセンスの割り当て前または割り当てと共に、ユーザーの場所を使用して各ユーザー アカウントを構成する必要があります。**

どちらの場合も、ユーザーが電子メールやMicrosoft TeamsなどのMicrosoft 365 サービスにアクセスできるように、ユーザー アカウントにライセンスを割り当てる必要があります。

ユーザー アカウントにライセンスを個別に割り当てるか、グループ メンバーシップを使用して自動的に割り当てることができます。

Microsoft 365 ライセンスを個々のユーザー アカウントに割り当てるには、次を使用できます。

- [Microsoft 365 管理センター](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD管理センター

## <a name="group-based-licensing"></a>グループベースのライセンス

Azure ADのセキュリティ グループを構成して、一連のサブスクリプションからグループのすべてのメンバーにライセンスを自動的に割り当てることができます。 これは *グループベースのライセンス* と呼ばれます。 グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。

すべてのグループ メンバーに十分なライセンスがあることを確認します。 ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。

>[!Note]
>Azure B2B (企業間) アカウントが含まれているグループに対してはグループベースのライセンスを構成しないでください。
>

詳細については、[Azure ADのグループ ベースのライセンスに関するページを](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)参照してください。

## <a name="next-steps"></a>次の手順

ライセンスが割り当てられている適切なユーザー アカウントのセットを使用して、次の準備が整いました。

- [セキュリティを実装する](../security/office-365-security/security-roadmap.md)
- [Microsoft 365 Appsなどのクライアント ソフトウェアを展開する](/DeployOffice/deployment-guide-microsoft-365-apps)
- [デバイス管理を設定する](device-management-roadmap-microsoft-365.md)
- [サービスとアプリケーションを構成する](configure-services-and-applications.md)