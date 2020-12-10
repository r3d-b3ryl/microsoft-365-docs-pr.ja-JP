---
title: Microsoft 365 グループ、Teams、SharePoint の間の設定の相互作用
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 グループ、Teams、SharePoint の間の設定の相互作用について説明します。
ms.openlocfilehash: 23ef7a316417109ae51c221f1a25524dea3abeca
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613668"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 グループ、Teams、SharePoint の間の設定の相互作用

Microsoft 365 グループ、Microsoft Teams、および Microsoft 365 の SharePoint の一部の設定には、特に、共有とグループ/チームおよび SharePoint サイトの作成に関連するものがあります。 この記事では、これらの相互作用と、これらの設定の使用方法に関するベストプラクティスについて説明します。

![SharePoint、Teams、および groups の各機能のベン図](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>グループとチームに対する SharePoint 設定の影響

|SharePoint の設定|説明|Microsoft 365 グループとチームへの影響|推奨事項|
|:-----------------|:----------|:---------------------------------------|:-------------|
|組織とサイトの外部共有|サイト、ファイル、およびフォルダーを組織外のユーザーと共有できるかどうかを決定します。|SharePoint、グループ、および Teams の設定が一致しない場合は、チーム内のゲストがサイトへのアクセスをブロックされたり、予期しない外部アクセスが発生することがあります。|共有設定を変更する場合は、グループ設定、Teams 設定、およびグループに接続されたチームサイトの SharePoint サイト設定をチェックします。<br><br> 「[チーム内でゲストと共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)を行う」を参照してください。|
|ドメイン許可/ブロック|指定したドメインとのコンテンツの共有を許可または禁止します。|グループとチームは、SharePoint の許可または禁止リストを認識しません。 SharePoint で許可されていないドメインのユーザーは、チームを介して SharePoint サイトまたはコンテンツにアクセスすることができます。|Azure AD と SharePoint のドメインの許可/ブロック一覧を管理します。 ドメインを許可およびブロックするための、組織全体のガバナンスプロセスを作成します。<br><br>「 [SharePoint ドメインの設定](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)」および「 [Azure AD ドメインの設定](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。|
|特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可します。|SharePoint サイト、フォルダー、およびファイルを外部で共有できるセキュリティグループを指定します。|この設定では、チームの所有者が外部で teams を共有することはできません。 チームゲストは、関連付けられた SharePoint サイトにアクセスできます。||
|SharePoint サイトの共有設定|チームメンバーシップの外部でサイトを直接共有できるユーザーを決定します。 これは、チームまたはサイトの所有者によって構成されます。|この設定はチームに直接影響しませんが、ユーザーをサイトに追加して、チーム自体または他の Teams リソースにアクセスできないようにすることができます。|この設定を使用してサイトの共有を直接制限し、チームを通じてサイトアクセスを管理することを検討してください。|
|ユーザーが SharePoint のスタートページおよび OneDrive からサイトを作成できるようにする|ユーザーが新しい SharePoint サイトを作成できるかどうかを指定します。|この設定を無効にした場合、ユーザーはチームを作成して、グループに接続されたチームサイトを作成できます。||

## <a name="the-effects-of-groups-settings-on-teams"></a>Teams でのグループ設定の効果

|Microsoft 365 グループの設定|説明|Teams への影響|推奨事項|
|:---------------------------|:----------|:--------------|:-------------|
|名前付けポリシー|グループの名前のプレフィックスとサフィックス、およびグループの作成に対してブロックする単語を指定します。|チームを作成するユーザーにポリシーを適用します。||
|グループのゲスト アクセス|組織外のユーザーをグループに追加できるかどうかを指定します。|グループまたは Teams のゲスト共有設定がオフの場合は、チームをゲストと共有することはできません。|ゲスト共有の設定を変更するときは、Teams、グループ、およびチームに関連付けられている SharePoint サイトの設定を確認します。<br><br> 「[チーム内でゲストと共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)を行う」を参照してください。|
|セキュリティグループによるグループの作成|グループは、特定のセキュリティグループのメンバーのみが作成できます。|セキュリティグループのメンバーではないユーザーは、チームを作成できません。|グループを要求するプロセスに、チームまたは SharePoint サイトを要求するための手順が含まれていることを確認してください。|
|グループの有効期限ポリシー|アクティブに使用されていないグループが自動的に削除されるまでの期間を指定します。|グループが削除されると、チームと関連付けられた SharePoint サイトも削除されます。 アイテム保持ポリシーによって保護されたコンテンツは保持されます。|有効期限ポリシーを使用して、使用されていないチーム、グループ、およびサイトが増加しないようにします。|

## <a name="related-topics"></a>関連項目

[コラボレーションガバナンスの計画のステップバイステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーションのガバナンス計画を作成する](collaboration-governance-first.md)

[組織外のユーザーとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[SharePoint のサイト作成を管理する](https://docs.microsoft.com/sharepoint/manage-site-creation)
