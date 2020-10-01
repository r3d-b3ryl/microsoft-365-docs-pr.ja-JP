---
title: Microsoft 365 グループを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 グループを管理する方法について説明します。
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328520"
---
# <a name="manage-microsoft-365-groups"></a>Microsoft 365 グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

構成に応じて、Microsoft 365 グループをさまざまな方法で管理できます。 ユーザーアカウントは、 [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)、PowerShell、Active Directory ドメインサービス (AD DS)、または [azure Active DIRECTORY (azure AD) 管理センター](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)で管理できます。 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>グループを管理する場所と方法を計画します。

ユーザーアカウントを管理する場所と方法は、Microsoft 365 で使用する id モデルによって異なります。 これらのモデル全体は、クラウド専用でハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

以下を使用して、グループを作成して管理します。

- [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理センター](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>ハイブリッド

AD DS グループは AD DS から Microsoft 365 と同期されるので、オンプレミスの AD DS ツールを使用してこれらのグループを管理する必要があります。

Ad DS グループとは別の Azure AD グループを作成して管理することもできますが、AD DS からユーザーとグループを含めることができます。 この場合は、次のものを使用できます。

- [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理センター](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>ユーザーが各自のグループを作成および管理できるようにする

Azure AD では、IT 管理者ではなくグループ所有者が管理できるグループを許可します。 *セルフ サービスによるグループ管理*と呼ばれるこの機能では、管理者ロールが割り当てられていないグループ所有者がセキュリティ グループを作成および管理できるようになります。 

ユーザーがセキュリティ グループのメンバーシップを要求できます。この要求は IT 管理者ではなくグループ所有者に送られます。これにより、グループ メンバーシップの日常的な管理が、業務でのグループの用途を理解してグループのメンバーシップを管理できるチーム所有者、プロジェクト所有者、またはビジネス所有者に委任されます。

>[!Note]
>セルフサービスによるグループ管理は Azure AD セキュリティと Microsoft 365 グループに対してのみ使用できます。 メールが有効なグループ、配布リスト、または AD DS から同期された任意のグループに対しては使用できません。
>

詳細については、「[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)」を参照してください。

## <a name="set-up-dynamic-group-membership"></a>動的グループ メンバーシップをセットアップする

Azure AD では、ユーザーアカウントを Azure AD グループのメンバーとして自動的に追加または削除する一連のルールの構成をサポートしています。 これは*動的グループ メンバーシップ*と呼ばれます。 ルールはユーザー アカウントの属性 (部門や国など) に基づいています。

ルールの適用方法を次に説明します。

- 新しいユーザー アカウントがグループのすべてのルールに一致すると、そのアカウントはメンバーになります。
- ユーザー アカウントがグループのメンバーではないものの、その属性が変更されグループのすべてのルールに一致した場合は、そのユーザーアカウントはグループのメンバーになります。
- ユーザー アカウントがグループのすべてのルールに一致しない場合、そのアカウントはグループに追加されません。
- ユーザー アカウントがグループのメンバーであるものの、その属性が変更されそのグループのすべてのルールに一致しなくなると、グループのメンバーではなくなります。

動的メンバーシップを使用するには、最初に共通のユーザー アカウント属性セットを持つ一連のグループを判別します。たとえば、Sales 部門のすべてのメンバーは、ユーザー アカウントの Department 属性が「Sales」に設定されていることに基づき、Sales Azure AD グループに入れます。

「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」を参照してください。

## <a name="set-up-automatic-licensing"></a>自動ライセンスをセットアップする

Azure AD のセキュリティグループを構成して、サブスクリプションのセットからグループのすべてのメンバーにライセンスを自動的に割り当てることができます。 これは*グループベースのライセンス*と呼ばれます。 グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。

Microsoft 365 Enterprise では、適切な MIcrosoft 365 Enterprise ライセンスを割り当てる Azure AD セキュリティ グループを構成します。

すべてのグループ メンバーに十分なライセンスがあることを確認します。 ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。

>[!Note]
>Azure B2B (企業間) アカウントが含まれているグループに対してはグループベースのライセンスを構成しないでください。
>

詳細については、「 [AZURE AD のグループベースのライセンスの基礎](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)」を参照してください。

「 [Azure セキュリティグループのグループベースのライセンスを構成するに](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)は」の手順を参照してください。
