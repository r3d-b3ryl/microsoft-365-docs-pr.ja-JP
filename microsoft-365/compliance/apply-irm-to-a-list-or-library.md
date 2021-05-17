---
title: リストまたはライブラリに Information Rights Management (IRM) を適用する
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
description: Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされるファイルを制御および保護できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233353"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="a9d94-103">リストまたはライブラリに Information Rights Management (IRM) を適用する</span><span class="sxs-lookup"><span data-stu-id="a9d94-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="a9d94-104">Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされるファイルを制御および保護できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span> <span data-ttu-id="a9d94-105">この機能は、Microsoft グローバル クラウドでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-105">This feature is only supported in the Microsoft global cloud.</span></span> <span data-ttu-id="a9d94-106">IRM は、国内クラウド展開SharePointリストとライブラリではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-106">IRM is not supported for SharePoint lists and libraries in national cloud deployments.</span></span>
  
## <a name="administrator-preparations-before-applying-irm"></a><span data-ttu-id="a9d94-107">IRM を適用する前の管理者の準備</span><span class="sxs-lookup"><span data-stu-id="a9d94-107">Administrator preparations before applying IRM</span></span>

- <span data-ttu-id="a9d94-108">Azure Information Protection の Azure Rights Management サービス (Azure RMS) と、オンプレミスと同等の Active Directory Rights Management サービス (AD RMS) は、サイトの Information Rights Management をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a9d94-108">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="a9d94-109">個別または追加のインストールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-109">No separate or additional installations are required.</span></span>

- <span data-ttu-id="a9d94-110">リストまたはライブラリに IRM を適用する前に、サイトの IRM を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-110">Before you apply IRM to a list or library, you need to enable IRM for your site.</span></span> <span data-ttu-id="a9d94-111">IRM を有効にするには、管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9d94-111">You'll need administrator permissions to enable IRM.</span></span>

- <span data-ttu-id="a9d94-112">IRM をリストまたはライブラリに適用するには、そのリストまたはライブラリに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9d94-112">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>

- <span data-ttu-id="a9d94-113">オンラインで使用している場合SharePoint、IRM で保護された大きなファイルをダウンロードするときにタイムアウトが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-113">If you're using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="a9d94-114">タイムアウトを回避するには、Office プログラムを使用して IRM 保護を適用し、IRM を使用しない SharePoint ライブラリに大きなファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-114">To avoid timeouts, use your Office programs to apply IRM protection, and store larger files in a SharePoint library that doesn't use IRM.</span></span>

> [!NOTE]
> <span data-ttu-id="a9d94-115">SharePoint Server 2013 を使用している場合、サーバー管理者は、IRM を使用して組織内のユーザーが保護するファイルの種類ごとに、すべてのフロントエンド Web サーバーにプロテクタをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-115">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span>
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="a9d94-116">リストまたはライブラリに IRM を適用する</span><span class="sxs-lookup"><span data-stu-id="a9d94-116">Apply IRM to a list or library</span></span>
<span data-ttu-id="a9d94-117"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="a9d94-117"><a name="__toc256598179"> </a></span></span>

