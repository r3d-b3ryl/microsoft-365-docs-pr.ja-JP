---
title: Microsoft 365 でのアプリへのユーザーの同意の管理
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: アプリに対するユーザーの同意と、サードパーティ製アプリがユーザーの Microsoft 365 情報にアクセスできるようにする方法について説明します。
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999573"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="f480d-103">Microsoft 365 でのアプリへのユーザーの同意の管理</span><span class="sxs-lookup"><span data-stu-id="f480d-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="f480d-104">この設定では、サインインおよびデータアクセスの要求に対して、OpenID Connect と OAuth 2.0 を使用するアプリに対してユーザーが同意を得ることができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f480d-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="f480d-105">アプリは、自分の組織内から作成することも、別の Office 365 組織またはサードパーティから入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="f480d-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="f480d-106">この設定をオンにすると、これらのアプリは組織のデータへのアクセス許可をユーザーに要求し、許可するかどうかをユーザーが選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f480d-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="f480d-107">この設定をオフにすると、管理者は、ユーザーが使用できるようにする前に、これらのアプリに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f480d-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="f480d-108">この場合は、Azure ポータルで管理者の同意ワークフローを設定し、ブロックされたアプリを使用するためにユーザーが管理者の承認要求を送信できるようにすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f480d-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="f480d-109">ユーザーは、Office 365 情報に対して自分自身が持っているアクセス権のみをアプリに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="f480d-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="f480d-110">他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="f480d-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="f480d-111">ユーザーの同意を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f480d-111">Turning user consent on or off</span></span>
<span data-ttu-id="f480d-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f480d-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f480d-113">アプリに対するユーザーの同意を有効または無効にする方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f480d-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="f480d-114">管理センターで、[設定] [ **Settings** \> **組織設定**  >  [サービス](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページに移動し、[ **アプリへのユーザーの同意** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f480d-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="f480d-115">[ **アプリへのユーザーの同意** ] ページで、[ユーザーの同意を有効または無効にする] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f480d-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="f480d-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f480d-116">More info</span></span>
<span data-ttu-id="f480d-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f480d-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f480d-118">Azure active directory で同意設定を構成する方法については、「 [管理者の同意ワークフローを構成](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f480d-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="f480d-119">ユーザーの同意をアプリに対して管理する方法については、「 [アプリケーションの同意を管理する」および「同意要求を評価](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f480d-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>