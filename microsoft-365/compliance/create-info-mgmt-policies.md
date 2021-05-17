---
title: 情報管理ポリシーを作成して適用する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: 情報管理ポリシーを設定して、情報の保持期間を制御し、情報を使用しているユーザーを追跡する方法について説明します。
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817996"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="39626-103">情報管理ポリシーを作成して適用する</span><span class="sxs-lookup"><span data-stu-id="39626-103">Create and apply information management policies</span></span>

<span data-ttu-id="39626-104">情報管理ポリシーを使用すると、組織はコンテンツの保持期間を制御したり、コンテンツに関するユーザーの操作を監査したり、ドキュメントにバーコードやラベルを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="39626-104">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="39626-105">ポリシーは、法的および政府の規制または内部ビジネス プロセスへの準拠を強制するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39626-105">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="39626-106">管理者は、ドキュメントの追跡方法とドキュメントの保持期間を制御するポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="39626-106">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="39626-107">情報管理ポリシーは、サイト階層内の 3 つの異なる場所 (最も広い場所から最も狭い場所まで) で作成できます。</span><span class="sxs-lookup"><span data-stu-id="39626-107">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="39626-108">サイト コレクション内の複数のコンテンツ タイプで使用するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39626-108">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="39626-109">サイト コンテンツ タイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39626-109">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="39626-110">リストまたはライブラリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39626-110">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="39626-111">詳細については、「情報管理ポリシー [の概要」を参照してください](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="39626-111">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="39626-112">サイト コレクション内の複数のコンテンツ タイプのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="39626-112">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="39626-113"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-113"><a name="__toc261001590"> </a></span></span>

<span data-ttu-id="39626-114">サイト コレクション内の特定の種類のすべてのドキュメントに情報ポリシーを適用するには、サイト コレクション レベルでポリシーを作成し、後でコンテンツ タイプにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="39626-114">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="39626-115">これらはサイト コレクション ポリシーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="39626-115">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="39626-116">サイト コレクションのホーム ページで \> **、タイトル バー** ![ 設定SharePoint 2016 設定ボタンをクリックします。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="39626-116">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="39626-117">\> **[サイトの設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="39626-117">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="39626-118">グループ接続されたSharePointで、[サイトコンテンツ] をクリック設定[サイト コンテンツ]をクリックし、[サイト] をクリック **設定。**</span><span class="sxs-lookup"><span data-stu-id="39626-118">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="39626-119">[サイトの管理設定] ページの [**サイト コレクション管理** \> コンテンツ タイプ ポリシー テンプレート]**の下にあります**。</span><span class="sxs-lookup"><span data-stu-id="39626-119">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="39626-121">[ポリシー] ページの [作成 \> **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39626-121">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="39626-122">ポリシーの名前と説明を入力し、ポリシーの内容をユーザーに説明する簡単なポリシー ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="39626-122">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="39626-123">ポリシーに関連付ける機能を設定する方法については、サイト コンテンツ タイプのポリシーの作成に関する次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39626-123">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="39626-124">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-124">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="39626-125">サイト コンテンツ タイプのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="39626-125">Create a policy for a site content type</span></span>
<span data-ttu-id="39626-126"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-126"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="39626-127">コンテンツ タイプに情報管理ポリシーを追加すると、ポリシー機能を複数のリストまたはライブラリに簡単に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="39626-127">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="39626-128">既存の情報管理ポリシーをコンテンツ タイプに追加するか、個々のコンテンツ タイプに固有の一意のポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="39626-128">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="39626-129">リストに固有のコンテンツ タイプに情報管理ポリシーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="39626-129">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="39626-130">これは、コンテンツ タイプを使用しているリスト内のアイテムにのみポリシーを適用する効果があります。</span><span class="sxs-lookup"><span data-stu-id="39626-130">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="39626-131">サイト コレクションのホーム ページで \> **、タイトル バー** ![ 設定SharePoint 2016 設定ボタンをクリックします。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="39626-131">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="39626-132">\> **[サイトの設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="39626-132">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="39626-133">グループ接続されたSharePointで、[サイトコンテンツ] をクリック設定[サイト コンテンツ]をクリックし、[サイト] をクリック **設定。**</span><span class="sxs-lookup"><span data-stu-id="39626-133">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="39626-134">[サイトの構成設定] ページの **[Web デザイナー ギャラリー]** \> **の [サイト コンテンツ タイプ] の下にあります**。</span><span class="sxs-lookup"><span data-stu-id="39626-134">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![[サイトの設定] ページの [サイト コンテンツ タイプ] リンク](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="39626-136">[サイト コンテンツ タイプ] ページ設定、ポリシーを追加するコンテンツ タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-136">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="39626-137">[サイト コンテンツ タイプ] ページの [情報 **設定** \> **ポリシー設定] の下にあります**。</span><span class="sxs-lookup"><span data-stu-id="39626-137">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="39626-138">[ポリシーの編集] ページで、ポリシーの名前と説明を入力し、ポリシーの内容をユーザーに説明する簡単な説明を記述します。</span><span class="sxs-lookup"><span data-stu-id="39626-138">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="39626-139">次のセクションで、情報管理ポリシーに追加する個々のポリシー機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-139">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![コンテンツ ポリシーの種類](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="39626-141">このポリシーの対象となるドキュメントとアイテムの保持期間を指定するには、[保持を有効にする] を選択し、アイテムの有効期限が切れたときに保持期間と実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="39626-141">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="39626-142">保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="39626-142">To specify a retention period</span></span>
    
||||||<span data-ttu-id="39626-143">**1.**</span><span class="sxs-lookup"><span data-stu-id="39626-143">**1.**</span></span>|<span data-ttu-id="39626-144">\*\*Choose \*\*Add a retention stage for records...\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="39626-144">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="39626-145">2。</span><span class="sxs-lookup"><span data-stu-id="39626-145">2.</span></span>  <br/> | <span data-ttu-id="39626-146">保持期間オプションを選択して、ドキュメントまたはアイテムの有効期限を設定する時期を指定します。</span><span class="sxs-lookup"><span data-stu-id="39626-146">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="39626-147">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39626-147">Do one of the following:</span></span>  <br/>  <span data-ttu-id="39626-148">date プロパティに基づいて有効期限を設定するには **、Event** This stage の下で、アイテムの date プロパティに基づいて、アイテムの有効期限を切るドキュメントまたはアイテムのアクション (たとえば、作成または変更済み) と、このアクションの後の時間 (日数、月数、年 \> 数など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-148">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="39626-149">カスタム保持式を使用して有効期限を決定するには、このサーバーにインストールされているユーザー設定の保持式で設定 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39626-149">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="39626-150">> [!NOTE]>このオプションは、ユーザー設定の数式が管理者によって設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-150">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="39626-151">3。</span><span class="sxs-lookup"><span data-stu-id="39626-151">3.</span></span>  <br/> |<span data-ttu-id="39626-152">[ **ワークフローの開始** ] オプションは、既にワークフローが関連付けられているリスト、ライブラリ、またはコンテンツ タイプのポリシーを定義している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-152">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="39626-153">次に、選択するワークフローの選択肢が与えられる。</span><span class="sxs-lookup"><span data-stu-id="39626-153">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="39626-154">4.</span><span class="sxs-lookup"><span data-stu-id="39626-154">4.</span></span>  <br/> |<span data-ttu-id="39626-155">[繰り **返し]** セクションで、[ **このステージのアクションを繰り返す]を選択します。** をクリックし、アクションを再発生する頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-155">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="39626-156">> [!NOTE]>このオプションは、選択したアクションを繰り返し実行できる場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-156">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="39626-157">たとえば、アクションの繰り返しを [完全に削除 **] に設定することはできません**。</span><span class="sxs-lookup"><span data-stu-id="39626-157">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="39626-158">5.</span><span class="sxs-lookup"><span data-stu-id="39626-158">5.</span></span>  <br/> |<span data-ttu-id="39626-159">**[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39626-159">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="39626-160">このポリシーの対象となるドキュメントとアイテムの監査を有効にするには、[監査を有効にする] を選択し、監査するイベントを指定します。</span><span class="sxs-lookup"><span data-stu-id="39626-160">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="39626-161">監査を有効にするには</span><span class="sxs-lookup"><span data-stu-id="39626-161">To enable auditing</span></span>
    
||||||<span data-ttu-id="39626-162">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="39626-162">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="39626-163">[ポリシーの編集] ページ **で、[** 監査を有効にする] \*\*の下で、監査証跡を保持するイベントの横にあるチェック ボックスをオン **\>** にします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="39626-163">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="39626-164">**2.**</span><span class="sxs-lookup"><span data-stu-id="39626-164">**2.**</span></span> <br/> |<span data-ttu-id="39626-165">**これらのバーコードをドキュメントに挿入** するようにユーザーに求めるには、[保存または印刷する前にバーコードを挿入するようにユーザーに確認 **する] を選択します\*\*\*\*。**</span><span class="sxs-lookup"><span data-stu-id="39626-165">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="39626-166">**3.**</span><span class="sxs-lookup"><span data-stu-id="39626-166">**3.**</span></span> <br/> |<span data-ttu-id="39626-167">**[OK]**  \*\* を選択して、監査機能をポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="39626-167">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="39626-168">監査ポリシー機能を使用すると、組織はドキュメントの監査証跡を作成および分析し、タスク リスト、問題リスト、ディスカッション グループ、予定表などのアイテムを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="39626-168">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="39626-169">このポリシー機能は、コンテンツの表示、編集、削除などのイベントを記録する監査ログを提供します。</span><span class="sxs-lookup"><span data-stu-id="39626-169">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="39626-170">監査が情報管理ポリシーの一部として有効になっている場合、管理者は、Microsoft Excel に基づいて現在の使用状況を要約するポリシー使用状況レポートで監査データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="39626-170">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="39626-171">管理者は、これらのレポートを使用して、組織内でどのように情報が使用されているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="39626-171">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="39626-172">また、これらのレポートは、組織が規制コンプライアンスを確認して文書化したり、潜在的な懸念事項を調査したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39626-172">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="39626-173">監査ログには、イベント名、イベントの日時、アクションを実行したユーザーのシステム名の情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="39626-173">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="39626-174">ポリシーの一部としてバーコードが有効になっている場合、バーコードはドキュメント プロパティに追加され、バーコードが適用されるドキュメントのヘッダー領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="39626-174">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="39626-175">ラベルと同様に、バーコードを手動でドキュメントから削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="39626-175">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="39626-176">2010 Office リリース プログラムの [挿入] タブを使用して、アイテムの印刷または保存時にバーコードを含めるかどうかをユーザーに求めるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="39626-176">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="39626-177">バーコードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="39626-177">To enable barcodes</span></span>
    
||||||<span data-ttu-id="39626-178">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="39626-178">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="39626-179">**[ポリシーの編集] ページの [バーコード **を有効にする** \> **] の下にある [バーコードを有効にする] をクリックします**。**</span><span class="sxs-lookup"><span data-stu-id="39626-179">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="39626-180">**2.**</span><span class="sxs-lookup"><span data-stu-id="39626-180">**2.**</span></span> <br/> |<span data-ttu-id="39626-181">これらのバーコードをドキュメントに挿入するようにユーザーに求めるには、[保存または印刷する前にバーコードを挿入するようにユーザーに確認 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39626-181">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="39626-182">**3.**</span><span class="sxs-lookup"><span data-stu-id="39626-182">**3.**</span></span> <br/> |<span data-ttu-id="39626-183">**[OK] を** 選択して、ポリシーにバーコード機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="39626-183">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="39626-184">バーコード ポリシーは、コード 39 標準バーコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="39626-184">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="39626-185">各バーコード イメージには、バーコード値を表すバーコード 記号の下のテキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39626-185">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="39626-186">これにより、ハードウェアをスキャンできない場合でも、バーコード データを使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-186">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="39626-187">ユーザーは手動でバーコード番号を検索ボックスに入力して、サイト上のアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="39626-187">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="39626-188">このポリシーの対象となるドキュメントにラベルを設定する必要がある場合は、[ラベルを有効にする] を選択し、ラベルに必要な設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="39626-188">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="39626-189">ラベルを有効にするには</span><span class="sxs-lookup"><span data-stu-id="39626-189">To enable labels</span></span>
    
||||||<span data-ttu-id="39626-190">**1.**</span><span class="sxs-lookup"><span data-stu-id="39626-190">**1.**</span></span>|<span data-ttu-id="39626-191">\*\*ユーザーにドキュメントへのラベルの追加を要求するには、[保存または印刷する前にラベルを挿入するようにユーザーに確認 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39626-191">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="39626-192">> [!NOTE]>ラベルをオプションにしたい場合は、このチェック ボックスをオンにしない。</span><span class="sxs-lookup"><span data-stu-id="39626-192">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="39626-193">2。</span><span class="sxs-lookup"><span data-stu-id="39626-193">2.</span></span>  <br/> |<span data-ttu-id="39626-194">ラベルを挿入した後でラベルを変更できない場合は、[ラベルを追加した後にラベルに変更を加えない] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39626-194">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="39626-195">この設定では、Word、Excel、または文書などのクライアント アプリケーション内のアイテムにラベルが挿入された後、ラベル テキストが更新PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="39626-195">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="39626-196">このドキュメントまたはアイテムのプロパティを更新するときにラベルを更新する場合は、このチェック ボックスをオンにしない必要があります。</span><span class="sxs-lookup"><span data-stu-id="39626-196">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="39626-197">3。</span><span class="sxs-lookup"><span data-stu-id="39626-197">3.</span></span>  <br/> |<span data-ttu-id="39626-198">[ラベルの形式] ボックスに、ラベルを表示するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-198">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="39626-199">ラベルには最大 10 列の参照を含めることができます。各列の長は最大 255 文字です。</span><span class="sxs-lookup"><span data-stu-id="39626-199">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="39626-200">ラベルの形式を作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39626-200">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="39626-201">ラベルに含める列の名前を、表示する順序で入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-201">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="39626-202">[ポリシーの編集] ページの例に示すように、列名を中かっこ ( ) {} で囲みます。</span><span class="sxs-lookup"><span data-stu-id="39626-202">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="39626-203">[ポリシーの編集] ページの例に示すように、かっこの外側の列を識別する単語を入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-203">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="39626-204">4.</span><span class="sxs-lookup"><span data-stu-id="39626-204">4.</span></span>  <br/> |<span data-ttu-id="39626-205">折れ線を追加するには **、\nを** 表示する場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-205">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="39626-206">5.</span><span class="sxs-lookup"><span data-stu-id="39626-206">5.</span></span>  <br/> |<span data-ttu-id="39626-207">必要なフォント サイズとスタイルを選択し、ラベルをドキュメント内で左、中央、または右に配置するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="39626-207">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="39626-208">ユーザーのコンピューターで使用できるフォントとスタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-208">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="39626-209">フォントのサイズは、ラベルに表示できるテキストの量に影響します。</span><span class="sxs-lookup"><span data-stu-id="39626-209">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="39626-210">6.</span><span class="sxs-lookup"><span data-stu-id="39626-210">6.</span></span>  <br/> |<span data-ttu-id="39626-211">ラベルの高さと幅を入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-211">Enter the height and width of the label.</span></span> <span data-ttu-id="39626-212">ラベルの高さは .25 インチから 20 インチの範囲で、ラベルの幅は .25 インチから 20 インチの範囲です。</span><span class="sxs-lookup"><span data-stu-id="39626-212">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="39626-213">ラベル テキストは常にラベル イメージ内の垂直方向の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="39626-213">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="39626-214">7.</span><span class="sxs-lookup"><span data-stu-id="39626-214">7.</span></span>  <br/> |<span data-ttu-id="39626-215">[ **更新] を** 選択してラベルコンテンツをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="39626-215">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="39626-216">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-216">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="39626-217">リスト、ライブラリ、またはフォルダーに対するポリシーを作成する (場所に応じた保持ポリシー)</span><span class="sxs-lookup"><span data-stu-id="39626-217">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="39626-218"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-218"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="39626-219">特定のリスト、ライブラリ、またはフォルダーにのみ適用されるアイテム保持ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="39626-219">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="39626-220">ただし、この方法でアイテム保持ポリシーを作成した場合、他のリスト、ライブラリ、フォルダー、またはサイトでこのポリシーを再利用することはできません。サイト コレクション ポリシーを場所ベースのポリシーに適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="39626-220">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="39626-221">1 つの場所のすべての種類のコンテンツに 1 つの保持ポリシーを適用する場合は、場所ベースの保持を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39626-221">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="39626-222">他のほとんどの場合、すべてのコンテンツ タイプに対してアイテム保持ポリシーが指定されているのを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39626-222">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="39626-223">各サブフォルダーは、継承を解除し、子レベルで新しい保持ポリシーを定義しない限り、親の保持ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="39626-223">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="39626-224">リストまたはライブラリへの保持以外の情報管理ポリシーを定義する場合は、そのリストまたはライブラリに関連付けられた個々のリスト コンテンツ タイプごとに情報管理ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39626-224">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="39626-225">リストまたはライブラリのコンテンツ タイプから場所ベースのポリシーに切り替える場合は、アイテム保持ポリシーだけが場所ベースのポリシーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="39626-225">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="39626-226">その他のすべての管理ポリシー (監査、バーコード、バーコード) は、関連付けられたコンテンツ タイプから継承されます。</span><span class="sxs-lookup"><span data-stu-id="39626-226">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="39626-227">場所に基づくポリシーは、ライブラリとフォルダー ベースの保持機能を無効にすることで、サイト コレクションで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="39626-227">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="39626-228">これにより、サイト コレクション管理者は、コンテンツ タイプ ポリシーがリスト管理者の場所ベースのポリシーによって上書きされないか確認できます。</span><span class="sxs-lookup"><span data-stu-id="39626-228">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="39626-229">リストまたはライブラリの情報管理ポリシー設定を変更するには、少なくとも [リストの管理] アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="39626-229">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="39626-230">情報管理ポリシーを指定するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="39626-230">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="39626-231">リボンで、[ライブラリ]**タブまたは**[**リスト]** タブの [ライブラリ] \> **または [リスト 設定]** を **設定。**</span><span class="sxs-lookup"><span data-stu-id="39626-231">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="39626-232">[オンラインSharePoint] で、[設定]**をクリックし、[リスト** の設定] または [ライブラリの **設定**]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39626-232">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="39626-233">[**アクセス許可と管理情報** \> **の管理ポリシー設定] の下にある 。**</span><span class="sxs-lookup"><span data-stu-id="39626-233">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="39626-235">[情報管理ポリシー] 設定ページで、リストまたはライブラリの保持元が [ライブラリとフォルダー] に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="39626-235">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="39626-236">コンテンツ **タイプがソース** として表示される場合は、[ソースの変更] をクリックし、[ライブラリとフォルダー]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39626-236">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="39626-237">コンテンツ タイプ保持ポリシーが無視されるという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39626-237">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="39626-238">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-238">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="39626-239">[ポリシーの編集] ページの [ **ライブラリ** ベースの保持スケジュール] で、作成するポリシーの簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-239">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="39626-240">[保持 **ステージの追加]を選択します。**</span><span class="sxs-lookup"><span data-stu-id="39626-240">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="39626-241">[レコード] で、[レコードに異なる保持ステージを定義する] オプションを選択して、レコードの異なる保持ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="39626-241">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="39626-242">[ステージのプロパティ] ダイアログで、保持期間オプションを選択して、ドキュメントまたはアイテムの有効期限を設定する時期を指定します。</span><span class="sxs-lookup"><span data-stu-id="39626-242">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="39626-243">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39626-243">Do one of the following:</span></span>
    
  - <span data-ttu-id="39626-244">date プロパティに基づいて有効期限を設定するには **、Event** This stage の下で、アイテムの date プロパティに基づいて、アイテムの有効期限を切るドキュメントまたはアイテムのアクション (たとえば、作成または変更済み) と、このアクションの後の時間 (日数、月数、年 \> 数など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-244">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="39626-245">カスタム保持式を使用して有効期限を決定するには、このサーバーにインストールされているユーザー設定の保持式で設定 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39626-245">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="39626-246">このオプションは、ユーザー設定の数式が管理者によって設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-246">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="39626-247">[ **アクション]** で、ドキュメントまたはアイテムの有効期限が切れたときに実行する処理を指定します。</span><span class="sxs-lookup"><span data-stu-id="39626-247">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="39626-248">ドキュメントまたはアイテムに対して特定のアクション (削除など) を有効にするには、一覧からアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-248">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="39626-249">[ **ワークフローの開始** ] オプションは、既にワークフローが関連付けられているリスト、ライブラリ、またはコンテンツ タイプのポリシーを定義している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-249">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="39626-250">次に、選択するワークフローの選択肢が与えられる。</span><span class="sxs-lookup"><span data-stu-id="39626-250">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="39626-251">[ **繰り返し**] で、[ **このステージのアクションを繰り返す]を選択します。** をクリックし、アクションを再発生する頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="39626-251">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="39626-252">このオプションは、選択したアクションを繰り返し実行できる場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-252">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="39626-253">たとえば、アクションの繰り返しを [完全に削除 **] に設定することはできません**。</span><span class="sxs-lookup"><span data-stu-id="39626-253">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="39626-254">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-254">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="39626-255">コンテンツ タイプにサイト コレクション ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="39626-255">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="39626-256"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-256"><a name="__apply_a_site"> </a></span></span>

<span data-ttu-id="39626-257">サイトの情報管理ポリシーがサイト コレクション ポリシーとして既に作成されている場合は、コンテンツ タイプにポリシーのいずれかを適用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-257">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="39626-258">これにより、同じ親コンテンツ タイプを共有しないサイト コレクション内の複数のコンテンツ タイプに同じポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-258">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="39626-259">サイト コレクション内の複数のコンテンツ タイプにポリシーを適用し、管理メタデータ サービスを構成している場合は、コンテンツ タイプ発行を使用して、複数のサイト コレクションに情報管理ポリシーを発行できます。</span><span class="sxs-lookup"><span data-stu-id="39626-259">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="39626-260">詳細については、「 [サイト コレクション間でポリシーを適用する」セクション](#apply-a-policy-across-site-collections) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39626-260">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="39626-261">ポリシーを適用するコンテンツ タイプを含むリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="39626-261">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="39626-262">リボンで、[ライブラリ]**タブまたは**[**リスト]** タブの [ライブラリ] \> **または [リスト 設定]** を **設定。**</span><span class="sxs-lookup"><span data-stu-id="39626-262">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="39626-263">[オンラインSharePoint] で、[設定]**をクリックし、[リスト** の設定] または [ライブラリの **設定**]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39626-263">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="39626-264">[**アクセス許可と管理情報** \> **の管理ポリシー設定] の下にある 。**</span><span class="sxs-lookup"><span data-stu-id="39626-264">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="39626-266">ポリシー ソースが [コンテンツ タイプ] に **設定** され、[コンテンツ タイプ ポリシー] でポリシーを適用するコンテンツ タイプを選択します。 </span><span class="sxs-lookup"><span data-stu-id="39626-266">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="39626-267">[**ポリシーの指定:** サイト コレクション ポリシーを使用する] で、一覧から適用するポリシー \> を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-267">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="39626-268">[サイト **コレクション ポリシーを使用** する] オプションを使用できない場合は、サイト コレクションに対してサイト コレクション ポリシーが定義されていません。</span><span class="sxs-lookup"><span data-stu-id="39626-268">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="39626-269">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-269">Choose **OK**.</span></span>
    
     <span data-ttu-id="39626-270">使用しているリストまたはライブラリが複数のコンテンツ タイプの管理をサポートしている場合は、[コンテンツ タイプ] で、情報管理ポリシーを指定するコンテンツ タイプを選択できます。</span><span class="sxs-lookup"><span data-stu-id="39626-270">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="39626-271">これにより、上記の手順 5 に直接進みます。</span><span class="sxs-lookup"><span data-stu-id="39626-271">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="39626-272">サイト コレクション全体にポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="39626-272">Apply a policy across site collections</span></span>
<span data-ttu-id="39626-273"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-273"><a name="__toc260646789"> </a></span></span>

<span data-ttu-id="39626-274">Managed Metadata Service アプリケーションを使用してコンテンツ タイプ発行を設定することで、サイト コレクション間でコンテンツ タイプを共有します。</span><span class="sxs-lookup"><span data-stu-id="39626-274">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="39626-275">コンテンツ タイプの発行は、コンテンツ タイプを一貫して作成および更新したり、更新プログラムを複数のサブスクライブサイト コレクションまたは Web アプリケーションに公開したりできるので、サイト全体でコンテンツとメタデータを一貫して管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39626-275">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="39626-276">サイト コレクション全体で使用する既存のポリシーからテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="39626-276">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="39626-277"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-277"><a name="__toc262125409"> </a></span></span>

<span data-ttu-id="39626-278">情報管理ポリシーを定義し、そこからテンプレートを作成して、複数のサイト コレクションで必要に応じて使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-278">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="39626-279">このメソッドは、情報ポリシーのバックアップを作成する場合や、サイト コレクション間で 1 つのポリシーを適用するためにコンテンツ タイプ発行を使用する代替方法として使用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-279">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="39626-280">ポリシーのテンプレートまたはバックアップを作成するには、ポリシーを 1 つのサイト コレクションからエクスポートし、保存された場所または別のサイト コレクションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="39626-280">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="39626-281">一連のポリシー テンプレートを作成する方法としてエクスポート/インポート機能を使用する場合は、ポリシー ファイル内に一意の識別子.xmlしてください。</span><span class="sxs-lookup"><span data-stu-id="39626-281">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="39626-282">この理由から、この一意の識別子を変更せずに、そのポリシーをサイトに複数インポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="39626-282">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="39626-283">ポリシーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="39626-283">Export a policy</span></span>
<span data-ttu-id="39626-284"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-284"><a name="__toc260646790"> </a></span></span>

1. <span data-ttu-id="39626-285">サイト コレクションのホーム ページで、[サイト **コレクション]** の設定を設定した小さな設定を選択します。 ![ ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **サイト** 設定。</span><span class="sxs-lookup"><span data-stu-id="39626-285">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="39626-286">グループ接続されたSharePointで、[サイトコンテンツ] をクリック設定[サイト コンテンツ]をクリックし、[サイト] をクリック **設定。**</span><span class="sxs-lookup"><span data-stu-id="39626-286">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="39626-287">[サイトの管理設定] ページの [**サイト コレクション管理** \> コンテンツ タイプ ポリシー テンプレート]**の下にあります**。</span><span class="sxs-lookup"><span data-stu-id="39626-287">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="39626-289">エクスポートするポリシーを選択して、 \> 下の [エクスポート] に \> **スクロールします**。</span><span class="sxs-lookup"><span data-stu-id="39626-289">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="39626-290">ファイルを保存または開くプロンプトで、[保存]を選択し、ファイルを保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="39626-290">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="39626-291">ポリシーをインポートするサイト コレクションで使用できる場所を必ず選択してください。</span><span class="sxs-lookup"><span data-stu-id="39626-291">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="39626-292">[ダウンロードの完了] ダイアログが表示されている場合は、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39626-292">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="39626-293">ポリシーを別のサイト コレクションにインポートする</span><span class="sxs-lookup"><span data-stu-id="39626-293">Import a policy to a different site collection</span></span>
<span data-ttu-id="39626-294"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="39626-294"><a name="__toc260646791"> </a></span></span>

<span data-ttu-id="39626-295">情報管理ポリシーをインポートすると、特定のサイト コレクション内のサイトまたはリスト レベルの複数のコンテンツ タイプに適用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-295">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="39626-296">これを行う利点は 2 つあります。各コンテンツ タイプにポリシーを再定義して適用する必要はなく、ポリシーを 1 か所で変更することで、ポリシーの変更を簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="39626-296">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="39626-297">ポリシーを適用するサイト コレクションのホーム ページで、[サイト 設定] の場所を使用した **設定** 小 設定 歯車を選択します。サイト 設定。 ![ ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> </span><span class="sxs-lookup"><span data-stu-id="39626-297">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="39626-298">グループ接続されたSharePointで、[サイトコンテンツ] をクリック設定[サイト コンテンツ]をクリックし、[サイト] をクリック **設定。**</span><span class="sxs-lookup"><span data-stu-id="39626-298">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="39626-299">[サイトの管理設定] ページの [**サイト コレクション管理** \> コンテンツ タイプ ポリシー テンプレート]**の下にあります**。</span><span class="sxs-lookup"><span data-stu-id="39626-299">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="39626-300">[ポリシー] ページの \> **[** \> **参照のインポート] で** 、ポリシーの XML ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="39626-300">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="39626-301">ポリシーが保存されている XML ファイルを選択します \> 。</span><span class="sxs-lookup"><span data-stu-id="39626-301">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="39626-302">[サイト コレクション ポリシーのインポート] ページ \> **の [インポート] で** 、サイト コレクションにポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39626-302">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="39626-303">インポートしたポリシーを、サイトまたはリスト レベルの 1 つ以上のコンテンツ タイプに適用できます。</span><span class="sxs-lookup"><span data-stu-id="39626-303">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="39626-304">情報管理ポリシーを使用すると、組織はコンテンツの保持期間を制御したり、コンテンツに関するユーザーの操作を監査したり、ドキュメントにバーコードやラベルを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="39626-304">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="39626-305">ポリシーは、法的および政府の規制または内部ビジネス プロセスへの準拠を強制するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39626-305">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="39626-306">管理者は、ドキュメントの追跡方法とドキュメントの保持期間を制御するポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="39626-306">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="39626-307">情報管理ポリシーは、サイト階層内の 3 つの異なる場所 (最も広い場所から最も狭い場所まで) で作成できます。</span><span class="sxs-lookup"><span data-stu-id="39626-307">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="39626-308">サイト コレクション内の複数のコンテンツ タイプで使用するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39626-308">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="39626-309">サイト コンテンツ タイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39626-309">Create a policy for a site content type.</span></span>
- <span data-ttu-id="39626-310">リストまたはライブラリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39626-310">Create a policy for a list or library.</span></span>

<span data-ttu-id="39626-311">詳細については、「情報管理ポリシー [の概要」を参照してください](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="39626-311">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