![Information Rights Management 設定](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="a9d94-119">IRM を構成するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-119">Go to the list or library for which you want to configure IRM.</span></span>

2. <span data-ttu-id="a9d94-120">リボンで 、[ライブラリ] タブ **を選択** し、[ライブラリ]**を選択設定。**</span><span class="sxs-lookup"><span data-stu-id="a9d94-120">On the ribbon, select the **Library** tab, and then select **Library Settings**.</span></span> <span data-ttu-id="a9d94-121">(リストで作業している場合は、[リスト] タブを選択し、[リスト] タブを選択 **設定)。**</span><span class="sxs-lookup"><span data-stu-id="a9d94-121">(If you're working in a list, select the **List** tab, and then select **List Settings**).</span></span>
    
    ![SharePointリボン設定ライブラリ ボタン](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="a9d94-123">[アクセス **許可と管理] で、[** 情報権限 **の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a9d94-123">Under **Permissions and Management**, select **Information Rights Management**.</span></span> <span data-ttu-id="a9d94-124">[Information Rights Management] リンクが表示されない場合は、サイトで IRM が有効になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-124">If the Information Rights Management link doesn't appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="a9d94-125">サイトの IRM を有効にできる場合は、サーバー管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a9d94-125">Contact your server administrator to see if you can enable IRM for your site.</span></span> <span data-ttu-id="a9d94-126">ピクチャ **ライブラリの [Information Rights Management]** リンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-126">The **Information Rights Management** link doesn't appear for picture libraries.</span></span>

4. <span data-ttu-id="a9d94-127">[Information **Rights Management 設定]** ページで、[ダウンロード時にこのライブラリ内のドキュメントへのアクセス許可を制限する] チェック ボックスをオンにして、ユーザーがこのリストまたはライブラリからダウンロードするドキュメントに制限されたアクセス許可を適用します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-127">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents users download from this list or library.</span></span>

5. <span data-ttu-id="a9d94-128">[アクセス **許可ポリシーの作成] タイトル ボックスに** 、ポリシーのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-128">In the **Create a permission policy title** box, enter a descriptive name for the policy.</span></span> <span data-ttu-id="a9d94-129">他のポリシーからこのポリシーを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-129">Use a name that helps you identify this policy from other policies.</span></span> <span data-ttu-id="a9d94-130">たとえば、会社機密 **を使用して** 、会社の機密文書を含むリストまたはライブラリに制限付きアクセス許可を適用します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-130">For example, use **Company Confidential** to apply restricted permissions to a list or library that contains confidential company documents.</span></span>

6. <span data-ttu-id="a9d94-131">[アクセス **許可ポリシーの** 説明の追加] ボックスに、このリストまたはライブラリを使用するユーザーに表示される説明を入力します。このリストまたはライブラリ内のドキュメントの処理方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-131">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="a9d94-132">たとえば、「このドキュメントの内容を他の従業員とのみ議論する」と入力すると、これらのドキュメント内の情報へのアクセスを内部の従業員に制限できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-132">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 

7. <span data-ttu-id="a9d94-133">このリストまたはライブラリのドキュメントに追加の制限を適用するには、[オプションの表示] を選択し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9d94-133">To apply additional restrictions to the documents in this list or library, select **Show Options**, and do any of the following:</span></span>

|<span data-ttu-id="a9d94-134">**これを行うには、次の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="a9d94-134">**To do this:**</span></span>|<span data-ttu-id="a9d94-135">**これを行います。**</span><span class="sxs-lookup"><span data-stu-id="a9d94-135">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9d94-136">このリストまたはライブラリからドキュメントを印刷するユーザーを許可する</span><span class="sxs-lookup"><span data-stu-id="a9d94-136">Allow people to print documents from this list or library</span></span>|<span data-ttu-id="a9d94-137">[閲覧者 **に印刷を許可する] チェック** ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a9d94-137">Select the **Allow viewers to print** check box.</span></span>|
|<span data-ttu-id="a9d94-138">[アイテムの表示] 権限を持つユーザーに対して、ドキュメントに埋め込みコードまたはマクロを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-138">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>|<span data-ttu-id="a9d94-139">[ダウンロードした **ドキュメントで閲覧者にスクリプト** とスクリーン リーダーの機能を許可する] チェック ボックスをオンにします。このオプションを選択すると、ユーザーはコードを実行してドキュメントの内容を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-139">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="a9d94-140">コンテンツへのアクセスを指定した期間に制限する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-140">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="a9d94-141">このオプションを選択すると、コンテンツにアクセスするユーザーの発行ライセンスは、指定した日数が経過すると期限切れになります。ユーザーは資格情報を確認して新しいコピーをダウンロードするためにサーバーに戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-141">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>|<span data-ttu-id="a9d94-142">[ダウンロード後、ドキュメント アクセス権は、これらの日数 **(1 ~ 365)** 後に期限切れになります] チェック ボックスをオンにし、ドキュメントを表示できる日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-142">Select the **After download, document access rights will expire after these number of days (1-365)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>|
| <span data-ttu-id="a9d94-143">IRM をサポートしていないドキュメントをこのリストまたはライブラリにアップロードするユーザーを防止します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-143">Prevent people from uploading documents that do not support IRM to this list or library.</span></span> <span data-ttu-id="a9d94-144">このオプションを選択すると、すべてのフロントエンド Web サーバーに対応する IRM プロテクタがインストールされていないファイルの種類をアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-144">If you select this option, people will not be able to upload any of the following file types: File types that do not have corresponding IRM protectors installed on all of the front-end web servers.</span></span> <span data-ttu-id="a9d94-145">Server 2010 SharePointファイルの種類は復号化できません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-145">File types that SharePoint Server 2010 cannot decrypt.</span></span> <span data-ttu-id="a9d94-146">別のプログラムで保護されている IRM であるファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="a9d94-146">File types that are IRM protected in another program.</span></span>|<span data-ttu-id="a9d94-147">**[IRM をサポートしていないドキュメントの** アップロードをユーザーに許可しない] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a9d94-147">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>|
|<span data-ttu-id="a9d94-148">特定の日付に、このリストまたはライブラリから制限付きアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-148">Remove restricted permissions from this list or library on a specific date.</span></span>|<span data-ttu-id="a9d94-149">[ライブラリ **へのアクセス制限** を停止する] チェック ボックスをオンにして、必要な日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-149">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>|
|<span data-ttu-id="a9d94-150">ドキュメントを開くライセンスを持つプログラムの資格情報がキャッシュされる間隔を制御します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-150">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>|<span data-ttu-id="a9d94-151">[ユーザーは **、この間隔 (日数)** を使用して資格情報を確認する必要があります] チェック ボックスをオンにし、資格情報を日数でキャッシュする間隔を入力します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-151">Select the **Users must verify their credentials using this interval (days)** check box, then enter the interval for caching credentials in number of days.</span></span>|
|<span data-ttu-id="a9d94-152">ユーザーが同じグループのメンバーと共有できるよう、グループ保護を許可します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-152">Allow group protection so that users can share with members of the same group.</span></span>|<span data-ttu-id="a9d94-153">[グループ **保護を許可する]** を選択し、共有するグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-153">Select **Allow group protection**, and enter the group's name for sharing.</span></span>|

8. <span data-ttu-id="a9d94-154">必要なオプションの選択が完了したら **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a9d94-154">After you finish selecting the options you want, select **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="a9d94-155">Information Rights Management とは</span><span class="sxs-lookup"><span data-stu-id="a9d94-155">What is Information Rights Management?</span></span>
<span data-ttu-id="a9d94-156"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="a9d94-156"><a name="__toc256598175"> </a></span></span>

<span data-ttu-id="a9d94-157">Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルに対してユーザーが実行できるアクションを制限できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-157">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="a9d94-158">IRM は、ダウンロードされたファイルを暗号化し、それらのファイルの暗号化を解除できる一連のユーザーおよびプログラムを制限します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-158">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="a9d94-159">また、IRM は、ファイルを読み取ることができるユーザーの権限を制限し、ファイルの印刷、ファイルからのテキストのコピーなど、そのユーザーがアクションを実行することを禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-159">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="a9d94-160">リストまたはライブラリで IRM を使用して、機密性の高いコンテンツの普及を制限できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-160">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="a9d94-161">たとえば、今後の製品に関する情報を選択したマーケティング担当者と共有するドキュメント ライブラリを作成する場合は、IRM を使用して、これらの個人が会社の他の従業員とこのコンテンツを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-161">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="a9d94-162">サイトでは、個々のファイルではなく、リストまたはライブラリ全体に IRM を適用します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-162">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="a9d94-163">これにより、一連のドキュメントまたはファイル全体に対して一貫したレベルの保護が容易になります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-163">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="a9d94-164">IRM は、機密情報または専有情報の使用と普及を管理する企業ポリシーを組織が実施するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-164">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9d94-165">Information Rights Management に関するこのページの情報は、Microsoft SharePoint Server 2013 および SharePoint Server 2016 の使用許諾契約書で「Information Rights Management」を参照する用語に取って代わるものになります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-165">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="a9d94-166">IRM がコンテンツの保護に役立つ方法</span><span class="sxs-lookup"><span data-stu-id="a9d94-166">How IRM can help protect content</span></span>
<span data-ttu-id="a9d94-167"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="a9d94-167"><a name="__toc256598176"> </a></span></span>

<span data-ttu-id="a9d94-168">IRM は、制限されたコンテンツを次の方法で保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-168">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="a9d94-169">承認された閲覧者が、許可されていない使用のためにコンテンツをコピー、変更、印刷、FAX、またはコピーおよび貼り付けするのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-169">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="a9d94-170">Microsoft Web サイトの印刷画面機能を使用して、承認された閲覧者がコンテンツをコピー Windows</span><span class="sxs-lookup"><span data-stu-id="a9d94-170">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="a9d94-171">承認されていない閲覧者がサーバーからダウンロードされた後に電子メールで送信された場合にコンテンツを表示するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-171">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="a9d94-172">コンテンツへのアクセスを指定した期間に制限します。その後、ユーザーは資格情報を確認してコンテンツを再度ダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-172">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="a9d94-173">組織内のコンテンツの使用と普及を管理する企業ポリシーの適用に役立ちます</span><span class="sxs-lookup"><span data-stu-id="a9d94-173">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="a9d94-174">IRM でコンテンツを保護できない方法</span><span class="sxs-lookup"><span data-stu-id="a9d94-174">How IRM cannot help protect content</span></span>
<span data-ttu-id="a9d94-175"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="a9d94-175"><a name="__toc256598177"> </a></span></span>

<span data-ttu-id="a9d94-176">IRM では、制限付きコンテンツを次から保護できません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-176">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="a9d94-177">トロイの木馬、キーストローク ロガー、特定の種類のスパイウェアなどの悪意のあるプログラムによる消去、盗難、キャプチャ、または送信</span><span class="sxs-lookup"><span data-stu-id="a9d94-177">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="a9d94-178">コンピューター ウイルスの操作による損失または破損</span><span class="sxs-lookup"><span data-stu-id="a9d94-178">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="a9d94-179">画面の表示からコンテンツを手動でコピーまたは再入力する</span><span class="sxs-lookup"><span data-stu-id="a9d94-179">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="a9d94-180">画面に表示されるコンテンツのデジタル写真またはフィルム写真</span><span class="sxs-lookup"><span data-stu-id="a9d94-180">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="a9d94-181">サード パーティ製のスクリーン キャプチャ プログラムの使用によるコピー</span><span class="sxs-lookup"><span data-stu-id="a9d94-181">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="a9d94-182">サード パーティ製のスクリーン キャプチャ プログラムまたはコピーアンド貼り付けアクションを使用したコンテンツ メタデータ (列の値) のコピー</span><span class="sxs-lookup"><span data-stu-id="a9d94-182">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="a9d94-183">リストとライブラリに対する IRM の動作</span><span class="sxs-lookup"><span data-stu-id="a9d94-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="a9d94-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="a9d94-184"><a name="__toc256598178"> </a></span></span>

<span data-ttu-id="a9d94-185">IRM 保護は、リストまたはライブラリ レベルのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-185">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="a9d94-186">ライブラリで IRM が有効になっている場合、著作権管理はそのライブラリ内のすべてのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-186">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="a9d94-187">リストに対して IRM が有効になっている場合、権限管理は、実際のリスト アイテムではなく、リスト アイテムに添付されているファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-187">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="a9d94-188">ユーザーが IRM 対応のリストまたはライブラリ内のファイルをダウンロードすると、ファイルは暗号化されるため、許可されたユーザーのみがファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-188">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="a9d94-189">権限が管理されたファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9d94-189">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="a9d94-190">一般的な制限には、ファイルを読み取り専用にする、テキストのコピーを無効にする、ユーザーがローカル コピーを保存できないようにする、ユーザーがファイルを印刷できないようにするなどがあります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-190">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="a9d94-191">IRM でサポートされているファイルの種類を読み取ることができるクライアント プログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-191">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="a9d94-192">これは、サーバーからダウンロードされた後でも、権限で管理されたファイルが保護を保持する方法です。</span><span class="sxs-lookup"><span data-stu-id="a9d94-192">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="a9d94-193">ファイルがリストまたはライブラリからダウンロードされる際に適用される制限の種類は、ファイルを含むサイトに対する個々のユーザーのアクセス許可に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="a9d94-193">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="a9d94-194">次の表では、サイトのアクセス許可が IRM アクセス許可とどのように対応するのかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a9d94-194">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="a9d94-195">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="a9d94-195">**Permissions**</span></span>|<span data-ttu-id="a9d94-196">**IRM のアクセス許可**</span><span class="sxs-lookup"><span data-stu-id="a9d94-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9d94-197">アクセス許可の管理、Web サイトの管理</span><span class="sxs-lookup"><span data-stu-id="a9d94-197">Manage Permissions, Manage Web Site</span></span>|<span data-ttu-id="a9d94-198">**フル コントロール** (クライアント プログラムによって定義されます): 通常、このアクセス許可を使用すると、ユーザーは権限が管理するコンテンツのアクセス許可を読み取り、編集、コピー、保存、および変更できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>|
|<span data-ttu-id="a9d94-199">アイテムの編集、リストの管理、ページの追加とカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a9d94-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>|<span data-ttu-id="a9d94-200">**編集**、**コピー**、および **保存:** ユーザーは、リストまたはライブラリの[Information Rights Management 設定] ページで [ドキュメントの印刷を許可する] チェック ボックスがオンの場合にのみ、ファイルを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="a9d94-201">アイテムの表示</span><span class="sxs-lookup"><span data-stu-id="a9d94-201">View Items</span></span>|<span data-ttu-id="a9d94-202">**読** み取り : ユーザーはドキュメントを読み取るが、そのコンテンツをコピーまたは変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-202">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="a9d94-203">ユーザーは、リストまたは **ライブラリの**[Information Rights Management 設定] ページで [ユーザーにドキュメントの印刷を許可する] チェック ボックスがオンの場合にのみ印刷できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-203">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="a9d94-204">その他</span><span class="sxs-lookup"><span data-stu-id="a9d94-204">Other</span></span>|<span data-ttu-id="a9d94-205">IRM アクセス許可に直接対応するアクセス許可は他にはありません。</span><span class="sxs-lookup"><span data-stu-id="a9d94-205">No other permissions correspond directly to IRM permissions.</span></span>|
   
<span data-ttu-id="a9d94-206">SharePoint Server 2013 でリストまたはライブラリの IRM を有効にした場合、プロテクタがすべてのフロントエンド Web サーバーにインストールされているリストまたはライブラリ内のファイルの種類のみを保護できます。</span><span class="sxs-lookup"><span data-stu-id="a9d94-206">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end web servers.</span></span> <span data-ttu-id="a9d94-207">プロテクタは、特定のファイル形式の権限管理ファイルの暗号化と暗号化解除を制御するプログラムです。</span><span class="sxs-lookup"><span data-stu-id="a9d94-207">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="a9d94-208">SharePointには、次のファイルの種類のプロテクタが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9d94-208">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="a9d94-209">Microsoft OfficeInfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="a9d94-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="a9d94-210">Microsoft Office Word、Microsoft Office Excel、Microsoft Office PowerPoint の 97 から 2003 までのファイル形式</span><span class="sxs-lookup"><span data-stu-id="a9d94-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="a9d94-211">次Officeプログラムの Open XML 形式Microsoft Office Word、Excel、およびPowerPoint</span><span class="sxs-lookup"><span data-stu-id="a9d94-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="a9d94-212">XML Paper Specification (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="a9d94-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="a9d94-213">組織が IRM を使用して上記のファイルの種類に加えて他の種類のファイルを保護する予定がある場合、サーバー管理者は、これらの追加のファイル形式用のプロテクタをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d94-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

