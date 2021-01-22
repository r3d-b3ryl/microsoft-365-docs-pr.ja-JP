---
title: 共有メールボックスの問題を解決する
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスで問題が発生した場合は、次の解決策を試してください。
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926488"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>共有メールボックスの問題を解決する

共有メールボックスを作成または使用するときにエラー メッセージが表示される場合は、次の解決策を試してください。 

## <a name="error-when-creating-shared-mailboxes"></a>共有メールボックスを作成するときにエラーが発生する
<a name="bkmk_Fix"> </a>

エラー メッセージが表示された場合は、プロキシ アドレス "smtp:<共有メールボックス名" が既にプロキシ アドレスまたは **\> " " の LegacyExchangeDN によって使用されています \<name> 。Please choose another proxy address**, it're trying to give the shared mailbox a name that's already in use. たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。 これを行うには 2 つの方法があります。

  - Windows PowerShell を使用します。 手順については、次のブログ投稿を参照してください。異なるドメインで同じエイリアスを持つ共有 [メールボックスを作成する](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 2 番目の共有メールボックスに、最初とは異なる名前を付け、エラーを回避します。 次に、管理センターで共有メールボックスの名前を変更します。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>共有メールボックスを使用するときに送信アクセス許可を持たない場合のエラー

共有メールボックスを作成し、そのメールボックスからメッセージを送信すると、次のメッセージが表示されることがあります。

**このメッセージを送信する必要があります。指定したユーザーの代わりにメッセージを送信するアクセス許可を持っている。**

このメッセージは、Microsoft 365 でレプリケーションの遅延の問題が発生している場合に表示されます。 新しい共有メールボックス (または追加されたユーザー) に関する情報がすべてのデータ センターにレプリケートされた場合は、1 時間以上後に削除されます。 1 時間待って、もう一度メッセージを送信してください。

## <a name="related-articles"></a>関連記事

[共有メールボックスについて](about-shared-mailboxes.md)

[共有メールボックスを作成する](create-a-shared-mailbox.md)

[共有メールボックスを構成する](configure-a-shared-mailbox.md)

[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)

[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md)


    

