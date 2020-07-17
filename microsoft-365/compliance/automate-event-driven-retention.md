---
title: イベント ベースの保持を自動化する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: このトピックでは、Microsoft 365 REST API を使用して、イベントによってビジネス プロセス フローの自動化の保持をセットアップする方法について説明します。
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068116"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="8d16d-103">イベント ベースの保持を自動化する</span><span class="sxs-lookup"><span data-stu-id="8d16d-103">Automate event-based retention</span></span>

><span data-ttu-id="8d16d-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8d16d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8d16d-p101">組織内でのコンテンツの急増やコンテンツの ROT (冗長、旧版、無駄) 化は、ビジネスにとって深刻な課題です。法令、業務、規制に関するコンプライアンスの課題に継続的に対応するには、企業は重要な情報を保持して保護し、必要な情報をすばやく見つけられる必要があります。重要かつ適切な情報のみを保持することがビジネスを成功させる上での鍵です。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="8d16d-p102">この要求を満たすために、組織は Office 365 セキュリティ/コンプライアンス センターの保持ソリューションを活用できます。保持は、[保持ラベル](labels.md)を使用してトリガーできます。保持ラベルには、[特定のイベントに基づいて保持期間を設定する](event-driven-retention.md)オプションがあります。通常、保持期間は、コンテンツの作成日や最終変更日など既知の日付に基づきます。ただし、組織で、ある従業員が組織から離れてから 7 年後などの特定のイベントに基づいてコンテンツを破棄するという要件が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="8d16d-p103">スケジュールに則りコンテンツを破棄するには、イベントが生じた時期を把握することが不可欠です。コンテンツの量が急速に増えている現在、コンプライアンスを守りながらコンテンツの保持および破棄を適時行うことは困難になりつつあります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="8d16d-p104">イベント ベースの保持はこの問題を解決できます。このトピックでは、Microsoft 365 REST API を使用して、イベントによりビジネス プロセス フローの保持の自動化をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="8d16d-117">イベント ベースの保持について</span><span class="sxs-lookup"><span data-stu-id="8d16d-117">About event-based retention</span></span>

