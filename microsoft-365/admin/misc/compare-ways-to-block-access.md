---
title: アクセスをブロックする方法を比較する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 従業員が退職したときにMicrosoft 365へのアクセスをブロックする方法について説明します。
ms.openlocfilehash: 75e824a73e6a7778952d4ab27f82c0b41251af32
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65467890"
---
# <a name="compare-ways-to-block-access-to-microsoft-365"></a>Microsoft 365へのアクセスをブロックする方法を比較する

従業員が組織を離れた場合、良好な条件または悪い条件で、Microsoft 365へのアクセスをブロックする必要があります。 ここでは、いくつかの方法を紹介します。
  
|アクセスをブロックする方法|定義|ベスト プラクティス|
|:-----|:-----|:-----|
|サインインをブロックする  <br/> |ユーザーがMicrosoft 365にアクセスできないようにする方法の 1 つは、サインインの状態を **サインインブロック** に変更することです。 これにより、コンピューターやモバイル デバイスからMicrosoft 365にサインインできなくなりますが、以前にダウンロードまたは同期された電子メールやドキュメントを表示することはできます。 Blackberry Enterprise Service を使用している場合は、そのサービスへのアクセスも無効にすることができます。  <br/> |従業員が組織を離れる場合や、長期休暇を取得する予定であるときに使います。  <br/> |
|ユーザー パスワードを再設定する  <br/> |ユーザーがMicrosoft 365にアクセスできないようにするもう 1 つの方法は、パスワードをリセットすることです。 これにより、以前にダウンロードまたは同期された電子メールやドキュメントを引き続き表示できますが、アカウントを使用できなくなります。 その後、サインインして、選択したパスワードに変更できます。  <br/> |従業員が突然組織を離れ、今後戻る様子がなく、ビジネス データに問題があると思われる場合に使用します。  <br/> |
|割り当てられたすべてのライセンスを削除する  <br/> |もう 1 つのオプションは、ユーザーに割り当てられているMicrosoft 365 ライセンスをすべて削除することです。 これにより、Office スイート、Office Web、Yammer、SharePoint Online などのアプリケーションやサービスを使用できなくなります。 サインインすることはできますが、これらのサービスを使用することはできません。  <br/> |このユーザーがMicrosoft 365の特定の機能にアクセスする必要がなくなったと感じるときに使用します。  <br/> <br> **大事な：** ライセンスを削除すると、ユーザーのメールボックスは 30 日後に削除されます。
   
## <a name="related-articles"></a>関連資料

[Microsoft 365からユーザーをオフボードにする](../add-users/remove-former-employee.md)
    
[Microsoft 365でユーザーのパスワードをリセットする](../add-users/reset-passwords.md)
    
[一般法人向け Microsoft 365 ライセンスをユーザーに割り当てる](../manage/assign-licenses-to-users.md)
    
[ビジネス向けのMicrosoft 365のユーザーからライセンスを削除する](../manage/remove-licenses-from-users.md)
    

