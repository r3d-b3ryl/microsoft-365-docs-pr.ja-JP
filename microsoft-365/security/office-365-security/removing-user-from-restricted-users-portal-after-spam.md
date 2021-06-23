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
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082854"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a><span data-ttu-id="33df5-104">Microsoft 365 の制限されたユーザー ポータルから、ブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="33df5-104">Remove blocked users from the Restricted users portal in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33df5-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="33df5-105">**Applies to**</span></span>
- [<span data-ttu-id="33df5-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="33df5-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="33df5-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="33df5-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="33df5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33df5-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="33df5-109">ユーザーが[サービスの制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパム ポリシー](configure-the-outbound-spam-policy.md)で指定されている送信の制限のいずれかを超えた場合、そのユーザーはメールの送信を制限されますが、メールを受信することはできます。</span><span class="sxs-lookup"><span data-stu-id="33df5-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="33df5-110">Microsoft 365 Defender ポータルの **制限されたユーザー** ページにユーザーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="33df5-110">The user is added to the **Restricted users** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="33df5-111">メールを送信しようとすると、メッセージは配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) として返され、エラー コード[ 5.1.8 ](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online)と次のテキストが記載されます。</span><span class="sxs-lookup"><span data-stu-id="33df5-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="33df5-112">「有効な送信者として認識されなかったため、メッセージを配信できませんでした。」</span><span class="sxs-lookup"><span data-stu-id="33df5-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="33df5-113">この最も一般的な理由は、メールアドレスがスパムを送信している疑いがあり、メールを送信することを許可されていないことです。</span><span class="sxs-lookup"><span data-stu-id="33df5-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="33df5-114">詳細については、メールアドレスの管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="33df5-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="33df5-115">リモートサーバーが 「550 5.1.8 アクセスが拒否されました。アウトバウンド送信者が正しくありません」を返す</span><span class="sxs-lookup"><span data-stu-id="33df5-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="33df5-116">管理者は、Microsoft 365 Defender または Exchange Online PowerShell の制限されたユーザー ページからユーザーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="33df5-116">Admins can remove users from the Restricted users page in the Microsoft 365 Defender or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33df5-117">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="33df5-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33df5-118"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="33df5-118">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="33df5-119">**制限されたユーザー** のページに直接移動するには <https://security.microsoft.com/restrictedusers> を使用します。</span><span class="sxs-lookup"><span data-stu-id="33df5-119">Too go directly to the **Restricted users** page, use <https://security.microsoft.com/restrictedusers>.</span></span>

