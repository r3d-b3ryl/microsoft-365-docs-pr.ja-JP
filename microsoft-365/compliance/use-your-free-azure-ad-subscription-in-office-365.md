---
title: Office 365 で無料の Azure Active Directory サブスクリプションを使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: 組織の Office 365 の有料サブスクリプションに含まれる、Azure Active Directory にアクセスする方法について説明します。
ms.openlocfilehash: 40ed5808f6e921a3649af408ee078dba64167bb3
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610594"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="f70b0-103">Office 365 で無料の Azure Active Directory サブスクリプションを使用する</span><span class="sxs-lookup"><span data-stu-id="f70b0-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="f70b0-p101">組織が Office 365、Microsoft Dynamics CRM Online、Enterprise Mobility Suite、その他の Microsoft サービスの有料サブスクリプションを保有している場合、Microsoft Azure Active Directory の無料サブスクリプションを利用できます。管理者であれば、Azure AD を使用してユーザー アカウントとグループ アカウントを作成および管理できます。Azure AD を使用するには、Azure portal にアクセスし、Office 365 アカウントを使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="f70b0-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f70b0-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="f70b0-107">Before you begin</span></span>

<span data-ttu-id="f70b0-p102">(通常のセッションではなく) プライベート ブラウジング セッションを使用して、Azure portal (以下の手順 1 参照) にアクセスします。これにより、現在のログオンに使用している資格情報が Azure に渡されません。プライベート ブラウジング セッションを開始するには:</span><span class="sxs-lookup"><span data-stu-id="f70b0-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this will prevent the credential that you are currently logged on with from being passed to Azure. To open an private browsing session:</span></span>

- <span data-ttu-id="f70b0-110">Microsoft Edge (レガシ バージョン)、Internet Explorer、または Mozilla FireFox では、`CTRL+SHIFT+P` を押します。</span><span class="sxs-lookup"><span data-stu-id="f70b0-110">In Microsoft Edge (legacy version), Internet Explorer, or Mozilla FireFox, press `CTRL+SHIFT+P`.</span></span>

- <span data-ttu-id="f70b0-111">Microsoft Edge (最新バージョン) または Google Chrome では、`CTRL+SHIFT+N` を押します。</span><span class="sxs-lookup"><span data-stu-id="f70b0-111">In Microsoft Edge (newest version) or Google Chrome, press `CTRL+SHIFT+N`.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="f70b0-112">Azure Active Directory にアクセスする</span><span class="sxs-lookup"><span data-stu-id="f70b0-112">Access Azure Active Directory</span></span>

1. <span data-ttu-id="f70b0-113">[portal.azure.com](https://portal.azure.com) にアクセスし、Office 365 の職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="f70b0-113">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="f70b0-114">Azure portal の左側のナビゲーション ウィンドウで **Azure Active Directory** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f70b0-114">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![Azure portal の左側のナビゲーション ウィンドウで [Azure Active Directory] をクリックします。](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="f70b0-116">**Azure Active Directory** 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f70b0-116">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="f70b0-117">More information</span><span class="sxs-lookup"><span data-stu-id="f70b0-117">More information</span></span>

- <span data-ttu-id="f70b0-118">無料の Azure Active Directory サブスクリプションには、サインイン アクティビティのレポートは含まれません。</span><span class="sxs-lookup"><span data-stu-id="f70b0-118">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="f70b0-119">(データ侵害が発生した場合に役立つ可能性がある) サインイン アクティビティを記録するには、Azure Active Directory Premium サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="f70b0-119">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="f70b0-120">詳細については、[Azure AD がデータを保存する期間](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f70b0-120">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="f70b0-121">Microsoft 365 管理センターから \*\* Azure Active Directory\*\* 管理センターにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f70b0-121">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f70b0-122">Microsoft 365 管理センターの左側のナビゲーションウィンドウで、[**管理センター**]、[\>\*\* Azure Active Directory\*\*] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f70b0-122">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="f70b0-123">ユーザーとグループの管理や、その他のディレクトリ管理タスクの実行の詳細については、「[Azure AD Directory の管理](https://docs.microsoft.com/azure/active-directory/active-directory-administer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f70b0-123">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
