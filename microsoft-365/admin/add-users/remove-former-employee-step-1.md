---
title: 手順 1 - 従業員がユーザーにログインMicrosoft 365
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
description: 元従業員のログインをブロックし、サービスへのアクセスMicrosoft 365します。
ms.openlocfilehash: 326188e0000d3c59eb411222d3e3c47177b383ed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161692"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>手順 1 - 元従業員のログインを防止し、サービスへのアクセスMicrosoft 365する

ユーザーのサインイン アクセスを直ちに防止する必要がある場合は、パスワードをリセットする必要があります。 この手順では、ユーザーから強制的にサインアウトMicrosoft 365。

> [!NOTE]
> 他の管理者のサインアウトを開始するには、グローバル管理者である必要があります。 管理者以外のユーザーの場合は、ユーザー管理者またはヘルプデスク管理者ユーザーを使用してこのアクションを実行できます。 [管理者ロールの詳細](about-admin-roles.md)

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ユーザーの名前の横にあるボックスを選択し、[パスワードのリセット] **を選択します**。
3. 新しいパスワードを入力し、[リセット] を **選択します**。 (送信しない。
4. ユーザーの名前を選択してプロパティ ウィンドウに移動し、[アカウント]タブで [すべてのセッションからサインアウト]**を選択します**。

1 時間以内に、または現在のページを離Microsoft 365後に、もう一度サインインするように求めるメッセージが表示されます。 アクセス トークンは 1 時間有効なので、タイムラインは、そのトークンに残されている時間と、現在の Web ページから移動するかどうかによって異なります。
  
> [!IMPORTANT]
> ユーザーがメールボックス内Outlook on the webクリックした場合、すぐには追い出されない可能性があります。 ユーザーが別のタイル (OneDriveを選択したり、ブラウザーを更新したりすると、すぐにサインアウトが開始されます。
  
PowerShell を使用してユーザーをすぐにサインアウトするには [、Revoke-AzureADUserAllRefreshToken コマンドレットを参照](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) してください。
  
ユーザーのメールの使用を終了するのにどれくらいかかるかの詳細については、「[従業員のメール セッションの終了について知っておく必要があること](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)」を参照してください。

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>元従業員のサービスへのアクセスをMicrosoft 365する

> [!IMPORTANT]
 > アカウントをブロックすると、有効に 24 時間かかる場合があります。 ユーザーのサインイン アクセスを直ちに防止する必要がある場合は、上記の手順に従ってパスワードをリセットします。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ブロックする従業員の名前を選択し、ユーザーの名前の下にある [このユーザーをブロックする] の記号 **を選択します**。
3. [ **ユーザーのサインインをブロックする**] を選択し、[保存] を **選択します**。

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>元従業員の電子メール (Exchange Online) へのアクセスをブロックする

Microsoft 365 サブスクリプションの一部としてメールがある場合は、Exchange 管理センターにサインインし、次の手順に従って、元従業員のメールへのアクセスをブロックします。
  
1. <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange 管理センター</a>に移動します。
2. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.
3. 一覧からユーザー メールボックスを選択し、詳細ウィンドウ *(右側*) で、[メール アプリ]の下の [メール アプリの設定を管理する]**を選択します**。 すべての **オプション** のスライダーをオフにします。**モバイル (Exchange ActiveSync)** **、Outlook on the web**、Outlook **デスクトップ (MAPI)** **、Exchange Web** サービス **、POP3、****および IMAP** です。
4. [**保存**] を選択します。

## <a name="related-content"></a>関連コンテンツ

[Exchange Online の Exchange 管理センター](/exchange/exchange-admin-center)

[ユーザーを復元する](restore-user.md)
