---
title: Web 上のメールボックスでメールボックスが見つからないOutlook取得する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: ライセンスのないユーザーにライセンスを追加して、メールボックスが見つからないエラーを修正する方法について説明します。
ms.openlocfilehash: e5cdb7b48f3634d51dfe1862d07d58a23e125135
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454327"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="d0876-103">Outlook on the web で「メールボックスが見つかりませんでした」というエラーが表示される場合</span><span class="sxs-lookup"><span data-stu-id="d0876-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="d0876-104">web 上で Outlook を使用している場合、エラーとしてメールボックスが見つからない場合は、web 上の Outlook に接続するために使用したアカウントに Exchange Online ライセンスが存在し、そのため、アカウントに関連付けられたメールボックスはありません。</span><span class="sxs-lookup"><span data-stu-id="d0876-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> <span data-ttu-id="d0876-105">管理者は、次の手順に従ってアカウントにライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="d0876-105">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="d0876-106">管理センター [Microsoft 365開き](https://portal.office.com/adminportal/home#/homepage)、[ユーザー]セクションの [アクティブ なユーザー] に移動し、エラーが表示されているユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0876-106">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
2. <span data-ttu-id="d0876-107">開いたユーザー ページで、[ライセンスとアプリ] セクションに移動し、適切な場所の値を選択し、Exchange Online を含むライセンスを割り当てる (ライセンスを展開して詳細を確認します)。</span><span class="sxs-lookup"><span data-stu-id="d0876-107">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> <span data-ttu-id="d0876-108">完了したら、[変更の保存]  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d0876-108">When you're finished, click  **Save changes**.</span></span>
