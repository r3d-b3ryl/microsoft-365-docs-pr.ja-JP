---
title: 秘密度ラベルを作成して発行する
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 組織のドキュメントやメールを分類し、保護するための秘密度ラベルを作成、構成、発行する手順です。
ms.openlocfilehash: edcfcf5a4f4891e4e1159c4c42327e59ceb35449
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238404"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="53d3b-103">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="53d3b-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="53d3b-104">[秘密度ラベル](sensitivity-labels.md)を作成して発行するには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)などラベル付けの管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="53d3b-105">Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="53d3b-106">まず、Office 用のアプリとサービスで使用する秘密度ラベルを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="53d3b-107">次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="53d3b-108">このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="53d3b-109">秘密度ラベルを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="53d3b-109">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="53d3b-110">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-110">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="53d3b-111">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="53d3b-111">Microsoft 365 compliance center</span></span> 
        - <span data-ttu-id="53d3b-112">[**ソリューション**]  >  [**Information Protection (プレビュー)**]</span><span class="sxs-lookup"><span data-stu-id="53d3b-112">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="53d3b-113">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-113">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="53d3b-114">Microsoft 365 セキュリティ センター:</span><span class="sxs-lookup"><span data-stu-id="53d3b-114">Microsoft 365 security center</span></span> 
        - <span data-ttu-id="53d3b-115">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="53d3b-115">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="53d3b-116">Office 365 セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="53d3b-116">Office 365 Security & Compliance Center</span></span>
        - <span data-ttu-id="53d3b-117">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="53d3b-117">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="53d3b-118">[**ラベル**] タブで、[**+ ラベルの作成**] を選択して、[**新しい秘密度ラベル**] ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-118">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="53d3b-119">ラベル設定の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="53d3b-119">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="53d3b-120">ラベル設定の詳細については、「概要」の「[秘密度ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-120">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="53d3b-121">さらにラベルを作成するには、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-121">Repeat these steps to create more labels.</span></span> <span data-ttu-id="53d3b-122">ただし、サブ ラベルを作成する場合は、まず親ラベルを選択してから、[**その他のアクション**] の [**...**] を選択し、[**サブ ラベルの追加**] を選択ます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-122">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="53d3b-123">必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-123">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="53d3b-124">ラベルの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-124">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="53d3b-125">詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-125">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="53d3b-126">既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-126">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="53d3b-127">これにより、[**秘密度ラベルの編集**] ウィザードが起動し、手順 3 のすべてのラベル設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-127">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> <span data-ttu-id="53d3b-128">ラベル ポリシーを使用して既にラベルが発行されている場合は、追加の手順は必要ありませんが、変更がユーザーと場所にレプリケートされるまでに最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="53d3b-128">If the label is already published by using a label policy, no extra steps are needed, but allow up to 24 hours for the changes to replicate to users and locations.</span></span>

<span data-ttu-id="53d3b-129">ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="53d3b-129">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="53d3b-130">ラベルを発行するには、ラベルをラベル ポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53d3b-130">To publish the labels, they must be added to a label policy.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="53d3b-131">Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定</span><span class="sxs-lookup"><span data-stu-id="53d3b-131">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="53d3b-132">[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-132">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="53d3b-133">たとえば、*LocaleSettings* パラメーターを使用して、ラベル名とヒントに別の言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-133">For example, use the the *LocaleSettings* parameter to specify different languages for your label names and tooltips.</span></span> 

<span data-ttu-id="53d3b-134">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-134">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="53d3b-135">この詳細設定には、ラベルが適用されたときのラベルの色の設定やカスタム プロパティの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-135">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="53d3b-136">完全な一覧については、「[利用できるラベル ポリシーの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-136">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="53d3b-137">ラベル ポリシーを作成して秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="53d3b-137">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="53d3b-138">ラベル付けの管理センターで、[**分類**]  >  [**秘密度ラベル**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-138">In your labeling admin center, navigate to **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="53d3b-139">[**ラベル ポリシー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d3b-139">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="53d3b-140">[**ラベルの発行**] を選択し、[**ポリシーの作成] ウィザード**を起動します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-140">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="53d3b-141">[**発行する秘密度ラベルの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53d3b-141">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="53d3b-142">アプリとサービスで使用するラベルを選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-142">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="53d3b-143">選択したラベルを確認し、変更する場合は [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-143">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="53d3b-144">それ以外の場合は、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-144">Otherwise select **Next**.</span></span>

6. <span data-ttu-id="53d3b-145">指示に従ってポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-145">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="53d3b-146">設定の詳細については、「概要」の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-146">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="53d3b-147">異なるユーザーや場所に対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-147">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="53d3b-148">たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-148">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="53d3b-149">複数のラベル ポリシーを作成すると、ユーザーまたは場所の競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-149">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="53d3b-150">ラベル ポリシーの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-150">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="53d3b-151">詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-151">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="53d3b-152">ウィザードを完了すると、ラベル ポリシーが自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-152">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="53d3b-153">発行したポリシーは、簡単に編集して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-153">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="53d3b-154">特定の発行や再発行のアクションを選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="53d3b-154">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="53d3b-155">既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、[**ポリシーの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53d3b-155">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="53d3b-156">これにより、[**ポリシーの作成**] ウィザードが起動し、含めるラベルとラベルの設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-156">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="53d3b-157">ウィザードを完了すると、選択したユーザーと場所に変更が自動的にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-157">When you complete the wizard, any changes are automatically replicated to the selected users and locations.</span></span> <span data-ttu-id="53d3b-158">レプリケーションが完了するまでに最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="53d3b-158">Allow up to 24 hours for the replication to complete.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="53d3b-159">Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="53d3b-159">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="53d3b-160">[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル ポリシー設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-160">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="53d3b-161">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="53d3b-161">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="53d3b-162">この詳細設定には、Outlook 用の異なる既定ラベルが含まれています。また、送信メールの警告、両端揃え、ブロックを行うポップアップ メッセージを Outlook に実装しています。</span><span class="sxs-lookup"><span data-stu-id="53d3b-162">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="53d3b-163">完全な一覧については、「[利用できるラベルの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-163">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="53d3b-164">このコマンドレットを使用して、ラベル ポリシーへのラベルの追加や削除も可能です。</span><span class="sxs-lookup"><span data-stu-id="53d3b-164">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="53d3b-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="53d3b-165">Next steps</span></span>

<span data-ttu-id="53d3b-166">特定のシナリオで秘密度ラベルを構成して使用するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-166">To configure and use your sensitivity labels for specific scenarios, see the following articles:</span></span>

- [<span data-ttu-id="53d3b-167">機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="53d3b-167">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="53d3b-168">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="53d3b-168">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="53d3b-169">チーム、グループ、およびサイトで機密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="53d3b-169">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="53d3b-170">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする</span><span class="sxs-lookup"><span data-stu-id="53d3b-170">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="53d3b-171">ラベルがどのように使われているかを監視するには、「[ラベル分析によるラベル使用状況の表示](label-analytics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d3b-171">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>