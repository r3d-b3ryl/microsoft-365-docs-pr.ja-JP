---
title: iOS および Android 用の Outlook で迷惑メールとフィッシングメールを報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、iOS および Android 用の Outlook の組み込みの迷惑メール、迷惑メール、フィッシングメール報告オプションについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d702ab1d97c07c3e38430a9a7beff5f14db7b60a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029282"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="6ba20-103">Exchange Online で iOS および Android 用の Outlook で迷惑メールとフィッシングメールを報告する</span><span class="sxs-lookup"><span data-stu-id="6ba20-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6ba20-104">ハイブリッドの最新認証を使用して Exchange Online またはオンプレミスのメールボックスにメールボックスを持[](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)つ Microsoft 365 組織では、iOS および Android 用の Outlook の組み込みのレポート オプションを使用して、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="6ba20-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6ba20-105">始める前に知る必要がある情報</span><span class="sxs-lookup"><span data-stu-id="6ba20-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="6ba20-106">Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ba20-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="6ba20-107">詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba20-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="6ba20-108">指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6ba20-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="6ba20-109">詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="6ba20-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="6ba20-110">Microsoft にメッセージを報告する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="6ba20-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="6ba20-111">ユーザー送信ポリシーで Outlook で迷惑メール報告が無効になっている場合、迷惑メールまたはフィッシングメッセージは迷惑メール フォルダーに移動され、管理者や Microsoft には報告されません。</span><span class="sxs-lookup"><span data-stu-id="6ba20-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="6ba20-112">iOS および Android 用の Outlook でスパムメッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="6ba20-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="6ba20-113">受信トレイ内のメッセージ、または迷惑メール以外の他のメール フォルダーの場合は、次の手順を使用して、iOS および Android のスパム メッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="6ba20-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="6ba20-114">1 つ以上のメッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="6ba20-114">Select one or more messages.</span></span>
2. <span data-ttu-id="6ba20-115">右上隅で、3 つの垂直ドットをタップします。</span><span class="sxs-lookup"><span data-stu-id="6ba20-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="6ba20-116">操作メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba20-116">The action menu opens.</span></span>

   ![操作メニューから迷惑メールまたはフィッシングメールを報告する](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="6ba20-118">[ **迷惑メールの報告]** をタップし、[ **迷惑メール** ] または [フィッシング **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6ba20-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![迷惑メールまたはフィッシングメールを報告する](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="6ba20-120">表示されるダイアログで、[レポート] または [No Thanks]**を\*\*\*\*選択できます**。</span><span class="sxs-lookup"><span data-stu-id="6ba20-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="6ba20-121">On selecting **No Thanks,** if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span><span class="sxs-lookup"><span data-stu-id="6ba20-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="6ba20-122">[ **レポート]** を選択すると、メッセージのコピーも Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="6ba20-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![迷惑メールまたはフィッシングメールの報告オプションを報告する](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="6ba20-124">考え変えた場合は、表示されるトースト **通知で** [元に戻す] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ba20-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="6ba20-125">メッセージは受信トレイ フォルダーに残ります。</span><span class="sxs-lookup"><span data-stu-id="6ba20-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="6ba20-126">iOS および Android 用の Outlook の [迷惑メール] フォルダーからスパムではないメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="6ba20-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="6ba20-127">迷惑メール フォルダーで、次の手順を使用してスパムの誤検知を報告します。</span><span class="sxs-lookup"><span data-stu-id="6ba20-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="6ba20-128">1 つ以上のメッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="6ba20-128">Select one or more messages.</span></span>
2. <span data-ttu-id="6ba20-129">右上隅で、3 つの垂直ドットをタップします。</span><span class="sxs-lookup"><span data-stu-id="6ba20-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="6ba20-130">操作メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba20-130">The action menu opens.</span></span>

   ![操作メニューから迷惑メールではないメールを報告する](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="6ba20-132">[迷惑 **メールではない] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="6ba20-132">Tap **Not junk**.</span></span>

<span data-ttu-id="6ba20-133">電子メールが受信トレイに移動したというトースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba20-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="6ba20-134">考え方が変わる場合は、トースト **通知で [元に戻** す] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ba20-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="6ba20-135">メールは迷惑メール フォルダーに残ります。</span><span class="sxs-lookup"><span data-stu-id="6ba20-135">The email remains in the Junk folder.</span></span>
