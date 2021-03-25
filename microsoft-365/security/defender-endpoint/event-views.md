---
title: 攻撃表面の縮小イベントの表示
description: カスタム ビューをインポートして、攻撃表面の縮小イベントを表示します。
keywords: イベント ビュー、exploit guard、監査、レビュー、イベント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: de605a667284c1218a3efe6e388d99b26b42e333
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068579"
---
# <a name="view-attack-surface-reduction-events"></a><span data-ttu-id="5aeb9-104">攻撃表面の縮小イベントの表示</span><span class="sxs-lookup"><span data-stu-id="5aeb9-104">View attack surface reduction events</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5aeb9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5aeb9-105">**Applies to:**</span></span>
- [<span data-ttu-id="5aeb9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5aeb9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5aeb9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5aeb9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5aeb9-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5aeb9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5aeb9-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="5aeb9-110">イベント ビューアーで攻撃表面の縮小イベントを確認し、動作しているルールや設定を監視します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-110">Review attack surface reduction events in Event Viewer to monitor what rules or settings are working.</span></span> <span data-ttu-id="5aeb9-111">また、設定が "ノイズ" すぎるか、毎日のワークフローに影響を与えるかどうかを判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-111">You can also determine if any settings are too "noisy" or impacting your day to day workflow.</span></span>

<span data-ttu-id="5aeb9-112">イベントのレビューは、機能を評価するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-112">Reviewing events is handy when you're evaluating the features.</span></span> <span data-ttu-id="5aeb9-113">機能または設定の監査モードを有効にし、完全に有効にした場合の動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-113">You can enable audit mode for features or settings, and then review what would have happened if they were fully enabled.</span></span>

<span data-ttu-id="5aeb9-114">この記事では、すべてのイベント、関連する機能または設定を一覧表示し、特定のイベントにフィルター処理するカスタム ビューを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-114">This article lists all the events, their associated feature or setting, and describes how to create custom views to filter to specific events.</span></span>

<span data-ttu-id="5aeb9-115">E5 サブスクリプションを持ち、Microsoft Defender for Endpoint を使用している場合は、Windows セキュリティの一部としてイベントやブロックに関する詳細なレポート [を取得します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-115">Get detailed reporting into events and blocks as part of Windows Security if you have an E5 subscription and use [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a><span data-ttu-id="5aeb9-116">カスタム ビューを使用して攻撃表面の縮小機能を確認する</span><span class="sxs-lookup"><span data-stu-id="5aeb9-116">Use custom views to review attack surface reduction capabilities</span></span>

<span data-ttu-id="5aeb9-117">Windows イベント ビューアーでカスタム ビューを作成して、特定の機能と設定のイベントのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-117">Create custom views in the Windows Event Viewer to only see events for specific capabilities and settings.</span></span> <span data-ttu-id="5aeb9-118">最も簡単な方法は、カスタム ビューを XML ファイルとしてインポートすることです。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-118">The easiest way is to import a custom view as an XML file.</span></span> <span data-ttu-id="5aeb9-119">このページから XML を直接コピーできます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-119">You can copy the XML directly from this page.</span></span>

<span data-ttu-id="5aeb9-120">また、機能に対応するイベント領域に手動で移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-120">You can also manually navigate to the event area that corresponds to the feature.</span></span>

### <a name="import-an-existing-xml-custom-view"></a><span data-ttu-id="5aeb9-121">既存の XML カスタム ビューをインポートする</span><span class="sxs-lookup"><span data-stu-id="5aeb9-121">Import an existing XML custom view</span></span>

1. <span data-ttu-id="5aeb9-122">空の .txt ファイルを作成し、使用するカスタム ビューの XML を .txt ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-122">Create an empty .txt file and copy the XML for the custom view you want to use into the .txt file.</span></span> <span data-ttu-id="5aeb9-123">使用するカスタム ビューごとにこれを行います。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-123">Do this for each of the custom views you want to use.</span></span> <span data-ttu-id="5aeb9-124">ファイルの名前を次のように変更します (型を .txt から .xml に変更してください)。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-124">Rename the files as follows (ensure you change the type from .txt to .xml):</span></span>
    - <span data-ttu-id="5aeb9-125">フォルダー アクセス イベントのカスタム ビューの制御: *cfa-events.xml*</span><span class="sxs-lookup"><span data-stu-id="5aeb9-125">Controlled folder access events custom view: *cfa-events.xml*</span></span>
    - <span data-ttu-id="5aeb9-126">エクスプロイト保護イベントのカスタム ビュー: *ep-events.xml*</span><span class="sxs-lookup"><span data-stu-id="5aeb9-126">Exploit protection events custom view: *ep-events.xml*</span></span>
    - <span data-ttu-id="5aeb9-127">攻撃表面の縮小イベントのカスタム ビュー: *asr-events.xml*</span><span class="sxs-lookup"><span data-stu-id="5aeb9-127">Attack surface reduction events custom view: *asr-events.xml*</span></span>
    - <span data-ttu-id="5aeb9-128">ネットワーク/保護イベントのカスタム ビュー: *np-events.xml*</span><span class="sxs-lookup"><span data-stu-id="5aeb9-128">Network/ protection events custom view: *np-events.xml*</span></span>

2. <span data-ttu-id="5aeb9-129">[スタート **] メニューに** イベント ビューアーを入力し、[イベント ビューアー] **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-129">Type **event viewer** in the Start menu and open **Event Viewer**.</span></span>

3. <span data-ttu-id="5aeb9-130">[アクション **の**  >  **インポート] [カスタム ビュー...] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="5aeb9-130">Select **Action** > **Import Custom View...**</span></span>

    ![[Even ビューアー] ウィンドウの左側にあるカスタム ビューのインポートを強調表示するアニメーション](/windows/security/threat-protection/images/events-import)

4. <span data-ttu-id="5aeb9-132">必要なカスタム ビューの XML ファイルを抽出した場所に移動し、選択します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-132">Navigate to where you extracted XML file for the custom view you want and select it.</span></span>

5. <span data-ttu-id="5aeb9-133">[**開く**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-133">Select **Open**.</span></span>

6. <span data-ttu-id="5aeb9-134">その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-134">It will create a custom view that filters to only show the events related to that feature.</span></span>

### <a name="copy-the-xml-directly"></a><span data-ttu-id="5aeb9-135">XML を直接コピーする</span><span class="sxs-lookup"><span data-stu-id="5aeb9-135">Copy the XML directly</span></span>

1. <span data-ttu-id="5aeb9-136">[ **スタート] メニューに** イベント ビューアーを入力し、Windows イベント ビューアー **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-136">Type **event viewer** in the Start menu and open the Windows **Event Viewer**.</span></span>

2. <span data-ttu-id="5aeb9-137">左側のパネルの [アクション] で **、[** カスタム ビューの **作成]を選択します。**</span><span class="sxs-lookup"><span data-stu-id="5aeb9-137">On the left panel, under **Actions**, select **Create Custom View...**</span></span>

    ![イベント ビューアー ウィンドウでカスタム ビューの作成オプションを強調表示するアニメーション](/windows/security/threat-protection/images/events-create)

3. <span data-ttu-id="5aeb9-139">[XML] タブに移動し、[クエリの手動編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-139">Go to the XML tab and select **Edit query manually**.</span></span> <span data-ttu-id="5aeb9-140">XML オプションを使用すると、[フィルター] タブを使用してクエリを編集できないという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-140">You'll see a warning that you can't edit the query using the **Filter** tab if you use the XML option.</span></span> <span data-ttu-id="5aeb9-141">**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-141">Select **Yes**.</span></span>

4. <span data-ttu-id="5aeb9-142">イベントをフィルター処理する機能の XML コードを XML セクションに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-142">Paste the XML code for the feature you want to filter events from into the XML section.</span></span>

5. <span data-ttu-id="5aeb9-143">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-143">Select **OK**.</span></span> <span data-ttu-id="5aeb9-144">フィルターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-144">Specify a name for your filter.</span></span>

6. <span data-ttu-id="5aeb9-145">その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-145">It will create a custom view that filters to only show the events related to that feature.</span></span>

### <a name="xml-for-attack-surface-reduction-rule-events"></a><span data-ttu-id="5aeb9-146">攻撃表面の縮小ルール イベントの XML</span><span class="sxs-lookup"><span data-stu-id="5aeb9-146">XML for attack surface reduction rule events</span></span>

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a><span data-ttu-id="5aeb9-147">フォルダー アクセスイベントを制御するための XML</span><span class="sxs-lookup"><span data-stu-id="5aeb9-147">XML for controlled folder access events</span></span>

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a><span data-ttu-id="5aeb9-148">エクスプロイト保護イベントの XML</span><span class="sxs-lookup"><span data-stu-id="5aeb9-148">XML for exploit protection events</span></span>

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a><span data-ttu-id="5aeb9-149">ネットワーク保護イベントの XML</span><span class="sxs-lookup"><span data-stu-id="5aeb9-149">XML for network protection events</span></span>

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a><span data-ttu-id="5aeb9-150">攻撃表面の縮小イベントの一覧</span><span class="sxs-lookup"><span data-stu-id="5aeb9-150">List of attack surface reduction events</span></span>

<span data-ttu-id="5aeb9-151">すべての攻撃表面の縮小イベントは、[アプリケーションとサービス ログ] > **Microsoft > Windows** の下にあり、次の表に示すフォルダーまたはプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-151">All attack surface reduction events are located under **Applications and Services Logs > Microsoft > Windows** and then the folder or provider as listed in the following table.</span></span>

<span data-ttu-id="5aeb9-152">Windows イベント ビューアーで次のイベントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-152">You can access these events in Windows Event viewer:</span></span>

1. <span data-ttu-id="5aeb9-153">[スタート] **メニューを** 開き、イベント **ビューアーと入力** し、イベント ビューアーの **結果を選択** します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-153">Open the **Start** menu and type **event viewer**, and then select the **Event Viewer** result.</span></span>
2. <span data-ttu-id="5aeb9-154">[ **アプリケーションとサービス** ログ] > Microsoft > Windows を展開し、次の表の [プロバイダー **/** ソース] の一覧にあるフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-154">Expand **Applications and Services Logs > Microsoft > Windows** and then go to the folder listed under **Provider/source** in the table below.</span></span>
3. <span data-ttu-id="5aeb9-155">サブアイテムをダブルクリックすると、イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-155">Double-click on the sub item to see events.</span></span> <span data-ttu-id="5aeb9-156">イベントをスクロールして、探しているイベントを見つける。</span><span class="sxs-lookup"><span data-stu-id="5aeb9-156">Scroll through the events to find the one you're looking.</span></span>

   ![イベント ビューアーを使用したアニメーションの表示](/windows/security/threat-protection/images/event-viewer)

<span data-ttu-id="5aeb9-158">機能</span><span class="sxs-lookup"><span data-stu-id="5aeb9-158">Feature</span></span> | <span data-ttu-id="5aeb9-159">プロバイダー/ソース</span><span class="sxs-lookup"><span data-stu-id="5aeb9-159">Provider/source</span></span> | <span data-ttu-id="5aeb9-160">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5aeb9-160">Event ID</span></span> | <span data-ttu-id="5aeb9-161">説明</span><span class="sxs-lookup"><span data-stu-id="5aeb9-161">Description</span></span>
:-|:-|:-:|:-
<span data-ttu-id="5aeb9-162">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-162">Exploit protection</span></span> | <span data-ttu-id="5aeb9-163">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-163">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-164">1</span><span class="sxs-lookup"><span data-stu-id="5aeb9-164">1</span></span> | <span data-ttu-id="5aeb9-165">ACG 監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-165">ACG audit</span></span>
<span data-ttu-id="5aeb9-166">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-166">Exploit protection</span></span> | <span data-ttu-id="5aeb9-167">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-167">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-168">2</span><span class="sxs-lookup"><span data-stu-id="5aeb9-168">2</span></span> | <span data-ttu-id="5aeb9-169">ACG の強制</span><span class="sxs-lookup"><span data-stu-id="5aeb9-169">ACG enforce</span></span>
<span data-ttu-id="5aeb9-170">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-170">Exploit protection</span></span> | <span data-ttu-id="5aeb9-171">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-171">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-172">3</span><span class="sxs-lookup"><span data-stu-id="5aeb9-172">3</span></span> | <span data-ttu-id="5aeb9-173">子プロセスの監査を許可しない</span><span class="sxs-lookup"><span data-stu-id="5aeb9-173">Do not allow child processes audit</span></span>
<span data-ttu-id="5aeb9-174">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-174">Exploit protection</span></span> | <span data-ttu-id="5aeb9-175">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-175">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-176">4</span><span class="sxs-lookup"><span data-stu-id="5aeb9-176">4</span></span> | <span data-ttu-id="5aeb9-177">子プロセスブロックを許可しない</span><span class="sxs-lookup"><span data-stu-id="5aeb9-177">Do not allow child processes block</span></span>
<span data-ttu-id="5aeb9-178">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-178">Exploit protection</span></span> | <span data-ttu-id="5aeb9-179">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-179">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-180">5</span><span class="sxs-lookup"><span data-stu-id="5aeb9-180">5</span></span> | <span data-ttu-id="5aeb9-181">低整合性イメージの監査をブロックする</span><span class="sxs-lookup"><span data-stu-id="5aeb9-181">Block low integrity images audit</span></span>
<span data-ttu-id="5aeb9-182">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-182">Exploit protection</span></span> | <span data-ttu-id="5aeb9-183">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-183">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-184">6</span><span class="sxs-lookup"><span data-stu-id="5aeb9-184">6</span></span> | <span data-ttu-id="5aeb9-185">低整合性イメージ ブロックをブロックする</span><span class="sxs-lookup"><span data-stu-id="5aeb9-185">Block low integrity images block</span></span>
<span data-ttu-id="5aeb9-186">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-186">Exploit protection</span></span> | <span data-ttu-id="5aeb9-187">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-187">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-188">7</span><span class="sxs-lookup"><span data-stu-id="5aeb9-188">7</span></span> | <span data-ttu-id="5aeb9-189">リモート イメージの監査をブロックする</span><span class="sxs-lookup"><span data-stu-id="5aeb9-189">Block remote images audit</span></span>
<span data-ttu-id="5aeb9-190">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-190">Exploit protection</span></span> | <span data-ttu-id="5aeb9-191">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-191">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-192">8</span><span class="sxs-lookup"><span data-stu-id="5aeb9-192">8</span></span> | <span data-ttu-id="5aeb9-193">[リモート イメージのブロック] ブロック</span><span class="sxs-lookup"><span data-stu-id="5aeb9-193">Block remote images block</span></span>
<span data-ttu-id="5aeb9-194">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-194">Exploit protection</span></span> | <span data-ttu-id="5aeb9-195">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-195">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-196">9</span><span class="sxs-lookup"><span data-stu-id="5aeb9-196">9</span></span> | <span data-ttu-id="5aeb9-197">win32k システム呼び出しの監査を無効にする</span><span class="sxs-lookup"><span data-stu-id="5aeb9-197">Disable win32k system calls audit</span></span>
<span data-ttu-id="5aeb9-198">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-198">Exploit protection</span></span> | <span data-ttu-id="5aeb9-199">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-199">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-200">10</span><span class="sxs-lookup"><span data-stu-id="5aeb9-200">10</span></span> | <span data-ttu-id="5aeb9-201">win32k システム呼び出しブロックを無効にする</span><span class="sxs-lookup"><span data-stu-id="5aeb9-201">Disable win32k system calls block</span></span>
<span data-ttu-id="5aeb9-202">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-202">Exploit protection</span></span> | <span data-ttu-id="5aeb9-203">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-203">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-204">11</span><span class="sxs-lookup"><span data-stu-id="5aeb9-204">11</span></span> | <span data-ttu-id="5aeb9-205">コード整合性ガードの監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-205">Code integrity guard audit</span></span>
<span data-ttu-id="5aeb9-206">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-206">Exploit protection</span></span> | <span data-ttu-id="5aeb9-207">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-207">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-208">12 </span><span class="sxs-lookup"><span data-stu-id="5aeb9-208">12</span></span> | <span data-ttu-id="5aeb9-209">コード整合性ガード ブロック</span><span class="sxs-lookup"><span data-stu-id="5aeb9-209">Code integrity guard block</span></span>
<span data-ttu-id="5aeb9-210">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-210">Exploit protection</span></span> | <span data-ttu-id="5aeb9-211">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-211">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-212">13</span><span class="sxs-lookup"><span data-stu-id="5aeb9-212">13</span></span> | <span data-ttu-id="5aeb9-213">EAF 監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-213">EAF audit</span></span>
<span data-ttu-id="5aeb9-214">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-214">Exploit protection</span></span> | <span data-ttu-id="5aeb9-215">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-215">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-216">14 </span><span class="sxs-lookup"><span data-stu-id="5aeb9-216">14</span></span> | <span data-ttu-id="5aeb9-217">EAF の強制</span><span class="sxs-lookup"><span data-stu-id="5aeb9-217">EAF enforce</span></span>
<span data-ttu-id="5aeb9-218">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-218">Exploit protection</span></span> | <span data-ttu-id="5aeb9-219">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-219">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-220">15 </span><span class="sxs-lookup"><span data-stu-id="5aeb9-220">15</span></span> | <span data-ttu-id="5aeb9-221">EAF+ 監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-221">EAF+ audit</span></span>
<span data-ttu-id="5aeb9-222">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-222">Exploit protection</span></span> | <span data-ttu-id="5aeb9-223">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-223">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-224">16 </span><span class="sxs-lookup"><span data-stu-id="5aeb9-224">16</span></span> | <span data-ttu-id="5aeb9-225">EAF+ の強制</span><span class="sxs-lookup"><span data-stu-id="5aeb9-225">EAF+ enforce</span></span>
<span data-ttu-id="5aeb9-226">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-226">Exploit protection</span></span> | <span data-ttu-id="5aeb9-227">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-227">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-228">17 </span><span class="sxs-lookup"><span data-stu-id="5aeb9-228">17</span></span> | <span data-ttu-id="5aeb9-229">IAF 監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-229">IAF audit</span></span>
<span data-ttu-id="5aeb9-230">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-230">Exploit protection</span></span> | <span data-ttu-id="5aeb9-231">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-231">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-232">18 </span><span class="sxs-lookup"><span data-stu-id="5aeb9-232">18</span></span> | <span data-ttu-id="5aeb9-233">IAF の強制</span><span class="sxs-lookup"><span data-stu-id="5aeb9-233">IAF enforce</span></span>
<span data-ttu-id="5aeb9-234">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-234">Exploit protection</span></span> | <span data-ttu-id="5aeb9-235">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-235">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-236">19</span><span class="sxs-lookup"><span data-stu-id="5aeb9-236">19</span></span> | <span data-ttu-id="5aeb9-237">ROP StackPivot 監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-237">ROP StackPivot audit</span></span>
<span data-ttu-id="5aeb9-238">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-238">Exploit protection</span></span> | <span data-ttu-id="5aeb9-239">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-239">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-240">20</span><span class="sxs-lookup"><span data-stu-id="5aeb9-240">20</span></span> | <span data-ttu-id="5aeb9-241">ROP StackPivot の強制</span><span class="sxs-lookup"><span data-stu-id="5aeb9-241">ROP StackPivot enforce</span></span>
<span data-ttu-id="5aeb9-242">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-242">Exploit protection</span></span> | <span data-ttu-id="5aeb9-243">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-243">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-244"> 21</span><span class="sxs-lookup"><span data-stu-id="5aeb9-244">21</span></span> | <span data-ttu-id="5aeb9-245">ROP CallerCheck 監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-245">ROP CallerCheck audit</span></span>
<span data-ttu-id="5aeb9-246">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-246">Exploit protection</span></span> | <span data-ttu-id="5aeb9-247">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-247">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-248">22</span><span class="sxs-lookup"><span data-stu-id="5aeb9-248">22</span></span> | <span data-ttu-id="5aeb9-249">ROP CallerCheck の強制</span><span class="sxs-lookup"><span data-stu-id="5aeb9-249">ROP CallerCheck enforce</span></span>
<span data-ttu-id="5aeb9-250">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-250">Exploit protection</span></span> | <span data-ttu-id="5aeb9-251">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-251">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-252">23</span><span class="sxs-lookup"><span data-stu-id="5aeb9-252">23</span></span> | <span data-ttu-id="5aeb9-253">ROP SimExec 監査</span><span class="sxs-lookup"><span data-stu-id="5aeb9-253">ROP SimExec audit</span></span>
<span data-ttu-id="5aeb9-254">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-254">Exploit protection</span></span> | <span data-ttu-id="5aeb9-255">Security-Mitigations (カーネル モード/ユーザー モード)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-255">Security-Mitigations (Kernel Mode/User Mode)</span></span> | <span data-ttu-id="5aeb9-256">24</span><span class="sxs-lookup"><span data-stu-id="5aeb9-256">24</span></span> | <span data-ttu-id="5aeb9-257">ROP SimExec の強制</span><span class="sxs-lookup"><span data-stu-id="5aeb9-257">ROP SimExec enforce</span></span>
<span data-ttu-id="5aeb9-258">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-258">Exploit protection</span></span> | <span data-ttu-id="5aeb9-259">WER-Diagnostics</span><span class="sxs-lookup"><span data-stu-id="5aeb9-259">WER-Diagnostics</span></span> | <span data-ttu-id="5aeb9-260">5</span><span class="sxs-lookup"><span data-stu-id="5aeb9-260">5</span></span> | <span data-ttu-id="5aeb9-261">CFG ブロック</span><span class="sxs-lookup"><span data-stu-id="5aeb9-261">CFG Block</span></span>
<span data-ttu-id="5aeb9-262">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-262">Exploit protection</span></span> | <span data-ttu-id="5aeb9-263">Win32K (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-263">Win32K (Operational)</span></span> | <span data-ttu-id="5aeb9-264">260</span><span class="sxs-lookup"><span data-stu-id="5aeb9-264">260</span></span> | <span data-ttu-id="5aeb9-265">信頼されていないフォント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-265">Untrusted Font</span></span>
<span data-ttu-id="5aeb9-266">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-266">Network protection</span></span> | <span data-ttu-id="5aeb9-267">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-267">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-268">5007</span><span class="sxs-lookup"><span data-stu-id="5aeb9-268">5007</span></span> | <span data-ttu-id="5aeb9-269">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-269">Event when settings are changed</span></span>
<span data-ttu-id="5aeb9-270">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-270">Network protection</span></span> | <span data-ttu-id="5aeb9-271">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-271">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-272">1125</span><span class="sxs-lookup"><span data-stu-id="5aeb9-272">1125</span></span> | <span data-ttu-id="5aeb9-273">監査モードでネットワーク保護が発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-273">Event when Network protection fires in Audit-mode</span></span>
<span data-ttu-id="5aeb9-274">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="5aeb9-274">Network protection</span></span> | <span data-ttu-id="5aeb9-275">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-275">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-276">1126</span><span class="sxs-lookup"><span data-stu-id="5aeb9-276">1126</span></span> | <span data-ttu-id="5aeb9-277">ブロック モードでネットワーク保護が発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-277">Event when Network protection fires in Block-mode</span></span>
<span data-ttu-id="5aeb9-278">フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="5aeb9-278">Controlled folder access</span></span> | <span data-ttu-id="5aeb9-279">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-279">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-280">5007</span><span class="sxs-lookup"><span data-stu-id="5aeb9-280">5007</span></span> | <span data-ttu-id="5aeb9-281">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-281">Event when settings are changed</span></span>
<span data-ttu-id="5aeb9-282">フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="5aeb9-282">Controlled folder access</span></span> | <span data-ttu-id="5aeb9-283">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-283">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-284">1124</span><span class="sxs-lookup"><span data-stu-id="5aeb9-284">1124</span></span> | <span data-ttu-id="5aeb9-285">監査された制御フォルダー アクセス イベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-285">Audited Controlled folder access event</span></span>
<span data-ttu-id="5aeb9-286">フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="5aeb9-286">Controlled folder access</span></span> | <span data-ttu-id="5aeb9-287">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-287">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-288">1123</span><span class="sxs-lookup"><span data-stu-id="5aeb9-288">1123</span></span> | <span data-ttu-id="5aeb9-289">ブロックされたフォルダー アクセスイベントの制御</span><span class="sxs-lookup"><span data-stu-id="5aeb9-289">Blocked Controlled folder access event</span></span>
<span data-ttu-id="5aeb9-290">フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="5aeb9-290">Controlled folder access</span></span> | <span data-ttu-id="5aeb9-291">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-291">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-292">1127</span><span class="sxs-lookup"><span data-stu-id="5aeb9-292">1127</span></span> | <span data-ttu-id="5aeb9-293">ブロックされたフォルダー アクセスのセクター書き込みブロック イベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-293">Blocked Controlled folder access sector write block event</span></span>
<span data-ttu-id="5aeb9-294">フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="5aeb9-294">Controlled folder access</span></span> | <span data-ttu-id="5aeb9-295">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-295">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-296">1128</span><span class="sxs-lookup"><span data-stu-id="5aeb9-296">1128</span></span> | <span data-ttu-id="5aeb9-297">監査された制御フォルダー アクセス セクター書き込みブロック イベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-297">Audited Controlled folder access sector write block event</span></span>
<span data-ttu-id="5aeb9-298">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="5aeb9-298">Attack surface reduction</span></span> | <span data-ttu-id="5aeb9-299">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-299">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-300">5007</span><span class="sxs-lookup"><span data-stu-id="5aeb9-300">5007</span></span> | <span data-ttu-id="5aeb9-301">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-301">Event when settings are changed</span></span>
<span data-ttu-id="5aeb9-302">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="5aeb9-302">Attack surface reduction</span></span> | <span data-ttu-id="5aeb9-303">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-303">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-304">1122</span><span class="sxs-lookup"><span data-stu-id="5aeb9-304">1122</span></span> | <span data-ttu-id="5aeb9-305">監査モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-305">Event when rule fires in Audit-mode</span></span>
<span data-ttu-id="5aeb9-306">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="5aeb9-306">Attack surface reduction</span></span> | <span data-ttu-id="5aeb9-307">Windows Defender (運用)</span><span class="sxs-lookup"><span data-stu-id="5aeb9-307">Windows Defender (Operational)</span></span> | <span data-ttu-id="5aeb9-308">1121</span><span class="sxs-lookup"><span data-stu-id="5aeb9-308">1121</span></span> | <span data-ttu-id="5aeb9-309">ブロック モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5aeb9-309">Event when rule fires in Block-mode</span></span>