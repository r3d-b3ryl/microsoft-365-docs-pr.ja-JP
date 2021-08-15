---
title: 管理者向け Microsoft 365 グループの概要
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: グループMicrosoft 365グループを使用すると、グループのユーザーに共有リソースのコレクションへのアクセス権を与えることによって、Microsoft 365全体のチームワークを促進できます。
ms.openlocfilehash: f054578e13fb4ee43aa158f615d3a2810769d6982981fcd534bb4ca8d234a70c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53826449"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>管理者向け Microsoft 365 グループの概要

Microsoft 365グループは、グループ全体のすべてのチームワークを促進するMicrosoft 365。 [Microsoft 365グループ] を使用すると、グループのユーザーに共有リソースのコレクションへのアクセス権を与えます。 これらのリソースは次のとおりです。

- 共有の Outlook 受信トレイ
- 共有の予定表
- SharePoint 文書ライブラリ
- Planner
- OneNote ノートブック
- Power BI
- Yammer (グループが Yammer から作成された場合)
- チーム (グループが Teams から作成された場合)
- ロードマップ (web のProject場合)
- Stream

グループをMicrosoft 365、これらの各リソースにアクセス許可を手動で割り当てる必要はありません。 グループにユーザーを追加すると、必要なアクセス許可が自動的に付与されます。

グループの作成を特定のユーザー セットに制限しない限り、任意のユーザー [がグループを作成できます](../../solutions/manage-creation-of-groups.md)。 グループの作成を制限すると、グループを作成できないユーザーは、SharePoint サイト、プランナー、チーム、Outlook グループ カレンダー、ストリーム グループ、Yammer グループ、OneDrive の共有ライブラリ、または共有 Power BI ワークスペースを作成できません。 これらのサービスでは、作成するユーザーがグループを作成できる必要があります。 ユーザーは、グループのメンバーである限り、Planner でのタスクの作成やチャットTeamsなど、グループ アクティビティに参加できます。

グループの役割は次のとおりです。

- **所有者** - グループ所有者は、メンバーを追加または削除できます。また、共有受信トレイから会話を削除する機能や、グループに関するさまざまな設定を変更する機能など、独自のアクセス許可を持っています。 グループ所有者は、グループ名の変更、説明や画像などの更新を行えます。
- **メンバー** - メンバーはグループ内のすべてのデータにアクセスできますが、グループの設定は変更できません。 既定では、グループ メンバーはゲストを招待してグループに参加させることができますが、[その設定は制御](manage-guest-access-in-groups.md)できます。
- **ゲスト** - グループ ゲストは、組織外のメンバーです。

グローバル管理者、ユーザー管理者、およびグループ管理者だけが、グループを作成および管理Microsoft 365 管理センター。 代理管理者 (たとえば、代理の管理者であるコンサルタント) になることはできません。

管理者は次のことが可能です。

- [グループを作成できるユーザーの指定](../../solutions/manage-creation-of-groups.md)
- [組織内のグループの名前付けポリシーの作成](../../solutions/groups-naming-policy.md)
- [グループを作成するときに使用するドメインの選択](../../solutions/choose-domain-to-create-groups.md)
- [グループへのゲスト アクセスの管理](manage-guest-access-in-groups.md)
- [削除したグループの復元](restore-deleted-group.md) (削除から 30 日以内)

Microsoft 365 グループのライフサイクルを管理するより自動化された方法が必要な場合は、有効期限ポリシーを使用して、特定の時間間隔でグループを期限切れにできます。 グループの所有者は、グループの有効期限の 30、15、および 1 日前にメールを受け取り、必要に応じてグループを更新できます。 詳細については、「Microsoft 365[有効期限ポリシー」を参照してください](../../solutions/microsoft-365-groups-expiration-policy.md)。

グループは、Microsoft 365 管理センターから、または [PowerShell を使用](../../enterprise/manage-microsoft-365-groups-with-powershell.md)して管理できます。

大企業や企業など、多くのユーザーを持っている場合は、さまざまな目的でグループを作成するユーザーが多い場合があります。 ベスト プラクティスについては、「グループ内のガバナンスの計画[Microsoft 365確認することを](../../solutions/collaboration-governance-overview.md)強くお勧めします。

## <a name="group-limits"></a>グループの制限

