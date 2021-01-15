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
ms.openlocfilehash: 55bdf2999610310babb60b6938afb97732e5a7a0
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845093"
---
# <a name="isolated-sharepoint-online-team-sites"></a>分離した SharePoint Online チーム サイト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **概要:** 分離した SharePoint Online チーム サイトの使用方法について説明します。

SharePoint Online チーム サイトは、コラボレーション用のスペースをすばやく作成する簡単な方法です。ユーザーは、Microsoft Office 365 のノート、ドキュメント、記事、予定表、およびその他のリソースで共同作業できます。SharePoint Online チーム サイトは、Microsoft 365 グループをベースとしており、グループ メンバーや組織全体の非公開セットを使用したオープンなコラボレーションを可能にする簡略化された管理モデルを備えています。既定の SharePoint Online チーム サイトでは、Microsoft 365 のグループのメンバーが他のユーザーを招待し、アクセス許可の設定を制御することが可能です。

ただし、グループ メンバーシップによって制御されるサイト アクセスと、SharePoint 管理者によって管理される SharePoint Online のアクセス許可レベルが必要になる場合があります。 これは、分離したサイトと呼ばれ、コラボレーション、コンテンツの表示、またはサイトの管理を実行するユーザーのセットに分離されています。 以下を対象として、分離したサイトが必要になることがあります。

- 組織内での機密プロジェクト。

- 組織にとって機密度が高い、または知的財産となる場所。

- 組織によって実施された、または現在遵守されている法的措置のリソース。

- 一部が重複する複数の組織間で Microsoft 365 サブスクリプションを共有するものの、ほとんどの部分は個別のビジネス エンティティとして存在する場合。

分離したサイトの要件を以下に示します。

- SharePoint Online 管理者だけが、サイトの管理を実行できます。これには、サイトにアクセスし、カスタム アクセス許可を構成するためのグループ メンバーシップが含まれます。

- サイトのメンバーは、他のメンバーをチーム サイトに招待することはできません。

- 分離したサイトのメンバーではないユーザーは、サイトへのアクセスを要求できません。サイトに関連付けられているいずれかの URL にアクセスしようとすると、アクセスが拒否された Web ページが表示されます。

一元的なアクセス制御を必要とすることと SharePoint Online 管理者によるカスタム アクセス許可とのトレードオフは、時間が経過してもサイトが分離されたままであるということです。たとえば、現在のメンバーは、意図的であれ偶然であれ、サイトのメンバーではない Microsoft 365 サブスクリプション内の他のユーザーを招待したり、他のユーザーのためにカスタムのアクセス許可を構成したりすることはできません。

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
