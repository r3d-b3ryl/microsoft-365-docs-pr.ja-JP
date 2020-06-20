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
description: 情報管理ポリシーを設定して情報を保持する時間を制御し、情報を使用しているユーザーを追跡する方法について説明します。
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817996"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="b277e-103">情報管理ポリシーを作成して適用する</span><span class="sxs-lookup"><span data-stu-id="b277e-103">Create and apply information management policies</span></span>

<span data-ttu-id="b277e-104">情報管理ポリシーを使用すると、コンテンツの保持期間を制御したり、コンテンツについてユーザーの作業を監査したり、バーコードやラベルをドキュメントに追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="b277e-104">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="b277e-105">ポリシーを使用すると、法律上および行政上の規制や内部のビジネスプロセスに準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-105">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="b277e-106">管理者は、ドキュメントの追跡方法やドキュメントを保持する期間を制御するポリシーをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="b277e-106">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="b277e-107">情報管理ポリシーは、サイト階層内の3つの異なる場所 (最も広いものから最も狭いものまで) に作成できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-107">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="b277e-108">サイトコレクション内の複数のコンテンツタイプで使用するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b277e-108">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="b277e-109">サイトコンテンツタイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b277e-109">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="b277e-110">リストまたはライブラリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b277e-110">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="b277e-111">詳細については、「[情報管理ポリシーの概要](intro-to-info-mgmt-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b277e-111">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="b277e-112">サイトコレクション内の複数のコンテンツタイプのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b277e-112">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="b277e-113"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-113"><a name="__toc261001590"> </a></span></span>