次の制限は、グループMicrosoft 365適用されます。

|最大...|値|
|:---------|:----|
|1 つのグループの所有者|100|
|ユーザーが作成できるグループ|250|
|管理者が作成できるグループ|500 K の既定のテナント制限まで|
|メンバー数 |1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。 <br>ユーザーは、カレンダーにアクセスするときに遅延に気付き、大規模なグループの会話にアクセスOutlook。|
|ユーザーがメンバーになれるグループの数|7,000|
|ファイルの記憶域|1 Terabyte + 10 GB/サブスクライブユーザー + 購入したその他のストレージ。 追加のストレージを無制限に購入できます。|
|グループ メールボックスのサイズ|50 GB|

組織が持Microsoft 365グループの既定の最大数は 500,000 です。 既定の制限を超える場合は、Microsoft サポートにお問い合わせください。 グループの制限の詳細については、「Microsoft 365グループ - 管理者[Microsoft 365」を参照してください](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

グループの使用状況にMicrosoft 365情報がある場合は、グループグループの管理が効果的です。 このMicrosoft 365 管理センターには、ストレージの使用、アクティブなグループの数、およびユーザーがグループを使用している方法を確認できるレポート ツールがあります。 詳細については[、「Microsoft 365レポート」を](../activity-reports/office-365-groups.md)参照してください。

## <a name="sensitivity-labels"></a>秘密度ラベル

組織内のユーザーがグループを作成するときに設定できるMicrosoft 365できます。 感度ラベルを使用して、次の設定を行います。 

- プライバシー (パブリックまたはプライベート)
- 外部ユーザーのアクセス
- 管理されていないデバイス アクセス

たとえば、高機密という名前のラベルを作成し、このラベルで作成されたグループをプライベートにし、外部ユーザーを許可することを指定できます。 組織内のユーザーがグループの作成時にこのラベルを選択すると、グループはプライベートに設定され、グループメンバーはグループに外部ユーザーを追加できない。

> [!IMPORTANT]
> 現在分類ラベルを使用している場合、感度ラベルが有効になると、グループを作成するユーザーは使用できなくなりました。 

感度ラベルの作成、管理、および使用の詳細については[、「Microsoft Teams、Microsoft 365](../../compliance/sensitivity-labels-teams-groups-sites.md)グループ、および SharePoint サイトのコンテンツを保護するために、感度ラベルを使用する」を参照してください。

## <a name="which-microsoft-365-plans-include-groups"></a>グループMicrosoft 365プランは何ですか?

オンラインMicrosoft 365が含Exchange OnlineサブスクリプションSharePointグループがサポートされます。 これには、Business Essentials プランと Business プレミアムプラン、E1、E3、E5 Enterpriseが含まれます。 グループは、グループを作成するユーザー (グループの "開催者" とも呼ばれる) のライセンスを引き受けます。 開催者がグループに必要な機能に対して適切なライセンスを持っている限り、そのライセンスはグループに伝達されます。

> [!NOTE]
> サービス ファミリとプランMicrosoft 365詳細については[、「Microsoft 365」を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。

Exchange 専用プランがある場合でも、Outlook のグループの共有受信トレイと共有予定表機能を取得できますが、ドキュメント ライブラリ、Planner、その他の機能は取得できません。

Microsoft 365グループは、グループをAzure Active Directory。 取得するグループ機能は、Azure Active Directoryサブスクリプション、およびグループの開催者に割り当てられているライセンスによって異なります。

> [!IMPORTANT]
> すべてのグループ機能について、Azure AD Premium サブスクリプションがある場合、ユーザーは AAD P1 ライセンスが割り当てられているかどうかに関してグループに参加できます。 ライセンスは適用されません。
> Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。 たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。 この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。

## <a name="related-content"></a>関連コンテンツ

[グループの詳細Microsoft 365 (](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)記事)\
[配布リストを Microsoft 365 グループにアップグレード](../manage/upgrade-distribution-lists.md)する (記事)\
[PowerShell Microsoft 365グループの管理](../../enterprise/manage-microsoft-365-groups-with-powershell.md)(記事)\
[SharePoint制限](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)(記事)\
[Microsoft Stream でグループとチャネルを整理](/stream/groups-channels-organization) する (記事)
