---
title: Microsoft 365 Defender でインシデント通知を取得する
description: Microsoft 365 Defender でインシデントのメール通知を取得するルールを作成する方法について説明します
keywords: インシデント, 電子メール, 電子メール通知, 構成, ユーザー, メールボックス, 電子メール, インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848893"
---
# <a name="get-incident-notifications-by-email"></a>電子メールでインシデント通知を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender をセットアップして、新しいインシデントや既存のインシデントに対する新しい更新が発生した場合に電子メールで通知することができます。 

インシデントの重大度またはデバイス グループに基づいて通知を取得できます。 インシデントごとに最初の更新時にのみ通知を受け取るオプションを選択できます。

電子メール通知で受信者を追加または削除できます。 新しく追加された受信者は、追加後にインシデントに関する通知を受け取る。 

電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。 インシデントに直接移動して、調査を直ちに開始することもできます。 インシデントの調査の詳細については [、「Microsoft 365 Defender でのインシデントの調査」を参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)。

>[!NOTE]
>電子メール通知の設定を構成するには、[セキュリティ設定の管理] アクセス許可が必要です。 基本的なアクセス許可管理を使用する場合は、セキュリティ管理者またはグローバル管理者の役割を持つユーザーが電子メール通知を構成できます。 <br> <br>
同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合、作成、編集、削除、および受信できるのは、管理が許可されているデバイス グループに基づく通知のみです。

## <a name="create-rules-for-incident-notifications"></a>インシデント通知のルールを作成する

インシデントの最初の電子メール通知を設定するには、新しいルールを作成し、電子メール通知の設定をカスタマイズします。

1. ナビゲーション ウィンドウで、[設定インシデントの電子 **メール**  >  **通知] を選択します**。
2. [アイテム **の追加] を選択します**。
3. ルールに名前を付け **、Description** を **指定します**。

    ![インシデント電子メールの通知のルール ウィンドウを作成する](../../media/incidentemailnotif1.png) 
4. [ **次へ] を** 選択して[通知の設定 **] に移動します**。 ここでは、次の項目を指定できます。
    - **アラートの重要度** - インシデント通知をトリガーするアラートの重要度を選択します。 たとえば、重大度の高いインシデントについてのみ通知する場合は、[高] を選択します。
    - **デバイス グループのスコープ** - このドロップダウンには、ユーザーがアクセスできるすべてのデバイス グループが表示されます。 インシデント通知ルールを作成するデバイス グループを選択します。
    - **インシデントごとに最初に** 発生した場合にのみ通知する - このオプションを選択すると、他の選択内容と一致する最初のアラートにのみ電子メール通知が送信されます。 その後の更新やインシデントに関連するアラートでは、通知はトリガーされます。
    - **組織名を含** める - 顧客名が電子メール通知に表示されるかどうかを示します。
    - **テナント固有のポータル リンクを含める** - 特定のテナントへのアクセスを許可するテナント ID のリンクを追加します。
    
    ![インシデントメールの通知設定ウィンドウ](../../media/incidentemailnotif2.png)
5. [ **次へ]** を選択して [ **受信者] セクションに移動** します。 ここでは、インシデントの電子メール通知を受信する電子メール アドレスを指定できます。 すべてのメール **アドレスを入力した後、[受信者の** 追加] を選択します。

    ![インシデントメールの通知の [受信者の追加] ウィンドウ](../../media/incidentemailnotif3.png) 

6. 最後に、[次 **へ]** を選択して **[ルール** の確認] に移動し、新しいルールに関連付けられているすべての設定を表示します。 受信者は、設定に基づいて電子メールでインシデント通知の受信を開始します。

## <a name="see-also"></a>こちらもご覧ください
- [Microsoft 365 Defender のインシデントの概要](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Microsoft 365 Defender でのインシデントの優先順位付け](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Microsoft 365 Defender でのインシデントの調査](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

