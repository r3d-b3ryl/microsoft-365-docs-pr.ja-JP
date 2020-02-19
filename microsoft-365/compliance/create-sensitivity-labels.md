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
description: 組織のドキュメントやメールを分類し、保護するための秘密度ラベルを作成、構成、発行する手順です。
ms.openlocfilehash: 8018c18e976d0e6f9904923471bb07c8bb3cbc40
ms.sourcegitcommit: 7d07e7ec84390a8f05034d3639fa5db912809585
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42091300"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="d9830-103">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="d9830-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="d9830-104">[秘密度ラベル](sensitivity-labels.md)を作成して発行するには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)などラベル付けの管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="d9830-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="d9830-105">Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9830-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="d9830-106">まず、Office 用のアプリとサービスで使用する秘密度ラベルを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="d9830-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="d9830-107">次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9830-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="d9830-108">このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。</span><span class="sxs-lookup"><span data-stu-id="d9830-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a><span data-ttu-id="d9830-109">機密ラベルの作成と管理に必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d9830-109">Permissions required to create and manage sensitivity labels</span></span>

<span data-ttu-id="d9830-110">機密ラベルを作成するコンプライアンス チームのメンバーは、Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターへのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9830-110">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> 

<span data-ttu-id="d9830-111">既定では、テナント管理者はこれらの管理センターへのアクセス権を所有し、コンプライアンス責任者や他のユーザーにアクセス権を付与できます (テナント管理者が持つすべての権限を付与する必要はありません)。この委任された制限付き管理者アクセス許可については、これらのいずれかの管理センターの [**アクセス許可**] ページに移動して、[**コンプライアンス データ管理者**] 役割グループ、[**コンプライアンス管理者**] 役割グループ、または [**セキュリティ管理者**] 役割グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d9830-111">By default, your tenant admin has access to these admin centers and can give compliance officers and other people access, without giving them all of the permissions of a tenant admin. For this delegated limited admin access, go to the **Permissions** page of one of these admin centers, and then add members to the **Compliance Data Administrator**, **Compliance Administrator** or **Security Administrator** role group.</span></span>

