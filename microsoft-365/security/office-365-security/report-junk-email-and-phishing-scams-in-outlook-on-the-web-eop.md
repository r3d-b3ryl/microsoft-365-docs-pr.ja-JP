---
title: 'Outlook on the web で迷惑メールとフィッシング詐欺を報告する '
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Microsoft Outlook on the web ユーザーは、組み込みの電子メール報告オプションを使用して、迷惑メール (スパム) とフィッシング詐欺を報告することができます。 また、電子メールが誤って迷惑メール (スパム) として識別されたかどうかを Microsoft に知らせることもできます。
ms.openlocfilehash: 98b53aa17cb84defa9d20aa4610390db9f5447c5
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957422"
---
# <a name="report-junk-email-and-phishing-scams-in-outlook-on-the-web"></a><span data-ttu-id="d29ae-104">Outlook on the web で迷惑メールとフィッシング詐欺を報告する</span><span class="sxs-lookup"><span data-stu-id="d29ae-104">Report junk email and phishing scams in Outlook on the web</span></span>

<span data-ttu-id="d29ae-p102">組織のユーザーが迷惑メールを受信したり、重要なメールがスパムと誤認されたため受信できなかったりすると、苛立つ原因になることがあります。Exchange Online Protection (EOP) スパム フィルターは精度を上げるための微調整が継続的に行われているため、お客様とエンド ユーザーはこのプロセスから恩恵を受けることができます。Microsoft Outlook on the web のユーザーは、組み込みの電子メール レポート オプションを使用して、迷惑メール (スパム) とフィッシング詐欺を報告できます。電子メールが迷惑メール (スパム) として誤って識別されたかどうかを Microsoft に通知することもできます。</span><span class="sxs-lookup"><span data-stu-id="d29ae-p102">It can be frustrating when users in your organization receive junk email or miss an important email because it was misidentified as spam. We're constantly fine-tuning the Exchange Online Protection (EOP) spam filters to be more accurate, and you and your end users can help with this process; Microsoft Outlook on the web users can report junk (spam) and phishing scams by using built-in email reporting options. You can also let Microsoft know if an email was incorrectly identified as junk (spam).</span></span>

## <a name="submit-junk-messages-in-outlook-on-the-web"></a><span data-ttu-id="d29ae-108">Outlook on the web で迷惑メール メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="d29ae-108">Submit junk messages in Outlook on the web</span></span>

<span data-ttu-id="d29ae-109">迷惑メール メッセージを Microsoft に送信するには:</span><span class="sxs-lookup"><span data-stu-id="d29ae-109">To submit a junk mail message to Microsoft:</span></span>