<span data-ttu-id="8d16d-p105">組織の規模は小、中、大とさまざまです。日常的に作成および管理されるビジネス文書、法的文書、従業員のファイル、契約書、製品文書は劇的に増えています。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="8d16d-p106">たとえば、数十、数百単位の従業員が入社したり退社したりします。人事部はビジネス要件に基づいて従業員関連の文書を継続的に作成、更新、削除します。このプロセスは、会社で規定されている各種保持ポリシーの対象となります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="8d16d-p107">**コンテンツの保持期間は既知の日付にすることが可能です**。たとえば、コンテンツの作成日、最終変更日またはラベル設定日などです。文書を作成後 7 年間保持し、その後処分するなどが可能です。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="8d16d-p108">**またコンテンツの保持期間を不明な日付にすることもできます**。たとえば、保持ラベルを使用すると、従業員が組織を離れるなどの特定のイベントが生じる時点に基づいて保持期間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="8d16d-p109">保持期間の開始はイベントによりトリガーされ、その種類のイベントのラベルが適用されているすべてのコンテンツに対してそのラベルの保持アクションが実行されます。これを、イベント ベースの保持と呼びます。詳細については、「[イベント ベースの保持の概要](event-driven-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="8d16d-130">イベント ベースの保持をセットアップする</span><span class="sxs-lookup"><span data-stu-id="8d16d-130">Set up event-based retention</span></span>

<span data-ttu-id="8d16d-131">このセクションでは、コンテンツを保持する前に行う必要がある作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="8d16d-132">役割を特定する</span><span class="sxs-lookup"><span data-stu-id="8d16d-132">Identify roles</span></span>

<span data-ttu-id="8d16d-133">レコード管理業務を実行し、業務文書の有効かつ効率的な保持に関して責任を担う、組織内の各役割を特定します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="8d16d-134">ペルソナ</span><span class="sxs-lookup"><span data-stu-id="8d16d-134">Persona</span></span> | <span data-ttu-id="8d16d-135">役割</span><span class="sxs-lookup"><span data-stu-id="8d16d-135">Role</span></span> |
  | - | - |
  | <span data-ttu-id="8d16d-136">管理者</span><span class="sxs-lookup"><span data-stu-id="8d16d-136">Admin</span></span> | <span data-ttu-id="8d16d-137">保持イベントの種類、保持ラベル、レコード リポジトリを SharePoint で作成します</span><span class="sxs-lookup"><span data-stu-id="8d16d-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="8d16d-138">レコード管理者</span><span class="sxs-lookup"><span data-stu-id="8d16d-138">Records Manager</span></span>                                  | <span data-ttu-id="8d16d-139">保持ポリシー、保持スケジュール ガイダンス、コンプライアンスの詳細を提供します</span><span class="sxs-lookup"><span data-stu-id="8d16d-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="8d16d-140">システム管理者 (会社)</span><span class="sxs-lookup"><span data-stu-id="8d16d-140">System Admin (business)</span></span>                          | <span data-ttu-id="8d16d-141">Microsoft 365 を扱う外部システムをセットアップして管理します</span><span class="sxs-lookup"><span data-stu-id="8d16d-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="8d16d-142">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="8d16d-142">Information Worker</span></span>                               | <span data-ttu-id="8d16d-143">(人事、財務、IT など) ビジネス プロセスのライフサイクルを管理します</span><span class="sxs-lookup"><span data-stu-id="8d16d-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="8d16d-144">セキュリティ/コンプライアンス センターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="8d16d-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="8d16d-145">コンプライアンス管理者がイベントの種類を作成します &ndash; たとえば、従業員の解雇、契約満了、製品の製造終了などです。</span><span class="sxs-lookup"><span data-stu-id="8d16d-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="8d16d-146"> (「[イベント ベースの保持](event-driven-retention.md)」で説明するプロセスの手順を参照してください。）</span><span class="sxs-lookup"><span data-stu-id="8d16d-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="8d16d-147">コンプライアンス管理者は、イベントに基づいて保持ラベルを作成し、そのラベルをイベントの種類に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="8d16d-148">保持ラベルのトリガーには 4 種類あります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="8d16d-149">作成日</span><span class="sxs-lookup"><span data-stu-id="8d16d-149">Create date</span></span>
                
    2. <span data-ttu-id="8d16d-150">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="8d16d-150">Last modified</span></span>
                
    3. <span data-ttu-id="8d16d-151">ラベル日付 (コンテンツがラベル付けされた日)</span><span class="sxs-lookup"><span data-stu-id="8d16d-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="8d16d-152">イベント ベース</span><span class="sxs-lookup"><span data-stu-id="8d16d-152">Event-based</span></span>
    
3. <span data-ttu-id="8d16d-153">コンプライアンス管理者が保持ラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="8d16d-154">SharePoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="8d16d-154">Set up SharePoint</span></span>
   
<span data-ttu-id="8d16d-155">レコード リポジトリを作成するには、コンプライアンス管理者は次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8d16d-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="8d16d-156">SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="8d16d-157">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-157">Does one of the following:</span></span>
        
   - <span data-ttu-id="8d16d-p111">SharePoint ライブラリを作成します。ライブラリ レベルでイベント ベースのラベルを設定します。詳しくは、[SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
   - <span data-ttu-id="8d16d-160">SharePoint でドキュメント セットをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="8d16d-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="8d16d-161">詳細については、「[ドキュメント セット の概要](https://support.microsoft.com/ja-JP/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d16d-161">For more information, see [Introduction to document sets](https://support.microsoft.com/ja-JP/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="8d16d-162">各従業員のドキュメント セットに資産 ID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="8d16d-163">資産 ID は、組織で使用されている製品名またはコードです。たとえば、従業員番号を資産 ID として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="8d16d-164">フォルダーに資産 ID を割り当てることで、そのフォルダー内のすべてのアイテムに同じ資産 ID が自動的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="8d16d-165">同一のイベントにより、すべてのアイテムで保持期間をトリガーできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="8d16d-166">イベント ベースの保持をトリガーする方法</span><span class="sxs-lookup"><span data-stu-id="8d16d-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="8d16d-167">イベント ベースの保持をトリガーするには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="8d16d-168">**管理センター UI を使用する** このプロセスは、同時に保持するコンテンツを減らしたり、保持をトリガーする頻度を減らしたり (月次、年次など) するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="8d16d-169">この方法の詳細については、「[イベント ベースの保持の概要](event-driven-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d16d-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="8d16d-170">ただし、保持をトリガーするためのこの方法は、時間がかかる場合があり、エラーも発生しやすいため、大規模な適用には不向きです。</span><span class="sxs-lookup"><span data-stu-id="8d16d-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="8d16d-171">そのため、自動化されたシームレスなソリューションを使用して保持をトリガーさせることで、データのセキュリティとコンプライアンスを向上させられます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="8d16d-p115">**M365 REST API を使用する** このプロセスは、1 度に大量のコンテンツを保持したり、保持をトリガーする頻度が毎日や週ごとなど多い場合に使用できます。このフローによって基幹業務システムでイベントが生じたタイミングが検出され、セキュリティ/コンプライアンス センターで関連するイベントが自動的に作成されます。該当するイベントが生じるたびに UI でイベントを手動で作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="8d16d-175">REST API の使用に関して次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="8d16d-176">イベントの発生を自動的にトリガーするために、**Microsoft Flow または同様のアプリケーション**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="8d16d-177">Microsoft Flow は、他のシステムとの接続における統合機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="8d16d-178">Microsoft Flow は、カスタム ソリューションがなくても使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="8d16d-179">**PowerShell または HTTP クライアントを使用して REST API を呼び出す** PowerShell (バージョン 6 以降) を使用して Microsoft 365 REST API を呼び出してイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="8d16d-180">Rest API は一連の HTTP 操作 (メソッド) をサポートするサービス エンドポイントで、サービスのリソースに対する作成/取得/更新/削除のアクセス権を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="8d16d-181">詳細については、「[REST API 要求/応答のコンポーネント](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d16d-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="8d16d-182">この場合、Microsoft 365 REST API を使用することにより、POST および GET 操作 (メソッド) を使用してイベントを作成および取得できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="8d16d-183">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="8d16d-183">Example scenarios</span></span>

<span data-ttu-id="8d16d-184">次のシナリオについて考えます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="8d16d-185">シナリオ 1: 従業員が組織のメンバーでなくなる</span><span class="sxs-lookup"><span data-stu-id="8d16d-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="8d16d-186">組織では、従業員ごとに多数の従業員関連文書を作成し、保管しています。</span><span class="sxs-lookup"><span data-stu-id="8d16d-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="8d16d-187">これらの文書は、各従業員の雇用期間中、管理および保持されます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="8d16d-188">ただし、従業員が組織のメンバーでなくなったり、従業員が退職したりした場合、法的および会社の要件に基づいて、規定された期間、その従業員の文書を保持する義務が組織にはあります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="8d16d-189">ここで、複数の従業員が毎日組織のメンバーでなくなるとすると、数千ではないものの数百もの文書の保持期間を毎日トリガーしなくてはなりません。</span><span class="sxs-lookup"><span data-stu-id="8d16d-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="8d16d-190">また、各従業員に関して保持期間を計算する必要もあります。従業員の退社日に、従業員レコードの種類に応じて、日数、月数、または年数を加算します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="8d16d-191">たとえば、要求される保持期間が、従業員の労働者災害補償の書類と同じ従業員の福利厚生申請書類とで異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="8d16d-192">次の図には、1 つのイベントに複数のラベルを関連付けられることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8d16d-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="8d16d-193">「労働者災害補償 (Worker’s compensation)」ラベル下のすべてのファイルと、「従業員の福利厚生 (Employee benefits)」ラベル下のすべてのファイルがどちらも、従業員が組織のメンバーでなくなるという単一のイベントに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="8d16d-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="8d16d-194">これらのファイルの保持期間はそれぞれ異なります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="8d16d-195">そのため、従業員が組織のメンバーでなくなると、各ラベルのファイルには異なる保持期間が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="8d16d-196">各従業員について、ファイルの各種類または各ラベルのこれらの異なる保持期間をすべてトリガーすることは、困難な作業です。</span><span class="sxs-lookup"><span data-stu-id="8d16d-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="8d16d-197">この作業を複数の従業員に対して行う場合は、困難さがさらに強まります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-197">Imagine doing this for multiple employees.</span></span>

![イベントの種類、イベント、およびラベルの図](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="8d16d-199">そのため、複数の従業員に対して異なる保持期間をトリガーする自動化されたプロセスでは、時間を節約し、エラーをなくし、効率性を非常に高められます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="8d16d-200">**このシナリオに関する自動化されたイベント ベースの保持を構成する:**</span><span class="sxs-lookup"><span data-stu-id="8d16d-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![従業員が組織のメンバーでなくなるシナリオに関する役割とアクションの図](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="8d16d-202">管理者は Jane Doe、John Smith などのドキュメント セットに従業員フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="8d16d-203">管理者は、福利厚生、給与、労働者災害補償などの従業員ファイルを各従業員フォルダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="8d16d-204">管理者は、各従業員フォルダーに資産 ID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="8d16d-205">SCC 管理者は、セキュリティ/コンプライアンス センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="8d16d-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="8d16d-206">SCC 管理者は、「従業員解雇」や「従業員雇用」など、従業員関連のイベントの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="8d16d-207">SCC 管理者は、「従業員保持」ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="8d16d-208">この「従業員の保持」ラベルを発行し、SharePoint 内の従業員ファイルに手動または自動で適用します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="8d16d-209">Workday などの人事管理システムを Microsoft Flow と連携させることにより、従業員ファイルの管理を定期的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="8d16d-210">従業員が組織のメンバーではなくなると、Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の従業員ファイルの保持期間が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="8d16d-211">Microsoft Flow の使用</span><span class="sxs-lookup"><span data-stu-id="8d16d-211">Using Microsoft Flow</span></span>

<span data-ttu-id="8d16d-212">手順 1 - Microsoft 365 REST API を使用してイベントを作成するフローを作成します</span><span class="sxs-lookup"><span data-stu-id="8d16d-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Flow を使用してイベントを作成する](../media/automate-event-driven-retention-flow-1.png)

![Flow を使用して REST API を呼び出す](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="8d16d-215">イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="8d16d-215">Create an event</span></span>

<span data-ttu-id="8d16d-216">REST API を呼び出すサンプル コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-216">Sample code to call the REST API:</span></span>

- <span data-ttu-id="8d16d-217">**方法**: 投稿</span><span class="sxs-lookup"><span data-stu-id="8d16d-217">**Method**: POST</span></span>
- <span data-ttu-id="8d16d-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="8d16d-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="8d16d-219">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d16d-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="8d16d-220">**本文**:</span><span class="sxs-lookup"><span data-stu-id="8d16d-220">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- <span data-ttu-id="8d16d-221">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d16d-221">**Authentication**: Basic</span></span>
- <span data-ttu-id="8d16d-222">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d16d-222">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="8d16d-223">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d16d-223">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="8d16d-224">利用可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="8d16d-224">Available parameters</span></span>


|<span data-ttu-id="8d16d-225">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d16d-225">Parameters</span></span>|<span data-ttu-id="8d16d-226">説明</span><span class="sxs-lookup"><span data-stu-id="8d16d-226">Description</span></span>|<span data-ttu-id="8d16d-227">Notes</span><span class="sxs-lookup"><span data-stu-id="8d16d-227">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="8d16d-228"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="8d16d-228"><d:Name></d:Name></span></span>|<span data-ttu-id="8d16d-229">イベントの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-229">Provide a unique name for the event,</span></span>|<span data-ttu-id="8d16d-230">末尾にスペースおよび以下の文字を含めることはできません: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="8d16d-230">Cannot contain trailing spaces, and the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="8d16d-231">, : ;</span><span class="sxs-lookup"><span data-stu-id="8d16d-231">, : ;</span></span>|
|<span data-ttu-id="8d16d-232"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="8d16d-232"><d:EventType></d:EventType></span></span>|<span data-ttu-id="8d16d-233">イベントの種類の名前 (または GUID) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-233">Enter event type name (or Guid),</span></span>|<span data-ttu-id="8d16d-p122">例: 「従業員の退職」というイベントの種類を保持ラベルに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="8d16d-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="8d16d-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="8d16d-237">「ComplianceAssetId:」と従業員 ID を入力します</span><span class="sxs-lookup"><span data-stu-id="8d16d-237">Enter “ComplianceAssetId:” + employee Id</span></span>|<span data-ttu-id="8d16d-238">例: 「ComplianceAssetId: 12345」</span><span class="sxs-lookup"><span data-stu-id="8d16d-238">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="8d16d-239"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="8d16d-239"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="8d16d-240">イベントの日時</span><span class="sxs-lookup"><span data-stu-id="8d16d-240">Event Date and Time</span></span>|<span data-ttu-id="8d16d-241">形式: yyyy-MM-ddTHH:mm:ssZ、例: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="8d16d-241">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

##### <a name="response-codes"></a><span data-ttu-id="8d16d-242">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-242">Response codes</span></span>

| <span data-ttu-id="8d16d-243">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-243">Response Code</span></span> | <span data-ttu-id="8d16d-244">説明</span><span class="sxs-lookup"><span data-stu-id="8d16d-244">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="8d16d-245">302</span><span class="sxs-lookup"><span data-stu-id="8d16d-245">302</span></span>               | <span data-ttu-id="8d16d-246">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d16d-246">Redirect</span></span>              |
| <span data-ttu-id="8d16d-247">201</span><span class="sxs-lookup"><span data-stu-id="8d16d-247">201</span></span>               | <span data-ttu-id="8d16d-248">作成済み</span><span class="sxs-lookup"><span data-stu-id="8d16d-248">Created</span></span>               |
| <span data-ttu-id="8d16d-249">403</span><span class="sxs-lookup"><span data-stu-id="8d16d-249">403</span></span>               | <span data-ttu-id="8d16d-250">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-250">Authorization Failed</span></span>  |
| <span data-ttu-id="8d16d-251">401</span><span class="sxs-lookup"><span data-stu-id="8d16d-251">401</span></span>               | <span data-ttu-id="8d16d-252">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-252">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="8d16d-253">時間範囲に基づいてイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="8d16d-253">Get Events based on time range</span></span>

- <span data-ttu-id="8d16d-254">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="8d16d-254">**Method**: GET</span></span>

- <span data-ttu-id="8d16d-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="8d16d-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="8d16d-256">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d16d-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d16d-257">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d16d-257">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d16d-258">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d16d-258">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d16d-259">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d16d-259">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="8d16d-260">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-260">Response codes</span></span>

| <span data-ttu-id="8d16d-261">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-261">Response Code</span></span> | <span data-ttu-id="8d16d-262">説明</span><span class="sxs-lookup"><span data-stu-id="8d16d-262">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="8d16d-263">200</span><span class="sxs-lookup"><span data-stu-id="8d16d-263">200</span></span>               | <span data-ttu-id="8d16d-264">問題ありません。イベントの一覧は atom+ xml 形式です</span><span class="sxs-lookup"><span data-stu-id="8d16d-264">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="8d16d-265">404</span><span class="sxs-lookup"><span data-stu-id="8d16d-265">404</span></span>               | <span data-ttu-id="8d16d-266">見つかりません</span><span class="sxs-lookup"><span data-stu-id="8d16d-266">Not found</span></span>                         |
| <span data-ttu-id="8d16d-267">302</span><span class="sxs-lookup"><span data-stu-id="8d16d-267">302</span></span>               | <span data-ttu-id="8d16d-268">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d16d-268">Redirect</span></span>                          |
| <span data-ttu-id="8d16d-269">401</span><span class="sxs-lookup"><span data-stu-id="8d16d-269">401</span></span>               | <span data-ttu-id="8d16d-270">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-270">Authorization Failed</span></span>              |
| <span data-ttu-id="8d16d-271">403</span><span class="sxs-lookup"><span data-stu-id="8d16d-271">403</span></span>               | <span data-ttu-id="8d16d-272">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-272">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="8d16d-273">ID でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="8d16d-273">Get an event by ID</span></span>

- <span data-ttu-id="8d16d-274">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="8d16d-274">**Method**: GET</span></span>

- <span data-ttu-id="8d16d-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="8d16d-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="8d16d-276">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d16d-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d16d-277">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d16d-277">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d16d-278">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d16d-278">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d16d-279">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d16d-279">**Password**: "Compliancepassword"</span></span>



##### <a name="response-codes"></a><span data-ttu-id="8d16d-280">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-280">Response codes</span></span>

| <span data-ttu-id="8d16d-281">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-281">Response Code</span></span> | <span data-ttu-id="8d16d-282">説明</span><span class="sxs-lookup"><span data-stu-id="8d16d-282">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="8d16d-283">200</span><span class="sxs-lookup"><span data-stu-id="8d16d-283">200</span></span>               | <span data-ttu-id="8d16d-284">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="8d16d-284">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="8d16d-285">404</span><span class="sxs-lookup"><span data-stu-id="8d16d-285">404</span></span>               | <span data-ttu-id="8d16d-286">見つかりません</span><span class="sxs-lookup"><span data-stu-id="8d16d-286">Not found</span></span>                                            |
| <span data-ttu-id="8d16d-287">302</span><span class="sxs-lookup"><span data-stu-id="8d16d-287">302</span></span>               | <span data-ttu-id="8d16d-288">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d16d-288">Redirect</span></span>                                             |
| <span data-ttu-id="8d16d-289">401</span><span class="sxs-lookup"><span data-stu-id="8d16d-289">401</span></span>               | <span data-ttu-id="8d16d-290">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-290">Authorization Failed</span></span>                                 |
| <span data-ttu-id="8d16d-291">403</span><span class="sxs-lookup"><span data-stu-id="8d16d-291">403</span></span>               | <span data-ttu-id="8d16d-292">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-292">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="8d16d-293">名前でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="8d16d-293">Get an event by name</span></span>

- <span data-ttu-id="8d16d-294">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="8d16d-294">**Method**: GET</span></span>

- <span data-ttu-id="8d16d-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="8d16d-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="8d16d-296">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d16d-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d16d-297">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d16d-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d16d-298">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d16d-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d16d-299">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d16d-299">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="8d16d-300">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-300">Response codes</span></span>

| <span data-ttu-id="8d16d-301">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d16d-301">Response Code</span></span> | <span data-ttu-id="8d16d-302">説明</span><span class="sxs-lookup"><span data-stu-id="8d16d-302">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="8d16d-303">200</span><span class="sxs-lookup"><span data-stu-id="8d16d-303">200</span></span>               | <span data-ttu-id="8d16d-304">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="8d16d-304">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="8d16d-305">404</span><span class="sxs-lookup"><span data-stu-id="8d16d-305">404</span></span>               | <span data-ttu-id="8d16d-306">見つかりません</span><span class="sxs-lookup"><span data-stu-id="8d16d-306">Not found</span></span>                                            |
| <span data-ttu-id="8d16d-307">302</span><span class="sxs-lookup"><span data-stu-id="8d16d-307">302</span></span>               | <span data-ttu-id="8d16d-308">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d16d-308">Redirect</span></span>                                             |
| <span data-ttu-id="8d16d-309">401</span><span class="sxs-lookup"><span data-stu-id="8d16d-309">401</span></span>               | <span data-ttu-id="8d16d-310">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-310">Authorization Failed</span></span>                                 |
| <span data-ttu-id="8d16d-311">403</span><span class="sxs-lookup"><span data-stu-id="8d16d-311">403</span></span>               | <span data-ttu-id="8d16d-312">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d16d-312">Authentication Failed</span></span>                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a><span data-ttu-id="8d16d-313">PowerShell (バージョン6 またはそれ以降) または任意の HTTP クライアントを使用</span><span class="sxs-lookup"><span data-stu-id="8d16d-313">Using PowerShell (version 6 or later) or any HTTP client</span></span>

<span data-ttu-id="8d16d-314">手順 1: PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-314">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="8d16d-315">手順 2: 次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-315">Step 2: Run the following script.</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="8d16d-316">両方のオプションの結果を確認する</span><span class="sxs-lookup"><span data-stu-id="8d16d-316">Verify the outcome in both options</span></span>

<span data-ttu-id="8d16d-317">手順 1: セキュリティ/コンプライアンス センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-317">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="8d16d-318">手順 2: [**情報ガバナンス**] の [**イベント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-318">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="8d16d-319">手順 3: イベントが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-319">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="8d16d-320">同様に、イベント ベースの保持を自動化する上記のオプションを以下のシナリオにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-320">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="8d16d-321">シナリオ 2: 契約の満了</span><span class="sxs-lookup"><span data-stu-id="8d16d-321">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="8d16d-322">組織には、顧客、ベンダー、パートナーとの各契約で複数のレコードを保持できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-322">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="8d16d-323">こうしたドキュメントは、SharePoint などのドキュメント ライブラリに格納できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-323">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="8d16d-324">契約に関連付けられている文書の保持期間の開始時期は、契約の終了時期に基づいて決められます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-324">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="8d16d-325">たとえば、契約に関連するすべてのレコードは、契約満了後 5 年間は保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-325">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="8d16d-326">5 年間の保持期間をトリガーするイベントは、契約の満了です。</span><span class="sxs-lookup"><span data-stu-id="8d16d-326">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="8d16d-327">顧客関係管理 (CRM) システムを Microsoft 365 と連携させ、契約文書の保持をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-327">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents.</span></span>

<span data-ttu-id="8d16d-328">**このシナリオに関する自動化されたイベント ベースの保持を構成する:**</span><span class="sxs-lookup"><span data-stu-id="8d16d-328">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![契約の有効期限シナリオの役割とタスクの図](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="8d16d-330">管理者は、契約の種類ごとにさまざまなフォルダーを含む SharePoint ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-330">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="8d16d-331">管理者は、ライセンス契約書、開発契約書などの契約ファイルを各契約フォルダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-331">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="8d16d-332">管理者は、各契約フォルダーに資産 ID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-332">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="8d16d-333">SCC 管理者は、セキュリティ/コンプライアンス センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="8d16d-333">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="8d16d-334">SCC 管理者は、「契約締結」イベントや「契約満了」イベントなど、契約関連のイベントの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-334">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="8d16d-335">SCC 管理者は、「契約満了」ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-335">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="8d16d-336">この「契約満了」ラベルを発行し、SharePoint 内の契約ファイルに手動または自動で適用します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-336">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="8d16d-337">契約管理システムを Microsoft Flow または同様のアプリケーションと連携させることにより、契約ファイルの管理を定期的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-337">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="8d16d-338">契約の期限が切れると、Microsoft Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の契約ファイルの保持期間が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-338">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="8d16d-339">シナリオ 3: 製品製造の終了</span><span class="sxs-lookup"><span data-stu-id="8d16d-339">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="8d16d-p124">さまざまな製品群を生み出す製造企業は、多数の製造仕様と価格に関する文書を作成します。製品が製造されなくなると、その製品にリンクされているすべての仕様と文書は、製品のライフサイクル後、特定に期間にわたり保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d16d-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="8d16d-342">エンタープライズ リソース プランニング (ERP) システムを Microsoft 365 および Microsoft Flow と連携させ、保持をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-342">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="8d16d-343">**このシナリオに関する自動化されたイベント ベースの保持を構成する:**</span><span class="sxs-lookup"><span data-stu-id="8d16d-343">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![製品のライフサイクル シナリオの役割とタスクの図](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="8d16d-345">管理者は、「製品 1」、「製品 2」 などの製品フォルダーをドキュメント セットに作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-345">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="8d16d-346">管理者は、「製造仕様」、「製品価格」、「製品ライセンス」などの製品ファイルを各製品フォルダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-346">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="8d16d-347">管理者は、各製品フォルダーに資産 ID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-347">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="8d16d-348">SCC 管理者は、セキュリティ/コンプライアンス センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="8d16d-348">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="8d16d-349">SCC 管理者は、「製品製造開始」イベントや「製品製造終了」イベントなど、従業員関連のイベントの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-349">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="8d16d-350">SCC 管理者は、「製品製造終了」ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-350">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="8d16d-351">この「製品製造終了」ラベルを発行し、SharePoint 内の製品ファイルに手動または自動で適用します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-351">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="8d16d-352">ERP システムを Microsoft Flow または同様のアプリケーションと連携させることにより、製品ファイルの管理を定期的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-352">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="8d16d-353">製品製造が終了すると、Microsoft Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の製品ファイルの保持期間が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8d16d-353">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="8d16d-354">付録</span><span class="sxs-lookup"><span data-stu-id="8d16d-354">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="8d16d-355">リダイレクト 302 応答結果を使用して REST API を呼び出す</span><span class="sxs-lookup"><span data-stu-id="8d16d-355">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="8d16d-356">REST API の URL を使用して、次のように保持後のイベントを呼び出す: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="8d16d-356">Invoke a POST retention event call by using the REST API URL: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
    
    <span data-ttu-id="8d16d-357">全体管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d16d-357">Global administrator permissions are required.</span></span>

2. <span data-ttu-id="8d16d-358">応答コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-358">Check the response code.</span></span> <span data-ttu-id="8d16d-359">302 の場合、応答ヘッダーの場所プロパティから、リダイレクトされた URL を取得します</span><span class="sxs-lookup"><span data-stu-id="8d16d-359">If it's 302, then get the redirected URL from Location property of the response header.</span></span>

3. <span data-ttu-id="8d16d-360">リダイレクトされた URL を使用して、もう一度 POST 保持イベント呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-360">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="8d16d-361">開発者情報</span><span class="sxs-lookup"><span data-stu-id="8d16d-361">Credits</span></span>

<span data-ttu-id="8d16d-362">このトピックの校閲者をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="8d16d-362">This topic was reviewed by:</span></span>

<span data-ttu-id="8d16d-363">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="8d16d-363">Antonio Maio</span></span><br/><span data-ttu-id="8d16d-364">Microsoft Office アプリとサービスの MVP</span><span class="sxs-lookup"><span data-stu-id="8d16d-364">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="8d16d-365">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="8d16d-365">Antonio.Maio@Protiviti.com</span></span>
