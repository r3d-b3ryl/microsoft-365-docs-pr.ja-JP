---
title: 法的保留通知を作成する
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 法的保留通知の送信、収集、および追跡Advanced eDiscovery場合は、通信ツールを使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840562"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="e60be-103">法的保留通知を作成する</span><span class="sxs-lookup"><span data-stu-id="e60be-103">Create a legal hold notice</span></span>

<span data-ttu-id="e60be-104">管理Advanced eDiscoveryを使用して、組織は保管担当者との通信に関するワークフローを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-104">Using Advanced eDiscovery custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="e60be-105">コミュニケーション ツールを通じて、法務チームは法的ホールド通知を体系的に送信、収集、追跡できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-105">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="e60be-106">柔軟な作成プロセスにより、チームは保留通知ワークフローと、保管担当者に送信される通知のコンテンツをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e60be-106">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span>

![コミュニケーション ページ](../media/CommunicationPage.PNG)

<span data-ttu-id="e60be-108">この記事では、保留通知ワークフローの手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="e60be-108">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="e60be-109">手順 1: 通信の詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="e60be-109">Step 1: Specify communication details</span></span>

<span data-ttu-id="e60be-110">最初の手順は、法的保留通知または他の保管担当者の通信に関する適切な詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-110">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span>

![[名前の通信] ページ](../media/NameCommunication.PNG)

1. <span data-ttu-id="e60be-112">[セキュリティ & コンプライアンス センター] で、[電子情報開示] > Advanced eDiscoveryに移動して、組織内 **の** ケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e60be-112">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>

2. <span data-ttu-id="e60be-113">ケースを選択し、[通信] **タブをクリック** し、[新しい通信] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e60be-113">Select a case, click the **Communications** tab, and then click **New communication**.</span></span>

3. <span data-ttu-id="e60be-114">[名前の **通信] ページ** で、次の (必須) 通信の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-114">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="e60be-115">**名前**: これは通信の名前です。</span><span class="sxs-lookup"><span data-stu-id="e60be-115">**Name**: This is the name for the communication.</span></span>

    - <span data-ttu-id="e60be-116">**発行担当者**: ドロップダウン リストにケース メンバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-116">**Issuing officer**: The dropdown list displays a list of case members.</span></span> <span data-ttu-id="e60be-117">ケースに新しいメンバーを追加する方法の詳細については[、「Create a case a case」をAdvanced eDiscoveryしてください](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case)。</span><span class="sxs-lookup"><span data-stu-id="e60be-117">For more information on how to add new members to a case, see [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case).</span></span> <span data-ttu-id="e60be-118">保管担当者に送信される通知は、指定された発行担当者に代わって送信されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-118">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

> [!NOTE]
> <span data-ttu-id="e60be-119">発行担当者が [発行担当者] **ドロップダウン** に表示するには、アクティブなメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e60be-119">The issuing officer must have an **active mailbox** to show up in the Issuing Officer dropdown</span></span>


4. <span data-ttu-id="e60be-120">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e60be-120">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="e60be-121">手順 2: ポータル コンテンツを定義する</span><span class="sxs-lookup"><span data-stu-id="e60be-121">Step 2: Define the portal content</span></span>

<span data-ttu-id="e60be-122">次に、保留通知のコンテンツを作成して追加できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-122">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="e60be-123">[通信 **の作成] ウィザードの** [ポータル コンテンツの定義] **ページで、** 保留通知の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-123">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="e60be-124">このコンテンツは、発行、再発行、アラーム、エスカレーション通知に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-124">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="e60be-125">さらに、このコンテンツは保管担当者のコンプライアンス ポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-125">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![ポータル コンテンツ ページ](../media/PortalContent.PNG)

<span data-ttu-id="e60be-127">ポータル コンテンツを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e60be-127">To create the portal content:</span></span>

