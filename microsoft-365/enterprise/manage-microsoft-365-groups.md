---
title: Microsoft 365 グループを管理する
ms.author: kvice
author: kelleyvice-msft
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
description: グループを管理する方法Microsoft 365します。
ms.openlocfilehash: 72bc47bb699e32f849f21ea4c5470a95d6228b68
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356686"
---
# <a name="manage-microsoft-365-groups"></a>Microsoft 365 グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

構成に応じてMicrosoft 365グループを複数の方法で管理できます。 ユーザー アカウントは、Microsoft 365 管理センター、PowerShell、Active Directory ドメイン サービス (AD DS)、または Azure Active Directory [(Azure AD) 管理センターで管理できます](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)。 [](../admin/add-users/index.yml) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>グループを管理する場所と方法を計画する

ユーザー アカウントを管理する場所と方法は、ユーザー アカウントに使用する id モデルによってMicrosoft 365。 2 つの全体的なモデルは、クラウド専用とハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

グループを作成および管理するには、次の機能を使用します。

- [Microsoft 365 管理センター](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理センター](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>ハイブリッド

AD DS グループは Microsoft 365 DS の AD と同期されます。そのため、これらのグループを管理するには、オンプレミスの DS AD ツールを使用する必要があります。

また、DS グループとは別の Azure ADグループを作成および管理AD DS からのユーザーとグループを含ADすることもできます。 この場合、次のコマンドを使用できます。

- [Microsoft 365 管理センター](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理センター](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>ユーザーが各自のグループを作成および管理できるようにする

Azure ADは、IT 管理者ではなくグループ所有者が管理できるグループを許可します。 *セルフ サービスによるグループ管理* と呼ばれるこの機能では、管理者ロールが割り当てられていないグループ所有者がセキュリティ グループを作成および管理できるようになります。 

ユーザーがセキュリティ グループのメンバーシップを要求できます。この要求は IT 管理者ではなくグループ所有者に送られます。これにより、グループ メンバーシップの日常的な管理が、業務でのグループの用途を理解してグループのメンバーシップを管理できるチーム所有者、プロジェクト所有者、またはビジネス所有者に委任されます。

>[!Note]
>セルフサービスによるグループ管理は Azure AD セキュリティと Microsoft 365 グループに対してのみ使用できます。 メールが有効なグループ、配布リスト、または DS から同期されたグループではADされません。
>

詳細については、「[セルフサービス グループ管理に必要な Azure Active Directory の設定](/azure/active-directory/active-directory-accessmanagement-self-service-group-management)」を参照してください。

## <a name="set-up-dynamic-group-membership"></a>動的グループ メンバーシップをセットアップする

Azure ADは、Azure アカウント グループのメンバーとしてユーザー アカウントを自動的に追加または削除する一連のルールADします。 これは *動的グループ メンバーシップ* と呼ばれます。 ルールはユーザー アカウントの属性 (部門や国など) に基づいています。

ルールの適用方法を次に説明します。

- 新しいユーザー アカウントがグループのすべてのルールに一致すると、そのアカウントはメンバーになります。
- ユーザー アカウントがグループのメンバーではないものの、その属性が変更されグループのすべてのルールに一致した場合は、そのユーザーアカウントはグループのメンバーになります。
- ユーザー アカウントがグループのすべてのルールに一致しない場合、そのアカウントはグループに追加されません。
- ユーザー アカウントがグループのメンバーであるものの、その属性が変更されそのグループのすべてのルールに一致しなくなると、グループのメンバーではなくなります。

動的メンバーシップを使用するには、最初に共通のユーザー アカウント属性セットを持つ一連のグループを判別します。たとえば、Sales 部門のすべてのメンバーは、ユーザー アカウントの Department 属性が「Sales」に設定されていることに基づき、Sales Azure AD グループに入れます。

「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」を参照してください。

## <a name="set-up-automatic-licensing"></a>自動ライセンスをセットアップする

Azure ADのセキュリティ グループを構成して、一連のサブスクリプションからグループのすべてのメンバーにライセンスを自動的に割り当てできます。 これは *グループベースのライセンス* と呼ばれます。 グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。

Microsoft 365 Enterprise では、適切な MIcrosoft 365 Enterprise ライセンスを割り当てる Azure AD セキュリティ グループを構成します。

すべてのグループ メンバーに十分なライセンスがあることを確認します。 ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。

>[!Note]
>Azure B2B (企業間) アカウントが含まれているグループに対してはグループベースのライセンスを構成しないでください。
>

詳細については、「Azure AD のグループ ベースのライセンス [の基本」を参照してください](/azure/active-directory/active-directory-licensing-whatis-azure-portal)。

Azure セキュリティ [グループのグループ ベースのライセンスを構成する手順を参照してください](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。