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
ms.openlocfilehash: 105ca66cdfacaab3b73d8bf89c3a05207b673a3c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921362"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f80c1-103">Microsoft Defender の攻撃シミュレーター for Office 365</span><span class="sxs-lookup"><span data-stu-id="f80c1-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f80c1-104">**Microsoft** Defender for [Office 365 プラン 2 に適用されます](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="f80c1-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="f80c1-105">組織に脅威の調査と応答機能を含む microsoft Defender for Office 365 プラン 2 がある場合は、セキュリティ & コンプライアンス センターの攻撃シミュレーターを使用して、組織内で現実的な攻撃シナリオを実行できます。 [](office-365-ti.md)</span><span class="sxs-lookup"><span data-stu-id="f80c1-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="f80c1-106">これらのシミュレートされた攻撃は、実際の攻撃が一番下の行に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="f80c1-107">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f80c1-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="f80c1-108">この記事で説明する攻撃シミュレーターは読み取り専用で [、Microsoft 365](https://security.microsoft.com)セキュリティ センターの電子メール & コラボレーション ノードの攻撃 **シミュレーション** トレーニングに置き換えされました。 </span><span class="sxs-lookup"><span data-stu-id="f80c1-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="f80c1-109">詳細については、「攻撃シミュレーション トレーニング [の使用を開始する」を参照してください](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="f80c1-110">このバージョンの攻撃シミュレーターから新しいシミュレーションを起動する機能が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f80c1-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="f80c1-111">ただし、2021 年 1 月 24 日から最大 90 日間レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f80c1-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f80c1-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f80c1-113">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="f80c1-114">攻撃シミュレーターは、脅威管理 **攻撃シミュレーター** \> **で利用できます**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="f80c1-115">直接攻撃シミュレーターに移動し、開きます <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="f80c1-115">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="f80c1-116">異なる Microsoft 365 サブスクリプション間での攻撃シミュレーターの可用性の詳細については [、「Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f80c1-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="f80c1-117">組織の管理またはセキュリティ管理者 **の役割グループ** の **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f80c1-118">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f80c1-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f80c1-119">攻撃シミュレーターでキャンペーンを作成および管理するには、多要素認証 (MFA) 用にアカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="f80c1-120">手順については、「多要素認証のセットアップ [」を参照してください](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="f80c1-121">攻撃シミュレーターは、クラウドベースのメールボックスでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="f80c1-122">フィッシング キャンペーンは 30 日間イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="f80c1-123">キャンペーンの開始後最大 90 日間、キャンペーンの履歴データを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="f80c1-124">攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="f80c1-125">詳細については [、「Microsoft 365 データの場所」を参照してください](../../enterprise/o365-data-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="f80c1-126">攻撃シミュレーターに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="f80c1-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="f80c1-127">スピア フィッシング キャンペーン</span><span class="sxs-lookup"><span data-stu-id="f80c1-127">Spear phishing campaigns</span></span>

<span data-ttu-id="f80c1-128">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージの機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="f80c1-129">*スピア* フィッシングは、対象となる受信者に合わせて特別に調整された、フォーカスとカスタマイズされたコンテンツを使用する標的型フィッシング攻撃です (通常、攻撃者による受信者の偵察後)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="f80c1-130">攻撃シミュレーターでは、次の 2 種類のスピア フィッシング キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="f80c1-131">**スピア フィッシング (資格情報の取得)**: 攻撃は、メッセージ内の URL をクリックする受信者を説得しようとする。</span><span class="sxs-lookup"><span data-stu-id="f80c1-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="f80c1-132">リンクをクリックすると、資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="f80c1-133">その場合は、次のいずれかの場所に移動されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="f80c1-134">これは単なるテストであり、フィッシング メッセージを認識するためのヒントを示す既定のページです。</span><span class="sxs-lookup"><span data-stu-id="f80c1-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシング リンクをクリックして資格情報を入力した場合に表示される情報](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="f80c1-136">指定したカスタム ページ (URL) です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="f80c1-137">**スピア フィッシング (添付ファイル)**: 攻撃は、メッセージ内の .docx または .pdf 添付ファイルを開く受信者を説得しようとする。</span><span class="sxs-lookup"><span data-stu-id="f80c1-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="f80c1-138">添付ファイルには、既定のフィッシング リンクと同じコンテンツが含まれているが、最初の文は " で始まります。このメッセージは、開いた最近の電子メール メッセージとして表示されます \<Display Name\> 。."。</span><span class="sxs-lookup"><span data-stu-id="f80c1-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="f80c1-139">現在、攻撃シミュレーターのスピア フィッシング キャンペーンの有効期限は切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="f80c1-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="f80c1-140">スピア フィッシング キャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="f80c1-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="f80c1-141">スピア フィッシング キャンペーンの重要な部分は、対象の受信者に送信される電子メール メッセージの外観です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="f80c1-142">電子メール メッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="f80c1-143">**組み込みの電子メール テンプレートを使用する**: 2 つの組み込みテンプレートを使用 **できます。**</span><span class="sxs-lookup"><span data-stu-id="f80c1-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="f80c1-144">キャンペーンの作成および起動時に、テンプレートの一部、すべて、または一部のメール プロパティをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f80c1-145">**再利用可能な電子メール テンプレートを作成する**: 電子メール テンプレートを作成して保存した後、今後のスピア フィッシング キャンペーンで再度使用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="f80c1-146">キャンペーンの作成および起動時に、テンプレートの一部、すべて、または一部のメール プロパティをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f80c1-147">**ウィザードで電子メール メッセージ** を作成する: スピア フィッシング キャンペーンを作成して起動すると、ウィザードで電子メール メッセージを直接作成できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="f80c1-148">手順 1 (オプション): カスタムメール テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="f80c1-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="f80c1-149">組み込みのテンプレートのいずれかを使用する場合や、ウィザードで直接電子メール メッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="f80c1-150">セキュリティ 管理コンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f80c1-151">[攻撃 **のシミュレート** ] ページの [スピア フィッシング **(Credentials Harvest)** セクションまたはスピア フィッシング **(添付ファイル)** セクションで、[攻撃の詳細] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="f80c1-152">テンプレートの作成場所は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="f80c1-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="f80c1-153">テンプレートで使用できるオプションは、両方の種類のフィッシング攻撃で同じです。</span><span class="sxs-lookup"><span data-stu-id="f80c1-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="f80c1-154">開いた **[攻撃の詳細]** ページの [フィッシング テンプレート] セクションの [テンプレートの作成] 領域 **で、[新** しいテンプレート]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="f80c1-155">フィッシング **テンプレートの構成ウィザードは** 、新しいフライアウトで開始します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="f80c1-156">[スタート] **ステップ** で、テンプレートの一意の表示名を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="f80c1-157">[電子メール **の詳細の構成]** 手順で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="f80c1-158">**From (Name)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="f80c1-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f80c1-159">**From (Email)**: 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="f80c1-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="f80c1-160">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、リストから使用可能な URL のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f80c1-161">これは、ユーザーがクリックする必要がある URL です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f80c1-162">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="f80c1-162">The choices are:</span></span>

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
     > <span data-ttu-id="f80c1-163">URL レピュテーション サービスは、これらの URL の 1 つ以上を安全でないと識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f80c1-164">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーの URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f80c1-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="f80c1-165">**カスタム ランディング ページ URL**: ユーザーがフィッシング リンクをクリックして資格情報を入力した場合にユーザーが取得されるオプションのランディング ページを入力します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f80c1-166">このリンクは、既定のランディング ページを置き換える。</span><span class="sxs-lookup"><span data-stu-id="f80c1-166">This link replaces the default landing page.</span></span> <span data-ttu-id="f80c1-167">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f80c1-168">**カテゴリ**: 現在、この設定は使用されません (入力した項目は無視されます)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="f80c1-169">**件名**: **電子メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="f80c1-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f80c1-170">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f80c1-171">[メール **の作成] 手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f80c1-172">[電子メール] タブ (**リッチ** HTML エディター)または [ソース] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f80c1-173">HTML の書式設定は、必要に応じて単純または複雑にできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f80c1-174">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの信じやすさを高めできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f80c1-175">`${username}` 受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f80c1-176">`${loginserverurl}` 前の手順 **からフィッシング ログイン サーバーの URL** 値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="f80c1-177">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f80c1-178">[確認] **手順で** 、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="f80c1-179">手順 2: スピア フィッシング キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="f80c1-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="f80c1-180">セキュリティ 管理コンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f80c1-181">[攻撃 **のシミュレート] ページ** で、作成するキャンペーンの種類に基づいて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="f80c1-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f80c1-182">[ス **ピア フィッシング (Credentials Harvest)]** セクションで、[ **攻撃の起動** ] をクリックするか、[攻撃 **の詳細** の起動攻撃] \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f80c1-183">[ス **ピア フィッシング (添付ファイル)]** セクションで、[ **攻撃の起動** ] をクリックするか、[攻撃 **の詳細の起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f80c1-184">フィッシング **攻撃の構成ウィザードは** 、新しいフライアウトで開始します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f80c1-185">[スタート **] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f80c1-186">[名前 **] ボックス** に、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="f80c1-187">ウィザードで後で **電子メール** メッセージを作成しますので、[テンプレートの使用] をクリックしない。</span><span class="sxs-lookup"><span data-stu-id="f80c1-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="f80c1-188">[テンプレート **の使用]** をクリックし、組み込みまたはカスタムの電子メール テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="f80c1-189">テンプレートを選択すると、[名前]ボックスはテンプレートに基づいて自動的に入力されますが、名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f80c1-190">![フィッシングの開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="f80c1-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="f80c1-191">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f80c1-192">[ターゲット **受信者] ステップで** 、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f80c1-193">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f80c1-194">対象となる各受信者には、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f80c1-195">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f80c1-196">[ **インポート]** を **クリックし、[ファイル** のインポート] をクリックして、電子メール アドレスのコンマ区切り値 (CSV) または行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f80c1-197">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f80c1-198">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f80c1-199">[電子メール **の詳細の構成]** 手順で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="f80c1-200">開始手順でテンプレートを選択した場合、これらの値のほとんどは既に構成済みですが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="f80c1-201">**From (Name)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="f80c1-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f80c1-202">**From (Email)**: 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="f80c1-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="f80c1-203">組織のメール ドメインから実際のメール アドレスまたは偽のメール アドレスを入力するか、実際または偽の外部メール アドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="f80c1-204">組織の有効な送信者の電子メール アドレスは、受信者の電子メール クライアントで実際に解決されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="f80c1-205">**フィッシング ログイン サーバーの URL**: ドロップダウンをクリックし、リストから使用可能な URL のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f80c1-206">これは、ユーザーがクリックする必要がある URL です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f80c1-207">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="f80c1-207">The choices are:</span></span>

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
     > - <span data-ttu-id="f80c1-208">すべての URL は意図的に http で、https ではありません。</span><span class="sxs-lookup"><span data-stu-id="f80c1-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="f80c1-209">URL レピュテーション サービスは、これらの URL の 1 つ以上を安全でないと識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f80c1-210">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーの URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f80c1-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="f80c1-211">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-211">You are required to select a URL.</span></span> <span data-ttu-id="f80c1-212">ス **ピア フィッシング (添付ファイル)** キャンペーンでは、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンクと添付ファイルの両方 **が** 含まれる)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="f80c1-213">**添付ファイルの** 種類 : この設定は、スピア フィッシング **(添付ファイル) キャンペーンでのみ** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f80c1-214">ドロップダウンをクリックして選択します **。DOCX** または **.一** 覧の PDF。</span><span class="sxs-lookup"><span data-stu-id="f80c1-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="f80c1-215">**添付ファイル** 名 : この設定は、スピア フィッシング **(添付ファイル) キャンペーンでのみ** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f80c1-216">.docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="f80c1-217">**カスタム ランディング ページ URL**: ユーザーがフィッシング リンクをクリックして資格情報を入力した場合にユーザーが取得されるオプションのランディング ページを入力します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f80c1-218">このリンクは、既定のランディング ページを置き換える。</span><span class="sxs-lookup"><span data-stu-id="f80c1-218">This link replaces the default landing page.</span></span> <span data-ttu-id="f80c1-219">たとえば、内部認識トレーニングがある場合は、ここでその URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f80c1-220">**件名**: **電子メール** メッセージの [件名] フィールド。</span><span class="sxs-lookup"><span data-stu-id="f80c1-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f80c1-221">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f80c1-222">[メール **の作成] 手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f80c1-223">開始手順でテンプレートを選択した場合、メッセージ本文は既に構成済みですが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="f80c1-224">[電子メール] タブ (**リッチ** HTML エディター)または [ソース] タブ (生の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f80c1-225">HTML の書式設定は、必要に応じて単純または複雑にできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f80c1-226">画像とテキストを挿入して、受信者の電子メール クライアントでメッセージの信じやすさを高めできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f80c1-227">`${username}` 受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f80c1-228">`${loginserverurl}` フィッシング ログイン **サーバーの URL 値を挿入** します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="f80c1-229">ス **ピア フィッシング (添付ファイル)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンクと添付ファイルの両方が含まれるので、リンクのクリックは添付ファイル キャンペーンでは追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f80c1-230">![メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="f80c1-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="f80c1-231">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f80c1-232">[確認] **手順で** 、[完了] **をクリックして** キャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f80c1-233">フィッシング メッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="f80c1-234">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="f80c1-234">Password attack campaigns</span></span>

<span data-ttu-id="f80c1-235">パスワード *攻撃は、* 通常、攻撃者が 1 つ以上の有効なユーザー アカウントを特定した後、組織内のユーザー アカウントのパスワードを推測します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="f80c1-236">Attack Simulator では、ユーザーのパスワードの複雑さをテストするために、次の 2 種類のパスワード攻撃キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="f80c1-237">**ブルート** フォース パスワード (辞書攻撃)  : ブルート フォース攻撃または辞書攻撃では、ユーザー アカウント上のパスワードの大きな辞書 ファイルを使用し、そのうちの 1 つが機能する (1 つのアカウントに対して多くのパスワード) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="f80c1-238">パスワードロックアウトが正しくないと、ブルートフォースパスワード攻撃を抑止できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="f80c1-239">辞書攻撃では、1 つ以上のパスワードを指定して (手動で入力するか、アップロードしたファイルで) 試し、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="f80c1-240">**パスワード スプレー攻撃**: パスワード *スプレー攻撃では* 、ユーザー アカウントのリストに対して同じ慎重に考慮されたパスワードを使用します (多くのアカウントに対して 1 つのパスワード)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="f80c1-241">パスワード スプレー攻撃は、ブルート フォース パスワード攻撃よりも検出が困難です (攻撃者がユーザーの誤ったパスワード ロックアウトをトリップするリスクなしに、数十または数百のアカウントで 1 つのパスワードを試行すると成功の確率が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="f80c1-242">パスワード スプレー攻撃では、1 つのパスワードのみを指定して、1 人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="f80c1-243">Attack Simulator のパスワード攻撃は、ユーザー名とパスワードの基本認証要求をエンドポイントに渡すので、他の認証方法 (AD FS、パスワード ハッシュ同期、パススルー、PingFederate など) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="f80c1-244">MFA が有効になっているユーザーの場合、パスワード攻撃によって実際のパスワードが試行された場合でも、試行は常に失敗として登録されます (つまり、MFA ユーザーはキャンペーンの成功試行回数に表示されません)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="f80c1-245">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-245">This is the expected result.</span></span> <span data-ttu-id="f80c1-246">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="f80c1-247">パスワード攻撃キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="f80c1-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="f80c1-248">セキュリティ 管理コンプライアンス センター&、脅威管理攻撃 **シミュレーターに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f80c1-249">[攻撃 **のシミュレート] ページ** で、作成するキャンペーンの種類に基づいて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="f80c1-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f80c1-250">[ブルー **ト フォース パスワード (辞書攻撃)]** セクションで、[攻撃の起動] をクリックするか、[攻撃 **の詳細の** 起動攻撃] \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f80c1-251">[パスワード スプレー **攻撃] セクションで、[** 攻撃の起動] **をクリックするか** 、[攻撃 **の詳細の起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f80c1-252">パスワード **攻撃の構成ウィザード** は、新しいフライアウトで開始します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f80c1-253">[スタート] **ステップ** で、キャンペーンの一意の表示名を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="f80c1-254">[ターゲット **ユーザー] ステップ** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f80c1-255">[ **アドレス帳]** をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f80c1-256">対象となる各受信者には、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f80c1-257">検索条件を **入力せずに [フィルター** と **適用** ] をクリックすると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f80c1-258">[ **インポート]** を **クリックし、[ファイル** のインポート] をクリックして、電子メール アドレスのコンマ区切り値 (CSV) または行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f80c1-259">各行には、受信者の電子メール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c1-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f80c1-260">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f80c1-261">[攻撃 **設定の選択] 手順** で、キャンペーンの種類に基づいて実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="f80c1-262">**ブルート フォース パスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="f80c1-263">**パスワードを手動で入力** する: **[Enter キーを押して** パスワードを追加する] ボックスにパスワードを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="f80c1-264">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="f80c1-265">**辞書ファイルからパスワードを** アップロードする: [アップロード] をクリックして、各行に 1 つのパスワードと空白の最後の行を含む既存のテキスト ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="f80c1-266">テキスト ファイルのサイズは 10 MB 以下で、30000 を超えるパスワードを含めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f80c1-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="f80c1-267">**パスワード スプレー攻撃**: 攻撃 **ボックスで** 使用するパスワードに、1 つのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="f80c1-268">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f80c1-269">[確認] **手順で** 、[完了] **をクリックして** キャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f80c1-270">指定したパスワードは、指定したユーザーに対して試されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="f80c1-271">キャンペーンの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="f80c1-271">View campaign results</span></span>

<span data-ttu-id="f80c1-272">キャンペーンを開始した後、メインの [攻撃のシミュレート] ページで進行状況と結果 **を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="f80c1-273">アクティブなキャンペーンでは、ステータス バー、完了した割合の値、および "(完了したユーザー) の (ユーザーの総数) カウント" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="f80c1-274">[更新] ボタン **をクリック** すると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="f80c1-275">[終了] をクリック **して** 、アクティブなキャンペーンを停止できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="f80c1-276">キャンペーンが終了すると、状態が [攻撃完了] **に変わります**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="f80c1-277">キャンペーンの結果を表示するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="f80c1-278">メインの [ **攻撃のシミュレート] ページ** で、キャンペーン **の名前の下にある [** レポートの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="f80c1-279">メインの [**攻撃のシミュレート**]ページで、攻撃の種類のセクションの [攻撃の詳細] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f80c1-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="f80c1-280">開いた **[攻撃の詳細]** ページで、[攻撃履歴] セクションで **キャンペーンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="f80c1-281">前のいずれかのアクションを実行すると、攻撃の詳細という名前のページ **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="f80c1-282">キャンペーンの種類ごとにこのページで利用できる情報については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="f80c1-283">スピア フィッシング (Credentials Harvest) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f80c1-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="f80c1-284">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f80c1-285">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f80c1-286">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f80c1-286">**Total users targeted**</span></span>

- <span data-ttu-id="f80c1-287">**成功した試行**: リンクをクリックして資格情報を入力したユーザーの数 *(ユーザー* 名とパスワードの値)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="f80c1-288">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f80c1-289">**[最速クリック**]: キャンペーンを開始した後、最初のユーザーがリンクをクリックする時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f80c1-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="f80c1-290">**平均クリック** 数 : リンクをクリックしたユーザー数で割ったリンクをクリックする時間の合計です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="f80c1-291">**[成功率**] : (リンクをクリックしたユーザーの数) によって計算される割合 / 対象ユーザー **の総数をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f80c1-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="f80c1-292">**最速の資格情報**: キャンペーンを開始した後、最初のユーザーが資格情報を入力するためにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="f80c1-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="f80c1-293">**平均資格情報**: すべてのユーザーが資格情報を入力するためにかかった時間の合計を、資格情報を入力したユーザーの数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="f80c1-294">**資格情報の成功** 率 : (資格情報を入力したユーザーの数) / 対象ユーザーの総数によって **計算される割合** です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="f80c1-295">リンクがクリックされ、資格情報が **1** 日 **に指定された番号を示す** 棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="f80c1-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="f80c1-296">リンクがクリックされ、**資格情報が指定** され、キャンペーンの **パーセンテージ** なしを示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="f80c1-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="f80c1-297">[ **侵害されたユーザー] セクション** には、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="f80c1-298">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="f80c1-298">The user's email address</span></span>

  - <span data-ttu-id="f80c1-299">リンクをクリックした日時。</span><span class="sxs-lookup"><span data-stu-id="f80c1-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="f80c1-300">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f80c1-300">The client IP address.</span></span>

  - <span data-ttu-id="f80c1-301">ユーザーのバージョンの Windows および Web ブラウザーの詳細。</span><span class="sxs-lookup"><span data-stu-id="f80c1-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="f80c1-302">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="f80c1-303">スピア フィッシング (添付ファイル) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f80c1-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="f80c1-304">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f80c1-305">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f80c1-306">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f80c1-306">**Total users targeted**</span></span>

- <span data-ttu-id="f80c1-307">**成功した試行**: 添付ファイルを開いたユーザーまたはダウンロードして開いたユーザーの数 (プレビューはカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="f80c1-308">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f80c1-309">**最速の添付ファイルの** オープン時間: キャンペーンを開始した後、最初のユーザーが添付ファイルを開くのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="f80c1-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="f80c1-310">**平均添付ファイルの開** く時間 : すべてのユーザーが添付ファイルを開くのにかかった時間の合計を、添付ファイルを開いたユーザーの数で割った値です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="f80c1-311">**添付ファイルを開く** 成功率 : (添付ファイルを開いたユーザーの数) / 対象ユーザーの総数によって **計算される割合** です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="f80c1-312">ブルート フォース パスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f80c1-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="f80c1-313">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f80c1-314">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f80c1-315">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f80c1-315">**Total users targeted**</span></span>

- <span data-ttu-id="f80c1-316">**成功した試行**: 指定されたパスワードのいずれかを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="f80c1-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="f80c1-317">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f80c1-318">[ **侵害されたユーザー] セクション** には、影響を受けるユーザーの電子メール アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="f80c1-319">[エクスポート] **をクリック** すると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="f80c1-320">パスワード スプレー攻撃キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="f80c1-320">Password spray attack campaign results</span></span>

<span data-ttu-id="f80c1-321">次の情報は、各キャンペーンの **[攻撃の詳細]** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f80c1-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f80c1-322">キャンペーンの期間 (開始日/時刻と終了日時)。</span><span class="sxs-lookup"><span data-stu-id="f80c1-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f80c1-323">**対象ユーザーの総数**</span><span class="sxs-lookup"><span data-stu-id="f80c1-323">**Total users targeted**</span></span>

- <span data-ttu-id="f80c1-324">**成功した試行**: 指定されたパスワードを使用しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="f80c1-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="f80c1-325">**全体的な成功率**: 成功した試行によって計算される割合  /  **ターゲットユーザーの総数** です。</span><span class="sxs-lookup"><span data-stu-id="f80c1-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>