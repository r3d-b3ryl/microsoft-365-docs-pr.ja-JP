---
title: 手順 3 - 元従業員のメールを別の従業員に転送するか、共有メールボックスに変換する
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
description: 次の手順に従って、元従業員のメールを別の従業員に転送するか、共有メールボックスに変換します。
ms.openlocfilehash: 5ab66cf9d71a597a7f33c9a5e3a180738592faca
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244246"
---
# <a name="step-3---forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a><span data-ttu-id="16f0c-103">手順 3 - 元従業員のメールを別の従業員に転送するか、共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="16f0c-103">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>

<span data-ttu-id="16f0c-104">この手順では、元従業員の電子メール アドレスを別の従業員に割り当てるか、ユーザーのメールボックスを共有メールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="16f0c-104">In this step, you assign the former employee's email address to another employee, or convert the user's mailbox to a shared mailbox.</span></span>

## <a name="convert-former-employees-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="16f0c-105">元従業員のメールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="16f0c-105">Convert former employee's mailbox to a shared mailbox</span></span>

<span data-ttu-id="16f0c-106">ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。</span><span class="sxs-lookup"><span data-stu-id="16f0c-106">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="16f0c-107">現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。</span><span class="sxs-lookup"><span data-stu-id="16f0c-107">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="16f0c-108">必要に合って、後日、共有メールボックスをユーザー (プライベート) メールボックスに変換できます。</span><span class="sxs-lookup"><span data-stu-id="16f0c-108">You can convert a shared mailbox back to a user (private) mailbox at a later date if you want.</span></span>

- <span data-ttu-id="16f0c-p102">共有メールボックスを作成すると、コストを低く抑えることができます。これは、 **メールボックスのサイズが 50 GB より小さい限り** 、ライセンスの料金を支払う必要がないからです。50 GB を超えると、メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16f0c-p102">Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it.</span></span>
- <span data-ttu-id="16f0c-p103">メールボックスを共有メールボックスに変換すると、以前のすべてのメールを入手できるようになります。この処理を行うと、占有する領域が大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16f0c-p103">If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.</span></span>
- <span data-ttu-id="16f0c-113">メール転送を設定した場合 *、元従業員* に送信された新しいメールだけが現在の従業員に送信されます。</span><span class="sxs-lookup"><span data-stu-id="16f0c-113">If you set up email forwarding, only *new* emails sent to the former employee will now be sent to the current employee.</span></span>

<span data-ttu-id="16f0c-114">ユーザーのメールボックスを共有メールボックスに変換する方法については、 [次の手順を実行します](../email/convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="16f0c-114">Follow these steps on how to [convert the user's mailbox to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md).</span></span>

## <a name="forward-a-former-employees-email-to-another-employee"></a><span data-ttu-id="16f0c-115">元従業員のメールを別の従業員に転送する</span><span class="sxs-lookup"><span data-stu-id="16f0c-115">Forward a former employee's email to another employee</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="16f0c-116">メール転送または共有メールボックスを設定する場合は、最後に元従業員のアカウントを削除しない。</span><span class="sxs-lookup"><span data-stu-id="16f0c-116">If you're setting up email forwarding or a shared mailbox, at the end, don't delete the former employee's account.</span></span> <span data-ttu-id="16f0c-117">メール転送や共有メールボックスを固定するには、アカウントを残しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="16f0c-117">The account needs to be there to anchor the email forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="16f0c-118">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="16f0c-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="16f0c-119">ブロックする従業員の名前を選択し、[メール] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="16f0c-119">Select the name of the employee that you want to block, and then select the **Mail** tab.</span></span>
3. <span data-ttu-id="16f0c-120">[メール **転送] で**、[メール転送 **の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="16f0c-120">Under **Email Forwarding**, select **Manage email forwarding**.</span></span>
4. <span data-ttu-id="16f0c-121">[ **このメールボックスに送信されたすべてのメールを転送する** ] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="16f0c-121">Turn on **Forward all email sent to this mailbox**.</span></span> <span data-ttu-id="16f0c-122">[転送 **先住所]** ボックスに、メールを取得する現在の従業員のメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="16f0c-122">In the **Forwarding address** box, type the email address of the current employee who's going to get the email.</span></span>
5. <span data-ttu-id="16f0c-123">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="16f0c-123">Select **Save**.</span></span>
6. <span data-ttu-id="16f0c-124">元従業員のアカウントを削除しないよう注意してください。</span><span class="sxs-lookup"><span data-stu-id="16f0c-124">Remember, don't delete the former employee's account.</span></span>
