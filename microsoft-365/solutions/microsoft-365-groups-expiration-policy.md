---
title: Microsoft 365有効期限ポリシー
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
- m365solution-collabgovernance
search.appverid:
- MET150
recommendations: false
description: グループのMicrosoft 365ポリシーについて説明します。
ms.openlocfilehash: 4617124801ed0400481bd81a453c6520a0c8d73a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214113"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365有効期限ポリシー

グループとグループの使用Microsoft 365増Microsoft Teams、管理者とユーザーは未使用のグループとチームをクリーンアップする方法が必要です。 グループMicrosoft 365有効期限ポリシーは、非アクティブなグループをシステムから削除し、よりクリーンな状態にするのに役立ちます。

グループの有効期限が切れると、関連付けられているすべてのサービス (メールボックス、Planner、SharePoint、チームなど) も削除されます。

グループの有効期限が切れると、"soft-deleted" になります。つまり、最大 30 日間回復できます。

管理者は有効期限を指定し、その期間の終わりに達し、更新されない非アクティブなグループは削除されます。 (これには、アーカイブされたチームが含まれます)。有効期限は、グループが作成された日、または最後に更新された日付から始まります。 グループの所有者は、有効期限の前にメールが自動的に送信され、グループを別の有効期限の間隔で更新できます。 Teamsユーザーに永続的な通知が表示Teams。

アクティブに使用されているグループは自動的に更新されます。 次のアクションは、グループを自動更新します。
- SharePoint - ファイルの表示、編集、ダウンロード、移動、共有、またはアップロードを行います。 (自動更新SharePointページを表示しても、アクションとしてカウントされません。
- Outlook - グループへの参加、グループからのグループ メッセージの読み取りまたは書き込み、およびメッセージ (Outlook on the web)。
- Teams - Teams チャネルを訪問します。

グループの自動更新をYammerするアクティビティは、コミュニティ内でのドキュメントのアップロードSharePointに注意してください。

> [!IMPORTANT]
> 有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。

有効期限が既定でオフになっていることを確認することが重要です。 管理者が使用する場合は、組織で有効にする必要があります。

> [!NOTE]
> Microsoft 365 グループの有効期限ポリシーを構成して使用するには、有効期限ポリシーが適用されるすべてのグループのメンバーに Azure AD Premium ライセンスを割り当てる必要がありますが、必ずしも割り当てる必要はありません。 詳細については[、「Getting started with Azure Active Directory Premium」 を参照してください](/azure/active-directory/active-directory-get-started-premium)。

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Whoグループの有効期限ポリシーを構成Microsoft 365使用できますか?

|Role|実行できる操作|
|---------|---------|
|Office 365管理者 (Azure、会社管理者)、ユーザー管理者|有効期限ポリシー設定を作成、読み取り、更新Microsoft 365削除します。|
|User|自分が[所有するMicrosoft 365](/azure/active-directory/users-groups-roles/groups-restore-deleted)グループを更新または復元する|

## <a name="how-to-set-the-expiration-policy"></a>有効期限ポリシーを設定する方法

上記のように、有効期限は既定でオフになっています。 管理者は、有効期限ポリシーを有効にして、有効にするプロパティを設定する必要があります。 有効にするには、[グループの有効期限] **Azure Active Directory**  >  **に**  >  **移動します**。 ここでは、既定のグループの有効期間を設定し、最初と 2 番目の有効期限通知をグループ所有者に移動する事前の期間を指定できます。

グループの有効期間は日数で指定され、180、365、または指定したカスタム値に設定できます。 カスタム値は、少なくとも 30 日間である必要があります。

グループに所有者が存在しない場合、有効期限の電子メールは指定された管理者に送信されます。

すべてのグループにポリシーを設定するか、選択したグループ (最大 500) のみを設定するか、[なし] を選択して完全にオフ **にできます**。 現時点では、グループごとに異なるポリシーを設定することはできません。

![[グループの有効期限の設定] のスクリーンショットをAzure Active Directory。](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>保持ポリシーでの有効期限の動作

セキュリティ とコンプライアンス センターでグループの保持ポリシーを設定している場合、有効期限ポリシーは保持ポリシーとシームレスに動作します。 グループの有効期限が切れると、グループ サイト内のグループのメールボックスの会話とファイルは、保持ポリシーで定義された特定の日数保持コンテナーに保持されます。 ただし、有効期限が過ぎた後、ユーザーにはグループまたはコンテンツは表示されない。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>グループの所有者がグループの有効期限が切れるか確認する方法と時間

グループの所有者には、電子メールによる通知のみ受け取る必要があります。 グループが Planner、SharePoint、または他のアプリを介して作成された場合、有効期限通知は常に電子メールで送信されます。 グループがグループを使用して作成Teams、グループの所有者はアクティビティ セクションを通じて更新する通知を受け取ります。 グループの所有者に有効なメール アドレスが設定されていない場合は、グループの有効期限を有効にすることはできません。

グループの有効期限が切れる 30 日前に、グループの所有者 (または所有者を持つグループに指定した電子メール アドレス) は、グループを簡単に更新できる電子メールを受信します。 更新しない場合は、有効期限の 15 日前に別の更新メールが届きます。 まだ更新していない場合は、有効期限の前にもう 1 回メール通知を受け取ります。

何らかの理由で、有効期限が切れる前に所有者または管理者がグループを更新しない場合、管理者は有効期限が切れた後、最大 30 日間グループを復元できます。 詳細については、「削除されたグループ[を復元する」をMicrosoft 365してください](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。

## <a name="archiving-group-contents"></a>グループの内容のアーカイブ

使用する予定がないグループがあるが、そのコンテンツを保持する場合は、「アーカイブ グループ、チーム、[および Yammer」](end-life-cycle-groups-teams-sites-yammer.md)を参照して、さまざまなグループ サービスから情報をエクスポートする方法について確認してください。

## <a name="related-topics"></a>関連項目

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[孤立グループに新しい所有者を割り当てる](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[グループMicrosoft 365の有効期限を構成する](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
