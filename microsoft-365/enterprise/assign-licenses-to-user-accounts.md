---
title: ユーザー アカウントMicrosoft 365ライセンスを割り当てる
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: ユーザー アカウントにライセンスを割りMicrosoft 365個別に、またはグループ メンバーシップに基づいて割り当てる方法について説明します。
ms.openlocfilehash: dd941be0d257aa356cf6e69bfdd59a8d1743ed93
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159464"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>ユーザー アカウントMicrosoft 365ライセンスを割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

クラウド専用 ID モデルの場合、作成方法に応じて、Microsoft 365ライセンスを作成時にユーザー アカウントに割り当てできます。

ハイブリッド ID モデルの場合、Active Directory ドメイン サービス (AD DS) ユーザー アカウントが初めて同期された場合、場所または Microsoft 365 ライセンスが自動的に割り当てられていない。 **ライセンスの割り当て前または割り当てと共に、ユーザーの場所を使用して各ユーザー アカウントを構成する必要があります。**

いずれの場合も、ユーザーが電子メールやメールサービスなどのサービスにアクセスMicrosoft 365ユーザー アカウントにライセンスを割り当てるMicrosoft Teams。

ユーザー アカウントにライセンスを割り当てるには、グループ メンバーシップを使用して個別にまたは自動的に割り当てできます。

個々のユーザー Microsoft 365にライセンスを割り当てるには、次のコマンドを使用できます。

- [Microsoft 365 管理センター](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD管理センター

## <a name="group-based-licensing"></a>グループベースのライセンス

Azure ADのセキュリティ グループを構成して、一連のサブスクリプションからグループのすべてのメンバーにライセンスを自動的に割り当てできます。 これは *グループベースのライセンス* と呼ばれます。 グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。

すべてのグループ メンバーに十分なライセンスがあることを確認します。 ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。

>[!Note]
>Azure B2B (企業間) アカウントが含まれているグループに対してはグループベースのライセンスを構成しないでください。
>

詳細については、「Azure AD でのグループ ベース [のライセンス」を参照してください](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

## <a name="next-steps"></a>次の手順

ライセンスが割り当てられている適切な一連のユーザー アカウントを使用して、次の準備ができました。

- [セキュリティの実装](../security/office-365-security/security-roadmap.md)
- [クライアント ソフトウェア (クライアント ソフトウェアなど) を展開Microsoft 365 Apps](/DeployOffice/deployment-guide-microsoft-365-apps)
- [デバイス管理のセットアップ](device-management-roadmap-microsoft-365.md)
- [サービスとアプリケーションの構成](configure-services-and-applications.md)