---
title: Microsoft 365 グループの有効期限ポリシー
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Microsoft 365 グループの有効期限ポリシーについて説明します。
ms.openlocfilehash: 8fc9c48d5a86c68eabd4139ad0a2d0dc1e83da0f
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377225"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 グループの有効期限ポリシー

Microsoft 365 グループと Microsoft Teams の使用率が向上したことで、管理者とユーザーは、使用されていないグループと teams をクリーンアップする方法が必要になります。 Microsoft 365 グループの有効期限ポリシーは、非アクティブなグループをシステムから削除して、クリーナーを作成するのに役立ちます。

グループの有効期限が切れると、関連付けられているすべてのサービス (メールボックス、プランナー、SharePoint サイト、チームなど) も削除されます。

グループの有効期限が切れた場合、"削除済み" となることを意味します。これは、最大30日間復旧できます。

管理者は、有効期限を指定して、その期間の最後に到達し、更新されていないアクティブなグループを削除することができます。 (アーカイブされたチームが含まれます)。有効期限は、グループが作成された時点、または最後に更新された日付から始まります。 グループの所有者は、有効期限が切れる前に、別の有効期限が切れるまでグループを更新できるように、メールを自動的に送信します。 Teams ユーザーには、Teams で永続的な通知が表示されます。

アクティブに使用されているグループは自動的に更新されます。 次のいずれかのアクションを実行すると、グループが自動的に更新されます。
- SharePoint-ファイルの表示、編集、ダウンロード、移動、共有、またはアップロードを行います。
- Outlook-グループのメッセージと同じように、グループからのメッセージの読み取りまたは書き込み。メッセージ (web 上の Outlook)。
- Teams チャネルを訪れます。

> [!IMPORTANT]
> 有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。

既定では、有効期限はオフになっていることに注意してください。 管理者は、組織で使用する必要がある場合は、それを有効にする必要があります。

> [!NOTE]
> Microsoft 365 グループの有効期限ポリシーを構成して使用するには、その有効期限ポリシーが適用されているすべてのグループのメンバーに対して、必ずしも Azure AD Premium ライセンスを割り当てる必要はありません。 詳細については、「 [Azure Active Directory Premium の](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)概要」を参照してください。

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Microsoft 365 グループの有効期限ポリシーを構成および使用できるユーザー

|役割|できること|
|---------|---------|
|Office 365 のグローバル管理者 (Azure、会社の管理者の場合)、ユーザー管理者|Microsoft 365 グループの有効期限ポリシーの設定を作成、読み取り、更新、または削除します。|
|User|自分が所有する Microsoft 365 グループを更新または [復元](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) する|

## <a name="how-to-set-the-expiration-policy"></a>有効期限ポリシーを設定する方法

前述したように、有効期限は既定でオフになっています。 管理者は有効期限ポリシーを有効にして、そのプロパティを有効にする必要があります。 これを有効にするには、 **Azure Active Directory**  >  **グループ**の  >  **有効期限**に移動します。 ここでは、既定のグループの有効期間を設定して、最初と2番目の有効期限の通知がグループの所有者に移動するまでの時間を指定できます。

グループの有効期間は日単位で指定し、180、365、または指定したカスタム値に設定できます。 カスタム値は、少なくとも30日である必要があります。

グループに所有者がいない場合、有効期限メールは指定された管理者に送られます。

すべてのグループに対してポリシーを設定するか、選択したグループのみを設定するか、または **[なし**] を選択して完全にオフにすることができます。 現在、グループごとに異なるポリシーを設定することはできません。

![Azure Active Directory でのグループの有効期限設定のスクリーンショット](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>保持ポリシーを使用した有効期限のしくみ

セキュリティ/コンプライアンスセンターでグループのアイテム保持ポリシーを設定している場合、有効期限ポリシーは保持ポリシーとシームレスに連動します。 グループの有効期限が切れると、グループのメールボックスの会話とグループサイト内のファイルは、アイテム保持ポリシーで定義されている特定の日数だけ、保持コンテナーに保持されます。 ただし、有効期限が切れた後は、グループまたはそのコンテンツは表示されません。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>グループの有効期限が切れるかどうかをグループの所有者が学習する方法とタイミング

グループの所有者には、電子メールを介してのみ通知されます。 このグループが Planner、SharePoint、またはその他のアプリによって作成された場合、有効期限通知は常に電子メール経由で送信されます。 グループが Teams によって作成された場合、グループの所有者は [activity] セクションを通じて更新する通知を受信します。 グループの所有者が有効な電子メールアドレスを持っていない場合は、グループの有効期限を有効にすることはお勧めしません。

グループの有効期限が切れるまで30日間、グループの所有者 (または所有者がいないグループに対して指定したメールアドレス) は、グループを簡単に更新できる電子メールを受信します。 更新されていない場合は、有効期限が切れるまで15日後にもう一度更新メールを受信します。 まだ更新していない場合は、有効期限が切れる前に1日に1回のメール通知を受信します。

何らかの理由で、所有者または管理者が期限切れになる前にグループを更新しない場合でも、管理者は有効期限が切れてから30日以内にグループを復元することができます。 詳細については [、「削除された Microsoft 365 グループを復元する](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)」を参照してください。

## <a name="archiving-group-contents"></a>グループのコンテンツをアーカイブする

使用を計画していないものの、そのコンテンツを保持する必要があるグループがある場合は、「 [Archive groups, teams, And Yammer](end-life-cycle-groups-teams-sites-yammer.md) 」を参照して、さまざまなグループサービスから情報をエクスポートする方法に関する情報を参照してください。

## <a name="related-articles"></a>関連記事

[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[孤立グループに新しい所有者を割り当てる](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Microsoft 365 グループの有効期限を構成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
