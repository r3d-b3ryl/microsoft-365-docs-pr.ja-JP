---
title: 管理者向け Microsoft 365 グループの概要
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 グループについて説明します。
ms.openlocfilehash: 14bc1211aaa65fb2daeebdb22729fce10154f204
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780411"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>管理者向け Microsoft 365 グループの概要

Microsoft 365 グループは、Microsoft 365 全体のすべてのチームワークを駆動する基本メンバーシップサービスです。 Microsoft 365 グループを使用すると、ユーザーのグループに、それらのユーザーが共有するコラボレーションリソースのコレクションへのアクセス権を与えることができます。 これらのリソースは次のとおりです。

- 共有の Outlook 受信トレイ
- 共有の予定表
- SharePoint 文書ライブラリ
- Planner
- OneNote ノートブック
- Power BI
- Yammer (グループが Yammer から作成された場合)
- チーム (グループが Teams から作成された場合)
- ロードマップ (web のプロジェクトがある場合)

Microsoft 365 グループでは、これらのリソースに対するアクセス許可を手動で割り当てる必要はありません。グループにユーザーを追加すると、そのグループが提供するツールに必要なアクセス許可が自動的に与えられるためです。

グループの作成を[特定のユーザーのセットに制限](manage-creation-of-groups.md)しない限り、任意のユーザーがグループを作成できます。 グループの作成を制限すると、グループを作成できないユーザーは、SharePoint サイト、Planners、またはチームを作成できなくなります。 これらのサービスでは、グループを作成できるようにするためにユーザーを作成する必要があります。 ユーザーがグループのメンバーである場合は、Planner でタスクを作成したり、Teams チャットを使用したりするなど、グループのアクティビティに参加できます。

グループの役割は次のとおりです。

- **所有者** - グループ所有者は、メンバーを追加または削除できます。また、共有受信トレイから会話を削除する機能や、グループに関するさまざまな設定を変更する機能など、独自のアクセス許可を持っています。 グループ所有者は、グループ名の変更、説明や画像などの更新を行えます。
- **メンバー** - メンバーはグループ内のすべてのデータにアクセスできますが、グループの設定は変更できません。 既定では、グループ メンバーはゲストを招待してグループに参加させることができますが、[その設定は制御](manage-guest-access-in-groups.md)できます。
- **ゲスト** - グループ ゲストは、組織外のメンバーです。

グローバル管理者、ユーザー管理者、およびグループ管理者のみが、Microsoft 365 管理センターでグループを作成および管理できます。 代理管理者 (たとえば、代理の管理者であるコンサルタント) になることはできません。

管理者は次のことが可能です。

- [グループを作成できるユーザーの指定](manage-creation-of-groups.md)
- [組織内のグループの名前付けポリシーの作成](groups-naming-policy.md)
- [グループを作成するときに使用するドメインの選択](choose-domain-to-create-groups.md)
- [グループへのゲスト アクセスの管理](manage-guest-access-in-groups.md)
- [削除したグループの復元](restore-deleted-group.md) (削除から 30 日以内)

Microsoft 365 グループのライフサイクルの管理方法をさらに自動化する場合は、有効期限ポリシーを使用して、特定の時間間隔でグループを期限切れにすることができます。 グループの所有者は、グループが期限切れになる 30、15、1 日前に電子メールを受け取ります。これにより、グループがまだ必要な場合は、所有者は簡単に更新することができます。 「 [Microsoft 365 グループ有効期限ポリシー](office-365-groups-expiration-policy.md)」を参照してください。

グループは、Microsoft 365 管理センターから、または [PowerShell を使用](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)して管理できます。

大規模企業など、多数のユーザーがいる場合は、さまざまな目的でグループを作成するユーザーが多数存在する可能性があります。 ベストプラクティスについては、「 [Microsoft 365 グループのガバナンスの計画」](plan-for-groups-governance.md)を参照することを強くお勧めします。

## <a name="group-limits"></a>グループの制限

Microsoft 365 グループには、次の制限が適用されます。

