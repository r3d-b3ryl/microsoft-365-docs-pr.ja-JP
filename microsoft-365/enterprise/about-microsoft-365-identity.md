---
title: Microsoft 365 ID モデルと Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
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
description: クラウド専用またはハイブリッド ID モデルを使用AD Microsoft 365 で Azure ユーザー ID サービスを管理する方法について説明します。
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905706"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 ID モデルと Azure Active Directory

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 は、Microsoft 365 サブスクリプションに含まれるクラウドベースのユーザー ID および認証サービスである Azure Active Directory (Azure AD) を使用して、Microsoft 365 の ID と認証を管理します。 組織の Microsoft 365 ユーザー アクセスとアクセス許可を管理するには、ID インフラストラクチャを正しく構成する必要があります。

開始する前に、Microsoft 365 の ID モデルと認証の概要についてこのビデオをご覧ください。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

最初の計画の選択は、Microsoft 365 ID モデルです。

## <a name="microsoft-365-identity-models"></a>Microsoft 365 ID モデル

ユーザー アカウントを計画するには、まず Microsoft 365 の 2 つの ID モデルを理解する必要があります。 組織の ID はクラウドでのみ維持するか、オンプレミスの Active Directory ドメイン サービス (AD DS) ID を維持し、ユーザーが Microsoft 365 クラウド サービスにアクセスするときに認証に使用できます。  

ID の 2 種類と、最適なフィット感と利点を次に示します。

| 属性 | クラウド専用 ID | ハイブリッド ID |
|:-------|:-----|:-----|
| **定義** | ユーザー アカウントは、Microsoft 365 サブスクリプションの Azure ADテナントにのみ存在します。 | ユーザー アカウントは DS AD存在し、コピーは Microsoft 365 サブスクリプションの Azure ADテナントにも存在します。 Azure ADのユーザー アカウントには、既にハッシュされた DS ユーザー アカウント のパスワードADが含まれる場合があります。 |
| **Microsoft 365 がユーザー資格情報を認証する方法** | Microsoft 365 ADの Azure クライアント テナントは、クラウド ID アカウントを使用して認証を実行します。 | Microsoft 365 サブスクリプションの Azure ADテナントは、認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。 |
| **最適シナリオ** | DS を使用するオンプレミスの組織または必要AD組織。 | DS または別AD ID プロバイダーを使用している組織。 |
| **最大のメリット** | 使いやすい。 追加のディレクトリ ツールやサーバーは必要ありません。 | ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。 |
||||

## <a name="cloud-only-identity"></a>クラウド専用 ID

クラウド専用 ID は、Azure アカウントにのみ存在するユーザー アカウントを使用AD。 クラウド専用 ID は、通常、オンプレミス のサーバーを持たない、またはローカル ID を管理するために AD DS を使用しない小規模な組織で使用されます。 

クラウド専用 ID の基本的なコンポーネントを次に示します。
 
![クラウド専用 ID の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

オンプレミスユーザーとリモート (オンライン) ユーザーの両方が、Azure ADとパスワードを使用して Microsoft 365 クラウド サービスにアクセスします。 Azure AD、保存されているユーザー アカウントとパスワードに基づいてユーザー資格情報を認証します。

### <a name="administration"></a>管理
ユーザー アカウントは Azure AD にのみ格納されるので[、Microsoft 365](../admin/add-users/index.yml)管理センターや管理センターなどのツールを使用してクラウド[ID をWindows PowerShell。](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md) 

## <a name="hybrid-identity"></a>ハイブリッド ID

ハイブリッド ID は、オンプレミスの DS からAD、Microsoft 365 サブスクリプションの Azure AD テナントにコピーを持つアカウントを使用します。 ただし、ほとんどの変更は 1 つの方法でのみフローします。 DS ユーザー アカウントに対して行AD変更は、Azure ユーザー アカウントのコピーと同期AD。 ただし、Azure AD のクラウドベースのアカウント (新しいユーザー アカウントなど) に加えた変更は、AD DS と同期されません。

Azure AD Connect は、継続的なアカウント同期を提供します。 オンプレミス サーバー上で実行し、DS の変更をADし、それらの変更を Azure サーバーに転送AD。 Azure AD Connect では、同期するアカウントと、パスワード ハッシュ同期 (PHS) と呼ばれるハッシュバージョンのユーザー パスワードを同期するかどうかをフィルター処理できます。

ハイブリッド ID を実装する場合、オンプレミスの AD DS がアカウント情報の権限を持つソースになります。 つまり、主にオンプレミスで管理タスクを実行し、Azure サーバーに同期AD。 

ハイブリッド ID のコンポーネントを次に示します。

![ハイブリッド ID のコンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure ADテナントには、DS アカウントのADがあります。 この構成では、Microsoft 365 クラウド サービスにアクセスするオンプレミスユーザーとリモート ユーザーの両方が Azure AD に対して認証されます。

>[!Note]
>ハイブリッド ID のユーザー アカウントを同期するには、常に Azure AD接続を使用する必要があります。 ライセンスの割り当てとグループAD、アクセス許可の構成、およびユーザー アカウントに関連するその他の管理タスクを実行するには、Azure AD で同期されたユーザー アカウントが必要です。
>

### <a name="administration"></a>管理

元のユーザー アカウントと権限のあるユーザー アカウントはオンプレミスの AD DS に格納されますので、AD DS を管理するのと同じツールを使用して id を管理します。 

Microsoft 365 管理センターまたは PowerShell for Microsoft 365 を使用して、Azure AD で同期されたユーザー アカウントを管理することはできません。

## <a name="next-step"></a>次の手順

クラウド専用 ID モデルが必要な場合は、「クラウド専用 [ID」を参照してください](cloud-only-identities.md)。

ハイブリッド ID モデルが必要な場合は、「ハイブリッド ID」 [を参照してください](plan-for-directory-synchronization.md)。


## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)