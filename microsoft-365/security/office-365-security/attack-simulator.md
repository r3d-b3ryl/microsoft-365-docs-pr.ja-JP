---
title: Microsoft Defender for Office 365 の攻撃シミュレータ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
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
ms.openlocfilehash: 2ffec891f7b1021f3c6c51b003c78aacb0ec0d6a
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794534"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="78845-103">Microsoft Defender for Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="78845-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="78845-104">組織に Microsoft Defender for Office 365 プラン 2 [](office-365-ti.md)(脅威の調査と対応の機能を含む) がある場合は、セキュリティ & コンプライアンス センターの攻撃シミュレータを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="78845-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="78845-105">これらのシミュレートされた攻撃は、実際の攻撃が下線に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="78845-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="78845-106">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78845-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="78845-107">攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="78845-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="78845-108">詳細については [、Microsoft 365 のデータの場所を参照してください](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="78845-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="78845-109">攻撃シミュレーション トレーニングは、Microsoft 365 セキュリティ センターのパブリック プレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="78845-110">詳細については [、「Office 365](attack-simulation-training.md) で Microsoft Defender を使ったフィッシング攻撃をシミュレートする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78845-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="78845-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="78845-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="78845-112">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="78845-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="78845-113">攻撃シミュレーターは、脅威管理 **攻撃シミュレーター** \> **で利用できます**。</span><span class="sxs-lookup"><span data-stu-id="78845-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="78845-114">Go directly to attack simulator, open <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="78845-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="78845-115">さまざまな Microsoft 365 サブスクリプションで攻撃シミュレータを利用する方法について詳しくは、Microsoft Defender で Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78845-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="78845-116">組織の管理役割グループまたはセキュリティ管理者 **役割グループ** の **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="78845-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="78845-117">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78845-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="78845-118">攻撃シミュレータでキャンペーンを作成および管理するには、アカウントを多要素認証 (MFA) 用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78845-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="78845-119">手順については、「多要素認証 [をセットアップする」を参照してください](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="78845-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="78845-120">フィッシング キャンペーンは、30 日間イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="78845-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="78845-121">キャンペーンの履歴データは、キャンペーンの開始後最大 90 日間利用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="78845-122">攻撃シミュレータに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="78845-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="78845-123">スピア フィッシング キャンペーン</span><span class="sxs-lookup"><span data-stu-id="78845-123">Spear phishing campaigns</span></span>

<span data-ttu-id="78845-124">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージ内の機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="78845-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="78845-125">*スピア* フィッシングは、対象となる受信者に合わせて特別に調整された、フォーカスされたカスタマイズされたコンテンツを使用する標的型フィッシング攻撃です (通常は、攻撃者による受信者の再調整後)。</span><span class="sxs-lookup"><span data-stu-id="78845-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="78845-126">攻撃シミュレータでは、次の 2 種類のスピア フィッシング キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="78845-127">**スピア フィッシング (資格情報の取得)**: 攻撃は、メッセージ内の URL をクリックする受信者を説得しようとする。</span><span class="sxs-lookup"><span data-stu-id="78845-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="78845-128">リンクをクリックすると、資格情報の入力を求める画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78845-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="78845-129">その場合、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="78845-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="78845-130">これが単なるテストであり、フィッシング メッセージを認識するためのヒントを提供する既定のページ。</span><span class="sxs-lookup"><span data-stu-id="78845-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシング リンクをクリックして資格情報を入力した場合に表示される情報](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="78845-132">指定するカスタム ページ (URL)。</span><span class="sxs-lookup"><span data-stu-id="78845-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="78845-133">**スピア フィッシング (添付ファイル)**: この攻撃は、受信者がメッセージ内の .docx 添付ファイルまたは .pdf 添付ファイルを開くという確信を与えようとします。</span><span class="sxs-lookup"><span data-stu-id="78845-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="78845-134">添付ファイルには、既定のフィッシング リンクと同じコンテンツが含まれているが、最初の文は " で始まります。このメッセージは、最近開いた電子メール メッセージとして \<Display Name\> 表示されます..."。</span><span class="sxs-lookup"><span data-stu-id="78845-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="78845-135">現在、攻撃シミュレータのスピア フィッシング キャンペーンには有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="78845-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="78845-136">スピア フィッシング キャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="78845-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="78845-137">スピア フィッシング キャンペーンの重要な部分は、対象の受信者に送信される電子メール メッセージの外観です。</span><span class="sxs-lookup"><span data-stu-id="78845-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="78845-138">電子メール メッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="78845-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="78845-139">**組み込みの電子メール テンプレートを** 使用する : 2 つの組み込みテンプレートを使用 **できます。**</span><span class="sxs-lookup"><span data-stu-id="78845-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="78845-140">キャンペーンを作成して起動するときに、テンプレートのメール プロパティの一部、すべて、またはなしをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="78845-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="78845-141">**再利用可能な電子メール テンプレート** を作成する: メール テンプレートを作成して保存した後、今後のスピア フィッシング キャンペーンで再び使用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="78845-142">キャンペーンを作成して起動するときに、テンプレートのメール プロパティの一部、すべて、またはなしをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="78845-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="78845-143">**ウィザードで電子メール メッセージを作成** します。スピア フィッシング キャンペーンを作成して起動すると、ウィザードで直接メール メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="78845-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="78845-144">手順 1 (オプション): カスタム メール テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="78845-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="78845-145">組み込みテンプレートの 1 つを使用する場合や、ウィザードで直接電子メール メッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="78845-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="78845-146">セキュリティ センターコンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="78845-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="78845-147">[ **攻撃のシミュレート** ] ページの [スピア フィッシング **(Credentials Harvest)** セクションまたはスピア フィッシング **(添付ファイル)** セクションで、[攻撃の詳細] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="78845-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="78845-148">テンプレートを作成する場所は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="78845-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="78845-149">テンプレートで使用可能なオプションは、どちらの種類のフィッシング攻撃でも同じです。</span><span class="sxs-lookup"><span data-stu-id="78845-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="78845-150">開いた **[攻撃の詳細**] ページの [フィッシング テンプレート]セクションの [テンプレートの作成] 領域で、[新しいテンプレート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="78845-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="78845-151">フィッシング **テンプレートの構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="78845-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="78845-152">開始ステップ **で** 、テンプレートの一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="78845-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="78845-153">電子メールの **詳細の構成手順で** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="78845-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="78845-154">**差出人 (名前)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="78845-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="78845-155">**差出人 (電子メール)**: 送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="78845-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="78845-156">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、使用可能な URL の 1 つを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="78845-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="78845-157">これは、ユーザーがクリックしたく思う URL です。</span><span class="sxs-lookup"><span data-stu-id="78845-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="78845-158">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="78845-158">The choices are:</span></span>

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
     > <span data-ttu-id="78845-159">URL 評価サービスでは、これらの URL の 1 つ以上が安全でないと識別される場合があります。</span><span class="sxs-lookup"><span data-stu-id="78845-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="78845-160">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL の可用性を確認します。</span><span class="sxs-lookup"><span data-stu-id="78845-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="78845-161">**カスタム ランディング ページの URL**: オプションのランディング ページを入力します。ユーザーがフィッシング リンクをクリックして資格情報を入力すると、ユーザーがアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="78845-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="78845-162">このリンクは、既定のランディング ページを置き換えるリンクです。</span><span class="sxs-lookup"><span data-stu-id="78845-162">This link replaces the default landing page.</span></span> <span data-ttu-id="78845-163">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="78845-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="78845-164">**カテゴリ**: 現在、この設定は使用されません (入力した項目は無視されます)。</span><span class="sxs-lookup"><span data-stu-id="78845-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="78845-165">**件名**: 電子 **メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="78845-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="78845-166">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="78845-167">電子メール **の作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="78845-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="78845-168">[電子メール] **タブ** (リッチ HTML エディター) または **[ソース** ] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="78845-169">HTML 形式は、必要に応じて単純にしたり複雑にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="78845-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="78845-170">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの操作性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="78845-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="78845-171">`${username}` は、受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="78845-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="78845-172">`${loginserverurl}` は、 **前の手順のフィッシング ログイン サーバーの URL** 値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="78845-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="78845-173">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="78845-174">確認手順で **、[** 完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="78845-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="78845-175">手順 2: スピア フィッシング キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="78845-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="78845-176">セキュリティ センターコンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="78845-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="78845-177">[ **攻撃のシミュレート** ] ページで、作成するキャンペーンの種類に基づいて次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="78845-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="78845-178">スピア **フィッシング (資格情報** の取得) セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細の** 起動攻撃] \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="78845-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="78845-179">スピア **フィッシング (添付ファイル)** セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="78845-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="78845-180">フィッシング **攻撃の構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="78845-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="78845-181">[スタート **] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="78845-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="78845-182">[名前 **] ボックス** に、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="78845-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="78845-183">ウィザードの後半 **で電子** メール メッセージを作成するために、[テンプレートの使用] をクリックしない。</span><span class="sxs-lookup"><span data-stu-id="78845-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="78845-184">[ **テンプレートの使用]** をクリックし、組み込みまたはカスタムの電子メール テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="78845-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="78845-185">テンプレートを選択すると、テンプレートに基づいて [名前] ボックスが自動的に入力されますが、名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="78845-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![フィッシングの開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="78845-187">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="78845-188">[ターゲット **の受信者] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="78845-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="78845-189">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="78845-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="78845-190">対象となる各受信者は、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78845-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="78845-191">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="78845-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="78845-192">[ **インポート]** を **クリックし、[** ファイル のインポート] をクリックして、コンマ区切り値 (CSV) または電子メール アドレスの行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="78845-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="78845-193">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78845-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="78845-194">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="78845-195">電子メールの **詳細の構成手順で** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="78845-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="78845-196">スタート ステップでテンプレートを選択した場合、これらの値の大部分は既に構成済みですが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="78845-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="78845-197">**差出人 (名前)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="78845-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="78845-198">**差出人 (電子メール)**: 送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="78845-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="78845-199">組織のメール ドメインから実際のメール アドレスまたは偽のメール アドレスを入力するか、実際のメール アドレスまたは偽の外部メール アドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="78845-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="78845-200">組織からの有効な送信者の電子メール アドレスは、実際には受信者の電子メール クライアントで解決されます。</span><span class="sxs-lookup"><span data-stu-id="78845-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="78845-201">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、使用可能な URL の 1 つを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="78845-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="78845-202">これは、ユーザーがクリックしたく思う URL です。</span><span class="sxs-lookup"><span data-stu-id="78845-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="78845-203">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="78845-203">The choices are:</span></span>

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
     > - <span data-ttu-id="78845-204">すべての URL は意図的に http で、https ではありません。</span><span class="sxs-lookup"><span data-stu-id="78845-204">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="78845-205">URL 評価サービスでは、これらの URL の 1 つ以上が安全でないと識別される場合があります。</span><span class="sxs-lookup"><span data-stu-id="78845-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="78845-206">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL の可用性を確認します。</span><span class="sxs-lookup"><span data-stu-id="78845-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="78845-207">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78845-207">You are required to select a URL.</span></span> <span data-ttu-id="78845-208">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれる)。</span><span class="sxs-lookup"><span data-stu-id="78845-208">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="78845-209">**添付ファイル** の種類 : この設定は、スピア フィッシング **(添付ファイル) キャンペーン** でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="78845-210">ドロップダウンをクリックして選択します **。DOCX** または **.一** 覧の PDF。</span><span class="sxs-lookup"><span data-stu-id="78845-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="78845-211">**添付ファイル名**: この設定は、スピア フィッシング **(添付ファイル) キャンペーン** でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="78845-212">.docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="78845-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="78845-213">**カスタム ランディング ページの URL**: オプションのランディング ページを入力します。ユーザーがフィッシング リンクをクリックして資格情報を入力すると、ユーザーがアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="78845-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="78845-214">このリンクは、既定のランディング ページを置き換えるリンクです。</span><span class="sxs-lookup"><span data-stu-id="78845-214">This link replaces the default landing page.</span></span> <span data-ttu-id="78845-215">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="78845-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="78845-216">**件名**: 電子 **メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="78845-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="78845-217">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="78845-218">電子メール **の作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="78845-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="78845-219">スタート ステップでテンプレートを選択した場合、メッセージ本文は既に構成済みですが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="78845-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="78845-220">[電子メール] **タブ** (リッチ HTML エディター) または **[ソース** ] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="78845-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="78845-221">HTML 形式は、必要に応じて単純にしたり複雑にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="78845-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="78845-222">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの操作性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="78845-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="78845-223">`${username}` は、受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="78845-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="78845-224">`${loginserverurl}` は、 **フィッシング ログイン サーバーの URL 値を挿入** します。</span><span class="sxs-lookup"><span data-stu-id="78845-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="78845-225">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれるので、リンクのクリックは添付ファイル キャンペーンでは追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="78845-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![電子メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="78845-227">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="78845-228">[確認 **] 手順で** 、[完了] **をクリック** してキャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="78845-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="78845-229">フィッシング メッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="78845-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="78845-230">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="78845-230">Password attack campaigns</span></span>

<span data-ttu-id="78845-231">パスワード *攻撃は、* 通常、攻撃者が 1 つ以上の有効なユーザー アカウントを特定した後に、組織内のユーザー アカウントのパスワードを推測しようと試みる。</span><span class="sxs-lookup"><span data-stu-id="78845-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="78845-232">攻撃シミュレータでは、次の 2 種類のパスワード攻撃キャンペーンを使用して、ユーザーのパスワードの複雑さをテストできます。</span><span class="sxs-lookup"><span data-stu-id="78845-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="78845-233">**ブルート** フォース パスワード (辞書攻撃)  : ブルート フォース攻撃または辞書攻撃では、ユーザー アカウントのパスワードの大きな辞書ファイルを使用し、そのうちの 1 つが機能する (1 つのアカウントに対して多数のパスワード) を使用します。</span><span class="sxs-lookup"><span data-stu-id="78845-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="78845-234">パスワードのロックアウトが間違っている場合は、ブルート フォース パスワード攻撃をデターするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="78845-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="78845-235">辞書攻撃では、1 つ以上のパスワードを指定して (手動で入力するか、アップロードしたファイルに)、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="78845-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="78845-236">**パスワード スプレー攻撃**: *パスワード* スプレー攻撃では、ユーザー アカウントのリストに対して同じ慎重に考慮されたパスワードを使用します (多くのアカウントに対して 1 つのパスワード)。</span><span class="sxs-lookup"><span data-stu-id="78845-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="78845-237">パスワード スプレー攻撃は、ブルート フォース パスワード攻撃よりも検出が困難です (攻撃者がユーザーの誤ったパスワード ロックアウトを行う危険性なしに数十または数百のアカウントにわたって 1 つのパスワードを試行すると、成功の確率が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="78845-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="78845-238">パスワード スプレー攻撃では、試用するパスワードを 1 つしか指定できません。また、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="78845-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="78845-239">攻撃シミュレータのパスワード攻撃は、ユーザー名とパスワードの基本認証要求をエンドポイントに渡すので、他の認証方法 (AD FS、パスワード ハッシュ同期、パススルー、PingFederate など) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="78845-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="78845-240">MFA が有効になっているユーザーの場合、パスワード攻撃が実際のパスワードを試しても、試行は常に失敗として登録されます (つまり、MFA ユーザーはキャンペーンの **成功** 試行回数に表示されません)。</span><span class="sxs-lookup"><span data-stu-id="78845-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="78845-241">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="78845-241">This is the expected result.</span></span> <span data-ttu-id="78845-242">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="78845-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="78845-243">パスワード攻撃キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="78845-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="78845-244">セキュリティ センターコンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="78845-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="78845-245">[ **攻撃のシミュレート** ] ページで、作成するキャンペーンの種類に基づいて次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="78845-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="78845-246">[**ブルート フォース パスワード (辞書攻撃)** ]セクションで、[攻撃の起動] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="78845-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="78845-247">[パスワード スプレー **攻撃] セクションで、[\*\*\*\*攻撃の起動**] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="78845-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="78845-248">パスワード **攻撃の構成ウィザードが** 新しいフライアウトで開始されます。</span><span class="sxs-lookup"><span data-stu-id="78845-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="78845-249">スタートステップ **で** 、キャンペーンの一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="78845-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="78845-250">[ターゲット **ユーザー] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="78845-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="78845-251">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="78845-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="78845-252">対象となる各受信者は、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78845-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="78845-253">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="78845-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="78845-254">[ **インポート]** を **クリックし、[** ファイル のインポート] をクリックして、コンマ区切り値 (CSV) または電子メール アドレスの行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="78845-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="78845-255">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78845-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="78845-256">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="78845-257">[攻撃 **設定の選択]** 手順で、キャンペーンの種類に基づいて実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="78845-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="78845-258">**ブルート フォース パスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="78845-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="78845-259">**パスワードを手動で** 入力する : Enter キーを押 **してパスワード** を追加するボックスにパスワードを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="78845-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="78845-260">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="78845-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="78845-261">**辞書ファイルからパスワードを** アップロードする: **[アップロード** ] をクリックして、各行に 1 つのパスワードと空白の最後の行を含む既存のテキスト ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="78845-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="78845-262">テキスト ファイルのサイズは 10 MB 以下で、30,000 を超えるパスワードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="78845-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="78845-263">**パスワード スプレー攻撃**: 攻撃 **ボックスで** 使用するパスワードにパスワードを 1 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="78845-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="78845-264">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="78845-265">[確認 **] 手順で** 、[完了] **をクリック** してキャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="78845-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="78845-266">指定したパスワードは、指定したユーザーに対して試みされます。</span><span class="sxs-lookup"><span data-stu-id="78845-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="78845-267">キャンペーンの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="78845-267">View campaign results</span></span>

<span data-ttu-id="78845-268">キャンペーンを起動した後、メインの [攻撃のシミュレート] ページで進行状況と結果 **を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="78845-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="78845-269">アクティブなキャンペーンには、ステータス バー、完了したパーセンテージの値、および "(完了したユーザー) の数 (合計ユーザー)" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78845-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="78845-270">[更新] **ボタンを** クリックすると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="78845-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="78845-271">[終了] を **クリックして** 、アクティブなキャンペーンを停止できます。</span><span class="sxs-lookup"><span data-stu-id="78845-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="78845-272">キャンペーンが完了すると、状態が [攻撃完了] **に変わります**。</span><span class="sxs-lookup"><span data-stu-id="78845-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="78845-273">次のいずれかの操作を行って、キャンペーンの結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="78845-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="78845-274">メインの [ **シミュレーション攻撃] ページで** 、 **キャンペーンの名前** の下の [レポートの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="78845-275">メインの [ **攻撃のシミュレート** ] ページで、攻撃の種類 **の** セクションの [攻撃の詳細] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78845-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="78845-276">[攻撃 **の詳細]** ページが開いたら、[攻撃履歴] セクションでキャンペーン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="78845-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="78845-277">前の操作のいずれかを実行すると、攻撃の詳細という名前のページ **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="78845-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="78845-278">キャンペーンの種類ごとにこのページで利用できる情報については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="78845-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="78845-279">スピア フィッシング (Credentials Harvest) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="78845-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="78845-280">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="78845-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="78845-281">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="78845-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="78845-282">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="78845-282">**Total users targeted**</span></span>

- <span data-ttu-id="78845-283">**成功した試行**: リンクをクリックして資格情報を入力したユーザーの数 *(任意* のユーザー名とパスワードの値)。</span><span class="sxs-lookup"><span data-stu-id="78845-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="78845-284">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="78845-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="78845-285">**最速の** クリック: キャンペーンの起動後に最初のユーザーがリンクをクリックした時間。</span><span class="sxs-lookup"><span data-stu-id="78845-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="78845-286">**平均クリック** 数 : すべてのユーザーがリンクをクリックした時間の合計を、リンクをクリックしたユーザー数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="78845-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="78845-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="78845-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="78845-288">**最速の資格情報**: キャンペーンの起動後、最初のユーザーが資格情報を入力するためにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="78845-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="78845-289">**Average Credentials**: すべてのユーザーが資格情報を入力するためにかかった時間の合計を、資格情報を入力したユーザーの数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="78845-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="78845-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="78845-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="78845-291">クリックされたリンクと、1 日 **あたりの\*\*\*\*資格情報の** 提供された数値を示す棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="78845-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="78845-292">クリックされたリンク、**指定された資格情報**、キャンペーンの **パーセンテージなし** を示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="78845-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="78845-293">[ **侵害されたユーザー]** セクションには、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="78845-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="78845-294">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="78845-294">The user's email address</span></span>

  - <span data-ttu-id="78845-295">リンクをクリックした日時。</span><span class="sxs-lookup"><span data-stu-id="78845-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="78845-296">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="78845-296">The client IP address.</span></span>

  - <span data-ttu-id="78845-297">ユーザーの Windows および Web ブラウザーのバージョンに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="78845-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="78845-298">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="78845-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="78845-299">スピア フィッシング (添付ファイル) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="78845-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="78845-300">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="78845-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="78845-301">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="78845-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="78845-302">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="78845-302">**Total users targeted**</span></span>

- <span data-ttu-id="78845-303">**成功した試行**: 添付ファイルを開いた、またはダウンロードして開いたユーザーの数 (プレビューはカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="78845-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="78845-304">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="78845-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="78845-305">**最速の添付ファイルの** オープン時間 : キャンペーンの起動後に最初のユーザーが添付ファイルを開くのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="78845-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="78845-306">**平均添付ファイルの** オープン時間 : すべてのユーザーが添付ファイルを開くのにかかった時間の合計を、添付ファイルを開いたユーザー数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="78845-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="78845-307">**添付ファイルを開く** 成功率 : (添付ファイルを開いたユーザーの数) / 対象ユーザーの総数によって計算される **割合**。</span><span class="sxs-lookup"><span data-stu-id="78845-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="78845-308">ブルート フォース パスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="78845-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="78845-309">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="78845-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="78845-310">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="78845-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="78845-311">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="78845-311">**Total users targeted**</span></span>

- <span data-ttu-id="78845-312">**成功した試行**: 指定されたパスワードのいずれかを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="78845-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="78845-313">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="78845-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="78845-314">[ **侵害されたユーザー] セクション** には、影響を受けるユーザーの電子メール アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="78845-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="78845-315">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="78845-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="78845-316">パスワード スプレー攻撃キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="78845-316">Password spray attack campaign results</span></span>

<span data-ttu-id="78845-317">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="78845-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="78845-318">キャンペーンの期間 (開始日時と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="78845-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="78845-319">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="78845-319">**Total users targeted**</span></span>

- <span data-ttu-id="78845-320">**成功した試行**: 指定されたパスワードを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="78845-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="78845-321">**全体的な成功率**: 対象ユーザーの合計が **成功** した回数によって  /  **計算される割合です**。</span><span class="sxs-lookup"><span data-stu-id="78845-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
