---
title: 手順 1 - 元従業員がログインできないようにし、Microsoft 365 サービスへのアクセスをブロックする
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
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
description: グローバル管理者は、元従業員のログインをブロックし、Microsoft 365 サービスへのアクセスをブロックできます。
ms.openlocfilehash: eec436a182f5e065f445167dea38fe99390ca105
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65436649"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>手順 1 - 元従業員がログインできないようにし、Microsoft 365 サービスへのアクセスをブロックする

ユーザーのサインイン アクセスをすぐに防ぐ必要がある場合は、パスワードをリセットする必要があります。 この手順では、ユーザーから強制的にサインアウトMicrosoft 365。

> [!NOTE]
> 他の管理者のサインアウトを開始するには、グローバル管理者である必要があります。 管理者以外のユーザーの場合は、ユーザー管理者またはヘルプデスク管理者ユーザーを使用して、この操作を実行できます。 [管理者ロールの詳細](about-admin-roles.md)

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. ユーザー名の横にあるボックスを選択し、[ **パスワードのリセット**] を選択します。
3. 新しいパスワードを入力し、[リセット] を選択 **します**。 (送信しないでください。)
4. ユーザーの名前を選択してプロパティ ウィンドウに移動し、[ **アカウント** ] タブで [ **すべてのセッションからサインアウト**] を選択します。

1 時間以内に、または現在のMicrosoft 365 ページを離れた後に、もう一度サインインするように求められます。 アクセス トークンは 1 時間有効であるため、タイムラインは、そのトークンに残されている時間と、現在の Web ページから移動するかどうかによって異なります。
  
> [!IMPORTANT]
> ユーザーがOutlook on the webにいる場合は、メールボックス内をクリックするだけで、すぐには追い出されない可能性があります。 OneDriveなどの別のタイルを選択するか、ブラウザーを更新するとすぐに、サインアウトが開始されます。
  
PowerShell を使用してユーザーをすぐにサインアウトするには、 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) コマンドレットを参照してください。
  
ユーザーのメールの使用を終了するのにどれくらいかかるかの詳細については、「[従業員のメール セッションの終了について知っておく必要があること](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)」を参照してください。

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>元従業員のMicrosoft 365 サービスへのアクセスをブロックする

> [!IMPORTANT]
 > アカウントをブロックするには、最大で 24 時間かかる場合があります。 ユーザーのサインイン アクセスをすぐに防ぐ必要がある場合は、上記の手順に従ってパスワードをリセットします。

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. ブロックする従業員の名前を選択し、ユーザーの名前の下で [ **このユーザーをブロック**] の記号を選択します。
3. [ **ユーザーのサインインをブロックする**] を選択し、[保存] を選択 **します**。

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>元従業員の電子メール (Exchange Online) へのアクセスをブロックする

Microsoft 365 サブスクリプションの一部としてメールがある場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>にサインインし、次の手順に従って元従業員がメールにアクセスできないようにします。
  
1. Exchange管理センター>**受信者メールボックスに**\>移動 <a href="https://go.microsoft.com/fwlink/?linkid=2183135" target="_blank">します</a>。
1. 一覧からユーザー メールボックスを選択し、*詳細ウィンドウ* (右側) で [**電子メール** アプリ] の [**電子メール アプリの設定の管理**] を選択します。 すべてのオプションのスライダーを **オフ** にします。**モバイル (Exchange ActiveSync)**、**Outlook on the web**、**Outlook デスクトップ (MAPI)**、**Exchange Web サービス**、**POP3**、**IMAP**。
1. [**保存**] を選択します。

## <a name="related-content"></a>関連コンテンツ

[Exchange OnlineのExchange管理センター](/exchange/exchange-admin-center) (記事)\

[ユーザーを復元する](restore-user.md) (記事)
