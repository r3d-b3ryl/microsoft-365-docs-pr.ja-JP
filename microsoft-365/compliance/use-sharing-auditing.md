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
description: 管理者は、組織外のユーザーと共有されるリソースを識別するために、Microsoft 365監査ログで共有監査を使用する方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 302ad7665c83ee9061b2e1965ef03ec25d0aab58
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341510"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a><span data-ttu-id="f63e9-103">監査ログで共有監査を使用する</span><span class="sxs-lookup"><span data-stu-id="f63e9-103">Use sharing auditing in the audit log</span></span>

<span data-ttu-id="f63e9-104">共有は、オンラインおよび SharePointおよびOneDrive for Businessの重要なアクティビティであり、組織で広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="f63e9-104">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in organizations.</span></span> <span data-ttu-id="f63e9-105">管理者は、監査ログの共有監査を使用して、組織内での共有の使用方法を判断できます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-105">Administrators can use sharing auditing in the audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="f63e9-106">共有SharePointスキーマ</span><span class="sxs-lookup"><span data-stu-id="f63e9-106">The SharePoint Sharing schema</span></span>

<span data-ttu-id="f63e9-107">共有イベント (共有ポリシーや共有リンクに関連するイベントを含む) は、ファイル関連イベントやフォルダー関連のイベントとは一つの主な方法で異なります。あるユーザーは、別のユーザーに影響を与えるアクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="f63e9-107">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="f63e9-108">たとえば、リソースユーザー A がユーザー B にファイルへのアクセス権を与える場合です。</span><span class="sxs-lookup"><span data-stu-id="f63e9-108">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="f63e9-109">この例では、ユーザー A はユーザー  *であり*  、ユーザー B はターゲット  *ユーザーです*。</span><span class="sxs-lookup"><span data-stu-id="f63e9-109">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="f63e9-110">ファイル スキーマSharePoint、ユーザーの操作はファイル自体にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-110">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="f63e9-111">ユーザー A がファイルを開くと **、FileAccessed** イベントで必要な唯一の情報は、実際のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f63e9-111">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="f63e9-112">この違いに対処するために、共有イベントの詳細をキャプチャする SharePoint共有スキーマ *と呼* ばれる別のスキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="f63e9-112">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="f63e9-113">これにより、管理者は、リソースを共有したユーザーとリソースが共有されたユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-113">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="f63e9-114">共有スキーマは、共有イベントに関連する監査レコードに 2 つの追加フィールドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-114">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="f63e9-115">**TargetUserOrGroupType:** ターゲット ユーザーまたはグループがメンバー、ゲスト、SharePointGroup、SecurityGroup、またはパートナーであるかどうかを識別します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-115">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="f63e9-116">**TargetUserOrGroupName:** リソースが共有されたターゲット ユーザーまたはグループの UPN または名前を格納します (前の例のユーザー B)。</span><span class="sxs-lookup"><span data-stu-id="f63e9-116">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="f63e9-117">これら 2 つのフィールドは、ユーザー、操作、日付などの監査ログ スキーマの他のプロパティに加えて、どのユーザーが誰といつどのリソースを共有したのかを完全に伝 *えます*。 </span><span class="sxs-lookup"><span data-stu-id="f63e9-117">These two fields, in addition to other properties from the audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="f63e9-118">共有ストーリーに重要な別のスキーマ プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f63e9-118">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="f63e9-119">監査ログの検索結果をエクスポートすると、エクスポートされた CSV ファイルの **AuditData** 列に、共有イベントに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-119">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="f63e9-120">たとえば、ユーザーがサイトを別のユーザーと共有する場合、ターゲット ユーザーを別のユーザー グループに追加SharePointします。</span><span class="sxs-lookup"><span data-stu-id="f63e9-120">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="f63e9-121">**AuditData 列は**、この情報をキャプチャして管理者のコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-121">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="f63e9-122">AuditData [列の情報](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) を解析する方法については、手順 2 **を参照** してください。</span><span class="sxs-lookup"><span data-stu-id="f63e9-122">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="f63e9-123">SharePoint共有イベント</span><span class="sxs-lookup"><span data-stu-id="f63e9-123">SharePoint sharing events</span></span>

<span data-ttu-id="f63e9-124">共有は、ユーザー (作用ユーザー)がリソースを別のユーザー (ターゲット ユーザー) と共有する場合に *定義* されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-124">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="f63e9-125">リソースを外部ユーザー (組織の外部にいて、組織の Azure Active Directory にゲスト アカウントを持ってないユーザー) との共有に関連する監査レコードは、監査ログに記録される次のイベントによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-125">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the audit log:</span></span>

