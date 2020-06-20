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
description: Microsoft Azure Active Directory Rights Management Services (RMS) を使用して SharePoint Online IRM を使用して SharePoint リストとドキュメントライブラリを保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33e5a72ea1d0733656379bc4efdca7dd14f78cb1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819197"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="7b5fa-103">SharePoint 管理センターで Information Rights Management (IRM) を設定する</span><span class="sxs-lookup"><span data-stu-id="7b5fa-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="7b5fa-104">SharePoint Online では、リストおよびライブラリのレベルでファイルに IRM 保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="7b5fa-105">組織で IRM 保護を使用するには、まず、Rights Management をセットアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="7b5fa-106">IRM は Azure Information Protection の Azure Rights Management サービスを利用して、暗号化と使用制限の割り当てを実施します。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="7b5fa-107">一部の Microsoft 365 プランには、Azure Rights Management は含まれていますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="7b5fa-108">詳細については、「 [Office アプリケーションとサービスが Azure Rights Management をサポートする方法](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-108">To learn more, read [How Office applications and services support Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="7b5fa-109">SharePoint 管理センターを使用して IRM サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="7b5fa-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="7b5fa-110">組織で SharePoint リストとライブラリを IRM で保護するには、まず、組織の Rights Management サービスをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="7b5fa-111">[Azure Rights Management をアクティブ化](https://docs.microsoft.com/information-protection/deploy-use/activate-service)する方法については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-111">To learn how see [Activating Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="7b5fa-112">Rights Management サービスを有効にするには、グローバル管理者特権を持つ職場または学校のアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="7b5fa-113">そうしないと、SharePoint Online で IRM 機能を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="7b5fa-114">Rights Management サービスをアクティブ化した後、SharePoint 管理センターにサインインして IRM を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="7b5fa-115">グローバル管理者または SharePoint 管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="7b5fa-116">左上のアプリ起動ツールのアイコン ![Office 365 のアプリ起動ツールのアイコン](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) を選択し、**[管理者]** を選択して Microsoft 365 管理センターを開きます</span><span class="sxs-lookup"><span data-stu-id="7b5fa-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="7b5fa-117">(管理者のタイルが表示されていない場合は、組織の管理者権限がありません。)</span><span class="sxs-lookup"><span data-stu-id="7b5fa-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="7b5fa-118">左側のウィンドウで、**[管理センター]** \> **[SharePoint]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="7b5fa-119">左側のウィンドウで、[**設定**] を選択し、[**クラシック設定] ページ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="7b5fa-120">[ **Information Rights Management (irm)** ] セクションで、[**構成で指定された Irm サービスを使用する**] を選択し、[ **irm 設定の更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="7b5fa-121">IRM 設定を更新した後、組織内のユーザーは、SharePoint リストとドキュメントライブラリで IRM を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="7b5fa-122">ただし、[ライブラリの設定] および [リストの設定] に表示されるまでに最大1時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="7b5fa-123">IRM-SharePoint ドキュメントライブラリとリストを有効にする</span><span class="sxs-lookup"><span data-stu-id="7b5fa-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="7b5fa-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="7b5fa-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="7b5fa-125">IRM 設定を更新すると、サイト所有者は SharePoint リストとドキュメントライブラリを IRM で保護できます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="7b5fa-126">詳細については、「[リストまたはライブラリに Information Rights Management を適用する](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7b5fa-127">サイト所有者は、リストまたはライブラリで IRM を有効にすると、そのリストまたはライブラリでサポートされているファイルの種類を保護できます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="7b5fa-128">ライブラリで IRM が有効になっている場合、rights management はそのライブラリ内のすべてのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="7b5fa-129">リストに対して IRM を有効にする場合、rights management は、実際のリストアイテムではなく、リストアイテムに添付されているファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="7b5fa-130">ユーザーが IRM 対応リストまたはライブラリにファイルをダウンロードすると、承認されたユーザーのみがファイルを表示できるように、ファイルが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="7b5fa-131">また、各権限管理ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="7b5fa-132">一般的な制限としては、ファイルを読み取り専用にし、テキストのコピーを無効にして、ユーザーがローカルコピーを保存しないようにしたり、ファイルを印刷できないようにしたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="7b5fa-133">IRM がサポートするファイルの種類を読み取ることができるクライアントプログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="7b5fa-134">これは、権限が管理されたファイルがダウンロードされた後も保護を保持する方法です。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="7b5fa-135">リストまたはライブラリで IRM を有効にするには、「[リストまたはライブラリへの Information Rights Management の適用](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7b5fa-136">ブラウザーで Office を使用して、IRM が有効なライブラリ内のドキュメントを作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="7b5fa-137">代わりに、一度に1人のユーザーが IRM で暗号化されたファイルをダウンロードして編集することができます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="7b5fa-138">チェックインとチェックアウトを使用して、複数のユーザーにまたがる*共同編集*または作成を管理します。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="7b5fa-139">IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Microsoft 365 は保護された PDF ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="7b5fa-140">ファイルの拡張子は変わりませんが、ファイルは保護されます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="7b5fa-141">このファイルを表示するには、Azure Information Protection viewer、完全な Azure Information Protection クライアント、または保護された PDF ファイルの表示をサポートする別のアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="7b5fa-142">SharePoint Online では、次の種類のファイルの暗号化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="7b5fa-143">PDF</span><span class="sxs-lookup"><span data-stu-id="7b5fa-143">PDF</span></span>
    
- <span data-ttu-id="7b5fa-144">次の Microsoft Office プログラムの97-2003 ファイル形式: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7b5fa-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="7b5fa-145">Office Open XML 形式の次の Microsoft Office プログラム: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7b5fa-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="7b5fa-146">XML Paper Specification (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="7b5fa-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="7b5fa-147">SharePoint はアップロード時にドキュメントを開く必要があるため、IRM 保護を保護されたドキュメント (デジタル署名された PDF ファイルなど) に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7b5fa-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="7b5fa-148">Next steps</span></span>
<span data-ttu-id="7b5fa-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="7b5fa-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="7b5fa-150">SharePoint Online の IRM を有効にしたら、[リストとライブラリへの rights management の適用] を開始できます。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="7b5fa-151">詳細については、「[リストまたはライブラリに Information Rights Management を適用する](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7b5fa-152">SharePoint 用の新しい OneDrive 同期クライアントでは、IRM で保護された SharePoint ドキュメントライブラリと OneDrive の場所の同期がサポートされるようになりました (ライブラリの IRM 設定でドキュメントアクセス権の有効期限が設定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="7b5fa-153">詳細については、または新しい同期クライアントの展開を開始するには、「 [Windows 用の新しい OneDrive 同期クライアントを展開](https://docs.microsoft.com/onedrive/deploy-on-windows)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5fa-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](https://docs.microsoft.com/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="7b5fa-154">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7b5fa-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)
