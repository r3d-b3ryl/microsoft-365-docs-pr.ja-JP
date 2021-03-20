---
title: ユーザーのアプリ 起動ツールにアプリをピン留めする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: グローバル管理者は、ユーザーのアプリ 起動ツールに最大 3 つのアプリをピン留めできます。
ms.openlocfilehash: 965fcbbb3f0e22074e3f6c5476d65ade98fea94c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915220"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="d8977-103">ユーザーのアプリ 起動ツールにアプリをピン留めする</span><span class="sxs-lookup"><span data-stu-id="d8977-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="d8977-104">Azure Active Directory ポータルのコントロールを使用すると、最大 3 つのアプリをピン留 Office.com、組織内のすべてのユーザーに対してアプリ 起動ツールを固定できます。</span><span class="sxs-lookup"><span data-stu-id="d8977-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="d8977-105">アプリケーションのグループを整理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8977-105">You can also organize groups of applications.</span></span> <span data-ttu-id="d8977-106">後で追加したアプリは、いつでもユーザーによって固定解除できます。</span><span class="sxs-lookup"><span data-stu-id="d8977-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="d8977-107">ユーザー用にアプリをピン留めするには、クラウド アプリケーション管理者、または Azure Active Directory のアプリケーション管理者、または 365 のグローバル管理者Office必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8977-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="d8977-108">管理者ロールの詳細については [、「Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) の管理者ロール」および [「Microsoft 365 の管理者ロール」を参照してください](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d8977-108">For more information about admin roles, see [admin roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="d8977-109">アプリ 起動ツールとアプリ 起動ツールの詳細 Office.com、[](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)アプリ 起動ツールと office.com および[Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)アプリ 起動ツールのブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8977-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="d8977-110">Azure Active Directory ポータルを使用してアプリをピン留めする</span><span class="sxs-lookup"><span data-stu-id="d8977-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="d8977-111">で Microsoft 365 管理センターに移動します <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="d8977-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="d8977-112">左側のナビゲーションで、[すべて表示] **を** 選択し、[ **管理** センター] で **[Azure Active Directory] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8977-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d8977-113">**Azure Active Directory で、[** エンタープライズ アプリケーション] **[ユーザー設定**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8977-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="d8977-114">**[365 Office] セクションで、[** アプリケーションの追加]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8977-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="d8977-115">ユーザーのアプリ 起動ツールにピン留めするアプリケーションを選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8977-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="アプリをピン留めする Microsoft 365 の設定。":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="d8977-117">カスタム アプリのピン留め</span><span class="sxs-lookup"><span data-stu-id="d8977-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="d8977-118">ユーザー インターフェイスは、この機能を使用するために追加の Azure ADを購入する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d8977-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="d8977-119">詳細については [、「Azure Active Directory の価格」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="d8977-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="d8977-120">**Azure Active Directory で、[** すべてのアプリケーション]**ページ** の上部にある [エンタープライズ アプリケーション] [新  >  **しいアプリケーション] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d8977-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="d8977-121">[アプリケーションの **追加] ページ** で、[ギャラリー以外のアプリケーション] または [独自のアプリケーションを作成する] を選択します (プレビュー バージョンの Azure Active Directory を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="d8977-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="d8977-122">アプリケーションの名前を入力し、[ユーザーとグループ] タブで **ユーザーを割り当** てる。</span><span class="sxs-lookup"><span data-stu-id="d8977-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="d8977-123">[プロパティ **] タブ** を使用して、アプリのアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d8977-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="d8977-124">アプリに URL を割り当てるには、[シングル サインオン]タブで[リンク] を選択し、URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8977-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="d8977-125">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8977-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="d8977-126">アプリケーション コレクションの作成</span><span class="sxs-lookup"><span data-stu-id="d8977-126">Create application collections</span></span>

<span data-ttu-id="d8977-127">また、組織内のユーザーのアプリケーション コレクションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8977-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="d8977-128">手順については、「Azure portal の My Apps ポータルでコレクションを作成 [する」を参照してください](/azure/active-directory/manage-apps/access-panel-collections)。</span><span class="sxs-lookup"><span data-stu-id="d8977-128">For instructions, see [create collections on the My Apps portal in the Azure portal](/azure/active-directory/manage-apps/access-panel-collections).</span></span>