- <span data-ttu-id="33df5-120">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33df5-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="33df5-121">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="33df5-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="33df5-122">制限されたユーザー ポータルからユーザーを削除するには、**組織の管理** または **セキュリティ管理者** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="33df5-122">To remove users from the Restricted users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="33df5-123">制限されたユーザー ポータルに読み取り専用でアクセスするには、**グローバル閲覧者** または **セキュリティ 閲覧者** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="33df5-123">For read-only access to the Restricted users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="33df5-124">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33df5-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="33df5-125">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="33df5-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="33df5-126">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33df5-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="33df5-127">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="33df5-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="33df5-128">送信メールの制限を超える送信者は、アカウントが侵害されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="33df5-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="33df5-129">制限されたユーザー ポータルからユーザーを削除する前に、必要な手順に従ってアカウントの制御を再度行ってください。</span><span class="sxs-lookup"><span data-stu-id="33df5-129">Before you remove the user from the Restricted users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="33df5-130">詳細については、「[侵害された Office 365 電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33df5-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="33df5-131">Microsoft 365 Defender ポータルを使用して、制限されたユーザーの一覧からユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="33df5-131">Use the Microsoft 365 Defender portal to remove a user from the Restricted users list</span></span>

1. <span data-ttu-id="33df5-132">Microsoft 365 Defender ポータルで、**[メールと共同作業]**  >  **[レビュー]**  >  **[制限されたユーザー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="33df5-132">In the Microsoft 365 Defender portal, go to **Email & collaboration** > **Review** > **Restricted users**.</span></span>

2. <span data-ttu-id="33df5-133">**[制限されたユーザー]** ページで、ブロックを解除したいユーザーをクリックして検索し、選択します。</span><span class="sxs-lookup"><span data-stu-id="33df5-133">On the **Restricted users** page, find and select the user that you want to unblock by clicking on the user.</span></span>

3. <span data-ttu-id="33df5-134">表示された **[ブロックを解除]** アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="33df5-134">Click the **Unblock** action that appears.</span></span>

4. <span data-ttu-id="33df5-135">表示される **[ブロックを解除したユーザー]** ポップアップで、制限されたアカウントの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="33df5-135">In the **Unblock user** flyout that appears, read the details about the restricted account.</span></span> <span data-ttu-id="33df5-136">アカウントが侵害された場合に備えて、適切な対策を講じるため、推奨事項を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33df5-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is compromised.</span></span>

   <span data-ttu-id="33df5-137">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33df5-137">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="33df5-138">次の画面には、今後の侵害を防ぐための推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="33df5-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="33df5-139">\*多要素認証 (MFA) を有効にし、パスワードをリセットすることは良い防御方法です。</span><span class="sxs-lookup"><span data-stu-id="33df5-139">Enabling multi-factor authentication (MFA) and resetting the password are a good defense.</span></span>

   <span data-ttu-id="33df5-140">完了したら、**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33df5-140">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="33df5-141">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="33df5-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33df5-142">ユーザーからすべての制限を削除するには、最大で 24 時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33df5-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="33df5-143">制限されたユーザーのアラート設定を確認する</span><span class="sxs-lookup"><span data-stu-id="33df5-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="33df5-144">ユーザーがメールの送信をブロックされている場合、**メール送信を制限されているユーザー** という既定のアラート ポリシーにより、管理者に自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="33df5-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="33df5-145">その設定を確認し、通知するユーザーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="33df5-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="33df5-146">アラート ポリシーの詳細については、「[Alert policies in Microsoft 365 (Microsoft 365 でのアラート ポリシー)](../../compliance/alert-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33df5-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33df5-147">アラートを機能させるには、監査ログ検索をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33df5-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="33df5-148">詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="33df5-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="33df5-149">Microsoft 365 Defender ポータルで、**[メールと共同作業]** \> **[ポリシーとルール]** \> **[通知ポリシー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="33df5-149">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="33df5-150">**[通知ポリシー]** ページで、「**メール送信を制限されたユーザー**」という名前の通知を見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="33df5-150">On the **Alert policy** page, find and select the alert named **User restricted from sending email**.</span></span> <span data-ttu-id="33df5-151">ポリシーを名前で並べ替えたり、**[検索ボックス]** を使用してポリシーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="33df5-151">You can sort the policies by name, or use the **Search box** to find the policy.</span></span>

3. <span data-ttu-id="33df5-152">表示される **[ユーザーに対してメールの送信が制限されました]** ポップアップで、次の設定を確認または構成します。</span><span class="sxs-lookup"><span data-stu-id="33df5-152">In the **User restricted from sending email** flyout that appears, verify or configure the following settings:</span></span>
   - <span data-ttu-id="33df5-153">**状態**: ![[オンに切り替え]](../../media/scc-toggle-on.png) で、アラートがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33df5-153">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="33df5-154">**メール受信者**: **[編集]** をクリックし、表示される **[受信者の編集]** ポップアップで、次の設定を確認または構成します。</span><span class="sxs-lookup"><span data-stu-id="33df5-154">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>
     - <span data-ttu-id="33df5-155">**メール通知の送信**: これが選択済み (**オン**) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33df5-155">**Send email notifications**: Verify this is selected (**On**).</span></span>
     - <span data-ttu-id="33df5-156">**メール受信者**: 既定値は **TenantAdmins** (つまり、**グローバル管理者** のメンバー) です。</span><span class="sxs-lookup"><span data-stu-id="33df5-156">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="33df5-157">受信者を追加するには、ボックスの空白の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33df5-157">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="33df5-158">受信者の一覧が表示されますので、名前を入力して、フィルター処理で受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="33df5-158">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="33df5-159">名前の横にある![削除アイコン](../../media/m365-cc-sc-remove-selection-icon.png)をクリックすると、既存の受信者をボックスから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="33df5-159">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to their name.</span></span>
     - <span data-ttu-id="33df5-160">**1 日の通知の上限**: 既定値は **制限なし** ですが、1 日あたりの通知数の上限を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="33df5-160">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="33df5-161">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33df5-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="33df5-162">**[メール送信を制限されているユーザー]** ポップアップの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33df5-162">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="33df5-163">Exchange Online PowerShell を使用して、制限されたユーザーの一覧からユーザーを表示および削除する</span><span class="sxs-lookup"><span data-stu-id="33df5-163">Use Exchange Online PowerShell to view and remove users from the Restricted users list</span></span>

<span data-ttu-id="33df5-164">メールの送信が制限されているユーザーの一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33df5-164">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="33df5-165">特定のユーザーの詳細を表示するには、\<emailaddress\>をユーザーのメール アドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33df5-165">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="33df5-166">構文およびパラメーターの詳細については、「[Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33df5-166">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="33df5-167">制限されたユーザーの一覧からユーザーを削除するには、\<emailaddress\> をメール アドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33df5-167">To remove a user from the Restricted users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="33df5-168">構文およびパラメーターの詳細については、「[Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33df5-168">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
