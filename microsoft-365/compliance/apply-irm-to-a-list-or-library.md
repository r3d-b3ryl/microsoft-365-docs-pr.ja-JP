---
title: Information Rights Management (IRM) をリストまたはライブラリに適用する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルを制御および保護できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c61b7c6f13208b6c017b5ed65c667203abade42
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663102"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="d8483-103">Information Rights Management (IRM) をリストまたはライブラリに適用する</span><span class="sxs-lookup"><span data-stu-id="d8483-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="d8483-104">Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルを制御および保護できます。</span><span class="sxs-lookup"><span data-stu-id="d8483-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span>
  
## <a name="administrator-preparations-before-applying-irm"></a><span data-ttu-id="d8483-105">IRM を適用する前の管理者の準備</span><span class="sxs-lookup"><span data-stu-id="d8483-105">Administrator preparations before applying IRM</span></span>

- <span data-ttu-id="d8483-106">Azure Information Protection の Azure Rights Management サービス (Azure RMS) と、オンプレミスと同等の Active Directory Rights Management サービス (AD RMS) は、サイトの Information Rights Management をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d8483-106">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="d8483-107">個別のインストールや追加のインストールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d8483-107">No separate or additional installations are required.</span></span>

- <span data-ttu-id="d8483-108">リストまたはライブラリに IRM を適用する前に、サイトで IRM を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8483-108">Before you apply IRM to a list or library, you need to enable IRM for your site.</span></span> <span data-ttu-id="d8483-109">IRM を有効にするには管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8483-109">You'll need administrator permissions to enable IRM.</span></span>

- <span data-ttu-id="d8483-110">リストまたはライブラリに IRM を適用するには、そのリストまたはライブラリに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8483-110">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>

- <span data-ttu-id="d8483-111">SharePoint Online を使用している場合、より大きな IRM で保護されたファイルをダウンロードすると、ユーザーにタイムアウトが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8483-111">If you're using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="d8483-112">タイムアウトを回避するには、Office プログラムを使用して IRM 保護を適用し、IRM を使用しない SharePoint ライブラリに大きなファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="d8483-112">To avoid timeouts, use your Office programs to apply IRM protection, and store larger files in a SharePoint library that doesn't use IRM.</span></span>

> [!NOTE]
> <span data-ttu-id="d8483-113">SharePoint Server 2013 を使用している場合、サーバー管理者は、組織内のユーザーが IRM を使用して保護するファイルの種類ごとに、すべてのフロントエンド Web サーバーにプロテクタをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8483-113">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span>
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="d8483-114">リストまたはライブラリに IRM を適用する</span><span class="sxs-lookup"><span data-stu-id="d8483-114">Apply IRM to a list or library</span></span>
<span data-ttu-id="d8483-115"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="d8483-115"><a name="__toc256598179"> </a></span></span>

