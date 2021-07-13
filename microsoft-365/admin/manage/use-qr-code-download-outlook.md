---
title: QR コードを使用して Outlook Mobile アプリにサインインする
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: QR コードを使用して Outlook Mobile を認証し、ダウンロードする方法について学習します。
ms.openlocfilehash: c13fbeabd320c64925165ba16797d5a3471961ad
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391341"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="a5287-103">QR コードを使用して Outlook Mobile アプリにサインインする</span><span class="sxs-lookup"><span data-stu-id="a5287-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5287-104">この機能は、ターゲットリリースを有効にしている組織でのみMicrosoft 365 管理センター。</span><span class="sxs-lookup"><span data-stu-id="a5287-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a5287-105">対象指定リリースを有効にする方法と、その動作の詳細については、「[標準リリースまたはターゲット リリース オプションをセットアップする](release-options-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5287-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="a5287-106">パブリック プレビューを通じて、今後数週間でさらに多くの組織に展開される予定です。</span><span class="sxs-lookup"><span data-stu-id="a5287-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="a5287-107">パブリック プレビューでは、Microsoft 365 の機能に事前にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5287-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="a5287-108">Microsoft 365 管理者は、ユーザーがユーザー名とパスワードを入力しなくても、モバイル デバイスにおいてAndroid 版 Outlook または iOS 版 Outlook アプリにサインインできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5287-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="a5287-109">QR コードをスキャンすることで、ユーザーはセキュリティで保護された認証を行い、Outlook モバイルにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="a5287-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="a5287-110">Outlook on the web または他のデスクトップ Outlook アプリケーションでは、モバイル デバイスで Outlook を使用できる旨の通知がユーザーに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5287-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="a5287-111">管理者は、これらの通知を Exchange PowerShell を使用して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="a5287-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="a5287-112">ユーザーがモバイル デバイスにアプリをダウンロードするために、自分自身に SMS メッセージを送信する場合、QR コードが自分のコンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5287-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="a5287-113">QR コードをスキャンして、スマートフォンまたはタブレットで Outlook にログインできます。</span><span class="sxs-lookup"><span data-stu-id="a5287-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="a5287-114">この QR コードは有効期限の短いトークンで、1 回のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5287-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="a5287-115">場合によっては、ユーザーは QR コードを生成するためにコンピューターで再認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5287-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="a5287-116">Exchange PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="a5287-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="a5287-117">この機能は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a5287-117">This feature is on by default.</span></span> <span data-ttu-id="a5287-118">この機能を無効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a5287-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="a5287-119">[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a5287-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="a5287-120">PowerShell を使用すると、Outlook モバイル アプリに関するユーザーへの通知を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a5287-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="a5287-121">これにより、QR コードサインイン フローが表示されません。</span><span class="sxs-lookup"><span data-stu-id="a5287-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="a5287-122">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="a5287-122">Related content</span></span>

<span data-ttu-id="a5287-123">[標準リリースオプションまたは対象リリース オプションの設定](release-options-in-office-365.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="a5287-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="a5287-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (記事)</span><span class="sxs-lookup"><span data-stu-id="a5287-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (article)</span></span>