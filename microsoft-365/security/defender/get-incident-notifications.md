---
title: メールでインシデント通知を受け取Microsoft 365 Defender
description: インシデントの電子メール通知を取得するルールを作成する方法についてMicrosoft 365 Defender
keywords: インシデント、電子メール、電子メールの通知、構成、ユーザー、メールボックス、電子メール、インシデント、分析、応答
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 028723dfb41f8e4cca71ea67aea5a88a46c9bb50
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189231"
---
# <a name="get-incident-notifications-by-email"></a>電子メールでインシデント通知を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

新しいインシデントやMicrosoft 365 Defenderに関するメールをスタッフに通知するメッセージを設定できます。 次に基づいて通知を受け取る方法を選択できます。

- インシデントの重大度。
- デバイス グループ。
- インシデントごとの最初の更新のみ。

電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。 インシデントに直接移動し、分析を直に開始することもできます。 詳細については、「インシデントの [調査」を参照してください](investigate-incidents.md)。

電子メール通知で受信者を追加または削除できます。 新しい受信者は、インシデントが追加された後に通知を受け取る。 

>[!NOTE]
>電子メール通知の設定を構成するには、[セキュリティ設定の管理] アクセス許可が必要です。 基本的なアクセス許可管理を使用する場合は、セキュリティ管理者またはグローバル管理者の役割を持つユーザーが電子メール通知を構成できます。 <br> <br>
同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づいて通知を作成、編集、削除、および受信できます。

## <a name="create-a-rule-for-email-notifications"></a>電子メール通知のルールを作成する

次の手順に従って新しいルールを作成し、メール通知設定をカスタマイズします。

1. ナビゲーション ウィンドウで、[インシデントメール通知設定 > Microsoft 365 Defender >**を選択します**。
2. [アイテム **の追加] を選択します**。
3. [基本 **] ページで** 、ルール名と説明を入力し、[次へ] を **選択します**。
4. [通知の **設定] ページで** 、次の構成を行います。
    - **アラートの重大度** - インシデント通知をトリガーするアラートの重大度を選択します。 たとえば、重大度の高いインシデントのみを通知する場合は、[高] を **選択します**。
    - **デバイス グループ スコープ** - すべてのデバイス グループを指定するか、テナント内のデバイス グループの一覧から選択できます。
    - **インシデントごとに最初に発生した 場合にのみ通知する** - 他の選択内容に一致する最初のアラートについてのみ通知する場合に選択します。 インシデントに関連するその後の更新やアラートでは、追加の通知は送信されません。
    - [**メールに組織名を含める**] - 組織名をメール通知に表示する場合に選択します。
    - [**テナント固有のポータル リンクを含める**] - 特定の Microsoft 365 テナントにアクセスするため、メール通知にテナント ID を含むリンクを追加する場合、選択してください。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="インシデントメール通知の通知設定。":::

5. [**次へ**] を選択します。 [受信者 **] ページ** で、インシデント通知を受信する電子メール アドレスを追加します。 新しい **メール アドレスを** 入力した後、[追加] を選択します。 通知をテストし、受信者が受信トレイで受信を確認するには、[テストメールの送信 **] を選択します**。 
6. [**次へ**] を選択します。 [ルール **の確認] ページ** で、ルールの設定を確認し、[ルールの作成] **を選択します**。 受信者は、設定に基づいて電子メールを介してインシデント通知の受信を開始します。

既存のルールを編集するには、ルールの一覧からルールを選択します。 ルール名を持つウィンドウで、[ルールの編集] を選択し、[基本]ページ、[通知設定] ページ、および [受信者] ページで変更を **行** います。 

ルールを削除するには、ルールの一覧からルールを選択します。 ルール名を持つウィンドウで、[削除] を **選択します**。

## <a name="see-also"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
