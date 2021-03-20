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
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 グループについて説明します。
ms.openlocfilehash: 18cb37a4aae7a163d2e198194251abc727b48848
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910608"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>管理者向け Microsoft 365 グループの概要

Microsoft 365 グループは、Microsoft 365 全体のすべてのチームワークを促進する基盤的なメンバーシップ サービスです。 Microsoft 365 グループを使用すると、グループのユーザーに共有リソースのコレクションへのアクセス権を与えます。 これらのリソースは次のとおりです。

- 共有の Outlook 受信トレイ
- 共有の予定表
- SharePoint 文書ライブラリ
- Planner
- OneNote ノートブック
- Power BI
- Yammer (グループが Yammer から作成された場合)
- チーム (グループが Teams から作成された場合)
- ロードマップ (Web 用 Project がある場合)
- Stream

Microsoft 365 グループでは、これらの各リソースに手動でアクセス許可を割り当てる必要はありません。 グループにユーザーを追加すると、必要なアクセス許可が自動的に付与されます。

グループの作成を特定のユーザー セットに制限しない限り、任意のユーザー [がグループを作成できます](../../solutions/manage-creation-of-groups.md)。 グループの作成を制限すると、グループを作成できないユーザーは SharePoint サイト、Planners、またはチームを作成できません。 これらのサービスでは、作成するユーザーがグループを作成できる必要があります。 ユーザーは、グループのメンバーである限り、Planner でのタスクの作成や Teams チャットの使用など、グループ アクティビティに参加できます。

グループの役割は次のとおりです。

- **所有者** - グループ所有者は、メンバーを追加または削除できます。また、共有受信トレイから会話を削除する機能や、グループに関するさまざまな設定を変更する機能など、独自のアクセス許可を持っています。 グループ所有者は、グループ名の変更、説明や画像などの更新を行えます。
- **メンバー** - メンバーはグループ内のすべてのデータにアクセスできますが、グループの設定は変更できません。 既定では、グループ メンバーはゲストを招待してグループに参加させることができますが、[その設定は制御](manage-guest-access-in-groups.md)できます。
- **ゲスト** - グループ ゲストは、組織外のメンバーです。

Microsoft 365 管理センターでグループを作成および管理できるのは、グローバル管理者、ユーザー管理者、およびグループ管理者のみです。 代理管理者 (たとえば、代理の管理者であるコンサルタント) になることはできません。

管理者は次のことが可能です。

- [グループを作成できるユーザーの指定](../../solutions/manage-creation-of-groups.md)
- [組織内のグループの名前付けポリシーの作成](../../solutions/groups-naming-policy.md)
- [グループを作成するときに使用するドメインの選択](../../solutions/choose-domain-to-create-groups.md)
- [グループへのゲスト アクセスの管理](manage-guest-access-in-groups.md)
- [削除したグループの復元](restore-deleted-group.md) (削除から 30 日以内)

Microsoft 365 グループのライフサイクルを管理するためのより自動化された方法が必要な場合は、有効期限ポリシーを使用して、特定の時間間隔でグループを期限切れにできます。 グループの所有者は、グループの有効期限の 30、15、および 1 日前にメールを受け取り、必要に応じてグループを更新できます。 「Microsoft [365 グループの有効期限ポリシー」を参照してください](../../solutions/microsoft-365-groups-expiration-policy.md)。

グループは、Microsoft 365 管理センターから、または [PowerShell を使用](../../enterprise/manage-microsoft-365-groups-with-powershell.md)して管理できます。

大企業や企業など、多くのユーザーを持っている場合は、さまざまな目的でグループを作成するユーザーが多い場合があります。 ベスト プラクティスについては [、「Microsoft 365 グループのガバナンスの計画」を参照することを強](../../solutions/collaboration-governance-overview.md) くお勧めします。

## <a name="group-limits"></a>グループの制限

Microsoft 365 グループには、次の制限が適用されます。

