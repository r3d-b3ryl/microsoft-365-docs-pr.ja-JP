---
title: Microsoft 365 Defenderで電子メールでインシデント通知を取得する
description: Microsoft 365 Defenderでインシデントの電子メール通知を取得するルールを作成する方法について説明します
keywords: インシデント, 電子メール, 電子メール通知, 構成, ユーザー, メールボックス, 電子メール, インシデント, 分析, 応答
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 600ff555762112222769fde0372716f4a89a12b9
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717585"
---
# <a name="get-incident-notifications-by-email"></a>電子メールでインシデント通知を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

新しいインシデントや既存のインシデントの更新に関するメールをスタッフに通知するMicrosoft 365 Defenderを設定できます。 次に基づいて通知を受け取ることを選択できます。

- インシデントの重大度。
- デバイス グループ。
- インシデントごとの最初の更新時のみ。

電子メール通知には、インシデントの名前、重大度、カテゴリなどのインシデントに関する重要な詳細が含まれています。 インシデントに直接移動し、すぐに分析を開始することもできます。 詳細については、「インシデントの [調査](investigate-incidents.md)」を参照してください。

電子メール通知で受信者を追加または削除できます。 新しい受信者は、インシデントの追加後に通知を受け取ります。 

>[!NOTE]
>電子メール通知設定を構成するには、[セキュリティ設定の管理] アクセス許可が必要です。 基本的なアクセス許可管理を使用するように選択した場合は、セキュリティ管理者ロールまたはグローバル管理者ロールを持つユーザーがメール通知を構成できます。 <br> <br>
同様に、組織でロールベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づいてのみ通知を作成、編集、削除、および受信できます。

## <a name="create-a-rule-for-email-notifications"></a>電子メール通知のルールを作成する

次の手順に従って新しいルールを作成し、メール通知設定をカスタマイズします。

1. ナビゲーション ウィンドウで、**インシデント メール通知設定 > Microsoft 365 Defender >** 選択します。
2. [ **項目の追加]** を選択します。
3. [ **基本]** ページで、ルール名と説明を入力し、[ **次へ**] を選択します。
4. [ **通知の設定]** ページで、次を構成します。
    - **アラートの重大度** - インシデント通知をトリガーするアラートの重大度を選択します。 たとえば、重大度の高いインシデントについてのみ通知する場合は、[ **高**] を選択します。
    - **デバイス グループ スコープ** - すべてのデバイス グループを指定するか、テナント内のデバイス グループの一覧から選択できます。
    - **インシデントごとに最初に発生した 場合にのみ通知する** - 他の選択内容に一致する最初のアラートについてのみ通知する場合に選択します。 インシデントに関連するその後の更新やアラートでは、追加の通知は送信されません。
    - [**メールに組織名を含める**] - 組織名をメール通知に表示する場合に選択します。
    - [**テナント固有のポータル リンクを含める**] - 特定の Microsoft 365 テナントにアクセスするため、メール通知にテナント ID を含むリンクを追加する場合、選択してください。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="インシデント メール通知の通知設定。":::

5. [**次へ**] を選択します。 [ **受信者]** ページで、インシデント通知を受信する電子メール アドレスを追加します。 新しい各メール アドレスを入力した後、[ **追加]** を選択します。 通知をテストし、受信者が受信トレイで受信することを確認するには、[ **テストメールの送信**] を選択します。 
6. [**次へ**] を選択します。 [ **ルールの確認** ] ページで、ルールの設定を確認し、[ **ルールの作成**] を選択します。 受信者は、設定に基づいて電子メールでインシデント通知の受信を開始します。

既存のルールを編集するには、ルールの一覧からルールを選択します。 ルール名が表示されたウィンドウで、[ **ルールの編集]** を選択し、[ **基本**]、[ **通知の設定]**、[ **受信者]** ページで変更を行います。

ルールを削除するには、ルールの一覧からルールを選択します。 ルール名が表示されたウィンドウで、[削除] を選択 **します**。

## <a name="see-also"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
