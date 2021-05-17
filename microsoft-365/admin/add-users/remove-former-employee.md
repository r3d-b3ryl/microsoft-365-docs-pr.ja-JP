---
title: 元従業員の削除 - 概要
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
description: このソリューションの手順に従って、組織のデータを保護Microsoft 365元の従業員を削除します。
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241738"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="ce63c-103">概要: 元従業員とセキュリティで保護されたデータを削除する</span><span class="sxs-lookup"><span data-stu-id="ce63c-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="ce63c-104">よく聞く質問は、「従業員が組織を離れるときにデータを保護し、アクセスを保護するために何をすべきですか?</span><span class="sxs-lookup"><span data-stu-id="ce63c-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="ce63c-105">この記事シリーズでは、Microsoft 365 へのアクセスをブロックする方法、データをセキュリティで保護するために実行する必要がある手順、および他の従業員がデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce63c-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="ce63c-106">従業員の削除に関する短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce63c-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="ce63c-107">このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../../business-video/index.yml)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce63c-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="ce63c-108">従業員がログインを防止するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="ce63c-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="ce63c-109">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ce63c-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="ce63c-110">ユーザーの名前の横にあるボックスを選択し、[パスワードのリセット] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce63c-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="ce63c-111">新しいパスワードを入力し、[リセット] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce63c-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="ce63c-112">(送信しない。</span><span class="sxs-lookup"><span data-stu-id="ce63c-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="ce63c-113">ユーザーの名前を選択してプロパティ ウィンドウに移動し、[アカウント]タブで [サインアウトの開始 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce63c-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="ce63c-114">サインアウトを開始するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce63c-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="ce63c-115">1 時間以内に、または現在のページを離Microsoft 365後に、もう一度サインインするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce63c-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="ce63c-116">アクセス トークンは 1 時間有効なので、タイムラインは、そのトークンに残されている時間と、現在の Web ページから移動するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ce63c-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce63c-117">このソリューションの手順に番号を付け、正確な順序でソリューションを完了する必要は一切ないが、この方法で手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ce63c-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce63c-118">はじめに</span><span class="sxs-lookup"><span data-stu-id="ce63c-118">Before you begin</span></span>

<span data-ttu-id="ce63c-119">このソリューションの手順を完了するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce63c-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ce63c-120">**手順**</span><span class="sxs-lookup"><span data-stu-id="ce63c-120">**Step**</span></span> <br/> |<span data-ttu-id="ce63c-121">**理由**</span><span class="sxs-lookup"><span data-stu-id="ce63c-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="ce63c-122">手順 1 - 元従業員のログインを防止し、サービスへのアクセスMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="ce63c-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="ce63c-123">これにより、元従業員がユーザーにログインMicrosoft 365し、ユーザーがサービスにアクセスMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="ce63c-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="ce63c-124">手順 2 - 元従業員のメールボックスの内容を保存する</span><span class="sxs-lookup"><span data-stu-id="ce63c-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="ce63c-125">これは、従業員の仕事を引き継ぐ人や訴訟がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ce63c-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="ce63c-126">手順 3 - 元従業員のメールを別の従業員に転送するか、共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="ce63c-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="ce63c-p104">この操作を行うと、元従業員のメール アドレスはアクティブなままとなります。顧客やパートナーが元従業員のアドレスにメールを引き続き送信する場合は、この手順を行うと、仕事を引き継ぐユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="ce63c-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="ce63c-129">手順 4 - 別の従業員にデータとOneDriveアクセスOutlookする</span><span class="sxs-lookup"><span data-stu-id="ce63c-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="ce63c-130">ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ce63c-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="ce63c-131">アカウントを削除する前に、ユーザーのアカウントにアクセス権を与OneDrive、Outlookユーザーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce63c-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="ce63c-132">従業員のアカウントを削除すると、従業員のアカウントOneDrive Outlook **30** 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="ce63c-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="ce63c-133">ただし、その 30 日間は、ユーザーのアカウントを復元し、そのユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ce63c-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="ce63c-134">ユーザーのアカウントを復元した場合、OneDriveおよびOutlookは 30 日後でもユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ce63c-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="ce63c-135">手順 5 - 元従業員のモバイル デバイスをワイプしてブロックする</span><span class="sxs-lookup"><span data-stu-id="ce63c-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="ce63c-136">携帯電話またはタブレットからビジネス データを削除します。</span><span class="sxs-lookup"><span data-stu-id="ce63c-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="ce63c-137">手順 6 - 元従業員からMicrosoft 365ライセンスを削除および削除する</span><span class="sxs-lookup"><span data-stu-id="ce63c-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="ce63c-p106">ライセンスを削除すると、別のユーザーに割り当てることができます。または、他のユーザーを採用するまで支払うことがないように、ライセンスを削除することもできます。  </span><span class="sxs-lookup"><span data-stu-id="ce63c-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="ce63c-p107">ライセンスを削除すると、ユーザーの古いメール、連絡先、および予定表は **30 日間** 保持され、その後、完全に削除されます。 ライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  </span><span class="sxs-lookup"><span data-stu-id="ce63c-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="ce63c-142">手順 7 - 元従業員のユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="ce63c-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="ce63c-143">これにより、管理センターからアカウントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ce63c-143">This removes the account from your admin center.</span></span> <span data-ttu-id="ce63c-144">これできれいになります。</span><span class="sxs-lookup"><span data-stu-id="ce63c-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="ce63c-145">関連記事</span><span class="sxs-lookup"><span data-stu-id="ce63c-145">Related articles</span></span>

[<span data-ttu-id="ce63c-146">ユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="ce63c-146">Restore a user</span></span>](restore-user.md)
