---
title: 別のユーザーにメールボックス アクセス許可を付与する - 管理者ヘルプ
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Microsoft 365 ユーザーに他のユーザーのメールボックスにアクセスする権利を与え、他のユーザーのメールボックスのメールを読んだり、送信したりすることができるようになります。
ms.openlocfilehash: 5b770b2967072ab6cc8b8abfec8176a7b6aac2c9
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66042376"
---
# <a name="give-mailbox-permissions-to-another-microsoft-365-user---admin-help"></a>別のMicrosoft 365 ユーザーにメールボックスのアクセス許可を付与する - 管理者ヘルプ

管理者として、一部のユーザーに別のユーザーのメールボックスへのアクセスを許可する会社要件を設定することができます。たとえば、アシスタントが上司のメールボックスの内容を読み取ったり、そこからメールを送信したりできるようにすること、または特定のユーザーが別のユーザーの代理でメールを送信できるようにすることが必要な場合があります。このトピックでは、これを実現する方法を説明します。
  
共有メールボックスの作成および管理の方法については、「[共有メールボックスを作成する](../email/create-a-shared-mailbox.md)」を参照してください。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。
    
## <a name="looking-to-set-up-mailbox-permissions"></a>メールボックスのアクセス許可をどのように設定しますか?

メールボックスのアクセス許可を使用すると、他のユーザーにメールボックスへの読み取り/書き込みのアクセス許可を付与できます。以下の記事では、この機能の設定および使用に必要なヘルプを提供します。
  
 **アクセス許可の設定**
  
アクセス許可を設定する最初のステップは、他のユーザーが特定のメールボックスで実行できるアクションを決定することです。ユーザーはそのメールボックスからメールを読み取ること、他のユーザーの代理としてメールを送信すること、そのメールボックスが送信元のように偽装してメールを送信することができます。それぞれのアクセス許可を設定する方法については、以下の記事を参照してください。
  
- [別のユーザーのメールボックスからメールを読み取る](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [別のユーザーのメールボックスからメールを送信する](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [別のユーザーの代理でメールを送信する](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **変更の伝達:**
  
アクセス許可を設定すると、変更がシステム全体に伝達されるまでに最大で 60 分かかる可能性があります。
  
 **アクセス許可の設定後に使用する方法:**
  
アクセス許可が付与された後に、メールボックスにアクセスするには、いくつかの異なる方法があります。このヘルプについては、次の記事を参照してください:[別のユーザーのメールボックスにアクセスする](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)。

> [!NOTE]
> アクセス許可は、現在の組織のテナント内でのみ、セットアップできます。 テナント外のユーザーが、メールボックスのアクセス許可をセットアップすることはできません。　　
  
## <a name="send-email-from-another-users-mailbox"></a>別のユーザーのメールボックスからメールを送信する

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。  
    
2. (送信許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。
    
3. [**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。

4. [**差出人を指定して送信する**] の横にある [**編集**] を選択します。 

5. [**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。 
    
6. **[追加]** を選択します。
 
::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 

2. 目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。

3. [**差出人を指定して送信する**] の横にある [**編集**] を選択します。 

4. [**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。 
    
5. **[追加]** を選択します。

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>別のユーザーのメールボックスのメールを読み取る

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。  
    
2. (読み取りを許可するメールボックスを持つ) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。
    
3. [**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。
    
4. [**読み取りと管理**] の横にある [**編集**] を選択します。 
    
5. [**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。

6. **[追加]** を選択します。


> [!NOTE]
> **[読み取り]** および **[管理]** の権限は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センターで</a> 付与された場合、**[フル アクセス]** 権限と呼ばれます。 このアクセス許可により、割り当てられたユーザー メールボックスは、アクセス許可が割り当てられているユーザー メールボックス内のメールの読み取りと管理を行うことができます。 [フル アクセス] 許可では、**[メールボックス所有者として送信する]** または **[代理人として送信する]** のアクセス許可は付与されません。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 
  
2. 目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。
    
3. [**読み取りと管理**] の横にある [**編集**] を選択します。 
    
4. [**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。

5. **[追加]** を選択します。

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>別のユーザーの代理でメールを送信する

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。  

2. (**代理送信** 許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。
    
3. [**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。
    
4. [**代理送信**] の横にある [**編集**] を選択します。

5. [**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。

6. **[追加]** を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 

2. 目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。

3. [**代理送信**] の横にある [**編集**] を選択します。
    
4. [**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。

5. **[追加]** を選択します。

::: moniker-end

> [!NOTE]
> メールボックスの *HiddenFromAddressListsEnabled* パラメーターが **True** に設定されている Outlook デスクトップ クライアントでは、メールボックスをグローバル アドレス一覧経由で Outlook に表示する必要があるため、**送信** と **代理で送信** のアクセス許可は機能しません。

## <a name="related-content"></a>関連コンテンツ
  
[他のユーザーのメールおよび予定表のアイテムを管理する](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (記事)\   
[別のユーザーまたはグループからメールを送信する](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (記事)\
[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (動画)

