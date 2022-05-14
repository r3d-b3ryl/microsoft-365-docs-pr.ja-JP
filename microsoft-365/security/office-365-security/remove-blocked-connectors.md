---
title: Microsoft 365の制限付きエンティティ ポータルからブロックされたコネクタを削除する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Microsoft 365 Defenderでブロックされたコネクタを削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0797f0ec16b8f813cf7db9b2fd27468c141ea53
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417002"
---
# <a name="remove-blocked-connectors-from-the-restricted-entities-portal"></a>制限付きエンティティ ポータルからブロックされたコネクタを削除する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**

- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

受信コネクタが侵害されている可能性があると検出された場合、リレー電子メールの送信は制限されます。 コネクタは、Microsoft 365 Defender ポータルの **[制限付きエンティティ**] ページに追加されます。 コネクタを使用して電子メールを送信すると、エラー コード 550;5.7.711 と次のテキストを含む配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) でメッセージが返されます。

> メッセージを配信できませんでした。 最も一般的な理由は、組織の電子メール コネクタがスパムやフィッシングを送信していると疑われ、電子メールの送信が許可されなくなったことです。 メール管理者にお問い合わせください。
> リモート サーバーから '550;5.7.711 アクセスが拒否されました。受信コネクタが正しくありません。 AS(2204)。'

管理者は、Microsoft 365 Defenderまたは PowerShell の [制限付きエンティティ] ページからコネクタExchange Online削除できます。

## <a name="learn-more-on-restricted-entities"></a>制限付きエンティティの詳細を確認する

制限付きエンティティとは、侵害された可能性があるか、送信制限を超えたために電子メールの送信がブロックされているエンティティです。

制限付きエンティティには次の 2 種類があります:

- **制限付きユーザー**: ユーザーを制限できる理由と制限付きユーザーを処理する方法の詳細については、「制限 [付きエンティティ ポータルからブロックされたユーザーを削除](removing-user-from-restricted-users-portal-after-spam.md)する」を参照してください。

- **制限付きコネクタ**: コネクタを制限できる理由と、制限付きコネクタを処理する方法について説明します (この記事)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Microsoft 365 Defender ポータルを開きます<https://security.microsoft.com>。 **[制限付きエンティティ**] ページに直接移動するには、<https://security.microsoft.com/restrictedentities>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事で説明されている手順に従う前に、**Exchange Online** にアクセス許可が必要です。
  - 制限付きエンティティ ポータルからコネクタを削除するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - 制限付きエンティティ ポータルへの読み取り専用アクセスの場合は、 **グローバル 閲覧者** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 制限付きエンティティ ポータルからコネクタを削除する前に、コネクタの制御を回復するために必要な手順に従ってください。 詳細については、「 [侵害されたコネクタに対応する」を](respond-compromised-connector.md)参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-connector-from-the-restricted-entities-list"></a>Microsoft 365 Defender ポータルを使用して、制限付きエンティティの一覧からコネクタを削除する

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com)で、[**電子メール & コラボレーション** の制限 **付き**\>エンティティ **の確認**\>] に移動します。 **[制限付きエンティティ**] ページに直接移動するには、<https://security.microsoft.com/restrictedentities>.

2. [ **制限付きエンティティ** ] ページで、ブロックを解除するコネクタを見つけて選択します。コネクタをクリックします。

3. 表示された **[ブロックを解除]** アクションをクリックします。

4. 表示される **ブロック解除エンティティ** ポップアップで、制限付きコネクタに関する詳細を読み取ります。 コネクタが侵害された場合に適切なアクションを実行していることを確認するために、推奨事項を確認する必要があります。

5. 完了したら、[ **ブロック解除**] をクリックします。

   > [!NOTE]
   > コネクタからすべての制限が削除されるまでに最大 1 時間かかる場合があります。

## <a name="verify-the-alert-settings-for-restricted-connectors"></a>制限付きコネクタのアラート設定を確認する

**不審なコネクタ アクティビティ** という名前の既定のアラート ポリシーは、コネクタが電子メールの中継をブロックされたときに管理者に自動的に通知します。 アラート ポリシーの詳細については、「[Alert policies in Microsoft 365 (Microsoft 365 でのアラート ポリシー)](../../compliance/alert-policies.md)」を参照してください。

> [!IMPORTANT]
> アラートを機能させるには、監査ログ検索をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \> **[ポリシーとルール]** \> **[通知ポリシー]** に移動します。

2. [ **アラート ポリシー** ] ページで、 **不審なコネクタ アクティビティ** という名前のアラートを見つけて選択します。 ポリシーを名前で並べ替えたり、**[検索ボックス]** を使用してポリシーを検索することができます。

3. 表示される **不審なコネクタ アクティビティ** ポップアップで、次の設定を確認または構成します。
   - **状態**: ![[オンに切り替え]](../../media/scc-toggle-on.png) で、アラートがオンになっていることを確認します。
   - **メール受信者**: **[編集]** をクリックし、表示される **[受信者の編集]** ポップアップで、次の設定を確認または構成します。
     - **メール通知の送信**: これが選択済み (**オン**) になっていることを確認します。
     - **メール受信者**: 既定値は **TenantAdmins** (つまり、**グローバル管理者** のメンバー) です。 受信者をさらに追加するには、ボックスの空白領域をクリックします。 受信者の一覧が表示されますので、名前を入力して、フィルター処理で受信者を選択します。 ![[削除]](../../media/m365-cc-sc-remove-selection-icon.png) アイコンをクリックすると、ボックスから既存の受信者を削除できます。 名前の横に表示されます。
     - **1 日の通知の制限**: 制限は、コネクタあたり 1 日あたり 3 件以下の通知です。

     完了したら、**[保存]** をクリックします。

4. **不審なコネクタ アクティビティ** ポップアップに戻り、[**閉じる**] をクリックします。

## <a name="use-exchange-online-powershell-to-view-and-remove-connectors-from-the-restricted-entities-list"></a>Exchange Online PowerShell を使用して、制限付きエンティティの一覧からコネクタを表示および削除する

電子メールの送信が制限されているコネクタの一覧を表示するには、次のコマンドを実行します。

```powershell
Get-BlockedConnector
```

特定のコネクタの詳細を表示するには、次のコマンドを置き換えて \<connectorId\> 実行します。

```powershell
Get-BlockedConnector -ConnectorId <connectorId>
```

制限付きエンティティの一覧からコネクタを削除するには、次のコマンドを置き換えて \<connectorId\> 実行します。

```powershell
Remove-BlockedConnector -ConnectorId <connectorId>
```

## <a name="more-information"></a>詳細

- [侵害されたコネクタに対応する](respond-compromised-connector.md)
- [ブロックされたユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)