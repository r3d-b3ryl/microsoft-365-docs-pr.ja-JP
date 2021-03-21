---
title: SharePoint 管理センターで Information Rights Management (IRM) を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: SharePoint リストとドキュメント ライブラリを保護するために、Microsoft Azure Active Directory Rights Management サービス (RMS) を介して SharePoint Online IRM を使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919403"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="db437-103">SharePoint 管理センターで Information Rights Management (IRM) を設定する</span><span class="sxs-lookup"><span data-stu-id="db437-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="db437-104">SharePoint Online では、リストおよびライブラリのレベルでファイルに IRM 保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="db437-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="db437-105">組織で IRM 保護を使用するには、まず、Rights Management をセットアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="db437-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="db437-106">IRM は Azure Information Protection の Azure Rights Management サービスを利用して、暗号化と使用制限の割り当てを実施します。</span><span class="sxs-lookup"><span data-stu-id="db437-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="db437-107">一部の Microsoft 365 プランには Azure Rights Management が含まれますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="db437-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="db437-108">詳細については、「アプリケーションとサービス [が Azure Rights Management をOfficeする方法」を参照してください](/azure/information-protection/understand-explore/office-apps-services-support)。</span><span class="sxs-lookup"><span data-stu-id="db437-108">To learn more, read [How Office applications and services support Azure Rights Management](/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="db437-109">SharePoint 管理センターを使用して IRM サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="db437-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="db437-110">組織が SharePoint リストとライブラリを IRM で保護するには、まず組織の Rights Management サービスをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db437-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="db437-111">詳細については [、「Azure Rights Management のアクティブ化」を参照してください](/information-protection/deploy-use/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="db437-111">To learn how see [Activating Azure Rights Management](/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="db437-112">Rights Management サービスを有効にするには、グローバル管理者特権を持つ仕事または学校のアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db437-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="db437-113">それ以外の場合は、SharePoint Online で IRM 機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="db437-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="db437-114">Rights Management サービスをアクティブ化した後、SharePoint 管理センターにサインインして IRM を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="db437-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="db437-115">グローバル管理者または SharePoint 管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="db437-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="db437-116">左上のアプリ起動ツールのアイコン ![Office 365 のアプリ起動ツールのアイコン](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) を選択し、**[管理者]** を選択して Microsoft 365 管理センターを開きます</span><span class="sxs-lookup"><span data-stu-id="db437-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="db437-117">([管理者] タイルが表示されていない場合は、組織内に管理者のアクセス許可を持つ必要があります)。</span><span class="sxs-lookup"><span data-stu-id="db437-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="db437-118">左側のウィンドウで、**[管理センター]** \> **[SharePoint]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="db437-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="db437-119">左側のウィンドウで、[設定] を **選択し**、[クラシック設定] **ページを選択します**。</span><span class="sxs-lookup"><span data-stu-id="db437-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="db437-120">[Information **Rights Management (IRM) セクションで** 、[構成で指定された IRM サービスを使用する] を選択し **、[IRM** 設定の更新] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="db437-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="db437-121">IRM 設定を更新すると、組織内のユーザーは SharePoint リストとドキュメント ライブラリで IRM の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="db437-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="db437-122">ただし、これを行うオプションは、[ライブラリの設定] と [リストの設定] に表示されるのに最大で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="db437-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="db437-123">IRM-enable SharePoint ドキュメント ライブラリとリスト</span><span class="sxs-lookup"><span data-stu-id="db437-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="db437-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="db437-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="db437-125">IRM 設定を更新すると、サイト所有者は自分の SharePoint リストとドキュメント ライブラリを IRM で保護できます。</span><span class="sxs-lookup"><span data-stu-id="db437-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="db437-126">詳細については、「Apply [Information Rights Management to a list or library」を参照してください](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="db437-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="db437-127">サイト所有者がリストまたはライブラリの IRM を有効にした場合、そのリストまたはライブラリでサポートされているファイルの種類を保護できます。</span><span class="sxs-lookup"><span data-stu-id="db437-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="db437-128">IRM がライブラリに対して有効になっている場合、権限管理はそのライブラリ内のすべてのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="db437-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="db437-129">リストの IRM を有効にした場合、権限管理は、実際のリスト アイテムではなく、リスト アイテムに添付されているファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="db437-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="db437-130">ユーザーが IRM が有効なリストまたはライブラリ内のファイルをダウンロードすると、ファイルは暗号化され、承認されたユーザーのみがファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="db437-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="db437-131">各権限管理ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスも含まれている。</span><span class="sxs-lookup"><span data-stu-id="db437-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="db437-132">一般的な制限としては、ファイルの読み取り専用化、テキストのコピーの無効化、ユーザーによるローカル コピーの保存の防止、ファイルの印刷の防止が含まれます。</span><span class="sxs-lookup"><span data-stu-id="db437-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="db437-133">IRM でサポートされているファイルの種類を読み取るクライアント プログラムは、権限管理ファイル内の発行ライセンスを使用して、これらの制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="db437-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="db437-134">これは、権限で管理されたファイルがダウンロードされた後でも保護を保持する方法です。</span><span class="sxs-lookup"><span data-stu-id="db437-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="db437-135">リストまたはライブラリで IRM を有効にするには、「情報権限管理をリストまたはライブラリに適用 [する」を参照してください](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="db437-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="db437-136">IRM が有効なライブラリ内のドキュメントを作成または編集するには、ブラウザー Officeを使用します。</span><span class="sxs-lookup"><span data-stu-id="db437-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="db437-137">代わりに、一度に 1 人のユーザーが IRM で暗号化されたファイルをダウンロードして編集できます。</span><span class="sxs-lookup"><span data-stu-id="db437-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="db437-138">チェックインとチェックアウトを使用して、複数のユーザー間で共同  *編集、または*  オーサリングを管理します。</span><span class="sxs-lookup"><span data-stu-id="db437-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="db437-139">IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Microsoft 365 は保護された PDF ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="db437-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="db437-140">ファイルの拡張子は変更されませんが、ファイルは保護されています。</span><span class="sxs-lookup"><span data-stu-id="db437-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="db437-141">このファイルを表示するには、Azure Information Protection ビューアー、Azure Information Protection クライアント全体、または保護された PDF ファイルの表示をサポートする別のアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="db437-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="db437-142">SharePoint Online では、次の種類のファイルの暗号化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="db437-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="db437-143">PDF</span><span class="sxs-lookup"><span data-stu-id="db437-143">PDF</span></span>
    
- <span data-ttu-id="db437-144">Word、Excel、PowerPoint の 97-2003 ファイル形式は、次Microsoft Officeプログラムの形式です。</span><span class="sxs-lookup"><span data-stu-id="db437-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="db437-145">次Officeプログラムの Open XML Microsoft Office形式: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="db437-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="db437-146">XML 用紙仕様 (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="db437-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="db437-147">SharePoint はアップロード時にドキュメントを開く必要があるので、保護されたドキュメント (デジタル署名された PDF ファイルなど) には IRM 保護を適用できません。</span><span class="sxs-lookup"><span data-stu-id="db437-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="db437-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="db437-148">Next steps</span></span>
<span data-ttu-id="db437-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="db437-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="db437-150">SharePoint Online の IRM を有効にしたら、リストとライブラリへの権限管理の適用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="db437-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="db437-151">詳細については、「 [情報権限管理をリストまたはライブラリに適用する」を参照してください](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="db437-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="db437-152">Windows 用の新しい OneDrive 同期クライアントは、IRM で保護された SharePoint ドキュメント ライブラリと OneDrive の場所の同期をサポートしています (ライブラリの IRM 設定がドキュメント アクセス権を期限切れに設定されていない限り)。</span><span class="sxs-lookup"><span data-stu-id="db437-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="db437-153">詳細については、または新しい同期クライアントの展開を開始するには、「新しい OneDrive 同期クライアントを Windows 用に展開する」を [参照してください](/onedrive/deploy-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="db437-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="db437-154">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="db437-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)