1. <span data-ttu-id="d29ae-p103">迷惑メール メッセージをクリックしてから、ツールバーの **[迷惑メール]** をクリックします。これにより、メッセージが迷惑メール フォルダーに移動され、その送信者が受信拒否リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d29ae-p103">Click on the junk message and then click **Junk** on the toolbar. This moves the message to your Junk email folder and adds the sender to your blocked sender list.</span></span>

   ![電子メールが Web 上の Outlook からの迷惑メールであることを示しています](../media/a10ae792-aab6-4374-a041-6c3f732eb2e3.png)

   > [!NOTE]
   > <span data-ttu-id="d29ae-113">または、メッセージを右クリックしてメニューを表示し、 **[迷惑メールにする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d29ae-113">Alternatively, right-click a message to display a menu, and click **Mark as junk**.</span></span>

   <span data-ttu-id="d29ae-114">迷惑メールメッセージは、**受信トレイ**または**削除済みアイテム**フォルダーから報告できます。</span><span class="sxs-lookup"><span data-stu-id="d29ae-114">You can report a junk message from your **Inbox** or **Deleted Items** folder.</span></span>

2. <span data-ttu-id="d29ae-p104">迷惑メール メッセージのコピーを分析のために Microsoft に送信するかどうかを確認するダイアログ ボックスが開きます。Microsoft スパム分析チームにメッセージを送信する場合は、 **[報告]** をクリックします。今後の迷惑メール メッセージをプロンプトなしで Microsoft に自動的に送信する場合には、オプションで、 **[今後、このメッセージを表示しない]** チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d29ae-p104">A dialog box opens asking if you want to send a copy of the junk email message to Microsoft for analysis. Click **report** to send the message to the Microsoft Spam Analysis Team. Optionally, select the **Don't show me this message again** check box if you want to automatically submit future junk messages to Microsoft without being prompted.</span></span>

   ![Web 上の Outlook から Microsoft に迷惑メールについて報告します](../media/e8d3a9f9-6eb6-4309-ba6d-643dffdb6a33.png)

   > [!TIP]
   > <span data-ttu-id="d29ae-p105">**[今後、このメッセージを表示しない]** チェック ボックスを選択した場合でも、後で Outlook on the web の表示設定にアクセスすることによって、迷惑メールを報告するようにこの設定を変更することができます (これらの設定には、サインイン名の横にあるギア メニューからアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="d29ae-p105">Even if you select the **Don't show me this message again** check box, you can later change your preferences for reporting junk email by accessing the display settings in Outlook on the web. (You can access these settings through the gear menu next to your sign in name.)</span></span>

## <a name="submit-phishing-scam-messages-in-outlook-on-the-web"></a><span data-ttu-id="d29ae-121">Outlook on the web でフィッシング詐欺メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="d29ae-121">Submit phishing scam messages in Outlook on the web</span></span>

<span data-ttu-id="d29ae-122">フィッシング詐欺メッセージを Microsoft に送信するには:</span><span class="sxs-lookup"><span data-stu-id="d29ae-122">To submit a phishing scam message to Microsoft:</span></span>

1. <span data-ttu-id="d29ae-123">フィッシング詐欺メッセージをクリックして、 **[迷惑メール]** の横にある下向き矢印をクリックしてから、ツールバーの **[フィッシング]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d29ae-123">Click on the phishing scam message, click the down arrow next to **Junk**, and then click **Phishing** on the toolbar.</span></span> <span data-ttu-id="d29ae-124">フィッシング詐欺メッセージの送信者は正当な送信者を偽装していることが多いため、Office 365 は送信者をブロックしません。</span><span class="sxs-lookup"><span data-stu-id="d29ae-124">Office 365 does not block the sender because senders of phishing scam messages typically impersonate legitimate senders.</span></span> <span data-ttu-id="d29ae-125">必要に応じて、「 [web 上の Outlook で迷惑メールとスパムをフィルター](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)する」の手順に従って、送信者を受信拒否リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="d29ae-125">If you prefer, add the sender to your blocked senders list by following the instructions in the topic [Filter junk email and spam in Outlook on the web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d).</span></span>

   ![電子メールが Web 上の Outlook 内のフィッシング詐欺メールであることを示しています](../media/959bb577-341c-41ee-a159-e46600b2cf8a.png)

   <span data-ttu-id="d29ae-127">または、メッセージを右クリックしてメニューを表示し、 **[Mark as Phishing] (フィッシングとして報告する)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d29ae-127">Alternatively, right-click a message to display a menu, and click **Mark as Phishing**.</span></span>

   <span data-ttu-id="d29ae-128">フィッシング詐欺メッセージは、**受信トレイ**または**削除済みアイテム**フォルダーから報告できます。</span><span class="sxs-lookup"><span data-stu-id="d29ae-128">You can report a phishing scam message from your **Inbox** or **Deleted Items** folder.</span></span>

2. <span data-ttu-id="d29ae-p107">組織によっては、フィッシング詐欺メールのコピーを分析のために Microsoft に送信するかどうかを尋ねるダイアログ ボックスが表示されます。メッセージを Microsoft スパム分析チームに送信するには、 **[報告]** をクリックします。この報告オプションは、現在、一部の組織でしか利用できません。そのため、フィッシング詐欺を Microsoft に報告するかどうかが尋ねられない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d29ae-p107">For some organizations, a dialog box opens asking if you want to send a copy of the phishing scam email to Microsoft for analysis. Click **report** to send the message to the Microsoft Spam Analysis Team. This reporting option is currently available to a limited number of organizations; you might not be asked to report a phishing scam to Microsoft.</span></span>

## <a name="submit-not-junk-messages-in-outlook-on-the-web"></a><span data-ttu-id="d29ae-132">Outlook on the web で「迷惑メールではないメール」メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="d29ae-132">Submit "not junk" messages in Outlook on the web</span></span>

<span data-ttu-id="d29ae-133">Office 365 によってメッセージが迷惑メールとして誤って識別された場合は、メッセージを「迷惑メールではないメール」として Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="d29ae-133">When a message is incorrectly identified as junk by Office 365, submit a message as "not junk" to Microsoft:</span></span>

1. <span data-ttu-id="d29ae-p108">迷惑メール フォルダーで、そのメッセージをクリックしてから、ツールバーの **[迷惑メールではないメール]** をクリックします。これにより、メッセージが **受信トレイ**に移動され、その送信者が差出人セーフ リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d29ae-p108">In your Junk email folder, click on the message and then click **Not Junk** on the toolbar. This moves the message to your **Inbox** and adds the sender to your safe senders list.</span></span>

   <span data-ttu-id="d29ae-136">[迷惑メール] フォルダー内のメッセージを右クリックしてメニューを表示し、[迷惑メールで**はないメールとしてマーク**] をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d29ae-136">You can also right-click on a message in your Junk mail folder to display a menu and click **Mark as not junk**.</span></span>

2. <span data-ttu-id="d29ae-p109">迷惑メールではないメール メッセージのコピーを分析のために Microsoft に送信するかどうかを尋ねるダイアログ ボックスが表示されます。Microsoft スパム分析チームにメッセージを送信するには、**[報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d29ae-p109">A dialog box opens asking if you want to send a copy of the not junk email message to Microsoft for analysis. Click **report** to send the message to the Microsoft Spam Analysis Team..</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d29ae-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d29ae-139">For more information</span></span>

[<span data-ttu-id="d29ae-140">迷惑メールやフィッシング詐欺について</span><span class="sxs-lookup"><span data-stu-id="d29ae-140">Learn about junk email and phishing</span></span>](https://support.microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)

[<span data-ttu-id="d29ae-141">Microsoft Outlook 用迷惑メール報告アドイン</span><span class="sxs-lookup"><span data-stu-id="d29ae-141">Junk email reporting add-in for Microsoft Outlook</span></span>](https://docs.microsoft.com/office365/securitycompliance/junk-email-reporting-add-in-for-microsoft-outlook)
