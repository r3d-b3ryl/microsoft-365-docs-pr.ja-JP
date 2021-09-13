---
title: Microsoft Defender for Endpoint でアラート通知を構成する
description: Microsoft Defender for Endpoint を使用すると、重大度や他の条件に基づいて、セキュリティアラートの電子メール通知設定を構成できます。
keywords: 電子メール通知、構成アラート通知、Microsoft Defender for Endpoint、Microsoft Defender for Endpoint 通知、Microsoft Defender for Endpoint アラート、Windows 10 enterprise、Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 857df1a9f088c316349fbbe02618a7345df5a075
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222005"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint でアラート通知を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-emailconfig-abovefoldlink)

Defender for Endpoint を構成して、新しい通知のために指定した受信者に電子メール通知を送信できます。 この機能を使用すると、直ちに通知を受け取り、重大度に基づいてアラートに基づいて行動できる個人のグループを識別できます。

> [!NOTE]
> [セキュリティ設定の管理] 権限を持つユーザーだけが電子メール通知を構成できます。 基本的なアクセス許可管理の使用を選択した場合、セキュリティ管理者またはグローバル管理者の役割を持つユーザーは、電子メール通知を構成できます。

通知をトリガーするアラートの重大度レベルを設定できます。 電子メール通知の受信者を追加または削除できます。 新しい受信者は、追加後にトリガーされたアラートに関する通知を受け取る。 アラートの詳細については、「アラート キューの [表示と整理」を参照してください](alerts-queue.md)。

役割ベースのアクセス制御 (RBAC) を使用している場合、受信者は通知ルールで構成されたデバイス グループに基づく通知のみを受信します。
適切なアクセス許可を持つユーザーは、デバイス グループ管理スコープに限定された通知のみを作成、編集、または削除できます。
グローバル管理者ロールに割り当てられたユーザーだけが、すべてのデバイス グループに対して構成されている通知ルールを管理できます。

電子メール通知には、アラートに関する基本情報と、さらに調査を行うポータルへのリンクが含まれています。

## <a name="create-rules-for-alert-notifications"></a>アラート通知のルールを作成する
電子メール通知を送信するデバイスとアラートの重大度と通知受信者を決定するルールを作成できます。


1. ナビゲーション ウィンドウで、[エンドポイント全般 **メール通知設定** \> **を** \>  \> **選択します**。

2. [アイテム **の追加] をクリックします**。

3. [全般] 情報を指定します。
    - **ルール名** - 通知ルールの名前を指定します。
    - **[組織名を含** める] - 電子メール通知に表示される顧客名を指定します。
    - **[テナント固有のポータル リンクを含める** ] - 特定のテナントへのアクセスを許可するテナント ID を含むリンクを追加します。
    - **[デバイス情報を含** める] - 電子メール通知本文にデバイス名を含める。

        > [!NOTE]
        > この情報は、Defender for Endpoint データで選択した地理的な場所ではない受信者メール サーバーによって処理される場合があります。

    - **[デバイス** ] - すべてのデバイス (グローバル管理者の役割のみ) または選択したデバイス グループの通知を受信者に通知するかどうかを選択します。 詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。
    - **アラートの重大度** - アラートの重大度レベルを選択します。

4. [**次へ**] をクリックします。

5. 受信者のメール アドレスを入力し、[受信者の追加] **をクリックします**。 複数のメール アドレスを追加することができます。

6. [テストメールの送信] を選択して、電子メール受信者が電子メール通知 **を受け取る可能性を確認します**。

7. [通知 **ルールの保存] をクリックします**。

## <a name="edit-a-notification-rule"></a>通知ルールの編集

1. 編集する通知ルールを選択します。

2. [全般] タブと [受信者] タブ情報を更新します。

3. [通知 **ルールの保存] をクリックします**。

## <a name="delete-notification-rule"></a>通知ルールの削除

1. 削除する通知ルールを選択します。

2. **[削除]** をクリックします。

## <a name="troubleshoot-email-notifications-for-alerts"></a>アラートの電子メール通知のトラブルシューティング

このセクションでは、アラートに電子メール通知を使用するときに発生する可能性があるさまざまな問題の一覧を示します。

**問題:** 対象の受信者は、通知を取得していないと報告します。

**ソリューション:** メール フィルターによって通知がブロックされないのを確認します。

1. Defender for Endpoint の電子メール通知が迷惑メール フォルダーに送信されないか確認します。 [迷惑メールではない] としてマークします。
2. メール セキュリティ製品が Defender for Endpoint からの電子メール通知をブロックされていないことを確認します。
3. Defender for Endpoint の電子メール通知をキャッチして移動する可能性がある電子メール アプリケーションルールを確認します。

## <a name="related-topics"></a>関連項目

- [データ保持設定の更新](data-retention-settings.md)
- [高度な機能を構成する](advanced-features.md)
- [Microsoft Defender for Endpoint で脆弱性メール通知を構成する](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
