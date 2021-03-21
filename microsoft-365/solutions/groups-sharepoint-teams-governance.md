---
title: Microsoft 365 グループ、Teams、および SharePoint の間の設定の相互作用
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
description: Microsoft 365 グループ、Teams、SharePoint の間の設定の操作について説明します。
ms.openlocfilehash: ba3578903731a66d66c943f8daaec1a61943228c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921014"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 グループ、Teams、および SharePoint の間の設定の相互作用

Microsoft 365 の Microsoft 365 グループ、Microsoft Teams、SharePoint の一部の設定は、特に共有とグループ/チームと SharePoint サイトの作成に関連し、互いに重なっています。 この記事では、これらの設定を操作する方法に関するこれらの操作とベスト プラクティスについて説明します。

![SharePoint、Teams、およびグループ機能のベン図](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>グループとチームに対する SharePoint 設定の影響

|SharePoint の設定|説明|Microsoft 365 グループと Teams への影響|推奨事項|
|:-----------------|:----------|:---------------------------------------|:-------------|
|組織とサイトの外部共有|サイト、ファイル、フォルダーを組織外のユーザーと共有できるかどうかを指定します。|SharePoint、グループ、Teams の設定が一致しない場合、チーム内のゲストがサイトへのアクセスをブロックされる可能性があります。または予期しない外部アクセスが発生する可能性があります。|共有設定を変更する場合は、グループに接続されたチーム サイトのグループ設定、Teams 設定、および SharePoint サイト設定を確認します。<br><br> 「チーム [のゲストと共同作業する」を参照してください。](./collaborate-as-team.md)|
|ドメインの許可/ブロック|指定したドメインとコンテンツが共有されるのを許可または防止します。|グループと Teams は SharePoint 許可リストまたはブロックリストを認識しない。 SharePoint で禁止されているドメインのユーザーは、チームを通じて SharePoint サイトまたはコンテンツにアクセスできます。|Azure ADおよび SharePoint のドメイン許可/ブロックリストを一緒に管理します。 ドメインを許可およびブロックする組織全体のガバナンス プロセスを作成します。<br><br>[「SharePoint ドメイン設定」および](/sharepoint/restricted-domains-sharing)[「Azure ドメイン設定AD」を参照してください。](/azure/active-directory/b2b/allow-deny-list)|
|特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可します。|SharePoint サイト、フォルダー、およびファイルを外部で共有できるセキュリティ グループを指定します。|この設定では、チームの所有者がチームを外部で共有できない場合があります。 チームゲストは、関連付けられた SharePoint サイトにアクセスできます。||
|SharePoint サイト共有設定|チーム メンバーシップの外部でサイトを直接共有できるユーザーを指定します。 これは、チームまたはサイトの所有者によって構成されます。|この設定はチームに直接影響しませんが、ユーザーがサイトに追加され、チーム自体や他の Teams リソースにアクセスできない場合があります。|この設定を使用して、サイトの共有を直接制限し、チームを通じてサイト アクセスを管理する方法を検討してください。|
|SharePoint スタート ページと OneDrive からサイトを作成する|ユーザーが新しい SharePoint サイトを作成できる場合に指定します。|この設定をオフにした場合でも、ユーザーはチームを作成してグループに接続されたチーム サイトを作成できます。||

## <a name="the-effects-of-groups-settings-on-teams"></a>グループ設定がチームに与える影響

|Microsoft 365 グループの設定|説明|Teams への影響|推奨事項|
|:---------------------------|:----------|:--------------|:-------------|
|名前付けポリシー|グループ名のプレフィックスとサフィックス、およびグループ作成のブロックされた単語を指定します。|ポリシーは、チームを作成するユーザーに適用されます。||
|グループのゲスト アクセス|組織外のユーザーをグループに追加できる場合に指定します。|グループまたは Teams のゲスト共有設定がオフの場合、チームはゲストと共有できません。|ゲスト共有設定を変更する場合は、チームに関連付けられている Teams、グループ、および SharePoint サイトの設定を確認します。<br><br> 「チーム [のゲストと共同作業する」を参照してください。](./collaborate-as-team.md)|
|セキュリティ グループによるグループ作成|グループを作成できるのは、特定のセキュリティ グループのメンバーのみです。|セキュリティ グループのメンバーではないユーザーは、チームを作成できます。|グループを要求するプロセスに、チームまたは SharePoint サイトを要求する手順が含まれています。|
|グループの有効期限ポリシー|アクティブに使用されていないグループが自動的に削除される期間を指定します。|グループを削除すると、チームと関連付けられた SharePoint サイトも削除されます。 アイテム保持ポリシーによって保護されたコンテンツは保持されます。|有効期限ポリシーを使用して、未使用のチーム、グループ、サイトの広がりを回避します。|

## <a name="related-topics"></a>関連項目

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[組織外部のユーザーとの共有](./collaborate-with-people-outside-your-organization.md)

[SharePoint のサイト作成を管理する](/sharepoint/manage-site-creation)