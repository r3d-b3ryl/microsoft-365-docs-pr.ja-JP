---
title: Teams、safelinks、安全なリンク、悪意のあるリンクのブロック、office 365 atp、Teams の安全なリンク、ユーザーによる不正なリンクのクリックを阻止する悪意のあるリンク
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: クリックしたときに Teams が安全なリンクにアクセスできるようになります。 1対1のチャット、グループ間、またはチャネル内のチャットを使用しているかどうか、および Office 365 ATP へのサブスクリプションがある場合は、このセーフティ機能を有効にして使用することができます。
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198753"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="6bd5f-104">Teams の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="6bd5f-104">Safe Links in Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="6bd5f-105">この機能は、2020年2月28日の Microsoft Teams テクノロジ導入プログラム (タップ) にあるお客様向けの **パブリックプレビュー** です。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="6bd5f-106">このメモは、Teams の安全なリンクがより幅広く利用できる場合に記事から削除されます。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="6bd5f-107">Microsoft Teams は、Microsoft のクラウドベースのアプリケーションである仕事を管理するために、既に安全な添付ファイル (Office 365) を使用していますが、これでクリック時に安全なリンクにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="6bd5f-108">Office 365 ATP へのサブスクリプションがある場合、チャット、グループチャット、チャネル、またはタブを使用しているかどうかにかかわらず、この安全手段を有効にして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="6bd5f-109">ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="6bd5f-110">次に、動作のしくみを示します。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-110">Here's how it works:</span></span>

1. <span data-ttu-id="6bd5f-111">Teams アプリケーションを起動すると、Microsoft 365 は、ユーザーが Office 365 ATP を使用している組織に所属しており、ユーザーが Microsoft Teams の保護が有効になっているアクティブな安全リンクポリシーの一部であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="6bd5f-112">上記の条件に該当する場合、Url は、チャット、グループチャット、チャネル、およびそのユーザーのタブでクリックしたときに検証されます。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

## <a name="what-will-users-experience"></a><span data-ttu-id="6bd5f-113">ユーザーにはどのような状況がありますか?</span><span class="sxs-lookup"><span data-stu-id="6bd5f-113">What will users experience?</span></span>

<span data-ttu-id="6bd5f-114">保護されたすべてのユーザーには、次のような危険な Url があります。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-114">All protected users will have this experience with hazardous URLs:</span></span>

- <span data-ttu-id="6bd5f-115">リンクが Teams 会話、グループチャット、またはチャネルからクリックされた場合は、既定のブラウザーでページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="6bd5f-116">固定されたタブからリンクがクリックされた場合は、そのページがそのタブ内の Teams GUI に表示され、セキュリティ上の理由から、ブラウザーで開くオプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="6bd5f-117">このユーザーは、URL のサイトへの進行をブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="6bd5f-118">リンクを送信したユーザーが Office 365 ATP によって保護されていない場合は、自分のコンピューターで URL をクリックして、問題のサイトを解決することができます。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="6bd5f-119">これにより、管理者は、保護されたユーザーがどのようなものであるかを認識できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Teams ページの安全なリンクは、悪意のあるリンクを報告し、ページへの送信をブロックします。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="6bd5f-121">Teams で、このページの [ *戻る* ] ボタンをクリックすると、そのページが閉じます (または、ユーザーが空白のページが閉じられる可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="6bd5f-122">ただし、リンクをもう一度クリックすると、このページが表示されるように、サイトの評価が reassessment されます。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="6bd5f-123">一部の Microsoft 365 管理者は、[ブロック] ページで **続行** するかどうかのメッセージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="6bd5f-124">ただし、安全なリンクによってサイトの評価が測定され、不足している場合は、これ以上のクリックスルーを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="6bd5f-125">ユーザーが安全対策を省略することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="6bd5f-126">続行する前に、この点を考慮に入れてください。</span><span class="sxs-lookup"><span data-stu-id="6bd5f-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span>
