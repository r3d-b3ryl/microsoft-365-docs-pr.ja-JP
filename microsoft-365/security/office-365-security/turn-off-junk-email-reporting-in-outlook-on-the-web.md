---
title: Outlook on the web で迷惑メール レポートを無効にする
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Office 365 管理者は、ユーザーが迷惑メールとして電子メールを報告する機能をオフにできます。
ms.openlocfilehash: 46ce4de8fa6ea14c81041208864957cbc73aebf5
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871283"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="cb65f-103">Outlook on the web で迷惑メール レポートを無効にする</span><span class="sxs-lookup"><span data-stu-id="cb65f-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="cb65f-104">Web 上の outlook on the web (以前の outlook Web App) の迷惑メール報告オプションを使用して、outlook on the web[上](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の outlook on the web を使用して分析することができます。</span><span class="sxs-lookup"><span data-stu-id="cb65f-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="cb65f-105">これらのオプションを使用しない場合は、管理者[は、次のコマンドレット](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)を使用してオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb65f-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) cmdlet.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cb65f-106">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="cb65f-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="cb65f-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="cb65f-107"></span></span>

- <span data-ttu-id="cb65f-108">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="cb65f-108">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="cb65f-109">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb65f-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="cb65f-110">必要なアクセス許可については、「 [Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)」の「web 上の Outlook メールボックスポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb65f-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

- <span data-ttu-id="cb65f-111">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb65f-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="cb65f-112">迷惑メール報告をオフにして Microsoft に通知しない</span><span class="sxs-lookup"><span data-stu-id="cb65f-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="cb65f-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="cb65f-113"></span></span>

<span data-ttu-id="cb65f-114">最初に、次のコマンドを実行して、web メールボックスポリシーで利用可能な Outlook の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb65f-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>

```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="cb65f-115">次に、以下の構文を使用して、Outlook on the web で迷惑メール報告を Microsoft に対して有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="cb65f-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="cb65f-116">この例では、既定の Outlook web app メールボックスポリシーでのレポートをオフにします。</span><span class="sxs-lookup"><span data-stu-id="cb65f-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="cb65f-117">構文およびパラメーターの詳細については、「[収集](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)」を[参照してください。](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="cb65f-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cb65f-118">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="cb65f-118">How do you know this worked?</span></span>
<span data-ttu-id="cb65f-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="cb65f-119"></span></span>

<span data-ttu-id="cb65f-120">**Get-Owamare Boxpolicy**を実行してパラメーター値を確認した後、影響を受けるユーザー (web 上の outlook メールボックスポリシーが適用されているユーザー) に対して web 上の outlook を開き、迷惑メールを報告するオプションが使用できないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb65f-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="cb65f-121">引き続き迷惑メール、フィッシング、および迷惑メールとしてメッセージをマークすることはできますが、それらを報告することはできません。</span><span class="sxs-lookup"><span data-stu-id="cb65f-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span>
