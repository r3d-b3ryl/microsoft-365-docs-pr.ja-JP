---
title: ユーザーのアプリ起動ツールにアプリを固定する
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
description: グローバル管理者として、最大3つのアプリをユーザーのアプリ起動ツールにピン留めすることができます。
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310877"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="6541c-103">ユーザーのアプリ起動ツールにアプリを固定する</span><span class="sxs-lookup"><span data-stu-id="6541c-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="6541c-104">Azure Active Directory ポータルのコントロールを使用して、Office.com に最大3つのアプリと、組織内のすべてのユーザーのアプリ起動ツールをピン留めできます。</span><span class="sxs-lookup"><span data-stu-id="6541c-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="6541c-105">アプリケーションのグループを整理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6541c-105">You can also organize groups of applications.</span></span> <span data-ttu-id="6541c-106">追加したアプリは、いつでもユーザーが後で固定解除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6541c-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="6541c-107">ユーザーに対してアプリを固定するには、Cloud application administrator または Azure Active Directory のアプリケーション管理者、または Office 365 の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6541c-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="6541c-108">管理者の役割の詳細については、「 [Microsoft 365 の](../add-users/about-admin-roles.md)「 [Azure Active Directory の管理役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」と「管理者の役割」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6541c-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="6541c-109">アプリ起動ツールおよび Office.com の詳細については、「 [アプリ起動ツール](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) と [更新プログラムについて office.com」および「Office 365 アプリ起動ツール](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 」のブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6541c-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="6541c-110">Azure Active Directory ポータルを使用してアプリを固定する</span><span class="sxs-lookup"><span data-stu-id="6541c-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="6541c-111">Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。</span><span class="sxs-lookup"><span data-stu-id="6541c-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="6541c-112">左側のナビゲーションで [ **すべて表示**] を選択し、[ **管理センター**] の下の [ **Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6541c-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="6541c-113">[ **Azure Active Directory**] で、[**エンタープライズアプリケーション**  >  **ユーザー設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6541c-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="6541c-114">[ **Office 365 の設定** ] セクションで、[ **アプリケーションの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6541c-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="6541c-115">ユーザーのアプリ起動ツールにピン留めするアプリケーションを選択し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6541c-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="アプリを固定するための Microsoft 365 設定。":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="6541c-117">カスタムアプリを固定する</span><span class="sxs-lookup"><span data-stu-id="6541c-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="6541c-118">この機能を使用するには、追加の Azure AD ライセンスを購入する必要があるかどうかを示すユーザーインターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6541c-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="6541c-119">詳細については、「 [Azure Active Directory の料金](https://azure.microsoft.com/pricing/details/active-directory/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6541c-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="6541c-120">**Azure Active Directory**で、[すべての**Enterprise applications**  >  **アプリケーション**] ページの上部にある [エンタープライズアプリケーション**新しいアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6541c-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="6541c-121">[ **アプリケーションの追加** ] ページで、プレビュー版の Azure Active Directory を使用している場合は、[ **ギャラリー以外のアプリケーション** ] または [独自のアプリケーションを **作成** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6541c-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="6541c-122">アプリケーションの名前を入力し、[ユーザー **とグループ** ] タブでユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6541c-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="6541c-123">[ **プロパティ** ] タブを使用して、アプリのアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="6541c-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="6541c-124">アプリに URL を割り当てるには、[ **シングルサインオン** ] タブで、[ **リンク** ] を選択し、url を入力します。</span><span class="sxs-lookup"><span data-stu-id="6541c-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="6541c-125">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6541c-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="6541c-126">アプリケーションコレクションを作成する</span><span class="sxs-lookup"><span data-stu-id="6541c-126">Create application collections</span></span>

<span data-ttu-id="6541c-127">組織内のユーザーのアプリケーションコレクションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6541c-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="6541c-128">手順については、「 [Azure portal の個人用アプリポータルでコレクションを作成する](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6541c-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>