![Information Rights Management の設定](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="d8483-117">IRM を構成するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8483-117">Go to the list or library for which you want to configure IRM.</span></span>

2. <span data-ttu-id="d8483-118">リボンで [ライブラリ] タブ **を選択** し、[ライブラリの設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8483-118">On the ribbon, select the **Library** tab, and then select **Library Settings**.</span></span> <span data-ttu-id="d8483-119">(リストで作業している場合は、[リスト] タブを選択し、[リストの設定] を **選択します**)。</span><span class="sxs-lookup"><span data-stu-id="d8483-119">(If you're working in a list, select the **List** tab, and then select **List Settings**).</span></span>
    
    ![リボンの SharePoint ライブラリ設定ボタン](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="d8483-121">[権限 **と管理] で、[Information** **Rights Management] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8483-121">Under **Permissions and Management**, select **Information Rights Management**.</span></span> <span data-ttu-id="d8483-122">Information Rights Management リンクが表示されない場合は、サイトで IRM が有効になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8483-122">If the Information Rights Management link doesn't appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="d8483-123">サイトで IRM を有効にできる場合は、サーバー管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d8483-123">Contact your server administrator to see if you can enable IRM for your site.</span></span> <span data-ttu-id="d8483-124">Information **Rights Management リンク** は、画像ライブラリには表示されません。</span><span class="sxs-lookup"><span data-stu-id="d8483-124">The **Information Rights Management** link doesn't appear for picture libraries.</span></span>

4. <span data-ttu-id="d8483-125">**[Information Rights Management の** 設定]ページで、[ダウンロード時にこのライブラリ内のドキュメントへのアクセス許可を制限する] チェック ボックスをオンにして、このリストまたはライブラリからユーザーがダウンロードするドキュメントに制限付きのアクセス許可を適用します。</span><span class="sxs-lookup"><span data-stu-id="d8483-125">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents users download from this list or library.</span></span>

5. <span data-ttu-id="d8483-126">[アクセス **許可ポリシーのタイトルの作成** ] ボックスに、ポリシーのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8483-126">In the **Create a permission policy title** box, enter a descriptive name for the policy.</span></span> <span data-ttu-id="d8483-127">他のポリシーからこのポリシーを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8483-127">Use a name that helps you identify this policy from other policies.</span></span> <span data-ttu-id="d8483-128">たとえば、会社の機密 **を使用して** 、会社の機密ドキュメントを含むリストまたはライブラリに制限付きのアクセス許可を適用します。</span><span class="sxs-lookup"><span data-stu-id="d8483-128">For example, use **Company Confidential** to apply restricted permissions to a list or library that contains confidential company documents.</span></span>

6. <span data-ttu-id="d8483-129">[アクセス許可 **ポリシー** の説明の追加] ボックスに、このリストまたはライブラリを使用するユーザーに表示される説明を入力します。このリストまたはライブラリ内のドキュメントの処理方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d8483-129">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="d8483-130">たとえば、「Discuss the **contents of this document** only with other employees if you want to restrict access to the information in these documents to internal employees.</span><span class="sxs-lookup"><span data-stu-id="d8483-130">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 

7. <span data-ttu-id="d8483-131">このリストまたはライブラリ内のドキュメントに追加の制限を適用するには、[オプションの表示] を選択し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8483-131">To apply additional restrictions to the documents in this list or library, select **Show Options**, and do any of the following:</span></span>

|<span data-ttu-id="d8483-132">**これを行うには、次の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="d8483-132">**To do this:**</span></span>|<span data-ttu-id="d8483-133">**これを行います。**</span><span class="sxs-lookup"><span data-stu-id="d8483-133">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8483-134">このリストまたはライブラリからドキュメントを印刷できるユーザーを許可する</span><span class="sxs-lookup"><span data-stu-id="d8483-134">Allow people to print documents from this list or library</span></span>|<span data-ttu-id="d8483-135">[閲覧者 **に印刷を許可する] チェック** ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d8483-135">Select the **Allow viewers to print** check box.</span></span>|
|<span data-ttu-id="d8483-136">少なくとも [アイテムの表示] 権限を持つユーザーに、文書に埋め込まれたコードまたはマクロを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8483-136">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>|<span data-ttu-id="d8483-137">[ダウンロードした **ドキュメントでスクリプトと** スクリーン リーダーを実行して機能する閲覧者を許可する] チェック ボックスをオンにします。このオプションを選択すると、ユーザーはコードを実行してドキュメントの内容を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="d8483-137">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="d8483-138">コンテンツへのアクセスを指定した期間に制限する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8483-138">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="d8483-139">このオプションを選択すると、コンテンツにアクセスするためのユーザーの発行ライセンスは、指定した日数が経過すると有効期限が切れ、資格情報を確認して新しいコピーをダウンロードするためにサーバーに戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8483-139">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>|<span data-ttu-id="d8483-140">[ダウンロード後、ドキュメントのアクセス権は、この日数 **(1 ~ 365)** 後に期限切れになります。次に、ドキュメントを表示可能な日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8483-140">Select the **After download, document access rights will expire after these number of days (1-365)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>|
| <span data-ttu-id="d8483-141">IRM をサポートしていないドキュメントをこのリストまたはライブラリにアップロードできない。</span><span class="sxs-lookup"><span data-stu-id="d8483-141">Prevent people from uploading documents that do not support IRM to this list or library.</span></span> <span data-ttu-id="d8483-142">このオプションを選択すると、ユーザーは次のファイルの種類をアップロードできません。対応する IRM プロテクタがインストールされていないファイルの種類は、すべてのフロントエンド Web サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d8483-142">If you select this option, people will not be able to upload any of the following file types: File types that do not have corresponding IRM protectors installed on all of the front-end web servers.</span></span> <span data-ttu-id="d8483-143">SharePoint Server 2010 で暗号化を解除できないファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="d8483-143">File types that SharePoint Server 2010 cannot decrypt.</span></span> <span data-ttu-id="d8483-144">別のプログラムで IRM 保護されているファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="d8483-144">File types that are IRM protected in another program.</span></span>|<span data-ttu-id="d8483-145">**[IRM をサポートしていないドキュメント** のアップロードをユーザーに許可しない] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d8483-145">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>|
|<span data-ttu-id="d8483-146">特定の日付に、このリストまたはライブラリから制限付きアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="d8483-146">Remove restricted permissions from this list or library on a specific date.</span></span>|<span data-ttu-id="d8483-147">[ライブラリ **へのアクセス制限を停止する]** チェック ボックスをオンにし、必要な日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8483-147">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>|
|<span data-ttu-id="d8483-148">ドキュメントを開くライセンスがあるプログラムの資格情報がキャッシュされる間隔を制御します。</span><span class="sxs-lookup"><span data-stu-id="d8483-148">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>|<span data-ttu-id="d8483-149">[ユーザーは **、この間隔 (日)** を使用して資格情報を確認する必要があります] チェック ボックスをオンにし、資格情報をキャッシュする間隔を日数で入力します。</span><span class="sxs-lookup"><span data-stu-id="d8483-149">Select the **Users must verify their credentials using this interval (days)** check box, then enter the interval for caching credentials in number of days.</span></span>|
|<span data-ttu-id="d8483-150">ユーザーが同じグループのメンバーと共有できるよう、グループ保護を許可します。</span><span class="sxs-lookup"><span data-stu-id="d8483-150">Allow group protection so that users can share with members of the same group.</span></span>|<span data-ttu-id="d8483-151">[ **グループ保護を許可** する] を選択し、共有するグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8483-151">Select **Allow group protection**, and enter the group's name for sharing.</span></span>|

8. <span data-ttu-id="d8483-152">必要なオプションの選択が完了したら **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8483-152">After you finish selecting the options you want, select **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="d8483-153">Information Rights Management とは</span><span class="sxs-lookup"><span data-stu-id="d8483-153">What is Information Rights Management?</span></span>
<span data-ttu-id="d8483-154"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="d8483-154"><a name="__toc256598175"> </a></span></span>

<span data-ttu-id="d8483-155">Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルに対してユーザーが実行できる操作を制限できます。</span><span class="sxs-lookup"><span data-stu-id="d8483-155">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="d8483-156">IRM は、ダウンロードされたファイルを暗号化し、それらのファイルの暗号化を解除できる一連のユーザーおよびプログラムを制限します。</span><span class="sxs-lookup"><span data-stu-id="d8483-156">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="d8483-157">また、IRM は、ファイルを読み取ることができるユーザーの権限を制限し、ファイルの印刷、ファイルからのテキストのコピーなど、そのユーザーがアクションを実行することを禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8483-157">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="d8483-158">リストまたはライブラリで IRM を使用して、機密性の高いコンテンツの流用を制限できます。</span><span class="sxs-lookup"><span data-stu-id="d8483-158">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="d8483-159">たとえば、今後の製品に関する情報を選択したマーケティング担当者と共有するドキュメント ライブラリを作成している場合は、IRM を使用して、これらの個人が会社の他の従業員とこのコンテンツを共有しなけれとすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8483-159">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="d8483-160">サイトでは、個々のファイルではなく、リストまたはライブラリ全体に IRM を適用します。</span><span class="sxs-lookup"><span data-stu-id="d8483-160">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="d8483-161">これにより、ドキュメントまたはファイルのセット全体に対して一貫したレベルの保護を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d8483-161">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="d8483-162">したがって、IRM は、組織が機密情報または専有情報の使用と提供を管理する企業ポリシーを適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8483-162">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8483-163">Information Rights Management に関するこのページの情報は、Microsoft SharePoint Server 2013 および SharePoint Server 2016 の使用許諾契約書で 「Information Rights Management」を参照する用語に取って代わるものになります。</span><span class="sxs-lookup"><span data-stu-id="d8483-163">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="d8483-164">IRM がコンテンツの保護に役立つ方法</span><span class="sxs-lookup"><span data-stu-id="d8483-164">How IRM can help protect content</span></span>
<span data-ttu-id="d8483-165"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="d8483-165"><a name="__toc256598176"> </a></span></span>

<span data-ttu-id="d8483-166">IRM は、次の方法で制限されたコンテンツを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8483-166">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="d8483-167">承認された閲覧者が、許可されていない使用のためにコンテンツをコピー、変更、印刷、FAX、またはコピーして貼り付けるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8483-167">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="d8483-168">Microsoft Windows の印刷画面機能を使用して、承認された閲覧者がコンテンツをコピーするのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8483-168">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="d8483-169">承認されていない閲覧者がサーバーからダウンロードした後に電子メールで送信された場合にコンテンツを表示しなくのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8483-169">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="d8483-170">コンテンツへのアクセスを指定した期間に制限します。その後、ユーザーは資格情報を確認してコンテンツを再びダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8483-170">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="d8483-171">組織内でのコンテンツの使用と提供を管理する企業ポリシーの適用に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8483-171">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="d8483-172">IRM でコンテンツを保護できない方法</span><span class="sxs-lookup"><span data-stu-id="d8483-172">How IRM cannot help protect content</span></span>
<span data-ttu-id="d8483-173"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="d8483-173"><a name="__toc256598177"> </a></span></span>

<span data-ttu-id="d8483-174">IRM では、制限されたコンテンツを次の内容から保護できません。</span><span class="sxs-lookup"><span data-stu-id="d8483-174">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="d8483-175">トロイの木馬、キーストローク ロガー、特定の種類のスパイウェアなどの悪意のあるプログラムによる消去、盗難、キャプチャ、転送</span><span class="sxs-lookup"><span data-stu-id="d8483-175">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="d8483-176">コンピューター ウイルスの操作による損失または破損</span><span class="sxs-lookup"><span data-stu-id="d8483-176">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="d8483-177">画面のディスプレイからコンテンツを手動でコピーまたは再入力する</span><span class="sxs-lookup"><span data-stu-id="d8483-177">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="d8483-178">画面に表示されるコンテンツのデジタル写真または映画写真</span><span class="sxs-lookup"><span data-stu-id="d8483-178">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="d8483-179">サード パーティ製のスクリーン キャプチャ プログラムを使用したコピー</span><span class="sxs-lookup"><span data-stu-id="d8483-179">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="d8483-180">サード パーティ製のスクリーン キャプチャ プログラムまたはコピー/貼り付けアクションを使用したコンテンツ メタデータ (列の値) のコピー</span><span class="sxs-lookup"><span data-stu-id="d8483-180">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
    
[<span data-ttu-id="d8483-181">Information Rights Management をリストまたはライブラリに適用する</span><span class="sxs-lookup"><span data-stu-id="d8483-181">Apply Information Rights Management to a list or library</span></span>](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="d8483-182">リストとライブラリに対する IRM の動作</span><span class="sxs-lookup"><span data-stu-id="d8483-182">How IRM works for lists and libraries</span></span>
<span data-ttu-id="d8483-183"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="d8483-183"><a name="__toc256598178"> </a></span></span>

<span data-ttu-id="d8483-184">IRM 保護は、リストレベルまたはライブラリ レベルのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8483-184">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="d8483-185">ライブラリに対して IRM を有効にすると、そのライブラリ内のすべてのファイルに権限管理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8483-185">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="d8483-186">リストに対して IRM が有効になっている場合、権限管理は、実際のリスト アイテムではなく、リスト アイテムに添付されているファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8483-186">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="d8483-187">ユーザーが IRM 対応のリストまたはライブラリでファイルをダウンロードすると、承認されたユーザーのみがファイルを表示できるよう、ファイルが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="d8483-187">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="d8483-188">権限が管理された各ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスも含めます。</span><span class="sxs-lookup"><span data-stu-id="d8483-188">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="d8483-189">一般的な制限としては、ファイルの読み取り専用化、テキストのコピーの無効化、ユーザーによるローカル コピーの保存の防止、ファイルの印刷の防止が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8483-189">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="d8483-190">IRM でサポートされるファイルの種類を読み取るクライアント プログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="d8483-190">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="d8483-191">これは、権限が管理されたファイルがサーバーからダウンロードされた後でも、その保護を維持する方法です。</span><span class="sxs-lookup"><span data-stu-id="d8483-191">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="d8483-192">ファイルをリストまたはライブラリからダウンロードするときにファイルに適用される制限の種類は、ファイルを含むサイトに対する個々のユーザーのアクセス許可に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="d8483-192">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="d8483-193">次の表では、サイトの権限が IRM 権限とどのように対応するのかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d8483-193">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="d8483-194">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="d8483-194">**Permissions**</span></span>|<span data-ttu-id="d8483-195">**IRM アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="d8483-195">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8483-196">権限の管理、Web サイトの管理</span><span class="sxs-lookup"><span data-stu-id="d8483-196">Manage Permissions, Manage Web Site</span></span>|<span data-ttu-id="d8483-197">**(クライアント** プログラムによって定義される) フル コントロール: 通常、このアクセス許可を使用すると、ユーザーは権限が管理されたコンテンツの読み取り、編集、コピー、保存、および権限の変更を行います。</span><span class="sxs-lookup"><span data-stu-id="d8483-197">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>|
|<span data-ttu-id="d8483-198">アイテムの編集、リストの管理、ページの追加とカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d8483-198">Edit Items, Manage Lists, Add and Customize Pages</span></span>|<span data-ttu-id="d8483-199">**編集**、**コピー**、および保存 **:** ユーザーがファイルを印刷できるのは、リストまたはライブラリの [Information Rights Management の設定] ページで [ドキュメントの印刷を許可する] チェック ボックスがオンの場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d8483-199">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="d8483-200">アイテムの表示</span><span class="sxs-lookup"><span data-stu-id="d8483-200">View Items</span></span>|<span data-ttu-id="d8483-201">**読** み取り : ユーザーはドキュメントを読み取できますが、コンテンツをコピーまたは変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8483-201">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="d8483-202">ユーザーが印刷できるのは、リストまたはライブラリの [Information Rights Management の設定] ページで [ドキュメントの印刷を許可する] チェック ボックスがオンの場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d8483-202">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="d8483-203">その他</span><span class="sxs-lookup"><span data-stu-id="d8483-203">Other</span></span>|<span data-ttu-id="d8483-204">他の権限は IRM 権限に直接対応する権限はありません。</span><span class="sxs-lookup"><span data-stu-id="d8483-204">No other permissions correspond directly to IRM permissions.</span></span>|
   
<span data-ttu-id="d8483-205">SharePoint Server 2013 でリストまたはライブラリに対して IRM を有効にした場合、保護機能がすべてのフロントエンド Web サーバーにインストールされているリストまたはライブラリ内のファイルの種類のみを保護できます。</span><span class="sxs-lookup"><span data-stu-id="d8483-205">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end web servers.</span></span> <span data-ttu-id="d8483-206">プロテクタは、権限が管理された特定のファイル形式のファイルの暗号化と解読を制御するプログラムです。</span><span class="sxs-lookup"><span data-stu-id="d8483-206">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="d8483-207">SharePoint には、次のファイルの種類のプロテクタが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8483-207">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="d8483-208">Microsoft Office InfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="d8483-208">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="d8483-209">Word、Excel、PowerPoint の 97-2003 ファイル形式は、次Microsoft Officeプログラム用です。</span><span class="sxs-lookup"><span data-stu-id="d8483-209">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="d8483-210">次Officeプログラム (Word、Excel、PowerPoint) Microsoft Office Open XML 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8483-210">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="d8483-211">XML Paper Specification (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="d8483-211">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="d8483-212">組織で IRM を使用して上記のファイルの種類以外のファイルの種類を保護する場合、サーバー管理者は、これらの追加のファイル形式のプロテクタをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8483-212">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

