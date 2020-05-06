---
title: 制限されたユーザー ポータルから、ブロックされたユーザーを削除する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Office 365 の制限されたユーザー ポータルからユーザーを削除する方法についての管理者向けの説明です。 アカウントを侵害していると見なされたユーザーは通常、スパム送信者として、制限されたユーザー ポータルに追加されます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 370d2ff5f98b507cd819a57e4b0de613de7ab395
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035422"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Office 365 の制限されたユーザー ポータルから、ブロックされたユーザーを削除する

ユーザーが[サービスの制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパム ポリシー](configure-the-outbound-spam-policy.md)で指定されている送信の制限のいずれかを超えた場合、そのユーザーはメールの送信を制限されますが、メールを受信することはできます。

そのユーザーは、セキュリティ/コンプライアンス センターの制限されたユーザー ポータルに追加されます。 メールを送信しようとすると、メッセージは配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) として返され、エラー コード[ 5.1.8 ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online)と次のテキストが記載されます。

> 「有効な送信者として認識されなかったため、メッセージを配信できませんでした。」 この最も一般的な理由は、メールアドレスがスパムを送信している疑いがあり、メールを送信することを許可されていないことです。  詳細については、メールアドレスの管理者に問い合わせてください。 リモートサーバーが 「550 5.1.8 アクセスが拒否されました。アウトバウンド送信者が正しくありません」を返す

管理者は、セキュリティ/コンプライアンス センターまたは Exchange Online PowerShell の制限された送信者ポータルからユーザーを削除することができます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **制限されたユーザー**のページに直接移動するには <https://protection.office.com/restrictedusers> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 制限されたユーザー ポータルからユーザーを削除するには、**組織の管理**または**セキュリティ管理者**役割グループのメンバーである必要があります。 制限されたユーザー ポータルに読み取り専用でアクセスするには、**セキュリティ リーダー**役割グループのメンバーである必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

- 送信メールの制限を超える送信者は、アカウントが侵害されていることを示しています。 制限されたユーザー ポータルからユーザーを削除する前に、必要な手順に従ってアカウントの制御を再度行ってください。 詳細については、「[侵害された Office 365 電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>セキュリティ/コンプライアンス センターを使用して、制限されたユーザーの一覧からユーザーを削除する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[制限されたユーザー]** の順に移動します。

2. ブロックを解除するユーザーを見つけて選択します。 **[アクション]** 列の **[ブロックを解除]** をクリックします。

3. 送信が制限されているアカウントの詳細がポップアップで表示されます。 アカウントが実際に侵害された場合に備えて、適切な対策を講じるため、推奨事項を確認する必要があります。 操作が完了したら、**[次へ]** をクリックします。

4. 次の画面には、今後の侵害を防ぐための推奨事項が表示されます。 *多要素認証 (MFA) を有効にし、 操作が完了したら、**[ユーザーのブロックを解除]** をクリックします。

5. **[はい]** をクリックして変更を確定します。

   > [!NOTE]
   > 制限が解除されるまで 30 分以上かかる場合があります。

## <a name="verify-the-alert-settings-for-restricted-users"></a>制限されたユーザーのアラート設定を確認する

ユーザーがメールの送信をブロックされている場合、**メール送信を制限されているユーザー**という既定のアラート ポリシーにより、管理者に自動的に通知されます。 その設定を確認し、通知するユーザーを追加することができます。 アラート ポリシーの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](../../compliance/alert-policies.md)」を参照してください。

> [!IMPORTANT]
> アラートを機能させるには、監査ログ検索をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

1. セキュリティ/コンプライアンス センターで、**[アラート]** \> **[アラート ポリシー]** の順に移動します。

2. **[メール送信を制限されているユーザー]** アラートを見つけて選択します。

3. 表示されるポップアップで、次の設定を確認または構成します。

   - **状態**: ![[オンに切り替え]](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) で、アラートがオンになっていることを確認します。

   - **メール受信者**: **[編集]** をクリックし、表示される **[受信者の編集]** ポップアップで、次の設定を確認または構成します。

     - **メール通知の送信**: チェック ボックスが選択済み (**オン**) になっていることを確認します。

     - **メール受信者**: 既定値は **TenantAdmins** (つまり、**グローバル管理者**のメンバー) です。 受信者を追加するには、ボックスの空白の領域をクリックします。 受信者の一覧が表示されますので、名前を入力して、フィルター処理で受信者を選択します。 名前の横にある![削除アイコン](../../media/scc-remove-icon.png)をクリックすると、既存の受信者をボックスから削除することができます。

     - **1 日の通知の上限**: 既定値は**制限なし**ですが、1 日あたりの通知数の上限を選択することができます。

     完了したら、**[保存]** をクリックします。

4. **[メール送信を制限されているユーザー]** ポップアップの **[閉じる]** をクリックします。

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Exchange Online PowerShell を使用して、制限されたユーザーの一覧からユーザーを表示および削除する

メールの送信が制限されているユーザーの一覧を表示するには、次のコマンドを実行します。

```powershell
Get-BlockedSenderAddress
```

特定のユーザーの詳細を表示するには、\<emailaddress\> をユーザーのメール アドレスに置き換えて、次のコマンドを実行します。

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

構文およびパラメーターの詳細については、「[Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress)」を参照してください。

制限されたユーザーの一覧からユーザーを削除するには、\<emailaddress\> をメール アドレスに置き換えて、次のコマンドを実行します。

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

構文およびパラメーターの詳細については、「[Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress)」を参照してください。
