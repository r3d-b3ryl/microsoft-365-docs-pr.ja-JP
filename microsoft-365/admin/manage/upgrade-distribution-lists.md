---
title: Outlook で配布リストを Microsoft 365 グループにアップグレードする
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 1 つ以上の配布リストを Outlook の Microsoft 365 グループにアップグレードする方法と、PowerShell を使用して複数の配布リストを同時にアップグレードする方法について説明します。
ms.openlocfilehash: 8179937cafa26a2258f67baee29fcec65bd60632
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332452"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="aede8-103">Outlook で配布リストを Microsoft 365 グループにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="aede8-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="aede8-104">Outlook で配布リストを Microsoft 365 グループにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="aede8-104">You can upgrade distribution lists to Microsoft 365 Groups in Outlook.</span></span> <span data-ttu-id="aede8-105">これは、組織の配布リストに Microsoft 365 グループのすべての機能と機能を提供する最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="aede8-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="aede8-106">Outlook で配布リストをグループにアップグレードする理由</span><span class="sxs-lookup"><span data-stu-id="aede8-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="aede8-107">配布リストは 1 つずつ、または複数を同時にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="aede8-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="aede8-108">Outlook で 1 つ以上の配布リスト グループを Microsoft 365 グループにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="aede8-108">Upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="aede8-109">配布リスト グループをアップグレードするには、グローバル管理者または Exchange 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aede8-109">You must be a global admin or Exchange admin to upgrade a distribution list group.</span></span> <span data-ttu-id="aede8-110">Microsoft 365 グループにアップグレードするには、配布リスト グループにメールボックスを持つ所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="aede8-110">To upgrade to Microsoft 365 Groups, the distribution list group must have an owner with a mailbox.</span></span>

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="aede8-111">Outlook の Microsoft 365 グループに 1 つ以上の配布リスト グループをアップグレードするには、新しい EAC を使用します。</span><span class="sxs-lookup"><span data-stu-id="aede8-111">Use the new EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="aede8-112">新しい Exchange 管理センター [に移動し](https://admin.exchange.microsoft.com)、[受信者グループ **] に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="aede8-112">Go to the new [Exchange admin center](https://admin.exchange.microsoft.com), and navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="aede8-113">[グループ] ページから、Microsoft 365 グループにアップグレードする配布リスト グループ (配布グループとも呼ばれる)**を選択** します。 </span><span class="sxs-lookup"><span data-stu-id="aede8-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span></span>

3. <span data-ttu-id="aede8-114">ツール バー **から [アップグレード配布グループ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aede8-114">Select the **Upgrade distribution group** from the tool bar.</span></span>

4. <span data-ttu-id="aede8-115">[アップグレードの準備完了] ダイアログ ボックス **で、[アップグレード]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aede8-115">In the dialog box **Ready to upgrade?**, click **Upgrade**.</span></span> <span data-ttu-id="aede8-116">プロセスがすぐに開始されます。</span><span class="sxs-lookup"><span data-stu-id="aede8-116">The process begins immediately.</span></span> <span data-ttu-id="aede8-117">アップグレードする配布リスト グループのサイズと数に応じて、プロセスには数分または数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aede8-117">Depending on the size and number of distribution list groups you're upgrading, the process can take minutes or hours.</span></span>

> [!NOTE]
> <span data-ttu-id="aede8-118">上部のバナーは、アップグレード (配布グループなど) がアップグレード *された状態を示します。変更を反映するには 5 分かかります。Microsoft 365 グループでフィルター処理して、アップグレードされた不侵入グループを確認します*。</span><span class="sxs-lookup"><span data-stu-id="aede8-118">A banner at the top indicates the upgrade, for example, *Distribution group(s) has been upgraded. It will take 5 minutes to reflect the changes. Filter by Microsoft 365 groups to see the upgraded distrubtion groups(s)*.</span></span>

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="aede8-119">クラシック EAC を使用して、1 つ以上の配布リスト グループを Outlook の Microsoft 365 グループにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="aede8-119">Use the Classic EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="aede8-120">クラシック Exchange 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">に移動します</a>。</span><span class="sxs-lookup"><span data-stu-id="aede8-120">Go to the Classic <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="aede8-121">クラシック Exchange 管理センターで、[受信者グループ] **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="aede8-121">In the Classic Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="aede8-122">Microsoft 365 グループにアップグレードできる配布リスト (配布 **グループとも呼** ばれる) を持っているという通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aede8-122">You'll see a notice indicating you have distribution lists (also called **distribution groups**) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="aede8-123">![[スタート] ボタンを選択する](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="aede8-123">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="aede8-124">[グループ] ページから 1 つ以上の配布リスト (配布 **グループ** とも呼ばれる) **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="aede8-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span></span><br/><span data-ttu-id="aede8-125">![配布グループを選択する](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="aede8-125">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="aede8-126">アップグレード アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="aede8-126">Select the upgrade icon.</span></span><br/>![[Microsoft 365 グループへのアップグレード] アイコン](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="aede8-128">情報ダイアログで、[はい] **を選択して** アップグレードを確認します。</span><span class="sxs-lookup"><span data-stu-id="aede8-128">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="aede8-129">プロセスがすぐに開始されます。</span><span class="sxs-lookup"><span data-stu-id="aede8-129">The process begins immediately.</span></span> <span data-ttu-id="aede8-130">アップグレードする配布リストのサイズや数に応じて、処理には数分または数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="aede8-130">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="aede8-131">配布リストをアップグレードできない場合は、それを示すダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aede8-131">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="aede8-132">「 [アップグレードできない配布リスト」を参照してください](#which-distribution-lists-cant-be-upgraded)。</span><span class="sxs-lookup"><span data-stu-id="aede8-132">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="aede8-133">複数の配布リストをアップグレードする場合は、ドロップダウン リストを使用して、アップグレードされた配布リストをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="aede8-133">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="aede8-134">リストが完了しない場合は、しばらく待ち、次に [更新] を選択して、正常にアップグレードされた項目を確認します。</span><span class="sxs-lookup"><span data-stu-id="aede8-134">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="aede8-p107">選択した配布リストのすべてのアップグレード プロセスが完了しても、通知は表示されません。[ **アップグレード可能** ] または [ **アップグレードされた配布リスト** ] に一覧された内容を確認して、これを把握することができます。</span><span class="sxs-lookup"><span data-stu-id="aede8-p107">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="aede8-137">アップグレード用に DL を選択したが、アップグレード可能としてページに表示された場合、アップグレードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="aede8-137">If you selected a DL for upgrade, but it's still appeared on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="aede8-138">「[アップグレードが機能しない場合の対処方法](#what-to-do-if-the-upgrade-doesnt-work)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aede8-138">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="aede8-p109">グループのダイジェスト メールを受け取っている場合は、下部に通知が表示され、所有者になっている対象の配布リストをアップグレードできるように示されることがあります。ダイジェスト メールの詳細については、「[Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)」 (Outlook でグループ会話を使用する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aede8-p109">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="aede8-141">アップグレードが機能しない場合の対処方法</span><span class="sxs-lookup"><span data-stu-id="aede8-141">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="aede8-142">アップグレードに失敗した配布リストは、変更されないまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="aede8-142">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="aede8-p110">1 つ以上の **対象** の配布リストがアップグレードに失敗した場合は、 [サポート チケット](../../business-video/get-help-support.md)を開きます。問題を解決するために、この問題をグループ エンジニアリング チームにエスカレーションする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aede8-p110">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../../business-video/get-help-support.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="aede8-145">サービスの停止により配布リストがアップグレードされませんが、可能性は低い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aede8-145">It's possible that the distribution list didn't get upgraded because of a service outage, but unlikely.</span></span> <span data-ttu-id="aede8-146">必要な場合は、しばらく待ってから、もう一度配布リストをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="aede8-146">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="aede8-147">PowerShell を使用して複数の配布リストを同時にアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="aede8-147">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="aede8-p112">PowerShell の使用経験がある場合は、UI ではなく、この手順を使用することをお勧めします。配布リストのアップグレードに役立つ一連のコマンドレットが用意されています。以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aede8-p112">If you're experienced at using PowerShell, you might want to go this route instead of using the UI. We have a set of cmdlets that will help you upgrade distribution lists. See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="aede8-151">1 つの DL をアップグレードする</span><span class="sxs-lookup"><span data-stu-id="aede8-151">Upgrade a single DL</span></span>

<span data-ttu-id="aede8-152">単一の DL をアップグレードするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aede8-152">To upgrade a single DL, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>
```

<span data-ttu-id="aede8-153">たとえば、SMTP アドレスが dl1@contoso.com の DL をアップグレードする場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aede8-153">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> <span data-ttu-id="aede8-154">[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell コマンドレットを使用して、1 つの配布リストを Microsoft 365 グループにアップグレードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aede8-154">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="aede8-155">複数の DL を一括してアップグレードする</span><span class="sxs-lookup"><span data-stu-id="aede8-155">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="aede8-156">複数の DL をバッチとして渡し、まとめてアップグレードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aede8-156">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="aede8-157">たとえば、SMTP アドレスを使用して 5 つの DLL をアップグレードする場合 `dl1@contoso.com` 、および `dl2@contoso.com` `dl3@contoso.com` 、 `dl4@contoso.com` `dl5@contoso.com` 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aede8-157">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="aede8-158">対象となるすべての DL をアップグレードする</span><span class="sxs-lookup"><span data-stu-id="aede8-158">Upgrade all eligible DLs</span></span>

<span data-ttu-id="aede8-159">対象となるすべての DL をアップグレードするには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="aede8-159">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="aede8-160">このUpgrade-DistributionGroupコマンドレットはパイプラインからデータを受け取らないので、"foreach-object" 演算子を使用して正常に {} 実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aede8-160">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="aede8-161">テナント内の適格な DLL を取得し、upgrade コマンドを使用してアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="aede8-161">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="aede8-162">2.すべての DL の一覧を取得し、対象となる DL のみをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="aede8-162">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="aede8-163">Outlook で配布リストを Microsoft 365 グループにアップグレードする方法に関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="aede8-163">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="aede8-164">アップグレードできない配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-164">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="aede8-165">クラウド管理されている、単純で入れ子になっていない配布リストのみをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="aede8-165">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="aede8-166">次の表に、アップグレードできない **配布リスト** を示します。</span><span class="sxs-lookup"><span data-stu-id="aede8-166">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="aede8-167">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="aede8-167">**Property**</span></span>|<span data-ttu-id="aede8-168">**対象**</span><span class="sxs-lookup"><span data-stu-id="aede8-168">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aede8-169">オンプレミスで管理される配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-169">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="aede8-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-170">No</span></span>  <br/> |
|<span data-ttu-id="aede8-p114">入れ子になった配布リスト子グループがあるか、または別のグループのメンバーである配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-p114">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="aede8-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-173">No</span></span>  <br/> |
|<span data-ttu-id="aede8-174">**UserMailbox**、SharedMailbox **、TeamMailbox** **、MailUser** 以外のメンバー **RecipientTypeDetails** を持つ配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-174">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="aede8-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-175">No</span></span>  <br/> |
|<span data-ttu-id="aede8-176">所有者が 100 人を超える配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-176">Distribution list that has more than 100 owners</span></span>  <br/> |<span data-ttu-id="aede8-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-177">No</span></span>  <br/> |
|<span data-ttu-id="aede8-178">メンバーのみを持ち、所有者がない配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-178">Distribution list that only has members but no owner</span></span>  <br/> |<span data-ttu-id="aede8-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-179">No</span></span>  <br/> |
|<span data-ttu-id="aede8-180">特殊文字を含むエイリアスを含む配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-180">Distribution list that has alias containing special characters</span></span>  <br/> |<span data-ttu-id="aede8-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-181">No</span></span>  <br/> |
|<span data-ttu-id="aede8-182">配布リストが共有メールボックスの転送アドレスになるように構成されている場合</span><span class="sxs-lookup"><span data-stu-id="aede8-182">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="aede8-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-183">No</span></span>  <br/> |
|<span data-ttu-id="aede8-184">DL が別の DL の **送信者制限の一** 部である場合。</span><span class="sxs-lookup"><span data-stu-id="aede8-184">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="aede8-185">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-185">No</span></span>  <br/> |
|<span data-ttu-id="aede8-186">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="aede8-186">Security groups</span></span>  <br/> |<span data-ttu-id="aede8-187">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-187">No</span></span>  <br/> |
|<span data-ttu-id="aede8-188">動的配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-188">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="aede8-189">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-189">No</span></span>  <br/> |
|<span data-ttu-id="aede8-190">**RoomLists** に変換された配布リスト</span><span class="sxs-lookup"><span data-stu-id="aede8-190">Distribution lists that were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="aede8-191">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-191">No</span></span>  <br/> |
|<span data-ttu-id="aede8-192">**MemberJoinRestriction および/または** **MemberDepartRestriction** が閉じている配布 **リスト**</span><span class="sxs-lookup"><span data-stu-id="aede8-192">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="aede8-193">いいえ</span><span class="sxs-lookup"><span data-stu-id="aede8-193">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="aede8-194">アップグレードの対象となる DLL を確認する</span><span class="sxs-lookup"><span data-stu-id="aede8-194">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="aede8-195">ある DL がアップグレード対象かどうかを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aede8-195">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="aede8-196">アップグレード対象の DL を確認する場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aede8-196">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="aede8-197">どのユーザーがアップグレード スクリプトを実行できますか?</span><span class="sxs-lookup"><span data-stu-id="aede8-197">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="aede8-198">グローバル管理者または Exchange 管理者権限を持つユーザー。</span><span class="sxs-lookup"><span data-stu-id="aede8-198">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="aede8-199">連絡先カードに依然として配布リストが表示されるのはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="aede8-199">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="aede8-200">アップグレードされた配布リストが自動提案リストに表示されるのを防ぐには、どのような操作を行う必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="aede8-200">What should I do to prevent an upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="aede8-201">Outlook の場合: 移行後に Microsoft 365 グループ名を入力して Outlook で電子メールを送信しようとすると、受信者はグループの代わりに配布リストとして解決されます。</span><span class="sxs-lookup"><span data-stu-id="aede8-201">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="aede8-202">受信者の連絡先カードは配布リストの連絡先カードとなります。</span><span class="sxs-lookup"><span data-stu-id="aede8-202">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="aede8-203">これは Outlook の受信者キャッシュまたはニックネーム キャッシュに起因します。</span><span class="sxs-lookup"><span data-stu-id="aede8-203">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="aede8-204">電子メールはグループに正常に送信されますが、送信者に混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aede8-204">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="aede8-205">この記事の「キャッシュをリセットする [Outlook AutoComplete](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) リストに関する情報」の手順を実行すると、この問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="aede8-205">You can perform the steps in this article, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="aede8-206">Outlook on the web: Outlook on the web の場合、配布リストの受信者は引き続きキャッシュに残ります。</span><span class="sxs-lookup"><span data-stu-id="aede8-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="aede8-207">「自動完了リストから推奨[](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58)される名前または電子メール アドレスを削除する」の手順に従って、キャッシュを更新してグループ連絡先カードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="aede8-207">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="aede8-208">新しいグループのメンバーは、受信トレイでウェルカム メッセージを受け取りますか?</span><span class="sxs-lookup"><span data-stu-id="aede8-208">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="aede8-p118">いいえ。ウェルカム メッセージを有効にする設定は、既定で false に設定されています。この設定は、既存のグループ メンバーにも、移行が完了した後に参加する可能性がある新しいグループ メンバーにも影響します。グループの所有者が後でゲスト ユーザーを許可した場合、ゲスト ユーザーは受信トレイでウェルカム メールを受け取ることはありません。ゲスト メンバーはグループで継続して作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="aede8-p118">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="aede8-214">1 つまたは一部の DLL がアップグレードされていない場合は、どうしますか。</span><span class="sxs-lookup"><span data-stu-id="aede8-214">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="aede8-215">DL が対象ですが、アップグレードできない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="aede8-215">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="aede8-216">DL はアップグレードされません。DL として残ります。</span><span class="sxs-lookup"><span data-stu-id="aede8-216">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="aede8-217">管理者が組織内の **グループ** にグループ メール アドレス ポリシーを適用し、条件を満たしていない DLL をアップグレードしようとする場合、DL はアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="aede8-217">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs that doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="aede8-218">**MemberJoinRestriction** または **MemberDepartRestriction** が **Closed** に設定されている DLL をアップグレードできない</span><span class="sxs-lookup"><span data-stu-id="aede8-218">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="aede8-219">EAC からのアップグレードに失敗した場合、配布リストはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="aede8-219">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="aede8-p120">呼び出しがサーバーに送信された場合にのみ、アップグレードが発生します。アップグレードが失敗した場合、配布リストはそのまま保持されます。配布リストは、以前のように動作します。</span><span class="sxs-lookup"><span data-stu-id="aede8-p120">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>
