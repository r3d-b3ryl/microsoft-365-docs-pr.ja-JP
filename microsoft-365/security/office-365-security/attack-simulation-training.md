---
title: Microsoft Defender for Office 365 でフィッシング攻撃をシミュレートする
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft Defender for Office 365 の攻撃シミュレーション トレーニングを使用して、フィッシング攻撃をシミュレートし、ユーザーをフィッシング防止に関するトレーニングを行う方法を学習できます。
ms.openlocfilehash: e7582b1f74266d988ecdf8f6dac49019699e2bc1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794258"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="f8186-103">フィッシング攻撃をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="f8186-103">Simulate a phishing attack</span></span>

<span data-ttu-id="f8186-104">Office 365 向け Microsoft Defender の攻撃シミュレーション トレーニングを使用すると、組織でサイバー攻撃シミュレーションを実行してセキュリティ ポリシーとプラクティスをテストできます。また、従業員の意識を高め、攻撃の影響を受けやすくするよう従業員をトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8186-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="f8186-105">この記事では、攻撃シミュレーション トレーニングを使用してシミュレートされたフィッシング攻撃を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8186-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f8186-106">シミュレートされたフィッシング攻撃を起動するには [、Microsoft 365](https://security.microsoft.com/)セキュリティ センターを開き、[メール **& コラボレーション** 攻撃シミュレーション トレーニング] に移動し、[シミュレーション] タブに切り替 \> えます [](https://security.microsoft.com/attacksimulator?viewid=simulations)。</span><span class="sxs-lookup"><span data-stu-id="f8186-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="f8186-107">[ **シミュレーション] で、[+** シミュレーション **の起動] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8186-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Microsoft 365 セキュリティ センターでシミュレーション ボタンを起動する](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="f8186-109">シミュレーション作成時の任意の時点で、保存して閉じて、後でシミュレーションの構成を続行できます。</span><span class="sxs-lookup"><span data-stu-id="f8186-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="f8186-110">ソーシャル エンジニアリング手法の選択</span><span class="sxs-lookup"><span data-stu-id="f8186-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="f8186-111">MITRE ATT と CK から選&[4](https://attack.mitre.org/techniques/enterprise/)つの®します。</span><span class="sxs-lookup"><span data-stu-id="f8186-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="f8186-112">さまざまな方法で使用できるペイロードは異なります。</span><span class="sxs-lookup"><span data-stu-id="f8186-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="f8186-113">**資格情報の取得** は、ユーザー名とパスワードを送信するための入力ボックスを持つよく知られた外観の Web サイトにユーザーを連れて行き、資格情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="f8186-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="f8186-114">**マルウェアの添付** ファイルは、悪意のある添付ファイルをメッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="f8186-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="f8186-115">ユーザーが添付ファイルを開くと、攻撃者がターゲットのデバイスを侵害するのに役立つ任意のコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f8186-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="f8186-116">**添付ファイル内のリンク** は、資格情報取得ハイブリッドの一種です。</span><span class="sxs-lookup"><span data-stu-id="f8186-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="f8186-117">攻撃者が電子メールの添付ファイルに URL を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f8186-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="f8186-118">添付ファイル内の URL は、資格情報の取得と同じ手法に従います。</span><span class="sxs-lookup"><span data-stu-id="f8186-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="f8186-119">**マルウェアへのリンクは** 、既知のファイル共有サービスでホストされているファイルから任意のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8186-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="f8186-120">ユーザーに送信されたメッセージには、この悪意のあるファイルへのリンクが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8186-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="f8186-121">ファイルを開き、攻撃者がターゲットのデバイスを侵害するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f8186-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="f8186-122">各技法の **説明内の [詳細の** 表示] をクリックすると、詳細な情報と、その手法のシミュレーション手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8186-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Microsoft 365 セキュリティ センターでの攻撃シミュレーション トレーニング内での資格情報取得のシミュレーション手順](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="f8186-124">この手法を選択し、[次へ] をクリックした後、シミュレーションに名前と必要に応じて説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8186-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="f8186-125">ペイロードの選択</span><span class="sxs-lookup"><span data-stu-id="f8186-125">Selecting a payload</span></span>

<span data-ttu-id="f8186-126">次に、既存のペイロード カタログからペイロードを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8186-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="f8186-127">ペイロードには、次の選択に役立つデータ ポイントが多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8186-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="f8186-128">**クリック率** は、このペイロードをクリックしたユーザーの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="f8186-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="f8186-129">**予測された侵害** 率は、365 ユーザーの Microsoft Defender 全体のペイロードの履歴データに基づいて、このペイロードによって侵害されるユーザーの割合Office予測します。</span><span class="sxs-lookup"><span data-stu-id="f8186-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="f8186-130">**起動されたシミュレーションでは** 、このペイロードが他のシミュレーションで使用された回数がカウントされます。</span><span class="sxs-lookup"><span data-stu-id="f8186-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="f8186-131">**フィルターで** 利用できる複雑 **性** は、攻撃の対象となるペイロード内のインジケーターの数に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="f8186-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="f8186-132">インジケーターの数が多い場合、複雑さも低下します。</span><span class="sxs-lookup"><span data-stu-id="f8186-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="f8186-133">**ソース**(フィルター **で使用可能**) は、ペイロードがテナントで作成されたのか、Microsoft の既存のペイロード カタログ (グローバル) の一部なのかを示します。</span><span class="sxs-lookup"><span data-stu-id="f8186-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 セキュリティ センターでの攻撃シミュレーション トレーニングで選択されたペイロード](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="f8186-135">一覧からペイロードを選択すると、ペイロードのプレビューと、そのペイロードに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8186-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="f8186-136">独自のペイロードを作成する場合は、「攻撃シミュレーション トレーニング用のペイロードを作成する」 [をお読みください](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="f8186-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="f8186-137">対象ユーザーの設定</span><span class="sxs-lookup"><span data-stu-id="f8186-137">Audience targeting</span></span>

<span data-ttu-id="f8186-138">次に、このシミュレーションの対象ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8186-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="f8186-139">組織内のすべてのユーザーを **含める** か、特定のユーザーとグループ **のみを含めるか選択できます**。</span><span class="sxs-lookup"><span data-stu-id="f8186-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="f8186-140">特定のユーザーと **グループのみを含める場合は、次** のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8186-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="f8186-141">**ユーザーを** 追加します。これにより、テナントの検索だけでなく、過去 3 か月間シミュレーションの対象にされていないユーザーのターゲット設定などの高度な検索およびフィルター機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f8186-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="f8186-142">![Microsoft 365 セキュリティ センターでの攻撃シミュレーション トレーニングでのユーザー フィルタリング](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="f8186-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="f8186-143">**CSV からインポートすると** 、このシミュレーション用に定義済みの一連のユーザーをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="f8186-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="f8186-144">トレーニングの割り当て</span><span class="sxs-lookup"><span data-stu-id="f8186-144">Assigning training</span></span>

<span data-ttu-id="f8186-145">トレーニングを受ける従業員は同様の攻撃を受けにくいので、シミュレーションごとにトレーニングを割り当てすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f8186-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="f8186-146">自分用にトレーニングを割り当てるか、自分でトレーニング コースとモジュールを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f8186-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="f8186-147">トレーニングの **期限を選択して** 、従業員がトレーニングを適切な時期に終了します。</span><span class="sxs-lookup"><span data-stu-id="f8186-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="f8186-148">自分でコースとモジュールを選択した場合でも、推奨されるコンテンツと利用可能なすべてのコースとモジュールを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f8186-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Microsoft 365 セキュリティ センターでの攻撃シミュレーション トレーニング内での推奨トレーニングの追加](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="f8186-150">次の手順では、自分でトレーニングを選択し、トレーニングランディング ページをカスタマイズする場合は、トレーニングを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8186-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="f8186-151">トレーニングランディング ページをプレビューし、ヘッダーと本文を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f8186-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="f8186-152">起動の詳細とレビュー</span><span class="sxs-lookup"><span data-stu-id="f8186-152">Launch details and review</span></span>

<span data-ttu-id="f8186-153">すべてが構成されたので、このシミュレーションをすぐに起動するか、後日スケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f8186-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="f8186-154">また、このシミュレーションを終了する場合を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8186-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="f8186-155">このシミュレーションの操作は、選択した時間を過ぎた時点でキャプチャを停止します。</span><span class="sxs-lookup"><span data-stu-id="f8186-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="f8186-156">**地域対応のタイムゾーン配信を有効** にして、シミュレートされた攻撃メッセージを、その地域に基づいて勤務時間内に従業員に配信します。</span><span class="sxs-lookup"><span data-stu-id="f8186-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="f8186-157">完了したら、[次へ] **をクリック** し、シミュレーションの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="f8186-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="f8186-158">任意の **パーツの [** 編集] をクリックして戻り、変更が必要な詳細を変更します。</span><span class="sxs-lookup"><span data-stu-id="f8186-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="f8186-159">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f8186-159">Once done, click **Submit**.</span></span>
