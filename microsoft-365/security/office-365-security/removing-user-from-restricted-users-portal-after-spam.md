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
ms.openlocfilehash: 43312ee6eff9b56ac4faf8173666a1ba79b9e067
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726733"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="37796-104">Office 365 の制限されたユーザー ポータルから、ブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="37796-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="37796-105">ユーザーが[サービスの制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパム ポリシー](configure-the-outbound-spam-policy.md)で指定されている送信の制限のいずれかを超えた場合、そのユーザーはメールの送信を制限されますが、メールを受信することはできます。</span><span class="sxs-lookup"><span data-stu-id="37796-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="37796-106">そのユーザーは、セキュリティ/コンプライアンス センターの制限されたユーザー ポータルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="37796-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="37796-107">メールを送信しようとすると、メッセージは配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) として返され、エラー コード[ 5.1.8 ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online)と次のテキストが記載されます。</span><span class="sxs-lookup"><span data-stu-id="37796-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="37796-108">「有効な送信者として認識されなかったため、メッセージを配信できませんでした。」</span><span class="sxs-lookup"><span data-stu-id="37796-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="37796-109">この最も一般的な理由は、メールアドレスがスパムを送信している疑いがあり、メールを送信することを許可されていないことです。</span><span class="sxs-lookup"><span data-stu-id="37796-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="37796-110">詳細については、メールアドレスの管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="37796-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="37796-111">リモートサーバーが 「550 5.1.8 アクセスが拒否されました。アウトバウンド送信者が正しくありません」を返す</span><span class="sxs-lookup"><span data-stu-id="37796-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="37796-112">管理者は、セキュリティ/コンプライアンス センターまたは Exchange Online PowerShell の制限された送信者ポータルからユーザーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="37796-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37796-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="37796-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="37796-114"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="37796-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="37796-115">**制限されたユーザー**のページに直接移動するには <https://protection.office.com/restrictedusers> を使用します。</span><span class="sxs-lookup"><span data-stu-id="37796-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="37796-116">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37796-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="37796-117">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="37796-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="37796-118">制限されたユーザー ポータルからユーザーを削除するには、次の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="37796-118">To remove users from the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="37796-119">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="37796-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="37796-120">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="37796-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="37796-121">制限されたユーザー ポータルに読み取り専用でアクセスするには、次の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="37796-121">For read-only access to the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="37796-122">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="37796-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="37796-123">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="37796-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="37796-124">送信メールの制限を超える送信者は、アカウントが侵害されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="37796-124">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="37796-125">制限されたユーザー ポータルからユーザーを削除する前に、必要な手順に従ってアカウントの制御を再度行ってください。</span><span class="sxs-lookup"><span data-stu-id="37796-125">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="37796-126">詳細については、「[侵害された Office 365 電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37796-126">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="37796-127">セキュリティ/コンプライアンス センターを使用して、制限されたユーザーの一覧からユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="37796-127">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="37796-128">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[制限されたユーザー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="37796-128">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="37796-129">ブロックを解除するユーザーを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="37796-129">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="37796-130">**[アクション]** 列の **[ブロックを解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37796-130">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="37796-131">送信が制限されているアカウントの詳細がポップアップで表示されます。</span><span class="sxs-lookup"><span data-stu-id="37796-131">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="37796-132">アカウントが実際に侵害された場合に備えて、適切な対策を講じるため、推奨事項を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37796-132">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="37796-133">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37796-133">Click **Next** when done.</span></span>

4. <span data-ttu-id="37796-134">次の画面には、今後の侵害を防ぐための推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37796-134">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="37796-135">\*多要素認証 (MFA) を有効にし、</span><span class="sxs-lookup"><span data-stu-id="37796-135">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="37796-136">操作が完了したら、**[ユーザーのブロックを解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37796-136">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="37796-137">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="37796-137">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="37796-138">制限が解除されるまで 30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37796-138">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="37796-139">制限されたユーザーのアラート設定を確認する</span><span class="sxs-lookup"><span data-stu-id="37796-139">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="37796-140">ユーザーがメールの送信をブロックされている場合、**メール送信を制限されているユーザー**という既定のアラート ポリシーにより、管理者に自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="37796-140">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="37796-141">その設定を確認し、通知するユーザーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="37796-141">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="37796-142">アラート ポリシーの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](../../compliance/alert-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37796-142">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37796-143">アラートを機能させるには、監査ログ検索をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37796-143">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="37796-144">詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="37796-144">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="37796-145">セキュリティ/コンプライアンス センターで、**[アラート]** \> **[アラート ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="37796-145">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="37796-146">**[メール送信を制限されているユーザー]** アラートを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="37796-146">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="37796-147">表示されるポップアップで、次の設定を確認または構成します。</span><span class="sxs-lookup"><span data-stu-id="37796-147">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="37796-148">**状態**: ![[オンに切り替え]](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) で、アラートがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="37796-148">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="37796-149">**メール受信者**: **[編集]** をクリックし、表示される **[受信者の編集]** ポップアップで、次の設定を確認または構成します。</span><span class="sxs-lookup"><span data-stu-id="37796-149">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="37796-150">**メール通知の送信**: チェック ボックスが選択済み (**オン**) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="37796-150">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="37796-151">**メール受信者**: 既定値は **TenantAdmins** (つまり、**グローバル管理者**のメンバー) です。</span><span class="sxs-lookup"><span data-stu-id="37796-151">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="37796-152">受信者を追加するには、ボックスの空白の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37796-152">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="37796-153">受信者の一覧が表示されますので、名前を入力して、フィルター処理で受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="37796-153">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="37796-154">名前の横にある![削除アイコン](../../media/scc-remove-icon.png)をクリックすると、既存の受信者をボックスから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="37796-154">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="37796-155">**1 日の通知の上限**: 既定値は**制限なし**ですが、1 日あたりの通知数の上限を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="37796-155">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="37796-156">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37796-156">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="37796-157">**[メール送信を制限されているユーザー]** ポップアップの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37796-157">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="37796-158">Exchange Online PowerShell を使用して、制限されたユーザーの一覧からユーザーを表示および削除する</span><span class="sxs-lookup"><span data-stu-id="37796-158">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="37796-159">メールの送信が制限されているユーザーの一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="37796-159">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="37796-160">特定のユーザーの詳細を表示するには、\<emailaddress\>をユーザーのメール アドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="37796-160">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="37796-161">構文およびパラメーターの詳細については、「[Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37796-161">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="37796-162">制限されたユーザーの一覧からユーザーを削除するには、\<emailaddress\> をメール アドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="37796-162">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="37796-163">構文およびパラメーターの詳細については、「[Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37796-163">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
