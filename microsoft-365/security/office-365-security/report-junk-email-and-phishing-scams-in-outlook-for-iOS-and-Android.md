---
title: IOS および Android 用の Outlook で迷惑メールとフィッシング詐欺メールを報告する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、iOS および Android 用の Outlook に組み込まれている迷惑メールと迷惑メールの報告オプションについて説明しています。
ms.openlocfilehash: 23668a762301ee442bc805e62863079ee7ae6076
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350857"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="33d76-103">Exchange Online で iOS および Android 用の Outlook で迷惑メールとフィッシング詐欺メールを報告する</span><span class="sxs-lookup"><span data-stu-id="33d76-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="33d76-104">[ハイブリッド先進認証](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)を使用する Exchange online またはオンプレミスのメールボックスを含む Microsoft 365 組織では、IOS および Android 用の Outlook の組み込みのレポート作成オプションを使用して誤検知 (スパムとしてマークされた良好な電子メール)、誤検知 (無効な電子メールが許可されている)、および Exchange Online PROTECTION (EOP) へ</span><span class="sxs-lookup"><span data-stu-id="33d76-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33d76-105">開始する前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="33d76-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="33d76-106">Exchange Online メールボックスを使用している組織内の管理者である場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33d76-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="33d76-107">詳細については、「 [管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d76-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="33d76-108">指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="33d76-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="33d76-109">詳細については、「 [ユーザーの送信ポリシー](user-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d76-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="33d76-110">Microsoft へのメッセージの報告の詳細については、「 [microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d76-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="33d76-111">迷惑メール報告がユーザー送信ポリシーの Outlook に対して無効になっている場合、迷惑メールまたはフィッシングメッセージは迷惑メールフォルダーに移動され、管理者または Microsoft には報告されません。</span><span class="sxs-lookup"><span data-stu-id="33d76-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="33d76-112">IOS および Android 用の Outlook でスパムメッセージとフィッシングメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="33d76-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="33d76-113">受信トレイ内のメッセージ、または迷惑メール以外の他の電子メールフォルダーについては、次の手順を使用して、iOS および Android 用のスパムおよびフィッシングメッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="33d76-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="33d76-114">1つ以上のメッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="33d76-114">Select one or more messages.</span></span>
2. <span data-ttu-id="33d76-115">右上隅にある3つの垂直点をタップします。</span><span class="sxs-lookup"><span data-stu-id="33d76-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="33d76-116">[アクション] メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="33d76-116">The action menu opens.</span></span>

   ![[アクション] メニューから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="33d76-118">[ **迷惑メールを報告** ] をタップしてから、[ **迷惑メール** または **フィッシング詐欺**] を選択</span><span class="sxs-lookup"><span data-stu-id="33d76-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![迷惑メールまたはフィッシング詐欺メールを報告する](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="33d76-120">表示されるダイアログで、[ **レポート** ] または [ **いいえ**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="33d76-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="33d76-121">[ **いいえ**] を選択した場合、[ **迷惑** メール] をタップすると、メッセージは [迷惑メール] フォルダーに移動します。 **フィッシング** をタップすると、メッセージは [削除済みアイテム] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="33d76-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="33d76-122">[ **レポート** ] を選択して、メッセージのコピーも Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="33d76-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![迷惑メールまたはフィッシング詐欺メールレポートのオプションを報告する](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="33d76-124">気が変わった場合は、表示されるトースト通知で [ **元に戻す** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d76-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="33d76-125">メッセージは受信トレイフォルダーに残ります。</span><span class="sxs-lookup"><span data-stu-id="33d76-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="33d76-126">Outlook for iOS および Android 用の迷惑メールフォルダーから非スパムメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="33d76-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="33d76-127">[迷惑メール] フォルダーで、次の手順を使用してスパム誤検知を報告します。</span><span class="sxs-lookup"><span data-stu-id="33d76-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="33d76-128">1つ以上のメッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="33d76-128">Select one or more messages.</span></span>
2. <span data-ttu-id="33d76-129">右上隅にある3つの垂直点をタップします。</span><span class="sxs-lookup"><span data-stu-id="33d76-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="33d76-130">[アクション] メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="33d76-130">The action menu opens.</span></span>

   ![[アクション] メニューから迷惑メールではないことを報告する](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="33d76-132">**迷惑メールではない**をタップします。</span><span class="sxs-lookup"><span data-stu-id="33d76-132">Tap **Not junk**.</span></span>

<span data-ttu-id="33d76-133">トースト通知は、電子メールが受信トレイに移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="33d76-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="33d76-134">気が変わった場合は、トースト通知で [ **元に戻す** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d76-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="33d76-135">電子メールは、迷惑メールフォルダーに残ります。</span><span class="sxs-lookup"><span data-stu-id="33d76-135">The email remains in the Junk folder.</span></span>
