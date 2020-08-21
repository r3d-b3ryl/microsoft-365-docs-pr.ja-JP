---
title: S/MIME 設定の構成 - Outlook on web の Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online の Web 上の Outlook で S/MIME 設定を表示および構成するために Exchange Online 管理者が行う必要がある作業について、簡単に説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825703"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="d189c-103">Outlook on the web 用に Exchange Online で S/MIME 設定値を構成する</span><span class="sxs-lookup"><span data-stu-id="d189c-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="d189c-104">Exchange Online の管理者は、S/MIME 保護メッセージの送受信を可能にするために、Web 上の Outlook (Outlook Web App) をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="d189c-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="d189c-105">**Get-SmimeConfig コマンドレットおよび** **Set-SmimeConfig**コマンドレットを使用し、Exchange Online PowerShell でこの機能を表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="d189c-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="d189c-106">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d189c-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="d189c-107">構文およびパラメーターの詳細については[、「Get-SmimeConfig」および](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)[「Set-SmimeConfig」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)。</span><span class="sxs-lookup"><span data-stu-id="d189c-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="d189c-108">新しい Microsoft Edge (Chromium ベース) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d189c-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="d189c-109">新しい Microsoft Edge Web ブラウザーの Web 上の Outlook で S/MIME を使用するには、新しい [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) で Microsoft S/MIME 拡張機能をインストールするには、管理者 (または別の管理者) が設定および構成する必要があります。このポリシーでは **、ExtensionInstallForcelist** という名前の Microsoft Edge ブラウザー ポリシーを設定および構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d189c-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="d189c-110">ポリシーの値は `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`</span><span class="sxs-lookup"><span data-stu-id="d189c-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d189c-111">このポリシーを適用するには、ドメインに参加しているデバイスまたは Azure AD に参加しているデバイスが必要です。したがって、新しい Microsoft Edge ブラウザーで S/MIME を使うには、ドメインに参加しているデバイスまたは Azure AD 参加済みデバイスが効果的です。</span><span class="sxs-lookup"><span data-stu-id="d189c-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="d189c-112">**ExtensionInstallForcelist ポリシーの詳細については**[、ExtensionInstallForcelist を参照してください](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。</span><span class="sxs-lookup"><span data-stu-id="d189c-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="d189c-113">この手順は、新しい Microsoft Edge を使用するための前提条件です。ユーザーによってインストールされる S/MIME コントロールを置き換えるのでない。</span><span class="sxs-lookup"><span data-stu-id="d189c-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d189c-114">ユーザーは、S/MIME を初めて使用する場合に、S/MIME コントロールを Web 上の Outlook にダウンロードしてインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d189c-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d189c-115">または、Web 上の Outlook の設定で **S/MIME** に移動して、コントロールのダウンロード リンクを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="d189c-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="d189c-116">Chrome に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d189c-116">Considerations for Chrome</span></span>

<span data-ttu-id="d189c-117">Google Chrome Web ブラウザーの Web 上の Outlook で S/MIME を使用するには、Chrome で Microsoft S/MIME 拡張機能をインストールするには、ユーザー (または別の管理者) が **ExtensionInstallForcelist** という名前の Chromium ポリシーを設定して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d189c-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="d189c-118">ポリシーの値は `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`</span><span class="sxs-lookup"><span data-stu-id="d189c-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d189c-119">このポリシーを適用するには、ドメインに参加しているコンピューターが必要になります。Chrome で S/MIME を使うには、ドメインに参加しているコンピューターが効果的です。</span><span class="sxs-lookup"><span data-stu-id="d189c-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="d189c-120">**ExtensionInstallForcelist ポリシーの詳細については**[、ExtensionInstallForcelist を参照してください](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。</span><span class="sxs-lookup"><span data-stu-id="d189c-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="d189c-121">この手順は、Chrome を使うための前提条件です。ユーザーによってインストールされる S/MIME コントロールを置き換えるのでない。</span><span class="sxs-lookup"><span data-stu-id="d189c-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d189c-122">ユーザーは、S/MIME を初めて使用する場合に、S/MIME コントロールを Web 上の Outlook にダウンロードしてインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d189c-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d189c-123">または、Web 上の Outlook の設定で **S/MIME** に移動して、コントロールのダウンロード リンクを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="d189c-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d189c-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d189c-124">For more information</span></span>

[<span data-ttu-id="d189c-125">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="d189c-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
