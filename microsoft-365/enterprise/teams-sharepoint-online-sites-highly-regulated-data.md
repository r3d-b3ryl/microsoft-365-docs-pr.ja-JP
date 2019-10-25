---
title: 厳しく規制されたデータ用の SharePoint サイト
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: セキュリティで保護された SharePoint チーム サイトを作成して、最も重要な機密ファイルを保存します。
ms.openlocfilehash: 7162ced48a64270713dc1eac6e73de053d24b2f4
ms.sourcegitcommit: 7ee256132358a86f8c6ad143816fcfdde011ca74
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "37628341"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="2377e-103">厳しく規制されたデータ用の SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="2377e-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="2377e-104">*このシナリオは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*</span><span class="sxs-lookup"><span data-stu-id="2377e-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2377e-p101">Microsoft 365 Enterprise には、一連のクラウドベースのサービスが含まれており、ファイルに保存された厳しく規制されたデータを作成、保存、保護、管理できます。これには次のようなデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2377e-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="2377e-107">地域の規制を遵守しているデータ。</span><span class="sxs-lookup"><span data-stu-id="2377e-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="2377e-108">企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータ。</span><span class="sxs-lookup"><span data-stu-id="2377e-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="2377e-109">Microsoft Teams を使用する場合の同じシナリオは、[こちら](secure-teams-highly-regulated-data-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="2377e-109">A similar scenario using Microsoft Teams is in development.</span></span>
>

<span data-ttu-id="2377e-110">上記のビジネス ニーズを満たす Microsoft 365 Enterprise のクラウドベースのシナリオは次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="2377e-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="2377e-111">SharePoint チーム サイトにファイル (ドキュメント、スライド セット、スプレッドシートなど) を保存します。</span><span class="sxs-lookup"><span data-stu-id="2377e-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="2377e-112">サイトをロックダウンし、以下を防止します。</span><span class="sxs-lookup"><span data-stu-id="2377e-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="2377e-113">サイトの Office 365 グループのメンバーではないユーザーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="2377e-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="2377e-114">サイトのメンバーから他のユーザーへのアクセス許可の付与。</span><span class="sxs-lookup"><span data-stu-id="2377e-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="2377e-115">サイトのメンバーでないユーザーからサイトへのアクセス要求。</span><span class="sxs-lookup"><span data-stu-id="2377e-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="2377e-116">ユーザーが組織外のファイルを送信するのをブロックする既定の方法として、SharePoint サイトの Office 365 保持ラベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="2377e-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="2377e-117">ファイルと共に移動する暗号化を使用して、サイトの最高機密ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="2377e-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="2377e-118">最高機密ファイルがサイト外で共有された場合でも、そのファイルを開くのにアクセス許可のあるユーザー アカウントの有効な資格情報が必要となるように、最高機密ファイルにアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="2377e-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="2377e-119">次の表は、上記のシナリオの要件を Microsoft 365 Enterprise の機能に関連付けたものです。</span><span class="sxs-lookup"><span data-stu-id="2377e-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="2377e-120">**要件**</span><span class="sxs-lookup"><span data-stu-id="2377e-120">**Requirement**</span></span> | <span data-ttu-id="2377e-121">**Microsoft 365 Enterprise の機能**</span><span class="sxs-lookup"><span data-stu-id="2377e-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="2377e-122">ファイルを保存します</span><span class="sxs-lookup"><span data-stu-id="2377e-122">Store files</span></span> | <span data-ttu-id="2377e-123">SharePoint チーム サイト</span><span class="sxs-lookup"><span data-stu-id="2377e-123">SharePoint team sites</span></span> |
| <span data-ttu-id="2377e-124">サイトのロックダウン</span><span class="sxs-lookup"><span data-stu-id="2377e-124">Lock down the site</span></span> | <span data-ttu-id="2377e-125">Office 365 グループおよび SharePoint チーム サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2377e-125">Office 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="2377e-126">サイトのファイルにラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="2377e-126">Label the files of the site</span></span> | <span data-ttu-id="2377e-127">Office 365 保持ラベル</span><span class="sxs-lookup"><span data-stu-id="2377e-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="2377e-128">ユーザーがファイルを組織外に送信できないようにする</span><span class="sxs-lookup"><span data-stu-id="2377e-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="2377e-129">Office 365 のデータ損失防止 (DLP) ポリシー</span><span class="sxs-lookup"><span data-stu-id="2377e-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="2377e-130">サイトのすべてのファイルを暗号化する</span><span class="sxs-lookup"><span data-stu-id="2377e-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="2377e-131">Office 365 の機密度ラベルまたはサブラベル</span><span class="sxs-lookup"><span data-stu-id="2377e-131">Office 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="2377e-132">サイトのファイルへのアクセス許可の追加</span><span class="sxs-lookup"><span data-stu-id="2377e-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="2377e-133">Office 365 の機密度ラベルまたはサブラベル</span><span class="sxs-lookup"><span data-stu-id="2377e-133">Office 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="2377e-134">次に、セキュリティで保護された SharePoint サイトの構成例を示します。</span><span class="sxs-lookup"><span data-stu-id="2377e-134">Here is the configuration for a secure SharePoint site.</span></span>

