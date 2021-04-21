---
title: メールの自動転送を停止する
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 電子メールの自動転送を停止する方法について学習します。
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903684"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="568b8-103">電子メールの自動転送を停止する</span><span class="sxs-lookup"><span data-stu-id="568b8-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="568b8-104">ハッカーがユーザーのメールボックスにアクセスすると、ユーザーの電子メールを外部アドレスに自動転送し、専有情報を盗む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="568b8-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="568b8-105">これを停止するには、メール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="568b8-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="568b8-106">お試しください!</span><span class="sxs-lookup"><span data-stu-id="568b8-106">Try it!</span></span>

1. <span data-ttu-id="568b8-107">Microsoft 365 管理センターで **、[Exchange]** **[メール** フロー]を選択し、[ルール] タブでプラス記号を選択し、[新しいルールの作成]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="568b8-108">[その **他のオプション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-108">Select **More options**.</span></span> <span data-ttu-id="568b8-109">新しいルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="568b8-109">Name your new rule.</span></span>
1. <span data-ttu-id="568b8-110">次に、ドロップダウンを開いて、送信者を選択し、外部内部である場合にこのルール **を適用します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="568b8-111">[組織内 **] を選択し\*\*\*\*、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="568b8-112">[ **条件の追加]** を選択し、ドロップダウンを開き、[メッセージのプロパティ] を **選択して**、メッセージ **の種類を指定します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="568b8-113">[メッセージの **種類の選択] ドロップダウン** を開き、[**自動転送] を選択し\*\*\*\*、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="568b8-114">[次の **操作を行う** ] ドロップダウンを開き、[メッセージをブロックする] **を選択し**、メッセージを拒否 **して説明を含める**。</span><span class="sxs-lookup"><span data-stu-id="568b8-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="568b8-115">説明のメッセージ テキストを入力し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="568b8-116">一番下までスクロールし、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="568b8-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="568b8-117">ルールが作成され、ハッカーはメッセージを自動転送できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="568b8-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="568b8-118">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="568b8-118">Related content</span></span>

<span data-ttu-id="568b8-119">[ユーザーに](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) 別のメール エイリアスを追加する (記事) [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) でメール転送を構成する (記事) ビジネス管理者向け [Office 365](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) として電子メール配信の問題を検索して修正する (記事)</span><span class="sxs-lookup"><span data-stu-id="568b8-119">[Add another email alias for a user](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) (article) [Configure email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>