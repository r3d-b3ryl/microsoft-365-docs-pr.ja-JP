---
title: '近日公開予定: SharePoint を Microsoft Viva Learning の学習コンテンツ ソースとして構成する (プレビュー)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Microsoft Viva Learning (プレビュー) の学習コンテンツ ソースとして SharePoint を構成する方法について説明します。
ms.openlocfilehash: 2bed3a42d62e2aab2165ee38379eb07503807e6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333580"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="3f10c-103">近日公開予定: SharePoint を Microsoft Viva Learning の学習コンテンツ ソースとして構成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3f10c-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="3f10c-104">この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="3f10c-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="3f10c-105">SharePoint をラーニング コンテンツ ソースとして構成して、組織独自のコンテンツをビバ ラーニング (プレビュー) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="3f10c-106">概要</span><span class="sxs-lookup"><span data-stu-id="3f10c-106">Overview</span></span>

<span data-ttu-id="3f10c-107">ナレッジ管理者 (またはグローバル管理者) は、ラーニング サービスが構造化された SharePoint リストの形式で空の一元化された場所 (Learning App Content Repository) を作成できるサイト URL を提供します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="3f10c-108">このリストは、組織が学習コンテンツを含む会社間の SharePoint フォルダーへのリンクを格納するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="3f10c-109">管理者は、フォルダーの URL の一覧を収集およびキュレーションする責任があります。</span><span class="sxs-lookup"><span data-stu-id="3f10c-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="3f10c-110">これらのフォルダーには、ビバ ラーニング (プレビュー) で使用できるコンテンツのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f10c-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="3f10c-111">Viva Learning (プレビュー) では、次のドキュメントの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3f10c-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="3f10c-112">Word、PowerPoint、Excel、PDF</span><span class="sxs-lookup"><span data-stu-id="3f10c-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="3f10c-113">オーディオ (.m4a)</span><span class="sxs-lookup"><span data-stu-id="3f10c-113">Audio (.m4a)</span></span>
- <span data-ttu-id="3f10c-114">ビデオ (.mov、.mp4、.avi)</span><span class="sxs-lookup"><span data-stu-id="3f10c-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="3f10c-115">詳細については [、「SharePoint の制限」を参照してください](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="3f10c-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="3f10c-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3f10c-116">Permissions</span></span>

<span data-ttu-id="3f10c-117">ドキュメント ライブラリ フォルダー URL は、組織内の任意の SharePoint サイトから収集できます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="3f10c-118">Viva Learning (プレビュー) は、既存のすべてのコンテンツアクセス許可に従います。</span><span class="sxs-lookup"><span data-stu-id="3f10c-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="3f10c-119">したがって、ユーザーがアクセス許可を持つコンテンツだけが検索可能で、ビバ ラーニング (プレビュー) 内で表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="3f10c-120">これらのフォルダー内のコンテンツは検索可能ですが、個々の従業員がアクセス許可を持つコンテンツのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="3f10c-121">組織のリポジトリからのコンテンツの削除は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3f10c-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="3f10c-122">意図せずに表示されたコンテンツを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="3f10c-123">ドキュメント ライブラリへのアクセスを制限するには、[アクションの表示] オプション **を選択し** 、[アクセスの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![SharePoint のドキュメント ライブラリ ページで、[アクセスの管理] を使用して [アクションの表示] オプションを表示します。](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="3f10c-125">ドキュメント ライブラリ内の元のドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="3f10c-126">詳細については [、「SharePoint モダン エクスペリエンスでの共有とアクセス許可」を参照してください](/sharepoint/modern-experience-sharing-permissions)。</span><span class="sxs-lookup"><span data-stu-id="3f10c-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="3f10c-127">ラーニング サービス</span><span class="sxs-lookup"><span data-stu-id="3f10c-127">Learning Service</span></span>

