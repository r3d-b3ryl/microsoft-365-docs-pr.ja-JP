---
title: 一般法人向け Office 365 のライセンスの競合を解決する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Office 365 for business サブスクリプションのライセンスの競合を解決する方法について説明します。
ms.openlocfilehash: c96f9e38b3799cb8b77f9422c72a7aec9d001eae
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254884"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a>一般法人向け Office 365 のライセンスの競合を解決する

新しいユーザーを作成する前に、サブスクリプションに必要なライセンスを購入することをお勧めします。 ユーザー アカウントを作成したとき、新しい ユーザーにライセンスを割り当てることができます。 すべてのライセンスをユーザーに既に割り当てているが、一部のライセンスの期限が切れている場合、あるいは既にユーザーに割り当てられているライセンスを削除するとき、ライセンスの競合が発生します。 詳細については、「[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md)」を参照してください。
  
## <a name="how-do-i-view-license-conflicts"></a>ライセンスの競合を確認する方法

1. 管理センターで、[**課金** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

    Office 365 ドイツを使用している場合は、[この<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページにアクセスしてください。

    21Vianet が運用している Office 365 を使用している場合は、[この<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページにアクセスしてください。

2. 競合に関する情報については、[**状態**] 列を確認してください。 競合がある場合は、1人以上のユーザーが有効なライセンスを必要としているという警告メッセージが表示されます。

    > [!NOTE]
    > 競合がない場合は [ **状態**] 列が表示されません。

## <a name="how-do-i-resolve-license-conflicts"></a>ライセンスの競合を解決する方法

ライセンスの競合を解決するには、[より多くのライセンスを購入](../../commerce/licenses/buy-licenses.md)するか、不要に[なったユーザーからライセンスを削除](remove-licenses-from-users.md)します。 任意で、[ユーザー アカウントを削除してライセンスを解放する](../add-users/delete-a-user.md)こともできます。
  
## <a name="related-articles"></a>関連記事 

[ユーザーにライセンスを割り当てる](assign-licenses-to-users.md)
  
[ユーザーからライセンスを削除する](remove-licenses-from-users.md)