1. <span data-ttu-id="e60be-128">ポータル コンテンツのテキスト ボックスに保留通知を入力 (または別のドキュメントから切り取って貼り付けます)。</span><span class="sxs-lookup"><span data-stu-id="e60be-128">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="e60be-129">通知に差し込み変数を挿入して通知をカスタマイズし、Custodian コンプライアンス ポータルを共有します。</span><span class="sxs-lookup"><span data-stu-id="e60be-129">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="e60be-130">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e60be-130">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="e60be-131">ポータル コンテンツのコンテンツと形式をカスタマイズする方法の詳細については、「Use [the Communications Editor」を参照してください](using-communications-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="e60be-131">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="e60be-132">手順 3: 必要な通知を設定する</span><span class="sxs-lookup"><span data-stu-id="e60be-132">Step 3: Set the required notifications</span></span>

<span data-ttu-id="e60be-133">保留通知の内容を定義した後、通知プロセスの送信と管理に関するワークフローを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-133">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="e60be-134">通知は、保管担当者に通知およびフォローアップするために送信される電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="e60be-134">Notifications are email messages that are sent to notify and follow up with custodians.</span></span> <span data-ttu-id="e60be-135">通信に追加された保管担当者は、同じ通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e60be-135">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="e60be-136">保留通知を設定して送信するには、発行、再発行、およびリリース通知を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e60be-136">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="e60be-137">発行通知</span><span class="sxs-lookup"><span data-stu-id="e60be-137">Issuance notification</span></span> 

<span data-ttu-id="e60be-138">通信が作成されると、指定された発行 **担当者** によって発行通知が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-138">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="e60be-139">発行通知は、保管担当者に保存義務を通知するために最初に送信される通信です。</span><span class="sxs-lookup"><span data-stu-id="e60be-139">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="e60be-140">発行通知を作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e60be-140">To create an issuance notification:</span></span>

1. <span data-ttu-id="e60be-141">[発行] **タイルで** 、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e60be-141">In the **Issuance** tile, click **Edit**.</span></span>

2. <span data-ttu-id="e60be-142">必要に応じて、Cc フィールドと Bcc フィールドにケース メンバーまたはスタッフ **を追加** します。 </span><span class="sxs-lookup"><span data-stu-id="e60be-142">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="e60be-143">これらのフィールドに複数のユーザーを追加するには、電子メール アドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e60be-143">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="e60be-144">通知の **件名を** 指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-144">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="e60be-145">保管担当者に提供する内容または追加の指示を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-145">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="e60be-146">手順 2 で定義したポータル コンテンツが発行通知の末尾に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-146">The portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 

5. <span data-ttu-id="e60be-147">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e60be-147">Click **Save**.</span></span>

### <a name="re-issuance-notification"></a><span data-ttu-id="e60be-148">Re-Issuance通知</span><span class="sxs-lookup"><span data-stu-id="e60be-148">Re-Issuance notification</span></span>

<span data-ttu-id="e60be-149">ケースが進むにつれて、以前に指示されたデータよりも追加または少ないデータを保持するために保管担当者が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e60be-149">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="e60be-150">ポータル コンテンツを更新すると、再発行通知が送信され、保管担当者に保存義務に対する変更について通知されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-150">After you update the portal content, the re-issuance notification is sent and alerts custodians about any changes to their preservation obligations.</span></span>

<span data-ttu-id="e60be-151">再発行通知を作成するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e60be-151">To create a re-issuance notification:</span></span>

