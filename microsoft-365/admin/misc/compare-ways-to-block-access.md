---
title: Office 365 へのアクセスをブロックする方法を比較する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 従業員が組織を離れたときに Office 365 へのアクセスをブロックする方法について説明します。
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257397"
---
# <a name="compare-ways-to-block-access-to-office-365"></a>Office 365 へのアクセスをブロックする方法を比較する

従業員が組織を離れたときは、その条件に関わらず、Office 365 へのアクセスをブロックする必要があります。ここでは、いくつかの方法を紹介します。
  
||||
|:-----|:-----|:-----|
|**アクセスをブロックする方法** <br/> |**定義** <br/> |**注意事項** <br/> |
|サインインをブロックする  <br/> |特定のユーザーからの Office 365 へのアクセスをブロックする 1 つの方法は、そのユーザーのサインイン状態を [ **サインインのブロック**] に変更することです。これにより、組織を離れた従業員がコンピューターやモバイル デバイスから Office 365 にサインインすることを防ぎます。ただし、以前にダウンロードした、または同期したメールとドキュメントは表示されます。Blackberry Enterprise Service を使用している場合は、組織を離れたユーザーの Blackberry Enterprise Service へのアクセスも無効にすることができます。  <br/> |従業員が組織を離れる場合や、長期休暇を取得する予定であるときに使います。  <br/> |
|ユーザー パスワードを再設定する  <br/> |特定のユーザーが Office 365 にアクセスすることを防止するには、パスワードをリセットする方法もあります。これにより、そのユーザーが自分のアカウントを使用することを防ぎます。ただし、以前にダウンロードした、または同期したメールとドキュメントは表示されます。そのユーザーとしてサインインし、パスワードを別のパスワードに変更します。  <br/> |従業員が突然組織を離れ、今後戻る様子がなく、ビジネス データに問題があると思われる場合に使用します。  <br/> |
|割り当てられたすべてのライセンスを削除する  <br/> |もう一つのオプションは、ユーザーに割り当てられたすべての Office 365 ライセンスを削除することです。 これにより、Office スイート、web 用の Office アプリ、Yammer、SharePoint Online などのアプリケーションやサービスを使用できなくなります。 サインインすることはできますが、これらのサービスを使用することはできません。  <br/> |そのユーザーが Office 365 の特定の機能にアクセスする必要がなくなったと感じる場合に使用します。  <br/> <br> **重要:** ライセンスを削除すると、ユーザーのメールボックスは30日後に削除されます。
   
## <a name="related-articles"></a>関連記事

[Office 365 からユーザーを削除する](../add-users/remove-former-employee.md)
    
[Office 365 でユーザーのパスワードを再設定する](../add-users/reset-passwords.md)
    
[一般法人向け Office 365 ライセンスをユーザーに割り当てる](../manage/assign-licenses-to-users.md)
    
[一般法人向け Office 365 のユーザーからライセンスを削除する](../manage/remove-licenses-from-users.md)
    

