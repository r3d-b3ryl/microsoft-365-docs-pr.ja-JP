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
description: 'すべての Microsoft Information Protection ソリューションの要件: 組織のドキュメントやメールを分類し、保護するための秘密度ラベルを作成、構成、発行します。'
ms.openlocfilehash: 96784edb6cf31d024d94e12a76c96b2f61340f04
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679081"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="1bf43-103">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="1bf43-103">Create and configure sensitivity labels and their policies</span></span>

><span data-ttu-id="1bf43-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="1bf43-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1bf43-105">すべての Microsoft Information Protection ソリューション (MIP と略されることもあります) は、[秘密度ラベル](sensitivity-labels.md)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-105">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="1bf43-106">それらのラベルを作成して発行するには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)などラベル付けの管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-106">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="1bf43-107">Microsoft 365 セキュリティ センター、またはセキュリティ/コンプライアンス センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-107">You can also use the Microsoft 365 security center, or the Security & Compliance Center.</span></span>

<span data-ttu-id="1bf43-108">まず、アプリやその他のサービスで使用する秘密度ラベルを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-108">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="1bf43-109">たとえば、ユーザーに表示して Office アプリから適用するラベルです。</span><span class="sxs-lookup"><span data-stu-id="1bf43-109">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="1bf43-110">次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-110">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="1bf43-111">このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-111">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1bf43-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="1bf43-112">Before you begin</span></span>

