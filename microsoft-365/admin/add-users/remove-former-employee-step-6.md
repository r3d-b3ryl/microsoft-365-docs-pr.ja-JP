---
title: 手順 6 - 元従業員からMicrosoft 365ライセンスを削除および削除する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 次の手順に従って、元Microsoft 365ライセンスを削除します。
ms.openlocfilehash: 7303c881e93d3ecb0c6637936ad12d8da227392c
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541567"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>手順 6 - 元従業員Microsoft 365ライセンスを削除する

他のユーザーが組織を離れた後にライセンスの支払いを行わない場合は、そのユーザーのライセンスを削除Microsoft 365サブスクリプションから削除する必要があります。 ライセンスを削除しない場合は、別のユーザーにライセンスを割り当てできます。
  
ライセンスの削除後、そのユーザーのすべてのデータが 30 日間保持されます。 データに[アクセス](get-access-to-and-back-up-a-former-user-s-data.md)したり、ユーザーが復帰した場合にアカウントを[復元](restore-user.md)したりすることができます。 30 日後、すべてのユーザーのデータ (SharePoint Online に保存されているドキュメントを除く) は Microsoft 365 から完全に削除され、回復できません。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ブロックする従業員の名前を選択し、[ライセンスとアプリ] **タブを選択** します。
3. 削除するライセンスのチェック ボックスをオフにし、[変更の保存] **を選択します**。

**他のユーザーを雇うまで** 支払うライセンスの数を減らすには、次の手順を実行します。

1. 管理センターで、[製品の請求] ページ **に** 移動し、[ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"></a>製品] タブ **を選択** します。
2. ライセンスを削除するサブスクリプションを選択します。
3. 詳細ページで、[ライセンスの削除] **を選択します**。
4. [ライセンス **の削除]** ウィンドウの [新しい数量] の [ライセンスの合計] **ボックスに、** このサブスクリプションに必要なライセンスの総数を入力します。 たとえば、25 のライセンスを持ち、そのうちの 1 つを削除する場合は、「24」と入力します。
5. **[保存]** を選択します。

ビジネスに [別のユーザー](add-users.md) を追加すると、1 つの手順でライセンスを同時に購入するように求めるメッセージが表示されます。

Microsoft 365 for business のユーザー ライセンスの管理の詳細については、「ビジネス向け[Microsoft 365](../manage/assign-licenses-to-users.md)のユーザーにライセンスを割り当てる」および「Microsoft 365 for business のユーザーからのライセンス[の割り当て解除」を](../manage/remove-licenses-from-users.md)参照してください。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>削除した従業員のアカウントが Skype for Business に与える影響

Office 365 からユーザーのライセンスを削除すると、ユーザーに関連付けられている PSTN 通話番号が解放されます。この番号を別のユーザーに割り当てることができます。
  
ユーザーがキュー グループに属している場合、ユーザーは呼び出しキューのエージェントの実行可能な対象にならなくなります。そのため、呼び出しキューに関連付けられているグループからもユーザーを削除することをお勧めします。

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>組織内のユーザーへの通話転送を設定する

終了した従業員の電話番号の通話転送を設定する必要がある場合は、通話ポリシーの下の通話転送設定で、着信通話を他のユーザーに転送したり、同時に他のユーザーを呼び出したりできる転送を設定できます。 詳細については、「通話ポリシー」[を参照Microsoft Teams。](/microsoftteams/teams-calling-policy)
