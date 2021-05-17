---
title: 手順 7 - 元従業員のユーザー アカウントを削除する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 次の手順に従って、元従業員のユーザー アカウントを削除します。
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244236"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="cba6d-103">手順 7 - 元従業員のユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="cba6d-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="cba6d-104">元従業員のすべてのユーザー データにアクセスして保存したら、元従業員のアカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="cba6d-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cba6d-p101">メールの転送を設定した場合や、アカウントを共有メールボックスに変換した場合、アカウントを削除しないでください。いずれの場合も、メール転送および共有メールボックスを固定するには、アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="cba6d-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="cba6d-107">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cba6d-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cba6d-108">削除する従業員の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="cba6d-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="cba6d-109">ユーザーの名前の下で、[ユーザーの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cba6d-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="cba6d-110">このユーザーに必要なオプションを選択し、[ユーザーの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cba6d-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="cba6d-111">既に別のユーザーにこのユーザーの電子メールへのアクセス権を与え、OneDrive場合は、ここでもう一度行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cba6d-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="cba6d-p103">ユーザーを削除するとき、約 30 日間アカウントが無効になります。30 日後に永久に削除されるまではアカウントを復元できます。</span><span class="sxs-lookup"><span data-stu-id="cba6d-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="cba6d-114">組織では Active Directory を使用していますか。</span><span class="sxs-lookup"><span data-stu-id="cba6d-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="cba6d-115">組織がローカルの Active Directory 環境Microsoft 365にユーザー アカウントを同期する場合は、ローカルの Active Directory サービスでそれらのユーザー アカウントを削除して復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba6d-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="cba6d-116">ユーザー アカウントを Office 365 で削除または復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="cba6d-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="cba6d-117">Active Directory でユーザー アカウントを削除および復元する方法については、「ユーザー アカウントの削除 [」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="cba6d-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="cba6d-118">このコマンドレットを使用しているAzure Active Directory [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell コマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba6d-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="cba6d-119">従業員のメール セッションの終了について知っておく必要があること</span><span class="sxs-lookup"><span data-stu-id="cba6d-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="cba6d-120">ここでは、従業員のメールの使用を終了する方法について説明します (Exchange)。</span><span class="sxs-lookup"><span data-stu-id="cba6d-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cba6d-121">**可能な操作**</span><span class="sxs-lookup"><span data-stu-id="cba6d-121">**What you can do**</span></span> <br/> |<span data-ttu-id="cba6d-122">**方法**</span><span class="sxs-lookup"><span data-stu-id="cba6d-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="cba6d-123">セッション (Outlook on the web、Outlook、Exchange Active Sync など) を終了し、新しいセッションを強制的に開く</span><span class="sxs-lookup"><span data-stu-id="cba6d-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="cba6d-124">パスワードを再設定する</span><span class="sxs-lookup"><span data-stu-id="cba6d-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="cba6d-125">(すべてのプロトコルの) セッションを終了し、今後のセッションに対するアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="cba6d-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="cba6d-126">アカウントを無効にする。</span><span class="sxs-lookup"><span data-stu-id="cba6d-126">Disable the account.</span></span> <span data-ttu-id="cba6d-127">たとえば、次の例を実行します (Exchangeまたは PowerShell を使用します)。</span><span class="sxs-lookup"><span data-stu-id="cba6d-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="cba6d-128">特定のプロトコル (ActiveSync など) のセッションを終了する</span><span class="sxs-lookup"><span data-stu-id="cba6d-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="cba6d-129">プロトコルを無効にする。</span><span class="sxs-lookup"><span data-stu-id="cba6d-129">Disable the protocol.</span></span> <span data-ttu-id="cba6d-130">たとえば、次の例を実行します (Exchangeまたは PowerShell を使用します)。</span><span class="sxs-lookup"><span data-stu-id="cba6d-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="cba6d-131">上記の操作は、次の 3 つの場所で実行できます。</span><span class="sxs-lookup"><span data-stu-id="cba6d-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cba6d-132">**セッションを終了する場所**</span><span class="sxs-lookup"><span data-stu-id="cba6d-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="cba6d-133">**所要時間**</span><span class="sxs-lookup"><span data-stu-id="cba6d-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="cba6d-134">Exchange 管理センターまたは PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="cba6d-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="cba6d-135">予想される遅延が 30 分以内</span><span class="sxs-lookup"><span data-stu-id="cba6d-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="cba6d-136">Azure Active Directory 管理センター</span><span class="sxs-lookup"><span data-stu-id="cba6d-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="cba6d-137">予想される遅延が 60 分以内</span><span class="sxs-lookup"><span data-stu-id="cba6d-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="cba6d-138">オンプレミス環境</span><span class="sxs-lookup"><span data-stu-id="cba6d-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="cba6d-139">予想される遅延が 3 時間以上</span><span class="sxs-lookup"><span data-stu-id="cba6d-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="cba6d-140">アカウントの終了に対して最も迅速な応答を取得する方法</span><span class="sxs-lookup"><span data-stu-id="cba6d-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="cba6d-p107">**最も迅速な応答**: Exchange 管理センターを使用 (PowerShell を使用) するか、または Azure Active Directory 管理センターを使用します。オンプレミスの環境では、DirSync を介して変更を同期するのに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cba6d-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="cba6d-p108">**オンプレミスおよび Exchange データ センターにプレゼンスがあるユーザーの場合、迅速な応答**: Azure Active Directory 管理センター/Exchange 管理センターを使用してセッションを終了し、オンプレミスの環境でも変更を加えます。そうしないと、Azure Active Directory 管理センター/Exchange 管理センターでの変更は、DirSync によって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="cba6d-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="cba6d-145">関連記事</span><span class="sxs-lookup"><span data-stu-id="cba6d-145">Related articles</span></span>

[<span data-ttu-id="cba6d-146">ユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="cba6d-146">Restore a user</span></span>](restore-user.md)
