---
title: 厳しく規制されたデータに Teams で対応する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 最重要ファイルおよび機密ファイルを保存するためのセキュリティで保護されたチームを作成します。
ms.openlocfilehash: aeb3662d6c8a21cbd56d983515913750fd5259f1
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951972"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="07278-103">厳しく規制されたデータに Teams で対応する</span><span class="sxs-lookup"><span data-stu-id="07278-103">Teams for highly regulated data</span></span>

<span data-ttu-id="07278-104">この記事では、Microsoft Teams 内のプライベート チームを構成して、チャット、会議、ファイルなどの Teams の機能へのアクセスをチームの Office 365 グループのメンバーおよび所有者のみに制限するための推奨事項および手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="07278-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="07278-105">この記事では、Office 365 グループに基づくプライベート アクセスの他にも、それの基となっている、チーム チャネルの [**ファイル**] セクションからアクセスできるプライベート SharePoint チーム サイトを構成して厳しく規制されたデータの保存で必要な追加のセキュリティを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07278-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="07278-106">この SharePoint チーム サイトでは、ファイル、ページ、共有予定表、タスク、ノートブック、およびリストを保存して共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="07278-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

>[!Note]
> <span data-ttu-id="07278-107">SharePoint を使用する場合の類似のシナリオが[こちら](teams-sharepoint-online-sites-highly-regulated-data.md)にあります。</span><span class="sxs-lookup"><span data-stu-id="07278-107">A similar scenario using SharePoint is [here](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
>

<span data-ttu-id="07278-108">規制の厳しいデータ用にチームを構成する場合の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07278-108">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="07278-109">プライベート チームおよびそれに対応する、所有者とメンバーのユーザー アカウントを持つ Office 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="07278-109">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="07278-110">チームの基になっている SharePoint サイトでの以下の追加のセキュリティ:</span><span class="sxs-lookup"><span data-stu-id="07278-110">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="07278-111">サイト メンバーが他のユーザーへアクセス許可を付与することの防止。</span><span class="sxs-lookup"><span data-stu-id="07278-111">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="07278-112">サイトのメンバーではないユーザーがサイトへのアクセス権を要求することの防止。</span><span class="sxs-lookup"><span data-stu-id="07278-112">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="07278-113">アイテム保持ポリシーを定義する既定の方法として、サイト上の新しいファイルに自動的に適用される、基となっている SharePoint サイトの Office 365 保持ラベル。</span><span class="sxs-lookup"><span data-stu-id="07278-113">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="07278-114">ユーザーがファイルを組織外と共有または組織外へ送信することを保持ラベルを使用してブロックする、データ損失防止 (DLP) ポリシー。</span><span class="sxs-lookup"><span data-stu-id="07278-114">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="07278-115">暗号化が有効になっている、規制の厳しいラベルの Office 365 秘密度ラベルまたはサブラベルおよびチームの Office 365 グループに対する共同作成者アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="07278-115">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="07278-116">ユーザーはチームの [**ファイル**] セクションに保存されているファイルにラベルまたはサブラベルを Word、Excel、PowerPoint の [**秘密度**] メニュー バーのオプションから適用します。</span><span class="sxs-lookup"><span data-stu-id="07278-116">Users apply the label or sublabel to files stored in **Files** section of the team from the **Sensitivity** menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="07278-117">この結果、秘密度ラベルが適用された構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07278-117">Here is the resulting configuration with a sensitivity label.</span></span>

![セキュリティで保護されたチーム シナリオの構成](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="07278-119">概要については、この短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07278-119">For a quick overview, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="07278-120">このシナリオを 1 ページにまとめた概要については、「[厳しく規制されたデータ用の Teams のポスター](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07278-120">For a 1-page summary of this scenario, see the [Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="07278-121">[![厳しく規制されたデータ用の Teams のポスター](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="07278-121">[![Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="07278-122">このポスターを [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) または [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) 形式でダウンロードして、レター、リーガル、タブロイド (11 x 17) のサイズの紙に印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="07278-122">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="07278-123">フェーズ 1: 厳しく規制されたデータ用のチームを構成する</span><span class="sxs-lookup"><span data-stu-id="07278-123">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="07278-124">エンド ツー エンド構成には次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="07278-124">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="07278-125">ID と デバイス アクセスを構成する。</span><span class="sxs-lookup"><span data-stu-id="07278-125">Configure identity and device access.</span></span>
2. <span data-ttu-id="07278-126">プライベート チームを作成する。</span><span class="sxs-lookup"><span data-stu-id="07278-126">Create a private team.</span></span>
3. <span data-ttu-id="07278-127">基となる SharePoint サイトを構成してセキュリティを強化する。</span><span class="sxs-lookup"><span data-stu-id="07278-127">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="07278-128">保持ラベルおよび DLP ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="07278-128">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="07278-129">厳しく規制されたラベル用のラベルまたはサブラベルを作成する。</span><span class="sxs-lookup"><span data-stu-id="07278-129">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="07278-130">手順 1: ID と デバイス アクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="07278-130">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="07278-131">チームおよびその基となっている SharePoint サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)と[推奨される SharePoint Online アクセス ポリシー](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07278-131">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="07278-132">手順 2: プライベート チームを作成する</span><span class="sxs-lookup"><span data-stu-id="07278-132">Step 2: Create a private team</span></span>

<span data-ttu-id="07278-133">[こちらの手順](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)を使用して、プライベート チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="07278-133">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="07278-134">プライベート チームを作成するときの既定のアクセス許可は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07278-134">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="07278-135">チームの Office 365 グループ (チーム グループ) には、グループの所有者とグループ メンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="07278-135">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="07278-136">チームの基になっている SharePoint サイト (チーム サイト) の場合:</span><span class="sxs-lookup"><span data-stu-id="07278-136">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="07278-137">サイト コレクション管理者がチーム グループ所有者に対して構成されます</span><span class="sxs-lookup"><span data-stu-id="07278-137">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="07278-138">チーム サイトの場合:</span><span class="sxs-lookup"><span data-stu-id="07278-138">For the Team Site:</span></span> 
    - <span data-ttu-id="07278-139">フル コントロールの権限レベルを持つチーム サイト所有者 SharePoint グループがチーム グループ所有者に設定されます。</span><span class="sxs-lookup"><span data-stu-id="07278-139">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="07278-140">編集権限レベルを持つチーム サイト メンバー SharePoint グループがチーム グループ メンバーに設定されます。</span><span class="sxs-lookup"><span data-stu-id="07278-140">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="07278-141">読み取り権限レベルを持つチーム サイト閲覧者 SharePoint グループには、グループまたはユーザー アカウントはありません。</span><span class="sxs-lookup"><span data-stu-id="07278-141">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="07278-142">チーム サイトの既定のアクセス許可は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07278-142">Here are the default permissions for the Team Site.</span></span>

![チーム サイトの既定のアクセス許可](../media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="07278-144">編集権限レベルの \<チーム名> 所有者 SharePoint グループを表示しても、\<チーム名> 所有者は表示されません。</span><span class="sxs-lookup"><span data-stu-id="07278-144">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="07278-145">この結果、アクセス許可では次の操作が許可されます。</span><span class="sxs-lookup"><span data-stu-id="07278-145">The resulting permissions allow:</span></span>

- <span data-ttu-id="07278-146">チーム グループの所有者がサイトを管理し、サイト コンテンツに対してフル コントロールを持つこと。</span><span class="sxs-lookup"><span data-stu-id="07278-146">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="07278-147">チーム グループ メンバーがサイト上でファイルを作成および編集すること。</span><span class="sxs-lookup"><span data-stu-id="07278-147">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="07278-148">アクセス許可の保守は、チーム メンバーおよび所有者の保守と同じです。</span><span class="sxs-lookup"><span data-stu-id="07278-148">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="07278-149">この結果、構成は現時点では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07278-149">Here’s the resulting configuration so far.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 2](../media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="07278-151">手順 3: 基となる SharePoint サイトを構成してセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="07278-151">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="07278-152">チーム サイトから、次のアクセス許可の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07278-152">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="07278-153">ツール バーで、設定アイコンをクリックし、[**サイトの権限**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07278-153">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="07278-154">[**サイトの権限**] ウィンドウで、[**共有の設定**] の [**共有設定を変更します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07278-154">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="07278-155">[**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07278-155">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="07278-156">[**アクセス要求の許可**] をオフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07278-156">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="07278-157">このように設定することで、チーム グループのメンバーがチーム サイトを他のメンバーと共有したり、メンバー以外のユーザーがチーム サイトへのアクセスを要求したりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="07278-157">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="07278-158">この結果、構成は現時点では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07278-158">Here’s the resulting configuration so far.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 3](../media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="07278-160">手順 4: 保持ラベルおよび DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="07278-160">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="07278-161">[こちらの手順](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)を使用して、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="07278-161">Use [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) to:</span></span>

1. <span data-ttu-id="07278-162">(必要な場合は) 厳しく規制されたデータの保持ラベルを作成して公開します。</span><span class="sxs-lookup"><span data-stu-id="07278-162">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="07278-163">手順 1 で作成した保持ラベル用にチーム サイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="07278-163">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="07278-164">手順 2 で作成した保持ラベルを使用する厳しく規制されたデータ用の DLP ポリシーを作成し、ユーザーが組織外にファイルを送信するのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="07278-164">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="07278-165">[DLP ポリシー テンプレート ](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates) に基づいて、追加の要件 (例: 医療業界や金融業界の規制のための要件) のためのポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="07278-165">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="07278-166">この結果、構成は現時点では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07278-166">Here’s the resulting configuration so far.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 4](../media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-a-sensitivity-label-or-a-sublabel-of-the-highly-regulated-sensitivity-label"></a><span data-ttu-id="07278-168">手順 5: 厳しく規制された機密度ラベル用の機密度ラベルまたはサブラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="07278-168">Step 5: Create a sensitivity label or a sublabel of the highly regulated sensitivity label</span></span>

<span data-ttu-id="07278-169">すべてのユーザーが任意のファイルに適用できる、厳しく規制されたデータの秘密度ラベルとは異なり、セキュリティで保護されたチーム サイトでは独自のラベルまたはサブラベルが必要です。ラベルまたはサブラベルが割り当てられたファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07278-169">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="07278-170">暗号化され、暗号化はファイルと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="07278-170">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="07278-171">チーム グループのメンバーのみがファイルを開けるようにするよう、カスタムのアクセス許可が含まれます。</span><span class="sxs-lookup"><span data-stu-id="07278-171">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="07278-172">チーム サイトに保存されているファイルに対してこの追加レベルのセキュリティ保護を行うには、サイト独自の新しい秘密度ラベルまたは厳しく規制されたファイルの一般的なラベルのサブラベルのいずれかを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07278-172">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="07278-173">ラベルの一覧にこれが表示されるのは、チーム グループのメンバーのみです。</span><span class="sxs-lookup"><span data-stu-id="07278-173">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="07278-174">全体での使用と個別のプライベート チームの両方に対して少ない数のラベルが必要な場合は、秘密度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="07278-174">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="07278-175">ラベルを多数使用している場合、またはプライベート チーム用のラベルを厳しく規制されたラベルの下でまとめる場合は、秘密度サブラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="07278-175">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="07278-176">[こちらの手順を使用して](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)、別のラベルまたはサブラベルを次の設定で構成します。</span><span class="sxs-lookup"><span data-stu-id="07278-176">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="07278-177">ラベルの名前に、チームの名前が含まれている。</span><span class="sxs-lookup"><span data-stu-id="07278-177">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="07278-178">暗号化が有効になっている。</span><span class="sxs-lookup"><span data-stu-id="07278-178">Encryption is enabled</span></span>
- <span data-ttu-id="07278-179">サイト グループに、共同作成者のアクセス許可がある。</span><span class="sxs-lookup"><span data-stu-id="07278-179">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="07278-180">この結果、新しいラベルが適用された構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07278-180">Here’s the resulting configuration with the new label.</span></span>

![セキュリティで保護されたチーム シナリオの構成の手順 5](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="07278-182">秘密度ラベルとチーム グループの関係は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07278-182">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![チーム グループとラベルのアクセス許可の関係](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="07278-184">秘密度ラベルまたはサブラベルをユーザー定義のアクセス許可用に構成した場合、または有効期限を付けて構成した場合は、ファイルは Teams または SharePoint から開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="07278-184">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="07278-185">Office アプリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07278-185">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="07278-186">カスタムのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="07278-186">Custom permissions</span></span>

<span data-ttu-id="07278-187">チーム サイト用に SharePoint サイトのカスタムアクセス許可および (必要な場合は) 対応する秘密度ラベルを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="07278-187">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="07278-188">2 つの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07278-188">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="07278-189">例 1: SharePoint サイトの管理を委任する</span><span class="sxs-lookup"><span data-stu-id="07278-189">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="07278-190">チームの所有者が SharePoint 管理者の経験がない場合、またはチーム サイトの管理を委任する場合は、チーム所有者のリストに SharePoint 管理者のユーザー アカウントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="07278-190">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="07278-191">ただし、SharePoint 管理者は、チームとそのすべてのリソースへのフル アクセスを持ち、秘密度ラベルが適用されているファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="07278-191">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="07278-192">このような、権限の過剰付与を防ぐには、高度なアクセス許可の設定で、SharePoint 管理者のユーザー アカウントをチーム サイト所有者 SharePoint グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="07278-192">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="07278-193">SharePoint 管理者はサイトを管理することはできますが、チームおよびそのリソースにアクセスすることも、秘密度ラベルが割り当てられているファイルを開くこともできません。</span><span class="sxs-lookup"><span data-stu-id="07278-193">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="07278-194">例 2: ラベル付きファイルへの表示線用アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="07278-194">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="07278-195">一部の社員が必要とするのはチーム サイトのラベル付きファイルの内容の表示のみである場合は、そうした社員の個人のユーザー アカウントを次に追加します。</span><span class="sxs-lookup"><span data-stu-id="07278-195">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="07278-196">\<チーム名> 閲覧者 SharePoint グループ。既定では、このグループは読み取り権限レベルを持ちます。</span><span class="sxs-lookup"><span data-stu-id="07278-196">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="07278-197">閲覧者権限付きの秘密度ラベル。</span><span class="sxs-lookup"><span data-stu-id="07278-197">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="07278-198">この結果、ラベルのアクセス許可は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07278-198">Here are the resulting permissions on the label.</span></span>

![ラベル付きのファイルを閲覧するためのカスタム アクセス許可の例](../media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="07278-200">サイトの訪問者はチーム サイトに直接アクセスして、サブラベルが適用されているファイルの内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="07278-200">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="07278-201">ただし、訪問者はチーム グループのメンバーではないため、チームまたはチームのリソースにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="07278-201">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="07278-202">フェーズ 2: チーム メンバーのユーザーによる導入を促す</span><span class="sxs-lookup"><span data-stu-id="07278-202">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="07278-203">チームを設置したら、このチームの導入とチーム メンバーへの追加のセキュリティを促します。</span><span class="sxs-lookup"><span data-stu-id="07278-203">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="07278-204">手順 1: ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="07278-204">Step 1: Train your users</span></span>

<span data-ttu-id="07278-205">チーム グループのメンバーは、チームおよびそのすべてのリソース (チャット、会議、およびその他のアプリなど) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="07278-205">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="07278-206">チャネルの [**ファイル**] セクションにあるファイルで作業をする場合、チーム グループのメンバーは、セキュリティで保護されたチーム用に作成されたファイルに秘密度ラベルまたはサブラベルを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="07278-206">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="07278-207">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07278-207">Here’s an example.</span></span>

![セキュリティで保護されたチームのファイルに適用されるラベルの例](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="07278-209">ラベルがファイルに適用されると、ファイルはセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="07278-209">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="07278-210">チーム グループのメンバーは、ファイルを Teams で開いてリアルタイムで共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="07278-210">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="07278-211">ファイルは暗号化され、チーム グループのメンバーには共同作成者アクセス許可が設定されます。</span><span class="sxs-lookup"><span data-stu-id="07278-211">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="07278-212">ファイルがサイトを離れて悪意のあるユーザーに転送された場合、そのようなユーザーがファイルを開いて内容を表示するには、チーム グループ メンバーのユーザー アカウントの資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07278-212">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="07278-213">チーム メンバーをトレーニングする:</span><span class="sxs-lookup"><span data-stu-id="07278-213">Train your team members:</span></span>

- <span data-ttu-id="07278-214">チーム サイトのチャット、会議、ファイル、その他のリソースに新しいチームを使用することの重要性と、厳しく規制されたデータのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。</span><span class="sxs-lookup"><span data-stu-id="07278-214">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="07278-215">チームにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="07278-215">How to access the team.</span></span>
- <span data-ttu-id="07278-216">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="07278-216">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="07278-217">DLP ポリシーを使用して、外部からのファイルの共有をできないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="07278-217">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="07278-218">チームのカスタム ラベルまたはサブラベルでファイルにラベルを付ける方法。</span><span class="sxs-lookup"><span data-stu-id="07278-218">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="07278-219">ファイルがサイトからリークされてもラベルまたはサブラベルによって保護されるしくみ。</span><span class="sxs-lookup"><span data-stu-id="07278-219">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="07278-220">このトレーニングには、チーム メンバーが上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="07278-220">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="07278-221">手順 2: 使用状況を定期的にレビューし、チーム メンバーのフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="07278-221">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="07278-222">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="07278-222">In the weeks after training:</span></span>

- <span data-ttu-id="07278-223">チーム メンバーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="07278-223">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="07278-224">チームの使用状況を分析し、それが期待された使用法と一致しているかを比較する。</span><span class="sxs-lookup"><span data-stu-id="07278-224">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="07278-225">厳しく規制されたファイルがカスタムの秘密度ラベルまたはサブラベルを使用して正しくラベル付けされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="07278-225">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="07278-226">ラベルが割り当てられているファイルがわかるようにするには、SharePoint のフォルダーを表示し、[**列の追加**] で [**列の表示/非表示**] オプションを使用して [**秘密度**] 列を追加します。</span><span class="sxs-lookup"><span data-stu-id="07278-226">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="07278-227">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="07278-227">Retrain your users as needed.</span></span>

## <a name="demonstrate-this-in-a-test-environment"></a><span data-ttu-id="07278-228">テスト環境でこれを実証する</span><span class="sxs-lookup"><span data-stu-id="07278-228">Demonstrate this in a test environment</span></span>

<span data-ttu-id="07278-229">機密ファイルおよび非常に機密性の高いファイルに適したチームのテストを行う独自のテスト環境を構築するには、[これらの手順](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07278-229">To build out your own test environment to test teams for sensitive and highly confidential files, see [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span></span> 

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)

## <a name="how-the-contoso-corporation-used-a-secure-team-for-a-top-secret-project"></a><span data-ttu-id="07278-231">Contoso Corporation が極秘プロジェクトでどのように安全なチームを運用したか</span><span class="sxs-lookup"><span data-stu-id="07278-231">How the Contoso Corporation used a secure team for a top-secret project</span></span>

<span data-ttu-id="07278-232">架空の企業、Contoso Corporation は、代表的な世界規模の製造業の複合企業です。</span><span class="sxs-lookup"><span data-stu-id="07278-232">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="07278-233">極秘プロジェクトを開発、市場に投入し、新しい製品とサービスを提供するために、Contoso がどのように[セキュリティが強化されたチーム](contoso-team-for-top-secret-project.md)を構成し、採用を推進したかついて説明します。</span><span class="sxs-lookup"><span data-stu-id="07278-233">See how Contoso configured and drove the adoption of a [secure team](contoso-team-for-top-secret-project.md) for a top secret project to develop and bring to market a new set of products and services.</span></span> 

## <a name="see-also"></a><span data-ttu-id="07278-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="07278-234">See also</span></span>

[<span data-ttu-id="07278-235">厳しく規制されたデータ用の SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="07278-235">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="07278-236">Microsoft 365 Enterprise のワークロードとシナリオ</span><span class="sxs-lookup"><span data-stu-id="07278-236">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="07278-237">[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="07278-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="07278-238">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="07278-238">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
