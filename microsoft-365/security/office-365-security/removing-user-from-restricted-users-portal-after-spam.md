---
title: 迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
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
description: 'ユーザーがスパムとして分類されている Office 365 からメッセージを送り続ける場合、メッセージを送信しないよう制限されます。 '
ms.openlocfilehash: e942cd9012c3eba226db58808031ac200fbdfeca
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558634"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する

ユーザーが、Office 365 からスパムとして分類される 電子メールを送信し続ける場合、電子メールの送信は制限されますが、それでも受信はできます。 ユーザーはサービスに不適切な送信者として記録され、次のような配信不能レポート（NDR）を受け取ります。

> 「有効な送信者として認識されなかったため、メッセージを配信できませんでした。」 この最も一般的な理由は、メールアドレスがスパムを送信している疑いがあり、メールを送信することを許可されていないことです。  詳細については、メールアドレスの管理者に問い合わせてください。 リモートサーバーが 「550 5.1.8 アクセスが拒否されました。アウトバウンド送信者が正しくありません」を返す

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

予想所要時間 : 5 分

この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可については、「[Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)」の「スパム対策」のエントリを参照してください。

以下の手順はリモート PowerShell 経由でも実行することができます。 Get-BlockedSenderAddress コマンドレットを使用して制限付きユーザーのリストを取得し、Remove-BlockedSenderAddress を使用して制限を削除します。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>ブロックされた Office 365 メールアカウントの制限を削除する

このタスクは、セキュリティ/コンプライアンス センター（SCC）で実行します。 SCC の詳細については、[セキュリティ/コンプライアンス センターにアクセス](../../compliance/go-to-the-securitycompliance-center.md)してください。 これらの機能を実行するには、**組織管理**または**セキュリティ管理者**の役割グループに属している必要があります。 SCC 役割グループの詳細については、[「セキュリティ/コンプライアンスセンターの権限」を参照](permissions-in-the-security-and-compliance-center.md)してください。

1. Office 365　の包括的な管理者権限を持つ職場または学校のアカウントを使用して、Office 365 セキュリティ/コンプライアンスセンターにサインインし、左側のリストで **[脅威の管理]** を展開し、**[レビュー]** を選択して、**[制限付きユーザー]** を選びます。

    > [!TIP]
    > **制限付きユーザー**ページ (旧称アクション センター、セキュリティ&amp; コンプライアンス センター内) に直接アクセスするには、次の URL を使用します: [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. このページには、メールの送信がブロックされているユーザーの一覧が表示されます。  制限を削除するユーザーを見つけて、**[ブロック解除]** を選択します。

3. 送信が制限されているアカウントの詳細がポップアップで表示されます。 アカウントが実際に侵害された場合に備えて、適切な対策を講じるため、推奨事項を確認する必要があります。 操作が完了したら、**[次へ]** をクリックします。

4. 次の画面には、今後の侵害を防ぐための推奨事項が表示されます。 *多要素認証 (MFA) を有効にし、 操作が完了したら、**[ユーザーのブロックを解除]** をクリックします。

5. **[はい]** をクリックして変更を確定します。

    > [!NOTE]
    > 制限が解除されるまで 30 分以上かかる場合があります。

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>この事態の際に管理者にアラートが送信されるようにする

「メールの送信を制限されたユーザー」アラートは、Office 365 のセキュリティ/コンプライアンスのアラート ポリシーページでポリシーとして利用できます。 これは以前は送信用のスパムポリシーでしたが、現在は Office 365 アラート プラットフォームに実装されています。 アラートの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](../../compliance/alert-policies.md)」を参照してください。 

> [!IMPORTANT]
> アラートを機能させるには、監査ログ検索をオンにする必要があります。 詳細については、「[Office 365 の監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

このアラートのポリシーは既定のものであり、すべての Office 365 テナントに付属しているため、設定する必要はありません。 これは重大度の高いアラートと見なされ、ユーザーがメールの送信を制限されている場合にアラートが発生するたび、設定された TenantAdmins グループにメールを送信します。 管理者は、[SCC ポータル] > [アラート] > [アラート ポリシー] > [メールの送信が制限されているユーザー]　の下にあるアラートに移動して、このアラートが発生したときに通知されるグループを更新できます。

アラートは次のように編集できます。
- メール通知をオン/オフにする
- 必要な受信者にメールを送信する
- 1 日に受信する通知を制限する

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>PowerShell を使用して制限を確認および削除する
制限付きユーザー向けの PowerShell コマンドは次のとおりです。
- `Get-BlockedSenderAddress`：メールの送信が制限されているユーザーのリストを取得する
- `Remove-BlockedSenderAddress`：ユーザーの制限を削除する

## <a name="for-more-information"></a>関連情報

[侵害された電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)

[メールアラートの送信が制限されているユーザーを把握する](https://docs.microsoft.com/office365/securitycompliance/alert-policies)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)

[セキュリティ/コンプライアンス センターのアラート ポリシー](https://docs.microsoft.com/office365/securitycompliance/alert-policies)
