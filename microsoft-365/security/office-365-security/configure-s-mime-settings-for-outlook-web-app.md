---
title: S/MIME 設定の構成-web 上の Outlook の Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange online の Outlook on the web で S/MIME 設定を表示および構成するために必要な Exchange Online 管理者の簡単な説明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ed3f3c6289c4663c6bebecdf9ab03eacd94e373
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035096"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="b69ef-103">Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b69ef-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="b69ef-104">Exchange Online の管理者は、S/MIME で保護されたメッセージを送受信できるように、Outlook on the web (旧称 Outlook Web App) をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="b69ef-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="b69ef-105">Exchange Online PowerShell でこの機能を表示および管理するには、 **-smimeconfig**コマンドレットおよび**Set-smimeconfig**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b69ef-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="b69ef-106">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69ef-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="b69ef-107">構文およびパラメーターの詳細については、「 [Get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) 」および「 [Set-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69ef-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="b69ef-108">新しい Microsoft Edge (Chromium ベース) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="b69ef-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="b69ef-109">Web 上の Outlook で S/MIME を新しい[Microsoft edge](https://www.microsoft.com/windows/microsoft-edge) web ブラウザーで使用するには、microsoft edge の新しい microsoft Edge に microsoft S/mime 拡張機能をインストールするために、ユーザー (または別の管理者) が、 **Extensioninstallforcelist**という microsoft edge browser policy を設定および構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69ef-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in new Microsoft Edge.</span></span> <span data-ttu-id="b69ef-110">ポリシーの値は`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`です。</span><span class="sxs-lookup"><span data-stu-id="b69ef-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="b69ef-111">このポリシーを適用するには、ドメインに参加しているコンピューターが必要であるため、新しい Microsoft Edge ブラウザーで S/MIME を使用するとドメインに参加しているコンピューターが効果的に必要になります。</span><span class="sxs-lookup"><span data-stu-id="b69ef-111">And note that applying this policy requires domain-joined computers, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined computers.</span></span>

<span data-ttu-id="b69ef-112">**Extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69ef-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="b69ef-113">この手順は、新しい Microsoft Edge を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="b69ef-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="b69ef-114">S/MIME の初めての使用時に、S/MIME コントロールをダウンロードして、web 上の Outlook にインストールするようにユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="b69ef-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="b69ef-115">または、ユーザーが Outlook on the web 設定で**S/MIME**を事前に参照して、コントロールのダウンロードリンクを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="b69ef-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="b69ef-116">Chrome の考慮事項</span><span class="sxs-lookup"><span data-stu-id="b69ef-116">Considerations for Chrome</span></span>

<span data-ttu-id="b69ef-117">Google Chrome web ブラウザーで Outlook on the web で S/MIME を使用するには、ユーザー (または別の管理者) が**Extensioninstallforcelist**という名前の Chromium ポリシーを設定および構成して、Microsoft S/mime 拡張機能を Chrome にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b69ef-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="b69ef-118">ポリシーの値は`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`です。</span><span class="sxs-lookup"><span data-stu-id="b69ef-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="b69ef-119">このポリシーを適用するには、ドメインに参加しているコンピューターが必要であるため、Chrome で S/MIME を使用するとドメインに参加しているコンピューターが効果的に必要になります。</span><span class="sxs-lookup"><span data-stu-id="b69ef-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="b69ef-120">**Extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69ef-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="b69ef-121">この手順は、Chrome を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="b69ef-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="b69ef-122">S/MIME の初めての使用時に、S/MIME コントロールをダウンロードして、web 上の Outlook にインストールするようにユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="b69ef-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="b69ef-123">または、ユーザーが Outlook on the web 設定で**S/MIME**を事前に参照して、コントロールのダウンロードリンクを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="b69ef-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b69ef-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b69ef-124">For more information</span></span>

[<span data-ttu-id="b69ef-125">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="b69ef-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
