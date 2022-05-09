---
title: Microsoft 365 グループ、Teams、および SharePoint の間の設定の相互作用
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365 グループ、Teams、SharePoint間の設定の相互作用について説明します
ms.openlocfilehash: 64f00fcb5ace9e2f2f4a6630def6beb0a51d40bf
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064345"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 グループ、Teams、および SharePoint の間の設定の相互作用

Microsoft 365のMicrosoft 365 グループ、Microsoft Teams、およびSharePointに関する一部の設定 (特に共有とグループ/チーム、SharePoint サイトの作成に関連) が互いに重複しています。 この記事では、これらの相互作用の説明と、これらの設定を操作する方法のベスト プラクティスについて説明します。

![SharePoint、Teams、およびグループの機能のベン図。](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>SharePoint設定がグループとチームに及ぼす影響

|SharePoint の設定|説明|Microsoft 365 グループとTeamsへの影響|推奨事項|
|:-----------------|:----------|:---------------------------------------|:-------------|
|組織とサイトの外部共有|サイト、ファイル、フォルダーを組織外のユーザーと共有できるかどうかを決定します。|SharePoint、グループ、Teamsの設定が一致しない場合、チーム内のゲストがサイトへのアクセスをブロックされたり、予期しない外部アクセスが発生したりする可能性があります。|共有設定を変更する場合は、グループに接続されたチーム サイトのグループ設定、Teams設定、SharePoint サイト設定をオンにします。<br><br> [「チーム内のゲストと共同作業する」を](./collaborate-as-team.md)参照してください|
|ドメインの許可/ブロック|指定したドメインとのコンテンツの共有を許可または禁止します。|グループとTeamsでは、許可リストまたはブロックリストSharePoint認識されません。 SharePointで許可されていないドメインのユーザーは、チームを通じてSharePointサイトまたはコンテンツにアクセスできます。|Azure AD と SharePoint のドメイン許可リストまたはブロック リストを一緒に管理します。 ドメインを許可およびブロックするための組織全体のガバナンス プロセスを作成します。<br><br>「[SharePoint ドメイン設定](/sharepoint/restricted-domains-sharing)」と「[Azure AD ドメイン設定](/azure/active-directory/b2b/allow-deny-list)」を参照してください|
|特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可する|SharePoint サイト、フォルダー、ファイルを外部で共有できるセキュリティ グループを指定します。|この設定では、チーム所有者がチームを外部で共有することはできません。 チーム ゲストは、関連付けられたSharePoint サイトにアクセスできます。||
|SharePoint サイトの共有設定|チーム メンバーシップの外部でサイトを直接共有できるユーザーを決定します。 これは、チームまたはサイトの所有者によって構成されます。|この設定はチームに直接影響を与えませんが、ユーザーをサイトに追加し、チーム自体や他のTeams リソースにアクセスできないようにすることができます。|この設定を使用してサイトの共有を直接制限し、チームを通じてサイト アクセスを管理することを検討してください。|
|ユーザーが SharePoint スタート ページと OneDrive からサイトを作成できるようにする|ユーザーが新しい SharePoint サイトを作成できるかどうかを指定します。|この設定をオフにした場合でも、ユーザーはチームを作成してグループに接続されたチーム サイトを作成できます。||

## <a name="the-effects-of-groups-settings-on-teams"></a>グループ設定がチームに及ぼす影響

|Microsoft 365 グループの設定|説明|Teamsへの影響|推奨事項|
|:---------------------------|:----------|:--------------|:-------------|
|名前付けポリシー|グループ名のプレフィックスとサフィックス、およびグループ作成時にブロックされる単語を指定します|ポリシーは、チームを作成するユーザーに適用されます。||
|グループのゲスト アクセス|組織外のユーザーをグループに追加できるかどうかを指定します。|グループまたはTeamsのゲスト共有設定のいずれかがオフの場合、チームをゲストと共有することはできません。|ゲスト共有設定を変更するときは、チームに関連付けられているTeams、グループ、およびSharePoint サイトの設定を確認します。<br><br> [「チーム内のゲストと共同作業する」を](./collaborate-as-team.md)参照してください|
|セキュリティ グループ別のグループ作成|特定のセキュリティ グループのメンバーのみがグループを作成できます。|セキュリティ グループのメンバーではないユーザーは、チームを作成できません。|グループを要求するプロセスに、チームまたはSharePoint サイトを要求する手順が含まれていることを確認します。|
|グループの有効期限ポリシー|アクティブに使用されていないグループが自動的に削除される期間を指定します。|グループが削除されると、チームと関連するSharePointサイトも削除されます。 アイテム保持ポリシーによって保護されているコンテンツは保持されます。|有効期限ポリシーを使用して、未使用のチーム、グループ、サイトのスプロールを回避します。|

## <a name="related-topics"></a>関連項目

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[組織外部のユーザーとの共有](./collaborate-with-people-outside-your-organization.md)

[SharePoint のサイト作成を管理する](/sharepoint/manage-site-creation)