---
title: Microsoft Defender for Endpointでアラート通知を構成する
description: Microsoft Defender for Endpointを使用すると、重大度やその他の条件に基づいて、セキュリティ アラートの電子メール通知設定を構成できます。
keywords: 電子メール通知、アラート通知の構成、Microsoft Defender for Endpoint、Microsoft Defender for Endpoint通知、Microsoft Defender for Endpointアラート、Windows エンタープライズ、Windows 教育
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f2e4cc2db64a01605a0003561ceda27409b16cf5
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165512"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでアラート通知を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-emailconfig-abovefoldlink)

Defender for Endpoint を構成して、新しいアラートのために指定した受信者に電子メール通知を送信できます。 この機能を使用すると、すぐに通知を受け取り、重大度に基づいてアラートに基づいて行動できる個人のグループを特定できます。

> [!NOTE]
> "セキュリティ設定の管理" アクセス許可を持つユーザーのみが電子メール通知を構成できます。 基本的なアクセス許可管理を使用するように選択した場合、セキュリティ管理者ロールまたはグローバル管理者ロールを持つユーザーは、電子メール通知を構成できます。

通知をトリガーするアラート重大度レベルを設定できます。 電子メール通知の受信者を追加または削除することもできます。 新しい受信者は、追加後にトリガーされたアラートについて通知を受け取ります。 アラートの詳細については、「 [アラート キューの表示と整理」を](alerts-queue.md)参照してください。

ロールベースのアクセス制御 (RBAC) を使用している場合、受信者は通知ルールで構成されたデバイス グループに基づく通知のみを受け取ります。
適切なアクセス許可を持つユーザーは、デバイス グループ管理スコープに制限されている通知のみを作成、編集、または削除できます。
グローバル管理者 ロールに割り当てられたユーザーのみが、すべてのデバイス グループに対して構成された通知ルールを管理できます。

電子メール通知には、アラートに関する基本情報と、詳細な調査を行うことができるポータルへのリンクが含まれています。

## <a name="create-rules-for-alert-notifications"></a>アラート通知のルールを作成する
デバイスとアラートの重大度を決定するルールを作成して、電子メール通知と通知受信者を送信できます。


1. ナビゲーション ウィンドウで、[**エンドポイント** \> **の一般的な** \> **電子メール通知****設定**\>] を選択します。

2. [ **アイテムの追加]** をクリックします。

3. [全般] 情報を指定します。
    - **ルール名** - 通知ルールの名前を指定します。
    - **組織名を含める** - 電子メール通知に表示される顧客名を指定します。
    - **テナント固有のポータル リンクを含める** - 特定のテナントへのアクセスを許可するテナント ID を持つリンクを追加します。
    - **デバイス情報を含める** - 電子メール アラート本文にデバイス名を含めます。

        > [!NOTE]
        > この情報は、Defender for Endpoint データ用に選択した地理的な場所にない受信者メール サーバーによって処理される場合があります。

    - **[デバイス]** - すべてのデバイス (グローバル管理者 ロールのみ) または選択したデバイス グループで、受信者にアラートを通知するかどうかを選択します。 詳細については、「 [デバイス グループの作成と管理](machine-groups.md)」を参照してください。
    - **アラートの重大度** - アラートの重大度レベルを選択します。

4. **[次へ]** をクリックします。

5. 受信者のメール アドレスを入力し、[ **受信者の追加**] をクリックします。 複数のメール アドレスを追加することができます。

6. [テスト メールの送信] を選択して、電子メール受信者が **電子メール** 通知を受け取ることができることを確認します。

7. [ **通知ルールの保存] をクリックします**。

## <a name="edit-a-notification-rule"></a>通知ルールを編集する

1. 編集する通知ルールを選択します。

2. [全般] タブと [受信者] タブ情報を更新します。

3. [ **通知ルールの保存] をクリックします**。

## <a name="delete-notification-rule"></a>通知ルールを削除する

1. 削除する通知ルールを選択します。

2. **[削除]** をクリックします。

## <a name="troubleshoot-email-notifications-for-alerts"></a>アラートの電子メール通知のトラブルシューティング

このセクションでは、アラートに電子メール通知を使用するときに発生する可能性があるさまざまな問題の一覧を示します。

**問題：** 目的の受信者は、通知を受け取っていないと報告します。

**ソリューション：** 電子メール フィルターによって通知がブロックされていないことを確認します。

1. Defender for Endpoint の電子メール通知が迷惑メール フォルダーに送信されていないことを確認します。 迷惑メールとしてマークします。
2. メール セキュリティ製品が Defender for Endpoint からの電子メール通知をブロックしていないことを確認します。
3. Defender for Endpoint の電子メール通知をキャッチして移動する可能性がある電子メール アプリケーションルールを確認します。

## <a name="related-topics"></a>関連項目

- [データ保持設定を更新する](data-retention-settings.md)
- [高度な機能を構成する](advanced-features.md)
- [Microsoft Defender for Endpointで脆弱性の電子メール通知を構成する](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
