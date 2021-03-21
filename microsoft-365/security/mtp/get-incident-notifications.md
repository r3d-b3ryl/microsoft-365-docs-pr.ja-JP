---
title: Microsoft 365 Defender でインシデント通知を取得する
description: Microsoft 365 Defender でインシデントのメール通知を取得するルールを作成する方法について説明します。
keywords: インシデント、電子メール、電子メールの通知、構成、ユーザー、メールボックス、電子メール、インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c6b255f7815a5b49cd0fb5ed27da0cf642ff2ca7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928834"
---
# <a name="get-incident-notifications-by-email"></a>電子メールでインシデント通知を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender をセットアップして、新しいインシデントや既存のインシデントに対する新しい更新が発生する度に電子メールで通知できます。 

インシデントの重大度またはデバイス グループに基づいて通知を取得できます。 また、インシデントごとの最初の更新時にのみ通知を受け取る場合も選択できます。

電子メール通知で受信者を追加または削除できます。 新しく追加された受信者は、インシデントが追加された後に通知を受け取る。 

電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。 インシデントに直接移動して、調査を直ちから開始することもできます。 インシデントの調査の詳細については [、「Microsoft 365 Defender](./investigate-incidents.md)でのインシデントの調査」を参照してください。

>[!NOTE]
>電子メール通知設定を構成するには、「セキュリティ設定の管理」権限が必要です。 基本的なアクセス許可管理を使用する場合は、セキュリティ管理者またはグローバル管理者の役割を持つユーザーが電子メール通知を構成できます。 <br> <br>
同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づいて通知を作成、編集、削除、および受信できます。

## <a name="create-rules-for-incident-notifications"></a>インシデント通知のルールを作成する

インシデントの最初の電子メール通知を設定するには、新しいルールを作成し、電子メール通知設定をカスタマイズします。

1. ナビゲーション ウィンドウで、[設定インシデントの電子 **メール**  >  **通知] を選択します**。
2. [アイテム **の追加] を選択します**。
3. [名前] でルールに名前を **付け、[** 説明] を **指定します**。

    ![インシデント メールの notifs のルール ウィンドウを作成する](../../media/incidentemailnotif1.png) 
4. [次 **へ] を** 選択して、[通知の **設定] に移動します**。 ここでは、以下を指定できます。
    - **アラートの重大度** - インシデント通知をトリガーするアラートの重大度を選択します。 たとえば、重大度の高いインシデントのみを通知する場合は、[高] を選択します。
    - **デバイス グループスコープ** - このドロップダウンには、ユーザーがアクセスできるすべてのデバイス グループが表示されます。 インシデント通知ルールを作成するデバイス グループを選択します。
    - **インシデントごとに最初に発生した** 場合にのみ通知する - このオプションを選択すると、他の選択内容に一致する最初のアラートにのみ電子メール通知が送信されます。 後でインシデントに関連する更新プログラムまたはアラートは通知をトリガーしない。
    - **[組織名を含** める] - 顧客名が電子メール通知に表示されるかどうかを示します。
    - **[テナント固有のポータル リンクを含める** ] - 特定のテナントへのアクセスを許可するテナント ID を含むリンクを追加します。
    
    ![インシデントメールの Notif 設定ウィンドウ](../../media/incidentemailnotif2.png)
5. [次 **へ] を** 選択して[ **受信者] セクションに移動** します。 ここでは、インシデントメール通知を受信する電子メール アドレスを指定できます。 [すべての **メール アドレスを入力した後に** 受信者を追加する] を選択します。

    ![インシデント 電子メールの notifs の [受信者の追加] ウィンドウ](../../media/incidentemailnotif3.png) 

6. 最後に、[ **次へ] を** 選択して **[ルール** の確認] に移動し、新しいルールに関連付けられているすべての設定を確認できます。 受信者は、設定に基づいて電子メールを介してインシデント通知の受信を開始します。

## <a name="see-also"></a>関連項目
- [Microsoft 365 Defender のインシデントの概要](./incidents-overview.md)
- [Microsoft 365 Defender でのインシデントの優先順位付け](./incident-queue.md)
- [Microsoft 365 Defender のインシデントを調査する](./investigate-incidents.md)