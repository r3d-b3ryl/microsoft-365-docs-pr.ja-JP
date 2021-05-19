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
description: 元従業員のログインをブロックし、サービスへのアクセスMicrosoft 365します。
ms.openlocfilehash: 8eb41c3b449e63284371aaf168262307a4c21941
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535952"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>手順 1 - 元従業員のログインを防止し、サービスへのアクセスMicrosoft 365する

ユーザーのサインイン アクセスを直ちに防止する必要がある場合は、パスワードをリセットする必要があります。 この手順では、ユーザーから強制的にサインアウトMicrosoft 365。

> [!NOTE]
> サインアウトを開始するには、グローバル管理者である必要があります。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ユーザーの名前の横にあるボックスを選択し、[パスワードのリセット] **を選択します**。
3. 新しいパスワードを入力し、[リセット] を **選択します**。 (送信しない。
4. ユーザーの名前を選択してプロパティ ウィンドウに移動し、[アカウント]タブで [サインアウトの開始 **] を選択します**。

1 時間以内に、または現在のページを離Microsoft 365後に、もう一度サインインするように求めるメッセージが表示されます。 アクセス トークンは 1 時間有効なので、タイムラインは、そのトークンに残されている時間と、現在の Web ページから移動するかどうかによって異なります。
  
> [!IMPORTANT]
> ユーザーが Web 上Outlook、メールボックス内をクリックしただけで、すぐには追い出されない可能性があります。 ユーザーが別のタイル (OneDriveを選択したり、ブラウザーを更新したりすると、すぐにサインアウトが開始されます。
  
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
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
2. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.
3. ユーザーをダブルクリックし、[メールボックスの機能] **ページに移動** します。 [**モバイル デバイス] で**、[デバイスに対して Exchange ActiveSyncを無効にする] と **[OWA** を無効にする] を選択し、メッセージが表示されたら両方に対して **[は** い] と答えます。 
4. [ **電子メールの接続] で**、[無効] **を選択し** 、メッセージ **が表示されたら [はい]** と答えます。
