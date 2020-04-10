---
title: 管理者向け Office 365 グループの概要
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Office 365 グループについて説明します。
ms.openlocfilehash: f5a0b72737a360a4bfe4cdd8fee4a08b7a7ff236
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212535"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>管理者向け Office 365 グループの概要

Office 365 グループは、Microsoft 365 全体のすべてのチームワークを駆動する基本メンバーシップサービスです。 Office 365 グループを使用すると、ユーザーのグループに、それらのユーザーが共有するコラボレーションリソースのコレクションへのアクセス権を与えることができます。 これらのリソースは次のとおりです。

- 共有の Outlook 受信トレイ
- 共有の予定表
- SharePoint 文書ライブラリ
- Planner
- Power BI
- Yammer (グループが Yammer から作成された場合)
- チーム (グループが Teams から作成された場合)
- ロードマップ (web のプロジェクトがある場合)

Office 365 グループでは、これらのリソースに対するアクセス許可を手動で割り当てる必要はありません。グループにユーザーを追加すると、グループが提供するツールに必要なアクセス許可が自動的に割り当てられるためです。

[グループの作成を特定のユーザーに制限しない](manage-creation-of-groups.md)限り、Office 365 ユーザーはグループを作成できます。 グループの作成を制限すると、グループを作成できないユーザーは、SharePoint サイト、Planners、またはチームを作成できなくなります。 これらのサービスでは、グループを作成できるようにするためにユーザーを作成する必要があります。 ユーザーがグループのメンバーである場合は、Planner でタスクを作成したり、Teams チャットを使用したりするなど、グループのアクティビティに参加できます。

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

Office 365 グループのライフサイクルの管理方法をさらに自動化する場合は、有効期限ポリシーを使用して、特定の時間間隔でグループを期限切れにすることができます。 グループの所有者は、グループが期限切れになる 30、15、1 日前に電子メールを受け取ります。これにより、グループがまだ必要な場合は、所有者は簡単に更新することができます。 「[Office 365 グループの有効期限ポリシー](office-365-groups-expiration-policy.md)」を参照してください。

グループは、Microsoft 365 管理センターから、または [PowerShell を使用](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)して管理できます。

大規模企業など、多数のユーザーがいる場合は、さまざまな目的でグループを作成するユーザーが多数存在する可能性があります。 ベストプラクティスについては、「[Office 365 グループでのガバナンスを計画する](plan-for-groups-governance.md)」を参照することを強くお勧めします。

## <a name="group-limits"></a>グループの制限

Office 365 グループには、次の制限が適用されます。

|最大...|値|
|:---------|:----|
|1 つのグループの所有者|100|
|ユーザーが作成できるグループ|250|
|管理者が作成できるグループ|既定のテナント数の上限は 500,000|
|メンバー数 |1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。 <br>Outlook で非常に大規模なグループの予定表や会話にアクセスする場合に、ユーザーが遅延を感じることがあります。|
|ユーザーがメンバーになれるグループの数|1,000|
|ファイルの記憶域|各サブスクライブ ユーザーに 1 TB + 10 GB と、購入した追加記憶域。 追加の記憶域は無制限で購入できます。|
|グループ メールボックスのサイズ|50 GB|

Office 365 組織が持つことができる Office 365 グループの既定の最大数は50万ですが、要求によって増やすことができます。 Office 365 グループの制限の詳細については、「 [office 365 groups-管理者向けヘルプ](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)」を参照してください。

グループの使用に関する操作可能な情報を持っている場合は、Office 365 グループの管理がより効果的です。 Microsoft 365 管理センターには、ストレージの使用状況、アクティブなグループの数、ユーザーがグループをどのように使用しているかなどの項目を表示できるレポートツールが用意されています。 詳細については、「[管理センターの Office 365 レポート](../activity-reports/office-365-groups.md)」を参照してください。

## <a name="which-office-365-plans-include-groups"></a>どの Office 365 プランにグループが含まれていますか?

Exchange Online と SharePoint Online を備えた Office 365 サブスクリプションでは、グループをサポートします。 このサブスクリプションには、Business Essentials プランと Business Premium プラン、Enterprise E1、E3、E5 プランが含まれます。 グループは、グループ (グループの "開催者" とも呼ばれます) を作成したユーザーのライセンスを受け取ります。 グループに含める任意の機能について、開催者が適切なライセンスを持っている限り、そのライセンスはグループに伝達されます。

> [!NOTE]
> Office 365 サービスファミリおよびプランの詳細については、「 [office 365 プランオプション](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)」を参照してください。

Exchange のみのプランを使用している場合でも、Outlook で共有の受信トレイと共有の予定表機能を取得することはできますが、ドキュメントライブラリ、Planner、その他の機能は取得できません。

Office 365 グループは、Azure Active Directory (AAD) で動作します。 取得するグループ機能は、使用している Azure Active Directory サブスクリプション、およびグループの開催者に割り当てられているライセンスによって異なります。

> [!IMPORTANT]
> すべてのグループ機能について、Azure AD Premium サブスクリプションを所有している場合、ユーザーは AAD P1 ライセンスが割り当てられているかどうかにかかわらず、グループに参加できます。 ライセンスは適用されません。
> Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。 たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。 この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。

## <a name="related-articles"></a>関連記事

[Office 365 グループの詳細](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[配布リストを Office 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

[PowerShell で Office 365 グループを管理する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[SharePoint Online の制限](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