|最大...|値|
|:---------|:----|
|1 つのグループの所有者|100|
|ユーザーが作成できるグループ|250|
|管理者が作成できるグループ|500 K の既定のテナント制限まで|
|メンバー数 |1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。 <br>Outlook の大規模なグループで予定表と会話にアクセスすると、ユーザーが遅延に気付く場合があります。|
|ユーザーがメンバーになれるグループの数|7,000|
|ファイルの記憶域|1 Terabyte + 10 GB/サブスクライブユーザー + 購入したその他のストレージ。 追加のストレージを無制限に購入できます。|
|グループ メールボックスのサイズ|50 GB|

組織で使用できる Microsoft 365 グループの既定の最大数は 500,000 です。 既定の制限を超える場合は、Microsoft サポートにお問い合わせください。 Microsoft 365 グループの制限の詳細については [、「Microsoft 365 グループ - 管理者向けヘルプ」を参照してください](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

グループの使用状況に関するアクション可能な情報がある場合は、Microsoft 365 グループを管理する方が効果的です。 Microsoft 365 管理センターには、ストレージの使用、アクティブなグループの数、およびユーザーがグループを使用している方法を確認できるレポート ツールがあります。 詳細については、「 [管理センターの Microsoft 365 レポート」](../activity-reports/office-365-groups.md) を参照してください。

## <a name="sensitivity-labels"></a>秘密度ラベル

組織内のユーザーが Microsoft 365 グループを作成するときに設定できる感度ラベルを作成できます。 感度ラベルを使用して、次の設定を行います。 

- プライバシー (パブリックまたはプライベート)
- 外部ユーザーのアクセス
- 管理されていないデバイス アクセス

たとえば、高機密という名前のラベルを作成し、このラベルで作成されたグループをプライベートにし、外部ユーザーを許可することを指定できます。 組織内のユーザーがグループの作成時にこのラベルを選択すると、グループはプライベートに設定され、グループメンバーはグループに外部ユーザーを追加できない。

> [!IMPORTANT]
> 現在分類ラベルを使用している場合、感度ラベルが有効になると、グループを作成するユーザーは使用できなくなりました。 

感度ラベルの作成、管理、および使用の詳細については、「感度ラベルを使用して [Microsoft Teams、Microsoft 365](../../compliance/sensitivity-labels-teams-groups-sites.md)グループ、および SharePoint サイトのコンテンツを保護する」を参照してください。

## <a name="which-microsoft-365-plans-include-groups"></a>グループが含まれる Microsoft 365 プラン

Exchange Online と SharePoint Online を持つ Microsoft 365 サブスクリプションは、グループをサポートします。 これには、Business Essentials および Business Premium プラン、および Enterprise E1、E3、および E5 プランが含まれます。 グループは、グループを作成するユーザー (グループの "開催者" とも呼ばれる) のライセンスを引き受けます。 開催者がグループに必要な機能に対して適切なライセンスを持っている限り、そのライセンスはグループに伝達されます。

> [!NOTE]
> Microsoft 365 サービス ファミリとプランの詳細については [、「Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)プラン オプション」を参照してください。

Exchange 専用プランがある場合でも、Outlook でグループの共有受信トレイと共有予定表機能を取得できますが、ドキュメント ライブラリ、Planner、その他の機能は取得できません。

Microsoft 365 グループは Azure Active Directory で動作します。 取得するグループ機能は、持っている Azure Active Directory サブスクリプションと、グループの開催者に割り当てられているライセンスによって異なります。

> [!IMPORTANT]
> すべてのグループ機能について、Azure AD Premium サブスクリプションがある場合、ユーザーは AAD P1 ライセンスが割り当てられているかどうかに関してグループに参加できます。 ライセンスは適用されません。
> Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。 たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。 この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。

## <a name="related-articles"></a>関連記事

[Microsoft 365 グループの詳細](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

[PowerShell を使用して Microsoft 365 グループを管理する](../../enterprise/manage-microsoft-365-groups-with-powershell.md)

[SharePoint Online の制限](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Microsoft Stream のグループとチャネルを整理する](/stream/groups-channels-organization)