---
title: トラブルシューティングとサポート情報
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: このトピックでは、エンドユーザーと管理者向けのトラブルシューティング手順と、支援を得るためのテクニカル サポートへの問合わせ方法について説明します。
ms.openlocfilehash: efb71aab852b76b2b898419444bfea4144728514
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598174"
---
# <a name="troubleshooting-and-support-information"></a><span data-ttu-id="cd561-103">トラブルシューティングとサポート情報</span><span class="sxs-lookup"><span data-stu-id="cd561-103">Troubleshooting and support information</span></span>

<span data-ttu-id="cd561-104">このトピックでは、エンドユーザーと管理者向けのトラブルシューティング手順と、支援を得るためのテクニカル サポートへの問合わせ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd561-104">This topic describes troubleshooting steps for end users and administrators, and provides information about how to contact technical support for assistance.</span></span>

## <a name="troubleshooting-for-users"></a><span data-ttu-id="cd561-105">ユーザー向けのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cd561-105">Troubleshooting for Users</span></span>

<span data-ttu-id="cd561-106">迷惑メール報告アドインを追加した後、Microsoft Outlook で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cd561-106">Occasionally, you may experience trouble with Microsoft Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="cd561-107">発生する可能性のある問題とそれらの問題を解決するためのヒントを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="cd561-107">Following are problems that you may encounter, along with tips for resolving these issues.</span></span>

- <span data-ttu-id="cd561-108">**[迷惑メールの報告]** をクリックしても何も起こらない</span><span class="sxs-lookup"><span data-stu-id="cd561-108">Nothing happens when you click **Report Junk**</span></span>

- <span data-ttu-id="cd561-109">電子メール メッセージを選択した後に Outlook が応答しなくなった</span><span class="sxs-lookup"><span data-stu-id="cd561-109">Outlook stops responding after you select an email message</span></span>

- <span data-ttu-id="cd561-110">"配信不能" と返され、報告された迷惑メールを配信できない</span><span class="sxs-lookup"><span data-stu-id="cd561-110">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="cd561-111">この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd561-111">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="cd561-112">Outlook を閉じて、再起動します。</span><span class="sxs-lookup"><span data-stu-id="cd561-112">Close and restart Outlook.</span></span>

2. <span data-ttu-id="cd561-p102">テスト メッセージを作成して、送信できることを確認します。これを実行するには、テスト メッセージを自分が管理する別の電子メール アカウントに送信し、電子メール メッセージが受信されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd561-p102">Verify that you are able to create and send a test message. To do this, you can send a test message to another email account that you are responsible for, and then verify that the email message is received.</span></span>

<span data-ttu-id="cd561-115">問題が解決しない場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="cd561-115">If the problem persists, contact your admin.</span></span>

> [!TIP]
> <span data-ttu-id="cd561-p103">また [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) 宛てにレポートを送信し、Microsoft に直接スパム メッセージを報告することもできます。さらに、誤検知のメッセージについては [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com) の電子メール アドレスに報告できます。詳細については、「 [スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd561-p103">You can also submit spam messages directly to Microsoft by using the [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) email address, and false positive messages by using the [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com) email address. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>

## <a name="troubleshooting-for-administrators"></a><span data-ttu-id="cd561-118">管理者向けのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cd561-118">Troubleshooting for Administrators</span></span>

<span data-ttu-id="cd561-119">管理者は、Outlook 用迷惑メール報告アドインを使用しているユーザーに問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cd561-119">As an administrator, you might experience issues with users using the Junk Email Reporting Add-in for Outlook.</span></span> <span data-ttu-id="cd561-120">以下に、発生する可能性のある問題を解決するためのヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="cd561-120">Following are some tips for resolving problems that you might encounter.</span></span>

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a><span data-ttu-id="cd561-121">問題: ユーザーにシステム管理者に問い合わせるよう要求するエラーメッセージが継続的に表示される</span><span class="sxs-lookup"><span data-stu-id="cd561-121">Problem: An error message asking users to contact their system administrator continually appears</span></span>

1. <span data-ttu-id="cd561-122">次のレジストリ キーの値を "Verbose" に設定します。</span><span class="sxs-lookup"><span data-stu-id="cd561-122">Set the following registry key value to "Verbose":</span></span>

   - <span data-ttu-id="cd561-123">**32 ビットオペレーティングシステムにインストールされ32た Outlook**:</span><span class="sxs-lookup"><span data-stu-id="cd561-123">**32 bit Outlook installed on a 32 bit operating system**:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - <span data-ttu-id="cd561-124">**32 ビットオペレーティングシステムにインストールされ64た Outlook**:</span><span class="sxs-lookup"><span data-stu-id="cd561-124">**32 bit Outlook installed on a 64 bit operating system**:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - <span data-ttu-id="cd561-125">**64 ビット Outlook (常に64ビットオペレーティングシステムにインストールされます)**:</span><span class="sxs-lookup"><span data-stu-id="cd561-125">**64 bit Outlook (always installed on a 64 bit operating system)**:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. <span data-ttu-id="cd561-126">Outlook を再起動し、エラーメッセージが表示された場合にユーザーに報告するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="cd561-126">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="cd561-127">次の場所にあるログ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="cd561-127">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="cd561-128">Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cd561-128">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a><span data-ttu-id="cd561-129">問題: ユーザーがメールを迷惑メールとして送信したときに、確認メッセージを表示しないように選択した</span><span class="sxs-lookup"><span data-stu-id="cd561-129">Problem: Users choose not to receive a confirmation when they submit an email as junk and now they want the option back</span></span>

1. <span data-ttu-id="cd561-130">次のレジストリキーの値を "True" に`HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`設定します。</span><span class="sxs-lookup"><span data-stu-id="cd561-130">Set the following registry key value to "True": `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`.</span></span>

2. <span data-ttu-id="cd561-131">Outlook を再起動します。</span><span class="sxs-lookup"><span data-stu-id="cd561-131">Restart Outlook.</span></span>

## <a name="support-information"></a><span data-ttu-id="cd561-132">サポート情報</span><span class="sxs-lookup"><span data-stu-id="cd561-132">Support Information</span></span>

<span data-ttu-id="cd561-133">アドインのインストール、構成、またはアンインストールに関してサポートが必要な場合は、Microsoft 365 管理センターのサポートページにある [新しいサービスリクエスト] リンクを使用してテクニカルサポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="cd561-133">If you need help with the installation, configuration, or uninstallation of the add-in, please contact technical support using the new service request link on the support page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cd561-134">電話およびセルフサポートオプション経由でのサービス要求の提出などのその他のオプションについては、「 [Help and support FOR EOP](help-and-support-for-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd561-134">For additional options including submitting a service request via the telephone and self-support options, see [Help and support for EOP](help-and-support-for-eop.md).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="cd561-135">関連情報</span><span class="sxs-lookup"><span data-stu-id="cd561-135">For more information</span></span>

[<span data-ttu-id="cd561-136">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="cd561-136">Enable the Report Message add-in</span></span>](enable-the-report-message-add-in.md)

[<span data-ttu-id="cd561-137">迷惑メール メッセージを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="cd561-137">Report junk email messages to Microsoft</span></span>](report-junk-email-messages-to-microsoft.md)
