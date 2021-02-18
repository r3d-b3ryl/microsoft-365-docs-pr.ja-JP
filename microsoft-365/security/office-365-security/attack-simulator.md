---
title: Microsoft Defender for Office 365 の攻撃シミュレータ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft 365 E5 または microsoft Defender for Office 365 プラン 2 組織で、攻撃シミュレーターを使ってシミュレートされたフィッシング攻撃とパスワード攻撃を実行する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e877900698d033cb99154b31e32fa04ff7d1010
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289583"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c6c07-103">Microsoft Defender for Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="c6c07-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c6c07-104">**Microsoft** Defender for [Office 365 プラン 2 に適用されます](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="c6c07-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="c6c07-105">組織に Microsoft Defender for Office 365 プラン 2 [](office-365-ti.md)(脅威の調査と対応の機能を含む) がある場合は、セキュリティ & コンプライアンス センターの攻撃シミュレータを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="c6c07-106">これらのシミュレートされた攻撃は、実際の攻撃が下線に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="c6c07-107">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6c07-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c07-108">攻撃シミュレータ v1 エクスペリエンスは読み取り専用モードに切り替えられたので、「攻撃シミュレーション トレーニングの使用を開始する」で説明されている攻撃シミュレータートレーニング [に置き換わります](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-108">Attack Simulator v1 experience has been switched to read-only mode and replaced by Attack simulator training that's described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
> <span data-ttu-id="c6c07-109">このサイトから新しいシミュレーションを起動する機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c6c07-109">The ability to launch new simulations from this site has been disabled.</span></span> <span data-ttu-id="c6c07-110">ただし、2021 年 1 月 24 日から 90 日間実行されるシミュレーションのレポートには引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-110">However, you can still access reports for simulations run for a period of 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c6c07-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c6c07-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c6c07-112">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="c6c07-113">攻撃シミュレーターは、脅威管理 **攻撃シミュレーター** \> **で利用できます**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="c6c07-114">Go directly to attack simulator, open <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="c6c07-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="c6c07-115">さまざまな Microsoft 365 サブスクリプションで攻撃シミュレータを利用する方法について詳しくは、Microsoft Defender で Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6c07-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="c6c07-116">組織の管理役割グループまたはセキュリティ管理者 **役割グループ** の **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="c6c07-117">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6c07-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="c6c07-118">攻撃シミュレータでキャンペーンを作成および管理するには、アカウントを多要素認証 (MFA) 用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="c6c07-119">手順については、「多要素認証 [をセットアップする」を参照してください](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-119">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="c6c07-120">フィッシング キャンペーンは、30 日間イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="c6c07-121">キャンペーンの履歴データは、キャンペーンの開始後最大 90 日間利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="c6c07-122">攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-122">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="c6c07-123">詳細については [、Microsoft 365 のデータの場所を参照してください](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-123">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="c6c07-124">攻撃シミュレータに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="c6c07-124">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="c6c07-125">スピア フィッシング キャンペーン</span><span class="sxs-lookup"><span data-stu-id="c6c07-125">Spear phishing campaigns</span></span>

<span data-ttu-id="c6c07-126">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージ内の機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-126">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="c6c07-127">*スピア* フィッシングは、対象の受信者に合わせて特別に調整された、フォーカスされたカスタマイズされたコンテンツを使用する標的型フィッシング攻撃です (通常は、攻撃者による受信者の再調整後)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-127">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="c6c07-128">攻撃シミュレータでは、次の 2 種類のスピア フィッシング キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-128">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="c6c07-129">**スピア フィッシング (資格情報の取得)**: 攻撃は、メッセージ内の URL をクリックする受信者を説得しようとする。</span><span class="sxs-lookup"><span data-stu-id="c6c07-129">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="c6c07-130">リンクをクリックすると、資格情報の入力を求める画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-130">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="c6c07-131">その場合、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-131">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="c6c07-132">これが単なるテストであり、フィッシング メッセージを認識するためのヒントを提供する既定のページ。</span><span class="sxs-lookup"><span data-stu-id="c6c07-132">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシング リンクをクリックして資格情報を入力した場合に表示される情報](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="c6c07-134">指定するカスタム ページ (URL)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-134">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="c6c07-135">**スピア フィッシング (添付ファイル)**: この攻撃は、受信者がメッセージ内の .docx 添付ファイルまたは .pdf 添付ファイルを開く方法を確信させようとします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-135">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="c6c07-136">添付ファイルには、既定のフィッシング リンクと同じコンテンツが含まれているが、最初の文は " で始まります。このメッセージは、最近開いた電子メール メッセージとして \<Display Name\> 表示されます..."。</span><span class="sxs-lookup"><span data-stu-id="c6c07-136">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="c6c07-137">現在、攻撃シミュレータのスピア フィッシング キャンペーンには有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="c6c07-137">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="c6c07-138">スピア フィッシング キャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="c6c07-138">Create a spear phishing campaign</span></span>

<span data-ttu-id="c6c07-139">スピア フィッシング キャンペーンの重要な部分は、対象の受信者に送信される電子メール メッセージの外観です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-139">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="c6c07-140">電子メール メッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-140">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="c6c07-141">**組み込みの電子メール テンプレートを** 使用する : 2 つの組み込みテンプレートを使用 **できます。**</span><span class="sxs-lookup"><span data-stu-id="c6c07-141">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="c6c07-142">キャンペーンを作成して起動するときに、テンプレートのメール プロパティの一部、すべて、またはなしをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="c6c07-143">**再利用可能な電子メール テンプレート** を作成する: メール テンプレートを作成して保存した後、今後のスピア フィッシング キャンペーンで再び使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-143">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="c6c07-144">キャンペーンを作成して起動するときに、テンプレートのメール プロパティの一部、すべて、またはなしをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="c6c07-145">**ウィザードで電子メール メッセージを作成** します。スピア フィッシング キャンペーンを作成して起動すると、ウィザードで直接メール メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-145">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="c6c07-146">手順 1 (オプション): カスタム メール テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="c6c07-146">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="c6c07-147">組み込みテンプレートの 1 つを使用する場合や、ウィザードで直接電子メール メッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-147">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="c6c07-148">セキュリティ センターコンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-148">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="c6c07-149">[ **攻撃のシミュレート** ] ページの [スピア フィッシング **(Credentials Harvest)** セクションまたはスピア フィッシング **(添付ファイル)** セクションで、[攻撃の詳細] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-149">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="c6c07-150">テンプレートを作成する場所は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="c6c07-150">It doesn't matter where you create the template.</span></span> <span data-ttu-id="c6c07-151">テンプレートで使用可能なオプションは、どちらの種類のフィッシング攻撃でも同じです。</span><span class="sxs-lookup"><span data-stu-id="c6c07-151">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="c6c07-152">開いた **[攻撃の詳細**] ページの [フィッシング テンプレート]セクションの [テンプレートの作成] 領域で、[新しいテンプレート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-152">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="c6c07-153">フィッシング **テンプレートの構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-153">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="c6c07-154">開始ステップ **で** 、テンプレートの一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-154">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="c6c07-155">電子メールの **詳細の構成手順で** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-155">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="c6c07-156">**差出人 (名前)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="c6c07-156">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="c6c07-157">**差出人 (電子メール)**: 送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="c6c07-157">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="c6c07-158">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、使用可能な URL の 1 つを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-158">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="c6c07-159">これは、ユーザーがクリックする URL です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-159">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="c6c07-160">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="c6c07-160">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > <span data-ttu-id="c6c07-161">URL 評価サービスでは、これらの URL の 1 つ以上が安全でないと識別される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-161">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="c6c07-162">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL の可用性を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-162">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="c6c07-163">**カスタム ランディング ページの URL**: オプションのランディング ページを入力します。ユーザーがフィッシング リンクをクリックして資格情報を入力すると、ユーザーがアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-163">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="c6c07-164">このリンクは、既定のランディング ページを置き換えるリンクです。</span><span class="sxs-lookup"><span data-stu-id="c6c07-164">This link replaces the default landing page.</span></span> <span data-ttu-id="c6c07-165">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-165">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="c6c07-166">**カテゴリ**: 現在、この設定は使用されません (入力した項目は無視されます)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-166">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="c6c07-167">**件名**: 電子 **メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="c6c07-167">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="c6c07-168">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-168">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c6c07-169">電子メール **の作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-169">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="c6c07-170">[電子メール] **タブ** (リッチ HTML エディター) または **[ソース** ] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-170">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="c6c07-171">HTML 形式は、必要に応じて単純または複雑にできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-171">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="c6c07-172">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの操作性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-172">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="c6c07-173">`${username}` は、受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-173">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="c6c07-174">`${loginserverurl}` は、 **前の手順のフィッシング ログイン サーバーの URL** 値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-174">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="c6c07-175">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-175">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="c6c07-176">確認手順で **、[** 完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-176">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="c6c07-177">手順 2: スピア フィッシング キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="c6c07-177">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="c6c07-178">セキュリティ センターコンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-178">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="c6c07-179">[ **攻撃のシミュレート** ] ページで、作成するキャンペーンの種類に基づいて、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-179">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="c6c07-180">スピア **フィッシング (資格情報** の取得) セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細の** 起動攻撃] \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-180">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="c6c07-181">スピア **フィッシング (添付ファイル)** セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-181">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="c6c07-182">フィッシング **攻撃の構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-182">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="c6c07-183">[スタート **] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-183">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="c6c07-184">[名前 **] ボックス** に、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-184">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="c6c07-185">ウィザードの後半 **で電子** メール メッセージを作成するために、[テンプレートの使用] をクリックしない。</span><span class="sxs-lookup"><span data-stu-id="c6c07-185">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="c6c07-186">[ **テンプレートの使用]** をクリックし、組み込みまたはカスタムの電子メール テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-186">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="c6c07-187">テンプレートを選択すると、テンプレートに基づいて [名前] ボックスが自動的に入力されますが、名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-187">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6c07-188">![フィッシングの開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="c6c07-188">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="c6c07-189">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-189">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c6c07-190">[ターゲット **の受信者] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-190">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="c6c07-191">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-191">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="c6c07-192">対象となる各受信者は、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-192">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="c6c07-193">検索条件を **入力せずに [** フィルターと **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-193">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="c6c07-194">[ **インポート]** を **クリックし、[** ファイル のインポート] をクリックして、メール アドレスのコンマ区切り値 (CSV) または行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-194">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="c6c07-195">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-195">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="c6c07-196">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c6c07-197">電子メールの **詳細の構成手順で** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-197">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="c6c07-198">スタート ステップでテンプレートを選択した場合、これらの値の大部分は既に構成済みですが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-198">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="c6c07-199">**差出人 (名前)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="c6c07-199">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="c6c07-200">**差出人 (電子メール)**: 送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="c6c07-200">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="c6c07-201">組織のメール ドメインから実際のメール アドレスまたは偽のメール アドレスを入力するか、実際のメール アドレスまたは偽の外部メール アドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-201">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="c6c07-202">組織からの有効な送信者の電子メール アドレスは、実際には受信者の電子メール クライアントで解決されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-202">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="c6c07-203">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、使用可能な URL の 1 つを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-203">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="c6c07-204">これは、ユーザーがクリックする URL です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-204">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="c6c07-205">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="c6c07-205">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="c6c07-206">すべての URL は意図的に http で、https ではありません。</span><span class="sxs-lookup"><span data-stu-id="c6c07-206">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="c6c07-207">URL 評価サービスでは、これらの URL の 1 つ以上が安全でないと識別される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-207">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="c6c07-208">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL の可用性を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-208">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="c6c07-209">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-209">You are required to select a URL.</span></span> <span data-ttu-id="c6c07-210">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合は、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれる)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-210">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="c6c07-211">**添付ファイル** の種類 : この設定は、スピア フィッシング **(添付ファイル) キャンペーン** でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-211">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="c6c07-212">ドロップダウンをクリックして選択します **。DOCX** または **.一** 覧の PDF。</span><span class="sxs-lookup"><span data-stu-id="c6c07-212">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="c6c07-213">**添付ファイル名**: この設定は、スピア フィッシング **(添付ファイル) キャンペーン** でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-213">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="c6c07-214">.docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-214">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="c6c07-215">**カスタム ランディング ページの URL**: オプションのランディング ページを入力します。ユーザーがフィッシング リンクをクリックして資格情報を入力すると、ユーザーがアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-215">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="c6c07-216">このリンクは、既定のランディング ページを置き換えるリンクです。</span><span class="sxs-lookup"><span data-stu-id="c6c07-216">This link replaces the default landing page.</span></span> <span data-ttu-id="c6c07-217">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-217">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="c6c07-218">**件名**: 電子 **メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="c6c07-218">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="c6c07-219">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-219">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c6c07-220">電子メール **の作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-220">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="c6c07-221">スタート ステップでテンプレートを選択した場合、メッセージ本文は既に構成済みですが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-221">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="c6c07-222">[電子メール] **タブ** (リッチ HTML エディター) または **[ソース** ] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-222">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="c6c07-223">HTML 形式は、必要に応じて単純または複雑にできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-223">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="c6c07-224">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの操作性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-224">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="c6c07-225">`${username}` は、受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-225">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="c6c07-226">`${loginserverurl}` は、 **フィッシング ログイン サーバーの URL 値を挿入** します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-226">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="c6c07-227">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれるので、リンクのクリックは添付ファイル キャンペーンでは追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-227">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6c07-228">![電子メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="c6c07-228">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="c6c07-229">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-229">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="c6c07-230">[確認 **] 手順で** 、[完了] **をクリックして** キャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-230">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="c6c07-231">フィッシング メッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-231">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="c6c07-232">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="c6c07-232">Password attack campaigns</span></span>

<span data-ttu-id="c6c07-233">パスワード *攻撃は、* 通常、攻撃者が 1 つ以上の有効なユーザー アカウントを特定した後に、組織内のユーザー アカウントのパスワードを推測しようと試みる。</span><span class="sxs-lookup"><span data-stu-id="c6c07-233">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="c6c07-234">攻撃シミュレータでは、次の 2 種類のパスワード攻撃キャンペーンを使用して、ユーザーのパスワードの複雑さをテストできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-234">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="c6c07-235">**ブルート** フォース パスワード (辞書攻撃)  : ブルート フォース攻撃または辞書攻撃では、ユーザー アカウントのパスワードの大きな辞書ファイルを使用し、そのうちの 1 つが機能する (1 つのアカウントに対して多数のパスワード) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-235">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="c6c07-236">パスワードのロックアウトが正しくない場合は、ブルート フォース パスワード攻撃をデターするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-236">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="c6c07-237">辞書攻撃では、1 つ以上のパスワードを指定して (手動で入力するか、アップロードしたファイルに)、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-237">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="c6c07-238">**パスワード スプレー攻撃**: *パスワード* スプレー攻撃では、ユーザー アカウントのリストに対して同じ慎重に考慮されたパスワードを使用します (多くのアカウントに対して 1 つのパスワード)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-238">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="c6c07-239">パスワード スプレー攻撃は、ブルート フォース パスワード攻撃よりも検出が困難です (攻撃者がユーザーの誤ったパスワード ロックアウトを行う危険性なしに数十または数百のアカウントにわたって 1 つのパスワードを試行すると、成功の確率が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-239">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="c6c07-240">パスワード スプレー攻撃では、試用するパスワードを 1 つしか指定できません。また、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-240">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c07-241">攻撃シミュレータのパスワード攻撃は、ユーザー名とパスワードの基本認証要求をエンドポイントに渡すので、他の認証方法 (AD FS、パスワード ハッシュ同期、パススルー、PingFederate など) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-241">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="c6c07-242">MFA が有効になっているユーザーの場合、パスワード攻撃が実際のパスワードを試しても、試行は常に失敗として登録されます (つまり、MFA ユーザーはキャンペーンの **成功** 試行回数に表示されません)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-242">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="c6c07-243">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-243">This is the expected result.</span></span> <span data-ttu-id="c6c07-244">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-244">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="c6c07-245">パスワード攻撃キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="c6c07-245">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="c6c07-246">セキュリティ センターコンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-246">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="c6c07-247">[ **攻撃のシミュレート** ] ページで、作成するキャンペーンの種類に基づいて、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-247">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="c6c07-248">[**ブルート フォース パスワード (辞書攻撃)** ]セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-248">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="c6c07-249">[パスワード スプレー **攻撃] セクションで、[\*\*\*\*攻撃の起動**] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-249">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="c6c07-250">パスワード **攻撃の構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-250">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="c6c07-251">スタートステップ **で** 、キャンペーンの一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-251">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="c6c07-252">[ターゲット **ユーザー] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-252">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="c6c07-253">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-253">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="c6c07-254">対象となる各受信者は、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-254">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="c6c07-255">検索条件を **入力せずに [** フィルターと **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-255">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="c6c07-256">[ **インポート]** を **クリックし、[** ファイル のインポート] をクリックして、メール アドレスのコンマ区切り値 (CSV) または行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-256">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="c6c07-257">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c07-257">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="c6c07-258">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-258">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c6c07-259">[攻撃 **設定の選択** ] 手順で、キャンペーンの種類に基づいて実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-259">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="c6c07-260">**ブルート フォース パスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-260">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="c6c07-261">**パスワードを手動で** 入力する : Enter キーを押 **してパスワード** を追加するボックスにパスワードを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-261">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="c6c07-262">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-262">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="c6c07-263">**辞書ファイルからパスワードを** アップロードする: **[アップロード** ] をクリックして、各行に 1 つのパスワードと空白の最後の行を含む既存のテキスト ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-263">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="c6c07-264">テキスト ファイルのサイズは 10 MB 以下で、30,000 を超えるパスワードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c6c07-264">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="c6c07-265">**パスワード スプレー攻撃**: 攻撃 **ボックスで** 使用するパスワードにパスワードを 1 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-265">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="c6c07-266">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-266">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c6c07-267">[確認 **] 手順で** 、[完了] **をクリックして** キャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-267">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="c6c07-268">指定したパスワードは、指定したユーザーに対して試みされます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-268">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="c6c07-269">キャンペーンの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="c6c07-269">View campaign results</span></span>

<span data-ttu-id="c6c07-270">キャンペーンを起動した後、メインの [シミュレーション攻撃] ページで進行状況と結果 **を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-270">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="c6c07-271">アクティブなキャンペーンには、ステータス バー、完了したパーセンテージの値、および "(完了したユーザー) の数 (合計ユーザー)" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-271">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="c6c07-272">[更新] **ボタンを** クリックすると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-272">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="c6c07-273">[終了] を **クリックして** 、アクティブなキャンペーンを停止できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-273">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="c6c07-274">キャンペーンが完了すると、状態が [攻撃完了] **に変わります**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-274">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="c6c07-275">次のいずれかの操作を行って、キャンペーンの結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-275">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="c6c07-276">メインの [ **シミュレーション攻撃] ページで** 、 **キャンペーンの名前** の下の [レポートの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-276">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="c6c07-277">メインの [ **攻撃のシミュレート** ] ページで、攻撃の種類 **の** セクションの [攻撃の詳細] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6c07-277">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="c6c07-278">[攻撃 **の詳細]** ページが開いたら、[攻撃履歴] セクションでキャンペーン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-278">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="c6c07-279">前の操作のいずれかを実行すると、攻撃の詳細という名前のページ **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-279">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="c6c07-280">キャンペーンの種類ごとにこのページで利用できる情報については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="c6c07-280">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="c6c07-281">スピア フィッシング (Credentials Harvest) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="c6c07-281">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="c6c07-282">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-282">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c6c07-283">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-283">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c6c07-284">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="c6c07-284">**Total users targeted**</span></span>

- <span data-ttu-id="c6c07-285">**成功した試行**: リンクをクリックして資格情報を入力したユーザーの数 *(任意* のユーザー名とパスワードの値)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-285">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="c6c07-286">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-286">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="c6c07-287">**最速の** クリック: キャンペーンの起動後に最初のユーザーがリンクをクリックした時間。</span><span class="sxs-lookup"><span data-stu-id="c6c07-287">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="c6c07-288">**平均クリック** 数 : すべてのユーザーがリンクをクリックした時間の合計を、リンクをクリックしたユーザー数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-288">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="c6c07-289">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="c6c07-289">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="c6c07-290">**最速の資格情報**: キャンペーンの起動後、最初のユーザーが資格情報を入力するためにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="c6c07-290">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="c6c07-291">**Average Credentials**: すべてのユーザーが資格情報を入力するためにかかった時間の合計を、資格情報を入力したユーザーの数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-291">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="c6c07-292">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="c6c07-292">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="c6c07-293">クリックされたリンクと、1 日 **あたりの\*\*\*\*資格情報の** 提供された数値を示す棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="c6c07-293">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="c6c07-294">クリックされたリンク、**指定された資格情報**、キャンペーンの **パーセンテージなし** を示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="c6c07-294">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="c6c07-295">[ **侵害されたユーザー]** セクションには、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-295">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="c6c07-296">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="c6c07-296">The user's email address</span></span>

  - <span data-ttu-id="c6c07-297">リンクをクリックした日時。</span><span class="sxs-lookup"><span data-stu-id="c6c07-297">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="c6c07-298">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c6c07-298">The client IP address.</span></span>

  - <span data-ttu-id="c6c07-299">ユーザーの Windows および Web ブラウザーのバージョンに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="c6c07-299">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="c6c07-300">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-300">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="c6c07-301">スピア フィッシング (添付ファイル) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="c6c07-301">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="c6c07-302">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-302">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c6c07-303">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-303">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c6c07-304">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="c6c07-304">**Total users targeted**</span></span>

- <span data-ttu-id="c6c07-305">**成功した試行**: 添付ファイルを開いた、またはダウンロードして開いたユーザーの数 (プレビューはカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-305">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="c6c07-306">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-306">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="c6c07-307">**最速の添付ファイルの** オープン時間 : キャンペーンの起動後に最初のユーザーが添付ファイルを開くのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="c6c07-307">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="c6c07-308">**平均添付ファイルの** オープン時間 : すべてのユーザーが添付ファイルを開くのにかかった時間の合計を、添付ファイルを開いたユーザー数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="c6c07-308">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="c6c07-309">**添付ファイルを開く** 成功率 : (添付ファイルを開いたユーザーの数) / 対象ユーザーの総数によって計算される **割合**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-309">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="c6c07-310">ブルート フォース パスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="c6c07-310">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="c6c07-311">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-311">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c6c07-312">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-312">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c6c07-313">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="c6c07-313">**Total users targeted**</span></span>

- <span data-ttu-id="c6c07-314">**成功した試行**: 指定されたパスワードのいずれかを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="c6c07-314">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="c6c07-315">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-315">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="c6c07-316">[ **侵害されたユーザー] セクション** には、影響を受けるユーザーの電子メール アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-316">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="c6c07-317">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-317">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="c6c07-318">パスワード スプレー攻撃キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="c6c07-318">Password spray attack campaign results</span></span>

<span data-ttu-id="c6c07-319">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6c07-319">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c6c07-320">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="c6c07-320">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c6c07-321">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="c6c07-321">**Total users targeted**</span></span>

- <span data-ttu-id="c6c07-322">**成功した試行**: 指定されたパスワードを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="c6c07-322">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="c6c07-323">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="c6c07-323">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
