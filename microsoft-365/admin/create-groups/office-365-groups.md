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
ms.openlocfilehash: b3bc0c30f4ac292da7af46678fc742854984db12
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925352"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>管理者向け Microsoft 365 グループの概要

Microsoft 365 グループは、Microsoft 365 全体のチームワークを促進する基盤のメンバーシップ サービスです。 Microsoft 365 グループを使用すると、ユーザーのグループに共有リソースのコレクションへのアクセス権を与えます。 これらのリソースは次のとおりです。

- 共有の Outlook 受信トレイ
- 共有の予定表
- SharePoint 文書ライブラリ
- Planner
- OneNote ノートブック
- Power BI
- Yammer (グループが Yammer から作成された場合)
- チーム (グループが Teams から作成された場合)
- ロードマップ (Project for the web を使用している場合)

Microsoft 365 グループでは、これらのリソースごとにアクセス許可を手動で割り当てる必要はありません。 グループにユーザーを追加すると、必要なアクセス許可が自動的に付与されます。

グループの作成を特定のユーザー のセットに制限しない限り、すべてのユーザー [がグループを作成できます](manage-creation-of-groups.md)。 グループの作成を制限すると、グループを作成できないユーザーは SharePoint サイト、プランナー、またはチームを作成できません。 これらのサービスでは、グループを作成するユーザーがグループを作成できる必要があります。 ユーザーは、グループのメンバーである場合、Planner でのタスクの作成や Teams チャットの使用などのグループ アクティビティに引き続き参加できます。

グループの役割は次のとおりです。

- **所有者** - グループ所有者は、メンバーを追加または削除できます。また、共有受信トレイから会話を削除する機能や、グループに関するさまざまな設定を変更する機能など、独自のアクセス許可を持っています。 グループ所有者は、グループ名の変更、説明や画像などの更新を行えます。
- **メンバー** - メンバーはグループ内のすべてのデータにアクセスできますが、グループの設定は変更できません。 既定では、グループ メンバーはゲストを招待してグループに参加させることができますが、[その設定は制御](manage-guest-access-in-groups.md)できます。
- **ゲスト** - グループ ゲストは、組織外のメンバーです。

Microsoft 365 管理センターでグループを作成および管理できるのは、グローバル管理者、ユーザー管理者、およびグループ管理者のみです。 代理管理者 (たとえば、代理の管理者であるコンサルタント) になることはできません。

管理者は次のことが可能です。

- [グループを作成できるユーザーの指定](manage-creation-of-groups.md)
- [組織内のグループの名前付けポリシーの作成](groups-naming-policy.md)
- [グループを作成するときに使用するドメインの選択](choose-domain-to-create-groups.md)
- [グループへのゲスト アクセスの管理](manage-guest-access-in-groups.md)
- [削除したグループの復元](restore-deleted-group.md) (削除から 30 日以内)

Microsoft 365 グループのライフサイクルを管理するより自動化された方法が必要な場合は、有効期限ポリシーを使用して、特定の時間間隔でグループを期限切れにできます。 グループの所有者は、グループの有効期限の 30 日、15 日前にメールを受け取り、必要に応じてグループを更新できます。 参照: [Microsoft 365 グループの有効期限ポリシー](office-365-groups-expiration-policy.md)。

グループは、Microsoft 365 管理センターから、または [PowerShell を使用](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel)して管理できます。

大企業や企業など、多数のユーザーが含む場合は、さまざまな目的でグループを作成するユーザーが多い場合があります。 ベスト プラクティスについては [、「Microsoft 365](plan-for-groups-governance.md) グループでのガバナンスの計画」を確認することを強くお勧めします。

## <a name="group-limits"></a>グループの制限

Microsoft 365 グループには、次の制限が適用されます。

|最大...|値|
|:---------|:----|
|1 つのグループの所有者|100|
|ユーザーが作成できるグループ|250|
|管理者が作成できるグループ|最大 500 K の既定のテナント制限|
|メンバー数 |1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。 <br>ユーザーは、Outlook の大規模なグループの予定表や会話にアクセスするときに遅延に気付く可能性があります。|
|ユーザーがメンバーになれるグループの数|7,000|
|ファイルの記憶域|サブスクライブしているユーザーごとに 1 テラバイト + 10 GB + 購入したその他のストレージ。 追加の記憶域を無制限に購入できます。|
|グループ メールボックスのサイズ|50 GB|

組織が持つ Microsoft 365 グループの既定の最大数は 500,000 です。 既定の制限を超える場合は、Microsoft サポートにお問い合わせください。 Microsoft 365 グループの制限の詳細については [、Microsoft 365 グループ -](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)管理者向けヘルプを参照してください。

グループの使用状況に関する操作可能な情報がある場合は、Microsoft 365 グループの管理が効果的です。 Microsoft 365 管理センターには、記憶域の使用、アクティブなグループの数、ユーザーがグループを使用している方法を確認できるレポート ツールがあります。 詳細については [、管理センターの Microsoft 365 レポート](../activity-reports/office-365-groups.md) を参照してください。

## <a name="sensitivity-labels"></a>秘密度ラベル

組織内のユーザーが Microsoft 365 グループを作成するときに設定できる、感度ラベルを作成できます。 感度ラベルを使用すると、次の設定を構成できます。 

- プライバシー (パブリックまたはプライベート)
- 外部ユーザーのアクセス
- 管理されていないデバイスへのアクセス

たとえば、高機密というラベルを作成し、このラベルで作成されたグループをプライベートにし、外部ユーザーを許可しないという指定を行います。 組織内のユーザーがグループの作成時にこのラベルを選択すると、グループはプライベートに設定され、グループメンバーはグループに外部ユーザーを追加できない。

> [!IMPORTANT]
> 現在分類ラベルを使用している場合、そのラベルは、グループを作成するユーザーは、そのラベルを使用できなくなりました。 

区別ラベルの作成、管理、および使用の詳細については、「Microsoft [Teams、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)グループ、および SharePoint サイトのコンテンツを保護するために、感度ラベルを使用する」を参照してください。

## <a name="which-microsoft-365-plans-include-groups"></a>グループが含まれる Microsoft 365 プランは何ですか?

Exchange Online と SharePoint Online を持つ Microsoft 365 サブスクリプションは、グループをサポートします。 これには、Business Essentials プランと Business Premium プラン、Enterprise E1、E3、および E5 プランが含まれます。 グループは、グループを作成したユーザー (グループの "開催者" とも呼ばれる) のライセンスを引き受けます。 開催者がグループに必要な機能に対して適切なライセンスを持っている限り、そのライセンスはグループに伝達されます。

> [!NOTE]
> Microsoft 365 サービス ファミリとプランの詳細については [、Microsoft 365 プランのオプションを参照してください](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。

Exchange 専用プランを使用している場合でも、Outlook のグループの共有受信トレイ機能と共有予定表機能を取得できますが、ドキュメント ライブラリ、Planner、その他の機能は取得できません。

Microsoft 365 グループは Azure Active Directory で動作します。 取得するグループ機能は、使用している Azure Active Directory サブスクリプション、およびグループの開催者に割り当てられるライセンスによって異なります。

> [!IMPORTANT]
> すべてのグループ機能について、Azure AD Premium サブスクリプションを持っている場合、ユーザーは AAD P1 ライセンスが割り当てられているかどうかに関わるかどうかに関してグループに参加できます。 ライセンスは適用されません。
> Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。 たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。 この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。

## <a name="related-articles"></a>関連記事

[Microsoft 365 グループについて](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

[PowerShell を使用して Microsoft 365 グループを管理する](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[SharePoint Online の制限](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
