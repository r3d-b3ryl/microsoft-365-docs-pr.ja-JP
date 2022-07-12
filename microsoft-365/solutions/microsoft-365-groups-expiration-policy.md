---
title: Microsoft 365 グループの有効期限ポリシー
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
recommendations: false
description: Microsoft 365 グループの有効期限ポリシーについて説明します。
ms.openlocfilehash: 41a179dc714063a66ba34aeb676321badfc5f947
ms.sourcegitcommit: 8101c12df67cfd9c15507b0133c23ce4cca1c6ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66720459"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 グループの有効期限ポリシー

Microsoft 365 グループと Microsoft Teams の使用が増えるにつれ、管理者とユーザーは未使用のグループとチームをクリーンアップする方法を必要とします。 Microsoft 365 グループの有効期限ポリシーは、システムから非アクティブなグループを削除し、物事をよりクリーンにするのに役立ちます。

グループの有効期限が切れると、関連するすべてのサービス (メールボックス、Planner、SharePoint サイト、チームなど) も削除されます。

グループの有効期限が切れると、"論理的に削除" されます。つまり、最大 30 日間回復できます。

管理者は有効期限を指定でき、その期間の終わりに達し、更新されていない非アクティブなグループはすべて削除されます。 (これには、アーカイブされたチームが含まれます。)有効期限は、グループが作成されたとき、または最後に更新された日付に開始されます。 グループの所有者は、有効期限が切れる前に自動的に電子メールが送信され、別の有効期限の間隔でグループを更新できます。 Teams ユーザーには、Teams に永続的な通知が表示されます。

アクティブに使用されているグループは自動的に更新されます。 次のアクションのいずれかにより、グループが自動更新されます。
- SharePoint - ファイルを表示、編集、ダウンロード、移動、共有、またはアップロードします。 (SharePoint ページの表示は、自動更新のアクションとしてカウントされません。)
- Outlook - グループへの参加または編集、グループからのグループ メッセージの読み取りまたは書き込み、およびメッセージの使用 (Outlook on the web)。
- Teams - チーム チャネルにアクセスします。
- Yammer - Yammer コミュニティ内の投稿や、Outlook の対話型メールを表示します。
- Forms - フォームの表示、作成、編集、またはフォームへの応答の送信。 

> [!IMPORTANT]
> 有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。

有効期限が既定でオフになっていることを確認することが重要です。 管理者は、組織で使用する場合は、それを有効にする必要があります。

> [!NOTE]
> Microsoft 365 グループの有効期限ポリシーを構成して使用するには、有効期限ポリシーが適用されているすべてのグループのメンバーに対して Azure AD Premium ライセンスを所有する必要がありますが、必ずしも割り当てる必要はありません。 詳細については、「[Azure Active Directory Premiumの概要](/azure/active-directory/active-directory-get-started-premium)」を参照してください。

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Microsoft 365 グループの有効期限ポリシーを構成して使用できるユーザー

|役割|可能な操作|
|---------|---------|
|Office 365 グローバル管理者 (Azure では会社の管理者)、ユーザー管理者|Microsoft 365 グループの有効期限ポリシー設定を作成、読み取り、更新、または削除します。|
|User|自分が所有する Microsoft 365 グループを更新または [復元](/azure/active-directory/users-groups-roles/groups-restore-deleted) する|

## <a name="how-to-set-the-expiration-policy"></a>有効期限ポリシーを設定する方法

前述のように、有効期限は既定でオフになっています。 管理者は、有効期限ポリシーを有効にして、有効にするプロパティを設定する必要があります。 これを有効にするには、**Azure Active Directory****グループ** > の > 有効期限に移動 **します**。 ここでは、既定のグループの有効期間を設定し、1 番目と 2 番目の有効期限通知をグループ所有者に送信する期間を事前に指定できます。

グループの有効期間は日数で指定され、180、365、または指定したカスタム値に設定できます。 カスタム値は 30 日以上である必要があります。

グループに所有者がいない場合、有効期限のメールは指定された管理者に送信されます。

すべてのグループに対してポリシーを設定するか、選択したグループのみ (最大 500) に設定するか、[ **なし**] を選択して完全に無効にすることができます。 現時点では、グループごとに異なるポリシーを設定することはできません。

![Azure Active Directory のグループの有効期限設定のスクリーンショット。](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>有効期限が保持ポリシーとどのように連携するか

Microsoft Purview コンプライアンス ポータル内のグループに対してアイテム保持ポリシーを設定した場合、有効期限ポリシーはアイテム保持ポリシーとシームレスに連携します。 グループの有効期限が切れると、グループ サイト内のグループのメールボックスの会話とファイルは、保持ポリシーで定義された特定の日数の間、保持コンテナに保持されます。 ただし、有効期限が切れると、ユーザーにはグループまたはそのコンテンツは表示されません。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>グループの所有者が、グループの有効期限が切れるかどうかを知る方法と時間

グループが Planner、SharePoint、またはその他のアプリを介して作成された場合、有効期限の通知は常にメールで送信されます。
Teams を使用してグループが作成された場合、グループの所有者は、アクティビティ セクションを通じて更新する電子メールと通知を受け取ります。 グループ所有者に有効なメール アドレスがない場合は、グループの有効期限を有効にすることはお勧めしません。

グループの有効期限が切れる 30 日前に、グループの所有者 (または所有者がいないグループに指定したメール アドレス) にメールが届き、グループを簡単に更新できます。 更新しない場合は、有効期限の 15 日前に別の更新メールが届きます。 それでも更新していない場合は、有効期限の前日にもう 1 通のメール通知が届きます。

何らかの理由で、有効期限が切れる前に所有者または管理者がグループを更新しなかった場合でも、管理者は有効期限が切れてから最大 30 日間グループを復元できます。 詳細については、「 [削除された Microsoft 365 グループを復元](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)する」を参照してください。

## <a name="archiving-group-contents"></a>グループの内容をアーカイブする

使用する予定がなく、そのコンテンツを保持するグループがある場合は、さまざまなグループ サービスから情報をエクスポートする方法の詳細については [、「グループ、チーム、Yammer をアーカイブ](end-life-cycle-groups-teams-sites-yammer.md) する」を参照してください。

## <a name="related-topics"></a>関連項目

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[孤立グループに新しい所有者を割り当てる](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Microsoft 365 グループの有効期限を構成する](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
