---
title: 厳しく規制されたデータに Teams で対応する
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 最重要ファイルおよび機密ファイルを保存するためのセキュリティで保護されたチームを作成します。
ms.openlocfilehash: 4ef4d4e9b8ab437c90aac434db158cfb40f066cb
ms.sourcegitcommit: 7ee256132358a86f8c6ad143816fcfdde011ca74
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "37628351"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="2907f-103">厳しく規制されたデータに Teams で対応する</span><span class="sxs-lookup"><span data-stu-id="2907f-103">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="2907f-104">この記事では、Microsoft Teams 内のプライベート チームを構成して、チャット、会議、ファイルなどの Teams の機能へのアクセスをチームの Office 365 グループのメンバーおよび所有者のみに制限するための推奨事項および手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="2907f-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="2907f-105">この記事では、Office 365 グループに基づくプライベート アクセスの他にも、それの基となっている、チーム チャネルの [**ファイル**] セクションからアクセスできるプライベート SharePoint チーム サイトを構成して厳しく規制されたデータの保存で必要な追加のセキュリティを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2907f-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="2907f-106">この SharePoint チーム サイトでは、ファイル、ページ、共有予定表、タスク、ノートブック、およびリストを保存して共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="2907f-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="2907f-107">規制の厳しいデータ用にチームを構成する場合の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2907f-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="2907f-108">プライベート チームおよびそれに対応する、所有者とメンバーのユーザー アカウントを持つ Office 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="2907f-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="2907f-109">チームの基になっている SharePoint サイトでの以下の追加のセキュリティ:</span><span class="sxs-lookup"><span data-stu-id="2907f-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="2907f-110">サイト メンバーが他のユーザーへアクセス許可を付与することの防止。</span><span class="sxs-lookup"><span data-stu-id="2907f-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="2907f-111">サイトのメンバーではないユーザーがサイトへのアクセス権を要求することの防止。</span><span class="sxs-lookup"><span data-stu-id="2907f-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="2907f-112">アイテム保持ポリシーを定義する既定の方法として、サイト上の新しいファイルに自動的に適用される、基となっている SharePoint サイトの Office 365 保持ラベル。</span><span class="sxs-lookup"><span data-stu-id="2907f-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="2907f-113">ユーザーがファイルを組織外と共有または組織外へ送信することを保持ラベルを使用してブロックする、データ損失防止 (DLP) ポリシー。</span><span class="sxs-lookup"><span data-stu-id="2907f-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="2907f-114">暗号化が有効になっている、規制の厳しいラベルの Office 365 秘密度ラベルまたはサブラベルおよびチームの Office 365 グループに対する共同作成者アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="2907f-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="2907f-115">ユーザーは Word、Excel、PowerPoint の [秘密度] メニュー バーのオプションから、チームの [**ファイル**] セクションに保存されているファイルにラベルまたはサブラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="2907f-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="2907f-116">この結果、秘密度ラベルが適用された構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2907f-116">Here is the resulting configuration with a sensitivity label.</span></span>