![厳しく規制されたデータ シナリオ用の SharePoint サイト](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="2377e-136">このシナリオでは、以下のものを既に展開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="2377e-137">基盤インフラストラクチャの [ID](identity-infrastructure.md) フェーズ、および[情報保護](infoprotect-infrastructure.md)フェーズの手順 1 と 2。</span><span class="sxs-lookup"><span data-stu-id="2377e-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="2377e-138">[SharePoint](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="2377e-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="2377e-139">以下のフェーズでは、厳しく規制されたデータを扱う SharePoint サイトの設計、構成、導入方法について、順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="2377e-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<span data-ttu-id="2377e-140">架空の多国籍組織を表す Contoso 社が、研究チーム向けに SharePoint サイトを設計した方法について確認するには、[構成例](contoso-sharepoint-online-site-for-highly-confidential-assets.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2377e-140">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="2377e-141">ID とデバイス アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="2377e-141">Identity and device access prerequisites</span></span>

<span data-ttu-id="2377e-142">SharePoint サイトへのアクセスを保護するには、[ID とデバイス アクセス ポリシー](identity-access-policies.md) と [推奨される SharePoint アクセス ポリシー](sharepoint-file-access-policies.md) を構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2377e-142">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="2377e-143">フェーズ 1: 設計</span><span class="sxs-lookup"><span data-stu-id="2377e-143">Phase 1: Design</span></span>

<span data-ttu-id="2377e-144">厳しく規制されたデータ用に SharePoint サイトを作成するには、最初にその目的を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-144">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="2377e-145">たとえば、製造組織の研究開発部門では、SharePoint サイトを使用して、既存の製品の現在の設計仕様と新製品を共同作業するための場所を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-145">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="2377e-146">研究開発部門のメンバーと選ばれた役職者だけがサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2377e-146">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="2377e-147">目的に基づいて、以下のような必須の構成項目を決定します。</span><span class="sxs-lookup"><span data-stu-id="2377e-147">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="2377e-148">サイトのドキュメント部分に割り当てる Office 365 保持ラベルと、そのラベル用の一連の DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="2377e-148">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="2377e-149">サイトに保存されている高機密ファイルに、ユーザーが適用する Office 365 秘密度サブラベルの設定</span><span class="sxs-lookup"><span data-stu-id="2377e-149">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="2377e-150">上記の項目を決定したら、それらの設定に基づき、フェーズ 2 でサイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="2377e-150">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="2377e-151">手順 1: Office 365 保持ラベルと DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="2377e-151">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="2377e-152">SharePoint チーム サイトのドキュメント部分に適用されると、Office 365 保持ラベルは、サイトに保存されているすべてのファイルを分類する既定のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2377e-152">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="2377e-153">SharePoint サイトで厳しく規制されたデータを扱う場合は、どの Office 365 保持ラベルを使用するかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-153">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="2377e-154">Office 365 ラベルの設計の考慮事項については、「[Office 365 の分類とラベル](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2377e-154">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="2377e-p103">機密性の高い情報を保護し、偶発的または意図的な開示を防止するためには、DLP ポリシーを使用します。詳細については、DLP ポリシーの[概要](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2377e-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="2377e-157">SharePoint サイトで高度な規制データを扱うには、ファイルを外部のユーザーと共有しようとするユーザーをブロックするために、サイトに割り当てられた Office 365 保持ラベルの DLP ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-157">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="2377e-158">手順 2: Office 365 秘密度サブラベル</span><span class="sxs-lookup"><span data-stu-id="2377e-158">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="2377e-159">暗号化と最高機密ファイルへの一連のアクセス許可を提供するには、ユーザーが Office 365 秘密度ラベルまたはサブラベルを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-159">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span> <span data-ttu-id="2377e-160">既存のラベルの下にサブラベルが存在します。</span><span class="sxs-lookup"><span data-stu-id="2377e-160">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="2377e-161">全体での使用と個別のプライベート チームのいずれにおいても必要なラベルの数が少ない場合は、秘密度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2377e-161">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="2377e-162">ラベルを多数使用している場合、または安全なサイト用のラベルを厳しく規制されたラベルの下でまとめる場合は、秘密度サブラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2377e-162">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="2377e-163">適用されたラベルまたはサブラベルの設定はファイルと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="2377e-163">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="2377e-164">サイト外にリークした場合でも、アクセス許可を持つ認証済みのユーザー アカウントのみが開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2377e-164">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="2377e-165">設計の結果</span><span class="sxs-lookup"><span data-stu-id="2377e-165">Design results</span></span>

<span data-ttu-id="2377e-166">以下を決定しました。</span><span class="sxs-lookup"><span data-stu-id="2377e-166">You have determined the following:</span></span>

- <span data-ttu-id="2377e-167">適切な Office 365 保持ラベルと、そのラベルに関連付けられている DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="2377e-167">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="2377e-168">暗号化とアクセス許可を含む Office 365 秘密度サブラベルの設定</span><span class="sxs-lookup"><span data-stu-id="2377e-168">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="2377e-169">フェーズ 2: 構成</span><span class="sxs-lookup"><span data-stu-id="2377e-169">Phase 2: Configure</span></span>

<span data-ttu-id="2377e-170">このフェーズでは、フェーズ 1 で決定した設定を実装し、厳しく規制されたデータを扱う SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2377e-170">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="2377e-171">手順 1: 対応する Office 365 グループの所有者およびメンバーと、SharePoint チーム サイトを作成</span><span class="sxs-lookup"><span data-stu-id="2377e-171">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="2377e-172">[以下の手順]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) に従って、プライベート SharePoint チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2377e-172">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="2377e-173">手順 2: SharePoint チーム サイトの追加のアクセス許可の設定を構成</span><span class="sxs-lookup"><span data-stu-id="2377e-173">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="2377e-174">SharePoint サイトから、これらのアクセス許可の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2377e-174">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="2377e-175">ツールバーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2377e-175">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="2377e-176">[**サイトの権限**] ウィンドウで、[**共有の設定**] の [**共有設定を変更します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2377e-176">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="2377e-177">[**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2377e-177">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="2377e-178">[**アクセス要求の許可**] をオフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2377e-178">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="2377e-179">これらの設定を使用すると、サイト グループのメンバーがサイトを他のメンバーと共有したり、メンバー以外がサイトへのアクセスを要求したりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="2377e-179">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="2377e-180">手順 3: Office 365 保持ラベル向けにサイトを構成</span><span class="sxs-lookup"><span data-stu-id="2377e-180">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="2377e-181">「[Office 365 ラベルと DLP による SharePoint ファイルの保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)」の手順を参照しながら、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="2377e-181">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="2377e-182">必要な場合には、厳しく規制されたデータの保持ラベルを作成して公開します。</span><span class="sxs-lookup"><span data-stu-id="2377e-182">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="2377e-183">手順 1 で作成した保持ラベルのサイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="2377e-183">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="2377e-184">手順 2 で作成した保持ラベルを使用する厳しく規制されたデータの DLP ポリシーを作成し、ユーザーが組織外にファイルを送信するのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2377e-184">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="2377e-185">手順 4: サイトの Office 365 秘密度サブラベルを作成</span><span class="sxs-lookup"><span data-stu-id="2377e-185">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="2377e-186">すべてのユーザーが任意のファイルに適用できる、厳しく規制されたデータの秘密度ラベルとは異なり、セキュリティで保護されたサイトは独自のサブラベルが必要となります。サブラベルが割り当てられたファイルは、</span><span class="sxs-lookup"><span data-stu-id="2377e-186">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="2377e-187">暗号化され、暗号化はファイルと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="2377e-187">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="2377e-188">カスタムのアクセス許可が含まれ、サイト グループのメンバーのみが開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2377e-188">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="2377e-189">このサイトに保存されているファイルに対して追加のセキュリティ レベルを設定するには、厳しく規制されたファイルの一般的なラベルの新しい機密ラベルまたは一般ラベルのサブラベルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-189">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="2377e-190">厳しく規制されたラベルのサブラベルのリストには、サイトのグループ メンバーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2377e-190">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="2377e-191">[この](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) 指示を参照しながら次の設定を行い、厳しく規制されたファイルに使用しているラベルのラベルまたはサブラベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="2377e-191">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="2377e-192">ラベルまたはサブラベルの名前には、ラベルまたはサブラベルをファイルに割り当てるときに簡単に関連付けるためのサイト名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2377e-192">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="2377e-193">暗号化が有効です。</span><span class="sxs-lookup"><span data-stu-id="2377e-193">Encryption is enabled.</span></span>
- <span data-ttu-id="2377e-194">サイト グループには、共同編集のアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-194">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="2377e-195">構成の結果</span><span class="sxs-lookup"><span data-stu-id="2377e-195">Configuration results</span></span>

<span data-ttu-id="2377e-196">以下を構成しました。</span><span class="sxs-lookup"><span data-stu-id="2377e-196">You have configured the following:</span></span>

- <span data-ttu-id="2377e-197">SharePoint サイトのアクセス許可の設定の制限</span><span class="sxs-lookup"><span data-stu-id="2377e-197">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="2377e-198">SharePoint サイトのドキュメント部分に割り当てられている Office 365 保持ラベル</span><span class="sxs-lookup"><span data-stu-id="2377e-198">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="2377e-199">Office 365 保持ラベルの DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="2377e-199">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="2377e-200">ユーザーは、Office 365 秘密度ラベルまたはサブラベルをファイルを暗号化しているサイトに保存された最高機密ファイルに適用できます。共同編集のアクセスが許可されるのは、サイト グループのメンバーのみです。</span><span class="sxs-lookup"><span data-stu-id="2377e-200">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="2377e-201">これは、厳しく規制されたラベルのサブラベルを使用した結果の構成です。</span><span class="sxs-lookup"><span data-stu-id="2377e-201">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![厳しく規制されたデータ シナリオ用の SharePoint サイト](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="2377e-203">サイトに保存されているファイルにサブラベルを適用したユーザーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2377e-203">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![厳しく規制されたデータ シナリオ用の SharePoint サイト](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="2377e-205">フェーズ 3: ユーザーによる導入を主導</span><span class="sxs-lookup"><span data-stu-id="2377e-205">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="2377e-206">厳しく規制されたデータを扱う SharePoint サイトは、機密ファイルのストレージとアクセスが継続的に使用されている場合にのみ、そのデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="2377e-206">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="2377e-207">これは、ユーザーが習慣や嗜好を変更することに依存するため、最も困難なフェーズです。</span><span class="sxs-lookup"><span data-stu-id="2377e-207">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="2377e-208">たとえば、従業員が機密ファイルを USB ドライブや個人のクラウド ベースのストレージ ソリューションに保存していた場合、その従業員は、厳しく規制されたデータを扱う SharePoint サイトのみに機密ファイルを保存しなければならなくなります。</span><span class="sxs-lookup"><span data-stu-id="2377e-208">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="2377e-209">手順 1: ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="2377e-209">Step 1: Train your users</span></span>

<span data-ttu-id="2377e-210">構成が完了したら、サイトのメンバーである一連のユーザーを以下の面でトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="2377e-210">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="2377e-211">重要なファイルを保護するために新しいサイトを使用することの重要性と、厳しく規制されたデータのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。</span><span class="sxs-lookup"><span data-stu-id="2377e-211">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="2377e-212">サイトとそのファイルへのアクセス方法。</span><span class="sxs-lookup"><span data-stu-id="2377e-212">How to access the site and its files.</span></span>
- <span data-ttu-id="2377e-213">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="2377e-213">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="2377e-214">DLP ポリシーを使用して、外部からのファイルの共有をできないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="2377e-214">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="2377e-215">最高機密ファイルに、サイトのラベルまたはサブラベルを使用してラベルを付ける方法。</span><span class="sxs-lookup"><span data-stu-id="2377e-215">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="2377e-216">ファイルがサイトからリークされてもラベルまたはサブラベルによって保護されるしくみ。</span><span class="sxs-lookup"><span data-stu-id="2377e-216">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="2377e-217">このトレーニングには、ユーザーが上記の操作とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="2377e-217">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="2377e-218">手順 2: 使用状況とファイルの定期的なレビューの実施</span><span class="sxs-lookup"><span data-stu-id="2377e-218">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="2377e-219">トレーニングの数週間後、SharePoint サイトの SharePoint 管理者は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="2377e-219">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="2377e-220">サイトの使用状況を分析し、それが期待された使用法と一致しているかを比較する。</span><span class="sxs-lookup"><span data-stu-id="2377e-220">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="2377e-221">高機密ファイルが秘密度ラベルまたはサブラベルを使用して正しくラベル付けされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="2377e-221">Verify that highly sensitive files have been properly labeled with the sensitivity sublabel.</span></span>

  <span data-ttu-id="2377e-222">ラベルが割り当てられているファイルがわかるようにするには、SharePoint のフォルダーを表示し、[**列の追加**] で [**列の表示/非表示**] オプションを使用して [**秘密度**] 列を追加します。</span><span class="sxs-lookup"><span data-stu-id="2377e-222">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="2377e-223">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="2377e-223">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="2377e-224">ユーザーによる採用の結果</span><span class="sxs-lookup"><span data-stu-id="2377e-224">User adoption results</span></span>

<span data-ttu-id="2377e-225">厳しく規制されたファイルは、厳しく規制されたデータ用の SharePoint サイトにのみ保存されます。また、最も重要なファイルには適用されたサイトの秘密度ラベルまたはサブラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="2377e-225">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="2377e-226">Contoso Corporation の Microsoft 365 Enterprise 展開方法</span><span class="sxs-lookup"><span data-stu-id="2377e-226">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2377e-227">架空の企業、Contoso Corporation は、代表的な世界規模の製造業の複合企業です。</span><span class="sxs-lookup"><span data-stu-id="2377e-227">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="2377e-228">Contoso 社が、パリ、モスクワ、ニューヨーク、北京、およびバンガロールの研究チーム向けに [SharePoint サイトの保護](contoso-sharepoint-online-site-for-highly-confidential-assets.md) をどのように設計、構成、導入したかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2377e-228">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2377e-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="2377e-229">See also</span></span>

[<span data-ttu-id="2377e-230">厳しく規制されたデータ用の Teams</span><span class="sxs-lookup"><span data-stu-id="2377e-230">Microsoft Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="2377e-231">Microsoft 365 Enterprise のワークロードとシナリオ</span><span class="sxs-lookup"><span data-stu-id="2377e-231">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="2377e-232">[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="2377e-232">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="2377e-233">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="2377e-233">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
