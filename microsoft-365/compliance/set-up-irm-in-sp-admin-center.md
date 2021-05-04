---
title: SharePoint 管理センターにおける Information Rights Management (IRM) の設定
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
description: Microsoft Azure Active Directory Rights Management サービス (RMS) を通じて SharePoint Online IRM を使用し、SharePoint リストやドキュメント ライブラリを保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919403"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="02f11-103">SharePoint 管理センターにおける Information Rights Management (IRM) の設定</span><span class="sxs-lookup"><span data-stu-id="02f11-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="02f11-104">SharePoint Online では、リストおよびライブラリのレベルでファイルに IRM 保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="02f11-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="02f11-105">組織で IRM 保護を使用するには、まず、Rights Management をセットアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f11-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="02f11-106">IRM は Azure Information Protection の Azure Rights Management サービスを利用して、暗号化と使用制限の割り当てを実施します。</span><span class="sxs-lookup"><span data-stu-id="02f11-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="02f11-107">Microsoft 365 のプランには Azure Rights Management が含まれているものと、含まれていないものがあります。</span><span class="sxs-lookup"><span data-stu-id="02f11-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="02f11-108">詳細については、「[Office のアプリケーションとサービスが Azure Rights Management をサポートするしくみ](/azure/information-protection/understand-explore/office-apps-services-support)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f11-108">To learn more, read [How Office applications and services support Azure Rights Management](/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="02f11-109">SharePoint 管理センターを使って IRM サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="02f11-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="02f11-110">組織で SharePoint リストとライブラリを IRM で保護するには、最初に Rights Management サービスを組織向けにアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f11-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="02f11-111">手順については、「[Azure Rights Management をアクティブにする](/information-protection/deploy-use/activate-service)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02f11-111">To learn how see [Activating Azure Rights Management](/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="02f11-112">Rights Management サービスを有効にするには、グローバル管理者権限を持つ職場または学校アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f11-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="02f11-113">そうしないと、SharePoint Online で IRM 機能を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="02f11-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="02f11-114">Rights Management サービスをアクティブにしたら、SharePoint 管理センターにサインインして、IRM をオンにします。</span><span class="sxs-lookup"><span data-stu-id="02f11-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="02f11-115">グローバル管理者または SharePoint 管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="02f11-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="02f11-116">左上のアプリ起動ツールのアイコン ![Office 365 のアプリ起動ツールのアイコン](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) を選択し、**[管理者]** を選択して Microsoft 365 管理センターを開きます</span><span class="sxs-lookup"><span data-stu-id="02f11-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="02f11-117">([管理者] タイルが表示されない場合、組織の管理者のアクセス許可が付与されていません。)</span><span class="sxs-lookup"><span data-stu-id="02f11-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="02f11-118">左側のウィンドウで、**[管理センター]** \> **[SharePoint]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="02f11-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="02f11-119">左側のウィンドウで、**[設定]** を選択してから、**[クラシック設定] ページ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f11-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="02f11-120">**[Information Rights Management (IRM)]** セクションで、**[構成で指定した IRM サービスを使う]**、**[IRM 設定の更新]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="02f11-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="02f11-121">IRM 設定を更新したら、組織内のユーザーは SharePoint リストとドキュメント ライブラリで IRM の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="02f11-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="02f11-122">ただし、そのためのオプションが [ライブラリ設定] と [リスト設定] に表示されるまでに最大 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f11-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="02f11-123">IRM 対応の SharePoint ドキュメント ライブラリとリスト</span><span class="sxs-lookup"><span data-stu-id="02f11-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="02f11-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="02f11-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="02f11-125">IRM 設定を更新したら、サイト所有者は SharePoint リストとドキュメント ライブラリを IRM で保護できます。</span><span class="sxs-lookup"><span data-stu-id="02f11-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="02f11-126">詳細については、「[Information Rights Management をリストまたはライブラリに適用する](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f11-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="02f11-127">サイト所有者がリストまたはライブラリに対して IRM を有効にすると、そのリストまたはライブラリでサポートされているファイルの種類を保護できます。</span><span class="sxs-lookup"><span data-stu-id="02f11-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="02f11-128">ライブラリで IRM が有効になっている場合、著作権管理はそのライブラリ内のすべてのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="02f11-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="02f11-129">リストに対して IRM を有効にすると、実際のリスト アイテムではなくリスト アイテムに関連付けられたファイルだけに著作権管理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="02f11-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="02f11-130">ユーザーが IRM 対応のリストまたはライブラリ内のファイルをダウンロードすると、ファイルは暗号化されるため、許可されたユーザーのみがファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="02f11-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="02f11-131">権限が管理されたファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="02f11-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="02f11-132">一般的な制限には、ファイルを読み取り専用にする、テキストのコピーを無効にする、ユーザーがローカル コピーを保存できないようにする、ユーザーがファイルを印刷できないようにするなどがあります。</span><span class="sxs-lookup"><span data-stu-id="02f11-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="02f11-133">IRM でサポートされているファイルの種類を読み取ることができるクライアント プログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="02f11-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="02f11-134">これは、権限が管理されたファイルがダウンロードされた後でもその保護を維持する方法です。</span><span class="sxs-lookup"><span data-stu-id="02f11-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="02f11-135">リストまたはライブラリで IRM を有効にするには、「[Information Rights Management をリストまたはライブラリに適用する](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f11-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="02f11-136">ブラウザーで Office を使用して、IRM 対応ライブラリでドキュメントを作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="02f11-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="02f11-137">代わりに、1 人ずつ IRM 暗号化ファイルをダウンロードして編集できます。</span><span class="sxs-lookup"><span data-stu-id="02f11-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="02f11-138">チェックインとチェックアウトを使用して、*共同編集*、または複数のユーザー間での作成を管理します。</span><span class="sxs-lookup"><span data-stu-id="02f11-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="02f11-139">IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Microsoft 365 は保護された PDF ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="02f11-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="02f11-140">ファイルの拡張子は変更されませんが、ファイルは保護されます。</span><span class="sxs-lookup"><span data-stu-id="02f11-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="02f11-141">このファイルを表示するには、Azure Information Protection ビューアー、完全な Azure Information Protection クライアント、または保護された PDF ファイルの表示をサポートする別のアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="02f11-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="02f11-142">SharePoint Online は次のファイルの種類の暗号化をサポートします。</span><span class="sxs-lookup"><span data-stu-id="02f11-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="02f11-143">PDF</span><span class="sxs-lookup"><span data-stu-id="02f11-143">PDF</span></span>
    
- <span data-ttu-id="02f11-144">Microsoft Office Word、Microsoft Office Excel、Microsoft Office PowerPoint の 97 から 2003 までのファイル形式</span><span class="sxs-lookup"><span data-stu-id="02f11-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="02f11-145">Microsoft Office Word、Microsoft Office Excel、および Microsoft Office PowerPoint の Office Open XML 形式</span><span class="sxs-lookup"><span data-stu-id="02f11-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="02f11-146">XML Paper Specification (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="02f11-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="02f11-147">SharePoint はアップロード時にドキュメントを開く必要があるため、保護されたドキュメント (デジタル署名の PDF ファイルなど) に IRM 保護を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="02f11-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="02f11-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="02f11-148">Next steps</span></span>
<span data-ttu-id="02f11-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="02f11-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="02f11-150">SharePoint Online の IRM を有効にすると、リストとライブラリへの著作権管理の適用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="02f11-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="02f11-151">詳細については、「[Information Rights Management をリストまたはライブラリに適用する](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f11-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="02f11-152">Windows の新しい OneDrive 同期クライアントでは、(ライブラリの IRM 設定に、ドキュメントのアクセス権の期限が設定されていない限り) IRM で保護された SharePoint ドキュメント ライブラリと OneDrive の場所の同期がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="02f11-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="02f11-153">詳細について、または新しい同期クライアントの展開を開始するには、「[Windows 向けの新しい OneDrive 同期クライアントを展開する](/onedrive/deploy-on-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f11-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="02f11-154">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="02f11-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)