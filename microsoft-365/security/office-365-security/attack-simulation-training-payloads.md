---
title: 攻撃シミュレーション トレーニングのペイロードを作成する
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft Defender で攻撃シミュレーション トレーニング用のカスタム ペイロードを 365 用に作成Officeできます。
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205193"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="6ab6c-103">攻撃シミュレーショントレーニングのカスタム ペイロードを作成する</span><span class="sxs-lookup"><span data-stu-id="6ab6c-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="6ab6c-104">Microsoft は、攻撃シミュレーション トレーニングと組み合わせ、さまざまなソーシャル エンジニアリング手法の堅牢なペイロード カタログを提供しています。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="6ab6c-105">ただし、組織に合ったカスタム ペイロードを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="6ab6c-106">この記事では、365 用 Microsoft Defender での攻撃シミュレーション トレーニングでペイロードを作成するOffice説明します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="6ab6c-107">ペイロードを作成するには、[専用のペイロード]タブまたはシミュレーション作成ウィザードで [ペイロードの作成[] をクリックします](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)</span><span class="sxs-lookup"><span data-stu-id="6ab6c-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="6ab6c-108">ウィザードの最初の手順では、ペイロードの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="6ab6c-109">**現在、電子メールのみを使用できます**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="6ab6c-110">次に、関連付けられた手法を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-110">Next, select an associated technique.</span></span> <span data-ttu-id="6ab6c-111">技術の詳細については [、「Selecting a social engineering technique 」を参照してください](attack-simulation-training.md#selecting-a-social-engineering-technique)。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="6ab6c-112">次の手順では、ペイロードに名前を付けています。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-112">In the next step name your payload.</span></span> <span data-ttu-id="6ab6c-113">必要に応じて、説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="6ab6c-114">ペイロードの構成</span><span class="sxs-lookup"><span data-stu-id="6ab6c-114">Configure payload</span></span>

<span data-ttu-id="6ab6c-115">次に、ペイロードをビルドします。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-115">Now it's time to build your payload.</span></span> <span data-ttu-id="6ab6c-116">[送信者の詳細] セクションに、送信者の名前、電子メール アドレス、および電子メールの件名 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="6ab6c-117">指定されたリストからフィッシング URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="6ab6c-118">この URL は、後でメッセージの本文に埋め込まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="6ab6c-119">ペイロードの送信者に対して内部メールを選択すると、そのペイロードが会社の別の従業員からのメールとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="6ab6c-120">これにより、ペイロードの影響を受けやすくし、内部の脅威のリスクについて従業員を教育するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="6ab6c-121">リッチ テキスト エディターを使用してペイロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="6ab6c-122">事前に作成したメールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="6ab6c-123">電子メールの本文を作成する場合は、動的タグを利用して、メールをターゲットに合ってカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="6ab6c-124">[ **フィッシング] リンクをクリック** して、以前に選択したフィッシング URL をメッセージの本文に追加します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![365 の Microsoft Defender のペイロード作成で強調表示されているフィッシング リンクと動的Office](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="6ab6c-126">時間を節約するには、電子メール メッセージ内のすべてのリンクをフィッシング リンクに置き換える **オプションをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="6ab6c-127">ペイロードの作成が完了したら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="6ab6c-128">インジケーターの追加</span><span class="sxs-lookup"><span data-stu-id="6ab6c-128">Adding indicators</span></span>

<span data-ttu-id="6ab6c-129">インジケーターは、攻撃シミュレーションを実行する従業員が、将来の攻撃で探す手がかりを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="6ab6c-130">開始するには、[インジケーターの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="6ab6c-131">ドロップダウン リストから使用するインジケーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="6ab6c-132">このリストは、フィッシングメール メッセージに表示される最も一般的な手がかりを含むキュアリングされます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="6ab6c-133">選択したら、インジケーターの配置が [メールの本文から] に設定され、[テキストの選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="6ab6c-134">このインジケーターが表示されるペイロードの部分を強調表示し、[選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![攻撃シミュレーション トレーニングでインジケーターに追加するメッセージ本文の強調表示されたテキスト](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="6ab6c-136">インジケーターを説明するカスタムの説明を追加し、インジケーターのプレビュー フレーム内をクリックすると、インジケーターのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="6ab6c-137">完了したら、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-137">Once done, click **Add**.</span></span> <span data-ttu-id="6ab6c-138">ペイロード内のすべてのインジケーターをカバーするまで、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="6ab6c-139">ペイロードの確認</span><span class="sxs-lookup"><span data-stu-id="6ab6c-139">Review payload</span></span>

<span data-ttu-id="6ab6c-140">ペイロードの構築は完了です。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-140">You're done building your payload.</span></span> <span data-ttu-id="6ab6c-141">次に、詳細を確認し、ペイロードのプレビューを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="6ab6c-142">プレビューには、作成したインジケーターすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="6ab6c-143">この手順では、ペイロードの各部分を編集できます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="6ab6c-144">完了したら、ペイロード **を送信** できます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ab6c-145">作成したペイロードには、テナント **がソース** として含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="6ab6c-146">ペイロードを選択する場合は、テナントをフィルター処理しない必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="6ab6c-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="6ab6c-147">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6ab6c-147">Related links</span></span>

[<span data-ttu-id="6ab6c-148">攻撃シミュレーション トレーニングの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6ab6c-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="6ab6c-149">フィッシング攻撃シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="6ab6c-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="6ab6c-150">攻撃シミュレーション トレーニングを通して洞察を得る</span><span class="sxs-lookup"><span data-stu-id="6ab6c-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