|最大...|値|
|:---------|:----|
|1 つのグループの所有者|100|
|ユーザーが作成できるグループ|250|
|管理者が作成できるグループ|既定のテナント数の上限は 500,000|
|メンバー数 |1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。 <br>Outlook で非常に大規模なグループの予定表や会話にアクセスする場合に、ユーザーが遅延を感じることがあります。|
|ユーザーがメンバーになれるグループの数|1,000|
|ファイルの記憶域|各サブスクライブ ユーザーに 1 TB + 10 GB と、購入した追加記憶域。 追加の記憶域は無制限で購入できます。|
|グループ メールボックスのサイズ|50 GB|

組織に割り当てることができる Microsoft 365 グループの既定の最大数は50万ですが、要求によって増やすことができます。 Microsoft 365 Groups の制限の詳細については、「 [microsoft 365 のグループ-管理者向けヘルプ](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)」を参照してください。

グループの使用に関する操作可能な情報を持っている場合は、Microsoft 365 グループを管理する方が効率的です。 Microsoft 365 管理センターには、ストレージの使用状況、アクティブなグループの数、ユーザーがグループをどのように使用しているかなどの項目を表示できるレポートツールが用意されています。 詳細については[、「管理センターの Microsoft 365 レポート](../activity-reports/office-365-groups.md)」を参照してください。

## <a name="sensitivity-labels"></a>秘密度ラベル

組織内のユーザーが Microsoft 365 グループを作成するときに設定できる機密ラベルを作成できます。 機密ラベルを使用すると、次のものを構成できます。 

- プライバシー (パブリックまたはプライベート)
- 外部ユーザーのアクセス
- 非管理対象デバイスアクセス

たとえば、*高機密*という名前のラベルを作成し、このラベルを使用して作成されたグループがプライベートで、外部ユーザーを許可していないことを指定できます。 グループの作成時に組織内のユーザーがこのラベルを選択すると、グループは [プライベート] に設定され、グループメンバーが外部ユーザーをグループに追加することは許可されません。

> [!IMPORTANT]
> 現在、分類ラベルを使用している場合、グループを作成するユーザーは、機密ラベルが有効になっていても使用できなくなります。 

機密ラベルの作成、管理、および使用の詳細については、「[機密情報を使用して Microsoft Teams のコンテンツを保護する」、「microsoft 365 グループ」、および「SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」を参照してください。

## <a name="which-microsoft-365-plans-include-groups"></a>どの Microsoft 365 プランにグループが含まれていますか?

Exchange Online および SharePoint Online を備えた Microsoft 365 サブスクリプションは、グループをサポートします。 このサブスクリプションには、Business Essentials プランと Business Premium プラン、Enterprise E1、E3、E5 プランが含まれます。 グループは、グループ (グループの "開催者" とも呼ばれます) を作成したユーザーのライセンスを受け取ります。 グループに含める任意の機能について、開催者が適切なライセンスを持っている限り、そのライセンスはグループに伝達されます。

> [!NOTE]
> Microsoft 365 サービスファミリおよびプランの詳細については、「 [microsoft 365 プランのオプション](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)」を参照してください。

Exchange のみのプランを使用している場合でも、Outlook で共有の受信トレイと共有の予定表機能を取得することはできますが、ドキュメントライブラリ、Planner、その他の機能は取得できません。

Microsoft 365 グループは、Azure Active Directory (AAD) で動作します。 取得するグループ機能は、使用している Azure Active Directory サブスクリプション、およびグループの開催者に割り当てられているライセンスによって異なります。

> [!IMPORTANT]
> すべてのグループ機能について、Azure AD Premium サブスクリプションを所有している場合、ユーザーは AAD P1 ライセンスが割り当てられているかどうかにかかわらず、グループに参加できます。 ライセンスは適用されません。
> Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。 たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。 この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。

## <a name="related-articles"></a>関連記事

[Microsoft 365 グループについて](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

[PowerShell を使用して Microsoft 365 グループを管理する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[SharePoint Online の制限](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
