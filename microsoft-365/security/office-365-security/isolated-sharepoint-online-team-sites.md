---
title: 分離した SharePoint Online チーム サイト
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 使用、要件、およびそれらで使用できる機能を含む、分離した SharePoint Online チーム サイトについて説明します。
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819535"
---
# <a name="isolated-sharepoint-online-team-sites"></a>分離した SharePoint Online チーム サイト

 **概要:** 分離した SharePoint Online チーム サイトの使用方法について説明します。
  
SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.
  
However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:
  
- 組織内での機密プロジェクト。
    
- 組織にとって機密度が高い、または知的財産となる場所。
    
- 組織によって実施された、または現在遵守されている法的措置のリソース。
    
- 一部が重複する複数の組織間で Microsoft 365 サブスクリプションを共有するものの、ほとんどの部分は個別のビジネス エンティティとして存在する場合。
    
分離したサイトの要件を以下に示します。
  
- SharePoint Online 管理者だけが、サイトの管理を実行できます。これには、サイトにアクセスし、カスタム アクセス許可を構成するためのグループ メンバーシップが含まれます。
    
- サイトのメンバーは、他のメンバーをチーム サイトに招待することはできません。
    
- Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.
    
The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.
  
分離したサイトは次のようにその他の機能と一緒に使用できます。
  
- Information Rights Management。ローカルにダウンロードしたり、組織全体で利用可能な別のサイトにアップロードしたりする場合でも、サイト上のリソースを暗号化されたままにします。
    
- データ損失防止。ユーザーがファイルなどのサイトのリソースを電子メールで送信できないようにします。
    
## <a name="next-steps"></a>次の手順

SharePoint Online チーム サイトを試用サブスクリプションで使用するには、「[Office 365 開発/テスト環境での分離した SharePoint Online チーム サイト](isolated-sharepoint-online-team-site-dev-test-environment.md)」にあるステップごとの指示を参照してください。
  
分離した SharePoint Online チーム サイトを実稼働に展開する準備ができたら、「[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)」にある設計に関するステップバイステップの考慮事項を参照してください。
  
## <a name="related-topics"></a>関連項目

[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)
  
[分離した SharePoint Online チーム サイトの管理](manage-an-isolated-sharepoint-online-team-site.md)

[分離した SharePoint Online チーム サイトの展開](deploy-an-isolated-sharepoint-online-team-site.md)


