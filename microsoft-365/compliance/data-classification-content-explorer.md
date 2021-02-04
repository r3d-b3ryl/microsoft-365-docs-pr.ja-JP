---
title: コンテンツ エクスプローラーの使用を開始する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: コンテンツ エクスプローラーにより、ラベル付きアイテムをネイティブに表示することができます。
ms.openlocfilehash: 19ad68d3c32046754e366919e8c4e66336945624
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080726"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="395e7-103">コンテンツ エクスプローラーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="395e7-103">Get started with content explorer</span></span>

<span data-ttu-id="395e7-104">データ分類コンテンツ エクスプローラーにより、概要ページで要約されたアイテムをネイティブに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![折りたたみ済みのコンテンツ エクスプローラーのスクリーンショット](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="395e7-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="395e7-106">Prerequisites</span></span>

<span data-ttu-id="395e7-107">データ分類にアクセスして使用するすべてのアカウントには、これらのいずれかのサブスクリプションのライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="395e7-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="395e7-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="395e7-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="395e7-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="395e7-109">Office 365 (E5)</span></span>
- <span data-ttu-id="395e7-110">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="395e7-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="395e7-111">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="395e7-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="395e7-112">Microsoft 365 E5/A5 情報保護およびガバナンス</span><span class="sxs-lookup"><span data-stu-id="395e7-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="395e7-113">Microsoft 365 E5/A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="395e7-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="395e7-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="395e7-114">Permissions</span></span>

<span data-ttu-id="395e7-115">[コンテンツ エクスプローラー] タブにアクセスするには、アカウントはこれらの役割または役割グループに割り当てられたメンバーシップであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="395e7-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="395e7-116">**Microsoft 365 の役割グループ**</span><span class="sxs-lookup"><span data-stu-id="395e7-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="395e7-117">全体管理者</span><span class="sxs-lookup"><span data-stu-id="395e7-117">Global administrator</span></span>
- <span data-ttu-id="395e7-118">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="395e7-118">Compliance administrator</span></span>
- <span data-ttu-id="395e7-119">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="395e7-119">Security administrator</span></span>
- <span data-ttu-id="395e7-120">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="395e7-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="395e7-121">これらの役割グループのメンバーシップでは、コンテンツ エクスプローラーでアイテムの一覧を表示したり、コンテンツ エクスプローラーでアイテムの内容を表示したりすることができません。</span><span class="sxs-lookup"><span data-stu-id="395e7-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="395e7-122">コンテンツ エクスプローラーでアイテムにアクセスするために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="395e7-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="395e7-123">コンテンツ エクスプローラーへのアクセスは、スキャンしたファイルのコンテンツを読み取ることができるため、厳しく制限されています。</span><span class="sxs-lookup"><span data-stu-id="395e7-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="395e7-124">これらのアクセス許可は、アイテムにローカルに割り当てられるアクセス許可の代わりに、コンテンツの表示を許可します。</span><span class="sxs-lookup"><span data-stu-id="395e7-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="395e7-125">コンテンツ エクスプローラーへのアクセスを許可する 2 つの役割があり、[Microsoft セキュリティ/コンプライアンス センター](https://protection.office.com/permissions)を使用して許可されます。</span><span class="sxs-lookup"><span data-stu-id="395e7-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="395e7-126">**コンテンツ エクスプローラーのリスト ビューアー**: この役割のグループのメンバーシップにより、ユーザーは各アイテムおよびその場所をリスト ビューで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="395e7-127">この役割グループには、`data classification list viewer` 役割が事前に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="395e7-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="395e7-128">**コンテンツ エクスプローラーのコンテンツ ビューアー**: この役割のグループのメンバーシップにより、ユーザーはリスト内の各アイテムのコンテンツを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="395e7-129">この役割グループには、`data classification content viewer` 役割が事前に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="395e7-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="395e7-130">コンテンツ エクスプローラーにアクセスするために使用するアカウントには、1 つまたは両方の役割のグループがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="395e7-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="395e7-131">独立した役割のグループがあり、累積ではありません。</span><span class="sxs-lookup"><span data-stu-id="395e7-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="395e7-132">たとえば、アイテムおよびそれらの場所のみ表示する機能をアカウントに付与する場合は、コンテンツ エクスプローラーのリスト ビューアーの権利を付与します。</span><span class="sxs-lookup"><span data-stu-id="395e7-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="395e7-133">その同じアカウントでリスト内のアイテムのコンテンツも表示できるようにするには、コンテンツ エクスプローラーのコンテンツ ビューアーの権利も付与します。</span><span class="sxs-lookup"><span data-stu-id="395e7-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="395e7-134">また、役割の一方または両方をカスタム役割グループに割り当てて、コンテンツ エクスプローラーへのアクセスをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="395e7-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="395e7-135">グローバル管理者、コンプライアンス管理者、またはデータ管理者は、必要な コンテンツ エクスプローラーのリスト ビューアー、および コンテンツ エクスプローラーのコンテンツ ビューアー の役割グループのメンバーシップを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="395e7-136">コンテンツ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="395e7-136">Content explorer</span></span>

<span data-ttu-id="395e7-137">コンテンツ エクスプローラーは、機密ラベル、保持ラベルまたは組織で機密情報の種類として分類されているアイテムの現在のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="395e7-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="395e7-138">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="395e7-138">Sensitive information types</span></span>

<span data-ttu-id="395e7-139">[DLP ポリシー](data-loss-prevention-policies.md)は、**機密情報の種類** として定義されている機密情報を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="395e7-139">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="395e7-140">Microsoft 365 には、さまざまな地域にわたる[多くの一般的な機密情報の種類に対する定義](sensitive-information-type-entity-definitions.md)が含まれていて、すぐに使用できる状態になっています。</span><span class="sxs-lookup"><span data-stu-id="395e7-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="395e7-141">たとえば、クレジットカード番号、銀行口座番号、国民識別番号、Windows Live ID サービス番号などです。</span><span class="sxs-lookup"><span data-stu-id="395e7-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="395e7-142">現在、コンテンツ エクスプローラーは、Exchange Online の機密情報の種類をスキャンしません。</span><span class="sxs-lookup"><span data-stu-id="395e7-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="395e7-143">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="395e7-143">Sensitivity labels</span></span>

<span data-ttu-id="395e7-144">[機密ラベル](sensitivity-labels.md)は、組織に対するアイテムの価値を示すタグです。</span><span class="sxs-lookup"><span data-stu-id="395e7-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="395e7-145">手動で、または自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="395e7-146">適用すると、ドキュメントに埋め込まれ、ドキュメントがどこへ移動されても機密ラベルは保持されます。</span><span class="sxs-lookup"><span data-stu-id="395e7-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="395e7-147">機密ラベルによって、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="395e7-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="395e7-148">SharePoint および OneDrive にあるファイルに対応するデータがデータ分類ページに表示されるようにするには、機密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="395e7-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="395e7-149">詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="395e7-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="395e7-150">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="395e7-150">Retention labels</span></span>

<span data-ttu-id="395e7-151">[保持ラベル](retention.md)を使用すると、ラベル付けされたアイテムの保持期間、およびアイテムを削除する前に行う手順を定義できます。</span><span class="sxs-lookup"><span data-stu-id="395e7-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="395e7-152">手動で、またはポリシーを使用して自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="395e7-153">組織が法的要件および規制要件を遵守するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="395e7-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="395e7-154">コンテンツ エクスプローラーの使用方法</span><span class="sxs-lookup"><span data-stu-id="395e7-154">How to use content explorer</span></span>

1. <span data-ttu-id="395e7-155">**Microsoft 365 コンプライアンス センター**  > **[データ分類]** > **[コンテンツ エクスプローラー]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="395e7-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="395e7-156">ラベルの名前または機密情報の種類が分かる場合は、それをフィルター ボックスに入力することができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="395e7-157">交互に、ラベルの種類を展開してリストからラベルを選択し、アイテムを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="395e7-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="395e7-158">[**すべての場所**] の下で場所を選択して、アイテムのフォルダー構造をドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="395e7-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="395e7-159">ダブルクリックして、コンテンツ エクスプローラーでネイティブにアイテムを開きます。</span><span class="sxs-lookup"><span data-stu-id="395e7-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="395e7-160">エクスポート</span><span class="sxs-lookup"><span data-stu-id="395e7-160">Export</span></span>
<span data-ttu-id="395e7-161">**エクスポート** コントロールは、**[すべての場所]** ウィンドウで表示される内容の一覧を含む .csv ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="395e7-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![データ分類エクスポート コントロール](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="395e7-163">検索</span><span class="sxs-lookup"><span data-stu-id="395e7-163">Search</span></span>

<span data-ttu-id="395e7-164">Exchange フォルダー、SharePoint、OneDrive サイトなどの場所をドリルダウンするとき、**検索** ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="395e7-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![コンテンツ エクスプローラー検索ツール](../media/data_classification_search_tool.png)


<span data-ttu-id="395e7-166">検索ツールの範囲は、**[すべての場所 ]** ウィンドウに表示される内容です。また、検索できる対象は、選択した場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="395e7-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="395e7-167">**Exchange** が選択された場所である場合、メールボックスの完全なメール アドレスを検索できます (`user@domainname.com` など)。</span><span class="sxs-lookup"><span data-stu-id="395e7-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="395e7-168">**SharePoint** または **OneDrive** が選択された場所である場合、サイト名、フォルダー、ファイルをドリルダウンすると、検索ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="395e7-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="395e7-169">**OneDrive** プレビュープログラム中に、OneDrive との統合に関する貴重なフィードバックをいただきました。</span><span class="sxs-lookup"><span data-stu-id="395e7-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="395e7-170">このフィードバックに基づき、すべての修正プログラムが適用されるまで、OneDrive の機能はプレビュー版のままになります。</span><span class="sxs-lookup"><span data-stu-id="395e7-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="395e7-171">テナントによっては、一部のお客様に OneDrive が場所として表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="395e7-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="395e7-172">この件に関する継続的なサポートに感謝いたします。</span><span class="sxs-lookup"><span data-stu-id="395e7-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="395e7-173">以下を検索できます。</span><span class="sxs-lookup"><span data-stu-id="395e7-173">You can search on:</span></span>


|<span data-ttu-id="395e7-174">値</span><span class="sxs-lookup"><span data-stu-id="395e7-174">value</span></span>|<span data-ttu-id="395e7-175">例</span><span class="sxs-lookup"><span data-stu-id="395e7-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="395e7-176">完全なサイト名</span><span class="sxs-lookup"><span data-stu-id="395e7-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="395e7-177">ルート フォルダー名 - すべてのサブフォルダーを取得する</span><span class="sxs-lookup"><span data-stu-id="395e7-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="395e7-178">ファイル名</span><span class="sxs-lookup"><span data-stu-id="395e7-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="395e7-179">ファイル名の最初のテキスト</span><span class="sxs-lookup"><span data-stu-id="395e7-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="395e7-180">ファイル名の下線文字 (_) 以降のテキスト</span><span class="sxs-lookup"><span data-stu-id="395e7-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="395e7-181">`Resume` または `1234`</span><span class="sxs-lookup"><span data-stu-id="395e7-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="395e7-182">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="395e7-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="395e7-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="395e7-183">See also</span></span>

- [<span data-ttu-id="395e7-184">秘密度ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="395e7-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="395e7-185">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="395e7-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="395e7-186">機密情報の種類のエンティティ定義.md</span><span class="sxs-lookup"><span data-stu-id="395e7-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="395e7-187">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="395e7-187">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
