---
title: アプリに対するユーザーの同意を管理Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: アプリに対するユーザーの同意、およびアプリを有効にし、サード パーティ製アプリがユーザーの情報にアクセスMicrosoft 365します。
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391233"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="adae0-103">アプリに対するユーザーの同意を管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="adae0-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="adae0-104">この設定は、ユーザーがサインインおよびデータへのアクセス要求に OpenID Connect および OAuth 2.0 を使用するアプリに対してその同意を与えるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="adae0-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="adae0-105">アプリは、自分の組織内から作成するか、別の組織またはOffice 365から作成できます。</span><span class="sxs-lookup"><span data-stu-id="adae0-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="adae0-106">この設定を有効にすると、これらのアプリはユーザーに組織のデータへのアクセス許可を求め、ユーザーは許可するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="adae0-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="adae0-107">この設定をオフにした場合、管理者はユーザーがアプリを使用する前に、それらのアプリに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adae0-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="adae0-108">この場合は、ユーザーがブロックされたアプリを使用する管理者の承認要求を送信できるよう、Azure portal で管理者の同意ワークフローを設定する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="adae0-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="adae0-109">ユーザーは、Office 365 情報に対して自分自身が持っているアクセス権のみをアプリに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="adae0-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="adae0-110">他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="adae0-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="adae0-111">ユーザーの同意をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="adae0-111">Turning user consent on or off</span></span>

<span data-ttu-id="adae0-112">アプリに対するユーザーの同意を有効またはオフにする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="adae0-112">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="adae0-113">管理センターで、[組織の設定サービス]**ページ設定** に移動し、[アプリに対するユーザーの同意 \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743)**] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="adae0-113">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="adae0-114">[アプリ **に対するユーザーの同意** ] ページで、ユーザーの同意を有効または無効にするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="adae0-114">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="adae0-115">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="adae0-115">Related content</span></span> 

<span data-ttu-id="adae0-116">[管理者の同意ワークフローを構成](/azure/active-directory/manage-apps/configure-admin-consent-workflow) する (記事)</span><span class="sxs-lookup"><span data-stu-id="adae0-116">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="adae0-117">[アプリケーションへの同意の管理と同意要求の評価](/azure/active-directory/manage-apps/manage-consent-requests) (記事)</span><span class="sxs-lookup"><span data-stu-id="adae0-117">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>