---
title: 実稼働環境で Microsoft Defender の評価Office 365を有効にし、評価、ライセンス認証をアクティブ化する
description: Microsoft Defender for Office365 評価をアクティブ化する手順、試用版ライセンス、MX レコード処理、&ドメインと受信接続の監査を実行します。
keywords: Microsoft 365 Defender試し、Microsoft 365 Defender を試し、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングを評価する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458368"
---
# <a name="enable-the-evaluation-environment"></a><span data-ttu-id="da6a5-104">評価環境を有効にする</span><span class="sxs-lookup"><span data-stu-id="da6a5-104">Enable the evaluation environment</span></span>

<span data-ttu-id="da6a5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="da6a5-105">**Applies to:**</span></span>
- <span data-ttu-id="da6a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da6a5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="da6a5-107">この記事は、Microsoft Defender の評価環境を設定するプロセスの手順[2/3](eval-defender-office-365-overview.md) Office 365。</span><span class="sxs-lookup"><span data-stu-id="da6a5-107">This article is [Step 2 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="da6a5-108">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-office-365-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="da6a5-108">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="da6a5-109">次の手順を使用して、Microsoft Defender の評価を有効にOffice 365。</span><span class="sxs-lookup"><span data-stu-id="da6a5-109">Use the following steps to enable the evaluation for Microsoft Defender for Office 365.</span></span>


