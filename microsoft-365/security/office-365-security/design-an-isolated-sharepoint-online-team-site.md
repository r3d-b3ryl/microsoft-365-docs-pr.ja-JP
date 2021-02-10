---
title: 分離した SharePoint Online チーム サイトの設計
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 分離した SharePoint Online チーム サイトを設計します。アクセス許可レベルの決定、アクセス グループを持つユーザーへのアクセス許可の割り当て、入れ子になった Azure AD グループがあります。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165513"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>分離した SharePoint Online チーム サイトの設計

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


 **概要:** 分離した SharePoint Online チーム サイトの設計プロセスをステップごとに示します。

この記事では、分離した SharePoint Online チーム サイトを作成する前に行う必要がある設計上の主要な決定事項について説明します。

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>フェーズ 1:SharePoint グループおよびアクセス許可レベルを決定します。

既定では、すべての SharePoint Online チーム サイトは次の SharePoint グループを使用して作成されます。

- \<site name> メンバー

- \<site name> 訪問者

- \<site name> 所有者

これらのグループは、Microsoft 365 および Azure Active Directory (AD) グループとは別のグループであり、サイトのリソースにアクセス許可を割り当てる基礎となります。

SharePoint グループのメンバーがサイトで実行できる内容を決定する特定のアクセス許可のセットが、アクセス許可レベルになります。SharePoint Online チーム サイトでは、既定では次の 3 つのアクセス許可レベルがあります。編集、読み取り、フル コントロールです。次の表は、SharePoint グループと割り当てられるアクセス許可レベルとの既定の相関関係を示しています。

****

|SharePoint グループ|アクセス許可レベル|
|---|---|
|\<site name> メンバー|編集|
|\<site name> 訪問者|読み取り|
|\<site name> 所有者|フル コントロール|
|

 **ベスト プラクティス:** 追加の SharePoint グループおよびアクセス許可レベルを作成できます。ただし、分離した SharePoint Online サイトには、既定の SharePoint グループおよびアクセス許可レベルを使用することをお勧めします。

既定の SharePoint グループとアクセス許可レベルを次に示します。

