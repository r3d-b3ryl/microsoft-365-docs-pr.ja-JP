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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'ビジネス アカウントに関連付けられたメール エイリアスと呼ばれる複数の電子メール アドレスをMicrosoft 365する方法について説明します。 '
ms.openlocfilehash: f5adc9e48110aa1e2a2e6c87f2c2f7847986d741
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766370"
---
# <a name="add-another-email-alias-for-a-user"></a>ユーザーに別のメール エイリアスを追加する
  
この記事は、ビジネス サブスクリプションMicrosoft 365管理者向けです。 ホーム ユーザー向けではありません。
  
ユーザーがアカウントを作成Microsoft 365割り当てられた電子メール アドレスは、通常、ユーザーのプライマリ メール アドレスです。 ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。 また、複数の電子メール アドレスをビジネス アカウントのユーザー Microsoft 365関連付けすることもできます。 これらの追加アドレスをエイリアスと呼びます。 
  
たとえば、Jenna が電子メール アドレス jenna@contosoco.com を持っているが、jen@contosoco.com でメールを受け取りたい場合は、その名前で彼女を参照する人もいたとします。 両方のメール アドレスが Jenna の受信トレイに移動できるよう、エイリアスを作成できます。
  
ユーザーあたり最大 400 個のエイリアスを作成できます。追加の料金やライセンスは必要ありません。
  
> [!Tip]
> 複数のユーザーが 1 つの電子メール アドレスに送信されるメールを管理する場合 (info@NodPublishers.com、sales@NodPublishers.com メールボックスを作成します。 詳細については、「共有メールボックスを [作成する」を参照してください](create-a-shared-mailbox.md)。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、Microsoft の小規模ビジネス スペシャリストとの [作業を検討してください](https://go.microsoft.com/fwlink/?linkid=2186871)。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させるにつれて、従業員と一緒に 24 時間、中小企業の専門家にアクセスできます。
  
## <a name="add-email-aliases-to-a-user"></a>ユーザーにメール エイリアスを追加する

メール エイリアスをユーザーに追加するには、グローバル管理者権限が必要です。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. [アクティブ な **ユーザー] ページ** で、[ユーザー名とメール> **管理する] のユーザーを選択します**。 ユーザーにライセンスが割り当てられていない場合、このオプションは表示しません。 
    
3. [ **+ エイリアスの追加] を選択** し、ユーザーの新しいエイリアスを入力します。   
    
    > [!Important] 
    > "パラメーター名 **'EmailAddresses** に一致するパラメーターが見つかりません" というエラー メッセージが表示された場合は、テナントのセットアップを完了するにはもう少し時間がかかります。最近追加した場合は、カスタム ドメインが表示されます。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
    
  
    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 


   > [!IMPORTANT]
   >  エラー メッセージが表示された場合 **、このユーザーはローカルの Active Directory と同期されます。一部** の詳細は、ローカルの Active Directory でのみ編集できます。これは、Active Directory が同期されたユーザーの属性に対して権限を持つという意味で、オンプレミスの Active Directory の属性を変更する必要があります。
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 リストに別のドメイン名を追加するには、「ドメイン[を追加する](../setup/add-domain.md)」を参照Microsoft 365。 
  
     
5. 完了したら、[変更の保存] **を選択します**。
    
6. 新しいエイリアスが新しいエイリアスに設定されるまで 24 時間Microsoft 365。
    
    これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。 たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると、*From* アドレスはユーザーのクライアントOutlookされます。Outlook on the webが受信されたエイリアスを使用します (これを ping-pong の原則と呼ぶ)。Outlookデスクトップは、プライマリ メール エイリアスを使用します。** たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。 Eliza がデスクトップを使用してメッセージに返信Outlook、メインの電子メール アドレスは、Eliza@NodPublishers.com として表示 Sales@NodPublishers.com。
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" を取得しましたか?

"**パラメーター名 EmailAddresses** に一致するパラメーターが見つかりません" というエラー メッセージが表示された場合は、テナントのセットアップを完了するにはもう少し時間がかかります。最近追加した場合は、カスタム ドメインが表示されます。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy または別のパートナーからサブスクリプションを購入した場合


GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。

## <a name="sending-email-from-the-proxy-address-easily"></a>プロキシ アドレスからメールを簡単に送信する

2021 年 7 月に新しい機能が展開され、ユーザーはエイリアスから簡単にメールを送信Outlook on the web。 テナント管理者が`Set-OrganizationConfig -SendFromAliasEnabled $true`コマンドレットを使用するテナントに機能がロールアウトすると、テナント内のユーザーは、各エントリが Outlook 設定のエイリアスに対応するチェック ボックスの一覧にアクセスできます。 エイリアスを選択すると、[新規作成] フォームの [From] ドロップダウンにエイリアスが表示されます。
  
## <a name="related-content"></a>関連コンテンツ

[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (記事)

[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (記事)

[Microsoft 365 でメールの転送を構成する](configure-email-forwarding.md) (記事)