<span data-ttu-id="d9830-112">役割を使用する代わりに、新しい役割グループを作成し、**秘密度ラベル管理者**の役割または**組織の構成**の役割をこのグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d9830-112">Alternatively to using roles, you can create a new role group and add either **Sensitivity Label Administrator** or **Organization Configuration** roles to this group.</span></span> <span data-ttu-id="d9830-113">手順については、「[ユーザーに Office 365 セキュリティ/センター コンプライアンス センターへのアクセスを許可する](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="d9830-114">これらのアクセス許可は、機密ラベルとそのラベル ポリシーの作成と構成を行う場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="d9830-114">These permissions are required only to create and configure sensitivity labels and their label policies.</span></span> <span data-ttu-id="d9830-115">アプリまたはサービスでラベルを適用するためには必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9830-115">They are not required to apply the labels in apps or services.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="d9830-116">秘密度ラベルを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="d9830-116">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="d9830-117">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d9830-117">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="d9830-118">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="d9830-118">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="d9830-119">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="d9830-119">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="d9830-120">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-120">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="d9830-121">Microsoft 365 セキュリティ センター:</span><span class="sxs-lookup"><span data-stu-id="d9830-121">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="d9830-122">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="d9830-122">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="d9830-123">Office 365 セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="d9830-123">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="d9830-124">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="d9830-124">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="d9830-125">[**ラベル**] タブで、[**+ ラベルの作成**] を選択して、[**新しい秘密度ラベル**] ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="d9830-125">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="d9830-126">ラベル設定の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d9830-126">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="d9830-127">ラベル設定の詳細については、「概要」の「[秘密度ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-127">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="d9830-128">さらにラベルを作成するには、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d9830-128">Repeat these steps to create more labels.</span></span> <span data-ttu-id="d9830-129">ただし、サブ ラベルを作成する場合は、まず親ラベルを選択してから、[**その他のアクション**] の [**...**] を選択し、[**サブ ラベルの追加**] を選択ます。</span><span class="sxs-lookup"><span data-stu-id="d9830-129">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="d9830-130">必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="d9830-130">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="d9830-131">ラベルの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-131">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="d9830-132">詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-132">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="d9830-133">既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-133">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="d9830-134">これにより、[**秘密度ラベルの編集**] ウィザードが起動し、手順 3 のすべてのラベル設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d9830-134">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="d9830-135">ラベル ポリシーを使用して既に発行されているラベルを編集する場合、ウィザードを終了するときに、追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d9830-135">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="d9830-136">たとえば、同じユーザーに変更を反映させるために、ラベルを新しいラベル ポリシーに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9830-136">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="d9830-137">ただし、変更をユーザーとサービスにレプリケートするには、最大で 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d9830-137">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="d9830-138">ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9830-138">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="d9830-139">ラベルを発行するには、ラベルを[ラベル ポリシーに追加](#publish-sensitivity-labels-by-creating-a-label-policy)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9830-139">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9830-140">この [**ラベル**] タブで、新しいラベル ポリシーを作成する必要がある場合を除き、[**ラベルの発行**] タブ (またはラベル編集時の [**ラベルの発行**] ボタン) を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="d9830-140">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="d9830-141">複数のラベル ポリシーが必要になるのは、ユーザーが異なるラベルまたは異なるポリシー設定を必要とする場合だけです。</span><span class="sxs-lookup"><span data-stu-id="d9830-141">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="d9830-142">できるだけ少ないラベル ポリシーを目指します。組織用のラベル ポリシーを 1 つだけ用意することは珍しくありません。</span><span class="sxs-lookup"><span data-stu-id="d9830-142">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="d9830-143">Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定</span><span class="sxs-lookup"><span data-stu-id="d9830-143">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="d9830-144">[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9830-144">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="d9830-145">多国籍の展開では、ユーザーが自分のローカル言語でラベル名とヒントを表示できるように *LocaleSettings* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9830-145">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="d9830-146">構成例については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-146">See the following section for an example configuration.</span></span> 

