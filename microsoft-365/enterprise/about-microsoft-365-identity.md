---
title: Microsoft 365 ID モデルと id モデルAzure Active Directory
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: クラウド専用またはハイブリッド ID モデルをADを使用して、Microsoft 365ユーザー ID サービスを管理する方法について説明します。
ms.openlocfilehash: 65cfd736ca12c91094d841277c00c42a916c6cda
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58354154"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 ID モデルと id モデルAzure Active Directory

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365は、Microsoft 365 サブスクリプションに含まれるクラウドベースのユーザー ID および認証サービスである Azure Active Directory (Azure AD) を使用して、Microsoft 365 の ID と認証を管理します。 ID インフラストラクチャを正しく構成することは、組織のユーザー アクセスMicrosoft 365アクセス許可を管理する上で重要です。

開始する前に、Microsoft 365 の ID モデルと認証の概要についてこのビデオをご覧ください。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

最初の計画の選択は、Microsoft 365 ID モデルです。

## <a name="microsoft-365-identity-models"></a>Microsoft 365 ID モデル

ユーザー アカウントを計画するには、まず、ユーザー アカウントの 2 つの ID モデルをMicrosoft 365。 組織の ID はクラウドでのみ維持するか、オンプレミスの Active Directory ドメイン サービス (AD DS) ID を維持し、ユーザーが Microsoft 365 クラウド サービスにアクセスするときに認証に使用できます。

ID の 2 種類と、最適なフィット感と利点を次に示します。

| 属性 | クラウド専用 ID | ハイブリッド ID |
|:-------|:-----|:-----|
| **定義** | ユーザー アカウントは、サブスクリプションの Azure ADテナントにのみMicrosoft 365されます。 | ユーザー アカウントは DS AD存在し、コピーはサブスクリプションの Azure ADテナントMicrosoft 365です。 Azure ADのユーザー アカウントには、既にハッシュされた DS ユーザー アカウント のパスワードADが含まれる場合があります。 |
| **ユーザー Microsoft 365認証方法** | サブスクリプションAD Azure Microsoft 365テナントは、クラウド ID アカウントを使用して認証を実行します。 | Azure ADサブスクリプションMicrosoft 365、認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。 |
| **最適シナリオ** | DS を使用するオンプレミスの組織または必要AD組織。 | DS または別AD ID プロバイダーを使用している組織。 |
| **最大のメリット** | 使いやすい。 追加のディレクトリ ツールやサーバーは必要ありません。 | ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。 |
||||

## <a name="cloud-only-identity"></a>クラウド専用 ID

クラウドのみの ID は、Azure AD にのみ存在するユーザー アカウントを使用します。 クラウド専用 ID は、通常、オンプレミス のサーバーを持たない、またはローカル ID を管理するために AD DS を使用しない小規模な組織で使用されます。

クラウド専用 ID の基本的なコンポーネントを次に示します。

![クラウド専用 ID の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

オンプレミスとリモート (オンライン) の両方のユーザーは、Azure ADアカウントとパスワードを使用して、クラウド Microsoft 365アクセスします。 Azure AD は、保存されたユーザー アカウントとパスワードに基づいて、ユーザー資格情報を認証します。

### <a name="administration"></a>管理
ユーザー アカウントは Azure AD にのみ格納されるので、クラウド ID は、クラウド ID などのツールを[](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)使用[Microsoft 365 管理センター管理](../admin/add-users/index.yml)Windows PowerShell。

## <a name="hybrid-identity"></a>ハイブリッド ID

ハイブリッド ID は、オンプレミスの DS で発生し、ADサブスクリプションの Azure AD テナントにコピー Microsoft 365します。 ただし、ほとんどの変更は 1 つの方法でのみフローします。 DS ユーザー アカウントに対して行AD変更は、Azure ユーザー アカウントのコピーと同期AD。 ただし、Azure AD のクラウドベースのアカウント (新しいユーザー アカウントなど) に加えた変更は、AD DS と同期されません。

Azure AD Connectは、継続的なアカウント同期を提供します。 オンプレミス サーバー上で実行し、DS の変更をADし、それらの変更を Azure サーバーに転送AD。 Azure AD Connectでは、同期するアカウントと、パスワード ハッシュ同期 (PHS) と呼ばれるハッシュバージョンのユーザー パスワードを同期するかどうかをフィルター処理できます。

ハイブリッド ID を導入した場合、オンプレミスの AD DS がアカウント情報の信頼できるソースとなります。 つまり、主にオンプレミスで管理タスクを実行し、Azure サーバーに同期AD。

ハイブリッド ID のコンポーネントを次に示します。

![ハイブリッド ID のコンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure ADテナントには、DS アカウントのADがあります。 この構成では、クラウド サービスにアクセスするオンプレミスユーザーとリモート ユーザーの両方Microsoft 365 Azure サービスに対して認証AD。

> [!NOTE]
> ハイブリッド ID のユーザー アカウントを同期するには、常AD Connect Azure サーバーを使用する必要があります。 ライセンスの割り当てとグループAD、アクセス許可の構成、およびユーザー アカウントに関連するその他の管理タスクを実行するには、Azure AD で同期されたユーザー アカウントが必要です。

### <a name="administration"></a>管理

元のユーザー アカウントと権限のあるユーザー アカウントはオンプレミスの AD DS に格納されますので、AD DS を管理するのと同じツールを使用して id を管理します。

Azure Microsoft 365 管理センターで同期Microsoft 365ユーザー アカウントを管理するために、Microsoft 365 管理センター PowerShell を使用AD。

## <a name="next-step"></a>次の手順

クラウド専用 ID モデルが必要な場合は、「クラウド専用 [ID」を参照してください](cloud-only-identities.md)。

ハイブリッド ID モデルが必要な場合は、「ハイブリッド ID」 [を参照してください](plan-for-directory-synchronization.md)。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