<span data-ttu-id="b277e-114">サイトコレクション内の特定の種類のすべてのドキュメントに情報ポリシーが適用されるようにするには、サイトコレクションレベルでポリシーを作成してから、そのポリシーをコンテンツタイプに適用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b277e-114">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="b277e-115">これらは、サイトコレクションポリシーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b277e-115">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="b277e-116">サイトコレクションのホームページ \> **設定** ![ SharePoint 2016 設定] ボタン (タイトルバー)。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="b277e-116">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="b277e-117">\> **[サイトの設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-117">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b277e-118">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-118">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b277e-119">[サイトの設定] ページの [**サイトコレクションの管理** \> **コンテンツタイプポリシーテンプレート**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-119">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="b277e-121">[ポリシー] ページで、[作成] をオンに \> **Create**します。</span><span class="sxs-lookup"><span data-stu-id="b277e-121">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="b277e-122">ポリシーの名前と説明を入力し、ユーザーに対してポリシーがどのようなものかを説明する簡単なポリシーステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="b277e-122">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="b277e-123">ポリシーに関連付ける機能をセットアップする方法については、「サイトコンテンツタイプのポリシーの作成」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b277e-123">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="b277e-124">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-124">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="b277e-125">サイトコンテンツタイプのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b277e-125">Create a policy for a site content type</span></span>
<span data-ttu-id="b277e-126"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-126"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="b277e-127">コンテンツタイプに情報管理ポリシーを追加すると、ポリシー機能と複数のリストまたはライブラリとの関連付けが容易になります。</span><span class="sxs-lookup"><span data-stu-id="b277e-127">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="b277e-128">既存の情報管理ポリシーをコンテンツタイプに追加するか、個別のコンテンツタイプに固有の一意のポリシーを作成するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-128">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="b277e-129">リストに固有のコンテンツタイプに情報管理ポリシーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b277e-129">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="b277e-130">これには、コンテンツタイプを使用しているリスト内のアイテムにのみポリシーを適用する効果があります。</span><span class="sxs-lookup"><span data-stu-id="b277e-130">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="b277e-131">サイトコレクションのホームページ \> **設定** ![ SharePoint 2016 設定] ボタン (タイトルバー)。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="b277e-131">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="b277e-132">\> **[サイトの設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-132">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b277e-133">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-133">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b277e-134">[サイトの設定] ページの [ **Web デザイナーギャラリー** \> **サイトコンテンツタイプ**] の下。</span><span class="sxs-lookup"><span data-stu-id="b277e-134">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![[サイトの設定] ページの [サイト コンテンツ タイプ] リンク](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="b277e-136">[サイトコンテンツタイプの設定] ページで、ポリシーを追加するコンテンツタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-136">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="b277e-137">[サイトコンテンツタイプ] ページの [**設定** \> **情報管理ポリシーの設定**] で。</span><span class="sxs-lookup"><span data-stu-id="b277e-137">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="b277e-138">[ポリシーの編集] ページで、ポリシーの名前と説明を入力し、ユーザーに対してポリシーの内容を説明する簡単な説明を記入します。</span><span class="sxs-lookup"><span data-stu-id="b277e-138">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="b277e-139">次のセクションでは、情報管理ポリシーに追加する個々のポリシー機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-139">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![コンテンツ ポリシーの種類](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="b277e-141">このポリシーの対象となるドキュメントとアイテムの保持期間を指定するには、[**保持を有効**にする] を選択し、アイテムの有効期限が切れたときに実行する保持期間とアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-141">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="b277e-142">保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="b277e-142">To specify a retention period</span></span>
    
||||||<span data-ttu-id="b277e-143">**1.**</span><span class="sxs-lookup"><span data-stu-id="b277e-143">**1.**</span></span>|<span data-ttu-id="b277e-144">\* \* Choose \* \* レコードの保持ステージを追加する... \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b277e-144">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b277e-145">2。</span><span class="sxs-lookup"><span data-stu-id="b277e-145">2.</span></span>  <br/> | <span data-ttu-id="b277e-146">ドキュメントまたはアイテムを期限切れにするタイミングを指定するには、[保持期間] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-146">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="b277e-147">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b277e-147">Do one of the following:</span></span>  <br/>  <span data-ttu-id="b277e-148">日付プロパティに基づいて有効期限を設定するには、[**イベント**は \> **このステージはアイテムの日付プロパティに基づいてい**ます] の下にある [ドキュメントまたはアイテム] アクション (たとえば、[作成日時] または [変更日時]) を選択し、このアクションの後の時間の増分 (たとえば、アイテムを期限切れにします)</span><span class="sxs-lookup"><span data-stu-id="b277e-148">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="b277e-149">カスタム保持期間の計算式を使用して有効期限を決定するには、[**このサーバーにインストールされているカスタム保持期間の数式で設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-149">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="b277e-150">> [!NOTE]> このオプションは、管理者によってカスタム式が設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-150">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="b277e-151">3。</span><span class="sxs-lookup"><span data-stu-id="b277e-151">3.</span></span>  <br/> |<span data-ttu-id="b277e-152">[**ワークフローの開始**] オプションは、既にワークフローが関連付けられているリスト、ライブラリ、またはコンテンツタイプのポリシーを定義している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-152">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="b277e-153">その後、選択するワークフローが選択されます。</span><span class="sxs-lookup"><span data-stu-id="b277e-153">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="b277e-154">4.</span><span class="sxs-lookup"><span data-stu-id="b277e-154">4.</span></span>  <br/> |<span data-ttu-id="b277e-155">[**定期的なパターン**] セクションで、[**このステージのアクションを繰り返す...** ] を選択します。を選択し、アクションを実行する頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="b277e-155">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="b277e-156">> [!NOTE]> このオプションは、選択したアクションを繰り返すことができる場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-156">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="b277e-157">たとえば、アクションが**完全に削除**されると、定期的なアイテムを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b277e-157">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="b277e-158">5.</span><span class="sxs-lookup"><span data-stu-id="b277e-158">5.</span></span>  <br/> |<span data-ttu-id="b277e-159">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-159">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="b277e-160">このポリシーの対象となるドキュメントとアイテムの監査を有効にするには、[**監査を有効**にする] を選択し、監査するイベントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-160">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="b277e-161">監査を有効にするには</span><span class="sxs-lookup"><span data-stu-id="b277e-161">To enable auditing</span></span>
    
||||||<span data-ttu-id="b277e-162">1. \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b277e-162">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="b277e-163">[ポリシーの編集] ページで、\* \* [監査を有効にする **] の下**の [**監査を**有効にする] チェックボックスをオンにして、 **\>** **Enable auditing**監査記録を保持するイベントの横にあるチェックボックスをオンにします。 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b277e-163">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b277e-164">**2.**</span><span class="sxs-lookup"><span data-stu-id="b277e-164">**2.**</span></span> <br/> |<span data-ttu-id="b277e-165">**ユーザーにドキュメントにバーコードを挿入するように求めるには、** **[** **保存または印刷する前に、ユーザーにバーコードを挿入するかどうかを確認**する] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="b277e-165">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="b277e-166">**3.**</span><span class="sxs-lookup"><span data-stu-id="b277e-166">**3.**</span></span> <br/> |<span data-ttu-id="b277e-167">[ **OK]** を**選択**して、ポリシーに監査機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="b277e-167">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="b277e-168">監査ポリシー機能を使用すると、組織でドキュメントの監査証跡を作成して分析したり、タスクリスト、案件リスト、ディスカッショングループ、予定表などのリストアイテムを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-168">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="b277e-169">このポリシー機能は、コンテンツの表示、編集、削除など、イベントを記録する監査ログを提供します。</span><span class="sxs-lookup"><span data-stu-id="b277e-169">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="b277e-170">情報管理ポリシーの一部として監査が有効になっている場合、管理者は、Microsoft Excel に基づくポリシー利用状況レポートで監査データを表示し、現在の使用状況を要約することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-170">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="b277e-171">管理者は、これらのレポートを使用して、組織内でどのように情報が使用されているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-171">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="b277e-172">これらのレポートは、組織が法令遵守を確認して文書化したり、潜在的な懸念事項を調査する際にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b277e-172">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="b277e-173">監査ログには次の情報が記録されます。イベント名、イベントの日付と時刻、およびアクションを実行したユーザーのシステム名です。</span><span class="sxs-lookup"><span data-stu-id="b277e-173">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="b277e-174">ポリシーの一部としてバーコードが有効になっている場合、バーコードはドキュメントプロパティに追加され、バーコードが適用される文書のヘッダー領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b277e-174">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="b277e-175">ラベルと同様に、バーコードをドキュメントから手動で削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="b277e-175">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="b277e-176">ユーザーがアイテムを印刷または保存するときにバーコードを含めるかどうかを確認するメッセージを表示するか、または2010の Office リリースプログラムの [**挿入**] タブを使用してバーコードを手動で挿入するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-176">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="b277e-177">バーコードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="b277e-177">To enable barcodes</span></span>
    
||||||<span data-ttu-id="b277e-178">1. \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b277e-178">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="b277e-179">**[ポリシーの編集] ページの [**バーコード**] の下で、 \> **バーコードを有効**にします。**</span><span class="sxs-lookup"><span data-stu-id="b277e-179">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b277e-180">**2.**</span><span class="sxs-lookup"><span data-stu-id="b277e-180">**2.**</span></span> <br/> |<span data-ttu-id="b277e-181">ユーザーにドキュメントにバーコードを挿入するように求めるには、[**保存または印刷する前に、ユーザーにバーコードを挿入するかどうかを確認**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-181">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="b277e-182">**3.**</span><span class="sxs-lookup"><span data-stu-id="b277e-182">**3.**</span></span> <br/> |<span data-ttu-id="b277e-183">**[OK]** を選択して、ポリシーにバーコード機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="b277e-183">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="b277e-184">バーコードポリシーは、コード39の標準バーコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="b277e-184">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="b277e-185">各バーコードイメージには、バーコード値を表すバーコードの下にテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b277e-185">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="b277e-186">これにより、スキャンハードウェアが使用できない場合でも、バーコードデータを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b277e-186">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="b277e-187">ユーザーは、サイト上のアイテムを検索するために、検索ボックスにバーコード番号を手動で入力することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-187">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="b277e-188">このポリシーの対象となるドキュメントにラベルがあることを要求するには、[**ラベルを有効**にする] を選択して、ラベルに必要な設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-188">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="b277e-189">ラベルを有効にするには</span><span class="sxs-lookup"><span data-stu-id="b277e-189">To enable labels</span></span>
    
||||||<span data-ttu-id="b277e-190">**1.**</span><span class="sxs-lookup"><span data-stu-id="b277e-190">**1.**</span></span>|<span data-ttu-id="b277e-191">\* \* ドキュメントにラベルを追加することをユーザーに要求するには、[**保存または印刷前にラベルを挿入するかどうかをユーザーに確認**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-191">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="b277e-192">> [!NOTE]> ラベルを省略可能にする場合は、このチェックボックスをオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="b277e-192">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b277e-193">2。</span><span class="sxs-lookup"><span data-stu-id="b277e-193">2.</span></span>  <br/> |<span data-ttu-id="b277e-194">挿入した後で変更できないようにラベルをロックするには、[**ラベルを追加した後にラベルを変更できないよう**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-194">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="b277e-195">この設定では、Word、Excel、PowerPoint などのクライアントアプリケーション内のアイテムにラベルが挿入されると、ラベルテキストは更新されません。</span><span class="sxs-lookup"><span data-stu-id="b277e-195">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="b277e-196">このドキュメントまたはアイテムのプロパティが更新されたときにラベルを更新する場合は、このチェックボックスをオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="b277e-196">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="b277e-197">3。</span><span class="sxs-lookup"><span data-stu-id="b277e-197">3.</span></span>  <br/> |<span data-ttu-id="b277e-198">[ラベルの書式] ボックスに、表示するラベルのテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="b277e-198">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="b277e-199">ラベルには最大10個の列参照を含めることができます。それぞれの値は最大255文字まで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-199">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="b277e-200">ラベルの書式を作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b277e-200">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="b277e-201">ラベルに含める列の名前を、表示する順序に従って入力します (この名前を付ける場合)。</span><span class="sxs-lookup"><span data-stu-id="b277e-201">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="b277e-202">{}[ポリシーの編集] ページの例に示すように、列名を中かっこ () で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b277e-202">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="b277e-203">[ポリシーの編集] ページの例に示されているように、角かっこの外側にある列を識別する単語を入力します。</span><span class="sxs-lookup"><span data-stu-id="b277e-203">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="b277e-204">4.</span><span class="sxs-lookup"><span data-stu-id="b277e-204">4.</span></span>  <br/> |<span data-ttu-id="b277e-205">改行を追加するには、改行を表示する場所に「 **\n** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b277e-205">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="b277e-206">5.</span><span class="sxs-lookup"><span data-stu-id="b277e-206">5.</span></span>  <br/> |<span data-ttu-id="b277e-207">目的のフォントサイズとスタイルを選択し、文書内でラベルを左揃え、中央揃え、右揃えのどちらに配置するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-207">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="b277e-208">ユーザーのコンピューターで使用可能なフォントとスタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-208">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="b277e-209">フォントのサイズは、ラベルに表示できるテキストの量に影響します。</span><span class="sxs-lookup"><span data-stu-id="b277e-209">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="b277e-210">6.</span><span class="sxs-lookup"><span data-stu-id="b277e-210">6.</span></span>  <br/> |<span data-ttu-id="b277e-211">ラベルの高さと幅を入力します。</span><span class="sxs-lookup"><span data-stu-id="b277e-211">Enter the height and width of the label.</span></span> <span data-ttu-id="b277e-212">ラベルの高さは0.25 インチから20インチで、ラベルの幅は0.25 インチから20インチの範囲にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-212">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="b277e-213">ラベルの文字列は、常にラベルのイメージ内で垂直方向に中央揃えされます。</span><span class="sxs-lookup"><span data-stu-id="b277e-213">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="b277e-214">7.</span><span class="sxs-lookup"><span data-stu-id="b277e-214">7.</span></span>  <br/> |<span data-ttu-id="b277e-215">[**更新**] を選択して、ラベルの内容をプレビューします。</span><span class="sxs-lookup"><span data-stu-id="b277e-215">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="b277e-216">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-216">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="b277e-217">リスト、ライブラリ、またはフォルダーに対するポリシーを作成する (場所に応じた保持ポリシー)</span><span class="sxs-lookup"><span data-stu-id="b277e-217">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="b277e-218"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-218"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="b277e-219">特定のリスト、ライブラリ、またはフォルダーにのみ適用されるアイテム保持ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-219">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="b277e-220">ただし、この方法でアイテム保持ポリシーを作成した場合、他のリスト、ライブラリ、フォルダー、またはサイトでこのポリシーを再利用することはできません。また、サイトコレクションポリシーを場所に基づいたポリシーに適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b277e-220">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="b277e-221">単一の場所にあるすべての種類のコンテンツに対して単一のアイテム保持ポリシーを適用する場合は、ほとんどの場合、場所に基づく保持を使用することをお考えください。</span><span class="sxs-lookup"><span data-stu-id="b277e-221">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="b277e-222">その他のほとんどの場合は、すべてのコンテンツタイプに対してアイテム保持ポリシーが指定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b277e-222">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="b277e-223">継承を解除して新しいアイテム保持ポリシーを子レベルで定義しない限り、各サブフォルダーはその親のアイテム保持ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b277e-223">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="b277e-224">リストまたはライブラリに保持以外の情報管理ポリシーを定義する場合は、そのリストまたはライブラリに関連付けられている個々のリストコンテンツタイプごとに情報管理ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b277e-224">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="b277e-225">コンテンツタイプからリストまたはライブラリの場所に基づくポリシーに切り替えることを決定した場合、そのアイテム保持ポリシーのみが場所ベースのポリシーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b277e-225">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="b277e-226">他のすべての管理ポリシー (監査、バーコード、およびバーコード) は、関連付けられたコンテンツタイプから継承されます。</span><span class="sxs-lookup"><span data-stu-id="b277e-226">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="b277e-227">サイトコレクションでは、ライブラリおよびフォルダーベースの保持機能を非アクティブ化することによって、場所に基づくポリシーを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-227">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="b277e-228">これにより、サイトコレクション管理者は、そのコンテンツタイプポリシーがリスト管理者の場所に基づいたポリシーによって上書きされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-228">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="b277e-229">リストまたはライブラリの情報管理ポリシーの設定を変更するには、少なくともリストの管理権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="b277e-229">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="b277e-230">情報管理ポリシーを指定するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b277e-230">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="b277e-231">リボンで、**ライブラリ**または**リスト**タブライブラリの \> **設定**または**リスト設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-231">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="b277e-232">SharePoint Online で、[**設定**] をクリックし、[**リストの設定**] または [**ライブラリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-232">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="b277e-233">[**権限と管理** \> **情報管理ポリシーの設定**] の下。</span><span class="sxs-lookup"><span data-stu-id="b277e-233">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="b277e-235">[情報管理ポリシーの設定] ページで、リストまたはライブラリの保持のソースが [ライブラリとフォルダー] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b277e-235">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="b277e-236">**コンテンツタイプ**がソースとして表示されている場合は、[**ソースの変更**] をクリックし、[**ライブラリとフォルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-236">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="b277e-237">コンテンツタイプのアイテム保持ポリシーが無視されるという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b277e-237">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="b277e-238">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-238">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="b277e-239">[ポリシーの編集] ページの [**ライブラリベースの保持スケジュール**] で、作成するポリシーの簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b277e-239">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="b277e-240">[**保持ステージの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-240">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="b277e-241">[レコード] の下で、[レコードに対してさまざまな保持ステージを定義する] オプションを選択することによって、レコードに異なるアイテム保持ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-241">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="b277e-242">[ステージのプロパティ] ダイアログで、[保持期間] オプションを選択して、ドキュメントまたはアイテムの有効期限を設定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-242">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="b277e-243">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b277e-243">Do one of the following:</span></span>
    
  - <span data-ttu-id="b277e-244">日付プロパティに基づいて有効期限を設定するには、[**イベント**は \> **このステージはアイテムの日付プロパティに基づいてい**ます] の下にある [ドキュメントまたはアイテム] アクション (たとえば、[作成日時] または [変更日時]) を選択し、このアクションの後の時間の増分 (たとえば、アイテムを期限切れにします)</span><span class="sxs-lookup"><span data-stu-id="b277e-244">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="b277e-245">カスタム保持期間の計算式を使用して有効期限を決定するには、[**このサーバーにインストールされているカスタム保持期間の数式で設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-245">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="b277e-246">このオプションは、管理者によってカスタム式が設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-246">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="b277e-247">[**アクション**] で、ドキュメントまたはアイテムの有効期限が切れたときに行う処理を指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-247">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="b277e-248">ドキュメントまたはアイテムに対する特定のアクション (削除など) を有効にするには、リストからアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-248">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="b277e-249">[**ワークフローの開始**] オプションは、既にワークフローが関連付けられているリスト、ライブラリ、またはコンテンツタイプのポリシーを定義している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-249">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="b277e-250">その後、選択するワークフローが選択されます。</span><span class="sxs-lookup"><span data-stu-id="b277e-250">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="b277e-251">[**定期的なアイテム**] で、[**このステージの動作を繰り返す**] を選択します。を選択し、アクションを実行する頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="b277e-251">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="b277e-252">このオプションは、選択したアクションを繰り返すことができる場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-252">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="b277e-253">たとえば、アクションが**完全に削除**されると、定期的なアイテムを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b277e-253">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="b277e-254">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-254">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="b277e-255">サイトコレクションポリシーをコンテンツタイプに適用する</span><span class="sxs-lookup"><span data-stu-id="b277e-255">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="b277e-256"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-256"><a name="__apply_a_site"> </a></span></span>

<span data-ttu-id="b277e-257">サイトコレクションポリシーとしてサイトに情報管理ポリシーが既に作成されている場合は、1つのポリシーをコンテンツタイプに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-257">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="b277e-258">これにより、同じ親コンテンツタイプを共有しないサイトコレクション内の複数のコンテンツタイプに同じポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-258">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="b277e-259">ポリシーをサイトコレクション内の複数のコンテンツタイプに適用し、Managed Metadata Service を構成している場合は、コンテンツタイプの発行を使用して、情報管理ポリシーを複数のサイトコレクションに公開できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-259">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="b277e-260">詳細については、「[サイトコレクション全体にポリシーを適用](#apply-a-policy-across-site-collections)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b277e-260">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="b277e-261">ポリシーを適用するコンテンツタイプを含むリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b277e-261">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="b277e-262">リボンで、**ライブラリ**または**リスト**タブライブラリの \> **設定**または**リスト設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-262">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="b277e-263">SharePoint Online で、[**設定**] をクリックし、[**リストの設定**] または [**ライブラリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-263">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="b277e-264">[**権限と管理** \> **情報管理ポリシーの設定**] の下。</span><span class="sxs-lookup"><span data-stu-id="b277e-264">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="b277e-266">ポリシーソースが [**コンテンツタイプ**] に設定されていることを確認し、[**コンテンツタイプポリシー** ] で、ポリシーを適用するコンテンツタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-266">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="b277e-267">[**ポリシーを指定**して \> **サイトコレクションポリシーを使用**する] で、適用するポリシーをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-267">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="b277e-268">[**サイトコレクションポリシーを使用**する] オプションが使用できない場合は、サイトコレクションに対してサイトコレクションポリシーが定義されていません。</span><span class="sxs-lookup"><span data-stu-id="b277e-268">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="b277e-269">その後で、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-269">Choose **OK**.</span></span>
    
     <span data-ttu-id="b277e-270">作業しているリストまたはライブラリが複数のコンテンツタイプの管理をサポートしている場合は、[**コンテンツタイプ**] で情報管理ポリシーを指定するコンテンツタイプを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-270">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="b277e-271">この操作を行うと、上記の手順5に進みます。</span><span class="sxs-lookup"><span data-stu-id="b277e-271">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="b277e-272">サイトコレクション間でポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="b277e-272">Apply a policy across site collections</span></span>
<span data-ttu-id="b277e-273"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-273"><a name="__toc260646789"> </a></span></span>

<span data-ttu-id="b277e-274">コンテンツタイプの発行をセットアップするために Managed Metadata service アプリケーションを使用して、サイトコレクション間でコンテンツタイプを共有します。</span><span class="sxs-lookup"><span data-stu-id="b277e-274">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="b277e-275">コンテンツタイプの発行は、コンテンツタイプを一元的に作成および更新できるため、また複数のサブスクライブ元サイトコレクションまたは Web アプリケーションに更新を発行できるため、コンテンツとメタデータをサイト全体で一貫して管理するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="b277e-275">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="b277e-276">サイトコレクション全体で使用するテンプレートを既存のポリシーから作成する</span><span class="sxs-lookup"><span data-stu-id="b277e-276">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="b277e-277"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-277"><a name="__toc262125409"> </a></span></span>

<span data-ttu-id="b277e-278">情報管理ポリシーを定義し、そこからテンプレートを作成して、複数のサイトコレクション間で必要に応じて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-278">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="b277e-279">この方法は、情報ポリシーのバックアップが必要な場合、またはサイトコレクション間で1つのポリシーを適用するためにコンテンツタイプの発行を使用する代替手段としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-279">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="b277e-280">ポリシーのテンプレートまたはバックアップを作成するには、ポリシーを1つのサイトコレクションからエクスポートしてから、保存した場所または別のサイトコレクションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="b277e-280">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="b277e-281">ポリシーテンプレートのセットを作成する方法としてエクスポート/インポート機能を使用している場合は、ポリシーの .xml ファイルに一意の識別子が存在することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b277e-281">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="b277e-282">そのため、この一意識別子を変更せずに、そのポリシーをサイトに複数回インポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b277e-282">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="b277e-283">ポリシーをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b277e-283">Export a policy</span></span>
<span data-ttu-id="b277e-284"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-284"><a name="__toc260646790"> </a></span></span>

1. <span data-ttu-id="b277e-285">サイトコレクションのホームページで、[**設定**] [サイトの設定] の代わりに [設定] を選択し ![ ます。 ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Site Settings**</span><span class="sxs-lookup"><span data-stu-id="b277e-285">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b277e-286">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-286">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b277e-287">[サイトの設定] ページの [**サイトコレクションの管理** \> **コンテンツタイプポリシーテンプレート**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-287">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="b277e-289">[エクスポートするポリシー] を選択し \> て、下のエクスポートにスクロールし \> **Export**ます。</span><span class="sxs-lookup"><span data-stu-id="b277e-289">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="b277e-290">ファイルを保存するか開くかを確認するメッセージが表示されたら、[**保存**] を選択して、ファイルを保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-290">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="b277e-291">ポリシーをインポートするサイトコレクションで使用可能な場所を選択してください。</span><span class="sxs-lookup"><span data-stu-id="b277e-291">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="b277e-292">[ダウンロードの完了] ダイアログが表示されたら、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-292">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="b277e-293">ポリシーを別のサイトコレクションにインポートする</span><span class="sxs-lookup"><span data-stu-id="b277e-293">Import a policy to a different site collection</span></span>
<span data-ttu-id="b277e-294"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="b277e-294"><a name="__toc260646791"> </a></span></span>

<span data-ttu-id="b277e-295">情報管理ポリシーをインポートすると、特定のサイトコレクション内のサイトレベルまたはリストレベルで複数のコンテンツタイプに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-295">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="b277e-296">これを行うと、次の2つの利点があります。各コンテンツタイプにポリシーを再定義して適用する必要はありません。また、ポリシーに変更を加えることによって、ポリシーの変更を1か所で容易に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-296">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="b277e-297">ポリシーを適用するサイトコレクションのホームページで、[設定] [サイトの設定] の代わりに [**設定**- ![ 小型の設定歯車] ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Site Settings**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b277e-297">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b277e-298">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b277e-298">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b277e-299">[サイトの設定] ページの [**サイトコレクションの管理** \> **コンテンツタイプポリシーテンプレート**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="b277e-299">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="b277e-300">[ポリシー] ページの [インポート] を選択して、 \> **Import** \> **Browse**ポリシーの XML ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="b277e-300">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="b277e-301">ポリシーが保存されている XML ファイルを選択し \> **Open**ます。</span><span class="sxs-lookup"><span data-stu-id="b277e-301">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="b277e-302">[サイトコレクションポリシーのインポート] ページで、この \> **Import**ポリシーをサイトコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b277e-302">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="b277e-303">インポートされたポリシーは、サイトレベルまたはリストレベルで、1つまたは複数のコンテンツタイプに適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b277e-303">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="b277e-304">情報管理ポリシーを使用すると、コンテンツの保持期間を制御したり、コンテンツについてユーザーの作業を監査したり、バーコードやラベルをドキュメントに追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="b277e-304">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="b277e-305">ポリシーを使用すると、法律上および行政上の規制や内部のビジネスプロセスに準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="b277e-305">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="b277e-306">管理者は、ドキュメントの追跡方法やドキュメントを保持する期間を制御するポリシーをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="b277e-306">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="b277e-307">情報管理ポリシーは、サイト階層内の3つの異なる場所 (最も広いものから最も狭いものまで) に作成できます。</span><span class="sxs-lookup"><span data-stu-id="b277e-307">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="b277e-308">サイトコレクション内の複数のコンテンツタイプで使用するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b277e-308">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="b277e-309">サイトコンテンツタイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b277e-309">Create a policy for a site content type.</span></span>
- <span data-ttu-id="b277e-310">リストまたはライブラリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b277e-310">Create a policy for a list or library.</span></span>

<span data-ttu-id="b277e-311">詳細については、「[情報管理ポリシーの概要](intro-to-info-mgmt-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b277e-311">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

