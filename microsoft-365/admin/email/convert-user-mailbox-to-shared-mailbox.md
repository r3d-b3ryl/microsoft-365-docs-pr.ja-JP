---
title: ユーザー メールボックスを共有メールボックスに変換する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'プライベート メールボックスを、1 人ではなく複数のユーザーがアクセスできる共有メールボックスに変換する方法について説明します。 '
ms.openlocfilehash: 67a4ce19e355b8a227e9471f164344ad22deffbc
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774666"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>ユーザー メールボックスを共有メールボックスに変換する

ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。

## <a name="before-you-begin"></a>開始する前に

**知っておく必要がある重要な点事項を次に示します**

- 共有メールボックスに変換する前に、変換するユーザー メールボックスにライセンスを割り当てる必要があります。 そうでない場合、変換オプションがメールボックスに表示されません。 ライセンスを削除した場合、メールボックスを変換するために再度それを戻す必要があります。 ライセンスは、メールボックスを共有に変換した後に、ユーザー アカウントから削除できます。

- 共有メールボックスには、ライセンスが割り当てられていない場合、最大 50 GB のデータを使用できます。 これ以上のデータを保持するには、ライセンスを割り当てる必要があります。 ライセンスを削除するには、(添付ファイルがあるものなど) 大きなメールを多数削除してサイズを小さくする必要があります。

- 古いユーザー アカウントは削除しないでください。 それは共有メールボックスの固定に必要です。 ユーザー アカウントを既に削除している場合、「[削除済みユーザーのメールボックスを変換する](#convert-the-mailbox-of-a-deleted-user)」 (削除されたユーザーのメールボックスを変換する) を参照してください。

- メールボックスが共有メールボックスに変換された後でも、ルールは変更されません。

## <a name="use-the-classic-exchange-admin-center-to-convert-a-mailbox"></a>クラシック サーバー管理Exchangeを使用してメールボックスを変換する
 
1. クラシック 管理センター<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">にExchangeします</a>。

2. **[受信者]** \> **[メールボックス]** の順に選択します。

3. ユーザー メールボックスを選択します。 **[共有メールボックスに変換]** で **[変換]** を選択します。

4. メールボックスが 50 GB より小さい場合は、ユーザー[](../manage/remove-licenses-from-users.md)からライセンスを削除し、支払いを停止できます。 ユーザーのアカウントを削除しない。 共有メールボックスではそれをアンカーとして必要としています。 組織を離れる従業員のメールボックスを変換する場合は、追加の手順を実行して、その従業員がログインできなくなったか確認する必要があります。 詳細については、「元従業員を従業員[から削除する」を参照Microsoft 365。](../add-users/remove-former-employee.md)
    
> [!NOTE]
> メールボックスの変換中にユーザーのパスワードをリセットする必要はありません。 ただし、パスワードがリセットされない場合、メールボックスの変換が終了した後も **元のユーザー名とパスワードは引き続き機能します**。

共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。

> [!NOTE]
> 共有メールボックスには、別途ライセンスが必要ではありません。 ただし、In-Place アーカイブを有効にするか、共有メールボックスに In-Place 保留または訴訟ホールドを設定する場合は、Exchange Online Archiving または Exchange Online プラン 2 ライセンスを持つ Exchange Online プラン 1 をメールボックスに割り当てる必要があります。

## <a name="use-the-new-exchange-admin-center-to-convert-a-mailbox"></a>メールボックスを変換Exchange新しい管理センターを使用する

1. [管理センター] <a href="https://admin.exchange.microsoft.com/#/homepage" target="_blank">Exchange移動します</a>。

2. **[受信者]** \> **[メールボックス]** の順に選択します。

3. ユーザー メールボックスを選択します。 [メールボックス] **タブの** [その他の **操作] で**、[共有 **メールボックスに変換] を選択します**。

4. メールボックスが 50 GB より小さい場合は、ユーザー[](../manage/remove-licenses-from-users.md)からライセンスを削除し、支払いを停止できます。 ユーザーのアカウントを削除しない。 共有メールボックスではそれをアンカーとして必要としています。 組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。 「元[従業員を削除する」を参照Microsoft 365。](../add-users/remove-former-employee.md)
    
> [!NOTE]
> メールボックスの変換中にユーザーのパスワードをリセットする必要はありません。 ただし、パスワードがリセットされない場合、メールボックスの変換が終了した後も **元のユーザー名とパスワードは引き続き機能します**。

共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。

> [!NOTE]
> 共有メールボックスには、別途ライセンスが必要ではありません。 ただし、In-Place アーカイブを有効にするか、共有メールボックスに In-Place 保留または訴訟ホールドを設定する場合は、Exchange Online Archiving または Exchange Online プラン 2 ライセンスを持つ Exchange Online プラン 1 をメールボックスに割り当てる必要があります。

## <a name="convert-the-mailbox-of-a-deleted-user"></a>削除済みユーザーのメールボックスを変換する

ユーザー アカウントを削除した後、次の手順に従って、古いメールボックスを共有メールボックスに変換します。

1. [ユーザーのアカウントを復元](../add-users/restore-user.md)します。

2. ライセンスが割りMicrosoft 365ライセンスが割り当てられているか確認します。

3. ユーザーのパスワードをリセットします。
    
4. メールボックスが再作成されるのを 20 ~ 30 分待ちます。
      
6. メールボックスを再作成したら、ユーザーのメールボックスからライセンスを削除します。 ユーザーの古いメールボックスは削除しないでください。 共有メールボックスではそれをアンカーとして必要としています。
    
7. 共有メールボックスにメンバーを追加します。

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>共有メールボックスを変換して、ユーザーの (プライベート) メールボックスに戻す

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
   
2. **[受信者]** \> **[共有]** の順に選択します。

3. 共有メールボックスを選択します。 **[通常のメールボックスに変換]** で **[変換]** を選択します。

4. 管理センターに戻ります。 [**ユーザー**] で古い共有メールボックスに関連付けられているユーザー アカウントを選びます。 アカウントにライセンスを割り当て、パスワードをリセットします。

   メールボックスをセットアップするには数分かかりますが、その後、そのアカウントを使用するユーザーは準備が整いました。 それらのユーザーがサインインすると、共有メールボックス内にあったメールと予定表のアイテムが表示されるようになります。

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>ハイブリッド環境でユーザーのメールボックスを変換する

ハイブリッド環境でユーザー メールボックスを共有メールボックスに変換する方法のExchange参照してください。

 - [オンプレミスのユーザー環境でリモート共有メールボックスを作成または変更Exchangeコマンドレット](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [共有メールボックスは、ハイブリッド展開でディレクトリ同期を実行した後、予期Exchangeユーザー メールボックスに変換されます。](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> 組織の管理役割グループまたは受信者管理役割グループのメンバーである場合は、Exchange 管理シェルを使用して、ユーザー メールボックスをオンプレミスの共有メールボックスに変更できます。 たとえば、`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared` などです。

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)\
[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)\
[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)\
[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)
