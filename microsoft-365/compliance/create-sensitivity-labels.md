---
title: 秘密度ラベルを作成して発行する
f1.keywords:
- NOCSH
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
description: 'すべての Microsoft Information Protection ソリューションの要件: 組織のデータを分類し、保護するための秘密度ラベルを作成、構成、発行します。'
ms.openlocfilehash: fc7debbe2fe1d59d4d172fd23587d0b2a1e6705e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244626"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="a4d8d-103">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="a4d8d-103">Create and configure sensitivity labels and their policies</span></span>

><span data-ttu-id="a4d8d-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="a4d8d-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="a4d8d-105">すべての Microsoft Information Protection ソリューション (MIP と略されることもあります) は、[秘密度ラベル](sensitivity-labels.md)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-105">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="a4d8d-106">それらのラベルを作成して発行するには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-106">To create and publish these labels, go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="a4d8d-107">または以前のポータルである Office 365 セキュリティ/コンプライアンス センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-107">You can also use the older portal, Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="a4d8d-108">まず、アプリやその他のサービスで使用する秘密度ラベルを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-108">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="a4d8d-109">たとえば、ユーザーに表示して Office アプリから適用するラベルです。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-109">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="a4d8d-110">次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-110">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="a4d8d-111">このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-111">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a4d8d-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="a4d8d-112">Before you begin</span></span>

<span data-ttu-id="a4d8d-113">組織のグローバル管理者には、秘密度ラベルのすべての側面を作成および管理するための完全な権限があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-113">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="a4d8d-114">グローバル管理者としてサインインしていない場合は、「[機密ラベルの作成と管理に必要なアクセス許可](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-114">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="a4d8d-115">秘密度ラベルを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="a4d8d-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="a4d8d-116">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-116">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="a4d8d-117">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="a4d8d-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="a4d8d-118">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="a4d8d-118">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="a4d8d-119">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-119">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="a4d8d-120">セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="a4d8d-120">Security & Compliance Center:</span></span>
        - <span data-ttu-id="a4d8d-121">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="a4d8d-121">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="a4d8d-122">[**ラベル**] ページで、[**+ ラベルの作成**] を選択して、[新しい秘密度ラベル] ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-122">On the **Labels** page, select **+ Create a label** to start the New sensitivity label wizard.</span></span> 
    
    <span data-ttu-id="a4d8d-123">たとえば、Microsoft 365 コンプライアンス センターでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-123">For example, from the Microsoft 365 compliance center:</span></span>
    
    ![秘密度ラベルを作成する](../media/create-sensitivity-label-full.png)
    
    > [!NOTE]
    > <span data-ttu-id="a4d8d-125">既定では、テナントにはラベルはありません。作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-125">By default, tenants don't have any labels and you must create them.</span></span> <span data-ttu-id="a4d8d-126">こちらに例示した図のラベルには、[Azure Information Protection から移行](/azure/information-protection/configure-policy-migrate-labels) された既定のラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-126">The labels in the example picture show default labels that were [migrated from Azure Information Protection](/azure/information-protection/configure-policy-migrate-labels).</span></span>

