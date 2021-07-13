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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: このソリューションの手順に従って、組織のデータを保護Microsoft 365元の従業員を削除します。
ms.openlocfilehash: dcc206cc0b088749c3936dcf1c548cc83b6fa595
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394293"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="49274-103">概要: 元従業員とセキュリティで保護されたデータを削除する</span><span class="sxs-lookup"><span data-stu-id="49274-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="49274-104">よく聞く質問は、「従業員が組織を離れるときにデータを保護し、アクセスを保護するために何をすべきですか?</span><span class="sxs-lookup"><span data-stu-id="49274-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="49274-105">この記事シリーズでは、Microsoft 365 へのアクセスをブロックする方法、データをセキュリティで保護するために実行する必要がある手順、および他の従業員がデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49274-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

:::image type="content" source="../../media/delete-user-overview.png" alt-text="スクリーンショット: 元従業員を削除するための概要手順":::

## <a name="before-you-begin"></a><span data-ttu-id="49274-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="49274-107">Before you begin</span></span>

<span data-ttu-id="49274-108">このソリューションの手順を完了するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="49274-108">You need to be a global administrator to complete the steps in this solution.</span></span>

## <a name="solution-remove-a-former-employee"></a><span data-ttu-id="49274-109">解決策: 元従業員を削除する</span><span class="sxs-lookup"><span data-stu-id="49274-109">Solution: Remove a former employee</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49274-110">このソリューションの手順に番号を付け、正確な順序でソリューションを完了する必要は一切ないが、この方法で手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49274-110">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

:::image type="content" source="../../media/delete-user-account.png" alt-text="スクリーンショット: 元従業員を組織から削除する手順":::

<br>

****

|<span data-ttu-id="49274-112">手順</span><span class="sxs-lookup"><span data-stu-id="49274-112">Step</span></span>|<span data-ttu-id="49274-113">理由</span><span class="sxs-lookup"><span data-stu-id="49274-113">Why do this</span></span>|
|---|---|
|[<span data-ttu-id="49274-114">手順 1 - 元従業員のログインを防止し、サービスへのアクセスMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="49274-114">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md)|<span data-ttu-id="49274-115">これにより、元従業員がユーザーにログインMicrosoft 365し、ユーザーがサービスにアクセスMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="49274-115">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span>|
|[<span data-ttu-id="49274-116">手順 2 - 元従業員のメールボックスの内容を保存する</span><span class="sxs-lookup"><span data-stu-id="49274-116">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md)|<span data-ttu-id="49274-117">これは、従業員の仕事を引き継ぐ人や訴訟がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="49274-117">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span>|
|[<span data-ttu-id="49274-118">手順 3 - 元従業員のメールを別の従業員に転送するか、共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="49274-118">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md)|<span data-ttu-id="49274-p102">この操作を行うと、元従業員のメール アドレスはアクティブなままとなります。顧客やパートナーが元従業員のアドレスにメールを引き続き送信する場合は、この手順を行うと、仕事を引き継ぐユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="49274-p102">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span>|
|[<span data-ttu-id="49274-121">手順 4 - 別の従業員にデータとOneDriveアクセスOutlookする</span><span class="sxs-lookup"><span data-stu-id="49274-121">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-4.md)|<span data-ttu-id="49274-122">ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="49274-122">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <p> <span data-ttu-id="49274-123">アカウントを削除する前に、ユーザーのアカウントにアクセス権を与OneDrive、Outlookユーザーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49274-123">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="49274-124">従業員のアカウントを削除すると、従業員のアカウントOneDrive Outlook **30** 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="49274-124">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="49274-125">ただし、その 30 日間は、ユーザーのアカウントを復元し、そのユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="49274-125">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="49274-126">ユーザーのアカウントを復元した場合、OneDriveおよびOutlookは 30 日後でもユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="49274-126">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span>|
|[<span data-ttu-id="49274-127">手順 5 - 元従業員のモバイル デバイスをワイプしてブロックする</span><span class="sxs-lookup"><span data-stu-id="49274-127">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-5.md)|<span data-ttu-id="49274-128">携帯電話またはタブレットからビジネス データを削除します。</span><span class="sxs-lookup"><span data-stu-id="49274-128">Removes your business data from the phone or tablet.</span></span>|
|[<span data-ttu-id="49274-129">手順 6 - 元従業員からMicrosoft 365ライセンスを削除および削除する</span><span class="sxs-lookup"><span data-stu-id="49274-129">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-6.md)|<span data-ttu-id="49274-p104">ライセンスを削除すると、別のユーザーに割り当てることができます。または、他のユーザーを採用するまで支払うことがないように、ライセンスを削除することもできます。  </span><span class="sxs-lookup"><span data-stu-id="49274-p104">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><p> <span data-ttu-id="49274-p105">ライセンスを削除すると、ユーザーの古いメール、連絡先、および予定表は **30 日間** 保持され、その後、完全に削除されます。 ライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  </span><span class="sxs-lookup"><span data-stu-id="49274-p105">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span>|
|[<span data-ttu-id="49274-134">手順 7 - 元従業員のユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="49274-134">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md)|<span data-ttu-id="49274-135">これにより、管理センターからアカウントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="49274-135">This removes the account from your admin center.</span></span> <span data-ttu-id="49274-136">これできれいになります。</span><span class="sxs-lookup"><span data-stu-id="49274-136">Keeps things clean.</span></span>|
|

## <a name="related-content"></a><span data-ttu-id="49274-137">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="49274-137">Related content</span></span>

<span data-ttu-id="49274-138">[ユーザーの復元](restore-user.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="49274-138">[Restore a user](restore-user.md) (article)</span></span>\
<span data-ttu-id="49274-139">[Microsoft 365 に新しい従業員を追加する](add-new-employee.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="49274-139">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="49274-140">[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="49274-140">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="49274-141">[ユーザーからのライセンスの割り当てを解除する](../manage/remove-licenses-from-users.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="49274-141">[Unassign licenses from users](../manage/remove-licenses-from-users.md) (article)</span></span>