<span data-ttu-id="d9830-147">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9830-147">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="d9830-148">この詳細設定には、ラベルが適用されたときのラベルの色の設定やカスタム プロパティの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9830-148">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="d9830-149">完全な一覧については、「[利用できるラベル ポリシーの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-149">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="d9830-150">異なる言語向けに機密ラベルを構成する構成例</span><span class="sxs-lookup"><span data-stu-id="d9830-150">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="d9830-151">次の例では、ヒント用のプレースホルダー テキストが含まれる "Public" という名前のラベルの PowerShell 構成を示します。</span><span class="sxs-lookup"><span data-stu-id="d9830-151">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="d9830-152">この例では、ラベル名とヒントのテキストはフランス語、イタリア語、ドイツ語向けに構成されます。</span><span class="sxs-lookup"><span data-stu-id="d9830-152">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="d9830-153">この構成の結果、これらの表示言語を使用する Office アプリを所有するユーザーには、ラベル名とツールヒントが同じ言語で表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d9830-153">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="d9830-154">同様に、ファイルへのラベル付けをエクスプローラーから行うために Azure Information Protection 統一ラベル付けクライアントがインストールされている場合、これらの言語バージョンの Windows を所有しているユーザーがラベル付けのために右クリック アクションを使用すると、ラベル名とツールヒントがローカル言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9830-154">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="d9830-155">サポートする必要がある言語については、Office の[言語識別子](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (言語タグとも呼ばれます) を使用して、ラベル名とツールヒントの独自の翻訳を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9830-155">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="d9830-156">PowerShell でコマンドを実行する前に、最初に [Office 365 セキュリティ/コンプライアンス センターの PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9830-156">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress)
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="d9830-157">ラベル ポリシーを作成して秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="d9830-157">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="d9830-158">ラベル付けの管理センターで、[秘密度ラベル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d9830-158">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="d9830-159">Microsoft 365 コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="d9830-159">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="d9830-160">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="d9830-160">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="d9830-161">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-161">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="d9830-162">Microsoft 365 セキュリティ センター:</span><span class="sxs-lookup"><span data-stu-id="d9830-162">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="d9830-163">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="d9830-163">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="d9830-164">Office 365 セキュリティ/コンプライアンス センター:</span><span class="sxs-lookup"><span data-stu-id="d9830-164">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="d9830-165">[**分類**]  >  [**秘密度ラベル**]</span><span class="sxs-lookup"><span data-stu-id="d9830-165">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="d9830-166">[**ラベル ポリシー**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-166">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="d9830-167">[**ラベルの発行**] を選択し、[**ポリシーの作成] ウィザード**を起動します。</span><span class="sxs-lookup"><span data-stu-id="d9830-167">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="d9830-168">[**発行する秘密度ラベルの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9830-168">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="d9830-169">アプリとサービスで使用するラベルを選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-169">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="d9830-170">選択したラベルを確認し、変更する場合は [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-170">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="d9830-171">それ以外の場合は、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-171">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="d9830-172">指示に従ってポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d9830-172">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="d9830-173">設定の詳細については、「概要」の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-173">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="d9830-174">異なるユーザーや場所に対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d9830-174">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="d9830-175">たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="d9830-175">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="d9830-176">複数のラベル ポリシーを作成すると、ユーザーまたは場所の競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="d9830-176">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="d9830-177">ラベル ポリシーの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-177">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="d9830-178">詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-178">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="d9830-179">ウィザードを完了すると、ラベル ポリシーが自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="d9830-179">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="d9830-180">発行したポリシーは、簡単に編集して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d9830-180">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="d9830-181">特定の発行や再発行のアクションを選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9830-181">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="d9830-182">既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、[**ポリシーの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9830-182">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="d9830-183">これにより、[**ポリシーの作成**] ウィザードが起動し、含めるラベルとラベルの設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="d9830-183">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="d9830-184">ウィザードを完了すると、選択したユーザーとサービスに変更が自動的にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="d9830-184">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="d9830-185">通常、Office アプリのラベルは数時間以内にユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9830-185">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="d9830-186">ただし、ラベル ポリシーおよびそれらに対する変更を最大 24 時間使用して、すべてのユーザとサービスにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="d9830-186">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="d9830-187">Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="d9830-187">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="d9830-188">[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル ポリシー設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9830-188">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="d9830-189">このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d9830-189">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="d9830-190">この詳細設定には、Outlook 用の異なる既定ラベルが含まれています。また、送信メールの警告、両端揃え、ブロックを行うポップアップ メッセージを Outlook に実装しています。</span><span class="sxs-lookup"><span data-stu-id="d9830-190">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="d9830-191">完全な一覧については、「[利用できるラベルの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-191">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="d9830-192">このコマンドレットを使用して、ラベル ポリシーへのラベルの追加や削除も可能です。</span><span class="sxs-lookup"><span data-stu-id="d9830-192">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="d9830-193">次の手順</span><span class="sxs-lookup"><span data-stu-id="d9830-193">Next steps</span></span>

<span data-ttu-id="d9830-194">特定のシナリオで秘密度ラベルを構成して使用するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-194">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="d9830-195">機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="d9830-195">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="d9830-196">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="d9830-196">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="d9830-197">チーム、グループ、およびサイトで機密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="d9830-197">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="d9830-198">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする</span><span class="sxs-lookup"><span data-stu-id="d9830-198">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="d9830-199">ラベルがどのように使われているかを監視するには、「[ラベル分析によるラベル使用状況の表示](label-analytics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9830-199">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