<span data-ttu-id="3f10c-128">ラーニング サービスは、指定されたフォルダー URL を使用して、それらのフォルダーに格納されているすべてのコンテンツからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="3f10c-129">一元化されたリポジトリにフォルダー URL を指定して 24 時間以内に、従業員はビバ ラーニング (プレビュー) 内で組織のコンテンツを検索して使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="3f10c-130">更新されたメタデータやアクセス許可を含むコンテンツに対する変更はすべて、24 時間以内にラーニング サービスにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="3f10c-131">ソースとして SharePoint を構成する</span><span class="sxs-lookup"><span data-stu-id="3f10c-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="3f10c-132">これらのタスクを実行するには、Microsoft 365 グローバル管理者、SharePoint 管理者、またはナレッジ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f10c-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="3f10c-133">ビバ ラーニング (プレビュー) の学習コンテンツ ソースとして SharePoint を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="3f10c-134">Microsoft 365 管理センターの左側のナビゲーションで、[設定] [組織の設定]  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="3f10c-135">[組織の **設定] ページ** の [サービス] **タブで** 、[ビバ ラーニング **(プレビュー) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![リストされているビバ ラーニングを表示する Microsoft 365 管理センターの [設定] ページ。](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="3f10c-137">[ **ビバ ラーニング (プレビュー)]** パネルの [SharePoint] で、サイト URL を SharePoint サイトに提供し、このサイトでは、ビバ ラーニング (プレビュー) で一元的なリポジトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![SharePoint が選択されている Microsoft 365 管理センターの学習パネル。](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="3f10c-139">SharePoint リストは、指定された SharePoint サイト内に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![SharePoint サイト内で新しく作成された SharePoint リスト。](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="3f10c-141">SharePoint サイトの左側のナビゲーションで、[サイト コンテンツ] **[** アプリ コンテンツ  >  **リポジトリ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![[サイト コンテンツ] ナビゲーションと [学習アプリ コンテンツ リポジトリ] セクションを示す SharePoint リスト。](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="3f10c-143">[アプリ **コンテンツ リポジトリの学習** ] ページで、SharePoint リストに URL を入力して、学習コンテンツ フォルダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="3f10c-144">[新規 **] を** 選択して、[新しいアイテム] **パネルを表示** します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-144">Select **New** to view the **New item** panel.</span></span> 

       ![[新しい] オプションを示す SharePoint の [コンテンツ リポジトリの学習] ページ。](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="3f10c-146">[新しい **アイテム]** パネルの [ **タイトル** ] フィールドに、選択したディレクトリ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="3f10c-147">[フォルダー **URL]** フィールドで、URL を学習コンテンツ フォルダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="3f10c-148">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-148">Select **Save**.</span></span>

       ![タイトルとフォルダーの URL フィールドを示す SharePoint の新しいアイテム パネル。](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="3f10c-150">[ **アプリコンテンツ リポジトリの学習]** ページが新しい学習コンテンツで更新されます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![更新された情報を示す SharePoint の [コンテンツ リポジトリの学習] ページ。](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="3f10c-152">Learning App Content Repository へのより広範なアクセスを可能にするために、リストへのリンクは、ユーザーがアクセスを要求し、最終的にリストを設定するのに役立つ、ビバ ラーニング (プレビュー) インターフェイスですぐに利用できます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="3f10c-153">サイト所有者とグローバル管理者は、リストへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f10c-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="3f10c-154">アクセスはリストにのみ固有であり、リストが保存されているサイトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="3f10c-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="3f10c-155">詳細については、この記事の [後半の「自分の組織のコンテンツを提供](#provide-your-own-organizations-content) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f10c-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="3f10c-156">フォルダー URL ドキュメント ライブラリのキュレーション</span><span class="sxs-lookup"><span data-stu-id="3f10c-156">Folder URL document library curation</span></span>

<span data-ttu-id="3f10c-157">既定のメタデータ (変更日、作成日、ドキュメント名、コンテンツ タイプ、組織名など) は、Microsoft Graph API によって自動的にビバ ラーニング (プレビュー) に引き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="3f10c-158">コンテンツの全体的な検出と検索の関連性を向上させるために、[説明] 列を追加することをお **勧** めします。</span><span class="sxs-lookup"><span data-stu-id="3f10c-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="3f10c-159">ドキュメント ライブラリ ページに **[説明]** 列を追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="3f10c-160">[ドキュメント] **ページで、[** 列の追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="3f10c-161">[アクションの **表示] オプションを** 選択し、[単一 **行のテキスト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![[アクションの表示] オプションを表示する SharePoint の [ドキュメント] ページで、1 行のテキストが強調表示されます。](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="3f10c-163">[列 **の作成] パネル** の [ **名前** ] フィールドに、列のわかりやすい名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="3f10c-164">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-164">Select **Save**.</span></span>

     ![名前と他のフィールドを示す列パネルを SharePoint に作成します。](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="3f10c-166">[ドキュメント **] ページの** [説明] **列** で、アイテムごとにカスタム説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="3f10c-167">説明が指定されていない場合、Viva Learning (Preview) は、コンテンツを独自の SharePoint ライブラリからの内容として強調表示する既定のメッセージを提供します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![[説明] 列の説明を示す SharePoint の [ドキュメント] ページ。](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="3f10c-169">独自の組織のコンテンツを提供する</span><span class="sxs-lookup"><span data-stu-id="3f10c-169">Provide your own organization's content</span></span>

<span data-ttu-id="3f10c-170">ナレッジ管理者は、組織のラーニング アプリ コンテンツ リポジトリに SharePoint でアクセスし、組織間のドキュメント ライブラリへの参照を提供できます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="3f10c-171">これらのライブラリ内のコンテンツは、ビバ ラーニング (プレビュー) で学習コンテンツとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f10c-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="3f10c-172">[ビバ ラーニング (プレビュー)] で、[その他の **オプション** ]**(..) を選択し**、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![[その他のオプションと設定] オプションを示す SharePoint ライブラリ ページ。](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="3f10c-174">[設定 **] で**、[アクセス許可] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f10c-174">Under **Settings**, select **Permissions**.</span></span>

     ![SharePoint の [アクセス許可] と [アクセスの確認] オプションを表示する [設定] オプション ページ。](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="3f10c-176">[ **アクセスの確認]** を選択して、組織の一元化されたライブラリに接続します。</span><span class="sxs-lookup"><span data-stu-id="3f10c-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
