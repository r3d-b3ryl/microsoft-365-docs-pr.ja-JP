---
title: 手順 6 - 元従業員のMicrosoft 365 ライセンスを削除して削除する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 元従業員のMicrosoft 365ライセンスを削除してから、サブスクリプションから削除するか、ライセンスを別のユーザーに割り当てることができます。
ms.openlocfilehash: 95f95403a316e176f91c7f120ce5a26487a7a59f
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65436231"
---
# <a name="step-6---remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>手順 6 - 元従業員のMicrosoft 365 ライセンスを削除して削除する

他のユーザーが組織を離れた後にライセンスの支払いを行わない場合は、Microsoft 365ライセンスを削除してからサブスクリプションから削除する必要があります。 ライセンスを削除しない場合は、別のユーザーにライセンスを割り当てることができます。

コンプライアンスまたは法的理由で電子情報開示アクセス許可を付与された承認されたユーザーがメールボックスにアクセスする必要がある場合は、Exchange Onlineプラン 2 ライセンス (またはExchange Online ArchivingでExchange Onlineプラン 1 ライセンス) を割り当てる必要があります。 アドオン ライセンス) を使用して、メールボックスを削除する前にホールドをメールボックスに適用できます。 ユーザー アカウントが削除されると、ユーザー アカウントに関連付けられているすべてのExchange Online ライセンスを新しいユーザーに割り当てることができます。
  
ライセンスの削除後、そのユーザーのすべてのデータが 30 日間保持されます。 データに[アクセス](get-access-to-and-back-up-a-former-user-s-data.md)したり、ユーザーが復帰した場合にアカウントを[復元](restore-user.md)したりすることができます。 30 日後、すべてのユーザーのデータ (SharePoint Online に保存されているドキュメントを除く) はMicrosoft 365から完全に削除され、回復できません。

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. ブロックする従業員の名前を選択し、[ **ライセンスとアプリ** ] タブを選択します。
3. 削除するライセンスのチェック ボックスをオフにし、[ **変更の保存]** を選択します。

別のユーザーを採用するまで **支払うライセンスの数を減らす** には、次の手順に従います。

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品</a>の **請求**\>] ページに移動し、[**製品**] タブを選択します。
2. ライセンスを削除するサブスクリプションを選択します。
3. 詳細ページで、[ライセンスの **削除**] を選択します。
4. [ **ライセンスの削除** ] ウィンドウの [新しい数量] の [ **ライセンスの合計** ] ボックスに、このサブスクリプションに必要なライセンスの合計数を入力します。 たとえば、25 個のライセンスがあり、そのうちの 1 つを削除する場合は、「24」と入力します。
5. [**保存**] を選択します。

別の [ユーザー](add-users.md) をビジネスに追加すると、1 つの手順でライセンスを同時に購入するように求められます。

ビジネス向けのMicrosoft 365のユーザー ライセンスの管理の詳細については、「ビジネス向けの[Microsoft 365のユーザーにライセンスを割り当てる」と「ビジネス向けの](../manage/assign-licenses-to-users.md)[Microsoft 365のユーザーからのライセンスの割り当て解除」を](../manage/remove-licenses-from-users.md)参照してください。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>削除した従業員のアカウントが Skype for Business に与える影響

Office 365 からユーザーのライセンスを削除すると、ユーザーに関連付けられている PSTN 通話番号が解放されます。この番号を別のユーザーに割り当てることができます。
  
ユーザーがキュー グループに属している場合、ユーザーは呼び出しキューのエージェントの実行可能な対象にならなくなります。そのため、呼び出しキューに関連付けられているグループからもユーザーを削除することをお勧めします。

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>組織内のユーザーへの通話転送を設定する

終了した従業員の電話番号の通話転送を設定する必要がある場合は、通話ポリシーの下の通話転送設定で、着信を他のユーザーに転送したり、別のユーザーを同時に呼び出したりできる転送を設定できます。 詳細については、「[Microsoft Teamsでのポリシーの呼び出し](/microsoftteams/teams-calling-policy)」を参照してください。
