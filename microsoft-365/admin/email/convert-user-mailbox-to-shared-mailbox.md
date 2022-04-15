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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'プライベート メールボックスを、1 人ではなく複数のユーザーがアクセスできる共有メールボックスに変換する方法について説明します。 '
ms.openlocfilehash: 4838dc7bd4856c89448cb501fdd20066d1c97aa2
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861942"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>ユーザー メールボックスを共有メールボックスに変換する

ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="before-you-begin"></a>はじめに

知っておくべき **重要な点をいくつか次に示** します。

- 共有メールボックスに変換する前に、ユーザー メールボックスにライセンスが割り当てられている必要があります。 そうでない場合、変換オプションがメールボックスに表示されません。 ライセンスを削除した場合、メールボックスを変換するために再度それを戻す必要があります。 ユーザー メールボックスを共有メールボックスに変換した後、ユーザーのアカウントからライセンスを削除できます。

- ライセンスがない場合は、共有メールボックスは 50 GB に制限されます。 ライセンスを削除できるように、共有メールボックスから大量の大きなメッセージ (添付ファイルを含むメッセージなど) を削除して圧縮する必要がある場合があります。

  サイズ制限を 100 GB に増やすには、共有メールボックスにExchange Onlineプラン 2 ライセンスを割り当てます。

  共有メールボックスにExchange Onlineプラン 1 ライセンスとExchange Online Archivingアドオン ライセンスを割り当てる場合は、アーカイブストレージ容量を追加するために自動拡張アーカイブを有効にすることができます。

- 共有メールボックスを固定するためにアカウントが必要なため、古いユーザーのアカウントを削除しないでください。 ユーザー アカウントを既に削除している場合、「[削除済みユーザーのメールボックスを変換する](#convert-the-mailbox-of-a-deleted-user)」 (削除されたユーザーのメールボックスを変換する) を参照してください。

- ユーザー メールボックスのアカウント パスワードをリセットする必要はありません。 ただし、パスワードをリセットしないと、変換が完了した後も、 **元のユーザー名とパスワードは共有メールボックスで引き続き機能** します。

- 受信トレイルールは、ユーザー メールボックスが共有メールボックスに変換された後も保持されます。

- 共有メールボックスにIn-Placeホールドまたは訴訟ホールドを設定するには、Exchange Online プラン 2 ライセンス *または* Exchange Onlineプラン 1 ライセンスとExchange Online Archivingアドオン ライセンスを共有メールボックスに割り当てる必要があります。

## <a name="use-the-classic-exchange-admin-center-to-convert-a-mailbox"></a>クラシック Exchange管理センターを使用してメールボックスを変換する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">クラシック Exchange管理センター</a>に移動します。

2. **[受信者]** \> **[メールボックス]** の順に選択します。

3. ユーザー メールボックスを選択します。 **[共有メールボックスに変換]** で **[変換]** を選択します。

4. メールボックスが 50 GB 未満の場合は、 [ユーザーからライセンス](../manage/remove-licenses-from-users.md)を削除し、その支払いを停止できます。 ユーザーのアカウントを削除しないでください。 共有メールボックスではそれをアンカーとして必要としています。 組織を離れる従業員のメールボックスを変換する場合は、追加の手順を実行して、従業員がログインできなくなることを確認する必要があります。 詳細については、「[元従業員をMicrosoft 365から削除する](../add-users/remove-former-employee.md)」を参照してください。

共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。

## <a name="use-the-new-exchange-admin-center-to-convert-a-mailbox"></a>新しいExchange管理センターを使用してメールボックスを変換する

1. <a href="https://admin.exchange.microsoft.com/#/homepage" target="_blank"> Exchange管理センター</a>に移動します。

2. **[受信者]** \> **[メールボックス]** の順に選択します。

3. ユーザー メールボックスを選択します。 [ **メールボックス** ] タブの [ **その他の操作]** で、[ **共有メールボックスに変換**] を選択します。

4. メールボックスが 50 GB 未満の場合は、 [ユーザーからライセンス](../manage/remove-licenses-from-users.md)を削除し、その支払いを停止できます。 ユーザーのアカウントを削除しないでください。 共有メールボックスではそれをアンカーとして必要としています。 組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。 「[元従業員をMicrosoft 365から削除する](../add-users/remove-former-employee.md)」を参照してください。

共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。

## <a name="convert-the-mailbox-of-a-deleted-user"></a>削除済みユーザーのメールボックスを変換する

ユーザー アカウントを削除した後、次の手順に従って古いメールボックスを共有メールボックスに変換します。

1. [ユーザーのアカウントを復元](../add-users/restore-user.md)します。

2. Microsoft 365 ライセンスが割り当てられていることを確認します。

3. ユーザーのパスワードをリセットします。

4. メールボックスが再作成されるまで 20 ~ 30 分待ちます。

5. メールボックスが再作成されたら、ユーザーのメールボックスからライセンスを削除します。 ユーザーの古いメールボックスは削除しないでください。 共有メールボックスではそれをアンカーとして必要としています。

6. 共有メールボックスにメンバーを追加します。

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>共有メールボックスを変換して、ユーザーの (プライベート) メールボックスに戻す

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. **[受信者]** \> **[共有]** の順に選択します。

3. 共有メールボックスを選択します。 **[通常のメールボックスに変換]** で **[変換]** を選択します。

4. 管理センターに戻ります。 [**ユーザー**] で古い共有メールボックスに関連付けられているユーザー アカウントを選びます。 アカウントにライセンスを割り当て、パスワードをリセットします。

   メールボックスの設定には数分かかりますが、その後、そのアカウントを使用するユーザーが移動する準備が整います。 それらのユーザーがサインインすると、共有メールボックス内にあったメールと予定表のアイテムが表示されるようになります。

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>ハイブリッド環境でユーザーのメールボックスを変換する

Exchange ハイブリッド環境でユーザー メールボックスを共有メールボックスに変換する方法の詳細については、次を参照してください。

- [オンプレミスのExchange環境でリモート共有メールボックスを作成または変更するためのコマンドレット](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
- [共有メールボックスは、Exchangeハイブリッド展開でディレクトリ同期が実行された後、予期せずユーザー メールボックスに変換されます](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)

> [!NOTE]
> 組織管理または受信者管理の役割グループのメンバーである場合は、Exchange管理シェルを使用して、ユーザー メールボックスをオンプレミスの共有メールボックスに変更できます。 たとえば、「 `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared` 」のように入力します。

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックス GWT を作成する](create-a-shared-mailbox.md) (記事)\
[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)\
[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)\
[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)