3. <span data-ttu-id="a4d8d-127">**[このラベルのスコープを定義する]** ページで、選択したオプションによって、構成できる設定のラベルのスコープと、公開時に表示される場所が決まります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-127">On the **Define the scope for this label** page, the options selected determine the label's scope for the settings that you can configure and where they will be visible when they are published:</span></span>
    
    ![機密度ラベルのスコープ](../media/sensitivity-labels-scopes.png)
    
    - <span data-ttu-id="a4d8d-129">**[ファイルとメール]** が選択されている場合、このウィザードで、Office Word や Outlook などの機密度ラベルをサポートするアプリに適用される設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-129">If **Files & emails** is selected, you can configure settings in this wizard that apply to apps that support sensitivity labels, such as Office Word and Outlook.</span></span> <span data-ttu-id="a4d8d-130">このオプションが選択されていない場合、ウィザードはこれらの設定の最初のページを表示しますが、それらを構成することはできず、ユーザーがこれらのアプリでラベルを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-130">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select in these apps.</span></span>
    
    - <span data-ttu-id="a4d8d-131">**[グループとサイト]** が選択されている場合、このウィザードで、Microsoft 365 グループ、および Teams と SharePoint のサイトに適用される設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-131">If **Groups & sites** is selected, you can configure settings in this wizard that apply to Microsoft 365 groups, and sites for Teams and SharePoint.</span></span> <span data-ttu-id="a4d8d-132">このオプションが選択されていない場合、ウィザードはこれらの設定の最初のページを表示しますが、それらを構成することはできず、ユーザーがグループおよびサイト用にラベルを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-132">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select for groups and site.</span></span>
    
    <span data-ttu-id="a4d8d-133">**Azure Purview assets (プレビュー)** スコープの詳細については、「[Azure Purview のコンテンツに自動的にラベルを付ける](/azure/purview/create-sensitivity-label)」を参照 してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-133">For information about the **Azure Purview assets (preview)** scope, see [Automatically label your content in Azure Purview](/azure/purview/create-sensitivity-label).</span></span>

