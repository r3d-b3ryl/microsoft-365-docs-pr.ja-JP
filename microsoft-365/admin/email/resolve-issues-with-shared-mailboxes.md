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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを設定すると、エラーが発生することがあります。 共有メールボックスで問題が発生した場合は、次の解決策を試してください。
ms.openlocfilehash: cf121504b53951e0aaaf248d43d045cfa937f4ed
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65437109"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>共有メールボックスの問題を解決する

共有メールボックスの作成時または使用時にエラー メッセージが表示される場合は、次の解決策を試してください。 

## <a name="error-when-creating-shared-mailboxes"></a>共有メールボックスを作成するときのエラー

エラー メッセージが表示された場合、 **プロキシ アドレス "smtp:<共有メールボックス名\>" は、プロキシ アドレスまたは LegacyExchangeDN の ""\<name> によって既に使用されています。別のプロキシ アドレスを選択してください**。これは、共有メールボックスに既に使用されている名前を付けようとしていることを意味します。 たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。 このようにするには、次の 2 つの方法があります。

  - Windows PowerShell を使用します。 手順については、このブログ投稿を参照してください: [異なるドメインで同じエイリアスを持つ共有メールボックスを作成する](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 2 つ目の共有メールボックスに、エラーを回避するために最初とは異なる名前を付けます。 次に、管理センターで、共有メールボックスの名前を目的のメールボックスに変更します。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>共有メールボックスを使用しているときに送信アクセス許可がないことに関するエラー

共有メールボックスを作成し、そこからメッセージを送信しようとすると、次のようになります。

**このメッセージを送信できませんでした。指定したユーザーに代わってメッセージを送信するアクセス許可がありません。**

このメッセージは、レプリケーション待機時間の問題が発生Microsoft 365場合に表示されます。 新しい共有メールボックス (または追加されたユーザー) に関する情報がすべてのデータ センターにレプリケートされると、1 時間ほどで削除されます。 1 時間待ってから、もう一度メッセージを送信してください。

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックス GWT を作成する](create-a-shared-mailbox.md) (記事)\
[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)\
[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)\
[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)