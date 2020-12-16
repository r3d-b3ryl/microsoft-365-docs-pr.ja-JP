---
title: 制限されたユーザー ポータルから、ブロックされたユーザーを削除する
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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Office 365 の制限されたユーザー ポータルからユーザーを削除する方法についての管理者向けの説明です。 アカウントを侵害していると見なされたユーザーは通常、スパム送信者として、制限されたユーザー ポータルに追加されます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bca9366fdb8cacdc58c12757e870c8ead8f1fa7a
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683057"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="7af89-104">Office 365 の制限されたユーザー ポータルから、ブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="7af89-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7af89-105">ユーザーが[サービスの制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパム ポリシー](configure-the-outbound-spam-policy.md)で指定されている送信の制限のいずれかを超えた場合、そのユーザーはメールの送信を制限されますが、メールを受信することはできます。</span><span class="sxs-lookup"><span data-stu-id="7af89-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="7af89-106">そのユーザーは、セキュリティ/コンプライアンス センターの制限されたユーザー ポータルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7af89-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7af89-107">メールを送信しようとすると、メッセージは配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) として返され、エラー コード[ 5.1.8 ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online)と次のテキストが記載されます。</span><span class="sxs-lookup"><span data-stu-id="7af89-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="7af89-108">「有効な送信者として認識されなかったため、メッセージを配信できませんでした。」</span><span class="sxs-lookup"><span data-stu-id="7af89-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="7af89-109">この最も一般的な理由は、メールアドレスがスパムを送信している疑いがあり、メールを送信することを許可されていないことです。</span><span class="sxs-lookup"><span data-stu-id="7af89-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="7af89-110">詳細については、メールアドレスの管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="7af89-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="7af89-111">リモートサーバーが 「550 5.1.8 アクセスが拒否されました。アウトバウンド送信者が正しくありません」を返す</span><span class="sxs-lookup"><span data-stu-id="7af89-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="7af89-112">管理者は、セキュリティ/コンプライアンス センターまたは Exchange Online PowerShell の制限された送信者ポータルからユーザーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="7af89-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7af89-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7af89-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7af89-114"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="7af89-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7af89-115">**制限されたユーザー** のページに直接移動するには <https://protection.office.com/restrictedusers> を使用します。</span><span class="sxs-lookup"><span data-stu-id="7af89-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="7af89-116">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af89-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7af89-117">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="7af89-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7af89-118">制限されたユーザー ポータルからユーザーを削除するには、**組織の管理** または **セキュリティ管理者** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af89-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="7af89-119">制限されたユーザー ポータルに読み取り専用でアクセスするには、**グローバル閲覧者** または **セキュリティ 閲覧者** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af89-119">For read-only access to the Restricted Users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7af89-120">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af89-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="7af89-121">**注**:</span><span class="sxs-lookup"><span data-stu-id="7af89-121">**Notes**:</span></span>

  - <span data-ttu-id="7af89-122">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="7af89-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7af89-123">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af89-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="7af89-124">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="7af89-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="7af89-125">送信メールの制限を超える送信者は、アカウントが侵害されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="7af89-125">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="7af89-126">制限されたユーザー ポータルからユーザーを削除する前に、必要な手順に従ってアカウントの制御を再度行ってください。</span><span class="sxs-lookup"><span data-stu-id="7af89-126">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="7af89-127">詳細については、「[侵害された Office 365 電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af89-127">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="7af89-128">セキュリティ/コンプライアンス センターを使用して、制限されたユーザーの一覧からユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="7af89-128">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="7af89-129">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[制限されたユーザー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7af89-129">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="7af89-130">ブロックを解除するユーザーを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="7af89-130">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="7af89-131">**[アクション]** 列の **[ブロックを解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af89-131">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="7af89-132">送信が制限されているアカウントの詳細がポップアップで表示されます。</span><span class="sxs-lookup"><span data-stu-id="7af89-132">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="7af89-133">アカウントが実際に侵害された場合に備えて、適切な対策を講じるため、推奨事項を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af89-133">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="7af89-134">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af89-134">Click **Next** when done.</span></span>

4. <span data-ttu-id="7af89-135">次の画面には、今後の侵害を防ぐための推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7af89-135">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="7af89-136">\*多要素認証 (MFA) を有効にし、</span><span class="sxs-lookup"><span data-stu-id="7af89-136">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="7af89-137">操作が完了したら、**[ユーザーのブロックを解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af89-137">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="7af89-138">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="7af89-138">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7af89-139">制限が解除されるまで 30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7af89-139">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="7af89-140">制限されたユーザーのアラート設定を確認する</span><span class="sxs-lookup"><span data-stu-id="7af89-140">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="7af89-141">ユーザーがメールの送信をブロックされている場合、**メール送信を制限されているユーザー** という既定のアラート ポリシーにより、管理者に自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="7af89-141">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="7af89-142">その設定を確認し、通知するユーザーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7af89-142">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="7af89-143">アラート ポリシーの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](../../compliance/alert-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af89-143">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7af89-144">アラートを機能させるには、監査ログ検索をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af89-144">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="7af89-145">詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7af89-145">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="7af89-146">セキュリティ/コンプライアンス センターで、**[アラート]** \> **[アラート ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7af89-146">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="7af89-147">**[メール送信を制限されているユーザー]** アラートを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="7af89-147">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="7af89-148">表示されるポップアップで、次の設定を確認または構成します。</span><span class="sxs-lookup"><span data-stu-id="7af89-148">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="7af89-149">**状態**: ![[オンに切り替え]](../../media/scc-toggle-on.png) で、アラートがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7af89-149">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="7af89-150">**メール受信者**: **[編集]** をクリックし、表示される **[受信者の編集]** ポップアップで、次の設定を確認または構成します。</span><span class="sxs-lookup"><span data-stu-id="7af89-150">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="7af89-151">**メール通知の送信**: チェック ボックスが選択済み (**オン**) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7af89-151">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="7af89-152">**メール受信者**: 既定値は **TenantAdmins** (つまり、**グローバル管理者** のメンバー) です。</span><span class="sxs-lookup"><span data-stu-id="7af89-152">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="7af89-153">受信者を追加するには、ボックスの空白の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af89-153">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="7af89-154">受信者の一覧が表示されますので、名前を入力して、フィルター処理で受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="7af89-154">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="7af89-155">名前の横にある![削除アイコン](../../media/scc-remove-icon.png)をクリックすると、既存の受信者をボックスから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="7af89-155">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="7af89-156">**1 日の通知の上限**: 既定値は **制限なし** ですが、1 日あたりの通知数の上限を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="7af89-156">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="7af89-157">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af89-157">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="7af89-158">**[メール送信を制限されているユーザー]** ポップアップの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af89-158">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="7af89-159">Exchange Online PowerShell を使用して、制限されたユーザーの一覧からユーザーを表示および削除する</span><span class="sxs-lookup"><span data-stu-id="7af89-159">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="7af89-160">メールの送信が制限されているユーザーの一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7af89-160">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="7af89-161">特定のユーザーの詳細を表示するには、\<emailaddress\>をユーザーのメール アドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7af89-161">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="7af89-162">構文およびパラメーターの詳細については、「[Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af89-162">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="7af89-163">制限されたユーザーの一覧からユーザーを削除するには、\<emailaddress\> をメール アドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7af89-163">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="7af89-164">構文およびパラメーターの詳細については、「[Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af89-164">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
