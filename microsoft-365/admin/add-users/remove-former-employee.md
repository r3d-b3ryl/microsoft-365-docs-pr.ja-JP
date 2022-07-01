---
title: 元従業員を削除する - 概要
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
- adminvideo
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- m365solution-removeemployee
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
description: 元従業員がサインインできないように Microsoft 365 へのアクセスをブロックし、組織データをセキュリティで保護し、他の従業員が自分の電子メールと OneDrive データにアクセスできるようにします。
ms.openlocfilehash: 12c1656ba0826e9d4d2472427642914cdcc7b2e6
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66601720"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>概要: 元従業員を削除し、データをセキュリティで保護する

YouTube の [Microsoft 365 小規模ビジネス ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

よく寄せられる質問は、「従業員が組織を離れたときにデータをセキュリティで保護し、アクセスを保護するためにどうすればよいか」です。 この記事シリーズでは、Microsoft 365 へのアクセスをブロックして、これらのユーザーが Microsoft 365 にサインインできないようにする方法、組織データをセキュリティで保護するために実行する手順、および他の従業員に電子メールと OneDrive データへのアクセスを許可する方法について説明します。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="before-you-begin"></a>開始する前に

このソリューションの手順を完了するには、グローバル管理者である必要があります。

このシリーズの手順を完了するには、次の Microsoft 365 の機能と機能を使用します。

|製品またはコンポーネント|機能|
|---|---|
|Microsoft 365 管理センター|メールボックスの変換、電子メールの転送、アクセスの取り消し、ユーザーの削除 |
|Exchange 管理センター|ユーザーのブロック、電子メールへのアクセスのブロック、デバイスのワイプ |
|OneDrive と SharePoint |他のユーザーにアクセス権を付与する |
|Outlook|pst ファイルのインポート、メールボックスの追加 |
|Active Directory|ハイブリッド環境でユーザーを削除する |


## <a name="solution-remove-a-former-employee"></a>解決策: 元従業員を削除する

> [!IMPORTANT]
> このソリューションの手順には番号が付けられているため、正確な順序を使用してソリューションを完了する必要はありませんが、この方法で手順を実行することをお勧めします。

:::image type="content" source="../../media/delete-user-account.png" alt-text="スクリーンショット: 元従業員を組織から削除する手順":::

<br>

****

|手順|理由|
|---|---|
|[手順 1 - 元従業員がログインできないようにし、Microsoft 365 サービスへのアクセスをブロックする](remove-former-employee-step-1.md)|これにより、元従業員が Microsoft 365 にログインできなくなります。これにより、ユーザーが Microsoft 365 サービスにアクセスできなくなります。|
|[手順 2 - 元従業員のメールボックスの内容を保存する](remove-former-employee-step-2.md)|これは、従業員の仕事を引き継ぐ人や訴訟がある場合に役立ちます。|
|[手順 3 - 元従業員のモバイル デバイスをワイプしてブロックする](remove-former-employee-step-3.md)|携帯電話またはタブレットからビジネス データを削除します。|
|[手順 4 - 元従業員のメールを別の従業員に転送するか、共有メールボックスに変換する](remove-former-employee-step-4.md)|この操作を行うと、元従業員のメール アドレスはアクティブなままとなります。顧客やパートナーが元従業員のアドレスにメールを引き続き送信する場合は、この手順を行うと、仕事を引き継ぐユーザーに転送されます。|
|[手順 5 - OneDrive と Outlook データへの別の従業員アクセス権を付与する](remove-former-employee-step-5.md)|ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。 <p> アカウントを削除する前に、OneDrive と Outlook のアクセス権を別のユーザーに付与する必要があります。 従業員のアカウントを削除すると、OneDrive と Outlook のコンテンツは **30** 日間保持されます。 ただし、その 30 日間は、ユーザーのアカウントを復元し、そのコンテンツにアクセスできます。 ユーザーのアカウントを復元した場合、OneDrive と Outlook のコンテンツは、30 日後も引き続きアクセスできます。| 
|[手順 6 - 元従業員から Microsoft 365 ライセンスを削除して削除する](remove-former-employee-step-6.md)|ライセンスを削除すると、別のユーザーに割り当てることができます。または、他のユーザーを採用するまで支払うことがないように、ライセンスを削除することもできます。  <p> ライセンスを削除すると、ユーザーの古いメール、連絡先、および予定表は **30 日間** 保持され、その後、完全に削除されます。 ライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  |
|[手順 7 - 元従業員のユーザー アカウントを削除する](remove-former-employee-step-7.md)|これにより、管理センターからアカウントが削除されます。 これできれいになります。|

## <a name="watch-delete-a-user"></a>ウォッチ: ユーザーを削除する

[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2198203)で、このビデオや他の動画を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR?autoplay=false]

従業員が退職したら、ビジネスのために Microsoft 365 から従業員を削除する必要があります。 これを行う前に、会社のファイルへのアクセスをブロックし、作成したドキュメントを保持し、ユーザーの削除に関連する他のいくつかの管理タスクを実行する必要があります。

1. 管理センターで [ **ユーザー**] を選択し、[ **アクティブなユーザー**] を選択します。
1. 削除するユーザーを選択し、[ **ユーザーの削除**] を選択します。
1. ライセンスを削除する場合はオンにし、メール エイリアスを削除する場合はチェック ボックスをオンにします。
1. 別のユーザーに元従業員のメールへのアクセス権を付与するには、このチェック ボックスをオンにし、[ **ユーザーの選択] を選択してメール オプションを設定します**。
1. 関連付けられているメール エイリアスを削除するには、そのエイリアスの横にある **[X** ] を選択します。
1. 共有メールボックス情報を確認し、[完了] を選択 **します**。
1. オプションが正しく設定されていることを確認し、[ **割り当てと変換**] を選択します。
1. 結果を確認し、[ **閉じる**] を選択します。

ユーザーを削除した後、アカウントを復元するには最大 30 日間です。
## <a name="related-content"></a>関連コンテンツ

[ユーザーの復元](restore-user.md) (記事)\
[Microsoft 365 に新しい従業員を追加する](add-new-employee.md) (記事)\
[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)(記事)\
[ユーザーからのライセンスの割り当て解除](../manage/remove-licenses-from-users.md) (記事)
