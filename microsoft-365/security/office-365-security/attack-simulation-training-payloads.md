---
title: 攻撃シミュレーショントレーニングのペイロードを作成する
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
description: Microsoft Defender for Office 365 で、攻撃シミュレーショントレーニング用のカスタムペイロードを作成する方法について説明します。
ms.openlocfilehash: ffb5397d9b39a35b4cb8bd0fdb3301cd156896e1
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944594"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="09eaf-103">攻撃シミュレーショントレーニング用のカスタムペイロードを作成する</span><span class="sxs-lookup"><span data-stu-id="09eaf-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="09eaf-104">Microsoft では、さまざまなソーシャルエンジニアリング手法に対して、攻撃シミュレーショントレーニングと組み合わせた堅牢なペイロードカタログを提供しています。</span><span class="sxs-lookup"><span data-stu-id="09eaf-104">Microsoft offer a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="09eaf-105">ただし、組織にとってより適切に機能するカスタムのペイロードを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="09eaf-106">ここでは、Microsoft Defender for Office 365 を使用して、攻撃シミュレーショントレーニングのペイロードを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-106">The following describes how to create a payload in attack simulation training through Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="09eaf-107">[ [専用 **ペイ** ロード] タブ](https://security.microsoft.com/attacksimulator?viewid=payload)または [シミュレーション作成ウィザード](attack-simulation-training.md#selecting-a-payload)内の [ **ペイロードの作成** ] をクリックすると、ペイロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="09eaf-108">ウィザードの最初の手順では、ペイロードの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="09eaf-109">**現在、電子メールのみ利用可能** です。</span><span class="sxs-lookup"><span data-stu-id="09eaf-109">**Currently only email is available**.</span></span>

<span data-ttu-id="09eaf-110">次に、関連する手法を選択します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-110">Next, select an associated technique.</span></span> <span data-ttu-id="09eaf-111">[ソーシャルエンジニアリング手法を選択](attack-simulation-training.md#selecting-a-social-engineering-technique)する方法について詳しくは、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09eaf-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="09eaf-112">次の手順では、ペイロードの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-112">In the next step name your payload.</span></span> <span data-ttu-id="09eaf-113">必要に応じて、説明を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="09eaf-114">ペイロードの構成</span><span class="sxs-lookup"><span data-stu-id="09eaf-114">Configure payload</span></span>

<span data-ttu-id="09eaf-115">ここで、ペイロードを作成します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-115">Now it's time to build your payload.</span></span> <span data-ttu-id="09eaf-116">[ **送信者の詳細** ] セクションに、送信者の名前、電子メールアドレス、電子メールの件名を入力します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-116">Input the sender's name, email and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="09eaf-117">指定されたリストからフィッシング URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="09eaf-118">この URL は、後でメッセージの本文に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="09eaf-119">ペイロードの送信者に対して内部電子メールを選択することができます。この場合、ペイロードは会社の別の従業員からのものとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="09eaf-120">これにより、ペイロードに対する弱点が増加し、内部の脅威のリスクについて従業員を教育することができます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="09eaf-121">ペイロードの作成には、リッチテキストエディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="09eaf-122">事前に作成した電子メールをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-122">You can also import an email you've created beforehand.</span></span> <span data-ttu-id="09eaf-123">電子メールの本文を構造化する際には、 **動的タグ** を利用して、対象の電子メールをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-123">As you structure the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="09eaf-124">[ **フィッシング] リンク** をクリックして、以前選択したフィッシング URL を電子メールの本文に追加します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-124">Click on **Phishing link** to add the previously selected phishing URL into the body of the email.</span></span>

![Microsoft Defender for Office 365 のためのペイロード作成で強調表示されたフィッシングリンクと動的タグ](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="09eaf-126">少し時間を節約するには、 **電子メールメッセージ内のすべてのリンクをフィッシングリンクに置き換える** オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-126">To save yourself some time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="09eaf-127">必要に応じてペイロードの作成が完了したら、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="09eaf-128">インジケーターの追加</span><span class="sxs-lookup"><span data-stu-id="09eaf-128">Adding indicators</span></span>

<span data-ttu-id="09eaf-129">インジケーターを使用すると、従業員が攻撃を仕掛ける際に、今後の攻撃で探すことができる手がかりがわかります。</span><span class="sxs-lookup"><span data-stu-id="09eaf-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="09eaf-130">開始するには、[ **インジケーターの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="09eaf-131">使用するインジケーターをドロップダウンリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="09eaf-132">このリストは、フィッシング電子メールメッセージに表示される最も一般的なヒントを含む合わせです。</span><span class="sxs-lookup"><span data-stu-id="09eaf-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="09eaf-133">選択したら、 **メールの本文から** インジケーターの配置がに設定されていることを確認し、[ **テキストの選択** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="09eaf-134">このインジケーターが表示されるペイロードの部分を選択状態にし、[ **選択] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![メッセージ本文内の強調表示されたテキスト。攻撃シミュレーショントレーニングのインジケーターに追加する](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="09eaf-136">インジケーターを説明するカスタムの説明を追加し、インジケータープレビューフレーム内をクリックして、インジケーターのプレビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="09eaf-137">完了したら、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09eaf-137">Once done, click **Add**.</span></span> <span data-ttu-id="09eaf-138">ペイロードのすべてのインジケーターについて説明するまで、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="09eaf-139">ペイロードの確認</span><span class="sxs-lookup"><span data-stu-id="09eaf-139">Review payload</span></span>

<span data-ttu-id="09eaf-140">ペイロードの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="09eaf-140">You're done building your payload.</span></span> <span data-ttu-id="09eaf-141">次に、詳細を確認して、ペイロードのプレビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="09eaf-142">プレビューには、作成したすべてのインジケーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-142">The preview will include all indicators you've created.</span></span> <span data-ttu-id="09eaf-143">この手順では、ペイロードの各部分を編集できます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="09eaf-144">問題がなければ、ペイロードを **送信** します。</span><span class="sxs-lookup"><span data-stu-id="09eaf-144">Once satisfied, **Submit** your payload.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="09eaf-145">作成したペイロードの **テナント** は、ソースとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="09eaf-145">Payloads you've created will have **Tenant** set as their source.</span></span> <span data-ttu-id="09eaf-146">ペイロードを選択するときは、 **テナント** が除外されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="09eaf-146">When selecting payloads, make sure you don't have **Tenant** filtered out.</span></span>