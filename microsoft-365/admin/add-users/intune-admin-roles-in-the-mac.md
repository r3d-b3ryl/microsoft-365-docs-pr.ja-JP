---
title: Microsoft 365管理センター の Intune 管理者の役割について
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 管理者ロールはビジネス機能にマップされ、管理センターで特定のタスクを実行するための権限を付与します。 たとえば、サービス管理者が Microsoft のサポート チケットを開きます。
ms.openlocfilehash: 48bb0f3d1a3a239025017fda261945094a3eda79
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126083"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a><span data-ttu-id="fb77f-104">Microsoft 365 管理センターにおける Intune 管理者の役割</span><span class="sxs-lookup"><span data-stu-id="fb77f-104">Intune admin roles in the Microsoft 365 admin center</span></span>

<span data-ttu-id="fb77f-105">Microsoft 365 または Office 365 サブスクリプションには、Microsoft 365 管理センターを使用して組織内のユーザーに割り当てることができる管理者ロールセットがあります。</span><span class="sxs-lookup"><span data-stu-id="fb77f-105">Your Microsoft 365 or Office 365 subscription comes with a set of admin roles that you can assign to users in your organization using the Microsoft 365 admin center.</span></span> <span data-ttu-id="fb77f-106">各管理者ロールは、一般的なビジネス機能にマップされ、組織内のユーザーに管理センターで特定のタスクを実行する許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-106">Each admin role maps to common business functions and gives people in your organization permissions to do specific tasks in the admin centers.</span></span>