![Microsoft Defender 評価環境で Microsoft Defender Office 365を有効にする手順](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [<span data-ttu-id="da6a5-111">手順 1: 試用版ライセンスをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="da6a5-111">Step 1: Activate trial licenses</span></span>](#step-1-activate-trial-licenses)
- [<span data-ttu-id="da6a5-112">手順 2: パブリック MX レコードの監査と確認</span><span class="sxs-lookup"><span data-stu-id="da6a5-112">Step 2: Audit and verify the public MX record</span></span>](#step-2-audit-and-verify-the-public-mx-record)
- [<span data-ttu-id="da6a5-113">手順 3: 承認されたドメインを監査する</span><span class="sxs-lookup"><span data-stu-id="da6a5-113">Step 3: Audit accepted domains</span></span>](#step-3-audit-accepted-domains)
- [<span data-ttu-id="da6a5-114">手順 4: 受信コネクタを監査する</span><span class="sxs-lookup"><span data-stu-id="da6a5-114">Step 4: Audit inbound connectors</span></span>](#step-4-audit-inbound-connectors)
- [<span data-ttu-id="da6a5-115">手順 5: 評価をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="da6a5-115">Step 5: Activate the evaluation</span></span>](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a><span data-ttu-id="da6a5-116">手順 1: 試用版ライセンスをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="da6a5-116">Step 1: Activate trial licenses</span></span>

<span data-ttu-id="da6a5-117">既存の Microsoft Defender にログオンして、Office 365管理ポータルにログオンします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-117">Log on to your existing Microsoft Defender for Office 365 environment or tenant administration portal.</span></span>

1. <span data-ttu-id="da6a5-118">管理ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-118">Navigate to the administration portal.</span></span>
2. <span data-ttu-id="da6a5-119">クイック 起動から [サービスの購入] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-119">Select Purchase Services from the quick launch.</span></span>

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="[サービスの購入] をクリックします。このページのナビゲーション ウィンドウOffice 365。":::

3.  <span data-ttu-id="da6a5-121">下にスクロールして 、[Add-On] セクション (または "Defender") を検索して、Microsoft Defender のプランをOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-121">Scroll down to the Add-On section (or search for "Defender") to locate the Microsoft Defender for Office 365 plans.</span></span>
4.  <span data-ttu-id="da6a5-122">評価するプランの横にある [詳細] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-122">Click Details next the plan you want to evaluate.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="[詳細] ボタンをクリックし、次へをクリックします。":::

5. <span data-ttu-id="da6a5-124">[無料試用版 *の開始] リンクをクリック* します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-124">Click the *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="このパネルの [無料試用版の開始 *ハイパーリンク*] をクリックします。":::

6. <span data-ttu-id="da6a5-126">要求を確認し、[今すぐ試 *す] ボタンをクリック* します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-126">Confirm your request and click the *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="[今すぐ試す] *ボタン *をクリックします。":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a><span data-ttu-id="da6a5-128">手順 2: パブリック MX レコードの監査と確認</span><span class="sxs-lookup"><span data-stu-id="da6a5-128">Step 2: Audit and verify the public MX record</span></span>

<span data-ttu-id="da6a5-129">Microsoft Defender for Office 365を効果的に評価するには、テナントに関連付けられた Exchange Online Protection (EOP) インスタンスを介して受信外部メールを中継することが重要です。</span><span class="sxs-lookup"><span data-stu-id="da6a5-129">To effectively evaluate Microsoft Defender for Office 365, it's important that inbound external email be relayed through the Exchange Online Protection (EOP) instance associated with your tenant.</span></span>

1. <span data-ttu-id="da6a5-130">M365 管理ポータルにログオンし、[ドメイン] 設定を展開します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-130">Log on to the M365 Admin Portal, expand Settings, and select Domains.</span></span>
2. <span data-ttu-id="da6a5-131">確認済みのメール ドメインを選択し、[DNS の管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-131">Select your verified email domain and click Manage DNS.</span></span>
3. <span data-ttu-id="da6a5-132">生成され、EOP テナントに割り当てられた MX レコードをメモします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-132">Make note of the MX record generated and assigned to your EOP tenant.</span></span>
4. <span data-ttu-id="da6a5-133">外部 (パブリック) DNS ゾーンにアクセスし、メール ドメインに関連付けられているプライマリ MX レコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-133">Access your external (public) DNS zone and check the primary MX record associated with your email domain.</span></span>
    - <span data-ttu-id="da6a5-134">*パブリック MX レコードが現在* 割り当てられている EOP アドレス (tenant-com.mail.protection.outlook.com など) と一致する場合は、それ以上のルーティング変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="da6a5-134">*If your public MX record currently matches the assigned EOP address (e.g. tenant-com.mail.protection.outlook.com) then no further routing changes should be required*.</span></span>
    - <span data-ttu-id="da6a5-135">パブリック MX レコードが現在サード パーティまたはオンプレミスの SMTP ゲートウェイに解決されている場合は、追加のルーティング構成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da6a5-135">If your public MX record currently resolves to a third-party or on-premises SMTP gateway then additional routing configurations may be required.</span></span>
    - <span data-ttu-id="da6a5-136">パブリック MX レコードが現在オンプレミスのレコードに解決されているExchange、一部の受信者メールボックスがまだ EXO に移行されていないハイブリッド モデルに存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da6a5-136">If your public MX record currently resolves to on-premises Exchange then you may still be in a hybrid model where some recipient mailbox have not yet been migrated to EXO.</span></span>

## <a name="step-3-audit-accepted-domains"></a><span data-ttu-id="da6a5-137">手順 3: 承認されたドメインを監査する</span><span class="sxs-lookup"><span data-stu-id="da6a5-137">Step 3: Audit accepted domains</span></span>

1. <span data-ttu-id="da6a5-138">管理者ポータルにログオンExchange Online[メール] を選択Flowし、[承諾されたドメイン] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-138">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Accepted Domains.</span></span>
2. <span data-ttu-id="da6a5-139">テナントで追加および検証された承認されたドメインの一覧から、プライマリ メール ドメインのドメインの種類をメモします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-139">From the list of accepted domains that have been added and verified in your tenant, make note of the **domain type** for your primary email domain.</span></span>
    - <span data-ttu-id="da6a5-140">ドメインの種類が [権限] に設定されている場合は、組織のすべての受信者メールボックスが現在、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="da6a5-140">If the domain type is set to ***Authoritative*** then it is assumed all recipient mailboxes for your organization currently reside in Exchange Online.</span></span>
    - <span data-ttu-id="da6a5-141">ドメインの種類が Internal ***Relay*** に設定されている場合、一部の受信者メールボックスがまだオンプレミスに存在するハイブリッド モデルに存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da6a5-141">If the domain type is set to ***Internal Relay*** then you may still be in a hybrid model where some recipient mailboxes still reside on-premises.</span></span>

## <a name="step-4-audit-inbound-connectors"></a><span data-ttu-id="da6a5-142">手順 4: 受信コネクタを監査する</span><span class="sxs-lookup"><span data-stu-id="da6a5-142">Step 4: Audit inbound connectors</span></span>

1. <span data-ttu-id="da6a5-143">[管理者ポータル] Exchange Onlineログオンし、[メール] Flowをクリックし、[コネクタ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-143">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Connectors.</span></span>
2. <span data-ttu-id="da6a5-144">構成済みのコネクタの一覧から、パートナー組織からのエントリをメモし、サード パーティの SMTP ゲートウェイに関連付ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da6a5-144">From the list of configured connectors, make note of any entries which are from **Partner Organization** and may correlate to a third-party SMTP gateway.</span></span>
3. <span data-ttu-id="da6a5-145">構成済みのコネクタの一覧から、ハイブリッド シナリオに残っている可能性がある組織のメール サーバーからというラベルが付いたエントリをメモします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-145">From the list of configured connectors, make note of any entries labeled **From your organization's email server** which may indicate that you are still in hybrid scenario.</span></span>

## <a name="step-5-activate-the-evaluation"></a><span data-ttu-id="da6a5-146">手順 5: 評価をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="da6a5-146">Step 5: Activate the evaluation</span></span>

<span data-ttu-id="da6a5-147">この手順を使用して、Microsoft Defender をアクティブ化し、Office 365評価をMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-147">Use the instructions here to activate your Microsoft Defender for Office 365 evaluation from the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="da6a5-148">ポータルにアクセスできるアカウントを使用してテナントにログオンMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-148">Log on to your tenant with an account that has access to the Microsoft 365 Defender portal.</span></span>
2. <span data-ttu-id="da6a5-149">管理者向け Microsoft Defender の既定のインターフェイスMicrosoft 365 Defender **ポータル** にする (推奨) Office 365選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-149">Choose whether you want to make the **Microsoft 365 Defender portal** your default interface for Microsoft Defender for Office 365 administration (recommended).</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="[設定を有効にする] ボタンをクリックして、管理用に一元管理Microsoft 365 Defenderを使用します。":::

3. <span data-ttu-id="da6a5-151">ナビゲーション メニューから、[メールとコラボレーション] の **下&ポリシーと** ルール *&選択します*。</span><span class="sxs-lookup"><span data-stu-id="da6a5-151">From the navigation menu, select **Policies & Rules** under *Email & Collaboration*.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="[ポリシーとルール] を&する [メール と共同作業] &します。クリックします。":::

4. <span data-ttu-id="da6a5-153">[ポリシー の *設定] &ダッシュボードで* 、[脅威 **ポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="da6a5-153">On the *Policy & Rules* dashboard, click **Threat Policies**.</span></span>

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="[ポリシーとルール] &の図と、脅威ポリシーを示す矢印を示します。次にクリックします。":::

5. <span data-ttu-id="da6a5-155">[その他の *ポリシー] まで下にスクロールし*、[追加ポリシーの Defender を評価 **する] タイルOffice 365** します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-155">Scroll down to *Additional Policies* and select the **Evaluate Defender for Office 365** tile.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="[Eval Defender for Office 365] タイルは、電子メールとコラボレーション ベクターの間で 30 日間&試用です。[クリックスルー] をクリックします。":::

6. <span data-ttu-id="da6a5-157">次に、外部メールを直接送信するかExchange Onlineサード パーティのゲートウェイまたはサービスにルーティングするか選択し、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-157">Now choose whether external email routes to Exchange Online directly, or to a third-party gateway or service, and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365は、メールボックスへのメール送信をExchange Onlineします。メールのルーティング方法の詳細 (メールをルーティングする送信コネクタの名前など) を指定します。EOP (EOP) Exchange Online Protection使用する場合は、コネクタを使用することはできません。3rd-party プロバイダーまたはオンプレミス プロバイダーを使用しているか、EOP のみを使用する場合は、1 つを選択します。":::

7. <span data-ttu-id="da6a5-159">サードパーティゲートウェイを使用する場合は、ドロップダウンからベンダー名を選択し、そのソリューションに関連付けられた受信コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-159">If you use a third-party gateway, select the vendor name from the drop-down along with the inbound connector associated with that solution.</span></span> <span data-ttu-id="da6a5-160">回答を一覧表示した場合は、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6a5-160">When you've listed your answers, click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="このダイアログで、組織で使用しているサードパーティ ベンダー サービスを選択するか、[*Other*] を選択します。次のダイアログ ボックスで、受信コネクタを選択します。次に、[次へ] をクリックします。":::

8. <span data-ttu-id="da6a5-162">設定を確認し、[評価の作成 **] ボタンをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="da6a5-162">Review your settings and click the **Create Evaluation** button.</span></span>

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="このウィンドウには、設定を確認するドロップダウンがあります。必要に応じて、[ルーティングの種類を編集する] へのリンクもクリックできます。準備ができたら、大きな青い [評価の作成] ボタンをクリックします。":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="これで、セットアップが完了しました。このページの青いボタンに「評価に移動」と表示されます。":::      |

## <a name="next-steps"></a><span data-ttu-id="da6a5-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="da6a5-165">Next steps</span></span>

<span data-ttu-id="da6a5-166">手順 3/ 3: Microsoft Defender のパイロットをセットアップして、ユーザーにOffice 365</span><span class="sxs-lookup"><span data-stu-id="da6a5-166">Step 3 of 3: Set up the pilot for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="da6a5-167">[Microsoft Defender for Office 365 の評価[] の概要に戻Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="da6a5-167">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="da6a5-168">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="da6a5-168">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>