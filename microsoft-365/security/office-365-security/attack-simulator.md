---
title: Office 365 のアタックシミュレータ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: アタックシミュレータを使用して、Office 365 E5 または ATP Plan 2 組織でシミュレートされたフィッシングおよびパスワード攻撃を実行します。これは、実際の攻撃に遭遇する前に、脆弱性のあるユーザーを特定するのに役立ちます。
ms.openlocfilehash: 95b7af302a5dcc1987040c23a7dde867e2d09292
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637340"
---
# <a name="attack-simulator-in-office-365-atp"></a><span data-ttu-id="a4951-103">Office 365 のアタックシミュレータ</span><span class="sxs-lookup"><span data-stu-id="a4951-103">Attack Simulator in Office 365 ATP</span></span>

<span data-ttu-id="a4951-104">アタックシミュレータ in Office 365 Advanced Threat Protection プラン 2 (ATP Plan 2) を使用すると、組織内で現実的にシミュレートされたフィッシングおよびパスワード攻撃のキャンペーンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-104">Attack Simulator in Office 365 Advanced Threat Protection Plan 2 (ATP Plan 2) allows you to run realistic, but simulated phishing and password attack campaigns in your organization.</span></span> <span data-ttu-id="a4951-105">キャンペーンの結果を使用して、脆弱性のあるユーザーを特定し、教育することができます。</span><span class="sxs-lookup"><span data-stu-id="a4951-105">You can use the results of campaigns to identify and train vulnerable users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a4951-106">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a4951-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a4951-107">Office 365 セキュリティ & コンプライアンスセンターを開くには、に<https://protection.office.com/>移動します。</span><span class="sxs-lookup"><span data-stu-id="a4951-107">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="a4951-108">アタックシミュレータは、**脅威管理** \>の**アタックシミュレータ**で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-108">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![脅威管理-アタックシミュレータ](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="a4951-110">異なる Office 365 サブスクリプション間でのアタックシミュレータの可用性の詳細については、「 [office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4951-110">For more information about the availability of Attack Simulator across different Office 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="a4951-111">**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4951-111">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a4951-112">セキュリティ & コンプライアンスセンターの役割グループの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4951-112">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a4951-113">アタックシミュレータでキャンペーンを作成および管理するには、アカウントが多要素認証 (MFA) 用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4951-113">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="a4951-114">手順については、「[多要素認証をセットアップ](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4951-114">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="a4951-115">Exchange Online のメールボックスを使用しているユーザーに対しては、フィッシングまたはパスワード攻撃のキャンペーンのみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-115">You can only run phishing or password attack campaigns on users with mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="a4951-116">フィッシングキャンペーンは、30日間、イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="a4951-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="a4951-117">キャンペーンを開始した後、過去90日間は過去のキャンペーンデータを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a4951-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="a4951-118">アタックシミュレータに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="a4951-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="a4951-119">スピアーフィッシングキャンペーン</span><span class="sxs-lookup"><span data-stu-id="a4951-119">Spear phishing campaigns</span></span>

<span data-ttu-id="a4951-120">*フィッシング*とは、正規または信頼された送信者からのメッセージで機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="a4951-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="a4951-121">*スピアーフィッシング*は、対象となる受信者に特化した、非常に集中的でカスタマイズされたコンテンツ (通常は、攻撃者による受信者の偵察後) を使用する、対象となるフィッシング攻撃です。</span><span class="sxs-lookup"><span data-stu-id="a4951-121">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="a4951-122">フィッシングとスピアーフィッシングの詳細については、「[フィッシング](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4951-122">For more information about phishing and spear phishing, see [Phishing](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing).</span></span>

<span data-ttu-id="a4951-123">アタックシミュレータでは、2つの異なる種類のスピアーフィッシングキャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-123">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="a4951-124">**スピアーフィッシング (資格情報のハーベスト)**: 攻撃により、受信者がメッセージ内の URL をクリックするように誘導しようとします。</span><span class="sxs-lookup"><span data-stu-id="a4951-124">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="a4951-125">ユーザーがリンクをクリックすると、資格情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a4951-125">If they click the link, users are asked to enter their credentials.</span></span> <span data-ttu-id="a4951-126">その場合は、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4951-126">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="a4951-127">これについて説明する既定のページはテストのみで、フィッシングメッセージを認識するためのヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="a4951-127">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に表示されること](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="a4951-129">指定するカスタムページ (URL)。</span><span class="sxs-lookup"><span data-stu-id="a4951-129">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="a4951-130">**スピアーフィッシング (添付ファイル)**: 攻撃により、受信者がメッセージ内の .docx または .pdf 添付ファイルを開くように誘導しようとします。</span><span class="sxs-lookup"><span data-stu-id="a4951-130">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="a4951-131">添付ファイルには、既定のフィッシングリンクと同じコンテンツが含まれていますが\<、最初\>の文の先頭には "表示名があります。このメッセージは、最近使用した電子メールメッセージとして表示されています..."。</span><span class="sxs-lookup"><span data-stu-id="a4951-131">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="a4951-132">現時点では、アタックシミュレータのスピアーフィッシングキャンペーンは期限切れになりません。</span><span class="sxs-lookup"><span data-stu-id="a4951-132">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="a4951-133">スピアーフィッシングキャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="a4951-133">Create a spear phishing campaign</span></span>

<span data-ttu-id="a4951-134">スピアーフィッシングキャンペーンの重要な部分は、対象の受信者に送信される電子メールメッセージのルックアンドフィールです。</span><span class="sxs-lookup"><span data-stu-id="a4951-134">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="a4951-135">電子メールメッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a4951-135">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="a4951-136">**組み込みの電子メールテンプレートを使用**する: 2 つの組み込みテンプレートを利用できます: [**賞品 Giveaway** ] および [**給与の更新**]。</span><span class="sxs-lookup"><span data-stu-id="a4951-136">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="a4951-137">キャンペーンを作成および開始するときに、テンプレートから、電子メールのプロパティをいくつか、すべて、またはまったくカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4951-137">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="a4951-138">**再利用可能な電子メールテンプレートを作成**する: 電子メールテンプレートを作成して保存すると、今後のスピアーフィッシングキャンペーンで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a4951-138">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="a4951-139">キャンペーンを作成および開始するときに、テンプレートから、電子メールのプロパティをいくつか、すべて、またはまったくカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4951-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="a4951-140">**ウィザードで電子メールメッセージを作成**する: スピアーフィッシングキャンペーンを作成して起動すると、ウィザードで直接電子メールメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-140">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="a4951-141">手順 1 (省略可能): カスタム電子メールテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="a4951-141">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="a4951-142">組み込みのテンプレートのいずれかを使用する場合、またはウィザードで直接電子メールメッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-142">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="a4951-143">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> ] [**アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4951-143">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="a4951-144">[**アタックのシミュレート**] ページの [**スピアーフィッシング (資格情報のハーベスト)** ] セクションまたは [**スピアーフィッシング (添付ファイル)** ] セクションで、[アタックの**詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-144">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="a4951-145">テンプレートを作成する場所は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="a4951-145">It doesn't matter where you create the template.</span></span> <span data-ttu-id="a4951-146">テンプレートで使用可能なオプションは、どちらの種類のフィッシング攻撃でも同じです。</span><span class="sxs-lookup"><span data-stu-id="a4951-146">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="a4951-147">開かれた [**アタックの詳細**] ページの [**フィッシングテンプレート**] セクションで、[**テンプレートの作成**] 領域の [**新しいテンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-147">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="a4951-148">新しいポップアップで [**フィッシングテンプレートの構成**] ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="a4951-148">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="a4951-149">[**開始**] ステップに、テンプレートの一意の表示名を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-149">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="a4951-150">[**電子メールの詳細の構成**] ステップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a4951-150">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="a4951-151">**From (名前)**: メッセージの送信者に使用する表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4951-151">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="a4951-152">**From (電子メール)**: 送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="a4951-152">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="a4951-153">[**フィッシングログインサーバーの URL**]: ドロップダウンをクリックし、一覧から使用可能な url のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4951-153">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="a4951-154">これは、ユーザーがクリックしたくなる URL です。</span><span class="sxs-lookup"><span data-stu-id="a4951-154">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="a4951-155">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="a4951-155">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="a4951-156">すべての Url は、https ではなく、意図的に http になっています。</span><span class="sxs-lookup"><span data-stu-id="a4951-156">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="a4951-157">URL 評価サービスでは、これらの Url の1つ以上が安全でないと識別されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a4951-157">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="a4951-158">フィッシングキャンペーンで URL を使用する前に、サポートされている web ブラウザーで URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a4951-158">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="a4951-159">**ユーザー設定のランディングページの URL**: ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に実行される、オプションのランディングページを入力します。</span><span class="sxs-lookup"><span data-stu-id="a4951-159">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="a4951-160">このリンクにより、既定のランディングページが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a4951-160">This link replaces the default landing page.</span></span> <span data-ttu-id="a4951-161">たとえば、社内の認識トレーニングがある場合は、その URL をここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-161">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="a4951-162">**Category**: 現在、この設定は使用されていません (入力した内容はすべて無視されます)。</span><span class="sxs-lookup"><span data-stu-id="a4951-162">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="a4951-163">**Subject**: 電子メールメッセージの**件名**フィールド。</span><span class="sxs-lookup"><span data-stu-id="a4951-163">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="a4951-164">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-164">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a4951-165">[**電子メールの作成**] ステップで、電子メールメッセージの本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="a4951-165">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="a4951-166">[**電子メール**] タブ (リッチ html エディター) または [**ソース**] タブ (生の html コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-166">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="a4951-167">必要に応じて、HTML 形式を単純にすることも複雑にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-167">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="a4951-168">受信者の電子メールクライアントでのメッセージの believability を向上させるために、画像とテキストを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="a4951-168">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="a4951-169">`${username}`受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a4951-169">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="a4951-170">`${loginserverurl}`前の手順で検出された**フィッシングログインサーバーの URL**値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a4951-170">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="a4951-171">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-171">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="a4951-172">[**確認**] ステップで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-172">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="a4951-173">手順 2: スピアーフィッシングキャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="a4951-173">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="a4951-174">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> ] [**アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4951-174">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="a4951-175">[**アタックのシミュレート**] ページで、作成するキャンペーンの種類に応じて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="a4951-175">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="a4951-176">[**スピアーフィッシング (資格情報のハーベスト)** ] セクションで、[**アタックの起動**] をクリックするか、[**アタックの詳細** \>の**起動攻撃**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-176">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="a4951-177">[**スピアーフィッシング (添付ファイル)** ] セクションで、[**アタックの起動**] をクリックするか、[**アタックの詳細** \>を**起動**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-177">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="a4951-178">新しいポップアップで [**フィッシング攻撃の構成**] ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-178">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="a4951-179">**開始**ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a4951-179">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="a4951-180">[**名前**] ボックスに、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4951-180">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="a4951-181">後でウィザードで電子メールメッセージを作成するので、[**テンプレートの使用**] をクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="a4951-181">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="a4951-182">[**テンプレートを使用する**] をクリックし、組み込みまたはカスタムの電子メールテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4951-182">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="a4951-183">テンプレートを選択すると、テンプレートに基づいて [**名前**] ボックスに自動的に入力されますが、名前を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-183">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![フィッシング開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="a4951-185">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a4951-186">[**ターゲット受信者**] ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a4951-186">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="a4951-187">[**アドレス帳**] をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4951-187">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="a4951-188">対象となる受信者ごとに、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4951-188">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="a4951-189">検索条件を入力せずに [**フィルター**と**適用**] をクリックすると、すべての受信者が返されてキャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-189">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="a4951-190">[**インポート**]、[**ファイルのインポート**] の順にクリックして、電子メールアドレスのコンマ区切り値 (CSV) または行区切りのファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a4951-190">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="a4951-191">各行には、受信者の電子メールアドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4951-191">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="a4951-192">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-192">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a4951-193">[**電子メールの詳細の構成**] ステップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a4951-193">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="a4951-194">**開始**ステップでテンプレートを選択した場合、これらの値のほとんどは既に構成されていますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-194">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="a4951-195">**From (名前)**: メッセージの送信者に使用する表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4951-195">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="a4951-196">**From (電子メール)**: 送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="a4951-196">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="a4951-197">組織の電子メールドメインから本物または偽の電子メールアドレスを入力することも、本物または偽の外部電子メールアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-197">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="a4951-198">組織からの有効な送信者の電子メールアドレスは、受信者の電子メールクライアントで実際に解決されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-198">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="a4951-199">[**フィッシングログインサーバーの URL**]: ドロップダウンをクリックし、一覧から使用可能な url のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4951-199">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="a4951-200">これは、ユーザーがクリックしたくなる URL です。</span><span class="sxs-lookup"><span data-stu-id="a4951-200">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="a4951-201">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="a4951-201">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="a4951-202">すべての Url は、https ではなく、意図的に http になっています。</span><span class="sxs-lookup"><span data-stu-id="a4951-202">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="a4951-203">URL 評価サービスでは、これらの Url の1つ以上が安全でないと識別されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a4951-203">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="a4951-204">フィッシングキャンペーンで URL を使用する前に、サポートされている web ブラウザーで URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a4951-204">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="a4951-205">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4951-205">You are required to select a URL.</span></span> <span data-ttu-id="a4951-206"><b>スピアーフィッシング (添付)</b>キャンペーンの場合は、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンク<b>と</b>添付ファイルの両方が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="a4951-206">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="a4951-207">**添付ファイルの種類**: この設定は、**スピアーフィッシング (添付ファイル)** キャンペーンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-207">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="a4951-208">ドロップダウンをクリックし、[] を選択し**ます。.DOCX**また**は**リストから PDF を表示します。</span><span class="sxs-lookup"><span data-stu-id="a4951-208">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="a4951-209">[**添付ファイル名**]: この設定は、**スピアーフィッシング (添付ファイル)** キャンペーンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-209">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="a4951-210">.Docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4951-210">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="a4951-211">**ユーザー設定のランディングページの URL**: ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に実行される、オプションのランディングページを入力します。</span><span class="sxs-lookup"><span data-stu-id="a4951-211">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="a4951-212">このリンクにより、既定のランディングページが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a4951-212">This link replaces the default landing page.</span></span> <span data-ttu-id="a4951-213">たとえば、社内の認識トレーニングがある場合は、その URL をここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-213">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="a4951-214">**Subject**: 電子メールメッセージの**件名**フィールド。</span><span class="sxs-lookup"><span data-stu-id="a4951-214">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="a4951-215">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-215">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a4951-216">[**電子メールの作成**] ステップで、電子メールメッセージの本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="a4951-216">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="a4951-217">**開始**手順でテンプレートを選択した場合、メッセージ本文は既に構成されていますが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-217">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="a4951-218">[**電子メール**] タブ (リッチ html エディター) または [**ソース**] タブ (生の html コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-218">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="a4951-219">必要に応じて、HTML 形式を単純にすることも複雑にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-219">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="a4951-220">受信者の電子メールクライアントでのメッセージの believability を向上させるために、画像とテキストを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="a4951-220">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="a4951-221">`${username}`受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a4951-221">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="a4951-222">`${loginserverurl}`[**フィッシングログインサーバーの URL**の値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a4951-222">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="a4951-223">**スピアーフィッシング (添付)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンク**と**添付ファイルの両方が含まれ、リンククリックは添付ファイルキャンペーンで追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="a4951-223">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![電子メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="a4951-225">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-225">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="a4951-226">[**確認**] ステップで、[**完了**] をクリックしてキャンペーンを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4951-226">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="a4951-227">フィッシングメッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-227">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="a4951-228">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="a4951-228">Password attack campaigns</span></span>

<span data-ttu-id="a4951-229">*パスワード攻撃*は、組織内のユーザーアカウントのパスワードを推測しようと試みます。通常、攻撃者が1つ以上の有効なユーザーアカウントを識別した後。</span><span class="sxs-lookup"><span data-stu-id="a4951-229">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="a4951-230">アタックシミュレータでは、2つの異なる種類のパスワード攻撃キャンペーンを使用して、ユーザーのパスワードの複雑さをテストできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-230">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="a4951-231">**ブルートフォースパスワード (辞書攻撃)**:*ブルートフォース*または*辞書*攻撃では、ユーザーアカウントのパスワードの大規模な辞書ファイルが使用されます。これは、1つのアカウントに対して多数のパスワードを使用することを望んでいます。</span><span class="sxs-lookup"><span data-stu-id="a4951-231">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="a4951-232">パスワードのロックアウトが正しくないと、ブルートフォースパスワード攻撃を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="a4951-232">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="a4951-233">辞書攻撃の場合、1つまたは複数のパスワードを指定して (手動で入力またはアップロードされたファイルで)、1人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-233">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="a4951-234">**パスワードのスプレー攻撃**:*パスワードのスプレー*攻撃では、ユーザーアカウントの一覧と同じように慎重にパスワードを使用します (1 つのパスワードを複数のアカウントに対して使用します)。</span><span class="sxs-lookup"><span data-stu-id="a4951-234">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="a4951-235">パスワードのスプレー攻撃は、ブルートフォースパスワード攻撃よりも検知するのは困難です (攻撃者が、ユーザーの誤ったパスワードロックアウトを防ぐリスクなしに、1つまたは数百のアカウントに対して1つのパスワードを試行したときに成功する可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="a4951-235">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="a4951-236">パスワードのスプレー攻撃では、1つのパスワードのみを指定して、1人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-236">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="a4951-237">アタックシミュレータのパスワード攻撃は、エンドポイントにユーザー名とパスワードの基本的な認証要求を渡すので、他の認証方法 (AD FS、パスワードハッシュ同期、パススルー、Ping フェデレーションなど) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="a4951-237">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="a4951-238">MFA が有効になっているユーザーは、パスワード攻撃が実際のパスワードを試行しても、常にエラーとして登録されます (つまり、MFA ユーザーがキャンペーンの**成功試行**回数に表示されることはありません)。</span><span class="sxs-lookup"><span data-stu-id="a4951-238">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="a4951-239">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="a4951-239">This is the expected result.</span></span> <span data-ttu-id="a4951-240">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="a4951-240">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="a4951-241">パスワード攻撃キャンペーンを作成および開始する</span><span class="sxs-lookup"><span data-stu-id="a4951-241">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="a4951-242">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> ] [**アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4951-242">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="a4951-243">[**アタックのシミュレート**] ページで、作成するキャンペーンの種類に応じて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="a4951-243">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="a4951-244">[**ブルートフォースパスワード (辞書攻撃)** ] セクションで、 **[アタックの起動**] をクリックするか、[アタックの**詳細** \>を**起動**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-244">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="a4951-245">[**パスワードのスプレーアタック**] セクションで、[**アタックの起動**] をクリックするか、[**アタックの詳細** \>の**起動攻撃**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-245">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="a4951-246">**パスワード攻撃の構成**ウィザードが新しいポップアップで開始されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-246">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="a4951-247">[**開始**] ステップで、キャンペーンの一意の表示名を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-247">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="a4951-248">[**ターゲットユーザー** ] ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a4951-248">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="a4951-249">[**アドレス帳**] をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4951-249">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="a4951-250">対象となる受信者ごとに、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4951-250">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="a4951-251">検索条件を入力せずに [**フィルター**と**適用**] をクリックすると、すべての受信者が返されてキャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-251">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="a4951-252">[**インポート**]、[**ファイルのインポート**] の順にクリックして、電子メールアドレスのコンマ区切り値 (CSV) または行区切りのファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a4951-252">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="a4951-253">各行には、受信者の電子メールアドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4951-253">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="a4951-254">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-254">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a4951-255">[**アタック設定の選択**] ステップで、キャンペーンの種類に基づいて、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4951-255">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="a4951-256">**ブルートフォースパスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a4951-256">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="a4951-257">**パスワードを手動で入力**します。 [enter**キーを押してパスワードを追加**します] ボックスにパスワードを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a4951-257">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="a4951-258">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a4951-258">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="a4951-259">**辞書ファイルからのパスワードのアップロード**: [**アップロード**] をクリックして、各行に1つのパスワードを含む既存のテキストファイルをインポートします。最後の行は空白にします。</span><span class="sxs-lookup"><span data-stu-id="a4951-259">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="a4951-260">テキストファイルのサイズは 10 MB 以下でなければなりません。また、3万を超えるパスワードを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="a4951-260">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="a4951-261">**パスワードのスプレーアタック**: [アタック] ボックスで**使用するパスワードには**、1つのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a4951-261">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="a4951-262">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-262">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a4951-263">[**確認**] ステップで、[**完了**] をクリックしてキャンペーンを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4951-263">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="a4951-264">指定したパスワードは、指定したユーザーに対して試行されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-264">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="a4951-265">キャンペーン結果の表示</span><span class="sxs-lookup"><span data-stu-id="a4951-265">View campaign results</span></span>

<span data-ttu-id="a4951-266">キャンペーンを開始した後、メインの [**攻撃のシミュレート**] ページで進行状況と結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-266">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="a4951-267">アクティブなキャンペーンには、ステータスバー、完成したパーセンテージの値、および (ユーザーの合計数) のカウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-267">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="a4951-268">[**更新**] ボタンをクリックすると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-268">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="a4951-269">[**終了**] をクリックして、アクティブなキャンペーンを停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-269">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="a4951-270">キャンペーンが完了すると、[**アタックが完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="a4951-270">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="a4951-271">次のいずれかの操作を実行して、キャンペーンの結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-271">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="a4951-272">[シミュレートされた**アタック**のメイン] ページで、キャンペーンの名前の下にある [**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-272">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="a4951-273">[アタックの**シミュレーション**] ページで、攻撃の種類についてセクションの [**アタックの詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4951-273">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="a4951-274">開かれた [**アタックの詳細**] ページで、[**アタックの履歴**] セクションでキャンペーンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4951-274">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="a4951-275">上記のいずれかの操作を行うと、[**アタックの詳細**] というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-275">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="a4951-276">各種類のキャンペーンでこのページで使用できる情報については、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="a4951-276">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="a4951-277">スピアーフィッシング (資格情報のハーベスト) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="a4951-277">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="a4951-278">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-278">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a4951-279">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4951-279">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a4951-280">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="a4951-280">**Total users targeted**</span></span>

- <span data-ttu-id="a4951-281">**成功**した試行: リンクをクリック**して**資格情報 (*任意*のユーザー名とパスワード値) を入力したユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="a4951-281">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="a4951-282">**全体的な成功率**:**対象となるユーザーの合計\*\*\*\*試行回数** / で計算されたパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a4951-282">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="a4951-283">**[最速] クリック**: キャンペーンの開始後、最初のユーザーがリンクをクリックするのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="a4951-283">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="a4951-284">**平均クリック**数: すべてのユーザーがリンクをクリックすると、リンクをクリックしたユーザーの数で割った時間の合計。</span><span class="sxs-lookup"><span data-stu-id="a4951-284">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="a4951-285">**[成功率]**: 計算されたパーセンテージ (リンクをクリックしたユーザーの数)/**対象ユーザーの合計**数。</span><span class="sxs-lookup"><span data-stu-id="a4951-285">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="a4951-286">**最高の資格情報**: キャンペーンを開始した後、最初のユーザーが資格情報を入力するのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="a4951-286">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="a4951-287">**平均資格情報**: ユーザーの資格情報を入力したユーザーの数で割った資格情報の入力にかかった時間の合計。</span><span class="sxs-lookup"><span data-stu-id="a4951-287">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="a4951-288">**資格情報の成功率**: 計算の対象となるパーセンテージ (資格情報を入力したユーザー数)/**対象ユーザーの合計**数。</span><span class="sxs-lookup"><span data-stu-id="a4951-288">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="a4951-289">**リンクがクリック**された、1日あたりの**資格情報が入力**された番号を示す棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="a4951-289">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="a4951-290">クリックされた**リンク**、指定された**資格情報**、およびキャンペーンの**None**パーセンテージを示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="a4951-290">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="a4951-291">[**侵害**されたユーザー] セクションに、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-291">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="a4951-292">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="a4951-292">The user's email address</span></span>

  - <span data-ttu-id="a4951-293">リンクをクリックした日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="a4951-293">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="a4951-294">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a4951-294">The client IP address.</span></span>

  - <span data-ttu-id="a4951-295">ユーザーの Windows および web ブラウザーのバージョンに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="a4951-295">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="a4951-296">[**エクスポート**] をクリックすると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-296">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="a4951-297">スピアーフィッシング (添付ファイル) のキャンペーン結果</span><span class="sxs-lookup"><span data-stu-id="a4951-297">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="a4951-298">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-298">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a4951-299">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4951-299">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a4951-300">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="a4951-300">**Total users targeted**</span></span>

- <span data-ttu-id="a4951-301">**成功**した試行回数: 添付ファイルを開いた、またはダウンロードしてから開いたユーザーの数 (プレビューではカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="a4951-301">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="a4951-302">**全体的な成功率**:**対象となるユーザーの合計\*\*\*\*試行回数** / で計算されたパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a4951-302">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="a4951-303">**添付ファイルの最速開き時間**: キャンペーンの開始後、最初のユーザーが添付ファイルを開いたのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="a4951-303">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="a4951-304">**添付ファイルの平均開かれる時間**: 添付ファイルを開いたユーザーの数によって除算された、すべてのユーザーが添付ファイルを開くのにかかった時間の合計。</span><span class="sxs-lookup"><span data-stu-id="a4951-304">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="a4951-305">**添付ファイルオープン成功率**: 計算されるパーセンテージ (添付ファイルを開いたユーザーの数)/**対象ユーザー総数**。</span><span class="sxs-lookup"><span data-stu-id="a4951-305">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="a4951-306">ブルートフォースパスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="a4951-306">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="a4951-307">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-307">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a4951-308">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4951-308">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a4951-309">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="a4951-309">**Total users targeted**</span></span>

- <span data-ttu-id="a4951-310">**成功**した試行: 指定されたパスワードの1つを使用していることが検出されたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="a4951-310">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="a4951-311">**全体的な成功率**:**対象となるユーザーの合計\*\*\*\*試行回数** / で計算されたパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a4951-311">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="a4951-312">[**侵害**されたユーザー] セクションに、影響を受けるユーザーの電子メールアドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4951-312">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="a4951-313">[**エクスポート**] をクリックすると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="a4951-313">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="a4951-314">パスワードスプレーアタックキャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="a4951-314">Password spray attack campaign results</span></span>

<span data-ttu-id="a4951-315">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="a4951-315">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a4951-316">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4951-316">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a4951-317">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="a4951-317">**Total users targeted**</span></span>

- <span data-ttu-id="a4951-318">**成功**した試行: 指定されたパスワードを使用していることが検出されたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="a4951-318">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="a4951-319">**全体的な成功率**:**対象となるユーザーの合計\*\*\*\*試行回数** / で計算されたパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a4951-319">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
