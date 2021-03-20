---
title: QR コードを使用して Outlook モバイル アプリにサインインする
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
description: QR コードを使用して Outlook モバイルを認証およびダウンロードする方法について学習します。
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914968"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="3f2e8-103">QR コードを使用して Outlook モバイル アプリにサインインする</span><span class="sxs-lookup"><span data-stu-id="3f2e8-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f2e8-104">この機能は、Microsoft 365 管理センターでターゲット リリースを有効にしている組織でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3f2e8-105">ターゲットリリースを有効にし、その動作の詳細については、「標準リリースオプションまたはターゲットリリースオプションを設定する」 [を参照してください](release-options-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="3f2e8-106">パブリック プレビューを通じて、今後数週間でさらに多くの組織に展開する予定です。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="3f2e8-107">パブリック プレビューは、Microsoft 365 の機能への早期アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="3f2e8-108">Microsoft 365 管理者は、ユーザー名とパスワードを入力することなく、モバイル デバイスで Outlook for Android または iOS アプリにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="3f2e8-109">QR コードをスキャンすることで、ユーザーは安全に認証し、Outlook モバイルにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="3f2e8-110">Outlook on the web または他のデスクトップ Outlook アプリケーションでは、ユーザーはモバイル デバイスで Outlook を使用できるという通知を表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="3f2e8-111">これらの通知は、管理者が Exchange Powershell を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="3f2e8-112">ユーザーがモバイル デバイスでアプリをダウンロードする SMS テキスト メッセージを自分で送信する場合は、自分のコンピューターに QR コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="3f2e8-113">QR コードをスキャンして、自分の携帯電話またはタブレットで Outlook にログインできます。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="3f2e8-114">この QR コードは、1 回だけ引き換え可能な短命トークンです。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="3f2e8-115">場合によっては、ユーザーが自分のコンピューターで再認証して QR コードを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="3f2e8-116">Exchange PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="3f2e8-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="3f2e8-117">この機能は既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-117">This feature is on by default.</span></span> <span data-ttu-id="3f2e8-118">この機能を無効にするには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="3f2e8-119">[Exchange PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="3f2e8-120">PowerShell を使用すると、Outlook モバイル アプリについてユーザーに通知する通知を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="3f2e8-121">これにより、QR コードサインイン フローが表示されるのを防ぐものになります。</span><span class="sxs-lookup"><span data-stu-id="3f2e8-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="3f2e8-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f2e8-122">Related topics</span></span>

[<span data-ttu-id="3f2e8-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="3f2e8-123">Set-OrganizationConfig</span></span>](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)