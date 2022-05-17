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
description: '一般法人向け Microsoft 365 アカウントにメール エイリアスと呼ばれる複数のメール アドレスを関連付ける方法を説明します。 '
ms.openlocfilehash: 2951b5eef21748ace22bee50afb24f86123fa46a
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65437461"
---
# <a name="add-another-email-alias-for-a-microsoft-365-business-subscription-user"></a>Microsoft 365 ビジネス サブスクリプション ユーザーの別の電子メール エイリアスを追加する
  
この記事は、一般法人向けサブスクリプションを持っている Microsoft 365 管理者を対象としています。ホーム ユーザー向けではありません。
  
Microsoft 365 のプライマリ メール アドレスは、通常、アカウントが作成されたときに割り当てられたメール アドレスです。ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの *[差出人]* フィールドに表示されているものが、プライマリ メール アドレスとなります。また、一般法人向け Microsoft 365 アカウントに関連付けられた複数のメール アドレスを持つこともできます。これらの追加アドレスをエイリアスと呼びます。 
  
たとえば、Jenna のメール アドレスは jenna@contosoco.com ですが、その名前で彼女を参照する人がいるため、jen@contosoco.com でメールを受信したいとします。 彼女のエイリアスを作成して、両方のメール アドレスが Jenna の受信トレイに送信されるようにすることができます。
  
ユーザーあたり最大 400 個のエイリアスを作成できます。追加の料金やライセンスは必要ありません。
  
> [!Tip]
> 1 つのメール アドレス (たとえば、info@NodPublishers.com、sales@NodPublishers.com など) に送信されたメールを複数のユーザーに管理させる場合、共有メールボックスを作成します。詳細については、「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。
  
## <a name="add-email-aliases-to-a-user"></a>ユーザーにメール エイリアスを追加する

メール エイリアスをユーザーに追加するには、グローバル管理者権限が必要です。

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. **[アクティブなユーザー]** ページで、[ユーザー] > **[ユーザー名とメールの管理]** の順に選択します。 このオプションは、ライセンスが割り当てられていないユーザーには表示されません。 
    
3. **[+ エイリアスを追加]** を選択し、ユーザーの新しいエイリアスを入力します。   
    
    > [!Important] 
    > "**パラメーター名 'EmailAddresses' に一致するパラメーターが見つかりません**" というエラー メッセージが表示される場合、これは、最近追加したテナントまたはカスタム ドメインのセットアップに少し時間がかかっていることを意味します。セットアップ プロセスが完了するには、最大 4 時間かかります。しばらくすると、セットアップ プロセスが完了します。その後、やり直してください。問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
    
  
    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 


   > [!IMPORTANT]
   >  エラー メッセージが表示された場合 **、このユーザーはローカルの Active Directory と同期されます。一部の詳細は、ローカルの Active Directory を使用してのみ編集できます**。つまり、Active Directory は同期されたユーザーの属性に対して権限を持っています。オンプレミスの Active Directory内の属性を変更する必要があります。
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。別のドメイン名を一覧に追加するには、「[Microsoft 365 にドメインを追加する](../setup/add-domain.md)」を参照してください。 
  
     
5. 完了したら、**[変更の保存]** を選びます。
    
6. Microsoft 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。
    
    これで、そのユーザーは、プライマリ アドレスとエイリアスを持つことになります。 たとえば、Eliza Hoffman のプライマリ アドレスである Eliza@NodPublishers.com と彼女のエイリアスである Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに送信されます。
    
  
7. **ユーザーが返信する場合、*差出人* アドレスはユーザーの Outlook クライアントによって異なります。Outlook on the web では、メールが受信されたエイリアスを使用します (これを卓球の原則としましょう)。Outlook デスクトップは、Eliza のプライマリ メール エイリアスを使用します。** たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに届いたとしましょう。 Eliza が Outlook デスクトップを使用してメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスとして Eliza@NodPublishers.com と表示されます。
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"パラメーター名 'EmailAddresses' に一致するパラメーターが見つかりません" と表示された場合

"**パラメーター名 'EmailAddresses' に一致するパラメーターが見つかりません**" というエラー メッセージが表示される場合、これは、最近追加したテナントまたはカスタム ドメインのセットアップに少し時間がかかっていることを意味します。セットアップ プロセスが完了するには、最大 4 時間かかります。しばらくすると、セットアップ プロセスが完了します。その後、やり直してください。問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy または別のパートナーからサブスクリプションを購入した場合


GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。

## <a name="sending-email-from-the-proxy-address-easily"></a>プロキシ アドレスからメールを簡単に送信する

2021 年 7 月に新しい機能が展開され、ユーザーは Outlook on the web を使用して、エイリアスから簡単にメールを送信できます。 テナント管理者が `Set-OrganizationConfig -SendFromAliasEnabled $true` コマンドレットを使用するテナントに機能をロールアウトすると、テナント内のユーザーは、各エントリが Outlook 設定のエイリアスに対応するチェック ボックスの一覧にアクセスできます。 エイリアスを選択すると、作成フォームの [差出人] ドロップダウンにエイリアスが表示されます。
  
## <a name="related-content"></a>関連コンテンツ

[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (記事)

[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (記事)

[Microsoft 365 でメールの転送を構成する](configure-email-forwarding.md) (記事)
