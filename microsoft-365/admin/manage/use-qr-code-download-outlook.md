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
ms.openlocfilehash: b9e433e0c7d3f5f3466924b318e242e5ac29181c
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122374"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="453df-103">QR コードを使用して Outlook モバイル アプリにサインインする</span><span class="sxs-lookup"><span data-stu-id="453df-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="453df-104">この Microsoft 365 機能はパブリック プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="453df-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="453df-105">パブリック プレビューでは、Microsoft 365 の機能に早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="453df-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="453df-106">Microsoft 365 管理者は、ユーザー名とパスワードを入力せずに、モバイル デバイスで Android 用 Outlook または iOS アプリにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="453df-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="453df-107">QR コードをスキャンすることで、ユーザーは安全に認証し、Outlook Mobile にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="453df-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="453df-108">Outlook on the web または他のデスクトップ Outlook アプリケーションでは、モバイル デバイスで Outlook を使用できるという通知がユーザーに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="453df-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="453df-109">これらの通知は、管理者が Exchange Powershell を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="453df-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="453df-110">ユーザーがモバイル デバイスにアプリをダウンロードするために SMS テキスト メッセージを送信する場合、自分のコンピューターに QR コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="453df-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="453df-111">QR コードをスキャンして、スマートフォンやタブレットで Outlook にログインできます。</span><span class="sxs-lookup"><span data-stu-id="453df-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="453df-112">この QR コードは、1 回だけ使用できる短い有効期限のトークンです。</span><span class="sxs-lookup"><span data-stu-id="453df-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="453df-113">場合によっては、ユーザーが自分のコンピューターで再認証して QR コードを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="453df-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="453df-114">Exchange PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="453df-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="453df-115">このエクスペリエンスは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="453df-115">This experience is on by default.</span></span> <span data-ttu-id="453df-116">この機能を無効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="453df-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="453df-117">[Exchange PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="453df-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="453df-118">PowerShell を使用すると、Outlook モバイル アプリについてユーザーに通知する通知を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="453df-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="453df-119">これにより、QR コードのサインイン フローも表示されません。</span><span class="sxs-lookup"><span data-stu-id="453df-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="453df-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="453df-120">Related topics</span></span>

[<span data-ttu-id="453df-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="453df-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
