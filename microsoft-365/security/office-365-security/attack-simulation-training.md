---
title: Microsoft Defender を使用したフィッシング攻撃をシミュレートする
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft Defender for Office 365 で、フィッシング攻撃をシミュレートし、フィッシング対策を使用してユーザーをトレーニングする方法について説明します。
ms.openlocfilehash: 8f5f457f60c81fe961282f33bb8c37f4d9e27aab
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616106"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="9db5d-103">フィッシング攻撃をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="9db5d-103">Simulate a phishing attack</span></span>

<span data-ttu-id="9db5d-104">アタックシミュレータのトレーニング Microsoft Defender for Office 365 を使用すると、組織内の危険なサイバー攻撃のシミュレーションを実行して、セキュリティポリシーとプラクティスをテストしたり、組織の従業員をトレーニングして、認識を拡大し、攻撃に対する弱点を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-104">Attack simulator training through Microsoft Defender for Office 365 lets you run benign cyber attack simulations on your organization to test your security policies and practices, as well as train the employees of your organization to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="9db5d-105">次に、攻撃シミュレータトレーニングを使用してフィッシング攻撃をシミュレートする手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-105">The following walks you through simulating a phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9db5d-106">シミュレートされたフィッシング攻撃を開始するには、 [Microsoft 365 セキュリティセンター](https://security.microsoft.com/)に移動します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-106">To launch a simulated phishing attack, navigate to the [Microsoft 365 security center](https://security.microsoft.com/).</span></span> <span data-ttu-id="9db5d-107">[ **電子メール & グループ作業** ] で、[ **アタックシミュレータ** ] をクリックし、[ [**シミュレーション**](https://security.microsoft.com/attacksimulator?viewid=simulations) ] タブに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-107">Under **Email & collaboration** click on **Attack simulator** and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="9db5d-108">[ **シミュレーション** ] **の下で、[シミュレーションの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-108">Under **Simulations** select **+ Launch a simulation**.</span></span>

![Microsoft 365 セキュリティセンターでシミュレーションボタンを起動する](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="9db5d-110">シミュレーションの作成中はいつでも、保存して閉じて、後でシミュレーションの構成を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-110">At any point during simulation creation you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="9db5d-111">ソーシャルエンジニアリング手法の選択</span><span class="sxs-lookup"><span data-stu-id="9db5d-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="9db5d-112">[MITRE ATT&](https://attack.mitre.org/techniques/enterprise/)の合わせの® framework から、4つの異なる手法から選択します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="9db5d-113">さまざまなペイロードをさまざまな方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-113">Different payloads are available for different techniques.</span></span>

- <span data-ttu-id="9db5d-114">**資格** 情報の収集では、ユーザー名とパスワードを送信する入力ボックスを使用して、従業員からの資格情報を既知の参照 web サイトに取り込みます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-114">**Credential harvest** attempts to collect credentials from employees by taking them to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="9db5d-115">**マルウェアの添付ファイル** は、メッセージに悪意のある添付ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="9db5d-116">この添付ファイルを開くと、攻撃者がターゲットのデバイスを侵害する際に役立つ任意のコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-116">When opened, this attachment will run some arbitrary code that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="9db5d-117">**添付ファイルのリンク** は、資格情報ハーベストハイブリッドの種類です。</span><span class="sxs-lookup"><span data-stu-id="9db5d-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="9db5d-118">攻撃者が電子メールの添付ファイルに URL を挿入します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="9db5d-119">添付ファイル内の URL は、資格情報のハーベストと同じ方法に従います。</span><span class="sxs-lookup"><span data-stu-id="9db5d-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="9db5d-120">**マルウェアへのリンク** は、既知のファイル共有サイトでホストされているファイルから任意のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file-sharing site.</span></span> <span data-ttu-id="9db5d-121">この悪意のあるファイルへのリンクが、ターゲットに送信されるメッセージに追加され、それをクリックすると、ファイルが実行され、攻撃者がターゲットのデバイスを侵害することができます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-121">A link to this malicious file is added to the message sent to the target and clicking it will run the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="9db5d-122">各手法の説明内で [ **詳細の表示** ] をクリックすると、その手法に関する詳細情報と、その手法のシミュレーション手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-122">Clicking on **View details** within the description of each technique will display further information about the technique as well as the simulation steps for that technique.</span></span>
>
> ![Microsoft 365 セキュリティセンターの攻撃シミュレーショントレーニングでの資格情報の収集のシミュレーション手順](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="9db5d-124">この方法を選択し、[] をクリックしたら、シミュレーションで名前と説明 **を指定し** ます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-124">Once you've selected the technique and clicked on **Next** give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="9db5d-125">ペイロードの選択</span><span class="sxs-lookup"><span data-stu-id="9db5d-125">Selecting a payload</span></span>

<span data-ttu-id="9db5d-126">次に、既存のペイロードカタログからペイロードを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9db5d-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="9db5d-127">ペイロードには、次の項目を選択するのに役立つさまざまなデータポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="9db5d-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="9db5d-128">**[利率] クリック** すると、このペイロードをクリックしたユーザー数がカウントされます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="9db5d-129">[予測される **侵害率**] Microsoft Defender for Office 365 のお客様について、このペイロードの履歴データに基づいて、このペイロードによって侵害されるユーザーの割合を予測します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historic data for this payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="9db5d-130">**シミュレーションが開始** された数このペイロードが他のシミュレーションで使用された回数。</span><span class="sxs-lookup"><span data-stu-id="9db5d-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="9db5d-131">**フィルター** によって使用可能な **複雑さ** は、ペイロード内のインジケーターの数に基づいて計算されます。これは、攻撃の対象となるターゲットを示すものです。</span><span class="sxs-lookup"><span data-stu-id="9db5d-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="9db5d-132">その他の指標により、複雑さが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="9db5d-133">**ソース**( **フィルター** 経由で利用可能) は、テナントでペイロードが作成されたかどうか、または Microsoft の既存のペイロードカタログ (グローバル) の一部であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 セキュリティセンターでの、アタックシミュレーショントレーニングの選択されたペイロード](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="9db5d-135">リストからペイロードを選択すると、ペイロードのプレビューが追加情報と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="9db5d-136">独自のペイロードを作成したい場合は、「 [アタックシミュレーショントレーニングのペイロードを作成](attack-simulation-training-payloads.md)する」をお読みください。</span><span class="sxs-lookup"><span data-stu-id="9db5d-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="9db5d-137">対象ユーザーの設定</span><span class="sxs-lookup"><span data-stu-id="9db5d-137">Audience targeting</span></span>

<span data-ttu-id="9db5d-138">ここで、このシミュレーションの対象ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="9db5d-139">**組織内のすべてのユーザーを含める** か、**特定のユーザーとグループのみ** を含めるかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="9db5d-140">**特定のユーザーとグループのみを含める** ように選択する場合は、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="9db5d-141">**ユーザーを追加** します。これにより、テナントの検索や、過去3か月間にシミュレーションの対象となっていないユーザーを対象にしたユーザーを対象とした、高度な検索とフィルター処理の機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="9db5d-142">![Microsoft 365 セキュリティセンターの攻撃シミュレーショントレーニングでのユーザーフィルタリング](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="9db5d-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="9db5d-143">**CSV からインポート** このシミュレーションでは、あらかじめ定義されたユーザーのセットをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="9db5d-144">トレーニングの割り当て</span><span class="sxs-lookup"><span data-stu-id="9db5d-144">Assigning training</span></span>

<span data-ttu-id="9db5d-145">トレーニングを受けている従業員は、同じような攻撃の影響を受けないため、各シミュレーションに対してトレーニングを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9db5d-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="9db5d-146">トレーニングを割り当てるか、自分でトレーニングコースやモジュールを選択するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="9db5d-147">[ **トレーニング期限日** ] を選択して、従業員が適切な方法でトレーニングを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9db5d-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="9db5d-148">自分でコースとモジュールを選択した場合でも、推奨コンテンツと利用可能なすべてのコースおよびモジュールを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Microsoft 365 セキュリティセンターの攻撃シミュレーショントレーニングで推奨トレーニングを追加する](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="9db5d-150">次の手順では、自分で選択するように選択した場合は、トレーニングを **追加** し、トレーニングランディングページをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9db5d-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="9db5d-151">トレーニングランディングページをプレビューしたり、ヘッダーと本文を変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="9db5d-152">詳細を起動して確認する</span><span class="sxs-lookup"><span data-stu-id="9db5d-152">Launch details and review</span></span>

<span data-ttu-id="9db5d-153">すべての構成が完了したので、このシミュレーションをすぐに開始するか、後でスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="9db5d-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="9db5d-154">このシミュレーションを終了するタイミングも選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9db5d-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="9db5d-155">このシミュレーションとの対話のキャプチャは、選択した時間を過ぎて停止します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="9db5d-156">**地域対応のタイムゾーン配信を有効** にして、地域に基づいて就業時間中に従業員にシミュレートされた攻撃メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="9db5d-157">完了したら、[ **次へ** ] をクリックして、シミュレーションの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="9db5d-158">いずれかのパーツの [ **編集** ] をクリックして戻り、変更が必要な詳細情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="9db5d-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="9db5d-159">完了したら、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9db5d-159">Once done, click **Submit**.</span></span>