![SharePoint Online サイトの既定の SharePoint グループとアクセス許可レベル。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>フェーズ 2:アクセス グループを使用してアクセス許可をユーザーに割り当てる

ユーザー アカウント、またはユーザー アカウントがメンバーである Microsoft 365 または Azure AD グループを SharePoint グループに追加することで、ユーザーにアクセス許可を割り当てできます。 追加されたユーザー アカウントには、Microsoft 365 または Azure AD グループのメンバーシップを介して直接的または間接的に、SharePoint グループに関連付けられたアクセス許可レベルが割り当てられます。

既定の SharePoint グループを使用した例:

- Members SharePoint **\<site name> グループのメンバー** には、ユーザー アカウントとグループの両方を含め、編集アクセス許可 **レベルが割り** 当てられます。

- ユーザー アカウントと **\<site name> グループの** 両方を含む、Visitors SharePoint グループのメンバーには、読み取りアクセス許可 **レベルが割り** 当てられます。

- 所有者 SharePoint **\<site name> グループのメンバー** には、ユーザー アカウントとグループの両方を含め、フル コントロールのアクセス許可 **レベルが割り** 当てられます。

 **ベスト プラクティス:** 個々のユーザー アカウントを使用してアクセス許可を管理することもできますが、代わりにアクセス グループと呼ばれる 1 つの Azure AD グループを使用することをお勧めします。この方法は、SharePoint グループごとにユーザー アカウントのリストを管理するのではなく、アクセス グループのメンバーシップでアクセス許可の管理を簡略化するものです。

Microsoft 365 の Azure ADグループは、Microsoft 365 グループとは異なります。 Azure ADグループは、Microsoft 365 管理センターに表示され、その種類が **[** セキュリティ] に設定され、メール アドレスが設定されません。 以下で Azure AD グループを管理できます。

- Active Directory Domain Services (AD DS)

    これらのグループは、オンプレミスの AD DS インフラストラクチャで作成され、Microsoft 365 サブスクリプションに同期されたグループです。 Microsoft 365 管理センターでは、これらのグループの状態は Active Directory と同期 **済みです**。

- Office 365

    これらは、Microsoft 365 管理センター、Azure ポータル、または Microsoft PowerShell を使用して作成されたグループです。 Microsoft 365 管理センターでは、これらのグループの状態は **クラウド****です**。

 **ベスト プラクティス:** オンプレミスの AD DS を使用し、Microsoft 365 サブスクリプションと同期している場合は、AD DS でユーザーとグループの管理を実行します。

分離した SharePoint Online チーム サイトの場合、推奨されるグループ構造は次のようになります。

****

|SharePoint グループ|Azure AD ベースのアクセス グループ|権限レベル|
|---|---|---|
|\<site name> メンバー|\<site name> メンバー|編集|
|\<site name> 訪問者|\<site name> 閲覧者|読み取り|
|\<site name> 所有者|\<site name> 管理者|フル コントロール|
|

 **ベスト プラクティス:** Microsoft 365 または Azure AD グループを SharePoint グループのメンバーとして使用することもできますが、Azure ADすることをお勧めします。 Azure ADグループは、AD DS または Microsoft 365 を通じて管理されます。入れ子になったグループを使用してアクセス許可を割り当てる柔軟性が向上します。

Azure ベースのアクセス グループを使用するように構成された既定AD SharePoint グループを次に示します。

![アクセス グループを既定の SharePoint Online サイト グループのメンバーとして使用する。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

3 つのアクセス グループを設計するときは、以下の点にご注意ください。

- Admins アクセス グループには、チーム **\<site name>** サイトを管理している少数の SharePoint Online 管理者に対応するメンバーが少数存在する必要があります。

- ほとんどのサイト メンバーは、メンバーまたは閲覧 **\<site name> 者****\<site name> のアクセス グループ** に参加しています。 Members アクセス グループのサイト **\<site name> メンバー** は、サイト内のリソースを削除または変更する機能を持つため、メンバーシップを慎重に検討してください。 疑問に思った場合は、サイト メンバーを Viewers アクセス **\<site name> グループに** 追加します。

ProjectX という名前の分離されたサイトの SharePoint グループとアクセス グループの例を次に示します。

![ProjectX という名前の SharePoint Online サイトにアクセス グループを使用する例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>フェーズ 3: ネストされた Azure AD グループを使用する

少数のユーザーに限定されるプロジェクトの場合、ほとんどのシナリオはサイトの SharePoint グループに追加される単一レベルの Azure AD ベースのアクセス グループに収まります。ただし、多数のユーザーがおり、それらのユーザーが既に確立された Azure AD グループのメンバーである場合、ネストされたグループ、つまり他のグループがメンバーとして含まれるグループを使用することで簡単に SharePoint アクセス許可を割り当てることができます。

たとえば、営業部門、マーケティング部門、エンジニアリング部門、法律部門の役員間でコラボレーションするための分離した SharePoint Online チーム サイトを作成したいと考えており、それらの部門には既に役員のユーザー アカウントのメンバーシップを持つ独自のグループが存在するとします。この場合、新しいサイト メンバー用に新しいグループを作成して、それぞれの役員ユーザー アカウントをすべてそこに含めるのではなく、各部門の既存の役員グループを新しいグループに入れます。

 複数の組織間で Microsoft 365 サブスクリプションを共有している場合、組織の分離されたサイトの単一レベルのグループ メンバーシップは、ユーザー アカウントの数が多く、管理が困難になる可能性があります。 この場合、組織内のグループが含まれるネストされた Azure AD グループを組織ごとに使用して、アクセス許可を管理することができます。

ネストされた Azure AD グループを使用するには、以下を実行します。

1. ユーザー アカウントを含める Azure AD グループを特定するか作成し、適切なユーザー アカウントをメンバーとして追加します。

2. 他の Azure AD グループを含めるコンテナーとなる Azure AD ベースのアクセス グループを作成し、それらのグループをメンバーとして追加します。

3.  コンテナー アクセス グループの適切なアクセス レベルについては、SharePoint グループと、対応するアクセス許可レベルを識別します。

> [!NOTE]
> 入れ子になった Microsoft 365 グループは使用できません。

ProjectX メンバー アクセス グループの入れ子になった Azure ADグループの例を次に示します。

![ProjectX サイトのメンバー アクセス グループに入れ子になったアクセス グループを使用する例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

リサーチ チーム、エンジニアリング チーム、および Project リード チームのすべてのユーザー アカウントはサイト メンバーを対象と考え、Azure AD グループを ProjectX メンバー アクセス グループに追加する方が簡単です。

## <a name="next-step"></a>次の手順

分離したサイトを運用環境で作成および構成する準備ができたら、「[Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md)」を参照してください。

## <a name="see-also"></a>関連項目

[分離した SharePoint Online チーム サイト](isolated-sharepoint-online-team-sites.md)

[分離した SharePoint Online チーム サイトの管理](manage-an-isolated-sharepoint-online-team-site.md)

[分離した SharePoint Online チーム サイトの展開](deploy-an-isolated-sharepoint-online-team-site.md)
