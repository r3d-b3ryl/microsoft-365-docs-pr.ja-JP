---
title: Microsoft Defender の攻撃シミュレーター for Office 365
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
description: 管理者は、攻撃シミュレーターを使用して、Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 組織でシミュレートされたフィッシング攻撃とパスワード攻撃を実行する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85b376701ffa0c567fd66aa629371e9f69b354e9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407476"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7beed-103">Microsoft Defender の攻撃シミュレーター for Office 365</span><span class="sxs-lookup"><span data-stu-id="7beed-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7beed-104">**Microsoft** Defender for [Office 365 プラン 2 に適用されます](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="7beed-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="7beed-105">組織に脅威の調査と応答機能を含む microsoft Defender for Office 365 プラン 2 がある場合は、セキュリティ & コンプライアンス センターの攻撃シミュレーターを使用して、組織内で現実的な攻撃シナリオを実行できます。 [](office-365-ti.md)</span><span class="sxs-lookup"><span data-stu-id="7beed-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="7beed-106">これらのシミュレートされた攻撃は、実際の攻撃が一番下の行に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7beed-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="7beed-107">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7beed-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="7beed-108">攻撃シミュレーター v1 エクスペリエンスは読み取り専用モードに切り替え、攻撃シミュレーション トレーニングの使用の開始に関する記事で説明されている攻撃シミュレーター トレーニング [に置き換わります](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="7beed-108">Attack Simulator v1 experience has been switched to read-only mode and replaced by Attack simulator training that's described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
> <span data-ttu-id="7beed-109">このサイトから新しいシミュレーションを起動する機能が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7beed-109">The ability to launch new simulations from this site has been disabled.</span></span> <span data-ttu-id="7beed-110">ただし、2021 年 1 月 24 日から 90 日間実行されるシミュレーションのレポートには引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-110">However, you can still access reports for simulations run for a period of 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7beed-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7beed-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7beed-112">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="7beed-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="7beed-113">攻撃シミュレーターは、脅威管理 **攻撃シミュレーター** \> **で利用できます**。</span><span class="sxs-lookup"><span data-stu-id="7beed-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="7beed-114">直接攻撃シミュレーターに移動し、開きます <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="7beed-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="7beed-115">異なる Microsoft 365 サブスクリプション間での攻撃シミュレーターの可用性の詳細については [、「Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7beed-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="7beed-116">組織の管理またはセキュリティ管理者 **の役割グループ** の **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="7beed-117">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7beed-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7beed-118">攻撃シミュレーターでキャンペーンを作成および管理するには、多要素認証 (MFA) 用にアカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="7beed-119">手順については、「多要素認証のセットアップ [」を参照してください](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="7beed-119">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="7beed-120">攻撃シミュレーターは、クラウドベースのメールボックスでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="7beed-120">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="7beed-121">フィッシング キャンペーンは 30 日間イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="7beed-121">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="7beed-122">キャンペーンの開始後最大 90 日間、キャンペーンの履歴データを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-122">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="7beed-123">攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-123">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="7beed-124">詳細については [、「Microsoft 365 データの場所」を参照してください](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="7beed-124">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="7beed-125">攻撃シミュレーターに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="7beed-125">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="7beed-126">スピア フィッシング キャンペーン</span><span class="sxs-lookup"><span data-stu-id="7beed-126">Spear phishing campaigns</span></span>

<span data-ttu-id="7beed-127">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージの機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="7beed-127">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="7beed-128">*スピア* フィッシングは、対象となる受信者に合わせて特別に調整された、フォーカスとカスタマイズされたコンテンツを使用する標的型フィッシング攻撃です (通常、攻撃者による受信者の偵察後)。</span><span class="sxs-lookup"><span data-stu-id="7beed-128">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="7beed-129">攻撃シミュレーターでは、次の 2 種類のスピア フィッシング キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-129">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="7beed-130">**スピア フィッシング (資格情報の取得)**: 攻撃は、メッセージ内の URL をクリックする受信者を説得しようとする。</span><span class="sxs-lookup"><span data-stu-id="7beed-130">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="7beed-131">リンクをクリックすると、資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-131">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="7beed-132">その場合は、次のいずれかの場所に移動されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-132">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="7beed-133">これは単なるテストであり、フィッシング メッセージを認識するためのヒントを示す既定のページです。</span><span class="sxs-lookup"><span data-stu-id="7beed-133">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシング リンクをクリックして資格情報を入力した場合に表示される情報](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="7beed-135">指定したカスタム ページ (URL) です。</span><span class="sxs-lookup"><span data-stu-id="7beed-135">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="7beed-136">**スピア フィッシング (添付ファイル)**: 攻撃は、メッセージ内の .docx または .pdf 添付ファイルを開く受信者を説得しようとする。</span><span class="sxs-lookup"><span data-stu-id="7beed-136">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="7beed-137">添付ファイルには、既定のフィッシング リンクと同じコンテンツが含まれているが、最初の文は " で始まります。このメッセージは、開いた最近の電子メール メッセージとして表示されます \<Display Name\> 。."。</span><span class="sxs-lookup"><span data-stu-id="7beed-137">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="7beed-138">現在、攻撃シミュレーターのスピア フィッシング キャンペーンの有効期限は切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="7beed-138">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="7beed-139">スピア フィッシング キャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="7beed-139">Create a spear phishing campaign</span></span>

<span data-ttu-id="7beed-140">スピア フィッシング キャンペーンの重要な部分は、対象の受信者に送信される電子メール メッセージの外観です。</span><span class="sxs-lookup"><span data-stu-id="7beed-140">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="7beed-141">電子メール メッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7beed-141">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="7beed-142">**組み込みの電子メール テンプレートを使用する**: 2 つの組み込みテンプレートを使用 **できます。**</span><span class="sxs-lookup"><span data-stu-id="7beed-142">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="7beed-143">キャンペーンの作成および起動時に、テンプレートの一部、すべて、または一部のメール プロパティをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-143">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="7beed-144">**再利用可能な電子メール テンプレートを作成する**: 電子メール テンプレートを作成して保存した後、今後のスピア フィッシング キャンペーンで再度使用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-144">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="7beed-145">キャンペーンの作成および起動時に、テンプレートの一部、すべて、または一部のメール プロパティをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-145">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="7beed-146">**ウィザードで電子メール メッセージ** を作成する: スピア フィッシング キャンペーンを作成して起動すると、ウィザードで電子メール メッセージを直接作成できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-146">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="7beed-147">手順 1 (オプション): カスタムメール テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="7beed-147">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="7beed-148">組み込みのテンプレートのいずれかを使用する場合や、ウィザードで直接電子メール メッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-148">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="7beed-149">セキュリティ 管理コンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="7beed-149">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7beed-150">[攻撃 **のシミュレート** ] ページの [スピア フィッシング **(Credentials Harvest)** セクションまたはスピア フィッシング **(添付ファイル)** セクションで、[攻撃の詳細] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-150">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="7beed-151">テンプレートの作成場所は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="7beed-151">It doesn't matter where you create the template.</span></span> <span data-ttu-id="7beed-152">テンプレートで使用できるオプションは、両方の種類のフィッシング攻撃で同じです。</span><span class="sxs-lookup"><span data-stu-id="7beed-152">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="7beed-153">開いた **[攻撃の詳細]** ページの [フィッシング テンプレート] セクションの [テンプレートの作成] 領域 **で、[新** しいテンプレート]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-153">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="7beed-154">フィッシング **テンプレートの構成ウィザードは** 、新しいフライアウトで開始します。</span><span class="sxs-lookup"><span data-stu-id="7beed-154">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="7beed-155">[スタート] **ステップ** で、テンプレートの一意の表示名を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-155">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="7beed-156">[電子メール **の詳細の構成]** 手順で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7beed-156">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="7beed-157">**From (Name)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="7beed-157">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="7beed-158">**From (Email)**: 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="7beed-158">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="7beed-159">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、リストから使用可能な URL のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7beed-159">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="7beed-160">これは、ユーザーがクリックする必要がある URL です。</span><span class="sxs-lookup"><span data-stu-id="7beed-160">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="7beed-161">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="7beed-161">The choices are:</span></span>

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
     > <span data-ttu-id="7beed-162">URL レピュテーション サービスは、これらの URL の 1 つ以上を安全でないと識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-162">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="7beed-163">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーの URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7beed-163">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="7beed-164">**カスタム ランディング ページ URL**: ユーザーがフィッシング リンクをクリックして資格情報を入力した場合にユーザーが取得されるオプションのランディング ページを入力します。</span><span class="sxs-lookup"><span data-stu-id="7beed-164">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="7beed-165">このリンクは、既定のランディング ページを置き換える。</span><span class="sxs-lookup"><span data-stu-id="7beed-165">This link replaces the default landing page.</span></span> <span data-ttu-id="7beed-166">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-166">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="7beed-167">**カテゴリ**: 現在、この設定は使用されません (入力した項目は無視されます)。</span><span class="sxs-lookup"><span data-stu-id="7beed-167">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="7beed-168">**件名**: **電子メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="7beed-168">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="7beed-169">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-169">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7beed-170">[メール **の作成] 手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="7beed-170">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="7beed-171">[電子メール] タブ (**リッチ** HTML エディター)または [ソース] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-171">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="7beed-172">HTML の書式設定は、必要に応じて単純または複雑にできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-172">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="7beed-173">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの信じやすさを高めできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-173">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="7beed-174">`${username}` 受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="7beed-174">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="7beed-175">`${loginserverurl}` 前の手順 **からフィッシング ログイン サーバーの URL** 値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="7beed-175">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="7beed-176">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-176">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="7beed-177">[確認] **手順で** 、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-177">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="7beed-178">手順 2: スピア フィッシング キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="7beed-178">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="7beed-179">セキュリティ 管理コンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="7beed-179">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7beed-180">[攻撃 **のシミュレート] ページ** で、作成するキャンペーンの種類に基づいて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="7beed-180">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="7beed-181">[ス **ピア フィッシング (Credentials Harvest)]** セクションで、[ **攻撃の起動** ] をクリックするか、[攻撃 **の詳細** の起動攻撃] \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-181">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="7beed-182">[ス **ピア フィッシング (添付ファイル)]** セクションで、[ **攻撃の起動** ] をクリックするか、[攻撃 **の詳細の起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-182">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="7beed-183">フィッシング **攻撃の構成ウィザードは** 、新しいフライアウトで開始します。</span><span class="sxs-lookup"><span data-stu-id="7beed-183">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="7beed-184">[スタート **] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7beed-184">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7beed-185">[名前 **] ボックス** に、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7beed-185">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="7beed-186">ウィザードで後で **電子メール** メッセージを作成しますので、[テンプレートの使用] をクリックしない。</span><span class="sxs-lookup"><span data-stu-id="7beed-186">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="7beed-187">[テンプレート **の使用]** をクリックし、組み込みまたはカスタムの電子メール テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7beed-187">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="7beed-188">テンプレートを選択すると、[名前]ボックスはテンプレートに基づいて自動的に入力されますが、名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-188">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7beed-189">![フィッシングの開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="7beed-189">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="7beed-190">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7beed-191">[ターゲット **受信者] ステップで** 、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7beed-191">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7beed-192">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="7beed-192">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="7beed-193">対象となる各受信者には、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7beed-193">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="7beed-194">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-194">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="7beed-195">[ **インポート]** を **クリックし、[ファイル** のインポート] をクリックして、電子メール アドレスのコンマ区切り値 (CSV) または行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7beed-195">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="7beed-196">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-196">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="7beed-197">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-197">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7beed-198">[電子メール **の詳細の構成]** 手順で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7beed-198">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="7beed-199">開始手順でテンプレートを選択した場合、これらの値のほとんどは既に構成済みですが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-199">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="7beed-200">**From (Name)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="7beed-200">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="7beed-201">**From (Email)**: 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="7beed-201">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="7beed-202">組織のメール ドメインから実際のメール アドレスまたは偽のメール アドレスを入力するか、実際または偽の外部メール アドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-202">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="7beed-203">組織の有効な送信者の電子メール アドレスは、受信者の電子メール クライアントで実際に解決されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-203">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="7beed-204">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、リストから使用可能な URL のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7beed-204">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="7beed-205">これは、ユーザーがクリックする必要がある URL です。</span><span class="sxs-lookup"><span data-stu-id="7beed-205">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="7beed-206">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="7beed-206">The choices are:</span></span>

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
     > - <span data-ttu-id="7beed-207">すべての URL は意図的に http で、https ではありません。</span><span class="sxs-lookup"><span data-stu-id="7beed-207">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="7beed-208">URL レピュテーション サービスは、これらの URL の 1 つ以上を安全でないと識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-208">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="7beed-209">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーの URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7beed-209">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="7beed-210">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-210">You are required to select a URL.</span></span> <span data-ttu-id="7beed-211">ス **ピア フィッシング (添付ファイル)** キャンペーンでは、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンクと添付ファイルの両方 **が** 含まれる)。</span><span class="sxs-lookup"><span data-stu-id="7beed-211">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="7beed-212">**添付ファイルの** 種類 : この設定は、スピア フィッシング **(添付ファイル) キャンペーンでのみ** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-212">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="7beed-213">ドロップダウンをクリックして選択します **。DOCX** または **.一** 覧の PDF。</span><span class="sxs-lookup"><span data-stu-id="7beed-213">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="7beed-214">**添付ファイル** 名 : この設定は、スピア フィッシング **(添付ファイル) キャンペーンでのみ** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-214">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="7beed-215">.docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7beed-215">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="7beed-216">**カスタム ランディング ページ URL**: ユーザーがフィッシング リンクをクリックして資格情報を入力した場合にユーザーが取得されるオプションのランディング ページを入力します。</span><span class="sxs-lookup"><span data-stu-id="7beed-216">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="7beed-217">このリンクは、既定のランディング ページを置き換える。</span><span class="sxs-lookup"><span data-stu-id="7beed-217">This link replaces the default landing page.</span></span> <span data-ttu-id="7beed-218">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-218">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="7beed-219">**件名**: **電子メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="7beed-219">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="7beed-220">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-220">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7beed-221">[メール **の作成] 手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="7beed-221">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="7beed-222">開始手順でテンプレートを選択した場合、メッセージ本文は既に構成済みですが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-222">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="7beed-223">[電子メール] タブ (**リッチ** HTML エディター)または [ソース] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-223">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="7beed-224">HTML の書式設定は、必要に応じて単純または複雑にできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-224">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="7beed-225">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの信じやすさを高めできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-225">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="7beed-226">`${username}` 受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="7beed-226">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="7beed-227">`${loginserverurl}` フィッシング ログイン **サーバーの URL 値を挿入** します。</span><span class="sxs-lookup"><span data-stu-id="7beed-227">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="7beed-228">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれるので、リンクのクリックは添付ファイル キャンペーンでは追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="7beed-228">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7beed-229">![メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="7beed-229">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="7beed-230">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-230">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="7beed-231">[確認] **手順で** 、[完了] **をクリックして** キャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="7beed-231">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="7beed-232">フィッシング メッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-232">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="7beed-233">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="7beed-233">Password attack campaigns</span></span>

<span data-ttu-id="7beed-234">パスワード *攻撃は、* 通常、攻撃者が 1 つ以上の有効なユーザー アカウントを特定した後、組織内のユーザー アカウントのパスワードを推測します。</span><span class="sxs-lookup"><span data-stu-id="7beed-234">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="7beed-235">Attack Simulator では、ユーザーのパスワードの複雑さをテストするために、次の 2 種類のパスワード攻撃キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-235">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="7beed-236">**ブルート** フォース パスワード (辞書攻撃)  : ブルート フォース攻撃または辞書攻撃では、ユーザー アカウント上のパスワードの大きな辞書 ファイルを使用し、そのうちの 1 つが機能する (1 つのアカウントに対して多くのパスワード) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7beed-236">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="7beed-237">パスワードロックアウトが正しくないと、ブルートフォースパスワード攻撃を抑止できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-237">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="7beed-238">辞書攻撃では、1 つ以上のパスワードを指定して (手動で入力するか、アップロードしたファイルで) 試し、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-238">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="7beed-239">**パスワード スプレー攻撃**: パスワード *スプレー攻撃では* 、ユーザー アカウントのリストに対して同じ慎重に考慮されたパスワードを使用します (多くのアカウントに対して 1 つのパスワード)。</span><span class="sxs-lookup"><span data-stu-id="7beed-239">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="7beed-240">パスワード スプレー攻撃は、ブルート フォース パスワード攻撃よりも検出が困難です (攻撃者がユーザーの誤ったパスワード ロックアウトをトリップするリスクなしに、数十または数百のアカウントで 1 つのパスワードを試行すると成功の確率が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="7beed-240">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="7beed-241">パスワード スプレー攻撃では、1 つのパスワードのみを指定して、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-241">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="7beed-242">Attack Simulator のパスワード攻撃は、ユーザー名とパスワードの基本認証要求をエンドポイントに渡すので、他の認証方法 (AD FS、パスワード ハッシュ同期、パススルー、PingFederate など) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="7beed-242">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="7beed-243">MFA が有効になっているユーザーの場合、パスワード攻撃によって実際のパスワードが試行された場合でも、試行は常に失敗として登録されます (つまり、MFA ユーザーはキャンペーンの成功試行回数に表示されません)。</span><span class="sxs-lookup"><span data-stu-id="7beed-243">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="7beed-244">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="7beed-244">This is the expected result.</span></span> <span data-ttu-id="7beed-245">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="7beed-245">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="7beed-246">パスワード攻撃キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="7beed-246">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="7beed-247">セキュリティ 管理コンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="7beed-247">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7beed-248">[攻撃 **のシミュレート] ページ** で、作成するキャンペーンの種類に基づいて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="7beed-248">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="7beed-249">[ブルー **ト フォース パスワード (辞書攻撃)]** セクションで、[攻撃の起動] をクリックするか、[攻撃 **の詳細の** 起動攻撃] \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-249">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="7beed-250">[パスワード スプレー **攻撃] セクションで、[** 攻撃の起動] **をクリックするか** 、[攻撃 **の詳細の起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-250">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="7beed-251">パスワード **攻撃の構成ウィザード** は、新しいフライアウトで開始します。</span><span class="sxs-lookup"><span data-stu-id="7beed-251">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="7beed-252">[スタート] **ステップ** で、キャンペーンの一意の表示名を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-252">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="7beed-253">[ターゲット **ユーザー] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7beed-253">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7beed-254">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="7beed-254">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="7beed-255">対象となる各受信者には、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7beed-255">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="7beed-256">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-256">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="7beed-257">[ **インポート]** を **クリックし、[ファイル** のインポート] をクリックして、電子メール アドレスのコンマ区切り値 (CSV) または行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7beed-257">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="7beed-258">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7beed-258">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="7beed-259">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-259">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7beed-260">[攻撃 **設定の選択] 手順** で、キャンペーンの種類に基づいて実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="7beed-260">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="7beed-261">**ブルート フォース パスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7beed-261">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="7beed-262">**パスワードを手動で入力** する: **[Enter キーを押して** パスワードを追加する] ボックスにパスワードを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7beed-262">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="7beed-263">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7beed-263">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="7beed-264">**辞書ファイルからパスワードを** アップロードする: [アップロード] をクリックして、各行に 1 つのパスワードと空白の最後の行を含む既存のテキスト ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7beed-264">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="7beed-265">テキスト ファイルのサイズは 10 MB 以下で、30000 を超えるパスワードを含めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7beed-265">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="7beed-266">**パスワード スプレー攻撃**: 攻撃 **ボックスで** 使用するパスワードに、1 つのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7beed-266">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="7beed-267">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-267">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7beed-268">[確認] **手順で** 、[完了] **をクリックして** キャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="7beed-268">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="7beed-269">指定したパスワードは、指定したユーザーに対して試されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-269">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="7beed-270">キャンペーンの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="7beed-270">View campaign results</span></span>

<span data-ttu-id="7beed-271">キャンペーンを開始した後、メインの [攻撃のシミュレート] ページで進行状況と結果 **を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-271">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="7beed-272">アクティブなキャンペーンでは、ステータス バー、完了した割合の値、および "(完了したユーザー) の (ユーザーの総数) カウント" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-272">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="7beed-273">[更新] ボタン **をクリック** すると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-273">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="7beed-274">[終了] をクリック **して** 、アクティブなキャンペーンを停止できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-274">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="7beed-275">キャンペーンが終了すると、状態が [攻撃完了] **に変わります**。</span><span class="sxs-lookup"><span data-stu-id="7beed-275">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="7beed-276">キャンペーンの結果を表示するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7beed-276">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="7beed-277">メインの [ **攻撃のシミュレート] ページ** で、キャンペーン **の名前の下にある [** レポートの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-277">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="7beed-278">メインの [**攻撃のシミュレート**]ページで、攻撃の種類のセクションの [攻撃の詳細] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7beed-278">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="7beed-279">開いた **[攻撃の詳細]** ページで、[攻撃履歴] セクションで **キャンペーンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="7beed-279">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="7beed-280">前のいずれかのアクションを実行すると、攻撃の詳細という名前のページ **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="7beed-280">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="7beed-281">キャンペーンの種類ごとにこのページで利用できる情報については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="7beed-281">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="7beed-282">スピア フィッシング (Credentials Harvest) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="7beed-282">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="7beed-283">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-283">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7beed-284">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="7beed-284">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7beed-285">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="7beed-285">**Total users targeted**</span></span>

- <span data-ttu-id="7beed-286">**成功した試行**: リンクをクリックして資格情報を入力したユーザーの数 *(ユーザー* 名とパスワードの値)。</span><span class="sxs-lookup"><span data-stu-id="7beed-286">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="7beed-287">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="7beed-287">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7beed-288">**[最速クリック**]: キャンペーンを開始した後、最初のユーザーがリンクをクリックする時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="7beed-288">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="7beed-289">**平均クリック** 数 : リンクをクリックしたユーザー数で割ったリンクをクリックする時間の合計です。</span><span class="sxs-lookup"><span data-stu-id="7beed-289">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="7beed-290">**[成功率**] : (リンクをクリックしたユーザーの数) によって計算される割合 / 対象ユーザー **の総数をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7beed-290">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="7beed-291">**最速の資格情報**: キャンペーンを開始した後、最初のユーザーが資格情報を入力するためにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="7beed-291">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="7beed-292">**平均資格情報**: すべてのユーザーが資格情報を入力するためにかかった時間の合計を、資格情報を入力したユーザーの数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="7beed-292">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="7beed-293">**資格情報の成功** 率 : (資格情報を入力したユーザーの数) / 対象ユーザーの総数によって **計算される割合** です。</span><span class="sxs-lookup"><span data-stu-id="7beed-293">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="7beed-294">リンクがクリックされ、資格情報が **1** 日 **に指定された番号を示す** 棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="7beed-294">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="7beed-295">リンクがクリックされ、**資格情報が指定** され、キャンペーンの **パーセンテージ** なしを示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="7beed-295">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="7beed-296">[ **侵害されたユーザー] セクション** には、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-296">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="7beed-297">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="7beed-297">The user's email address</span></span>

  - <span data-ttu-id="7beed-298">リンクをクリックした日時。</span><span class="sxs-lookup"><span data-stu-id="7beed-298">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="7beed-299">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7beed-299">The client IP address.</span></span>

  - <span data-ttu-id="7beed-300">ユーザーのバージョンの Windows および Web ブラウザーの詳細。</span><span class="sxs-lookup"><span data-stu-id="7beed-300">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="7beed-301">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-301">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="7beed-302">スピア フィッシング (添付ファイル) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="7beed-302">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="7beed-303">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-303">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7beed-304">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="7beed-304">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7beed-305">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="7beed-305">**Total users targeted**</span></span>

- <span data-ttu-id="7beed-306">**成功した試行**: 添付ファイルを開いたユーザーまたはダウンロードして開いたユーザーの数 (プレビューはカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="7beed-306">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="7beed-307">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="7beed-307">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7beed-308">**最速の添付ファイルの** オープン時間: キャンペーンを開始した後、最初のユーザーが添付ファイルを開くのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="7beed-308">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="7beed-309">**平均添付ファイルの開** く時間 : すべてのユーザーが添付ファイルを開くのにかかった時間の合計を、添付ファイルを開いたユーザーの数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="7beed-309">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="7beed-310">**添付ファイルを開く** 成功率 : (添付ファイルを開いたユーザーの数) / 対象ユーザーの総数によって **計算される割合** です。</span><span class="sxs-lookup"><span data-stu-id="7beed-310">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="7beed-311">ブルート フォース パスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="7beed-311">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="7beed-312">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-312">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7beed-313">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="7beed-313">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7beed-314">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="7beed-314">**Total users targeted**</span></span>

- <span data-ttu-id="7beed-315">**成功した試行**: 指定されたパスワードのいずれかを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="7beed-315">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="7beed-316">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="7beed-316">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7beed-317">[ **侵害されたユーザー] セクション** には、影響を受けるユーザーの電子メール アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7beed-317">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="7beed-318">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7beed-318">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="7beed-319">パスワード スプレー攻撃キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="7beed-319">Password spray attack campaign results</span></span>

<span data-ttu-id="7beed-320">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="7beed-320">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7beed-321">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="7beed-321">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7beed-322">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="7beed-322">**Total users targeted**</span></span>

- <span data-ttu-id="7beed-323">**成功した試行**: 指定されたパスワードを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="7beed-323">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="7beed-324">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="7beed-324">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
