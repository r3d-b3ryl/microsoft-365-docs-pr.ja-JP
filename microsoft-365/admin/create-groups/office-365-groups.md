---
title: 管理者向け Microsoft 365 グループの概要
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 グループを使用すると、ユーザーのグループに共有リソースのコレクションへのアクセス権を付与することで、Microsoft 365 全体でチームワークを促進できます。
ms.openlocfilehash: 4e0668ea1204dd9aa3fd9891574f3fe17a1b5e15
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084171"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>管理者向け Microsoft 365 グループの概要

Microsoft 365 グループは、Microsoft 365 全体でチームワークを推進する基盤となるメンバーシップ サービスです。 Microsoft 365 グループを使用すると、ユーザー グループに、共有するコラボレーション リソースのコレクションへのアクセス権を付与できます。 これらのリソースは次のとおりです。

- 共有の Outlook 受信トレイ
- 共有の予定表
- SharePoint 文書ライブラリ
- Planner
- OneNote ノートブック
- Power BI
- Yammer (グループが Yammer から作成された場合)
- チーム (グループが Teams から作成された場合)
- ロードマップ (Project for the web を所有している場合)
- Stream

Microsoft 365 グループでは、これらの各リソースに手動でアクセス許可を割り当てる必要はありません。 グループにユーザーを追加すると、必要なアクセス許可が自動的に付与されます。

グループの作成を [特定のユーザー セットに制限しない限り、任意のユーザーがグループを作成](../../solutions/manage-creation-of-groups.md)できます。 グループの作成を制限すると、グループを作成できないユーザーは、SharePoint サイト、Planners、teams、Outlook グループ 予定表、Stream グループ、Yammer グループ、OneDrive の共有ライブラリ、または共有 Power BI ワークスペースを作成できません。 これらのサービスでは、作成するユーザーがグループを作成できるようにする必要があります。 ユーザーは、グループのメンバーである限り、Planner でのタスクの作成や Teams チャットの使用など、グループ アクティビティに引き続き参加できます。

グループの役割は次のとおりです。

- **所有者** - グループの所有者は、メンバーを追加または削除したり、共有受信トレイから会話を削除したり、グループに関するさまざまな設定を変更したりするなど、固有のアクセス許可を持つことができます。グループの所有者はグループの名前を変更したり、説明や図などを更新したりできます。
- **メンバー** - メンバーはグループ内のすべてのデータにアクセスできますが、グループの設定は変更できません。 既定では、グループ メンバーはゲストを招待してグループに参加させることができますが、[その設定は制御](manage-guest-access-in-groups.md)できます。
- **ゲスト** - グループ ゲストは、組織外のメンバーです。

<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Microsoft 365 管理センター</a>でグループを作成および管理できるのは、グローバル管理者、ユーザー管理者、およびグループ管理者のみです。 代理管理者 (たとえば、代理の管理者であるコンサルタント) になることはできません。

管理者は次のことが可能です。

- [グループを作成できるユーザーの指定](../../solutions/manage-creation-of-groups.md)
- [組織内のグループの名前付けポリシーの作成](../../solutions/groups-naming-policy.md)
- [グループを作成するときに使用するドメインの選択](../../solutions/choose-domain-to-create-groups.md)
- [グループへのゲスト アクセスの管理](manage-guest-access-in-groups.md)
- [削除したグループの復元](restore-deleted-group.md) (削除から 30 日以内)

Microsoft 365 グループのライフサイクルを管理するより自動化された方法が必要な場合は、有効期限ポリシーを使用して、特定の時間間隔でグループの有効期限を切ることができます。 グループの所有者は、グループの有効期限の 30 日前、15 日、1 日前にメールを受け取り、必要に応じてグループを更新できます。 参照: [Microsoft 365 グループの有効期限ポリシー](../../solutions/microsoft-365-groups-expiration-policy.md)。

グループは、Microsoft 365 管理センターから、または [PowerShell を使用](../../enterprise/manage-microsoft-365-groups-with-powershell.md)して管理できます。

大企業や企業など、ユーザーが多い場合は、さまざまな目的でグループを作成するユーザーが多い可能性があります。 ベスト プラクティスについては、 [Microsoft 365 グループのガバナンスの計画](../../solutions/collaboration-governance-overview.md) を確認することを非常にお勧めします。