- <span data-ttu-id="f63e9-126">**SharingInvitationCreated:** 組織内のユーザーがリソース (サイトの可能性がある) を外部ユーザーと共有しようとした。</span><span class="sxs-lookup"><span data-stu-id="f63e9-126">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="f63e9-127">これにより、外部共有の招待がターゲット ユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-127">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="f63e9-128">この時点では、リソースへのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="f63e9-128">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="f63e9-129">**SharingInvitationAccepted:** 外部ユーザーは、そのユーザーが送信した共有の招待を受け入れ、リソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-129">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="f63e9-130">**AnonymousLinkCreated:** リソースに対して匿名リンク ("Anyone" リンクとも呼ばれる) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-130">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="f63e9-131">匿名リンクを作成してからコピーすることができますので、匿名リンクを持つドキュメントがターゲット ユーザーと共有されたと見なすのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="f63e9-131">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="f63e9-132">**AnonymousLinkUsed:** 名前が示すように、このイベントは、匿名リンクを使用してリソースにアクセスするときに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-132">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="f63e9-133">**SecureLinkCreated:** ユーザーが特定のユーザーとリソースを共有する "特定のユーザー リンク" を作成しました。</span><span class="sxs-lookup"><span data-stu-id="f63e9-133">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="f63e9-134">このターゲット ユーザーは、組織外のユーザーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f63e9-134">This target user may be someone who is external to your organization.</span></span> <span data-ttu-id="f63e9-135">リソースが共有されているユーザーは **、AddedToSecureLink** イベントの監査レコードで識別されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-135">The person that the resource is shared with is identified in the audit record for the **AddedToSecureLink** event.</span></span> <span data-ttu-id="f63e9-136">これら 2 つのイベントのタイム スタンプは、ほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="f63e9-136">The time stamps for these two events are nearly identical.</span></span>

- <span data-ttu-id="f63e9-137">**AddedToSecureLink:** ユーザーが特定のユーザー リンクに追加されました。</span><span class="sxs-lookup"><span data-stu-id="f63e9-137">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="f63e9-138">このイベントの **TargetUserOrGroupName** フィールドを使用して、対応する特定のユーザー リンクに追加されたユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-138">Use the **TargetUserOrGroupName** field in this event to identify the user added to the corresponding specific people link.</span></span> <span data-ttu-id="f63e9-139">このターゲット ユーザーは、組織外のユーザーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f63e9-139">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="f63e9-140">監査の作業フローの共有</span><span class="sxs-lookup"><span data-stu-id="f63e9-140">Sharing auditing work flow</span></span>
  
<span data-ttu-id="f63e9-141">ユーザー (作用するユーザー) がリソースを別のユーザー (ターゲット ユーザー) と共有する場合、SharePoint (または OneDrive for Business) は、ターゲット ユーザーの電子メール アドレスが組織のディレクトリ内のユーザー アカウントに既に関連付けられているか最初に確認します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-141">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="f63e9-142">ターゲット ユーザーがディレクトリに (対応するゲスト ユーザー アカウントを持つ) 場合、SharePointを実行します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-142">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="f63e9-143">ターゲット ユーザーを適切なグループに追加して、リソースにアクセスするターゲット ユーザーのアクセス許可をすぐに割り当て **、AddedToGroup** イベントSharePointログに記録します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-143">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="f63e9-144">共有通知をターゲット ユーザーの電子メール アドレスに送信します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-144">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="f63e9-145">**SharingSet イベントをログに記録** します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-145">Logs a **SharingSet** event.</span></span> <span data-ttu-id="f63e9-146">このイベントには、監査ログ検索ツールのアクティビティ ピッカーの [共有とアクセス要求のアクティビティ] の下に、"共有ファイル、フォルダー、またはサイト" という名前のフレンドリーな名前が付きます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-146">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="f63e9-147">手順 1 のスクリーンショット [を参照してください](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)。</span><span class="sxs-lookup"><span data-stu-id="f63e9-147">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="f63e9-148">ターゲット ユーザーのユーザー アカウントがディレクトリに存在しない場合、SharePointを実行します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-148">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="f63e9-149">リソースの共有方法に基づいて、次のいずれかのイベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-149">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="f63e9-150">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="f63e9-150">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="f63e9-151">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="f63e9-151">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="f63e9-152">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="f63e9-152">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="f63e9-153">**SharingInvitationCreated** (このイベントは、共有リソースがサイトの場合にのみログに記録されます)</span><span class="sxs-lookup"><span data-stu-id="f63e9-153">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="f63e9-154">ターゲット ユーザーが (招待内のリンクをクリックして) 送信された共有招待を受け入れる場合、SharePoint は **SharingInvitationAccepted** イベントをログに記録し、リソースにアクセスするためのターゲット ユーザーのアクセス許可を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f63e9-154">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="f63e9-155">ターゲット ユーザーに匿名リンクが送信された場合、ターゲット ユーザーがリンクを使用してリソースにアクセスした後 **、AnonymousLinkUsed** イベントがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-155">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="f63e9-156">セキュリティで保護されたリンクの場合、外部ユーザーがリンクを使用してリソースにアクセスすると **、FileAccessed** イベントがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-156">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="f63e9-157">招待先のユーザーの ID や、招待を受け入れるユーザーなど、ターゲット ユーザーに関する追加情報も記録されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-157">Additional information about the target user is also logged, such as the identity of the user the invitation is to and the user who accepts the invitation.</span></span> <span data-ttu-id="f63e9-158">場合によっては、これらのユーザー (または電子メール アドレス) が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f63e9-158">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="f63e9-159">外部ユーザーと共有されているリソースを識別する方法</span><span class="sxs-lookup"><span data-stu-id="f63e9-159">How to identify resources shared with external users</span></span>

