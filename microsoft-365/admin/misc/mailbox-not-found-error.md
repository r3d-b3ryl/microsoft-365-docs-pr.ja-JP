---
title: Outlook on the web でメールボックスが見つからないというエラーを取得する
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
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: ライセンスのないユーザーにライセンスを追加して、メールボックスが見つからないというエラーを修正する方法について説明します。
ms.openlocfilehash: bf8ff57704b97c8ef278938675113f5de11849de
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804870"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="8a1e8-103">Outlook on the web で「メールボックスが見つかりませんでした」というエラーが表示される場合</span><span class="sxs-lookup"><span data-stu-id="8a1e8-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="8a1e8-104">Web 上の Outlook を使用していて、  **メールボックスがエラーのために見つから**  ない場合、web 上の outlook への接続に使用したアカウントには Exchange Online ライセンスがないため、アカウントに関連付けられているメールボックスはありません。</span><span class="sxs-lookup"><span data-stu-id="8a1e8-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> <span data-ttu-id="8a1e8-105">管理者は、次の手順に従って、アカウントにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8a1e8-105">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="8a1e8-106">[Microsoft 365 管理センター](https://portal.office.com/adminportal/home#/homepage)を開き、[ **ユーザー** ] セクションの下にある [ **アクティブなユーザー** ] に移動して、エラーを表示しているユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a1e8-106">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
2. <span data-ttu-id="8a1e8-107">開いたユーザーページで、[  **ライセンスとアプリ**  ] セクションに移動し、適切な  **場所**  の値を選択して、Exchange Online を含むライセンスを割り当てます (ライセンスを展開して詳細を表示します)。</span><span class="sxs-lookup"><span data-stu-id="8a1e8-107">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> <span data-ttu-id="8a1e8-108">完了したら、[  **変更の保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1e8-108">When you're finished, click  **Save changes** .</span></span>
