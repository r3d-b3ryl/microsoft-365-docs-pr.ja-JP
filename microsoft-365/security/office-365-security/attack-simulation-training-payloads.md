---
title: 攻撃シミュレーション トレーニング用のペイロードを作成する
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Office 365 向け Microsoft Defender で攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する方法について説明します。
ms.openlocfilehash: fbab4825625c33d027ceaa9aa9272c06e286ed61
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794222"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="daee7-103">攻撃シミュレーショントレーニングのカスタム ペイロードを作成する</span><span class="sxs-lookup"><span data-stu-id="daee7-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="daee7-104">Microsoft は、さまざまなソーシャル エンジニアリング技術に対応した堅牢なペイロード カタログを提供し、攻撃シミュレーション トレーニングと組み合わせ可能です。</span><span class="sxs-lookup"><span data-stu-id="daee7-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="daee7-105">ただし、組織に対してより良く機能するカスタム ペイロードを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="daee7-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="daee7-106">この記事では、Microsoft Defender for Office 365 の攻撃シミュレーション トレーニングでペイロードを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="daee7-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="daee7-107">ペイロードを作成するには、専用の [Payloads] タブまたはシミュレーション作成ウィザードで [Create **a** [ **payload]**](https://security.microsoft.com/attacksimulator?viewid=payload) (ペイロードの作成) [をクリックします](attack-simulation-training.md#selecting-a-payload)。</span><span class="sxs-lookup"><span data-stu-id="daee7-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="daee7-108">ウィザードの最初の手順では、ペイロードの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="daee7-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="daee7-109">**現時点では、電子メールのみを利用できます**。</span><span class="sxs-lookup"><span data-stu-id="daee7-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="daee7-110">次に、関連付けられている手法を選択します。</span><span class="sxs-lookup"><span data-stu-id="daee7-110">Next, select an associated technique.</span></span> <span data-ttu-id="daee7-111">技術の詳細については、「ソーシャル エンジニアリング手法の選択 [」を参照してください](attack-simulation-training.md#selecting-a-social-engineering-technique)。</span><span class="sxs-lookup"><span data-stu-id="daee7-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="daee7-112">次の手順では、ペイロードに名前を付けています。</span><span class="sxs-lookup"><span data-stu-id="daee7-112">In the next step name your payload.</span></span> <span data-ttu-id="daee7-113">必要に応じて、説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="daee7-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="daee7-114">ペイロードを構成する</span><span class="sxs-lookup"><span data-stu-id="daee7-114">Configure payload</span></span>

<span data-ttu-id="daee7-115">次に、ペイロードをビルドします。</span><span class="sxs-lookup"><span data-stu-id="daee7-115">Now it's time to build your payload.</span></span> <span data-ttu-id="daee7-116">[送信者の詳細] セクションに、送信者の名前、メール アドレス、メールの件名 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="daee7-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="daee7-117">指定された一覧からフィッシング URL を選ぶ。</span><span class="sxs-lookup"><span data-stu-id="daee7-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="daee7-118">この URL は、後でメッセージの本文に埋め込まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="daee7-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="daee7-119">ペイロードの送信者の内部電子メールを選択すると、ペイロードは会社の別の従業員から送信されたメールとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="daee7-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="daee7-120">これによりペイロードの影響を受けやすくなり、内部の脅威のリスクについて従業員を教育するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="daee7-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="daee7-121">ペイロードを作成するには、リッチ テキスト エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="daee7-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="daee7-122">事前に作成したメールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="daee7-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="daee7-123">メールの本文を作成する場合は、動的タグを利用して、ターゲットに合ったメールをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="daee7-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="daee7-124">[ **フィッシング] リンクを** クリックして、以前に選択したフィッシング URL をメッセージの本文に追加します。</span><span class="sxs-lookup"><span data-stu-id="daee7-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Microsoft Defender for Office 365 のペイロード作成で強調表示されたフィッシング リンクと動的タグ](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="daee7-126">時間を節約するには、電子メール メッセージ内のすべてのリンクをフィッシング リンクに置き換える **オプションをオンに切り替える必要があります**。</span><span class="sxs-lookup"><span data-stu-id="daee7-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="daee7-127">必要に合ったペイロードの作成が完了したら、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="daee7-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="daee7-128">インジケーターの追加</span><span class="sxs-lookup"><span data-stu-id="daee7-128">Adding indicators</span></span>

<span data-ttu-id="daee7-129">インジケーターは、攻撃シミュレーションを通過する従業員が、将来の攻撃で探す手がかりを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="daee7-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="daee7-130">開始するには、[インジケーターの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="daee7-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="daee7-131">ドロップダウン リストから使用するインジケーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="daee7-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="daee7-132">この一覧は、フィッシングメール メッセージに表示される最も一般的な手がかりを含む目的で作成されています。</span><span class="sxs-lookup"><span data-stu-id="daee7-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="daee7-133">選択したら、インジケーターの配置が電子メールの本文からに設定され、[テキストの選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="daee7-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="daee7-134">このインジケーターが表示されるペイロードの部分を強調表示し、[選択] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="daee7-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![攻撃シミュレーション トレーニングのインジケーターに追加するメッセージ本文の強調表示されたテキスト](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="daee7-136">インジケーターを説明するカスタム説明を追加し、インジケータープレビュー フレーム内をクリックしてインジケーターのプレビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="daee7-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="daee7-137">完了したら、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="daee7-137">Once done, click **Add**.</span></span> <span data-ttu-id="daee7-138">ペイロード内のすべてのインジケーターをカバーするまで、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="daee7-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="daee7-139">ペイロードを確認する</span><span class="sxs-lookup"><span data-stu-id="daee7-139">Review payload</span></span>

<span data-ttu-id="daee7-140">ペイロードの作成は完了です。</span><span class="sxs-lookup"><span data-stu-id="daee7-140">You're done building your payload.</span></span> <span data-ttu-id="daee7-141">次に、詳細を確認し、ペイロードのプレビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="daee7-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="daee7-142">プレビューには、作成したインジケーターすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="daee7-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="daee7-143">この手順では、ペイロードの各部分を編集できます。</span><span class="sxs-lookup"><span data-stu-id="daee7-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="daee7-144">問題がなければ、 **ペイロードを** 送信します。</span><span class="sxs-lookup"><span data-stu-id="daee7-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="daee7-145">作成したペイロードには、テナント **が** ソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="daee7-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="daee7-146">ペイロードを選択する場合は、テナントをフィルターで削除しなけれと **します**。</span><span class="sxs-lookup"><span data-stu-id="daee7-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>
