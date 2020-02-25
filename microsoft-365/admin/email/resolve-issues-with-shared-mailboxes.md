---
title: 共有メールボックスの問題を解決する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスに問題が発生した場合は、これらのソリューションを試してみてください。
ms.openlocfilehash: b45c2eefa8cb4fb5fa34808223efbc1f0023161d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255165"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>共有メールボックスの問題を解決する

共有メールボックスの作成時または使用時にエラーメッセージが表示する場合は、次の考えられる解決策を試してみてください。 

## <a name="error-when-creating-shared-mailboxes"></a>共有メールボックスの作成時のエラー
<a name="bkmk_Fix"> </a>

エラーメッセージが表示された場合は、**プロキシアドレス "smtp: <共有\>メールボックス名" が、プロキシアドレスまたは "\<名前>" の LegacyExchangeDN によって既に使用されています。別のプロキシアドレスを選択してください**。これは、共有メールボックスに既に使用されている名前を付けようとしていることを意味します。 たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。 これを行うには 2 つの方法があります。

  - Windows PowerShell を使用します。 手順については、次のブログの投稿を参照してください。[Create Shared Mailboxes with Same Alias at Different Domains in Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365) (Office 365 の別のドメインで同じエイリアスを使って共有メールボックスを作成する)
    
  - エラーを回避するために、2番目の共有メールボックスの名前を開始日とは別のものにします。 次に、管理センターで、共有メールボックスの名前を目的の名前に変更します。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>共有メールボックスを使用している場合に送信アクセス許可を持たないエラー

共有メールボックスを作成してから、そのメールボックスからメッセージを送信しようとすると、次のように表示されることがあります。

**このメッセージを送信できませんでした。指定したユーザーの代わりにメッセージを送信するためのアクセス許可がありません。**

このメッセージは、Office 365 でレプリケーションの遅延の問題が発生した場合に表示されます。 新しい共有メールボックス (または追加されたユーザー) に関する情報がすべてのデータセンターでレプリケートされるときには、1時間以内に移行する必要があります。 1時間待機してから、もう一度メッセージを送信してください。

## <a name="related-articles"></a>関連記事

[共有メールボックスについて](about-shared-mailboxes.md)

[共有メールボックスを作成する](create-a-shared-mailbox.md)

[共有メールボックスを構成する](configure-a-shared-mailbox.md)

[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)

[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md)


    