<span data-ttu-id="1bf43-113">組織のグローバル管理者には、秘密度ラベルのすべての側面を作成および管理するための完全な権限があります。</span><span class="sxs-lookup"><span data-stu-id="1bf43-113">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="1bf43-114">グローバル管理者としてサインインしていない場合は、「[機密ラベルの作成と管理に必要なアクセス許可](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-114">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="1bf43-115">秘密度ラベルを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="1bf43-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="1bf43-116">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-116">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="1bf43-117">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="1bf43-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="1bf43-118">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="1bf43-118">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="1bf43-119">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-119">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="1bf43-120">Microsoft 365 セキュリティ センター:</span><span class="sxs-lookup"><span data-stu-id="1bf43-120">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="1bf43-121">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="1bf43-121">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="1bf43-122">セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="1bf43-122">Security & Compliance Center:</span></span>
        - <span data-ttu-id="1bf43-123">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="1bf43-123">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="1bf43-124">[**ラベル**] タブで、[**+ ラベルの作成**] を選択して、[**新しい秘密度ラベル**] ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-124">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="1bf43-125">ラベル設定の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="1bf43-125">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="1bf43-126">ラベル設定の詳細については、「概要」の「[秘密度ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-126">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="1bf43-127">さらにラベルを作成するには、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-127">Repeat these steps to create more labels.</span></span> <span data-ttu-id="1bf43-128">ただし、サブ ラベルを作成する場合は、まず親ラベルを選択してから、[**その他のアクション**] の [**...**] を選択し、[**サブ ラベルの追加**] を選択ます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-128">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="1bf43-129">必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-129">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="1bf43-130">ラベルの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-130">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="1bf43-131">詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-131">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="1bf43-132">既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-132">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="1bf43-133">これにより、[**秘密度ラベルの編集**] ウィザードが起動し、手順 3 のすべてのラベル設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-133">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="1bf43-134">ラベル ポリシーを使用して既に発行されているラベルを編集する場合、ウィザードを終了するときに、追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-134">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="1bf43-135">たとえば、同じユーザーに変更を反映させるために、ラベルを新しいラベル ポリシーに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-135">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="1bf43-136">ただし、変更をユーザーとサービスにレプリケートするには、最大で 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="1bf43-136">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="1bf43-137">ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-137">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="1bf43-138">ラベルを発行するには、ラベルを[ラベル ポリシーに追加](#publish-sensitivity-labels-by-creating-a-label-policy)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bf43-138">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bf43-139">この [**ラベル**] タブで、新しいラベル ポリシーを作成する必要がある場合を除き、[**ラベルの発行**] タブ (またはラベル編集時の [**ラベルの発行**] ボタン) を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-139">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="1bf43-140">複数のラベル ポリシーが必要になるのは、ユーザーが異なるラベルまたは異なるポリシー設定を必要とする場合だけです。</span><span class="sxs-lookup"><span data-stu-id="1bf43-140">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="1bf43-141">できるだけ少ないラベル ポリシーを目指します。組織用のラベル ポリシーを 1 つだけ用意することは珍しくありません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-141">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="1bf43-142">セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定</span><span class="sxs-lookup"><span data-stu-id="1bf43-142">Additional label settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="1bf43-143">[セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-143">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label?view=exchange-ps) cmdlet from [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="1bf43-144">多国籍の展開では、ユーザーが自分のローカル言語でラベル名とヒントを表示できるように *LocaleSettings* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-144">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="1bf43-145">構成例については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-145">See the following section for an example configuration.</span></span> 

<span data-ttu-id="1bf43-146">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-146">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="1bf43-147">この詳細設定には、ラベルが適用されたときのラベルの色の設定やカスタム プロパティの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-147">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="1bf43-148">完全な一覧については、「[利用できるラベル ポリシーの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-148">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="1bf43-149">異なる言語向けに機密ラベルを構成する構成例</span><span class="sxs-lookup"><span data-stu-id="1bf43-149">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="1bf43-150">次の例では、ヒント用のプレースホルダー テキストが含まれる "Public" という名前のラベルの PowerShell 構成を示します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-150">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="1bf43-151">この例では、ラベル名とヒントのテキストはフランス語、イタリア語、ドイツ語向けに構成されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-151">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="1bf43-152">この構成の結果、これらの表示言語を使用する Office アプリを所有するユーザーには、ラベル名とツールヒントが同じ言語で表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="1bf43-152">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="1bf43-153">同様に、ファイルへのラベル付けをエクスプローラーから行うために Azure Information Protection 統一ラベル付けクライアントがインストールされている場合、これらの言語バージョンの Windows を所有しているユーザーがラベル付けのために右クリック アクションを使用すると、ラベル名とツールヒントがローカル言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-153">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="1bf43-154">サポートする必要がある言語については、Office の[言語識別子](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (言語タグとも呼ばれます) を使用して、ラベル名とツールヒントの独自の翻訳を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-154">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="1bf43-155">PowerShell でコマンドを実行する前に、最初に[セキュリティ/コンプライアンス センターの PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bf43-155">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="1bf43-156">ラベル ポリシーを作成して秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="1bf43-156">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="1bf43-157">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-157">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="1bf43-158">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="1bf43-158">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="1bf43-159">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="1bf43-159">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="1bf43-160">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-160">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="1bf43-161">Microsoft 365 セキュリティ センター:</span><span class="sxs-lookup"><span data-stu-id="1bf43-161">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="1bf43-162">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="1bf43-162">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="1bf43-163">セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="1bf43-163">Security & Compliance Center:</span></span>
        - <span data-ttu-id="1bf43-164">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="1bf43-164">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="1bf43-165">[**ラベル ポリシー**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-165">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="1bf43-166">[**ラベルの発行**] を選択し、[**ポリシーの作成] ウィザード**を起動します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-166">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="1bf43-167">[**発行する秘密度ラベルの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bf43-167">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="1bf43-168">アプリとサービスで使用するラベルを選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-168">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1bf43-169">サブラベルを選択する場合は、必ず親ラベルも選択してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-169">If you select a sublabel, make sure you also select its parent label.</span></span>
    
5. <span data-ttu-id="1bf43-170">選択したラベルを確認し、変更する場合は [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-170">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="1bf43-171">それ以外の場合は、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-171">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="1bf43-172">指示に従ってポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-172">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="1bf43-173">これらの設定の詳細については、概要情報の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-173">For more information about these settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="1bf43-174">異なるユーザーや場所に対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-174">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="1bf43-175">たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-175">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="1bf43-176">複数のラベル ポリシーを作成すると、ユーザーまたは場所の競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-176">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="1bf43-177">ラベル ポリシーの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-177">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="1bf43-178">詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-178">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="1bf43-179">ウィザードを完了すると、ラベル ポリシーが自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-179">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="1bf43-180">発行したポリシーは、簡単に編集して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-180">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="1bf43-181">特定の発行や再発行のアクションを選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-181">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="1bf43-182">既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、[**ポリシーの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-182">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="1bf43-183">これにより、[**ポリシーの作成**] ウィザードが起動し、含めるラベルとラベルの設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-183">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="1bf43-184">ウィザードを完了すると、選択したユーザーとサービスに変更が自動的にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-184">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="1bf43-185">通常、Office アプリのラベルは数時間以内にユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-185">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="1bf43-186">ただし、ラベル ポリシーおよびそれらに対する変更を最大 24 時間使用して、すべてのユーザとサービスにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-186">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="1bf43-187">セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="1bf43-187">Additional label policy settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="1bf43-188">[セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル ポリシー設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-188">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label?view=exchange-ps) cmdlet from [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="1bf43-189">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-189">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="1bf43-190">この詳細設定には、Outlook 用の異なる既定ラベルが含まれています。また、送信メールの警告、両端揃え、ブロックを行うポップアップ メッセージを Outlook に実装しています。</span><span class="sxs-lookup"><span data-stu-id="1bf43-190">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="1bf43-191">完全な一覧については、「[利用できるラベルの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-191">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="1bf43-192">このコマンドレットを使用して、ラベル ポリシーへのラベルの追加や削除も可能です。</span><span class="sxs-lookup"><span data-stu-id="1bf43-192">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="1bf43-193">ラベルの解除と削除</span><span class="sxs-lookup"><span data-stu-id="1bf43-193">Removing and deleting labels</span></span>

<span data-ttu-id="1bf43-194">運用環境では、通常、ラベル ポリシーから秘密度ラベルを解除したり、秘密度ラベルを削除したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-194">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="1bf43-195">テストの初期段階では、そのいずれかまたは両方の操作を行う必要が発生する可能性が高いかもしれません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-195">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="1bf43-196">それらの操作を行った場合、何が起こるかをよく理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-196">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="1bf43-197">ラベル ポリシーからのラベルの解除は、削除に比べてリスクが少なく、必要に応じて後でいつでもラベル ポリシーに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-197">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="1bf43-198">ラベル ポリシーからラベルを解除して当初指定したユーザーにラベルが発行されないようになった場合、次にラベル ポリシーが更新されるときに、そのラベルは Office アプリの選択対象としてユーザーに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1bf43-198">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="1bf43-199">ただし、ラベルがドキュメントやメールに適用されている場合は、そのコンテンツからはラベルは解除されません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-199">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="1bf43-200">ラベルによって適用された暗号化があればそのまま残り、基となる保護テンプレートは発行済のまま維持されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-200">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="1bf43-201">解除されたラベルが、以前にコンテンツに適用されていた場合、Word、Excel、PowerPoint の組み込みラベルを使っているユーザーに対しては、適用されたラベルは引き続きステータス バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-201">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="1bf43-202">同様に、SharePoint サイトに適用されている解除済みのラベルも**秘密度**列のラベル名に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-202">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="1bf43-203">これに対して、ラベルを削除した場合は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="1bf43-203">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="1bf43-204">ラベルが暗号化を適用している場合、以前に保護したコンテンツを引き続き開けるようにするため、基になる保護テンプレートはアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-204">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="1bf43-205">これはアーカイブされた保護テンプレートなので、新しいラベルを同じ名前で作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-205">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="1bf43-206">[PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate) を使って保護テンプレートを削除することはできますが、アーカイブしたテンプレートを使用して暗号化されたコンテンツを開く必要がないことが確実な場合を除いて、この操作は実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-206">Although it's possible to delete a protection template by using [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="1bf43-207">デスクトップ アプリの場合: メタデータのラベル情報は残りますが、名前のマッピングに使うラベル ID は利用できなくなっているため、適用されたラベル名は表示されず (ステータス バーなどに)、これによりユーザーはコンテンツはラベル付けされていないと判断します。</span><span class="sxs-lookup"><span data-stu-id="1bf43-207">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="1bf43-208">ラベルが暗号化を適用している場合、暗号化はそのまま残り、コンテンツが開かれると、既にアーカイブされた保護テンプレートの名前と説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-208">If the label applied encryption, the encryption remains and when the content is opened, uses still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="1bf43-209">Office on the web の場合: ステータス バーまたは**秘密度**列にラベル名は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1bf43-209">For Office on the web: Users don't see the label name on status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="1bf43-210">ラベルが暗号化を適用していない場合にのみ、メタデータのラベル情報はそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="1bf43-210">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="1bf43-211">ラベルが暗号化を適用していて、[SharePoint と OneDrive の秘密度ラベル](sensitivity-labels-sharepoint-onedrive-files.md)が有効になっている場合、メタデータのラベル情報は削除され、暗号化は解除されます。</span><span class="sxs-lookup"><span data-stu-id="1bf43-211">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and Onedrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="1bf43-212">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1bf43-212">Next steps</span></span>

<span data-ttu-id="1bf43-213">特定のシナリオで秘密度ラベルを構成して使用するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-213">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="1bf43-214">機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="1bf43-214">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="1bf43-215">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="1bf43-215">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="1bf43-216">チーム、グループ、およびサイトで機密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="1bf43-216">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="1bf43-217">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする</span><span class="sxs-lookup"><span data-stu-id="1bf43-217">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="1bf43-218">ラベルがどのように使われているかを監視するには、「[ラベル分析によるラベル使用状況の表示](label-analytics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf43-218">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
