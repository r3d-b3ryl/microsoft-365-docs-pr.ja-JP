---
title: Exchange Online の差出人セーフ リストと受信拒否リスト
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。
ms.openlocfilehash: 9c281460aeff64226343af5e5608ccf42fc83799
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238394"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="a8fe0-104">Exchange Online の差出人セーフ リストと受信拒否リスト</span><span class="sxs-lookup"><span data-stu-id="a8fe0-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="a8fe0-p102">Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="a8fe0-107">[Office 365 で良好なメールがスパムとしてマークされないようにする方法](prevent-email-from-being-marked-as-spam.md)*について、これらのリストを管理者として管理する方法に関するヒントと手順の更新版を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="a8fe0-108">管理者ではない場合に、差出人セーフリストを使用して Outlook で自分の迷惑メールを管理する場合は、[「迷惑メールフィルターの概要](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="a8fe0-109">Exchange Online での信頼できる差出人とブロックする差出人の制限について</span><span class="sxs-lookup"><span data-stu-id="a8fe0-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="a8fe0-p103">Exchange Online での信頼できる差出人とブロックする差出人の制限は、Active Directory の制限や Outlook の制限と異なります。以下にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>

- <span data-ttu-id="a8fe0-112">差出人セーフ リストの制限: 1,024</span><span class="sxs-lookup"><span data-stu-id="a8fe0-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="a8fe0-113">ブロックする差出人の制限: 500</span><span class="sxs-lookup"><span data-stu-id="a8fe0-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="a8fe0-114">注:</span><span class="sxs-lookup"><span data-stu-id="a8fe0-114">Note:</span></span>

<span data-ttu-id="a8fe0-115">[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)で説明されているエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="a8fe0-116">この問題を解決するには、[連絡先からの電子メールを信頼する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="a8fe0-117">または、"MaxSafeSenders" 属性に設定されている Exchange Online で、既定の連絡先フォルダーに含まれる電子メールアドレスの量を減らして、最大許容制限である1024に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="a8fe0-118">この属性とメールボックスの設定コマンドレットの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8fe0-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="a8fe0-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="a8fe0-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="a8fe0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8fe0-120">See also</span></span>

[<span data-ttu-id="a8fe0-121">Exchange Server での送信者フィルター</span><span class="sxs-lookup"><span data-stu-id="a8fe0-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
