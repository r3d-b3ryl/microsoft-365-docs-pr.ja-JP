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
description: 管理者は、Microsoft 365 E5 または microsoft Defender for Office 365 プラン 2 組織で、攻撃シミュレーターを使用してシミュレートされたフィッシング攻撃とパスワード攻撃を実行する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 824ee04e2fcf0757a7eb32b48246bf1a1c638926
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175892"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f5fd1-103">Microsoft Defender for Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="f5fd1-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f5fd1-104">**Microsoft** Defender for [Office 365 プラン 2 に適用されます](https://go.microsoft.com/fwlink/?linkid=2148715)</span><span class="sxs-lookup"><span data-stu-id="f5fd1-104">**Applies to** [Microsoft Defender for Office 365 plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span></span>

<span data-ttu-id="f5fd1-105">組織に Microsoft Defender for Office 365 プラン 2 [](office-365-ti.md)(脅威の調査と対応の機能を含む) がある場合は、セキュリティ & コンプライアンス センターの攻撃シミュレータを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="f5fd1-106">これらのシミュレートされた攻撃は、実際の攻撃が下線に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="f5fd1-107">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f5fd1-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f5fd1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f5fd1-109">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="f5fd1-110">攻撃シミュレーターは、脅威管理 **攻撃シミュレーター** \> **で利用できます**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="f5fd1-111">Go directly to attack simulator, open <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="f5fd1-111">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="f5fd1-112">さまざまな Microsoft 365 サブスクリプションで攻撃シミュレータを利用する方法について詳しくは、Microsoft Defender で Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="f5fd1-113">組織の管理役割グループ **またはセキュリティ管理者** 役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f5fd1-114">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f5fd1-115">攻撃シミュレータでキャンペーンを作成および管理するには、アカウントを多要素認証 (MFA) 用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="f5fd1-116">手順については、「多要素認証 [をセットアップする」を参照してください](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="f5fd1-117">フィッシング キャンペーンは、30 日間イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-117">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="f5fd1-118">キャンペーンの履歴データは、キャンペーンの開始後最大 90 日間利用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-118">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="f5fd1-119">攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="f5fd1-120">詳細については [、Microsoft 365 のデータの場所を参照してください](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="f5fd1-121">攻撃シミュレータに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="f5fd1-122">スピア フィッシング キャンペーン</span><span class="sxs-lookup"><span data-stu-id="f5fd1-122">Spear phishing campaigns</span></span>

<span data-ttu-id="f5fd1-123">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージ内の機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="f5fd1-124">*スピア* フィッシングは、対象となる受信者に合わせて特別に調整された、フォーカスされたカスタマイズされたコンテンツを使用する標的型フィッシング攻撃です (通常は、攻撃者による受信者の再調整後)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-124">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="f5fd1-125">攻撃シミュレータでは、次の 2 種類のスピア フィッシング キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-125">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="f5fd1-126">**スピア フィッシング (資格情報の取得)**: 攻撃は、メッセージ内の URL をクリックする受信者を説得しようとする。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-126">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="f5fd1-127">リンクをクリックすると、資格情報の入力を求める画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-127">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="f5fd1-128">その場合、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-128">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="f5fd1-129">これが単なるテストであり、フィッシング メッセージを認識するためのヒントを提供する既定のページ。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-129">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシング リンクをクリックして資格情報を入力した場合に表示される情報](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="f5fd1-131">指定するカスタム ページ (URL)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="f5fd1-132">**スピア フィッシング (添付ファイル)**: この攻撃は、受信者がメッセージ内の .docx 添付ファイルまたは .pdf 添付ファイルを開くという確信を与えようとします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="f5fd1-133">添付ファイルには、既定のフィッシング リンクと同じコンテンツが含まれているが、最初の文は" で始まります。このメッセージは、最近開いた電子メール メッセージとして \<Display Name\> 表示されます。..."</span><span class="sxs-lookup"><span data-stu-id="f5fd1-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="f5fd1-134">現在、攻撃シミュレータのスピア フィッシング キャンペーンには有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="f5fd1-135">スピア フィッシング キャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="f5fd1-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="f5fd1-136">スピア フィッシング キャンペーンの重要な部分は、対象の受信者に送信される電子メール メッセージの外観です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="f5fd1-137">電子メール メッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="f5fd1-138">**組み込みの電子メール テンプレートを** 使用する : 2 つの組み込みテンプレートを使用 **できます。**</span><span class="sxs-lookup"><span data-stu-id="f5fd1-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="f5fd1-139">キャンペーンを作成して起動するときに、テンプレートのメール プロパティの一部、すべて、またはなしをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f5fd1-140">**再利用可能な電子** メール テンプレートを作成する: メール テンプレートを作成して保存した後、今後のスピア フィッシング キャンペーンで再び使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="f5fd1-141">キャンペーンを作成して起動するときに、テンプレートのメール プロパティの一部、すべて、またはなしをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f5fd1-142">**ウィザードで電子メール メッセージを作成** します。スピア フィッシング キャンペーンを作成して起動すると、ウィザードで直接メール メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="f5fd1-143">手順 1 (オプション): カスタム メール テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="f5fd1-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="f5fd1-144">組み込みテンプレートの 1 つを使用する場合や、ウィザードで直接電子メール メッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="f5fd1-145">セキュリティ センターコンプライアンス センター&、脅威管理攻撃シミュレーター **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f5fd1-146">[ **攻撃のシミュレート** ] ページの [スピア フィッシング **(Credentials Harvest)** セクションまたはスピア フィッシング **(添付ファイル)** セクションで、[攻撃の詳細] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="f5fd1-147">テンプレートを作成する場所は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="f5fd1-148">テンプレートで使用可能なオプションは、どちらの種類のフィッシング攻撃でも同じです。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="f5fd1-149">開いた **[攻撃の詳細**] ページの [フィッシング テンプレート]セクションの [テンプレートの作成] 領域で、[新しいテンプレート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="f5fd1-150">フィッシング **テンプレートの構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="f5fd1-151">開始ステップ **で** 、テンプレートの一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="f5fd1-152">電子メールの **詳細の構成手順で** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="f5fd1-153">**差出人 (名前)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f5fd1-154">**差出人 (電子メール)**: 送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="f5fd1-155">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、使用可能な URL の 1 つを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f5fd1-156">これは、ユーザーがクリックしたく思う URL です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f5fd1-157">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-157">The choices are:</span></span>

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
     > <span data-ttu-id="f5fd1-158">URL 評価サービスは、これらの URL の 1 つ以上を安全でない URL として識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-158">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f5fd1-159">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL の可用性を確認します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-159">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="f5fd1-160">**カスタム ランディング ページの URL**: オプションのランディング ページを入力します。ユーザーがフィッシング リンクをクリックして資格情報を入力すると、ユーザーがアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-160">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f5fd1-161">このリンクは、既定のランディング ページを置き換えるリンクです。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-161">This link replaces the default landing page.</span></span> <span data-ttu-id="f5fd1-162">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-162">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f5fd1-163">**カテゴリ**: 現在、この設定は使用されません (入力した項目は無視されます)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-163">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="f5fd1-164">**件名**: 電子 **メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-164">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f5fd1-165">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-165">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f5fd1-166">電子メール **の作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-166">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f5fd1-167">[電子メール] **タブ** (リッチ HTML エディター) または **[ソース** ] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f5fd1-168">HTML 形式は、必要に応じて単純にしたり複雑にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-168">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f5fd1-169">画像とテキストを挿入すると、受信者の電子メール クライアントでメッセージの操作性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-169">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f5fd1-170">`${username}` は、受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-170">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f5fd1-171">`${loginserverurl}` は、 **前の手順のフィッシング ログイン サーバーの URL** 値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-171">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="f5fd1-172">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-172">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f5fd1-173">確認手順で **、[** 完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-173">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="f5fd1-174">手順 2: スピア フィッシング キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="f5fd1-174">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="f5fd1-175">セキュリティ センターコンプライアンス センター&、脅威管理攻撃シミュレーター **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-175">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f5fd1-176">[ **攻撃のシミュレート** ] ページで、作成するキャンペーンの種類に基づいて次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-176">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f5fd1-177">スピア **フィッシング (資格情報** の取得) セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細の** 起動攻撃] \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-177">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f5fd1-178">スピア **フィッシング (添付ファイル)** セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-178">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f5fd1-179">フィッシング **攻撃の構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-179">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f5fd1-180">スタートステップ **で** 、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-180">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f5fd1-181">[名前 **] ボックス** に、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-181">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="f5fd1-182">ウィザードの後半 **で電子** メール メッセージを作成するために、[テンプレートの使用] をクリックしない。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-182">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="f5fd1-183">[ **テンプレートの使用]** をクリックし、組み込みまたはカスタムの電子メール テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-183">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="f5fd1-184">テンプレートを選択すると、[名前]ボックスはテンプレートに基づいて自動的に入力されますが、名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-184">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5fd1-185">![フィッシングの開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="f5fd1-185">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="f5fd1-186">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f5fd1-187">[ターゲット **の受信者] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-187">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f5fd1-188">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-188">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f5fd1-189">対象となる各受信者は、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-189">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f5fd1-190">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-190">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f5fd1-191">[ **インポート]** を **クリックし、[** ファイル のインポート] をクリックして、コンマ区切り値 (CSV) または電子メール アドレスの行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-191">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f5fd1-192">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-192">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f5fd1-193">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f5fd1-194">電子メールの **詳細の構成手順で** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-194">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="f5fd1-195">スタート ステップでテンプレートを選択した場合、これらの値の大部分は既に構成済みですが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-195">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="f5fd1-196">**差出人 (名前)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-196">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f5fd1-197">**差出人 (電子メール)**: 送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-197">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="f5fd1-198">組織のメール ドメインから実際のメール アドレスまたは偽のメール アドレスを入力するか、実際のメール アドレスまたは偽の外部メール アドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-198">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="f5fd1-199">組織からの有効な送信者の電子メール アドレスは、実際には受信者の電子メール クライアントで解決されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-199">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="f5fd1-200">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、使用可能な URL の 1 つを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-200">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f5fd1-201">これは、ユーザーがクリックしたく思う URL です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-201">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f5fd1-202">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-202">The choices are:</span></span>

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
     > - <span data-ttu-id="f5fd1-203">すべての URL は意図的に http で、https ではありません。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-203">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="f5fd1-204">URL 評価サービスは、これらの URL の 1 つ以上を安全でない URL として識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-204">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f5fd1-205">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL の可用性を確認します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-205">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="f5fd1-206">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-206">You are required to select a URL.</span></span> <span data-ttu-id="f5fd1-207">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれる)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-207">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="f5fd1-208">**添付ファイル** の種類 : この設定は、スピア フィッシング **(添付ファイル) キャンペーン** でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-208">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f5fd1-209">ドロップダウンをクリックして選択します **。DOCX** または **.一** 覧の PDF。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-209">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="f5fd1-210">**添付ファイル** 名 : この設定は、スピア フィッシング **(添付ファイル) キャンペーンでのみ** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-210">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f5fd1-211">.docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-211">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="f5fd1-212">**カスタム ランディング ページの URL**: オプションのランディング ページを入力します。ユーザーがフィッシング リンクをクリックして資格情報を入力すると、ユーザーがアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-212">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f5fd1-213">このリンクは、既定のランディング ページを置き換えるリンクです。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-213">This link replaces the default landing page.</span></span> <span data-ttu-id="f5fd1-214">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-214">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f5fd1-215">**件名**: 電子 **メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-215">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f5fd1-216">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-216">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f5fd1-217">電子メール **の作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-217">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f5fd1-218">スタート ステップでテンプレートを選択した場合、メッセージ本文は既に構成済みですが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-218">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="f5fd1-219">[電子メール] **タブ** (リッチ HTML エディター) または **[ソース** ] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f5fd1-220">HTML 形式は、必要に応じて単純にしたり複雑にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-220">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f5fd1-221">画像とテキストを挿入すると、受信者の電子メール クライアントでメッセージの操作性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-221">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f5fd1-222">`${username}` は、受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-222">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f5fd1-223">`${loginserverurl}` は、 **フィッシング ログイン サーバーの URL 値を挿入** します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-223">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="f5fd1-224">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれるので、リンクのクリックは添付ファイル キャンペーンでは追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-224">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5fd1-225">![電子メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="f5fd1-225">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="f5fd1-226">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-226">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f5fd1-227">[確認 **] 手順で** 、[完了] **をクリック** してキャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-227">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f5fd1-228">フィッシング メッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-228">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="f5fd1-229">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="f5fd1-229">Password attack campaigns</span></span>

<span data-ttu-id="f5fd1-230">パスワード *攻撃は、* 通常、攻撃者が 1 つ以上の有効なユーザー アカウントを特定した後に、組織内のユーザー アカウントのパスワードを推測しようと試みる。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-230">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="f5fd1-231">攻撃シミュレータでは、次の 2 種類のパスワード攻撃キャンペーンを利用して、ユーザーのパスワードの複雑さをテストできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-231">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="f5fd1-232">**ブルート** フォース パスワード (辞書攻撃)  : ブルート フォース攻撃または辞書攻撃では、ユーザー アカウントのパスワードの大きな辞書ファイルを使用して、そのうちの 1 つが機能します (1 つのアカウントに対して多数のパスワードが使用されます)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-232">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="f5fd1-233">パスワードのロックアウトが間違っている場合は、ブルート フォース パスワード攻撃をデターするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-233">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="f5fd1-234">辞書攻撃では、1 つ以上のパスワードを指定して (手動で入力するか、アップロードしたファイルに)、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-234">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="f5fd1-235">**パスワード スプレー攻撃**: *パスワード* スプレー攻撃では、ユーザー アカウントのリストに対して同じ慎重に考慮されたパスワードを使用します (多くのアカウントに対して 1 つのパスワード)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-235">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="f5fd1-236">パスワード スプレー攻撃は、ブルート フォース パスワード攻撃よりも検出が困難です (攻撃者がユーザーの誤ったパスワード ロックアウトに失敗する危険性なしに数十または数百のアカウントにわたって 1 つのパスワードを試行すると、成功の確率が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-236">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="f5fd1-237">パスワード スプレー攻撃では、試用するパスワードを 1 つしか指定できません。また、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-237">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="f5fd1-238">攻撃シミュレータのパスワード攻撃は、ユーザー名とパスワードの基本認証要求をエンドポイントに渡すので、他の認証方法 (AD FS、パスワード ハッシュ同期、パススルー、PingFederate など) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-238">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="f5fd1-239">MFA が有効になっているユーザーの場合、パスワード攻撃が実際のパスワードを試みる場合でも、試行は常に失敗として登録されます (つまり、MFA ユーザーはキャンペーンの **成功** 試行回数に表示されません)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-239">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="f5fd1-240">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-240">This is the expected result.</span></span> <span data-ttu-id="f5fd1-241">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-241">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="f5fd1-242">パスワード攻撃キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="f5fd1-242">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="f5fd1-243">セキュリティ センターコンプライアンス センター&、脅威管理攻撃シミュレーター **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-243">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f5fd1-244">[ **攻撃のシミュレート** ] ページで、作成するキャンペーンの種類に基づいて次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-244">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f5fd1-245">[**ブルート フォース パスワード (辞書攻撃)** ]セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-245">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f5fd1-246">[パスワード スプレー **攻撃] セクションで、[\*\*\*\*攻撃の起動**] をクリックするか、[**攻撃の詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-246">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f5fd1-247">パスワード **攻撃の構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-247">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f5fd1-248">スタートステップ **で** 、キャンペーンの一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-248">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="f5fd1-249">[ターゲット **ユーザー] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-249">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f5fd1-250">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-250">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f5fd1-251">対象となる各受信者は、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-251">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f5fd1-252">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-252">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f5fd1-253">[ **インポート]** を **クリックし、[** ファイル のインポート] をクリックして、コンマ区切り値 (CSV) または電子メール アドレスの行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-253">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f5fd1-254">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-254">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f5fd1-255">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-255">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f5fd1-256">[攻撃 **設定の選択]** 手順で、キャンペーンの種類に基づいて実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-256">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="f5fd1-257">**ブルート フォース パスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-257">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="f5fd1-258">**パスワードを手動で** 入力する : Enter キーを押 **して** パスワードを追加するボックスにパスワードを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-258">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="f5fd1-259">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-259">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="f5fd1-260">**辞書ファイルからパスワード** をアップロードする: **[アップロード** ] をクリックして、各行に 1 つのパスワードと空白の最後の行を含む既存のテキスト ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-260">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="f5fd1-261">テキスト ファイルのサイズは 10 MB 以下で、30,000 を超えるパスワードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-261">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="f5fd1-262">**パスワード スプレー攻撃**: 攻撃 **ボックスで** 使用するパスワードにパスワードを 1 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-262">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="f5fd1-263">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-263">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f5fd1-264">[確認 **] 手順で** 、[完了] **をクリック** してキャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-264">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f5fd1-265">指定したパスワードは、指定したユーザーに対して試みされます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-265">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="f5fd1-266">キャンペーンの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="f5fd1-266">View campaign results</span></span>

<span data-ttu-id="f5fd1-267">キャンペーンを起動した後、メインの [攻撃のシミュレート] ページで進行状況と結果 **を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-267">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="f5fd1-268">アクティブなキャンペーンには、ステータス バー、完了したパーセンテージの値、および "(完了したユーザー) の数 (合計ユーザー)" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-268">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="f5fd1-269">[更新] **ボタンを** クリックすると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-269">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="f5fd1-270">[終了] を **クリックして** 、アクティブなキャンペーンを停止できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-270">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="f5fd1-271">キャンペーンが完了すると、状態が [攻撃完了] **に変わります**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-271">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="f5fd1-272">次のいずれかの操作を行って、キャンペーンの結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-272">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="f5fd1-273">メインの [ **シミュレーション攻撃] ページで** 、 **キャンペーンの名前** の下の [レポートの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-273">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="f5fd1-274">メインの [**攻撃のシミュレート**]ページで、攻撃の種類のセクションの [攻撃の詳細] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-274">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="f5fd1-275">[攻撃 **の詳細]** ページが開いたら、[攻撃履歴] セクションでキャンペーン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-275">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="f5fd1-276">前の操作のいずれかを実行すると、攻撃の詳細という名前のページ **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-276">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="f5fd1-277">キャンペーンの種類ごとにこのページで利用できる情報については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-277">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="f5fd1-278">スピア フィッシング (Credentials Harvest) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f5fd1-278">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="f5fd1-279">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-279">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f5fd1-280">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-280">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f5fd1-281">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f5fd1-281">**Total users targeted**</span></span>

- <span data-ttu-id="f5fd1-282">**成功した試行**: リンクをクリックして資格情報を入力したユーザーの数 *(任意* のユーザー名とパスワードの値)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-282">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="f5fd1-283">**全体的な成功率**: 対象ユーザーの合計が **成功した回数によって**  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-283">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f5fd1-284">**最速の** クリック: キャンペーンの起動後に最初のユーザーがリンクをクリックした時間。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-284">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="f5fd1-285">**平均クリック** 数 : すべてのユーザーがリンクをクリックした時間の合計を、リンクをクリックしたユーザー数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-285">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="f5fd1-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="f5fd1-287">**最速の資格情報**: キャンペーンの起動後、最初のユーザーが資格情報を入力するためにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-287">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="f5fd1-288">**Average Credentials**: すべてのユーザーが自分の資格情報を入力するためにかかった時間の合計を、資格情報を入力したユーザーの数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-288">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="f5fd1-289">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-289">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="f5fd1-290">クリックされたリンクと資格情報が1 日あたりの数値 **を示す** 棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-290">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="f5fd1-291">クリックされたリンク、**指定された資格情報**、キャンペーンの **パーセンテージなし** を示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-291">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="f5fd1-292">[ **侵害されたユーザー]** セクションには、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-292">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="f5fd1-293">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="f5fd1-293">The user's email address</span></span>

  - <span data-ttu-id="f5fd1-294">リンクをクリックした日時。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-294">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="f5fd1-295">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-295">The client IP address.</span></span>

  - <span data-ttu-id="f5fd1-296">ユーザーの Windows および Web ブラウザーのバージョンに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-296">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="f5fd1-297">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-297">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="f5fd1-298">スピア フィッシング (添付ファイル) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f5fd1-298">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="f5fd1-299">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-299">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f5fd1-300">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-300">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f5fd1-301">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f5fd1-301">**Total users targeted**</span></span>

- <span data-ttu-id="f5fd1-302">**成功した試行**: 添付ファイルを開いた、またはダウンロードして開いたユーザーの数 (プレビューはカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-302">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="f5fd1-303">**全体的な成功率**: 対象ユーザーの合計が **成功した回数によって**  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-303">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f5fd1-304">**最速の添付ファイルの** オープン時間 : キャンペーンの起動後、最初のユーザーが添付ファイルを開くのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-304">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="f5fd1-305">**平均添付ファイルの** オープン時間 : すべてのユーザーが添付ファイルを開くのにかかった時間の合計を、添付ファイルを開いたユーザー数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-305">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="f5fd1-306">**添付ファイルを開く** 成功率 : (添付ファイルを開いたユーザーの数) / 対象ユーザーの総数によって計算される **割合**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-306">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="f5fd1-307">ブルート フォース パスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f5fd1-307">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="f5fd1-308">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-308">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f5fd1-309">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-309">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f5fd1-310">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f5fd1-310">**Total users targeted**</span></span>

- <span data-ttu-id="f5fd1-311">**成功した試行**: 指定したパスワードのいずれかを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-311">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="f5fd1-312">**全体的な成功率**: 対象ユーザーの合計が **成功した回数によって**  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-312">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f5fd1-313">[ **侵害されたユーザー] セクション** には、影響を受けるユーザーの電子メール アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-313">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="f5fd1-314">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-314">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="f5fd1-315">パスワード スプレー攻撃キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f5fd1-315">Password spray attack campaign results</span></span>

<span data-ttu-id="f5fd1-316">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-316">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f5fd1-317">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-317">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f5fd1-318">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f5fd1-318">**Total users targeted**</span></span>

- <span data-ttu-id="f5fd1-319">**成功した試行**: 指定されたパスワードを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-319">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="f5fd1-320">**全体的な成功率**: 対象ユーザーの合計が **成功した回数によって**  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="f5fd1-320">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
