---
title: Microsoft 365専用 ID
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
description: サブスクリプションでクラウド専用 ID を使用している場合Microsoft 365グループを作成する方法について説明します。
---

# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365専用 ID

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

クラウド専用 ID モデルを選択した場合は、Microsoft 365 サブスクリプション用の Azure Active Directory (Azure AD) テナントが既に存在し、すべてのユーザー、グループ、連絡先を格納できます。 手順 [2](protect-your-global-administrator-accounts.md) の管理者アカウントと、このソリューションの手順 [3](microsoft-365-secure-sign-in.md) のユーザー アカウントの保護を設定した後、組織で必要な新しいアカウントとグループの作成を開始する準備ができました。

クラウド専用 ID の基本的なコンポーネントを次に示します。
 
![クラウド専用 ID の基本的なコンポーネント。](../media/about-microsoft-365-identity/cloud-only-identity.png)

組織のユーザーとユーザー アカウントは、さまざまな方法で分類できます。 たとえば、従業員であり、永続的なステータスを持つユーザーもいます。 一部のベンダー、請負業者、または一時的なステータスを持つパートナーがあります。 一部のユーザー は、ユーザー アカウントを持たず、対話とコラボレーションをサポートするために特定のサービスとリソースへのアクセスを許可する必要がある外部ユーザーです。 例:

- テナント アカウントは、組織内でクラウド サービスのライセンスを付与したユーザーを表します。

- B2B (Business to Busines) アカウントは、コラボレーションへの参加のために招待された組織外部のユーザーを表します。

組織内のユーザーの種類を確認します。 グループ化とは何ですか? たとえば、ユーザーを組織に対して高レベルの機能または目的でグループ化できます。

また、一部のクラウド サービスを、ユーザー アカウントを持たない組織外のユーザーと共有できます。この場合、このような外部ユーザーのグループも指定する必要があります。

クラウド環境の管理を簡略化Azure AD、複数の目的でグループを使用できます。 たとえば、グループを使用Azure AD、次の方法を実行できます。

- グループ ベースのライセンスを使用して、Microsoft 365アカウントがメンバーとして追加されたとすぐに自動的にユーザー アカウントにライセンスを割り当てる。
- 部署名などのユーザー アカウント属性に基づいて、ユーザー アカウントを特定のグループに動的に追加します。
- サービスとしてのソフトウェア (SaaS) アプリケーションのユーザーを自動的にプロビジョニングし、多要素認証 (MFA) および他の条件付きアクセス ポリシーを使用してそれらのアプリケーションへのアクセスを保護します。
- チームおよびオンライン チーム サイトに対するアクセス許可SharePointレベルをプロビジョニングします。

## <a name="next-steps-for-cloud-only-identity"></a>クラウド専用 ID の次の手順

- [ユーザー アカウントを管理する](manage-microsoft-365-accounts.md)
- [ユーザー アカウントにライセンスを割り当てる](assign-licenses-to-user-accounts.md)
- [グループとグループ メンバーシップの管理](manage-microsoft-365-groups.md)
- [ユーザー アカウントのパスワードを管理する](manage-microsoft-365-passwords.md)