1. <span data-ttu-id="e60be-152">[再 **発行] タイルで、[** 編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e60be-152">In the **Reissue** tile, click **Edit**.</span></span>

2. <span data-ttu-id="e60be-153">必要に応じて、Cc フィールドと Bcc フィールドにケース メンバーまたはスタッフ **を追加** します。 </span><span class="sxs-lookup"><span data-stu-id="e60be-153">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="e60be-154">これらのフィールドに複数のユーザーを追加するには、電子メール アドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e60be-154">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="e60be-155">通知の **件名を** 指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-155">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="e60be-156">保管担当者に提供する内容または追加の指示を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-156">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="e60be-157">手順 2 で定義したポータル コンテンツは、再発行通知の最後に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-157">The portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>

5. <span data-ttu-id="e60be-158">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e60be-158">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e60be-159">(通信の編集ウィザードの [ポータルコンテンツの定義]ページで) ポータル コンテンツが変更された場合、再発行通知は通知に割り当てられているすべての保管担当者に自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-159">If the portal content is modified (on the **Define Portal Content** page in the **Edit communication** wizard), the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="e60be-160">通知が送信された後、保管担当者は保留通知の再確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-160">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="e60be-161">リマインダーまたはエスカレーション ワークフローを設定している場合は、これらのワークフローも再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-161">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> <span data-ttu-id="e60be-162">他のケース管理イベントによって通信がトリガーされるイベントの詳細については、「通知をトリガー [するイベント」を参照してください](#events-that-trigger-notifications)。</span><span class="sxs-lookup"><span data-stu-id="e60be-162">For more information about what other case management events trigger communications, see [Events that trigger notifications](#events-that-trigger-notifications).</span></span>

### <a name="release-notification"></a><span data-ttu-id="e60be-163">リリース通知</span><span class="sxs-lookup"><span data-stu-id="e60be-163">Release notification</span></span>

<span data-ttu-id="e60be-164">問題が解決された後、または保管担当者がコンテンツを保持する対象でなくなった場合は、ケースから保管担当者を解放できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-164">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="e60be-165">保管担当者が以前に保留通知を発行した場合、リリース通知を使用して、保管担当者に対して、その義務から解放されたという警告を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-165">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="e60be-166">リリース通知を作成するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e60be-166">To create a release notification:</span></span> 

1. <span data-ttu-id="e60be-167">[リリース] **タイルで** 、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e60be-167">In the **Release** tile, click **Edit**.</span></span>

2. <span data-ttu-id="e60be-168">必要に応じて、Cc フィールドと Bcc フィールドにケース メンバーまたはスタッフ **を追加** します。 </span><span class="sxs-lookup"><span data-stu-id="e60be-168">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="e60be-169">これらのフィールドに複数のユーザーを追加するには、電子メール アドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e60be-169">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="e60be-170">通知の **件名を** 指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-170">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="e60be-171">保管担当者に提供する内容または追加の指示を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-171">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>

5. <span data-ttu-id="e60be-172">[保存 **] を** クリックし、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e60be-172">Click **Save** and go to the next step.</span></span>

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="e60be-173">(省略可能)手順 4: オプションの通知を設定する</span><span class="sxs-lookup"><span data-stu-id="e60be-173">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="e60be-174">必要に応じて、自動アラーム通知とエスカレーション通知を作成およびスケジュールすることで、応答しない保管担当者をサポートするためのワークフローを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-174">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![アラーム/エスカレーション ページ](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="e60be-176">リマインダー</span><span class="sxs-lookup"><span data-stu-id="e60be-176">Reminders</span></span>

<span data-ttu-id="e60be-177">保留通知を送信した後、アラーム ワークフローを定義することで、応答しない保管担当者をフォローアップできます。</span><span class="sxs-lookup"><span data-stu-id="e60be-177">After you have sent a hold notification, you can follow up with unresponsive custodians by defining a reminder workflow.</span></span>

<span data-ttu-id="e60be-178">アラームのスケジュールを設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e60be-178">To schedule reminders:</span></span>

1. <span data-ttu-id="e60be-179">[アラーム] **タイルで** 、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e60be-179">In the **Reminder** tile, click **Edit**.</span></span>

2. <span data-ttu-id="e60be-180">[状態 **] トグル (** 必須) をオンにして **、アラーム ワークフロー** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e60be-180">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>

3. <span data-ttu-id="e60be-181">アラーム間隔 **(日数) (必須)** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-181">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="e60be-182">これは、最初の通知とフォローアップ通知を送信するまでに待機する日数です。</span><span class="sxs-lookup"><span data-stu-id="e60be-182">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="e60be-183">たとえば、アラーム間隔を 7 日間に設定すると、最初のアラームは、保留通知が最初に発行された 7 日後に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-183">For example, if you set the reminder interval to seven days, then the first reminder would be sent seven days after the hold notification was initially issued.</span></span> <span data-ttu-id="e60be-184">それ以降のすべてのリマインダーも 7 日ごとに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-184">All subsequent reminders would also be sent every seven days.</span></span>

4. <span data-ttu-id="e60be-185">アラームの **数を指定します** (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-185">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="e60be-186">このフィールドは、応答しない保管担当者に送信するアラームの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-186">This field specifies how many reminders to send to unresponsive custodians.</span></span> <span data-ttu-id="e60be-187">たとえば、アラームの数を 3 に設定すると、保管担当者は最大 3 つのアラームを受信します。</span><span class="sxs-lookup"><span data-stu-id="e60be-187">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of three reminders.</span></span> <span data-ttu-id="e60be-188">保管担当者が保留通知を確認すると、アラームはそのユーザーに送信されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e60be-188">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>

5. <span data-ttu-id="e60be-189">通知の **件名を** 指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-189">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="e60be-190">保管担当者に提供する内容または追加の指示を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-190">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="e60be-191">手順 2 で定義したポータル コンテンツがリマインダー通知の最後に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-191">The portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>

7. <span data-ttu-id="e60be-192">[保存 **] をクリック** し、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e60be-192">Click **Save** and go the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="e60be-193">エスカレーション</span><span class="sxs-lookup"><span data-stu-id="e60be-193">Escalations</span></span>

<span data-ttu-id="e60be-194">場合によっては、応答しない保管担当者をフォローアップするための追加の方法が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e60be-194">In some situations, you may need additional ways to follow up with unresponsive custodians.</span></span> <span data-ttu-id="e60be-195">指定した数のアラームを受け取った後に保管担当者が保留通知を確認しない場合、法務チームは、エスカレート通知を保管担当者とそのマネージャーに自動的に送信するワークフローを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-195">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="e60be-196">エスカレーションをスケジュールするには、</span><span class="sxs-lookup"><span data-stu-id="e60be-196">To schedule escalations:</span></span>

1. <span data-ttu-id="e60be-197">[エスカ **レーション] タイルで** 、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e60be-197">In the **Escalation** tile, click **Edit**.</span></span>

2. <span data-ttu-id="e60be-198">[状態] **トグルを** オンにして、エスカレーション ワークフロー **を有効** にします。</span><span class="sxs-lookup"><span data-stu-id="e60be-198">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>

3. <span data-ttu-id="e60be-199">エスカ **レーション間隔 (日数) (必須)** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-199">Specify the **Escalation interval (in days)** (required).</span></span>

4. <span data-ttu-id="e60be-200">[エス **カレーションの数] (必須)** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-200">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="e60be-201">このフィールドは、応答しないカストディアンに送信するエスカレーションの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e60be-201">This field specifies how many escalations to send to unresponsive custodians.</span></span> <span data-ttu-id="e60be-202">たとえば、エスカレーションの数を 3 に設定すると、エスカレーション通知が保管担当者とそのマネージャーに最大 3 回送信されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-202">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of three times.</span></span> <span data-ttu-id="e60be-203">保管担当者が保留通知を確認すると、エスカレーションは送信されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e60be-203">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span>

5. <span data-ttu-id="e60be-204">通知の **件名を** 指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-204">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="e60be-205">保管担当者に提供する内容または追加の指示を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="e60be-205">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="e60be-206">手順 2 で定義したポータル コンテンツがエスカレーション通知の最後に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-206">The portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>

7. <span data-ttu-id="e60be-207">[保存 **] をクリック** し、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e60be-207">Click **Save** and go the next step.</span></span>

## <a name="step-5-assign-custodians-to-receive-notifications"></a><span data-ttu-id="e60be-208">手順 5: 通知を受信する保管担当者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="e60be-208">Step 5: Assign custodians to receive notifications</span></span>

<span data-ttu-id="e60be-209">通知のコンテンツを確定したら、通知を送信するカストディアンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e60be-209">After you have finalized the content for notifications, select the custodians that you would like to send notifications to.</span></span> 

![[保管担当者の選択] ページ](../media/SelectCustodians.PNG)

<span data-ttu-id="e60be-211">保管担当者を追加するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e60be-211">To add custodians:</span></span>

1. <span data-ttu-id="e60be-212">名前の横にあるチェック ボックスをクリックして、通信にカストディアンを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e60be-212">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="e60be-213">通信が作成されると、通知ワークフローは選択した保管担当者に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-213">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>

2. <span data-ttu-id="e60be-214">[次 **へ]** をクリックして、通信の設定と詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="e60be-214">Click **Next** to review the communication settings and details.</span></span>

>[!NOTE]
><span data-ttu-id="e60be-215">ケースに追加され、ケース内で別の通知が送信されていないカストディアンのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e60be-215">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="e60be-216">手順 6: 設定を確認する</span><span class="sxs-lookup"><span data-stu-id="e60be-216">Step 6: Review settings</span></span>

<span data-ttu-id="e60be-217">設定を確認し、[送信]をクリックして通信を完了すると、システムは発行通知を送信して通信ワークフローを自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="e60be-217">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

## <a name="events-that-trigger-notifications"></a><span data-ttu-id="e60be-218">通知をトリガーするイベント</span><span class="sxs-lookup"><span data-stu-id="e60be-218">Events that trigger notifications</span></span>

<span data-ttu-id="e60be-219">次の表では、さまざまな種類の通知が保管担当者に送信される場合にトリガーされるケース管理プロセスのイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e60be-219">The following table describes events in the case management process that trigger when the different types of notifications are sent to custodians.</span></span>

|<span data-ttu-id="e60be-220">通信の種類</span><span class="sxs-lookup"><span data-stu-id="e60be-220">Type of communication</span></span>|<span data-ttu-id="e60be-221">トリガー</span><span class="sxs-lookup"><span data-stu-id="e60be-221">Trigger</span></span> |
|:---------|:---------|
|<span data-ttu-id="e60be-222">発行通知</span><span class="sxs-lookup"><span data-stu-id="e60be-222">Issuance notices</span></span>|<span data-ttu-id="e60be-223">通知の最初の作成。</span><span class="sxs-lookup"><span data-stu-id="e60be-223">The initial creation of the notification.</span></span> <span data-ttu-id="e60be-224">保留通知を手動で再送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="e60be-224">You can also manually resend a hold notification.</span></span> |
|<span data-ttu-id="e60be-225">再発行に関する通知</span><span class="sxs-lookup"><span data-stu-id="e60be-225">Re-issuance notices</span></span>|<span data-ttu-id="e60be-226">通信の編集ウィザードの **[ポータル コンテンツの定義** ] ページでポータル **コンテンツを更新** します。</span><span class="sxs-lookup"><span data-stu-id="e60be-226">Updating the portal content on the **Define Portal Content** page in the **Edit communication** wizard.</span></span>|
|<span data-ttu-id="e60be-227">リリース通知</span><span class="sxs-lookup"><span data-stu-id="e60be-227">Release notices</span></span>|<span data-ttu-id="e60be-228">保管担当者はケースから解放されます。</span><span class="sxs-lookup"><span data-stu-id="e60be-228">The custodian is released from the case.</span></span>|
|<span data-ttu-id="e60be-229">リマインダー</span><span class="sxs-lookup"><span data-stu-id="e60be-229">Reminders</span></span>|<span data-ttu-id="e60be-230">アラーム用に構成されたアラームの間隔と数。</span><span class="sxs-lookup"><span data-stu-id="e60be-230">The interval and number of reminders configured for the reminder.</span></span>|
|<span data-ttu-id="e60be-231">エスカレーション</span><span class="sxs-lookup"><span data-stu-id="e60be-231">Escalations</span></span>|<span data-ttu-id="e60be-232">エスカレーション用に構成されたアラームの間隔と数。</span><span class="sxs-lookup"><span data-stu-id="e60be-232">The interval and number of reminders configured for the escalation.</span></span>|
|||
