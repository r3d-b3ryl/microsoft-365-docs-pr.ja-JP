---
title: ユーザーアカウントに Microsoft 365 ライセンスを割り当てる
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Microsoft 365 ライセンスを個別に、またはグループメンバーシップに基づいてユーザーアカウントに割り当てる方法について説明します。
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326509"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>ユーザーアカウントに Microsoft 365 ライセンスを割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

クラウド専用の id モデルの場合は、作成方法に応じて、ユーザーアカウントの作成時に Microsoft 365 ライセンスを割り当てることができます。

ハイブリッド id モデルでは、Active Directory ドメインサービス (AD DS) ユーザーアカウントが初めて同期されるときに、場所または Microsoft 365 ライセンスが自動的に割り当てられることはありません。 **各ユーザーアカウントは、ライセンスを割り当てる前またはユーザーの場所で構成する必要があります。**

どちらの場合も、ユーザーが Microsoft 365 サービス (電子メールや Microsoft Teams など) にアクセスできるように、ユーザーアカウントにライセンスを割り当てる必要があります。

ユーザーアカウントには、個別に、またはグループメンバーシップを使用して、自動的にライセンスを割り当てることができます。

Microsoft 365 ライセンスを個々のユーザーアカウントに割り当てるには、次のものを使用できます。

- [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD 管理センター

## <a name="group-based-licensing"></a>グループベースのライセンス

Azure AD のセキュリティグループを構成して、サブスクリプションのセットからグループのすべてのメンバーにライセンスを自動的に割り当てることができます。 これは*グループベースのライセンス*と呼ばれます。 グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。

すべてのグループ メンバーに十分なライセンスがあることを確認します。 ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。

>[!Note]
>Azure B2B (企業間) アカウントが含まれているグループに対してはグループベースのライセンスを構成しないでください。
>

Informaion の詳細については、「 [AZURE AD でのグループベースのライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)」を参照してください。

## <a name="next-steps"></a>次の手順

ライセンスが割り当てられている適切なユーザーアカウントのセットにより、次の準備が整いました。

- [セキュリティを実装する](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Microsoft 365 アプリなどのクライアントソフトウェアを展開する](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [デバイス管理をセットアップする](device-management-roadmap-microsoft-365.md)
- [サービスとアプリケーションを構成する](configure-services-and-applications.md)
