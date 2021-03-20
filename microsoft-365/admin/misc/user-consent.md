---
title: Microsoft 365 のアプリに対するユーザーの同意の管理
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
description: アプリに対するユーザーの同意、およびアプリを有効にし、サード パーティ製アプリがユーザーの Microsoft 365 情報にアクセスできる方法について説明します。
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914560"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="442e8-103">Microsoft 365 のアプリに対するユーザーの同意の管理</span><span class="sxs-lookup"><span data-stu-id="442e8-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="442e8-104">この設定は、ユーザーがサインインおよびデータへのアクセス要求に OpenID Connect および OAuth 2.0 を使用するアプリに対してその同意を与えるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="442e8-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="442e8-105">アプリは、自分の組織内から作成するか、別の組織または 365 組織またはOfficeから作成できます。</span><span class="sxs-lookup"><span data-stu-id="442e8-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="442e8-106">この設定を有効にすると、これらのアプリはユーザーに組織のデータへのアクセス許可を求め、ユーザーは許可するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="442e8-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="442e8-107">この設定をオフにした場合、管理者はユーザーがアプリを使用する前に、それらのアプリに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="442e8-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="442e8-108">この場合は、ユーザーがブロックされたアプリを使用する管理者の承認要求を送信できるよう、Azure portal で管理者の同意ワークフローを設定する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="442e8-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="442e8-109">ユーザーは、Office 365 情報に対して自分自身が持っているアクセス権のみをアプリに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="442e8-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="442e8-110">他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="442e8-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="442e8-111">ユーザーの同意をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="442e8-111">Turning user consent on or off</span></span>
<span data-ttu-id="442e8-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="442e8-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="442e8-113">アプリに対するユーザーの同意を有効またはオフにする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="442e8-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="442e8-114">管理センターで、[組織の設定サービスの設定] ページに移動し、[アプリに対するユーザーの同意 \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743)**] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="442e8-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="442e8-115">[アプリ **に対するユーザーの同意** ] ページで、ユーザーの同意を有効または無効にするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="442e8-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="442e8-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="442e8-116">More info</span></span>
<span data-ttu-id="442e8-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="442e8-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="442e8-118">Azure active directory で同意設定を構成する方法については、「管理者の同意ワークフローを構成 [する」を参照してください](/azure/active-directory/manage-apps/configure-admin-consent-workflow)。</span><span class="sxs-lookup"><span data-stu-id="442e8-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="442e8-119">アプリに対するユーザーの同意を管理する方法については、「アプリケーションに対する同意の管理」と「同意要求 [の評価」を参照してください](/azure/active-directory/manage-apps/manage-consent-requests)。</span><span class="sxs-lookup"><span data-stu-id="442e8-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span></span>