<span data-ttu-id="fb77f-107">Microsoft 365 管理センターを使用すると、Microsoft Intune の役割を管理できます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-107">The Microsoft 365 admin center lets you manage some Microsoft Intune roles.</span></span> <span data-ttu-id="fb77f-108">ただし、これらの役割は、Intune 管理センターで使用可能な役割のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="fb77f-108">However, these roles are a subset of the roles available in the Intune admin center.</span></span> <span data-ttu-id="fb77f-109">Microsoft Intune の役割の詳細な説明をお探しですか ?</span><span class="sxs-lookup"><span data-stu-id="fb77f-109">Looking for the detailed role descriptions for Microsoft Intune?</span></span> <span data-ttu-id="fb77f-110">「[Microsoft Intune の役割ベースのアクセス制御 (RBAC)](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb77f-110">Check out [Role-based access control (RBAC) with Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span></span>

<span data-ttu-id="fb77f-111">Microsoft 365 管理センターでの役割を割り当てる方法の詳細については、「[管理者ロールを割り当てる](assign-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb77f-111">For more information on assigning roles in the Microsoft 365 admin center, see [Assign admin roles](assign-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="fb77f-112">Microsoft 365 管理センターで、[**役割**] に移動し、任意の役割を選択して詳細ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-112">In the Microsoft 365 admin center, you can go to **Roles**, and then select any role to open its detail pane.</span></span> <span data-ttu-id="fb77f-113">[**アクセス許可**] タブを選択して、実行する許可を持った役割を割り当てられた管理者についての詳細な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="fb77f-113">Select the **Permissions** tab to view the detailed list of what admins assigned that role have permissions to do.</span></span> <span data-ttu-id="fb77f-114">役割にユーザーを追加するには、**[割り当てられた]** または **[割り当てられた管理者]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="fb77f-114">Select the **Assigned** or **Assigned admins** tab to add users to roles.</span></span>

::: moniker-end

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a><span data-ttu-id="fb77f-115">Microsoft 365 管理センターで利用可能なMicrosoft Intune の役割</span><span class="sxs-lookup"><span data-stu-id="fb77f-115">Microsoft Intune Roles available in the Microsoft 365 admin center</span></span>

|<span data-ttu-id="fb77f-116">管理者ロール</span><span class="sxs-lookup"><span data-stu-id="fb77f-116">Admin role</span></span>     |<span data-ttu-id="fb77f-117">誰にこの役割を割り当てるか</span><span class="sxs-lookup"><span data-stu-id="fb77f-117">Who should be assigned this role?</span></span>  |
|---------|---------|
|<span data-ttu-id="fb77f-118">アプリケーション マネージャー</span><span class="sxs-lookup"><span data-stu-id="fb77f-118">Application manager</span></span>     |   <span data-ttu-id="fb77f-119">モバイルアプリのアプリケーションライフサイクルを管理し、ポリシーに管理されたアプリとビューのデバイス情報と構成プロファイルを表示するユーザーに、アプリケーション マネージャーの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-119">Assign the Application manager role to users who mangage the application lifecycle for mobile apps, configures policy-managed apps and views device info and configuration profiles.</span></span>  |
|<span data-ttu-id="fb77f-120">ヘルプデスク オペレーター</span><span class="sxs-lookup"><span data-stu-id="fb77f-120">Help desk operator</span></span>     |   <span data-ttu-id="fb77f-121">ユーザーとデバイスにアプリとポリシーを割り当てるユーザーに、ヘルプデスク オペレーターの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-121">Assign the help desk operator role to users who assign apps and policies to users and devices.</span></span> |
|<span data-ttu-id="fb77f-122">Intune の役割の管理者</span><span class="sxs-lookup"><span data-stu-id="fb77f-122">Intune role administrator</span></span>    |   <span data-ttu-id="fb77f-123">Intune の管理者を他の管理者に割り当てることができるユーザーに、Intune の役割を割り当てることができます。ユーザーは Intune の役割を管理できます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-123">Assign the Intune role administrator to users who can assign Intune permissions to other admins and can manage custom and built in Intune roles.</span></span>   |
|<span data-ttu-id="fb77f-124">ポリシーおよびプロファイル マネージャー</span><span class="sxs-lookup"><span data-stu-id="fb77f-124">Policy and profile manager</span></span>     |   <span data-ttu-id="fb77f-125">ポリシーおよびプロファイル マネージャーの役割をユーザーに割り当て	て、コンプライアンス ポリシーの管理、構成プロファイル、Apple の登録を行います。</span><span class="sxs-lookup"><span data-stu-id="fb77f-125">Assign the policy and profile manager role to users manage compliance policy, configuration profiles and Apple enrollment.</span></span>   |
|<span data-ttu-id="fb77f-126">読み取り専用の演算子</span><span class="sxs-lookup"><span data-stu-id="fb77f-126">Read only operator</span></span>     |   <span data-ttu-id="fb77f-127">ユーザー、デバイス、登録の詳細、構成の表示のみ可能なユーザーに読み取り専用オペレーターの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-127">Assign the read only operator role to users who can only view users, devices, enrollment details and configurations.</span></span>   |
|<span data-ttu-id="fb77f-128">学校の管理者</span><span class="sxs-lookup"><span data-stu-id="fb77f-128">School administrator</span></span>     |   <span data-ttu-id="fb77f-129">Intune for Education で Windows 10 と iOS デバイス、アプリ、および構成を管理するためのフルアクセス権をもつユーザーに学校の管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-129">Assign the school administrator role to users for full access to manage Windows 10 and iOS devices, apps and configurations in Intune for Education.</span></span>   |

## <a name="delegated-administration-for-microsoft-partners"></a><span data-ttu-id="fb77f-130">Microsoft パートナーの代理管理</span><span class="sxs-lookup"><span data-stu-id="fb77f-130">Delegated administration for Microsoft Partners</span></span>

<span data-ttu-id="fb77f-131">Microsoft パートナーと連携している場合、パートナーに管理者ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-131">If you're working with a Microsoft partner, you can assign them admin roles.</span></span> <span data-ttu-id="fb77f-132">次に、彼らはあなたの会社のユーザーまたはその会社の管理者ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-132">They, in turn, can assign users in your company - or their company - admin roles.</span></span> <span data-ttu-id="fb77f-133">たとえば、彼らがあなたのためにオンライン組織をセットアップし管理している場合、彼らにして欲しいのはこれかもしれません。</span><span class="sxs-lookup"><span data-stu-id="fb77f-133">You might want them to do this, for example, if they are setting up and managing your online organization for you.</span></span>
  
<span data-ttu-id="fb77f-134">パートナーは、次の役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-134">A partner can assign these roles:</span></span>
  
- <span data-ttu-id="fb77f-135">パートナー センターを介した多要素認証の管理を除いた、グローバル管理者と同等の特権を持つ完全な管理。</span><span class="sxs-lookup"><span data-stu-id="fb77f-135">Full administration, which has privileges equivalent to a global admin, with the exception of managing multi-factor authentication through the Partner Center.</span></span>

- <span data-ttu-id="fb77f-136">ヘルプデスク管理者と同等の特権を持つ制限付き管理。</span><span class="sxs-lookup"><span data-stu-id="fb77f-136">Limited administration, which has privileges equivalent to a helpdesk admin.</span></span>

<span data-ttu-id="fb77f-137">パートナーがこれらの役割をユーザーに割り当てる前に、パートナーを代理管理者としてアカウントに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb77f-137">Before the partner can assign these roles to users, you must add the partner as a delegated admin to your account.</span></span> <span data-ttu-id="fb77f-138">このプロセスは認定パートナーによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="fb77f-138">This process is initiated by an authorized partner.</span></span> <span data-ttu-id="fb77f-139">パートナーは管理者に電子メールを送信し、代理管理者となる権限を割り当てるかどうか質問します。手順については、「[パートナー リレーションシップの承認または削除](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb77f-139">The partner sends you an email to ask you if you want to give them permission to act as a delegated admin. For instructions, see [Authorize or remove partner relationships](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="fb77f-140">関連記事</span><span class="sxs-lookup"><span data-stu-id="fb77f-140">Related articles</span></span>

[<span data-ttu-id="fb77f-141">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="fb77f-141">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="fb77f-142">管理者の役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fb77f-142">Assign admin roles</span></span>](assign-admin-roles.md)

[<span data-ttu-id="fb77f-143">Microsoft 365 管理センターのアクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="fb77f-143">Activity reports in the Microsoft 365 admin center</span></span>](../activity-reports/activity-reports.md)