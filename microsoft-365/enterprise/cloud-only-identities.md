---
title: Microsoft 365専用 ID
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
description: サブスクリプションでクラウド専用 ID を使用している場合Microsoft 365グループを作成する方法について説明します。
ms.openlocfilehash: c12b3bea5523430c89c89f1e310308925a04c3c6fe6bd0a4b1a033dadd57501f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53864989"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365専用 ID

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

クラウド専用 ID を使用すると、すべてのユーザー、グループ、連絡先が Azure Active Directory (Azure AD) テナントの Microsoft 365 サブスクリプションに格納されます。 クラウド専用 ID の基本的なコンポーネントを次に示します。
 
![クラウド専用 ID の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

組織のユーザーとユーザー アカウントは、さまざまな方法で分類できます。 たとえば、従業員であり、永続的なステータスを持つユーザーもいます。 一部のベンダー、請負業者、または一時的なステータスを持つパートナーがあります。 一部のユーザー は、ユーザー アカウントを持たず、対話とコラボレーションをサポートするために特定のサービスとリソースへのアクセスを許可する必要がある外部ユーザーです。 次に例を示します。

- テナント アカウントは、組織内でクラウド サービスのライセンスを付与したユーザーを表します。

- B2B (Business to Busines) アカウントは、コラボレーションへの参加のために招待された組織外部のユーザーを表します。

組織内のユーザーの種類を確認します。 グループ化とは何ですか? たとえば、ユーザーを組織に対して高レベルの機能または目的でグループ化できます。

また、一部のクラウド サービスを、ユーザー アカウントを持たない組織外のユーザーと共有できます。この場合、このような外部ユーザーのグループも指定する必要があります。

Azure ADグループは、クラウド環境の管理を簡素化する目的で使用できます。 たとえば、Azure ADを使用すると、次の方法を実行できます。

- グループ ベースのライセンスを使用して、Microsoft 365アカウントがメンバーとして追加されたとすぐに自動的にユーザー アカウントにライセンスを割り当てる。
- 部署名などのユーザー アカウント属性に基づいて、ユーザー アカウントを特定のグループに動的に追加します。
- サービスとしてのソフトウェア (SaaS) アプリケーションのユーザーを自動的にプロビジョニングし、多要素認証 (MFA) および他の条件付きアクセス ポリシーを使用してそれらのアプリケーションへのアクセスを保護します。
- オンライン チーム サイトに対するアクセス許可SharePointレベルをプロビジョニングします。

## <a name="next-steps-for-cloud-only-identity"></a>クラウド専用 ID の次の手順

- [ユーザー アカウントを管理する](manage-microsoft-365-accounts.md)
- [ユーザー アカウントにライセンスを割り当てる](assign-licenses-to-user-accounts.md)
- [グループとグループ メンバーシップの管理](manage-microsoft-365-groups.md)
- [ユーザー アカウントのパスワードを管理する](manage-microsoft-365-passwords.md)
