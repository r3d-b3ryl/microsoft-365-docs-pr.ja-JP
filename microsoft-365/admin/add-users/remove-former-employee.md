---
title: 元従業員の削除 - 概要
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
- AdminTemplateSet
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: このソリューションの手順に従って、組織のデータを保護Microsoft 365元の従業員を削除します。
ms.openlocfilehash: 7c9667b771300a75a91588727f1d333ff2215302
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648665"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>概要: 元従業員とセキュリティで保護されたデータを削除する

よく聞く質問は、「従業員が組織を離れるときにデータを保護し、アクセスを保護するために何をすべきですか? この記事シリーズでは、Microsoft 365 へのアクセスをブロックして、これらのユーザーが Microsoft 365 にサインインできない方法、組織データをセキュリティで保護するために実行する手順、および他の従業員が電子メールと OneDrive データにアクセスする方法について説明します。

## <a name="before-you-begin"></a>はじめに

このソリューションの手順を完了するには、グローバル管理者である必要があります。

このシリーズの手順を完了するには、これらの機能と機能Microsoft 365使用します。

|製品またはコンポーネント|機能|
|---|---|
|Microsoft 365 管理センター|メールボックスの変換、メールの転送、アクセスの取り消し、ユーザーの削除 |
|Exchange 管理センター|ユーザーのブロック、電子メールへのアクセスのブロック、デバイスのワイプ |
|OneDrive と SharePoint |他のユーザーにアクセス権を与える |
|Outlook|pst ファイルのインポート、メールボックスの追加 |
|Active Directory|ハイブリッド環境でユーザーを削除する |

## <a name="solution-remove-a-former-employee"></a>解決策: 元従業員を削除する

> [!IMPORTANT]
> このソリューションの手順に番号を付け、正確な順序でソリューションを完了する必要は一切ないが、この方法で手順を実行することをお勧めします。

:::image type="content" source="../../media/delete-user-account.png" alt-text="スクリーンショット: 元従業員を組織から削除する手順":::

<br>

****

|手順|理由|
|---|---|
|[手順 1 - 元従業員のログインを防止し、サービスへのアクセスMicrosoft 365する](remove-former-employee-step-1.md)|これにより、元従業員がユーザーにログインMicrosoft 365し、ユーザーがサービスにアクセスMicrosoft 365します。|
|[手順 2 - 元従業員のメールボックスの内容を保存する](remove-former-employee-step-2.md)|これは、従業員の仕事を引き継ぐ人や訴訟がある場合に便利です。|
|[手順 3 - 元従業員のメールを別の従業員に転送するか、共有メールボックスに変換する](remove-former-employee-step-3.md)|この操作を行うと、元従業員のメール アドレスはアクティブなままとなります。顧客やパートナーが元従業員のアドレスにメールを引き続き送信する場合は、この手順を行うと、仕事を引き継ぐユーザーに転送されます。|
|[手順 4 - 別の従業員にデータとOneDriveアクセスOutlookする](remove-former-employee-step-4.md)|ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。 <p> アカウントを削除する前に、ユーザーのアカウントにアクセス権を与OneDrive、Outlookユーザーにアクセスする必要があります。 従業員のアカウントを削除すると、従業員のアカウントOneDrive Outlook **30** 日間保持されます。 ただし、その 30 日間は、ユーザーのアカウントを復元し、そのユーザーのコンテンツにアクセスできます。 ユーザーのアカウントを復元した場合、OneDriveおよびOutlookは 30 日後でもユーザーがアクセスできます。|
|[手順 5 - 元従業員のモバイル デバイスをワイプしてブロックする](remove-former-employee-step-5.md)|携帯電話またはタブレットからビジネス データを削除します。|
|[手順 6 - 元従業員からMicrosoft 365ライセンスを削除および削除する](remove-former-employee-step-6.md)|ライセンスを削除すると、別のユーザーに割り当てることができます。または、他のユーザーを採用するまで支払うことがないように、ライセンスを削除することもできます。  <p> ライセンスを削除すると、ユーザーの古いメール、連絡先、および予定表は **30 日間** 保持され、その後、完全に削除されます。 ライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  |
|[手順 7 - 元従業員のユーザー アカウントを削除する](remove-former-employee-step-7.md)|これにより、管理センターからアカウントが削除されます。 これできれいになります。|
|

## <a name="related-content"></a>関連コンテンツ

[ユーザーの復元](restore-user.md) (記事)\
[Microsoft 365 に新しい従業員を追加する](add-new-employee.md) (記事)\
[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)(記事)\
[ユーザーからのライセンスの割り当てを解除する](../manage/remove-licenses-from-users.md) (記事)
