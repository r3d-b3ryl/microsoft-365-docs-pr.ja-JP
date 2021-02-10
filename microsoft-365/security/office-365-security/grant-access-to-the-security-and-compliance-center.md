---
title: ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーは、Microsoft 365 セキュリティ/コンプライアンス センターでアクセス許可を割り当&、セキュリティまたはコンプライアンス機能を管理する必要があります。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9e19825ce0f8224b2aee8e1419ef5d1ad425aadb
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165417"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="c4fb0-103">ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="c4fb0-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c4fb0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c4fb0-104">**Applies to**</span></span>
- [<span data-ttu-id="c4fb0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c4fb0-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c4fb0-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c4fb0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c4fb0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4fb0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c4fb0-108">ユーザーは、セキュリティまたはコンプライアンス機能を管理する前&セキュリティ/コンプライアンス センターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="c4fb0-109">セキュリティ & コンプライアンス センターのグローバル管理者または OrganizationManagement 役割グループのメンバーは、これらのアクセス許可をユーザーに付与できます。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="c4fb0-110">ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="c4fb0-111">セキュリティ & コンプライアンス センターでユーザーに付与できるさまざまなアクセス許可の詳細については、セキュリティ/コンプライアンス センターでアクセス許可 [&確認してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c4fb0-112">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c4fb0-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c4fb0-113">この記事の手順を完了するには、グローバル管理者、またはセキュリティ & コンプライアンス センターの OrganizationManagement 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="c4fb0-114">セキュリティ/コンプライアンス センター&グループの名前は Exchange Online の役割グループと似ていますが、同じではありません。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="c4fb0-115">役割グループのメンバーシップは、Exchange Online とセキュリティ/コンプライアンス センター&共有されます。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="c4fb0-116">代理アクセス許可 (DAP) パートナーが代理管理 (AOBO) アクセス許可を持つ場合、セキュリティ/コンプライアンス センター&できません。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="c4fb0-117">セキュリティ/コンプライアンス センター&使用して、別のユーザーにセキュリティ/コンプライアンス センターへのアクセス&与える</span><span class="sxs-lookup"><span data-stu-id="c4fb0-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="c4fb0-118">セキュリティ/コンプライアンス センター&開き、[ <https://protection.office.com> アクセス許可] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="c4fb0-119">[アクセス許可] タブに **直接移動するには** 、開きます <https://protection.office.com/permissions> 。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="c4fb0-120">役割グループの一覧から役割グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="c4fb0-121">役割グループのプロパティ ページの **[メンバー**]で、[追加] アイコンをクリックし、追加するユーザー ![ の名前 ](../../media/ITPro-EAC-AddIcon.gif) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="c4fb0-122">役割グループに追加するユーザー **\>** を選択したら、[追加] をクリックし **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="c4fb0-123">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="c4fb0-124">セキュリティ/コンプライアンス & PowerShell を使用して、別のユーザーにセキュリティ/コンプライアンス センターへのアクセス&与える</span><span class="sxs-lookup"><span data-stu-id="c4fb0-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="c4fb0-125">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-125">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c4fb0-126">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="c4fb0-127">構文およびパラメーターの詳細については[、「Add-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c4fb0-128">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c4fb0-128">How do you know this worked?</span></span>

<span data-ttu-id="c4fb0-129">セキュリティ センター コンプライアンス センターへのアクセスが正常に許可されたことを確認&、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="c4fb0-130">セキュリティ/コンプライアンス センター&アクセス許可に移動し、役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="c4fb0-131">開く詳細フライアウトで、役割グループのメンバーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="c4fb0-132">セキュリティ センター & コンプライアンス センターの PowerShell で、役割グループの名前に置き換え、次 \<RoleGroupName\> のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="c4fb0-133">構文およびパラメーターの詳細については [、「Get-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="c4fb0-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
