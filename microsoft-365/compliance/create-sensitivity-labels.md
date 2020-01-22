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
ms.openlocfilehash: 964fd20d6ada935d2a76ca0bffccc5bf46161c58
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247460"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="37418-103">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="37418-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="37418-104">[秘密度ラベル](sensitivity-labels.md)を作成して発行するには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)などラベル付けの管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="37418-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="37418-105">Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="37418-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="37418-106">まず、Office 用のアプリとサービスで使用する秘密度ラベルを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="37418-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="37418-107">次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="37418-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="37418-108">このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。</span><span class="sxs-lookup"><span data-stu-id="37418-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="37418-109">秘密度ラベルを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="37418-109">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="37418-110">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="37418-110">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="37418-111">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="37418-111">Microsoft 365 compliance center</span></span> 
        - <span data-ttu-id="37418-112">[**ソリューション**]  >  [**Information Protection (プレビュー)**]</span><span class="sxs-lookup"><span data-stu-id="37418-112">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="37418-113">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-113">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="37418-114">Microsoft 365 セキュリティ センター:</span><span class="sxs-lookup"><span data-stu-id="37418-114">Microsoft 365 security center</span></span> 
        - <span data-ttu-id="37418-115">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="37418-115">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="37418-116">Office 365 セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="37418-116">Office 365 Security & Compliance Center</span></span>
        - <span data-ttu-id="37418-117">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="37418-117">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="37418-118">[**ラベル**] タブで、[**+ ラベルの作成**] を選択して、[**新しい秘密度ラベル**] ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="37418-118">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="37418-119">ラベル設定の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="37418-119">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="37418-120">ラベル設定の詳細については、「概要」の「[秘密度ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-120">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="37418-121">さらにラベルを作成するには、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="37418-121">Repeat these steps to create more labels.</span></span> <span data-ttu-id="37418-122">ただし、サブ ラベルを作成する場合は、まず親ラベルを選択してから、[**その他のアクション**] の [**...**] を選択し、[**サブ ラベルの追加**] を選択ます。</span><span class="sxs-lookup"><span data-stu-id="37418-122">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="37418-123">必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="37418-123">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="37418-124">ラベルの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-124">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="37418-125">詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-125">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="37418-126">既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-126">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="37418-127">これにより、[**秘密度ラベルの編集**] ウィザードが起動し、手順 3 のすべてのラベル設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="37418-127">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="37418-128">ラベル ポリシーを使用して既に発行されているラベルを編集する場合、ウィザードを終了するときに、追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="37418-128">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="37418-129">たとえば、新しいラベル ポリシーに変更内容を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="37418-129">For example, you don't need to add it to a new label policy.</span></span> <span data-ttu-id="37418-130">ただし、変更をユーザーとサービスにレプリケートするには、最大で 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="37418-130">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="37418-131">ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="37418-131">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="37418-132">ラベルを発行するには、ラベルをラベル ポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37418-132">To publish the labels, they must be added to a label policy.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="37418-133">Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定</span><span class="sxs-lookup"><span data-stu-id="37418-133">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="37418-134">[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="37418-134">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="37418-135">たとえば、*LocaleSettings* パラメーターを使用して、ラベル名とヒントに別の言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="37418-135">For example, use the the *LocaleSettings* parameter to specify different languages for your label names and tooltips.</span></span> 

<span data-ttu-id="37418-136">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="37418-136">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="37418-137">この詳細設定には、ラベルが適用されたときのラベルの色の設定やカスタム プロパティの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="37418-137">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="37418-138">完全な一覧については、「[利用できるラベル ポリシーの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-138">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="37418-139">ラベル ポリシーを作成して秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="37418-139">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="37418-140">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="37418-140">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="37418-141">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="37418-141">Microsoft 365 compliance center</span></span> 
        - <span data-ttu-id="37418-142">[**ソリューション**]  >  [**Information Protection (プレビュー)**]</span><span class="sxs-lookup"><span data-stu-id="37418-142">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="37418-143">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-143">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="37418-144">Microsoft 365 セキュリティ センター:</span><span class="sxs-lookup"><span data-stu-id="37418-144">Microsoft 365 security center</span></span> 
        - <span data-ttu-id="37418-145">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="37418-145">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="37418-146">Office 365 セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="37418-146">Office 365 Security & Compliance Center</span></span>
        - <span data-ttu-id="37418-147">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="37418-147">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="37418-148">[**ラベル ポリシー**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-148">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="37418-149">[**ラベルの発行**] を選択し、[**ポリシーの作成] ウィザード**を起動します。</span><span class="sxs-lookup"><span data-stu-id="37418-149">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="37418-150">[**発行する秘密度ラベルの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37418-150">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="37418-151">アプリとサービスで使用するラベルを選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-151">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="37418-152">選択したラベルを確認し、変更する場合は [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-152">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="37418-153">それ以外の場合は、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-153">Otherwise select **Next**.</span></span>

6. <span data-ttu-id="37418-154">指示に従ってポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="37418-154">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="37418-155">設定の詳細については、「概要」の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-155">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="37418-156">異なるユーザーや場所に対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="37418-156">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="37418-157">たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="37418-157">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="37418-158">複数のラベル ポリシーを作成すると、ユーザーまたは場所の競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="37418-158">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="37418-159">ラベル ポリシーの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-159">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="37418-160">詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-160">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="37418-161">ウィザードを完了すると、ラベル ポリシーが自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="37418-161">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="37418-162">発行したポリシーは、簡単に編集して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="37418-162">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="37418-163">特定の発行や再発行のアクションを選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="37418-163">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="37418-164">既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、[**ポリシーの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37418-164">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="37418-165">これにより、[**ポリシーの作成**] ウィザードが起動し、含めるラベルとラベルの設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="37418-165">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="37418-166">ウィザードを完了すると、選択したユーザーとサービスに変更が自動的にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="37418-166">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="37418-167">通常、Office アプリのラベルは数時間以内にユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="37418-167">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="37418-168">ただし、ラベル ポリシーおよびそれらに対する変更を最大 24 時間使用して、すべてのユーザとサービスにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="37418-168">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="37418-169">Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="37418-169">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="37418-170">[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル ポリシー設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="37418-170">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="37418-171">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="37418-171">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="37418-172">この詳細設定には、Outlook 用の異なる既定ラベルが含まれています。また、送信メールの警告、両端揃え、ブロックを行うポップアップ メッセージを Outlook に実装しています。</span><span class="sxs-lookup"><span data-stu-id="37418-172">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="37418-173">完全な一覧については、「[利用できるラベルの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-173">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="37418-174">このコマンドレットを使用して、ラベル ポリシーへのラベルの追加や削除も可能です。</span><span class="sxs-lookup"><span data-stu-id="37418-174">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="37418-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="37418-175">Next steps</span></span>

<span data-ttu-id="37418-176">特定のシナリオで秘密度ラベルを構成して使用するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-176">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="37418-177">機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="37418-177">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="37418-178">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="37418-178">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="37418-179">チーム、グループ、およびサイトで機密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="37418-179">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="37418-180">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする</span><span class="sxs-lookup"><span data-stu-id="37418-180">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="37418-181">ラベルがどのように使われているかを監視するには、「[ラベル分析によるラベル使用状況の表示](label-analytics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37418-181">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>