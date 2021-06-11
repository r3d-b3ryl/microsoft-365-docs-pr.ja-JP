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
description: 管理者は、Microsoft Defender で攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する方法をOffice 365。
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878762"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="59066-103">攻撃シミュレーショントレーニングのカスタム ペイロードを作成する</span><span class="sxs-lookup"><span data-stu-id="59066-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="59066-104">**Microsoft** Defender for [Office 365プラン 2 に適用されます](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="59066-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="59066-105">Microsoft は、攻撃シミュレーション トレーニングと組み合わせ、さまざまなソーシャル エンジニアリング手法の堅牢なペイロード カタログを提供しています。</span><span class="sxs-lookup"><span data-stu-id="59066-105">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="59066-106">ただし、組織に合ったカスタム ペイロードを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="59066-106">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="59066-107">この記事では、Microsoft Defender の攻撃シミュレーション トレーニングでペイロードを作成する方法についてOffice 365。</span><span class="sxs-lookup"><span data-stu-id="59066-107">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="59066-108">ペイロードを作成するには、[専用のペイロード]タブまたはシミュレーション作成ウィザードで [ペイロードの作成[] をクリックします](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)</span><span class="sxs-lookup"><span data-stu-id="59066-108">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="59066-109">ウィザードの最初の手順では、ペイロードの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="59066-109">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="59066-110">**現在、電子メールのみを使用できます**。</span><span class="sxs-lookup"><span data-stu-id="59066-110">**Currently, only email is available**.</span></span>

<span data-ttu-id="59066-111">次に、関連付けられた手法を選択します。</span><span class="sxs-lookup"><span data-stu-id="59066-111">Next, select an associated technique.</span></span> <span data-ttu-id="59066-112">技術の詳細については [、「Selecting a social engineering technique 」を参照してください](attack-simulation-training.md#selecting-a-social-engineering-technique)。</span><span class="sxs-lookup"><span data-stu-id="59066-112">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="59066-113">次の手順では、ペイロードに名前を付けています。</span><span class="sxs-lookup"><span data-stu-id="59066-113">In the next step name your payload.</span></span> <span data-ttu-id="59066-114">必要に応じて、説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="59066-114">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="59066-115">ペイロードの構成</span><span class="sxs-lookup"><span data-stu-id="59066-115">Configure payload</span></span>

<span data-ttu-id="59066-116">次に、ペイロードをビルドします。</span><span class="sxs-lookup"><span data-stu-id="59066-116">Now it's time to build your payload.</span></span> <span data-ttu-id="59066-117">[送信者の詳細] セクションに、送信者の名前、電子メール アドレス、および電子メールの件名 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="59066-117">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="59066-118">指定されたリストからフィッシング URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="59066-118">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="59066-119">この URL は、後でメッセージの本文に埋め込まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="59066-119">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="59066-120">ペイロードの送信者に対して内部メールを選択すると、そのペイロードが会社の別の従業員からのメールとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="59066-120">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="59066-121">これにより、ペイロードの影響を受けやすくし、内部の脅威のリスクについて従業員を教育するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="59066-121">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="59066-122">リッチ テキスト エディターを使用してペイロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="59066-122">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="59066-123">事前に作成したメールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="59066-123">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="59066-124">電子メールの本文を作成する場合は、動的タグを利用して、メールをターゲットに合ってカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="59066-124">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="59066-125">[ **フィッシング] リンクをクリック** して、以前に選択したフィッシング URL をメッセージの本文に追加します。</span><span class="sxs-lookup"><span data-stu-id="59066-125">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Microsoft Defender のペイロードの作成で強調表示されているフィッシング リンクと動的Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="59066-127">時間を節約するには、電子メール メッセージ内のすべてのリンクをフィッシング リンクに置き換える **オプションをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="59066-127">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="59066-128">ペイロードの作成が完了したら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="59066-128">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="59066-129">インジケーターの追加</span><span class="sxs-lookup"><span data-stu-id="59066-129">Adding indicators</span></span>

<span data-ttu-id="59066-130">インジケーターは、攻撃シミュレーションを実行する従業員が、将来の攻撃で探す手がかりを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="59066-130">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="59066-131">開始するには、[インジケーターの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="59066-131">To start, click **Add indicator**.</span></span>

<span data-ttu-id="59066-132">ドロップダウン リストから使用するインジケーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="59066-132">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="59066-133">このリストは、フィッシングメール メッセージに表示される最も一般的な手がかりを含むキュアリングされます。</span><span class="sxs-lookup"><span data-stu-id="59066-133">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="59066-134">選択したら、インジケーターの配置が [メールの本文から] に設定され、[テキストの選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="59066-134">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="59066-135">このインジケーターが表示されるペイロードの部分を強調表示し、[選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="59066-135">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![攻撃シミュレーション トレーニングでインジケーターに追加するメッセージ本文の強調表示されたテキスト](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="59066-137">インジケーターを説明するカスタムの説明を追加し、インジケーターのプレビュー フレーム内をクリックすると、インジケーターのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59066-137">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="59066-138">完了したら、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="59066-138">Once done, click **Add**.</span></span> <span data-ttu-id="59066-139">ペイロード内のすべてのインジケーターをカバーするまで、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="59066-139">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="59066-140">ペイロードの確認</span><span class="sxs-lookup"><span data-stu-id="59066-140">Review payload</span></span>

<span data-ttu-id="59066-141">ペイロードの構築は完了です。</span><span class="sxs-lookup"><span data-stu-id="59066-141">You're done building your payload.</span></span> <span data-ttu-id="59066-142">次に、詳細を確認し、ペイロードのプレビューを確認します。</span><span class="sxs-lookup"><span data-stu-id="59066-142">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="59066-143">プレビューには、作成したインジケーターすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="59066-143">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="59066-144">この手順では、ペイロードの各部分を編集できます。</span><span class="sxs-lookup"><span data-stu-id="59066-144">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="59066-145">完了したら、ペイロード **を送信** できます。</span><span class="sxs-lookup"><span data-stu-id="59066-145">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59066-146">作成したペイロードには、テナント **がソース** として含まれます。</span><span class="sxs-lookup"><span data-stu-id="59066-146">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="59066-147">ペイロードを選択する場合は、テナントをフィルター処理しない必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="59066-147">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="59066-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="59066-148">Related links</span></span>

[<span data-ttu-id="59066-149">攻撃シミュレーション トレーニングの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="59066-149">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="59066-150">フィッシング攻撃シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="59066-150">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="59066-151">攻撃シミュレーション トレーニングを通して洞察を得る</span><span class="sxs-lookup"><span data-stu-id="59066-151">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