![セキュリティで保護されたチーム シナリオの構成](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="2907f-118">フェーズ 1: 厳しく規制されたデータ用のチームを構成する</span><span class="sxs-lookup"><span data-stu-id="2907f-118">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="2907f-119">エンド ツー エンド構成には次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2907f-119">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="2907f-120">ID と デバイス アクセスを構成する。</span><span class="sxs-lookup"><span data-stu-id="2907f-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="2907f-121">プライベート チームを作成する。</span><span class="sxs-lookup"><span data-stu-id="2907f-121">Create a team</span></span>
3. <span data-ttu-id="2907f-122">基となる SharePoint サイトを構成してセキュリティを強化する。</span><span class="sxs-lookup"><span data-stu-id="2907f-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="2907f-123">保持ラベルおよび DLP ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="2907f-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="2907f-124">厳しく規制されたラベル用のラベルまたはサブラベルを作成する。</span><span class="sxs-lookup"><span data-stu-id="2907f-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="2907f-125">手順 1: ID と デバイス アクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="2907f-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="2907f-126">チームおよびその基となっている SharePoint サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)と[推奨される SharePoint Online アクセス ポリシー](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2907f-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="2907f-127">手順 2: プライベート チームを作成する</span><span class="sxs-lookup"><span data-stu-id="2907f-127">Step 2: Create a private team</span></span>

<span data-ttu-id="2907f-128">[こちらの手順](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)を使用して、プライベート チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="2907f-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="2907f-129">プライベート チームを作成するときの既定のアクセス許可は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2907f-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="2907f-130">チームの Office 365 グループ (チーム グループ) には、グループの所有者とグループ メンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="2907f-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="2907f-131">チームの基になっている SharePoint サイト (チーム サイト) の場合:</span><span class="sxs-lookup"><span data-stu-id="2907f-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="2907f-132">サイト コレクション管理者がチーム グループ所有者に対して構成されます</span><span class="sxs-lookup"><span data-stu-id="2907f-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="2907f-133">チーム サイトの場合:</span><span class="sxs-lookup"><span data-stu-id="2907f-133">For the Team Site:</span></span> 
    - <span data-ttu-id="2907f-134">フル コントロールの権限レベルを持つチーム サイト所有者 SharePoint グループがチーム グループ所有者に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2907f-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="2907f-135">編集権限レベルを持つチーム サイト メンバー SharePoint グループがチーム グループ メンバーに設定されます。</span><span class="sxs-lookup"><span data-stu-id="2907f-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="2907f-136">読み取り権限レベルを持つチーム サイト閲覧者 SharePoint グループには、グループまたはユーザー アカウントはありません。</span><span class="sxs-lookup"><span data-stu-id="2907f-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="2907f-137">チーム サイトの既定のアクセス許可は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2907f-137">Here are the default permissions for the Team Site.</span></span>

![チーム サイトの既定のアクセス許可](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="2907f-139">編集権限レベルの \<チーム名> 所有者 SharePoint グループを表示しても、\<チーム名> 所有者は表示されません。</span><span class="sxs-lookup"><span data-stu-id="2907f-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="2907f-140">この結果、アクセス許可では次の操作が許可されます。</span><span class="sxs-lookup"><span data-stu-id="2907f-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="2907f-141">チーム グループの所有者がサイトを管理し、サイト コンテンツに対してフル コントロールを持つこと。</span><span class="sxs-lookup"><span data-stu-id="2907f-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="2907f-142">チーム グループ メンバーがサイト上でファイルを作成および編集すること。</span><span class="sxs-lookup"><span data-stu-id="2907f-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="2907f-143">アクセス許可の保守は、チーム メンバーおよび所有者の保守と同じです。</span><span class="sxs-lookup"><span data-stu-id="2907f-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="2907f-144">この結果、構成は現時点では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2907f-144">Here’s the resulting configuration so far.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 2](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="2907f-146">手順 3: 基となる SharePoint サイトを構成してセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="2907f-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="2907f-147">チーム サイトから、次のアクセス許可の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2907f-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="2907f-148">ツール バーで、設定アイコンをクリックし、[**サイトの権限**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2907f-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="2907f-149">[**サイトの権限**] ウィンドウで、[**共有の設定**] の [**共有設定を変更します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2907f-149">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="2907f-150">[**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2907f-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="2907f-151">[**アクセス要求の許可**] をオフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2907f-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="2907f-152">このように設定することで、チーム グループのメンバーがチーム サイトを他のメンバーと共有したり、メンバー以外のユーザーがチーム サイトへのアクセスを要求したりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="2907f-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="2907f-153">この結果、構成は現時点では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2907f-153">Here’s the resulting configuration so far.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 3](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="2907f-155">手順 4: 保持ラベルおよび DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2907f-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="2907f-156">[こちらの手順](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp)を使用して、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="2907f-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="2907f-157">(必要な場合は) 厳しく規制されたデータの保持ラベルを作成して公開します。</span><span class="sxs-lookup"><span data-stu-id="2907f-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="2907f-158">手順 1 で作成した保持ラベル用にチーム サイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="2907f-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="2907f-159">手順 2 で作成した保持ラベルを使用する厳しく規制されたデータ用の DLP ポリシーを作成し、ユーザーが組織外にファイルを送信するのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2907f-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="2907f-160">[DLP ポリシー テンプレート ](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates) に基づいて、追加の要件 (例: 医療業界や金融業界の規制のための要件) のためのポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2907f-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="2907f-161">この結果、構成は現時点では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2907f-161">Here’s the resulting configuration so far.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 4](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="2907f-163">手順 5: 厳しく規制されたラベル用のラベルまたはサブラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="2907f-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="2907f-164">すべてのユーザーが任意のファイルに適用できる、厳しく規制されたデータの秘密度ラベルとは異なり、セキュリティで保護されたチーム サイトでは独自のラベルまたはサブラベルが必要です。ラベルまたはサブラベルが割り当てられたファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2907f-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="2907f-165">暗号化され、暗号化はファイルと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="2907f-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="2907f-166">チーム グループのメンバーのみがファイルを開けるようにするよう、カスタムのアクセス許可が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2907f-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="2907f-167">チーム サイトに保存されているファイルに対してこの追加レベルのセキュリティ保護を行うには、サイト独自の新しい秘密度ラベルまたは厳しく規制されたファイルの一般的なラベルのサブラベルのいずれかを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2907f-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="2907f-168">ラベルの一覧にこれが表示されるのは、チーム グループのメンバーのみです。</span><span class="sxs-lookup"><span data-stu-id="2907f-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="2907f-169">全体での使用と個別のプライベート チームのいずれにおいても必要なラベルの数が少ない場合は、秘密度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2907f-169">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="2907f-170">ラベルを多数使用している場合、またはプライベート チーム用のラベルを厳しく規制されたラベルの下でまとめる場合は、秘密度サブラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2907f-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="2907f-171">[こちらの手順を使用して](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)、別のラベルまたはサブラベルを次の設定で構成します。</span><span class="sxs-lookup"><span data-stu-id="2907f-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="2907f-172">ラベルの名前に、チームの名前が含まれている。</span><span class="sxs-lookup"><span data-stu-id="2907f-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="2907f-173">暗号化が有効になっている。</span><span class="sxs-lookup"><span data-stu-id="2907f-173">Encryption is enabled.</span></span>
- <span data-ttu-id="2907f-174">サイト グループに、共同作成者のアクセス許可がある。</span><span class="sxs-lookup"><span data-stu-id="2907f-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="2907f-175">この結果、新しいラベルが適用された構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2907f-175">Here’s the resulting configuration with the new label.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 5](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="2907f-177">秘密度ラベルとチーム グループの関係は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2907f-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![チーム グループとラベルのアクセス許可の関係](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="2907f-179">秘密度ラベルまたはサブラベルをユーザー定義のアクセス許可用に構成した場合、または有効期限を付けて構成した場合は、ファイルは Teams または SharePoint から開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="2907f-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="2907f-180">Office アプリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2907f-180">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="2907f-181">カスタムのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2907f-181">Custom permissions</span></span>

<span data-ttu-id="2907f-182">チーム サイト用に SharePoint サイトのカスタムアクセス許可および (必要な場合は) 対応する秘密度ラベルを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2907f-182">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="2907f-183">2 つの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2907f-183">Here are two examples:</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="2907f-184">例 1: SharePoint サイトの管理を委任する</span><span class="sxs-lookup"><span data-stu-id="2907f-184">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="2907f-185">チームの所有者が SharePoint 管理者の経験がない場合、またはチーム サイトの管理を委任する場合は、チーム所有者のリストに SharePoint 管理者のユーザー アカウントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2907f-185">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="2907f-186">ただし、SharePoint 管理者は、チームとそのすべてのリソースへのフル アクセスを持ち、秘密度ラベルが適用されているファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2907f-186">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="2907f-187">このような、権限の過剰付与を防ぐには、高度なアクセス許可の設定で、SharePoint 管理者のユーザー アカウントをチーム サイト所有者 SharePoint グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="2907f-187">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="2907f-188">SharePoint 管理者はサイトを管理することはできますが、チームおよびそのリソースにアクセスすることも、秘密度ラベルが割り当てられているファイルを開くこともできません。</span><span class="sxs-lookup"><span data-stu-id="2907f-188">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="2907f-189">例 2: ラベル付きファイルへの表示線用アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="2907f-189">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="2907f-190">一部の社員が必要とするのはチーム サイトのラベル付きファイルの内容の表示のみである場合は、そうした社員の個人のユーザー アカウントを次に追加します。</span><span class="sxs-lookup"><span data-stu-id="2907f-190">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="2907f-191">\<チーム名> 閲覧者 SharePoint グループ。既定では、このグループは読み取り権限レベルを持ちます。</span><span class="sxs-lookup"><span data-stu-id="2907f-191">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="2907f-192">閲覧者権限付きの秘密度ラベル。</span><span class="sxs-lookup"><span data-stu-id="2907f-192">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="2907f-193">この結果、ラベルのアクセス許可は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2907f-193">Here are the resulting permissions on the label.</span></span>

![ラベル付きのファイルを閲覧するためのカスタム アクセス許可の例](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="2907f-195">サイトの訪問者はチーム サイトに直接アクセスして、サブラベルが適用されているファイルの内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2907f-195">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="2907f-196">ただし、訪問者はチーム グループのメンバーではないため、チームまたはチームのリソースにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2907f-196">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="2907f-197">フェーズ 2: チーム メンバーのユーザーによる導入を促す</span><span class="sxs-lookup"><span data-stu-id="2907f-197">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="2907f-198">チームを設置したら、このチームの導入とチーム メンバーへの追加のセキュリティを促します。</span><span class="sxs-lookup"><span data-stu-id="2907f-198">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="2907f-199">手順 1: ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="2907f-199">Step 1: Train your users</span></span>

<span data-ttu-id="2907f-200">チーム グループのメンバーは、チームおよびそのすべてのリソース (チャット、会議、およびその他のアプリなど) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2907f-200">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="2907f-201">チャネルの [**ファイル**] セクションにあるファイルで作業をする場合、チーム グループのメンバーは、セキュリティで保護されたチーム用に作成されたファイルに秘密度ラベルまたはサブラベルを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2907f-201">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="2907f-202">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2907f-202">Here’s an example.</span></span>

![セキュリティで保護されたチームのファイルに適用されるラベルの例](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="2907f-204">ラベルがファイルに適用されると、ファイルはセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="2907f-204">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="2907f-205">チーム グループのメンバーは、ファイルを Teams で開いてリアルタイムで共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="2907f-205">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="2907f-206">ファイルは暗号化され、チーム グループのメンバーには共同作成者アクセス許可が設定されます。</span><span class="sxs-lookup"><span data-stu-id="2907f-206">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="2907f-207">ファイルがサイトを離れて悪意のあるユーザーに転送された場合、そのようなユーザーがファイルを開いて内容を表示するには、チーム グループ メンバーのユーザー アカウントの資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2907f-207">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="2907f-208">チーム メンバーをトレーニングする:</span><span class="sxs-lookup"><span data-stu-id="2907f-208">Train your helpdesk team.</span></span>

- <span data-ttu-id="2907f-209">チーム サイトのチャット、会議、ファイル、その他のリソースに新しいチームを使用することの重要性と、厳しく規制されたデータのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。</span><span class="sxs-lookup"><span data-stu-id="2907f-209">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="2907f-210">チームにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="2907f-210">How to access the team.</span></span>
- <span data-ttu-id="2907f-211">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="2907f-211">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="2907f-212">DLP ポリシーを使用して、外部からのファイルの共有をできないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="2907f-212">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="2907f-213">チームのカスタム ラベルまたはサブラベルでファイルにラベルを付ける方法。</span><span class="sxs-lookup"><span data-stu-id="2907f-213">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="2907f-214">ファイルがサイトからリークされてもラベルまたはサブラベルによって保護されるしくみ。</span><span class="sxs-lookup"><span data-stu-id="2907f-214">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="2907f-215">このトレーニングには、チーム メンバーが上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="2907f-215">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="2907f-216">手順 2: 使用状況を定期的にレビューし、チーム メンバーのフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="2907f-216">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="2907f-217">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="2907f-217">In the weeks after training:</span></span>

- <span data-ttu-id="2907f-218">チーム メンバーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="2907f-218">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="2907f-219">チームの使用状況を分析し、それが期待された使用法と一致しているかを比較する。</span><span class="sxs-lookup"><span data-stu-id="2907f-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="2907f-220">厳しく規制されたファイルがカスタムの秘密度ラベルまたはサブラベルを使用して正しくラベル付けされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="2907f-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

  <span data-ttu-id="2907f-221">ラベルが割り当てられているファイルがわかるようにするには、SharePoint のフォルダーを表示し、[**列の追加**] で [**列の表示/非表示**] オプションを使用して [**秘密度**] 列を追加します。</span><span class="sxs-lookup"><span data-stu-id="2907f-221">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="2907f-222">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="2907f-222">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2907f-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="2907f-223">See also</span></span>

[<span data-ttu-id="2907f-224">厳しく規制されたデータ用の SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="2907f-224">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="2907f-225">Microsoft 365 Enterprise のワークロードとシナリオ</span><span class="sxs-lookup"><span data-stu-id="2907f-225">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="2907f-226">[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="2907f-226">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="2907f-227">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="2907f-227">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
