---
title: Outlook on the web で「メールボックスが見つかりませんでした」というエラーが表示される場合
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 「**のメールボックス見つかりませんでした**」 というエラーは、Outlook on the web への接続に使用したアカウントに Exchange Online のライセンスが存在しないという意味です。
ms.openlocfilehash: 54aa196b0b324054d6220d4437a672a3db2a45ec
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338567"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="568c0-103">Outlook on the web で「メールボックスが見つかりませんでした」というエラーが表示されますか?</span><span class="sxs-lookup"><span data-stu-id="568c0-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="568c0-104">Outlook on the web を使用しているときに、「**メールボックスが見つかりませんでした**」というエラーが表示された場合は、Outlook on the web への接続時に使用したアカウントに Exchange Online ライセンスが付与されていないため、そのアカウントにメールボックスが関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="568c0-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> 

## <a name="assign-a-license-to-your-account"></a><span data-ttu-id="568c0-105">アカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="568c0-105">Assign a license to your account</span></span>

<span data-ttu-id="568c0-106">管理者は、次の手順に従って、アカウントにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="568c0-106">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="568c0-107">[Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home#/homepage)を開き、[**ユーザー**] セクションの [**アクティブ ユーザー**] に移動して、エラーが表示されているユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="568c0-107">Open the  [Microsoft 365 admin center](https://admin.microsoft.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
1. <span data-ttu-id="568c0-108">開いたユーザー ページで、[**ライセンスとアプリ**] セクションに移動し、該当する [**場所**] の値を選択し、Exchange Online を含むライセンスを割り当てます (ライセンスを展開して、その詳細を表示します)。</span><span class="sxs-lookup"><span data-stu-id="568c0-108">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> 
1. <span data-ttu-id="568c0-109">完了したら、[**変更の保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="568c0-109">When you're finished, click  **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="568c0-110">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="568c0-110">Related content</span></span>

<span data-ttu-id="568c0-111">[ユーザーに別のメール エイリアスを追加する](../email/add-another-email-alias-for-a-user.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="568c0-111">[Add another email alias for a user](../email/add-another-email-alias-for-a-user.md) (article)\</span></span>
<span data-ttu-id="568c0-112">[Microsoft 365 でメールの転送を構成する](../email/configure-email-forwarding.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="568c0-112">[Configure email forwarding in Microsoft 365](../email/configure-email-forwarding.md) (article)\</span></span>
<span data-ttu-id="568c0-113">[共有メールボックス GWT を作成する](../email/create-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="568c0-113">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>