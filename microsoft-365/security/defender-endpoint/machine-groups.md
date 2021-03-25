---
title: Microsoft Defender ATP でデバイス グループを作成および管理する
description: デバイス グループを作成し、グループに適用されるルールを混同して、デバイス グループに自動修復レベルを設定する
keywords: デバイス グループ、グループ、修復、レベル、ルール、aad グループ、役割、割り当て、ランク
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dfc7c04bbde2b7061c92f5a25115b75a2f5b47b5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066300"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="a53d8-104">デバイス グループの作成と管理</span><span class="sxs-lookup"><span data-stu-id="a53d8-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a53d8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a53d8-105">**Applies to:**</span></span>
- <span data-ttu-id="a53d8-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a53d8-106">Azure Active Directory</span></span>
- <span data-ttu-id="a53d8-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="a53d8-107">Office 365</span></span>

> <span data-ttu-id="a53d8-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a53d8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a53d8-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="a53d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="a53d8-110">エンタープライズ シナリオでは、通常、セキュリティ操作チームには一連のデバイスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="a53d8-111">これらのデバイスは、ドメイン、コンピューター名、指定されたタグなどの一連の属性に基づいてグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="a53d8-112">Microsoft Defender for Endpoint では、デバイス グループを作成し、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="a53d8-113">RBAC ロールが割り当てられている特定の Azure ADグループへのアクセス [を制限する](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="a53d8-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="a53d8-114">デバイスの異なるセットに対して異なる自動修復設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a53d8-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="a53d8-115">自動調査中に適用する特定の修復レベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a53d8-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="a53d8-116">調査では、グループ フィルターを使用 **して** 、[デバイス] リストを特定のデバイス グループに **フィルター処理** します。</span><span class="sxs-lookup"><span data-stu-id="a53d8-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="a53d8-117">役割ベースのアクセス (RBAC) のコンテキストでデバイス グループを作成して、デバイス グループをユーザー グループに割り当て、特定のアクションを実行したり情報を表示したりできるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="a53d8-118">詳細については、「役割ベースのアクセス [制御を使用してポータル アクセスを管理する」を参照してください](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="a53d8-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="a53d8-119">RBAC アプリケーションの包括的な外観については、「SOC は RBAC でフラット [に実行されていますか」を参照してください](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)。</span><span class="sxs-lookup"><span data-stu-id="a53d8-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="a53d8-120">デバイス グループの作成プロセスの一環として、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a53d8-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="a53d8-121">そのグループの自動修復レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a53d8-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="a53d8-122">修復レベルの詳細については、「自動化された調査を使用して脅威を調査および修復する」 [を参照してください](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="a53d8-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="a53d8-123">デバイス名、ドメイン、タグ、および OS プラットフォームに基づいてグループに属するデバイス グループを決定する一致ルールを指定します。</span><span class="sxs-lookup"><span data-stu-id="a53d8-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="a53d8-124">デバイスが他のグループにも一致する場合は、最もランクの高いデバイス グループにのみ追加されます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="a53d8-125">デバイス グループにADする必要がある Azure ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a53d8-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="a53d8-126">作成後、他のグループを基準にデバイス グループをランク付けします。</span><span class="sxs-lookup"><span data-stu-id="a53d8-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="a53d8-127">Azure グループを割り当てない場合は、すべてのユーザーがデバイス グループADアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="a53d8-128">デバイス グループの作成</span><span class="sxs-lookup"><span data-stu-id="a53d8-128">Create a device group</span></span>

1. <span data-ttu-id="a53d8-129">ナビゲーション ウィンドウで、[設定] [デバイス **グループ**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a53d8-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="a53d8-130">[デバイス **グループの追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a53d8-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="a53d8-131">グループ名とオートメーション設定を入力し、グループに属するデバイスを決定する一致ルールを指定します。</span><span class="sxs-lookup"><span data-stu-id="a53d8-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="a53d8-132">「 [自動調査の開始方法」を参照してください](automated-investigations.md#how-the-automated-investigation-starts)。</span><span class="sxs-lookup"><span data-stu-id="a53d8-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="a53d8-133">組織単位でデバイスをグループ化する場合は、グループ所属のレジストリ キーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="a53d8-134">デバイスタグ付けの詳細については、「デバイス タグの作成と [管理」を参照してください](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="a53d8-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="a53d8-135">このルールに一致する複数のデバイスをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="a53d8-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="a53d8-136">ルールに問題がなければ、[ユーザー アクセス] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="a53d8-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="a53d8-137">作成したデバイス グループにアクセスできるユーザー グループを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a53d8-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a53d8-138">RBAC ロールに割り当てられているユーザー AD Azure へのアクセスのみを許可できます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="a53d8-139">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a53d8-139">Click **Close**.</span></span> <span data-ttu-id="a53d8-140">構成の変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="a53d8-141">デバイス グループの管理</span><span class="sxs-lookup"><span data-stu-id="a53d8-141">Manage device groups</span></span>

<span data-ttu-id="a53d8-142">デバイス グループのランクを昇格または降格して、一致中に優先度を高くまたは低くすることができます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="a53d8-143">デバイスが複数のグループに一致すると、そのデバイスは最もランクの高いグループにのみ追加されます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="a53d8-144">グループを編集および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="a53d8-145">デバイス グループを削除すると、電子メール通知ルールに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a53d8-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="a53d8-146">電子メール通知ルールの下でデバイス グループが構成されている場合は、そのルールから削除されます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="a53d8-147">デバイス グループが電子メール通知用に構成されている唯一のグループである場合、その電子メール通知ルールはデバイス グループと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="a53d8-148">既定では、デバイス グループには、ポータル アクセス権を持つすべてのユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="a53d8-149">Azure ユーザー グループをデバイス グループに割り当AD既定の動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="a53d8-150">グループに一致しないデバイスは、グループ化されていないデバイス (既定) グループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="a53d8-151">このグループのランクを変更したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a53d8-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="a53d8-152">ただし、このグループの修復レベルを変更し、このグループにアクセスできる Azure ADグループを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a53d8-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="a53d8-153">デバイス グループ構成に変更を適用するには、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a53d8-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a53d8-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="a53d8-154">Related topics</span></span>

- [<span data-ttu-id="a53d8-155">役割ベースのアクセス制御を使用したポータル アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="a53d8-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="a53d8-156">デバイス タグの作成と管理</span><span class="sxs-lookup"><span data-stu-id="a53d8-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="a53d8-157">Graph API を使用してテナント デバイス グループのリストを取得する</span><span class="sxs-lookup"><span data-stu-id="a53d8-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
