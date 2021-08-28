---
title: 制限されたユーザー ポータルからブロックされたユーザーを削除する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Microsoft 365 Defender ポータルの制限されたユーザー ページからユーザーを削除する方法についての管理者向けの説明です。 アカウントを侵害していると見なされたユーザーは通常、スパム送信者として、制限されたユーザー ポータルに追加されます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 774f47c65f98a2e93ee6e50406afe897a315de12
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58572397"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>Microsoft 365 の制限されたユーザー ポータルから、ブロックされたユーザーを削除する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

ユーザーが[サービスの制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパム ポリシー](configure-the-outbound-spam-policy.md)で指定されている送信の制限のいずれかを超えた場合、そのユーザーはメールの送信を制限されますが、メールを受信することはできます。

Microsoft 365 Defender ポータルの **制限されたユーザー** ページにユーザーが追加されます。 メールを送信しようとすると、メッセージは配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) として返され、エラー コード[ 5.1.8 ](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online)と次のテキストが記載されます。

> 「有効な送信者として認識されなかったため、メッセージを配信できませんでした。」 この最も一般的な理由は、メールアドレスがスパムを送信している疑いがあり、メールを送信することを許可されていないことです。  詳細については、メールアドレスの管理者に問い合わせてください。 リモートサーバーが 「550 5.1.8 アクセスが拒否されました。アウトバウンド送信者が正しくありません」を返す

管理者は、Microsoft 365 Defender または Exchange Online PowerShell の制限されたユーザー ページからユーザーを削除することができます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **制限されたユーザー** のページに直接移動するには <https://security.microsoft.com/restrictedusers> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 制限されたユーザー ポータルからユーザーを削除するには、**組織の管理** または **セキュリティ管理者** 役割グループのメンバーである必要があります。
  - 制限されたユーザー ポータルに読み取り専用でアクセスするには、**グローバル閲覧者** または **セキュリティ 閲覧者** 役割グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 送信メールの制限を超える送信者は、アカウントが侵害されていることを示しています。 制限されたユーザー ポータルからユーザーを削除する前に、必要な手順に従ってアカウントの制御を再度行ってください。 詳細については、「[侵害された Office 365 電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>Microsoft 365 Defender ポータルを使用して、制限されたユーザーの一覧からユーザーを削除する

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]**  >  **[レビュー]**  >  **[制限されたユーザー]** に移動します。

2. **[制限されたユーザー]** ページで、ブロックを解除したいユーザーをクリックして検索し、選択します。

3. 表示された **[ブロックを解除]** アクションをクリックします。

4. 表示される **[ブロックを解除したユーザー]** ポップアップで、制限されたアカウントの詳細を確認します。 アカウントが侵害された場合に備えて、適切な対策を講じるため、推奨事項を確認する必要があります。

   完了したら、**[次へ]** をクリックします。

5. 次の画面には、今後の侵害を防ぐための推奨事項が表示されます。 *多要素認証 (MFA) を有効にし、パスワードをリセットすることは良い防御方法です。

   完了したら、**[送信]** をクリックします。

6. **[はい]** をクリックして変更を確定します。

   > [!NOTE]
   > ユーザーからすべての制限を削除するには、最大で 1 時間かかる可能性があります。

## <a name="verify-the-alert-settings-for-restricted-users"></a>制限されたユーザーのアラート設定を確認する

ユーザーがメールの送信をブロックされている場合、**メール送信を制限されているユーザー** という既定のアラート ポリシーにより、管理者に自動的に通知されます。 その設定を確認し、通知するユーザーを追加することができます。 アラート ポリシーの詳細については、「[Alert policies in Microsoft 365 (Microsoft 365 でのアラート ポリシー)](../../compliance/alert-policies.md)」を参照してください。

> [!IMPORTANT]
> アラートを機能させるには、監査ログ検索をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \> **[ポリシーとルール]** \> **[通知ポリシー]** に移動します。

2. **[通知ポリシー]** ページで、「**メール送信を制限されたユーザー**」という名前の通知を見つけて選択します。 ポリシーを名前で並べ替えたり、**[検索ボックス]** を使用してポリシーを検索することができます。

3. 表示される **[ユーザーに対してメールの送信が制限されました]** ポップアップで、次の設定を確認または構成します。
   - **状態**: ![[オンに切り替え]](../../media/scc-toggle-on.png) で、アラートがオンになっていることを確認します。
   - **メール受信者**: **[編集]** をクリックし、表示される **[受信者の編集]** ポップアップで、次の設定を確認または構成します。
     - **メール通知の送信**: これが選択済み (**オン**) になっていることを確認します。
     - **メール受信者**: 既定値は **TenantAdmins** (つまり、**グローバル管理者** のメンバー) です。 受信者を追加するには、ボックスの空白の領域をクリックします。 受信者の一覧が表示されますので、名前を入力して、フィルター処理で受信者を選択します。 ![[削除]](../../media/m365-cc-sc-remove-selection-icon.png) アイコンをクリックすると、ボックスから既存の受信者を削除できます。 名前の横に表示されます。
     - **1 日の通知の上限**: 既定値は **制限なし** ですが、1 日あたりの通知数の上限を選択することができます。

     完了したら、**[保存]** をクリックします。

4. **[メール送信を制限されているユーザー]** ポップアップの **[閉じる]** をクリックします。

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Exchange Online PowerShell を使用して、制限されたユーザーの一覧からユーザーを表示および削除する

メールの送信が制限されているユーザーの一覧を表示するには、次のコマンドを実行します。

```powershell
Get-BlockedSenderAddress
```

特定のユーザーの詳細を表示するには、\<emailaddress\>をユーザーのメール アドレスに置き換えて、次のコマンドを実行します。

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

構文およびパラメーターの詳細については、「[Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress)」を参照してください。

制限されたユーザーの一覧からユーザーを削除するには、\<emailaddress\> をメール アドレスに置き換えて、次のコマンドを実行します。

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

構文およびパラメーターの詳細については、「[Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress)」を参照してください。