<span data-ttu-id="f63e9-160">管理者の一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-160">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="f63e9-161">管理者は、共有監査をOffice 365、この一覧を生成できます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-161">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="f63e9-162">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-162">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="f63e9-163">手順 1: 共有イベントを検索し、CSV ファイルに結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f63e9-163">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="f63e9-164">最初の手順は、監査ログで共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-164">The first step is to search the audit log for sharing events.</span></span> <span data-ttu-id="f63e9-165">監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「セキュリティ コンプライアンス センターで監査ログを検索する」を参照& [してください](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="f63e9-165">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="f63e9-166"><https://compliance.microsoft.com> に移動します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-166">Go to <https://compliance.microsoft.com>.</span></span>

2. <span data-ttu-id="f63e9-167">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f63e9-167">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="f63e9-168">ウィンドウの左側のウィンドウで、[監査Microsoft 365 コンプライアンス センターを **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f63e9-168">In the left pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

    <span data-ttu-id="f63e9-169">[**監査**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-169">The **Audit** page is displayed.</span></span>

4. <span data-ttu-id="f63e9-170">[ **アクティビティ] で**、[ **共有とアクセス要求アクティビティ] をクリックして** 、共有関連イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-170">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 

    ![[アクティビティ] で、[要求アクティビティの共有とアクセス] を選択します。](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. <span data-ttu-id="f63e9-172">日付と時刻の範囲を選択して、その期間中に発生した共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-172">Select a date and time range to find the sharing events that occurred within that period.</span></span> 

6. <span data-ttu-id="f63e9-173">[検索 **] を** クリックして検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-173">Click **Search** to run the search.</span></span> 

7. <span data-ttu-id="f63e9-174">検索の実行が完了し、結果が表示された場合は、[結果のエクスポート] **をクリックしてすべての結果** \> **をダウンロードします**。</span><span class="sxs-lookup"><span data-stu-id="f63e9-174">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>

    <span data-ttu-id="f63e9-175">エクスポート オプションを選択すると、ウィンドウの下部にあるメッセージで、CSV ファイルを開くまたは保存するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-175">After you select the export option, a message at the bottom of the window prompts you to open or save the CSV file.</span></span>

8. <span data-ttu-id="f63e9-176">[ **名前を** \> **付けて保存]** をクリックし、CSV ファイルをローカル コンピューターのフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-176">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="f63e9-177">手順 2: PowerQuery エディターを使用してエクスポートされた監査ログの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="f63e9-177">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="f63e9-178">次の手順では、Excel の Power Query Editor の JSON 変換機能を使用して **、AuditData** 列 (複数プロパティ JSON オブジェクトで構成される) の各プロパティを独自の列に分割します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-178">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="f63e9-179">これにより、列をフィルター処理して、共有に関連するレコードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-179">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="f63e9-180">詳しい手順については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f63e9-180">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="f63e9-181">手順 3: 外部ユーザーと共有するリソースの CSV ファイルをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="f63e9-181">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="f63e9-182">次の手順では、「共有イベントの共有」セクションで前述したさまざまな共有関連イベントに対して[CSV をSharePointします](#sharepoint-sharing-events)。</span><span class="sxs-lookup"><span data-stu-id="f63e9-182">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="f63e9-183">または **、TargetUserOrGroupType** 列をフィルター処理して、このプロパティの値が Guest であるすべてのレコードを **表示できます**。</span><span class="sxs-lookup"><span data-stu-id="f63e9-183">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="f63e9-184">前の手順に従って、PowerQuery エディターを使用して CSV ファイルを準備した後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-184">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="f63e9-185">手順 2 でExcelしたファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-185">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="f63e9-186">[ホーム] **タブで** 、[フィルターの並 **べ替え&] をクリック** し、[フィルター] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f63e9-186">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="f63e9-187">[操作]**列&** [フィルターの並べ替え] ドロップダウン リストで、すべての選択をクリアし、次の共有関連イベントを 1 つ以上選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f63e9-187">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="f63e9-188">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="f63e9-188">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="f63e9-189">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="f63e9-189">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="f63e9-190">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="f63e9-190">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="f63e9-191">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="f63e9-191">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="f63e9-192">Excel選択したイベントの行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f63e9-192">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="f63e9-193">**TargetUserOrGroupType という名前の列に移動し**、選択します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-193">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="f63e9-194">[フィルター **の並べ&] ドロップダウン** リストで、すべての選択をクリアし **、[TargetUserOrGroupType:Guest]** を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f63e9-194">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="f63e9-195">外部Excel **TargetUserOrGroupType:Guest** の値で識別されるので、共有イベントの行と、ターゲット ユーザーが組織の外部にある場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="f63e9-195">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f63e9-196">表示される監査レコードの場合 **、ObjectId** 列は、ターゲット ユーザーと共有されたリソースを識別します。たとえば  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .</span><span class="sxs-lookup"><span data-stu-id="f63e9-196">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
