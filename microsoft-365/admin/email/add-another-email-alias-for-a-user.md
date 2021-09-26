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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'ビジネス アカウントに関連付けられたメール エイリアスと呼ばれる複数の電子メール アドレスをMicrosoft 365する方法について説明します。 '
ms.openlocfilehash: 83413bcf0adffd0af09405db7e936cec523530d9
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774858"
---
# <a name="add-another-email-alias-for-a-user"></a>ユーザーに別のメール エイリアスを追加する
  
この記事は、ビジネス サブスクリプションMicrosoft 365管理者向けです。 ホーム ユーザー向けではありません。
  
ユーザーがアカウントを作成Microsoft 365割り当てられた電子メール アドレスは、通常、ユーザーのプライマリ メール アドレスです。 ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。 また、複数の電子メール アドレスをビジネス アカウントのユーザー Microsoft 365関連付けすることもできます。 これらの追加アドレスをエイリアスと呼びます。 
  
たとえば、Jenna が電子メール アドレス jenna@contosoco.com を持っているが、jen@contosoco.com でメールを受け取りたい場合は、その名前で彼女を参照する人もいたとします。 両方のメール アドレスが Jenna の受信トレイに移動できるよう、エイリアスを作成できます。
  
ユーザーあたり最大 400 個のエイリアスを作成できます。追加の料金やライセンスは必要ありません。
  
> [!Tip]
> 複数のユーザーが 1 つの電子メール アドレスに送信されるメールを管理する場合 (info@NodPublishers.com、sales@NodPublishers.com メールボックスを作成します。 詳細については、「共有メールボックスの [作成」を参照してください](create-a-shared-mailbox.md)。
  
## <a name="add-email-aliases-to-a-user"></a>ユーザーにメール エイリアスを追加する

これを行うには [、管理者のアクセス許可](../add-users/about-admin-roles.md) が必要です。 

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. [アクティブ な **ユーザー] ページ** で、[ユーザー名とメール> **管理する] のユーザーを選択します**。 ユーザーにライセンスが割り当てられていない場合、このオプションは表示しません。 
    
3. [+ **エイリアスの追加] を選択** し、ユーザーの新しいエイリアスを入力します。   
    
    > [!Important] 
    > エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
    
  
    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 リストに別のドメイン名を追加するには、「[ドメインをリストに追加する」をMicrosoft 365。](../setup/add-domain.md) 
  
     
5. 完了したら、[変更の保存] **を選択します**。
    
6. 新しいエイリアスが新しいエイリアスに設定されるまで 24 時間Microsoft 365。
    
    これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。 たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると *、From* アドレスはユーザーのクライアントOutlookされます。Outlook on the webが受信されたエイリアスを使用します (これを ping-pong の原則と呼ぶ)。Outlookデスクトップは、プライマリ メール エイリアスを使用します。** たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。 Eliza がデスクトップを使用してメッセージに返信Outlook、メインの電子メール アドレスは、Eliza@NodPublishers.com として表示 Sales@NodPublishers.com。
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" を取得しましたか?

"パラメーター名 **EmailAddresses** に一致するパラメーターが見つかりません" というエラー メッセージが表示された場合は、テナントのセットアップを完了するにはもう少し時間がかかっています。最近追加した場合は、カスタム ドメインが表示されます。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy または別のパートナーからサブスクリプションを購入した場合


GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。

## <a name="sending-email-from-the-proxy-address-easily"></a>プロキシ アドレスからメールを簡単に送信する

2021 年 7 月に新しい機能が展開され、ユーザーはエイリアスから簡単にメールを送信Outlook on the web。 テナント管理者がコマンドレットを使用するテナントに機能がロールアウトすると、テナント内のユーザーは、各エントリが Outlook 設定のエイリアスに対応するチェック ボックスの一覧にアクセスできます。 `Set-OrganizationConfig -SendFromAliasEnabled $true` エイリアスを選択すると、[新規作成] フォームの [From] ドロップダウンにエイリアスが表示されます。
  
## <a name="related-content"></a>関連コンテンツ

[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (記事)

[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (記事)

[Microsoft 365 でメールの転送を構成する](configure-email-forwarding.md) (記事)
