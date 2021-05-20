---
title: ユーザーに別のメール エイリアスを追加する
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'ビジネスアカウントのMicrosoft 365に関連付けられた電子メール エイリアスと呼ばれる複数の電子メール アドレスを設定する方法について説明します。 '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572107"
---
# <a name="add-another-email-alias-for-a-user"></a>ユーザーに別のメール エイリアスを追加する
  
この記事は、ビジネス サブスクリプションを持つMicrosoft 365管理者を対象にしています。 ホーム ユーザー向けではありません。
  
Microsoft 365のプライマリ電子メール アドレスは、通常、アカウントの作成時にユーザーが割り当てられた電子メール アドレスです。 ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。 また、ビジネス アカウントのMicrosoft 365に関連付けられた複数の電子メール アドレスを持つことができます。 これらの追加アドレスをエイリアスと呼びます。 
  
たとえば、Jenna が jenna@contosoco.com メールアドレスを持っているが、その名前で彼女を参照する人がいるため、jen@contosoco.com でメールを受信したいとします。 両方のメールアドレスが Jenna の受信トレイに移動するように、彼女のエイリアスを作成できます。
  
ユーザーあたり最大 400 個のエイリアスを作成できます。追加の料金やライセンスは必要ありません。
  
> [!Tip]
> info@NodPublishers.com や sales@NodPublishers.com などの単一の電子メール アドレスに送信された電子メールを複数のユーザーが管理する場合は、共有メールボックスを作成します。 詳細については、「 [共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。
  
## <a name="add-email-aliases-to-a-user"></a>ユーザーにメール エイリアスを追加する

これを行うには [、管理者権限](../add-users/about-admin-roles.md) が必要です。 

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. [ **アクティブなユーザー** ] ページで、[ **ユーザー名と電子メールの管理**] >ユーザーを選択します。 ユーザーに割り当てられたライセンスがない場合、このオプションは表示されません。 
    
3. [+ **エイリアスの追加] を** 選択し、ユーザの新しいエイリアスを入力します。   
    
    > [!Important] 
    > **"EmailAddresses" というパラメータ名と一致するパラメータが見つからない** というエラー メッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかっていることを意味します。 セットアップ プロセスが完了するには、最大 4 時間かかります。 セットアッププロセスが完了するまでしばらく待ってから、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
    
  
    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 別のドメイン名を一覧に追加するには、「 [Microsoft 365にドメインを追加する](../setup/add-domain.md)」を参照してください。 
  
     
5. 完了したら、[ **変更を保存]** を選択します。
    
6. 新しいエイリアスがMicrosoft 365全体を通して入力されるまで 24 時間待ちます。
    
    これで、ユーザーはプライマリ アドレスとエイリアスを持つことになります。 たとえば、イライザ・ホフマンのプライマリアドレスである Eliza@NodPublishers.com と彼女のエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、イライザの受信トレイに送信されます。
    
  
7. **ユーザーが返信すると *、From* アドレスは、Outlookクライアントに依存します。ウェブ上のOutlookは、電子メールが受信されたエイリアスを使用します(これをピンポン原則と呼びます)。Outlookデスクトップは、彼女のプライマリ電子メールエイリアスを使用します。** たとえば、メッセージが Sales@NodPublishers.com に送信され、そのメッセージが Eliza の受信トレイに届く場合を考えてみましょう。 イライザがデスクトップを使用 Outlookしてメッセージに返信すると、プライマリ電子メール アドレスは Sales@NodPublishers.com ではなく Eliza@NodPublishers.com として表示されます。
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"パラメータ名 EmailAddresses と一致するパラメータが見つかりません" が表示されましたか?

**"EmailAddresses" というパラメータ名と一致するパラメータが見つからない** 場合は、テナントの設定が完了するまでに少し時間がかかっていることを意味します。 セットアップ プロセスが完了するには、最大 4 時間かかります。 セットアッププロセスが完了するまでしばらく待ってから、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy または別のパートナーからサブスクリプションを購入した場合


GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。

## <a name="sending-email-from-the-proxy-address-easily"></a>プロキシ アドレスから簡単にメールを送信する

2021 年 4 月に、ユーザーが web 上でOutlookを使用するときにエイリアスから簡単に送信できる新機能が展開されています。 テナント管理者がコマンドレットを使用するテナント管理者に機能がロールアウトされると `Set-OrganizationConfig -SendFromAliasEnabled $true` 、テナント内のユーザーは、各エントリがOutlook設定のエイリアスに対応するチェック ボックスの一覧にアクセスできます。 エイリアスを選択すると、[作成] フォームの [差出人] ドロップダウンにエイリアスが表示されます。
  
## <a name="related-content"></a>関連コンテンツ

[別のアドレスからメールを送信](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) する (記事)

[ユーザー名と電子メール アドレスを変更](../add-users/change-a-user-name-and-email-address.md) する (記事)

[Microsoft 365 でメールの転送を構成する](configure-email-forwarding.md) (記事)
