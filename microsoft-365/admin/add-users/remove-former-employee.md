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
search.appverid:
- BCS160
- MET150
- MOE150
description: このソリューションの手順に従って、組織のデータを保護Microsoft 365元の従業員を削除します。
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241738"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>概要: 元従業員とセキュリティで保護されたデータを削除する

よく聞く質問は、「従業員が組織を離れるときにデータを保護し、アクセスを保護するために何をすべきですか? この記事シリーズでは、Microsoft 365 へのアクセスをブロックする方法、データをセキュリティで保護するために実行する必要がある手順、および他の従業員がデータにアクセスする方法について説明します。

従業員の削除に関する短いビデオをご覧ください。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../../business-video/index.yml)」をご覧ください。

従業員がログインを防止するには、次の方法を実行します。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ユーザーの名前の横にあるボックスを選択し、[パスワードのリセット] **を選択します**。
3. 新しいパスワードを入力し、[リセット] を **選択します**。 (送信しない。
4. ユーザーの名前を選択してプロパティ ウィンドウに移動し、[アカウント]タブで [サインアウトの開始 **] を選択します**。

> [!NOTE]
> サインアウトを開始するには、グローバル管理者である必要があります。

1 時間以内に、または現在のページを離Microsoft 365後に、もう一度サインインするように求めるメッセージが表示されます。 アクセス トークンは 1 時間有効なので、タイムラインは、そのトークンに残されている時間と、現在の Web ページから移動するかどうかによって異なります。

> [!IMPORTANT]
> このソリューションの手順に番号を付け、正確な順序でソリューションを完了する必要は一切ないが、この方法で手順を実行することをお勧めします。

## <a name="before-you-begin"></a>はじめに

このソリューションの手順を完了するには、グローバル管理者である必要があります。

|||
|:-----|:-----|
|**手順** <br/> |**理由** <br/> |
|[手順 1 - 元従業員のログインを防止し、サービスへのアクセスMicrosoft 365する](remove-former-employee-step-1.md) <br/> |これにより、元従業員がユーザーにログインMicrosoft 365し、ユーザーがサービスにアクセスMicrosoft 365します。 <br/> |
|[手順 2 - 元従業員のメールボックスの内容を保存する](remove-former-employee-step-2.md) <br/> |これは、従業員の仕事を引き継ぐ人や訴訟がある場合に便利です。 <br/> |
|[手順 3 - 元従業員のメールを別の従業員に転送するか、共有メールボックスに変換する](remove-former-employee-step-3.md) <br/> |この操作を行うと、元従業員のメール アドレスはアクティブなままとなります。顧客やパートナーが元従業員のアドレスにメールを引き続き送信する場合は、この手順を行うと、仕事を引き継ぐユーザーに転送されます。 <br/> |
|[手順 4 - 別の従業員にデータとOneDriveアクセスOutlookする](remove-former-employee-step-6.md) <br/> |ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。 <br/><br/> アカウントを削除する前に、ユーザーのアカウントにアクセス権を与OneDrive、Outlookユーザーにアクセスする必要があります。 従業員のアカウントを削除すると、従業員のアカウントOneDrive Outlook **30** 日間保持されます。 ただし、その 30 日間は、ユーザーのアカウントを復元し、そのユーザーのコンテンツにアクセスできます。 ユーザーのアカウントを復元した場合、OneDriveおよびOutlookは 30 日後でもユーザーがアクセスできます。 <br/> |
|[手順 5 - 元従業員のモバイル デバイスをワイプしてブロックする](remove-former-employee-step-4.md) <br/> |携帯電話またはタブレットからビジネス データを削除します。  <br/> |
|[手順 6 - 元従業員からMicrosoft 365ライセンスを削除および削除する](remove-former-employee-step-7.md) <br/> |ライセンスを削除すると、別のユーザーに割り当てることができます。または、他のユーザーを採用するまで支払うことがないように、ライセンスを削除することもできます。  <br/><br/> ライセンスを削除すると、ユーザーの古いメール、連絡先、および予定表は **30 日間** 保持され、その後、完全に削除されます。 ライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  <br/> |
|[手順 7 - 元従業員のユーザー アカウントを削除する](remove-former-employee-step-7.md) <br/> |これにより、管理センターからアカウントが削除されます。 これできれいになります。 <br/> |

## <a name="related-articles"></a>関連記事

[ユーザーを復元する](restore-user.md)
