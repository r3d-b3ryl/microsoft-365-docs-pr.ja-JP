---
title: 監査ログで共有監査を使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 管理者は、Microsoft 365 監査ログで共有監査を使用して、組織外のユーザーと共有されているリソースを識別する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819297"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a><span data-ttu-id="c00fe-103">監査ログで共有監査を使用する</span><span class="sxs-lookup"><span data-stu-id="c00fe-103">Use sharing auditing in the audit log</span></span>

<span data-ttu-id="c00fe-104">共有は、SharePoint Online と OneDrive for business の主要なアクティビティであり、組織で広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="c00fe-104">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in organizations.</span></span> <span data-ttu-id="c00fe-105">管理者は監査ログで共有監査を使用して、組織での共有の使用方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-105">Administrators can use sharing auditing in the audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="c00fe-106">SharePoint 共有スキーマ</span><span class="sxs-lookup"><span data-stu-id="c00fe-106">The SharePoint Sharing schema</span></span>

<span data-ttu-id="c00fe-107">共有イベント (共有ポリシーと共有リンクに関連するイベントは含まれません) は、1人のユーザーが別のユーザーに影響を与えるアクションを実行しているという主な方法で、ファイルとフォルダーに関連するイベントとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-107">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="c00fe-108">たとえば、リソースユーザー A がファイルへのアクセス権をユーザー B に付与したとします。</span><span class="sxs-lookup"><span data-stu-id="c00fe-108">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="c00fe-109">この例では、ユーザー A は、動作している*ユーザー*で、ユーザー B は*対象ユーザー*です。</span><span class="sxs-lookup"><span data-stu-id="c00fe-109">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="c00fe-110">SharePoint ファイルスキーマでは、動作しているユーザーの操作だけがファイル自体に影響します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-110">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="c00fe-111">ユーザーがファイルを開くと、 **Fileaccessed**イベントに必要な情報は、動作しているユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-111">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="c00fe-112">この違いに対処するために、共有イベントに関する詳細情報を収集する、 *SharePoint 共有スキーマ*と呼ばれる別のスキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-112">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="c00fe-113">これにより、管理者がリソースを共有しているユーザーや、リソースが共有されていたユーザーを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-113">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="c00fe-114">共有スキーマは、イベントの共有に関連する監査レコードに2つの追加フィールドを提供します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-114">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="c00fe-115">**TargetUserOrGroupType:** 対象のユーザーまたはグループが、Member、Guest、SharePointGroup、Microsoft.rtc.management.writableconfig.settings.centralizedlogging.securitygroup、または Partner であるかどうかを識別します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-115">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="c00fe-116">**Targetuserorgroupname:** リソースが共有されていたターゲットユーザーまたはグループの UPN または名前を格納します (前の例では User B)。</span><span class="sxs-lookup"><span data-stu-id="c00fe-116">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="c00fe-117">ユーザー、操作、日付などの監査ログスキーマの他のプロパティに加えて、これらの2つのフィールドには、*どの*ユーザーがどのリソースを*どのよう*な*とき*に*共有し*たかについての完全なストーリーを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-117">These two fields, in addition to other properties from the audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="c00fe-118">共有ストーリーにとって重要なスキーマプロパティは他にもあります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-118">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="c00fe-119">監査ログの検索結果をエクスポートすると、エクスポートされた CSV ファイルの**Auditdata**列に、共有イベントに関する情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-119">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="c00fe-120">たとえば、ユーザーが別のユーザーとサイトを共有する場合は、ターゲットユーザーを SharePoint グループに追加することによって実現します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-120">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="c00fe-121">**Auditdata**列は、管理者向けにコンテキストを提供するために、この情報を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-121">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="c00fe-122">**Auditdata**列の情報を解析する手順については、[手順 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00fe-122">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="c00fe-123">SharePoint 共有イベント</span><span class="sxs-lookup"><span data-stu-id="c00fe-123">SharePoint sharing events</span></span>

<span data-ttu-id="c00fe-124">共有は、ユーザー (*動作*しているユーザー) が別のユーザー (*ターゲット*ユーザー) とリソースを共有しようとしたときに定義されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-124">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="c00fe-125">外部ユーザーとのリソースの共有に関連する監査レコード (組織外のユーザーが組織の Azure Active Directory にゲストアカウントを持っていない場合) は、監査ログに記録されている次のイベントによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-125">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the audit log:</span></span>

- <span data-ttu-id="c00fe-126">**SharingInvitationCreated:** 組織内のユーザーが外部ユーザーとリソース (通常はサイト) を共有しようとしました。</span><span class="sxs-lookup"><span data-stu-id="c00fe-126">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="c00fe-127">この結果、外部共有への招待がターゲットユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-127">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="c00fe-128">この時点では、リソースへのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="c00fe-128">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="c00fe-129">**SharingInvitationAccepted:** 外部ユーザーが、動作しているユーザーによって送信された共有の招待を承諾し、リソースにアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c00fe-129">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="c00fe-130">**AnonymousLinkCreated:** 匿名リンク ([すべてのユーザー] リンクとも呼ばれます) は、リソースに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-130">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="c00fe-131">匿名リンクを作成してコピーすることができるので、匿名リンクが設定されているドキュメントは、ターゲットユーザーと共有していることを前提としては十分です。</span><span class="sxs-lookup"><span data-stu-id="c00fe-131">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="c00fe-132">**AnonymousLinkUsed:** その名前が示すように、このイベントは、匿名リンクを使用してリソースにアクセスしたときに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-132">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="c00fe-133">**Securelinkcreated:** ユーザーが、特定のユーザーとリソースを共有するための "特定のユーザーリンク" を作成しました。</span><span class="sxs-lookup"><span data-stu-id="c00fe-133">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="c00fe-134">このターゲットユーザーには、組織の外部にいる人がいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-134">This target user may be someone who is external to your organization.</span></span> <span data-ttu-id="c00fe-135">リソースを共有しているユーザーは、 **Addedtosecurelink**イベントの監査レコードで識別されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-135">The person that the resource is shared with is identified in the audit record for the **AddedToSecureLink** event.</span></span> <span data-ttu-id="c00fe-136">これら2つのイベントのタイムスタンプはほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="c00fe-136">The time stamps for these two events are nearly identical.</span></span>

- <span data-ttu-id="c00fe-137">**Addedtosecurelink:** ユーザーが特定の人物リンクに追加されました。</span><span class="sxs-lookup"><span data-stu-id="c00fe-137">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="c00fe-138">このイベントの**Targetuserorgroupname**フィールドを使用して、対応する特定の people リンクに追加されたユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-138">Use the **TargetUserOrGroupName** field in this event to identify the user added to the corresponding specific people link.</span></span> <span data-ttu-id="c00fe-139">このターゲットユーザーには、組織の外部にいる人がいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-139">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="c00fe-140">共有監査ワークフロー</span><span class="sxs-lookup"><span data-stu-id="c00fe-140">Sharing auditing work flow</span></span>
  
<span data-ttu-id="c00fe-141">ユーザー (動作しているユーザー) が別のユーザー (ターゲットユーザー) とリソースを共有しようとしている場合、SharePoint (または OneDrive for Business) は最初に、対象ユーザーの電子メールアドレスが組織のディレクトリ内のユーザーアカウントに関連付けられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-141">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="c00fe-142">ターゲットユーザーがディレクトリ内にあり、対応するゲストユーザーアカウントを持っている場合、SharePoint は次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="c00fe-142">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="c00fe-143">ターゲットユーザーを適切な SharePoint グループに追加して、リソースにアクセスするためのターゲットユーザーのアクセス許可を即時に割り当て、 **Addedtogroup**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-143">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="c00fe-144">ターゲットユーザーの電子メールアドレスに共有通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-144">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="c00fe-145">**Sharingset**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-145">Logs a **SharingSet** event.</span></span> <span data-ttu-id="c00fe-146">このイベントには、監査ログ検索ツールの [アクティビティの選択] の [**共有とアクセスの要求のアクティビティ**] の [共有ファイル、フォルダー、またはサイト] のフレンドリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-146">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="c00fe-147">[手順 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)のスクリーンショットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00fe-147">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="c00fe-148">ターゲットユーザーのユーザーアカウントがディレクトリにない場合、SharePoint は次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="c00fe-148">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="c00fe-149">リソースがどのように共有されているかに基づいて、次のいずれかのイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-149">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="c00fe-150">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c00fe-150">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="c00fe-151">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c00fe-151">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="c00fe-152">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="c00fe-152">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="c00fe-153">**SharingInvitationCreated** (このイベントは、共有リソースがサイトである場合にのみ記録されます)</span><span class="sxs-lookup"><span data-stu-id="c00fe-153">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="c00fe-154">ターゲットユーザーが (招待のリンクをクリックすることによって) 送信された共有の招待を承諾すると、SharePoint は**SharingInvitationAccepted**イベントをログに記録し、リソースにアクセスするためのアクセス許可をターゲットユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-154">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="c00fe-155">ターゲットユーザーが匿名リンクを送信している場合、ターゲットユーザーがリンクを使用してリソースにアクセスした後、 **AnonymousLinkUsed**イベントがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-155">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="c00fe-156">セキュリティで保護されたリンクの場合、外部ユーザーがリンクを使用してリソースにアクセスするときに、 **fileaccessed**イベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-156">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="c00fe-157">対象ユーザーに関する追加情報もログに記録されます。たとえば、招待されたユーザーの id、招待を承諾したユーザーの id などが記録されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-157">Additional information about the target user is also logged, such as the identity of the user the invitation is to and the user who accepts the invitation.</span></span> <span data-ttu-id="c00fe-158">場合によっては、これらのユーザー (またはメールアドレス) が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c00fe-158">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="c00fe-159">外部ユーザーと共有されるリソースを特定する方法</span><span class="sxs-lookup"><span data-stu-id="c00fe-159">How to identify resources shared with external users</span></span>

<span data-ttu-id="c00fe-160">管理者にとって一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成することです。</span><span class="sxs-lookup"><span data-stu-id="c00fe-160">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="c00fe-161">Office 365 で共有監査を使用すると、管理者はこの一覧を生成できます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-161">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="c00fe-162">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-162">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="c00fe-163">手順 1: 共有イベントを検索し、結果を CSV ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="c00fe-163">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="c00fe-164">最初の手順として、監査ログで共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-164">The first step is to search the audit log for sharing events.</span></span> <span data-ttu-id="c00fe-165">監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「[セキュリティ & のコンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00fe-165">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="c00fe-166">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-166">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c00fe-167">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c00fe-167">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="c00fe-168">セキュリティ/コンプライアンス センターの左側のウィンドウで、[**検索**]   >  [**監査ログの検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c00fe-168">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="c00fe-169">[**監査ログの検索**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-169">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="c00fe-170">[**アクティビティ**] の下の [**共有とアクセス要求アクティビティ**] をクリックして、共有関連イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-170">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![[アクティビティ] の下で、[共有とアクセスの要求のアクティビティ] を選択します。](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="c00fe-172">日付と時刻の範囲を選択して、その期間内に発生した共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-172">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="c00fe-173">[**検索**] をクリックして検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-173">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="c00fe-174">検索の実行が完了し、結果が表示されたら、[**結果のエクスポート**] をクリックしてすべての \> **結果をダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-174">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="c00fe-175">[エクスポート] オプションを選択すると、ウィンドウの下部にメッセージが表示され、CSV ファイルを開いたり保存したりするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-175">After you select the export option, a message at the bottom of the window prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="c00fe-176">[名前を付けて保存] を**クリックし** \> **Save as** 、CSV ファイルをローカルコンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-176">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="c00fe-177">手順 2: PowerQuery Editor を使用して、エクスポートされた監査ログを書式設定する</span><span class="sxs-lookup"><span data-stu-id="c00fe-177">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="c00fe-178">次の手順では、Excel の Power Query エディターで JSON 変換機能を使用して、 **Auditdata**列 (複数のプロパティを持つ JSON オブジェクトから構成される) の各プロパティをそれぞれの列に分割します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-178">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="c00fe-179">これにより、共有に関連するレコードを表示するための列をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-179">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="c00fe-180">詳細な手順については、「[エクスポート、構成、および監査ログレコードの表示](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: エクスポートされた監査ログを Power Query エディターを使用して書式設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00fe-180">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="c00fe-181">手順 3: 外部ユーザーと共有しているリソースの CSV ファイルをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c00fe-181">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="c00fe-182">次の手順では、 [SharePoint 共有イベント](#sharepoint-sharing-events)セクションに記載されている、さまざまな共有関連イベントに対して CSV をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-182">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="c00fe-183">または、 **TargetUserOrGroupType**列をフィルター処理して、このプロパティの値が**Guest**になっているすべてのレコードを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-183">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="c00fe-184">前の手順の手順に従って、PowerQuery エディターを使用して CSV ファイルを準備した後、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c00fe-184">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="c00fe-185">手順2で作成した Excel ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-185">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="c00fe-186">[**ホーム**] タブで、[**並べ替え & フィルター**] をクリックし、[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c00fe-186">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="c00fe-187">[**操作**] 列の [**並べ替え & フィルター** ] ボックスの一覧で、すべての選択をオフにし、次に共有関連のイベントを1つ以上選択して、[ **Ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c00fe-187">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="c00fe-188">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="c00fe-188">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="c00fe-189">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c00fe-189">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="c00fe-190">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c00fe-190">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="c00fe-191">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="c00fe-191">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="c00fe-192">Excel には、選択したイベントの行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-192">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="c00fe-193">**TargetUserOrGroupType**という名前の列に移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="c00fe-193">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="c00fe-194">[**並べ替え & フィルター** ] ドロップダウンリストで、すべての選択をオフにし、[ **TargetUserOrGroupType: Guest**] を選択して、[ **Ok**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c00fe-194">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="c00fe-195">ここでは、外部ユーザーは**TargetUserOrGroupType: GUEST**という値で識別されるため、共有イベントの行と、対象ユーザーが組織外にある場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-195">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c00fe-196">表示されている監査レコードについては、 **ObjectId**列に、ターゲットユーザーと共有されているリソースが示されます。例を示し `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` ます。</span><span class="sxs-lookup"><span data-stu-id="c00fe-196">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
