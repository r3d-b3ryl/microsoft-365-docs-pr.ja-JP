---
title: Office 365 の ATP の安全なリンクのしくみ
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '[安全なリンク] 機能を使用すると、Office ドキュメントや電子メールメッセージ内のハイパーリンクの時間を確認できます。 ATP の安全なリンクのしくみについては、この記事をお読みください。'
ms.openlocfilehash: bb60d57a422d908b013caf7267f21f390769cfb4
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772201"
---
# <a name="how-office-365-atp-safe-links-works"></a>Office 365 の ATP の安全なリンクのしくみ
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>ATP の安全なリンクが電子メール内の Url と連携する方法

高レベルでは、(オンプレミスではなく Office 365 でホストされている) 電子メール内の Url に対して、 [ATP の安全なリンク](atp-safe-links.md)保護がどのように機能するかを説明します。
  
1. ユーザーが電子メールメッセージを受信します。その中には、Url が含まれています。
    
2. すべての電子メールは、インターネットプロトコル (IP) とエンベロープフィルター、署名ベースのマルウェア対策、スパム対策およびマルウェア対策フィルターを適用する Exchange Online Protection によって処理されます。 
    
3. 電子メールは、ユーザーの受信トレイで到着します。
    
4. ユーザーが Office 365 にサインインし、電子メールの受信トレイに進みます。
    
5. ユーザーが電子メールメッセージを開き、電子メールメッセージ内の URL をクリックしたとき。
    
6. ATP の安全なリンク機能は、web サイトを開く前に、すぐに URL をチェックします。 URL は、ブロック、悪意、または安全として識別されます。
    
    - ユーザーに適用されるポリシーの["リライト not リライト" url リスト](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれる web サイトへの url がある場合は、その web サイトが開きます。 
    
    - URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれる web サイトに対するものである場合は、[警告ページ](atp-safe-links-warning-pages.md)が表示されます。 
    
    - 悪意があると判断された web サイトへの URL の場合は、[警告のページ](atp-safe-links-warning-pages.md)が表示されます。 
    
    - URL がダウンロード可能なファイルに送られ、組織の[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)がそのようなコンテンツをスキャンするように構成されている場合は、ダウンロード可能なファイルがチェックされます。 
    
    - URL が安全であると判断された場合は、web サイトが開きます。
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Office ドキュメントの Url で ATP の安全なリンクが機能するしくみ

大まか[に説明する](atp-safe-links.md)と、Office 365 ProPlus またはビジネスプレミアムアプリケーション (Windows、Mac、またはブラウザーでの現在のバージョンの Word、Excel、PowerPoint の場合)、またはブラウザー、iOS または Android デバイスの Office アプリ、Visio onWindows、ブラウザーの OneNote):
  
1. ユーザーは、コンピューター、スマートフォン、またはタブレットに Office 365 ProPlus または Business Premium をインストールしています。 (または、ユーザーがブラウザーで Office を使用している場合)。
    
2. ユーザーが Word、Excel、PowerPoint、OneNote (web)、または Visio (デスクトップ) を開き、職場または学校のアカウントを使用して Office 365 Enterprise にサインインします。 ドキュメントに Url が含まれている。
    
3. ユーザーがドキュメント内の URL をクリックすると、そのリンクは ATP の安全なリンクサービスによってチェックされます。
    
      - ユーザーに適用されるポリシーの["リライト not リライト" url リスト](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれる web サイトへの url がの場合、そのユーザーが web サイトに移動します。 
    
      - URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれる web サイトに対するものである場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)に移動されます。
    
      - 悪意があると判断された web サイトに URL が設定されている場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)にジャンプします。
    
      - URL がダウンロード可能なファイルに送られ、そのようなダウンロードをスキャンするように[ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)が構成されている場合は、ダウンロード可能なファイルがチェックされます。 
    
      - URL が安全であると判断された場合は、ユーザーが web サイトに移動します。
      
      - URL チェックに失敗すると、安全なリンクの保護はトリガーされません。 デスクトップクライアントでは、ユーザーはサイトに進む前に警告が表示されます。