## <a name="group-limits"></a>グループの制限

Microsoft 365 グループには、次の制限が適用されます。

|最大...|値|
|:---------|:----|
|1 つのグループの所有者|100|
|ユーザーが作成できるグループ|250|
|管理者が作成できるグループ|既定のテナント制限 500 K まで|
|メンバー数 |1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。 <br>Outlook の大規模なグループの予定表と会話にアクセスすると、ユーザーが遅延に気付く場合があります。|
|ユーザーがメンバーになれるグループの数|7,000|
|ファイルの記憶域|サブスクライブしたユーザーあたり 1 テラバイト + 10 GB、購入したその他のストレージ。 追加のストレージを無制限に購入できます。|
|グループ メールボックスのサイズ|50 GB|

組織で使用できる Microsoft 365 グループの既定の最大数は 500,000 です。 既定の制限を超えるには、Microsoft サポートに連絡する必要があります。 Microsoft 365 グループ制限の詳細については、「[Microsoft 365 グループ - 管理 ヘルプ」を](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)参照してください。

Microsoft 365 グループの管理は、グループの使用状況に関する実用的な情報がある場合に、より効果的です。 Microsoft 365 管理センターには、ストレージの使用、アクティブなグループの数、ユーザーがグループを使用している方法を確認できるレポート ツールがあります。 詳細については、「 [管理センターの Microsoft 365 レポート](../activity-reports/office-365-groups.md) 」を参照してください。

## <a name="sensitivity-labels"></a>秘密度ラベル

組織内のユーザーが Microsoft 365 グループを作成するときに設定できる秘密度ラベルを作成できます。 秘密度ラベルを使用すると、次の項目を構成できます。 

- プライバシー (パブリックまたはプライベート)
- 外部ユーザーのアクセス
- アンマネージド デバイス アクセス

たとえば、 *Highly Confidential* という名前のラベルを作成し、このラベルを使用して作成されたすべてのグループをプライベートにし、外部ユーザーを許可しないように指定できます。 組織内のユーザーがグループの作成時にこのラベルを選択すると、グループはプライベートに設定され、グループ メンバーはグループに外部ユーザーを追加できません。

> [!IMPORTANT]
> 現在分類ラベルを使用している場合、機密ラベルが有効になると、グループを作成するユーザーは分類ラベルを使用できなくなります。 

秘密度ラベルの作成、管理、および使用の詳細については、「 [機密ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../../compliance/sensitivity-labels-teams-groups-sites.md)」を参照してください。

## <a name="which-microsoft-365-plans-include-groups"></a>グループを含む Microsoft 365 プランはどれですか?

Exchange Onlineおよび SharePoint Online を持つ Microsoft 365 サブスクリプションは、グループをサポートします。 これには、Business Essentials プランと Business Premium プラン、Enterprise E1、E3、E5 プランが含まれます。 グループは、グループを作成するユーザーのライセンスを引き受ける (グループの "開催者" とも呼ばれます)。 開催者がグループに必要な機能に対して適切なライセンスを持っている限り、そのライセンスはグループに伝達されます。

> [!NOTE]
> Microsoft 365 サービス ファミリとプランの詳細については、 [Microsoft 365 プランのオプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)に関するページを参照してください。

Exchange のみのプランをお持ちの場合でも、Outlook でグループの共有受信トレイと共有予定表機能を取得できますが、ドキュメント ライブラリ、Planner、その他の機能は取得できません。

Microsoft 365 グループは、Azure Active Directory で動作します。 取得するグループ機能は、所有している Azure Active Directory サブスクリプションと、グループの開催者に割り当てられているライセンスによって異なります。

> [!IMPORTANT]
> すべてのグループ機能について、Azure AD Premium サブスクリプションがある場合、ユーザーは AAD P1 ライセンスが割り当てられているかどうかにかかわらず、グループに参加できます。 ライセンスは適用されません。
> Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。 たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。 この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 グループについて学習](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)する (記事)\
[配布リストをMicrosoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md) (記事)\
[PowerShell を使用してMicrosoft 365 グループを管理](../../enterprise/manage-microsoft-365-groups-with-powershell.md)する (記事)\
[SharePoint Online の制限](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (記事)\
[Microsoft Streamでグループとチャネルを整理する](/stream/groups-channels-organization) (記事)
