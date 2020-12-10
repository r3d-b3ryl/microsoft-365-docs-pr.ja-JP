---
title: Microsoft Defender for Office 365 のアタックシミュレータ
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
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理者は、アタックシミュレータを使用して、Microsoft 365 E5 または Microsoft Defender for Office 365 プラン2の組織で、シミュレートされたフィッシングおよびパスワード攻撃を実行する方法を学習できます。
ms.openlocfilehash: b1c2ad265c4812f67aee66f0f59664480b4db229
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615206"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2e6e0-103">Microsoft Defender for Office 365 のアタックシミュレータ</span><span class="sxs-lookup"><span data-stu-id="2e6e0-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2e6e0-104">[脅威の調査および応答機能](office-365-ti.md)を含む Microsoft Defender for Office 365 プラン2が組織にある場合は、セキュリティ & コンプライアンスセンターでアタックシミュレータを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="2e6e0-105">このようなシミュレートされた攻撃は、実際の攻撃が下の回線に影響を与える前に、脆弱性のあるユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="2e6e0-106">詳細については、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="2e6e0-107">アタックシミュレーションおよびトレーニング関連データは、Microsoft 365 サービスの他の顧客データと共に保存されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="2e6e0-108">詳細については、「 [Microsoft 365 データの保存場所](/microsoft-365/enterprise/o365-data-locations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="2e6e0-109">攻撃シミュレーショントレーニングは、Microsoft 365 セキュリティセンターのパブリックプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="2e6e0-110">詳細について [は、「Microsoft Defender For Office 365 を使用してフィッシング攻撃をシミュレート](attack-simulation-training.md) する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2e6e0-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="2e6e0-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2e6e0-112">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="2e6e0-113">アタックシミュレータは、 **脅威管理** の \> **アタックシミュレータ** で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="2e6e0-114">[アタックシミュレータ] を直接開き <https://protection.office.com/attacksimulator> ます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="2e6e0-115">異なる Microsoft 365 サブスクリプション間でのアタックシミュレータの可用性の詳細については、「 [Microsoft Defender For Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="2e6e0-116">**組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2e6e0-117">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2e6e0-118">アタックシミュレータでキャンペーンを作成および管理するには、アカウントが多要素認証 (MFA) 用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="2e6e0-119">手順については、「 [多要素認証をセットアップ](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="2e6e0-120">フィッシングキャンペーンは、30日間、イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="2e6e0-121">キャンペーンを開始した後、過去90日間は過去のキャンペーンデータを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="2e6e0-122">アタックシミュレータに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="2e6e0-123">スピアーフィッシングキャンペーン</span><span class="sxs-lookup"><span data-stu-id="2e6e0-123">Spear phishing campaigns</span></span>

<span data-ttu-id="2e6e0-124">*フィッシング* とは、正規または信頼された送信者からのメッセージで機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="2e6e0-125">*スピアーフィッシング* は、対象となる受信者に特化した、特定の受信者に特化した (通常は、攻撃者が受信した受信者に対して) カスタマイズされたコンテンツを使用する、対象となるフィッシング攻撃です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="2e6e0-126">アタックシミュレータでは、2つの異なる種類のスピアーフィッシングキャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="2e6e0-127">**スピアーフィッシング (資格情報のハーベスト)**: 攻撃により、受信者がメッセージ内の URL をクリックするように誘導しようとします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="2e6e0-128">ユーザーがリンクをクリックすると、資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="2e6e0-129">その場合は、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="2e6e0-130">これはテストのみであることを示す既定のページであり、フィッシングメッセージを認識するためのヒントが提供されています。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に表示されること](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="2e6e0-132">指定するカスタムページ (URL)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="2e6e0-133">**スピアーフィッシング (添付ファイル)**: 攻撃により、受信者がメッセージ内の .docx または .pdf 添付ファイルを開くように誘導しようとします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="2e6e0-134">添付ファイルには、既定のフィッシングリンクと同じ内容が含まれていますが、最初の文は "" という \<Display Name\> メッセージが最近の電子メールメッセージとして表示されています。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="2e6e0-135">現時点では、アタックシミュレータのスピアーフィッシングキャンペーンは期限切れになりません。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="2e6e0-136">スピアーフィッシングキャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="2e6e0-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="2e6e0-137">スピアーフィッシングキャンペーンの重要な部分は、対象の受信者に送信される電子メールメッセージのルックアンドフィールです。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="2e6e0-138">電子メールメッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="2e6e0-139">**組み込みの電子メールテンプレートを使用** する: 2 つの組み込みテンプレートを利用できます: [ **賞品 Giveaway** ] および [ **給与の更新**]。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="2e6e0-140">キャンペーンを作成および開始するときに、テンプレートから、電子メールのプロパティをいくつか、すべて、またはまったくカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="2e6e0-141">**再利用可能な電子メールテンプレートを作成** する: 電子メールテンプレートを作成して保存すると、今後のスピアーフィッシングキャンペーンで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="2e6e0-142">キャンペーンを作成および開始するときに、テンプレートから、電子メールのプロパティをいくつか、すべて、またはまったくカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="2e6e0-143">**ウィザードで電子メールメッセージを作成** する: スピアーフィッシングキャンペーンを作成して起動すると、ウィザードで直接電子メールメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="2e6e0-144">手順 1 (省略可能): カスタム電子メールテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="2e6e0-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="2e6e0-145">組み込みのテンプレートのいずれかを使用する場合、またはウィザードで直接電子メールメッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="2e6e0-146">セキュリティ & コンプライアンスセンターで、[ **脅威管理**] [ \> **アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2e6e0-147">[ **アタックのシミュレート** ] ページの [ **スピアーフィッシング (資格情報のハーベスト)** ] セクションまたは [ **スピアーフィッシング (添付ファイル)** ] セクションで、[アタックの **詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="2e6e0-148">テンプレートを作成する場所は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="2e6e0-149">テンプレートで使用可能なオプションは、どちらの種類のフィッシング攻撃でも同じです。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="2e6e0-150">開かれた [ **アタックの詳細** ] ページの [ **フィッシングテンプレート** ] セクションで、[ **テンプレートの作成** ] 領域の [ **新しいテンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="2e6e0-151">新しいポップアップで [ **フィッシングテンプレートの構成** ] ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="2e6e0-152">[ **開始** ] ステップに、テンプレートの一意の表示名を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="2e6e0-153">[ **電子メールの詳細の構成** ] ステップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="2e6e0-154">**From (名前)**: メッセージの送信者に使用する表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="2e6e0-155">**From (電子メール)**: 送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="2e6e0-156">[**フィッシングログインサーバーの URL**]: ドロップダウンをクリックし、一覧から使用可能な url のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="2e6e0-157">これは、ユーザーがクリックしたくなる URL です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="2e6e0-158">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-158">The choices are:</span></span>

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
     > - <span data-ttu-id="2e6e0-159">すべての Url は、https ではなく、意図的に http になっています。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-159">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="2e6e0-160">URL 評価サービスでは、これらの Url の1つ以上が安全でないと識別されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="2e6e0-161">フィッシングキャンペーンで URL を使用する前に、サポートされている web ブラウザーで URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="2e6e0-162">**ユーザー設定のランディングページの URL**: ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に実行される、オプションのランディングページを入力します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="2e6e0-163">このリンクにより、既定のランディングページが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-163">This link replaces the default landing page.</span></span> <span data-ttu-id="2e6e0-164">たとえば、社内の認識トレーニングがある場合は、その URL をここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="2e6e0-165">**Category**: 現在、この設定は使用されていません (入力した内容はすべて無視されます)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="2e6e0-166">**Subject**: 電子メールメッセージの **件名** フィールド。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="2e6e0-167">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2e6e0-168">[ **電子メールの作成** ] ステップで、電子メールメッセージの本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="2e6e0-169">[ **電子メール** ] タブ (リッチ html エディター) または [ **ソース** ] タブ (生の html コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="2e6e0-170">必要に応じて、HTML 形式を単純にすることも複雑にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="2e6e0-171">受信者の電子メールクライアントでのメッセージの believability を向上させるために、画像とテキストを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="2e6e0-172">`${username}` 受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="2e6e0-173">`${loginserverurl}` 前の手順で検出された **フィッシングログインサーバーの URL** 値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="2e6e0-174">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="2e6e0-175">[ **確認** ] ステップで、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="2e6e0-176">手順 2: スピアーフィッシングキャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="2e6e0-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="2e6e0-177">セキュリティ & コンプライアンスセンターで、[ **脅威管理**] [ \> **アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2e6e0-178">[ **アタックのシミュレート** ] ページで、作成するキャンペーンの種類に応じて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="2e6e0-179">[ **スピアーフィッシング (資格情報のハーベスト)** ] セクションで、[ **アタックの起動** ] をクリックするか、[ **アタックの詳細** の \> **起動攻撃**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="2e6e0-180">[ **スピアーフィッシング (添付ファイル)** ] セクションで、[ **アタックの起動** ] をクリックするか、[ **アタックの詳細** \> を **起動** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="2e6e0-181">新しいポップアップで [ **フィッシング攻撃の構成** ] ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="2e6e0-182">**開始** ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2e6e0-183">[ **名前** ] ボックスに、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="2e6e0-184">後でウィザードで電子メールメッセージを作成するので、[ **テンプレートの使用**] をクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="2e6e0-185">[ **テンプレートを使用する** ] をクリックし、組み込みまたはカスタムの電子メールテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="2e6e0-186">テンプレートを選択すると、テンプレートに基づいて [ **名前** ] ボックスに自動的に入力されますが、名前を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![フィッシング開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="2e6e0-188">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2e6e0-189">[ **ターゲット受信者** ] ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2e6e0-190">[ **アドレス帳** ] をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="2e6e0-191">対象となる受信者ごとに、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="2e6e0-192">検索条件を入力せずに [ **フィルター** と **適用** ] をクリックすると、すべての受信者が返されてキャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="2e6e0-193">[ **インポート** ]、[ **ファイルのインポート** ] の順にクリックして、電子メールアドレスのコンマ区切り値 (CSV) または行区切りのファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="2e6e0-194">各行には、受信者の電子メールアドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="2e6e0-195">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2e6e0-196">[ **電子メールの詳細の構成** ] ステップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="2e6e0-197">**開始** ステップでテンプレートを選択した場合、これらの値のほとんどは既に構成されていますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="2e6e0-198">**From (名前)**: メッセージの送信者に使用する表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="2e6e0-199">**From (電子メール)**: 送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="2e6e0-200">組織の電子メールドメインから本物または偽の電子メールアドレスを入力することも、本物または偽の外部電子メールアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="2e6e0-201">組織からの有効な送信者の電子メールアドレスは、受信者の電子メールクライアントで実際に解決されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="2e6e0-202">[**フィッシングログインサーバーの URL**]: ドロップダウンをクリックし、一覧から使用可能な url のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="2e6e0-203">これは、ユーザーがクリックしたくなる URL です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="2e6e0-204">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-204">The choices are:</span></span>

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
     > - <span data-ttu-id="2e6e0-205">すべての Url は、https ではなく、意図的に http になっています。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-205">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="2e6e0-206">URL 評価サービスでは、これらの Url の1つ以上が安全でないと識別されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="2e6e0-207">フィッシングキャンペーンで URL を使用する前に、サポートされている web ブラウザーで URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="2e6e0-208">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-208">You are required to select a URL.</span></span> <span data-ttu-id="2e6e0-209">**スピアーフィッシング (添付)** キャンペーンの場合は、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンク **と** 添付ファイルの両方が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-209">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="2e6e0-210">**添付ファイルの種類**: この設定は、 **スピアーフィッシング (添付ファイル)** キャンペーンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="2e6e0-211">ドロップダウンをクリックし、[] を選択し **ます。.DOCX** また **は** リストから PDF を表示します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="2e6e0-212">[**添付ファイル名**]: この設定は、**スピアーフィッシング (添付ファイル)** キャンペーンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="2e6e0-213">.Docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="2e6e0-214">**ユーザー設定のランディングページの URL**: ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に実行される、オプションのランディングページを入力します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="2e6e0-215">このリンクにより、既定のランディングページが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-215">This link replaces the default landing page.</span></span> <span data-ttu-id="2e6e0-216">たとえば、社内の認識トレーニングがある場合は、その URL をここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="2e6e0-217">**Subject**: 電子メールメッセージの **件名** フィールド。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="2e6e0-218">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2e6e0-219">[ **電子メールの作成** ] ステップで、電子メールメッセージの本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="2e6e0-220">**開始** 手順でテンプレートを選択した場合、メッセージ本文は既に構成されていますが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="2e6e0-221">[ **電子メール** ] タブ (リッチ html エディター) または [ **ソース** ] タブ (生の html コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="2e6e0-222">必要に応じて、HTML 形式を単純にすることも複雑にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="2e6e0-223">受信者の電子メールクライアントでのメッセージの believability を向上させるために、画像とテキストを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="2e6e0-224">`${username}` 受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="2e6e0-225">`${loginserverurl}` [ **フィッシングログインサーバーの URL** の値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="2e6e0-226">**スピアーフィッシング (添付)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンク **と** 添付ファイルの両方が含まれ、リンククリックは添付ファイルキャンペーンで追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![電子メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="2e6e0-228">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="2e6e0-229">[ **確認** ] ステップで、[ **完了** ] をクリックしてキャンペーンを開始します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="2e6e0-230">フィッシングメッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="2e6e0-231">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="2e6e0-231">Password attack campaigns</span></span>

<span data-ttu-id="2e6e0-232">*パスワード攻撃* は、組織内のユーザーアカウントのパスワードを推測しようと試みます。通常、攻撃者が1つ以上の有効なユーザーアカウントを識別した後。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="2e6e0-233">アタックシミュレータでは、2つの異なる種類のパスワード攻撃キャンペーンを使用して、ユーザーのパスワードの複雑さをテストできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="2e6e0-234">**ブルートフォースパスワード (辞書攻撃)**: *ブルートフォース* または *辞書* 攻撃では、ユーザーアカウントのパスワードの大規模な辞書ファイルが使用されます。これは、1つのアカウントに対して多数のパスワードを使用することを望んでいます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="2e6e0-235">パスワードのロックアウトが正しくないと、ブルートフォースパスワード攻撃を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="2e6e0-236">辞書攻撃の場合、1つまたは複数のパスワードを指定して (手動で入力またはアップロードされたファイルで)、1人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="2e6e0-237">**パスワードのスプレー攻撃**: *パスワードのスプレー* 攻撃では、ユーザーアカウントの一覧と同じように慎重にパスワードを使用します (1 つのパスワードを複数のアカウントに対して使用します)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="2e6e0-238">パスワードのスプレー攻撃は、ブルートフォースパスワード攻撃よりも検知するのは困難です (攻撃者が、ユーザーの誤ったパスワードロックアウトを防ぐリスクなしに、1つまたは数百のアカウントに対して1つのパスワードを試行したときに成功する可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="2e6e0-239">パスワードのスプレー攻撃では、1つのパスワードのみを指定して、1人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="2e6e0-240">アタックシミュレータのパスワード攻撃は、エンドポイントにユーザー名とパスワードの基本的な認証要求を渡すので、他の認証方法 (AD FS、パスワードハッシュ同期、パススルー、Ping フェデレーションなど) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="2e6e0-241">MFA が有効になっているユーザーは、パスワード攻撃が実際のパスワードを試行しても、常にエラーとして登録されます (つまり、MFA ユーザーがキャンペーンの **成功試行** 回数に表示されることはありません)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="2e6e0-242">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-242">This is the expected result.</span></span> <span data-ttu-id="2e6e0-243">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="2e6e0-244">パスワード攻撃キャンペーンを作成および開始する</span><span class="sxs-lookup"><span data-stu-id="2e6e0-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="2e6e0-245">セキュリティ & コンプライアンスセンターで、[ **脅威管理**] [ \> **アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2e6e0-246">[ **アタックのシミュレート** ] ページで、作成するキャンペーンの種類に応じて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="2e6e0-247">[ **ブルートフォースパスワード (辞書攻撃)** ] セクションで、[ **アタックの起動** ] をクリックするか、[アタックの **詳細** \> を **起動** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="2e6e0-248">[ **パスワードのスプレーアタック** ] セクションで、[ **アタックの起動** ] をクリックするか、[ **アタックの詳細** の \> **起動攻撃**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="2e6e0-249">**パスワード攻撃の構成** ウィザードが新しいポップアップで開始されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="2e6e0-250">[ **開始** ] ステップで、キャンペーンの一意の表示名を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="2e6e0-251">[ **ターゲットユーザー** ] ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2e6e0-252">[ **アドレス帳** ] をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="2e6e0-253">対象となる受信者ごとに、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="2e6e0-254">検索条件を入力せずに [ **フィルター** と **適用** ] をクリックすると、すべての受信者が返されてキャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="2e6e0-255">[ **インポート** ]、[ **ファイルのインポート** ] の順にクリックして、電子メールアドレスのコンマ区切り値 (CSV) または行区切りのファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="2e6e0-256">各行には、受信者の電子メールアドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="2e6e0-257">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2e6e0-258">[ **アタック設定の選択** ] ステップで、キャンペーンの種類に基づいて、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="2e6e0-259">**ブルートフォースパスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="2e6e0-260">**パスワードを手動で入力** します。 [enter **キーを押してパスワードを追加** します] ボックスにパスワードを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="2e6e0-261">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="2e6e0-262">**辞書ファイルからのパスワードのアップロード**: [ **アップロード** ] をクリックして、各行に1つのパスワードを含む既存のテキストファイルをインポートします。最後の行は空白にします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="2e6e0-263">テキストファイルのサイズは 10 MB 以下でなければなりません。また、3万を超えるパスワードを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="2e6e0-264">**パスワードのスプレーアタック**: [アタック] ボックスで **使用するパスワードには** 、1つのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="2e6e0-265">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2e6e0-266">[ **確認** ] ステップで、[ **完了** ] をクリックしてキャンペーンを開始します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="2e6e0-267">指定したパスワードは、指定したユーザーに対して試行されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="2e6e0-268">キャンペーン結果の表示</span><span class="sxs-lookup"><span data-stu-id="2e6e0-268">View campaign results</span></span>

<span data-ttu-id="2e6e0-269">キャンペーンを開始した後、メインの [ **攻撃のシミュレート** ] ページで進行状況と結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="2e6e0-270">アクティブなキャンペーンには、ステータスバー、完成したパーセンテージの値、および (ユーザーの合計数) のカウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="2e6e0-271">[ **更新** ] ボタンをクリックすると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="2e6e0-272">[ **終了** ] をクリックして、アクティブなキャンペーンを停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="2e6e0-273">キャンペーンが完了すると、[ **アタックが完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="2e6e0-274">次のいずれかの操作を実行して、キャンペーンの結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="2e6e0-275">[シミュレートされた **アタック** のメイン] ページで、キャンペーンの名前の下にある [ **レポートの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="2e6e0-276">[アタックの **シミュレーション** ] ページで、攻撃の種類についてセクションの [ **アタックの詳細** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="2e6e0-277">開かれた [ **アタックの詳細** ] ページで、[ **アタックの履歴** ] セクションでキャンペーンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="2e6e0-278">上記のいずれかの操作を行うと、[ **アタックの詳細**] というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="2e6e0-279">各種類のキャンペーンでこのページで使用できる情報については、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="2e6e0-280">スピアーフィッシング (資格情報のハーベスト) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="2e6e0-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="2e6e0-281">次の情報は、各キャンペーンの [ **アタックの詳細** ] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2e6e0-282">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2e6e0-283">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="2e6e0-283">**Total users targeted**</span></span>

- <span data-ttu-id="2e6e0-284">**成功** した試行: リンクをクリック **して** 資格情報 (*任意* のユーザー名とパスワード値) を入力したユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="2e6e0-285">**全体的な成功率**: 対象となるユーザーの **合計試行回数** で計算されたパーセンテージ  /  。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2e6e0-286">**[最速] クリック**: キャンペーンの開始後、最初のユーザーがリンクをクリックするのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="2e6e0-287">**平均クリック** 数: すべてのユーザーがリンクをクリックすると、リンクをクリックしたユーザーの数で割った時間の合計。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="2e6e0-288">**[成功率]**: 計算されたパーセンテージ (リンクをクリックしたユーザーの数)/ **対象ユーザーの合計** 数。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="2e6e0-289">**最高の資格情報**: キャンペーンを開始した後、最初のユーザーが資格情報を入力するのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="2e6e0-290">**平均資格情報**: ユーザーの資格情報を入力したユーザーの数で割った資格情報の入力にかかった時間の合計。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="2e6e0-291">**資格情報の成功率**: 計算の対象となるパーセンテージ (資格情報を入力したユーザー数)/ **対象ユーザーの合計** 数。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="2e6e0-292">**リンクがクリック** された、1日あたりの **資格情報が入力** された番号を示す棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="2e6e0-293">クリックされた **リンク**、指定された **資格情報**、およびキャンペーンの **None** パーセンテージを示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="2e6e0-294">[ **侵害** されたユーザー] セクションに、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="2e6e0-295">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="2e6e0-295">The user's email address</span></span>

  - <span data-ttu-id="2e6e0-296">リンクをクリックした日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="2e6e0-297">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-297">The client IP address.</span></span>

  - <span data-ttu-id="2e6e0-298">ユーザーの Windows および web ブラウザーのバージョンに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="2e6e0-299">[ **エクスポート** ] をクリックすると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="2e6e0-300">スピアーフィッシング (添付ファイル) のキャンペーン結果</span><span class="sxs-lookup"><span data-stu-id="2e6e0-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="2e6e0-301">次の情報は、各キャンペーンの [ **アタックの詳細** ] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2e6e0-302">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2e6e0-303">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="2e6e0-303">**Total users targeted**</span></span>

- <span data-ttu-id="2e6e0-304">**成功** した試行回数: 添付ファイルを開いた、またはダウンロードしてから開いたユーザーの数 (プレビューではカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="2e6e0-305">**全体的な成功率**: 対象となるユーザーの **合計試行回数** で計算されたパーセンテージ  /  。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2e6e0-306">**添付ファイルの最速開き時間**: キャンペーンの開始後、最初のユーザーが添付ファイルを開いたのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="2e6e0-307">**添付ファイルの平均開かれる時間**: 添付ファイルを開いたユーザーの数によって除算された、すべてのユーザーが添付ファイルを開くのにかかった時間の合計。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="2e6e0-308">**添付ファイルオープン成功率**: 計算されるパーセンテージ (添付ファイルを開いたユーザーの数)/ **対象ユーザー総数**。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="2e6e0-309">ブルートフォースパスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="2e6e0-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="2e6e0-310">次の情報は、各キャンペーンの [ **アタックの詳細** ] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2e6e0-311">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2e6e0-312">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="2e6e0-312">**Total users targeted**</span></span>

- <span data-ttu-id="2e6e0-313">**成功** した試行: 指定されたパスワードの1つを使用していることが検出されたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="2e6e0-314">**全体的な成功率**: 対象となるユーザーの **合計試行回数** で計算されたパーセンテージ  /  。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2e6e0-315">[ **侵害** されたユーザー] セクションに、影響を受けるユーザーの電子メールアドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="2e6e0-316">[ **エクスポート** ] をクリックすると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="2e6e0-317">パスワードスプレーアタックキャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="2e6e0-317">Password spray attack campaign results</span></span>

<span data-ttu-id="2e6e0-318">次の情報は、各キャンペーンの [ **アタックの詳細** ] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2e6e0-319">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2e6e0-320">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="2e6e0-320">**Total users targeted**</span></span>

- <span data-ttu-id="2e6e0-321">**成功** した試行: 指定されたパスワードを使用していることが検出されたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="2e6e0-322">**全体的な成功率**: 対象となるユーザーの **合計試行回数** で計算されたパーセンテージ  /  。</span><span class="sxs-lookup"><span data-stu-id="2e6e0-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
