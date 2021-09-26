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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスをセットアップすると、エラーが発生する可能性があります。 共有メールボックスに問題が発生した場合は、次の解決策を試してください。
ms.openlocfilehash: 27c3d23b3d5a496a6de85811c7aa23c8f199d654
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774630"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>共有メールボックスの問題を解決する

共有メールボックスを作成または使用するときにエラー メッセージが表示される場合は、次の解決策を試してください。 

## <a name="error-when-creating-shared-mailboxes"></a>共有メールボックスを作成するときにエラーが発生する
<a name="bkmk_Fix"> </a>

エラー メッセージが表示された場合は、プロキシ アドレス "smtp:<共有メールボックス名" が既に "" のプロキシ アドレスまたは **\> LegacyExchangeDN によって使用されています。 \<name>別のプロキシ アドレスを選択** してください。これは、共有メールボックスに既に使用されている名前を付けようとしているという意味です。 たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。 このようにするには、次の 2 つの方法があります。

  - Windows PowerShell を使用します。 手順については、このブログの投稿を参照してください。 異なるドメインで同じエイリアスを使用 [して共有メールボックスを作成する](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - エラーを回避するには、2 番目の共有メールボックスに最初とは異なる名前を付きます。 次に、管理センターで共有メールボックスの名前を変更します。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>共有メールボックスの使用時に送信アクセス許可を持たない場合のエラー

共有メールボックスを作成し、そのメールボックスからメッセージを送信しようとする場合は、次の情報を取得できます。

**このメッセージを送信する必要があります。指定したユーザーに代わってメッセージを送信するアクセス許可を持つ必要があります。**

このメッセージは、レプリケーションMicrosoft 365が発生している場合に表示されます。 新しい共有メールボックス (または追加ユーザー) に関する情報がすべてのデータ センターにレプリケートされた場合、1 時間かそれ以上で削除する必要があります。 1 時間待って、もう一度やり直してメッセージを送信します。

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)\
[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)\
[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)\
[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)


    