4. <span data-ttu-id="a4d8d-134">ウィザードで、ラベル設定の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-134">Follow the prompts in the wizard for the label settings.</span></span>
    
    <span data-ttu-id="a4d8d-135">ラベル設定の詳細については、「概要」の「[秘密度ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。また、個々の設定については、ウィザードのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-135">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>

5. <span data-ttu-id="a4d8d-136">さらにラベルを作成するには、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-136">Repeat these steps to create more labels.</span></span> <span data-ttu-id="a4d8d-137">ただし、サブ ラベルを作成する場合は、まず親ラベルを選択してから、[**その他のアクション**] の [**...**] を選択し、[**サブ ラベルの追加**] を選択ます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-137">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

6. <span data-ttu-id="a4d8d-138">必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-138">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="a4d8d-139">ラベルの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-139">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="a4d8d-140">詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-140">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="a4d8d-141">既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-141">To edit an existing label, select it, and then select the **Edit label** button:</span></span>

![[ラベルの編集] ボタンを押して、秘密度ラベルを編集する](../media/edit-sensitivity-label-full.png)

<span data-ttu-id="a4d8d-143">このボタンを選択すると、[**秘密度ラベルの編集**] ウィザードが起動し、手順 4 のすべてのラベル設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-143">This button starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 4.</span></span>

<span data-ttu-id="a4d8d-144">ユーザーへの影響がどの程度かわからない場合は、ラベルを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-144">Don't delete a label unless you understand the impact for users.</span></span> <span data-ttu-id="a4d8d-145">詳細については、「[ラベルの解除と削除](#removing-and-deleting-labels)」 のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-145">For more information, see the [Removing and deleting labels](#removing-and-deleting-labels) section.</span></span> 

> [!NOTE]
> <span data-ttu-id="a4d8d-146">ラベル ポリシーを使用して既に発行されているラベルを編集する場合、ウィザードを終了するときに、追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-146">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="a4d8d-147">たとえば、同じユーザーに変更を反映させるために、ラベルを新しいラベル ポリシーに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-147">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="a4d8d-148">ただし、変更をすべてのアプリとサービスにレプリケートするには、最大で 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-148">However, allow up to 24 hours for the changes to replicate to all apps and services.</span></span>

<span data-ttu-id="a4d8d-149">ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-149">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="a4d8d-150">ラベルを発行するには、ラベルを[ラベル ポリシーに追加](#publish-sensitivity-labels-by-creating-a-label-policy)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-150">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4d8d-151">この [**ラベル**] タブで、新しいラベル ポリシーを作成する必要がある場合を除き、[**ラベルの発行**] タブ (またはラベル編集時の [**ラベルの発行**] ボタン) を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-151">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="a4d8d-152">複数のラベル ポリシーが必要になるのは、ユーザーが異なるラベルまたは異なるポリシー設定を必要とする場合だけです。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-152">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="a4d8d-153">ラベルポリシーをできるだけ少なくすることを目指してください。組織のラベルポリシーを1つだけにすることも珍しくありません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-153">Aim to have as few label policies as possible—it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="a4d8d-154">セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定</span><span class="sxs-lookup"><span data-stu-id="a4d8d-154">Additional label settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="a4d8d-155">[セキュリティ/コンプライアンス センターの PowerShell](/powershell/exchange/scc-powershell) の [Set-Label](/powershell/module/exchange/set-label) コマンドレットを使ってその他のラベル設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-155">Additional label settings are available with the [Set-Label](/powershell/module/exchange/set-label) cmdlet from [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="a4d8d-156">例として以下のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-156">For example:</span></span>

- <span data-ttu-id="a4d8d-157">ユーザーがローカル言語でラベル名とヒントを表示できるように、多国籍の展開では *LocaleSettings* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-157">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="a4d8d-158">[次のセクション](#example-configuration-to-configure-a-sensitivity-label-for-different-languages)には、フランス語、イタリア語、ドイツ語のラベル名とヒントのテキストを指定する設定例があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-158">The [following section](#example-configuration-to-configure-a-sensitivity-label-for-different-languages) has an example configuration that specifies the label name and tooltip text for French, Italian, and German.</span></span>

- <span data-ttu-id="a4d8d-159">Azure Information Protection 統合ラベリング クライアントの場合のみ、ラベルの色の設定やラベルが適用されたときにカスタムプロパティを適用するなどの[詳細設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-159">For the Azure Information Protection unified labeling client only, specify [advanced settings](/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="a4d8d-160">完全なリストについては、このクライアントの管理ガイドの「[利用できるラベルの詳細設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-160">For the full list, see [Available advanced settings for labels](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels) from this client's admin guide.</span></span>

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="a4d8d-161">異なる言語向けに機密ラベルを構成する構成例</span><span class="sxs-lookup"><span data-stu-id="a4d8d-161">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="a4d8d-162">次の例では、ヒント用のプレースホルダー テキストが含まれる "Public" という名前のラベルの PowerShell 構成を示します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-162">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="a4d8d-163">この例では、ラベル名とヒントのテキストがフランス語、イタリア語、ドイツ語用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-163">In this example, the label name and tooltip text are configured for French, Italian, and German.</span></span>

<span data-ttu-id="a4d8d-164">この構成の結果、これらの表示言語を使用する Office アプリを所有するユーザーには、ラベル名とツールヒントが同じ言語で表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-164">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="a4d8d-165">同様に、ファイルへのラベル付けをエクスプローラーから行うために Azure Information Protection 統一ラベル付けクライアントがインストールされている場合、これらの言語バージョンの Windows を所有しているユーザーがラベル付けのために右クリック アクションを使用すると、ラベル名とツールヒントがローカル言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-165">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="a4d8d-166">サポートする必要がある言語については、Office の[言語識別子](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (言語タグとも呼ばれます) を使用して、ラベル名とツールヒントの独自の翻訳を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-166">For the languages that you need to support, use the Office [language identifiers](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="a4d8d-167">PowerShell でコマンドを実行する前に、最初に[セキュリティ/コンプライアンス センターの PowerShell に接続](/powershell/exchange/connect-to-scc-powershell)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-167">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="a4d8d-168">ラベル ポリシーを作成して秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="a4d8d-168">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="a4d8d-169">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-169">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="a4d8d-170">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="a4d8d-170">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="a4d8d-171">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="a4d8d-171">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="a4d8d-172">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-172">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="a4d8d-173">セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="a4d8d-173">Security & Compliance Center:</span></span>
        - <span data-ttu-id="a4d8d-174">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="a4d8d-174">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="a4d8d-175">[**ラベル ポリシー**] タブ、[**ラベルの発行**] の順に選択して、ポリシー ウィザードの作成を開始してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-175">Select the **Label policies** tab, and then **Publish labels** to start the Create policy wizard:</span></span>
    
    <span data-ttu-id="a4d8d-176">たとえば、Microsoft 365 コンプライアンス センターでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-176">For example, from the Microsoft 365 compliance center:</span></span>
        
    ![ラベルを発行](../media/publish-sensitivity-labels-full.png)
    
    > [!NOTE]
    > <span data-ttu-id="a4d8d-178">既定では、テナントにはラベル ポリシーはありません。作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-178">By default, tenants don't have any label policies and you must create them.</span></span> 

3. <span data-ttu-id="a4d8d-179">ウィザードで、[**発行する秘密度ラベルの選択**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-179">In the wizard, select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="a4d8d-180">アプリとサービスで使用するラベルを選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-180">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a4d8d-181">サブラベルを選択する場合は、必ず親ラベルも選択してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-181">If you select a sublabel, make sure you also select its parent label.</span></span>
    
4. <span data-ttu-id="a4d8d-182">選択したラベルを確認し、変更する場合は [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-182">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="a4d8d-183">それ以外の場合は、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-183">Otherwise, select **Next**.</span></span>

5. <span data-ttu-id="a4d8d-184">指示に従ってポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-184">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="a4d8d-185">表示されるポリシー設定は、選択したラベルのスコープと一致します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-185">The policy settings that you see match the scope of the labels that you selected.</span></span> <span data-ttu-id="a4d8d-186">たとえば、**[ファイルとメール]** のスコープのみを持つラベルを選択した場合、ポリシー設定 **[このラベルを既定でグループとサイトに適用する]** および **[ユーザーにグループやサイトにラベルを付けるように要求する]** は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-186">For example, if you selected labels that have just the **Files & emails** scope, you don't see the policy settings **Apply this label by default to groups and sites** and **Require users to apply a label to their groups and sites**.</span></span>
    
    <span data-ttu-id="a4d8d-187">これらの設定の詳細については、概要情報の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。また、個々の設定については、ウィザードのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-187">For more information about these settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>
    
    <span data-ttu-id="a4d8d-188">**Azure Purview assets (プレビュー) に構成されているラベルの場合**: これらのラベルには関連付けられたポリシー設定はありません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-188">For labels configured for **Azure Purview assets (preview)**: These labels don't have any associated policy settings.</span></span>

7. <span data-ttu-id="a4d8d-189">異なるユーザーやスコープに対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-189">Repeat these steps if you need different policy settings for different users or scopes.</span></span> <span data-ttu-id="a4d8d-190">たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-190">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span> <span data-ttu-id="a4d8d-191">または、異なるスコープを持つようにラベルを構成した場合です。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-191">Or, if you have configured labels to have different scopes.</span></span>

8. <span data-ttu-id="a4d8d-192">複数のラベル ポリシーを作成すると、ユーザーの競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-192">If you create more than one label policy that might result in a conflict for a user, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="a4d8d-193">ラベル ポリシーの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-193">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="a4d8d-194">詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-194">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="a4d8d-195">ウィザードを完了すると、ラベル ポリシーが自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-195">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="a4d8d-196">発行したポリシーは、簡単に編集して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-196">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="a4d8d-197">特定の発行や再発行のアクションを選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-197">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="a4d8d-198">既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、[**ポリシーの編集**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-198">To edit an existing label policy, select it, and then select the **Edit Policy** button:</span></span> 

![秘密度ラベルを編集する](../media/edit-sensitivity-label-policy-full.png)

<span data-ttu-id="a4d8d-200">このボタンを選択すると、[**ポリシーの作成**] ウィザードが起動し、含めるラベルとラベルの設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-200">This button starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="a4d8d-201">ウィザードを完了すると、選択したユーザーとサービスに変更が自動的にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-201">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="a4d8d-p125">Windows、macOS、iOS、Android の Office アプリに組み込みのラベル付けを使用すると、ユーザーには 4 時間以内に新しいラベルが表示されます。web 上のWord、Excel、PowerPoint の場合は更新を行ってから 1 時間以内に新しいラベルが表示されます。ただし、変更がすべてのアプリとサービスに複製されるまでに最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-p125">When you use built-in labeling for Office apps on Windows, macOS, iOS, and Android, users see new labels within four hours, and within one hour for Word, Excel, and PowerPoint on the web when you refresh the browser. However, allow up to 24 hours for changes to replicate to all apps and services.</span></span>

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="a4d8d-204">セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="a4d8d-204">Additional label policy settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="a4d8d-205">[セキュリティ/コンプライアンス センター](/powershell/exchange/scc-powershell) PowerShell の [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) コマンドレットを使用すると、追加のラベルポリシー設定を利用できます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-205">Additional label policy settings are available with the [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) cmdlet from [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="a4d8d-206">Azure Information Protection の統合ラベル付けクライアントは、他のラベリング ソリューションからの移行や、送信されるメールを警告、正当化、またはブロックする Outlook のポップアップ メッセージなど、多くの[詳細設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-206">The Azure Information Protection unified labeling client supports many [advanced settings](/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include migrating from other labeling solutions, and pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="a4d8d-207">完全なリストについては、このクライアントの管理ガイドの [[利用できるラベルの詳細設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-207">For the full list, see [Available advanced settings for label policies](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies) from this client's admin guide.</span></span>

## <a name="use-powershell-for-sensitivity-labels-and-their-policies"></a><span data-ttu-id="a4d8d-208">機密ラベルとそのポリシーに PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="a4d8d-208">Use PowerShell for sensitivity labels and their policies</span></span>

<span data-ttu-id="a4d8d-209">[セキュリティ / コンプライアンスセンター PowerShell](/powershell/exchange/scc-powershell) を使用して、ラベル管理センターに表示されるすべての設定を作成し、構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-209">You can now use [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell) to create and configure all the settings you see in your labeling admin center.</span></span> <span data-ttu-id="a4d8d-210">つまり、ラベル管理センターでは使用できない設定に PowerShell を使用することに加えて、機密ラベルと機密ラベルポリシーの作成とメンテナンスを完全にスクリプト化できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-210">This means that in addition to using PowerShell for settings that aren't available in the labeling admin centers, you can now fully script the creation and maintenance of sensitivity labels and sensitivity label policies.</span></span> 

<span data-ttu-id="a4d8d-211">サポートされるパラメーターと値については、次のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-211">See the following documentation for supported parameters and values:</span></span>

- [<span data-ttu-id="a4d8d-212">New-Label</span><span class="sxs-lookup"><span data-stu-id="a4d8d-212">New-Label</span></span>](/powershell/module/exchange/new-label)
- [<span data-ttu-id="a4d8d-213">New-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="a4d8d-213">New-LabelPolicy</span></span>](/powershell/module/exchange/new-labelpolicy)
- [<span data-ttu-id="a4d8d-214">Set-Label</span><span class="sxs-lookup"><span data-stu-id="a4d8d-214">Set-Label</span></span>](/powershell/module/exchange/set-label)
- [<span data-ttu-id="a4d8d-215">Set-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="a4d8d-215">Set-LabelPolicy</span></span>](/powershell/module/exchange/set-labelpolicy)

<span data-ttu-id="a4d8d-216">機密ラベルまたは機密ラベルポリシーの削除をスクリプト化する必要がある場合は、 [Remove-Label](/powershell/module/exchange/remove-label) および [Remove-LabelPolicy](/powershell/module/exchange/remove-labelpolicy) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-216">You can also use [Remove-Label](/powershell/module/exchange/remove-label) and [Remove-LabelPolicy](/powershell/module/exchange/remove-labelpolicy) if you need to script the deletion of sensitivity labels or sensitivity label policies.</span></span> <span data-ttu-id="a4d8d-217">ただし、機密ラベルを削除する前に、次のセクションを必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-217">However, before you delete sensitivity labels, make sure you read the following section.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="a4d8d-218">ラベルの解除と削除</span><span class="sxs-lookup"><span data-stu-id="a4d8d-218">Removing and deleting labels</span></span>

<span data-ttu-id="a4d8d-219">運用環境では、通常、ラベル ポリシーから秘密度ラベルを解除したり、秘密度ラベルを削除したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-219">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="a4d8d-220">テストの初期段階では、そのいずれかまたは両方の操作を行う必要が発生する可能性が高いかもしれません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-220">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="a4d8d-221">それらの操作を行った場合、何が起こるかをよく理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-221">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="a4d8d-222">ラベル ポリシーからのラベルの解除は、削除に比べてリスクが少なく、必要に応じて後でいつでもラベル ポリシーに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-222">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="a4d8d-223">ラベル ポリシーからラベルを解除して当初指定したユーザーにラベルが発行されないようになった場合、次にラベル ポリシーが更新されるときに、そのラベルは Office アプリの選択対象としてユーザーに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-223">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="a4d8d-224">ただし、ラベルがドキュメントやメールに適用されている場合は、そのコンテンツからはラベルは解除されません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-224">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="a4d8d-225">ラベルによって適用された暗号化があればそのまま残り、基となる保護テンプレートは発行済のまま維持されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-225">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="a4d8d-226">解除されたラベルが、以前にコンテンツに適用されていた場合、Word、Excel、PowerPoint の組み込みラベルを使っているユーザーに対しては、適用されたラベルは引き続きステータス バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-226">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="a4d8d-227">同様に、SharePoint サイトに適用されている解除済みのラベルも **秘密度** 列のラベル名に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-227">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="a4d8d-228">これに対して、ラベルを削除した場合は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="a4d8d-228">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="a4d8d-229">ラベルが暗号化を適用している場合、以前に保護したコンテンツを引き続き開けるようにするため、基になる保護テンプレートはアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-229">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="a4d8d-230">これはアーカイブされた保護テンプレートなので、新しいラベルを同じ名前で作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-230">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="a4d8d-231">[PowerShell](/powershell/module/aipservice/remove-aipservicetemplate) を使って保護テンプレートを削除することはできますが、アーカイブしたテンプレートを使用して暗号化されたコンテンツを開く必要がないことが確実な場合を除いて、この操作は実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-231">Although it's possible to delete a protection template by using [PowerShell](/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="a4d8d-232">デスクトップ アプリの場合: メタデータのラベル情報は残りますが、名前のマッピングに使うラベル ID は利用できなくなっているため、適用されたラベル名は表示されず (ステータス バーなどに)、これによりユーザーはコンテンツはラベル付けされていないと判断します。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-232">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="a4d8d-233">ラベルが暗号化を行っている場合、暗号化はそのまま行われ、コンテンツが開かれると、既にアーカイブされている保護テンプレートの名前と説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-233">If the label applied encryption, the encryption remains and when the content is opened, users still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="a4d8d-234">Office on the web の場合: ステータス バーまたは **秘密度** 列にラベル名は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-234">For Office on the web: Users don't see the label name on the status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="a4d8d-235">ラベルが暗号化を適用していない場合にのみ、メタデータのラベル情報はそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-235">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="a4d8d-236">ラベルが暗号化を適用していて、[SharePoint と OneDrive の秘密度ラベル](sensitivity-labels-sharepoint-onedrive-files.md)が有効になっている場合、メタデータのラベル情報は削除され、暗号化は解除されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-236">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

<span data-ttu-id="a4d8d-237">ラベルポリシーから秘密度ラベルを削除したり、秘密度ラベルを削除したりすると、これらの変更がすべてのユーザーとサービスに複製されるまでに最大 24 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-237">When you remove a sensitivity label from a label policy, or delete a sensitivity label, these changes can take up to 24 hours to replicate to all users and services.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a4d8d-238">次の手順</span><span class="sxs-lookup"><span data-stu-id="a4d8d-238">Next steps</span></span>

<span data-ttu-id="a4d8d-239">特定のシナリオで秘密度ラベルを構成して使用するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-239">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="a4d8d-240">機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="a4d8d-240">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="a4d8d-241">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="a4d8d-241">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="a4d8d-242">チーム、グループ、およびサイトで機密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="a4d8d-242">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="a4d8d-243">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする</span><span class="sxs-lookup"><span data-stu-id="a4d8d-243">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="a4d8d-244">ラベルの使用状況を監視するには、「[データ分類の使用を開始する](data-classification-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8d-244">To monitor how your labels are being used, see [Get started with data classification](data-classification-overview.md).</span></span>
