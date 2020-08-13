---
title: ATP のアタックシミュレータ
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
ms.custom:
- seo-marvel-apr2020
description: アタックシミュレータを使用して、Microsoft 365 E5 または ATP Plan 2 組織でシミュレートされたフィッシングおよびパスワード攻撃を実行する方法について説明します。
ms.openlocfilehash: 6aa1d2027915caeffe2c20ba8f75f3658c336dbe
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653223"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="b0fab-103">ATP のアタックシミュレータ</span><span class="sxs-lookup"><span data-stu-id="b0fab-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="b0fab-104">**概要**グローバル管理者またはセキュリティ管理者で、組織に Office 365 Advanced Threat Protection プラン2があり、脅威の[調査および応答機能](office-365-ti.md)が含まれている場合は、攻撃シミュレータを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-104">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="b0fab-105">これにより、実際の攻撃が収益に影響を与える前に、脆弱なユーザーを特定して検出することができます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-105">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="b0fab-106">詳細については、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b0fab-107">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="b0fab-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b0fab-108">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="b0fab-109">アタックシミュレータは、**脅威管理**の \> **アタックシミュレータ**で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![脅威管理-アタックシミュレータ](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="b0fab-111">異なる Microsoft 365 サブスクリプション間でのアタックシミュレータの可用性の詳細については、「 [Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="b0fab-112">**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="b0fab-113">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b0fab-114">アタックシミュレータでキャンペーンを作成および管理するには、アカウントが多要素認証 (MFA) 用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="b0fab-115">手順については、「[多要素認証をセットアップ](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="b0fab-116">攻撃が正常に開始されるようにするには、シミュレートされた攻撃の実行に使用しているアカウントが多要素認証を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-116">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="b0fab-117">さらに、全体管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-117">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="b0fab-118">役割とアクセス許可の詳細については、「[セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-118">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="b0fab-119">フィッシングキャンペーンは、30日間、イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-119">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="b0fab-120">キャンペーンを開始した後、過去90日間は過去のキャンペーンデータを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-120">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="b0fab-121">アタックシミュレータに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="b0fab-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="b0fab-122">スピアーフィッシングキャンペーン</span><span class="sxs-lookup"><span data-stu-id="b0fab-122">Spear phishing campaigns</span></span>

<span data-ttu-id="b0fab-123">*フィッシング*とは、正規または信頼された送信者からのメッセージで機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="b0fab-124">*スピアーフィッシング*は、対象となる受信者に特化した、非常に集中的でカスタマイズされたコンテンツ (通常は、攻撃者による受信者の偵察後) を使用する、対象となるフィッシング攻撃です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-124">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="b0fab-125">グローバル管理者またはセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="b0fab-125">You are a global administrator or security administrator</span></span>

<span data-ttu-id="b0fab-126">アタックシミュレータでは、2つの異なる種類のスピアーフィッシングキャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="b0fab-127">少なくとも、グローバル管理者アカウントと、アタックシミュレータを使用するセキュリティ管理者に対して、[多要素認証/条件付きアクセス](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b0fab-127">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="b0fab-128">(理想的には、組織内のすべてのユーザーに対して多要素認証/条件付きアクセスが有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-128">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="b0fab-129">これについて説明する既定のページはテストのみで、フィッシングメッセージを認識するためのヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-129">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に表示されること](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="b0fab-131">指定するカスタムページ (URL)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="b0fab-132">**スピアーフィッシング (添付ファイル)**: 攻撃により、受信者がメッセージ内の .docx または .pdf 添付ファイルを開くように誘導しようとします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="b0fab-133">添付ファイルには、既定のフィッシングリンクと同じ内容が含まれていますが、最初の文は "" という \<Display Name\> メッセージが最近の電子メールメッセージとして表示されています。</span><span class="sxs-lookup"><span data-stu-id="b0fab-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="b0fab-134">現時点では、アタックシミュレータのスピアーフィッシングキャンペーンは期限切れになりません。</span><span class="sxs-lookup"><span data-stu-id="b0fab-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="b0fab-135">スピアーフィッシングキャンペーンを作成する</span><span class="sxs-lookup"><span data-stu-id="b0fab-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="b0fab-136">スピアーフィッシングキャンペーンの重要な部分は、対象の受信者に送信される電子メールメッセージのルックアンドフィールです。</span><span class="sxs-lookup"><span data-stu-id="b0fab-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="b0fab-137">電子メールメッセージを作成して構成するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="b0fab-138">**組み込みの電子メールテンプレートを使用**する: 2 つの組み込みテンプレートを利用できます: [**賞品 Giveaway** ] および [**給与の更新**]。</span><span class="sxs-lookup"><span data-stu-id="b0fab-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="b0fab-139">キャンペーンを作成および開始するときに、テンプレートから、電子メールのプロパティをいくつか、すべて、またはまったくカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b0fab-140">**再利用可能な電子メールテンプレートを作成**する: 電子メールテンプレートを作成して保存すると、今後のスピアーフィッシングキャンペーンで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="b0fab-141">キャンペーンを作成および開始するときに、テンプレートから、電子メールのプロパティをいくつか、すべて、またはまったくカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b0fab-142">**ウィザードで電子メールメッセージを作成**する: スピアーフィッシングキャンペーンを作成して起動すると、ウィザードで直接電子メールメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="b0fab-143">手順 1 (省略可能): カスタム電子メールテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="b0fab-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="b0fab-144">組み込みのテンプレートのいずれかを使用する場合、またはウィザードで直接電子メールメッセージを作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="b0fab-145">セキュリティ & コンプライアンスセンターで、[**脅威管理**] [ \> **アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b0fab-146">[**アタックのシミュレート**] ページの [**スピアーフィッシング (資格情報のハーベスト)** ] セクションまたは [**スピアーフィッシング (添付ファイル)** ] セクションで、[アタックの**詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="b0fab-147">テンプレートを作成する場所は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="b0fab-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="b0fab-148">テンプレートで使用可能なオプションは、どちらの種類のフィッシング攻撃でも同じです。</span><span class="sxs-lookup"><span data-stu-id="b0fab-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="b0fab-149">開かれた [**アタックの詳細**] ページの [**フィッシングテンプレート**] セクションで、[**テンプレートの作成**] 領域の [**新しいテンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="b0fab-150">新しいポップアップで [**フィッシングテンプレートの構成**] ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="b0fab-151">[**開始**] ステップに、テンプレートの一意の表示名を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="b0fab-152">[**電子メールの詳細の構成**] ステップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="b0fab-153">**From (名前)**: メッセージの送信者に使用する表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b0fab-154">**From (電子メール)**: 送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="b0fab-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="b0fab-155">[**フィッシングログインサーバーの URL**]: ドロップダウンをクリックし、一覧から使用可能な url のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b0fab-156">これは、ユーザーがクリックしたくなる URL です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b0fab-157">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="b0fab-157">The choices are:</span></span>

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
     > - <span data-ttu-id="b0fab-158">すべての Url は、https ではなく、意図的に http になっています。</span><span class="sxs-lookup"><span data-stu-id="b0fab-158">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="b0fab-159">URL 評価サービスでは、これらの Url の1つ以上が安全でないと識別されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b0fab-160">フィッシングキャンペーンで URL を使用する前に、サポートされている web ブラウザーで URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="b0fab-161">**ユーザー設定のランディングページの URL**: ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に実行される、オプションのランディングページを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b0fab-162">このリンクにより、既定のランディングページが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-162">This link replaces the default landing page.</span></span> <span data-ttu-id="b0fab-163">たとえば、社内の認識トレーニングがある場合は、その URL をここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b0fab-164">**Category**: 現在、この設定は使用されていません (入力した内容はすべて無視されます)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="b0fab-165">**Subject**: 電子メールメッセージの**件名**フィールド。</span><span class="sxs-lookup"><span data-stu-id="b0fab-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b0fab-166">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b0fab-167">[**電子メールの作成**] ステップで、電子メールメッセージの本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b0fab-168">[**電子メール**] タブ (リッチ html エディター) または [**ソース**] タブ (生の html コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b0fab-169">必要に応じて、HTML 形式を単純にすることも複雑にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b0fab-170">受信者の電子メールクライアントでのメッセージの believability を向上させるために、画像とテキストを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b0fab-171">`${username}`受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b0fab-172">`${loginserverurl}`前の手順で検出された**フィッシングログインサーバーの URL**値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="b0fab-173">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b0fab-174">[**確認**] ステップで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="b0fab-175">手順 2: スピアーフィッシングキャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="b0fab-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="b0fab-176">セキュリティ & コンプライアンスセンターで、[**脅威管理**] [ \> **アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b0fab-177">[**アタックのシミュレート**] ページで、作成するキャンペーンの種類に応じて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="b0fab-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b0fab-178">[**スピアーフィッシング (資格情報のハーベスト)** ] セクションで、[**アタックの起動**] をクリックするか、[**アタックの詳細**の \> **起動攻撃**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b0fab-179">[**スピアーフィッシング (添付ファイル)** ] セクションで、[**アタックの起動**] をクリックするか、[**アタックの詳細** \> を**起動**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b0fab-180">新しいポップアップで [**フィッシング攻撃の構成**] ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b0fab-181">**開始**ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b0fab-182">[**名前**] ボックスに、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="b0fab-183">後でウィザードで電子メールメッセージを作成するので、[**テンプレートの使用**] をクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="b0fab-184">[**テンプレートを使用する**] をクリックし、組み込みまたはカスタムの電子メールテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="b0fab-185">テンプレートを選択すると、テンプレートに基づいて [**名前**] ボックスに自動的に入力されますが、名前を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![フィッシング開始ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="b0fab-187">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b0fab-188">[**ターゲット受信者**] ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b0fab-189">[**アドレス帳**] をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b0fab-190">対象となる受信者ごとに、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b0fab-191">検索条件を入力せずに [**フィルター**と**適用**] をクリックすると、すべての受信者が返されてキャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b0fab-192">[**インポート**]、[**ファイルのインポート**] の順にクリックして、電子メールアドレスのコンマ区切り値 (CSV) または行区切りのファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b0fab-193">各行には、受信者の電子メールアドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b0fab-194">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b0fab-195">[**電子メールの詳細の構成**] ステップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="b0fab-196">**開始**ステップでテンプレートを選択した場合、これらの値のほとんどは既に構成されていますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="b0fab-197">**From (名前)**: メッセージの送信者に使用する表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b0fab-198">**From (電子メール)**: 送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="b0fab-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="b0fab-199">組織の電子メールドメインから本物または偽の電子メールアドレスを入力することも、本物または偽の外部電子メールアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="b0fab-200">組織からの有効な送信者の電子メールアドレスは、受信者の電子メールクライアントで実際に解決されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="b0fab-201">[**フィッシングログインサーバーの URL**]: ドロップダウンをクリックし、一覧から使用可能な url のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b0fab-202">これは、ユーザーがクリックしたくなる URL です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b0fab-203">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="b0fab-203">The choices are:</span></span>

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
     > - <span data-ttu-id="b0fab-204">すべての Url は、https ではなく、意図的に http になっています。</span><span class="sxs-lookup"><span data-stu-id="b0fab-204">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="b0fab-205">URL 評価サービスでは、これらの Url の1つ以上が安全でないと識別されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b0fab-206">フィッシングキャンペーンで URL を使用する前に、サポートされている web ブラウザーで URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b0fab-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="b0fab-207">URL を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-207">You are required to select a URL.</span></span> <span data-ttu-id="b0fab-208">**スピアーフィッシング (添付)** キャンペーンの場合は、次の手順でメッセージの本文からリンクを削除できます (それ以外の場合、メッセージにはリンク**と**添付ファイルの両方が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-208">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="b0fab-209">**添付ファイルの種類**: この設定は、**スピアーフィッシング (添付ファイル)** キャンペーンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b0fab-210">ドロップダウンをクリックし、[] を選択し**ます。.DOCX**また**は**リストから PDF を表示します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="b0fab-211">[**添付ファイル名**]: この設定は、**スピアーフィッシング (添付ファイル)** キャンペーンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b0fab-212">.Docx または .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="b0fab-213">**ユーザー設定のランディングページの URL**: ユーザーがフィッシングリンクをクリックして資格情報を入力した場合に実行される、オプションのランディングページを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b0fab-214">このリンクにより、既定のランディングページが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-214">This link replaces the default landing page.</span></span> <span data-ttu-id="b0fab-215">たとえば、社内の認識トレーニングがある場合は、その URL をここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b0fab-216">**Subject**: 電子メールメッセージの**件名**フィールド。</span><span class="sxs-lookup"><span data-stu-id="b0fab-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b0fab-217">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b0fab-218">[**電子メールの作成**] ステップで、電子メールメッセージの本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b0fab-219">**開始**手順でテンプレートを選択した場合、メッセージ本文は既に構成されていますが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="b0fab-220">[**電子メール**] タブ (リッチ html エディター) または [**ソース**] タブ (生の html コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b0fab-221">必要に応じて、HTML 形式を単純にすることも複雑にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b0fab-222">受信者の電子メールクライアントでのメッセージの believability を向上させるために、画像とテキストを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b0fab-223">`${username}`受信者の名前を挿入します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b0fab-224">`${loginserverurl}`[**フィッシングログインサーバーの URL**の値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="b0fab-225">**スピアーフィッシング (添付)** キャンペーンの場合は、メッセージの本文からリンクを削除する必要があります (それ以外の場合、メッセージにはリンク**と**添付ファイルの両方が含まれ、リンククリックは添付ファイルキャンペーンで追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![電子メール本文の作成](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="b0fab-227">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b0fab-228">[**確認**] ステップで、[**完了**] をクリックしてキャンペーンを開始します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b0fab-229">フィッシングメッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="b0fab-230">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="b0fab-230">Password attack campaigns</span></span>

<span data-ttu-id="b0fab-231">*パスワード攻撃*は、組織内のユーザーアカウントのパスワードを推測しようと試みます。通常、攻撃者が1つ以上の有効なユーザーアカウントを識別した後。</span><span class="sxs-lookup"><span data-stu-id="b0fab-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="b0fab-232">アタックシミュレータでは、2つの異なる種類のパスワード攻撃キャンペーンを使用して、ユーザーのパスワードの複雑さをテストできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="b0fab-233">**ブルートフォースパスワード (辞書攻撃)**:*ブルートフォース*または*辞書*攻撃では、ユーザーアカウントのパスワードの大規模な辞書ファイルが使用されます。これは、1つのアカウントに対して多数のパスワードを使用することを望んでいます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="b0fab-234">パスワードのロックアウトが正しくないと、ブルートフォースパスワード攻撃を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="b0fab-235">辞書攻撃の場合、1つまたは複数のパスワードを指定して (手動で入力またはアップロードされたファイルで)、1人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="b0fab-236">**パスワードのスプレー攻撃**:*パスワードのスプレー*攻撃では、ユーザーアカウントの一覧と同じように慎重にパスワードを使用します (1 つのパスワードを複数のアカウントに対して使用します)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="b0fab-237">パスワードのスプレー攻撃は、ブルートフォースパスワード攻撃よりも検知するのは困難です (攻撃者が、ユーザーの誤ったパスワードロックアウトを防ぐリスクなしに、1つまたは数百のアカウントに対して1つのパスワードを試行したときに成功する可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="b0fab-238">パスワードのスプレー攻撃では、1つのパスワードのみを指定して、1人または複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="b0fab-239">アタックシミュレータのパスワード攻撃は、エンドポイントにユーザー名とパスワードの基本的な認証要求を渡すので、他の認証方法 (AD FS、パスワードハッシュ同期、パススルー、Ping フェデレーションなど) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="b0fab-240">MFA が有効になっているユーザーは、パスワード攻撃が実際のパスワードを試行しても、常にエラーとして登録されます (つまり、MFA ユーザーがキャンペーンの**成功試行**回数に表示されることはありません)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="b0fab-241">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-241">This is the expected result.</span></span> <span data-ttu-id="b0fab-242">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="b0fab-243">パスワード攻撃キャンペーンを作成および開始する</span><span class="sxs-lookup"><span data-stu-id="b0fab-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="b0fab-244">セキュリティ & コンプライアンスセンターで、[**脅威管理**] [ \> **アタックシミュレータ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b0fab-245">[**アタックのシミュレート**] ページで、作成するキャンペーンの種類に応じて、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="b0fab-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b0fab-246">[**ブルートフォースパスワード (辞書攻撃)** ] セクションで、[**アタックの起動**] をクリックするか、[アタックの**詳細** \> を**起動**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b0fab-247">[**パスワードのスプレーアタック**] セクションで、[**アタックの起動**] をクリックするか、[**アタックの詳細**の \> **起動攻撃**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b0fab-248">**パスワード攻撃の構成**ウィザードが新しいポップアップで開始されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b0fab-249">[**開始**] ステップで、キャンペーンの一意の表示名を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="b0fab-250">[**ターゲットユーザー** ] ステップで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b0fab-251">[**アドレス帳**] をクリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b0fab-252">対象となる受信者ごとに、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0fab-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b0fab-253">検索条件を入力せずに [**フィルター**と**適用**] をクリックすると、すべての受信者が返されてキャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b0fab-254">[**インポート**]、[**ファイルのインポート**] の順にクリックして、電子メールアドレスのコンマ区切り値 (CSV) または行区切りのファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b0fab-255">各行には、受信者の電子メールアドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b0fab-256">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b0fab-257">[**アタック設定の選択**] ステップで、キャンペーンの種類に基づいて、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="b0fab-258">**ブルートフォースパスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="b0fab-259">**パスワードを手動で入力**します。 [enter**キーを押してパスワードを追加**します] ボックスにパスワードを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="b0fab-260">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="b0fab-261">**辞書ファイルからのパスワードのアップロード**: [**アップロード**] をクリックして、各行に1つのパスワードを含む既存のテキストファイルをインポートします。最後の行は空白にします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="b0fab-262">テキストファイルのサイズは 10 MB 以下でなければなりません。また、3万を超えるパスワードを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0fab-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="b0fab-263">**パスワードのスプレーアタック**: [アタック] ボックスで**使用するパスワードには**、1つのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="b0fab-264">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b0fab-265">[**確認**] ステップで、[**完了**] をクリックしてキャンペーンを開始します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b0fab-266">指定したパスワードは、指定したユーザーに対して試行されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="b0fab-267">キャンペーン結果の表示</span><span class="sxs-lookup"><span data-stu-id="b0fab-267">View campaign results</span></span>

<span data-ttu-id="b0fab-268">キャンペーンを開始した後、メインの [**攻撃のシミュレート**] ページで進行状況と結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="b0fab-269">アクティブなキャンペーンには、ステータスバー、完成したパーセンテージの値、および (ユーザーの合計数) のカウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="b0fab-270">[**更新**] ボタンをクリックすると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="b0fab-271">[**終了**] をクリックして、アクティブなキャンペーンを停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="b0fab-272">キャンペーンが完了すると、[**アタックが完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="b0fab-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="b0fab-273">次のいずれかの操作を実行して、キャンペーンの結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="b0fab-274">[シミュレートされた**アタック**のメイン] ページで、キャンペーンの名前の下にある [**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="b0fab-275">[アタックの**シミュレーション**] ページで、攻撃の種類についてセクションの [**アタックの詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0fab-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="b0fab-276">開かれた [**アタックの詳細**] ページで、[**アタックの履歴**] セクションでキャンペーンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="b0fab-277">上記のいずれかの操作を行うと、[**アタックの詳細**] というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="b0fab-278">各種類のキャンペーンでこのページで使用できる情報については、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="b0fab-279">スピアーフィッシング (資格情報のハーベスト) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="b0fab-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="b0fab-280">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b0fab-281">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b0fab-282">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="b0fab-282">**Total users targeted**</span></span>

- <span data-ttu-id="b0fab-283">**成功**した試行: リンクをクリック**して**資格情報 (*任意*のユーザー名とパスワード値) を入力したユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b0fab-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="b0fab-284">**全体的な成功率**: 対象となるユーザーの**合計試行回数**で計算されたパーセンテージ  /  **Total users targeted**。</span><span class="sxs-lookup"><span data-stu-id="b0fab-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b0fab-285">**[最速] クリック**: キャンペーンの開始後、最初のユーザーがリンクをクリックするのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="b0fab-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="b0fab-286">**平均クリック**数: すべてのユーザーがリンクをクリックすると、リンクをクリックしたユーザーの数で割った時間の合計。</span><span class="sxs-lookup"><span data-stu-id="b0fab-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="b0fab-287">**[成功率]**: 計算されたパーセンテージ (リンクをクリックしたユーザーの数)/**対象ユーザーの合計**数。</span><span class="sxs-lookup"><span data-stu-id="b0fab-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="b0fab-288">**最高の資格情報**: キャンペーンを開始した後、最初のユーザーが資格情報を入力するのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="b0fab-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="b0fab-289">**平均資格情報**: ユーザーの資格情報を入力したユーザーの数で割った資格情報の入力にかかった時間の合計。</span><span class="sxs-lookup"><span data-stu-id="b0fab-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="b0fab-290">**資格情報の成功率**: 計算の対象となるパーセンテージ (資格情報を入力したユーザー数)/**対象ユーザーの合計**数。</span><span class="sxs-lookup"><span data-stu-id="b0fab-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="b0fab-291">**リンクがクリック**された、1日あたりの**資格情報が入力**された番号を示す棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="b0fab-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="b0fab-292">クリックされた**リンク**、指定された**資格情報**、およびキャンペーンの**None**パーセンテージを示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="b0fab-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="b0fab-293">[**侵害**されたユーザー] セクションに、リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="b0fab-294">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="b0fab-294">The user's email address</span></span>

  - <span data-ttu-id="b0fab-295">リンクをクリックした日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="b0fab-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="b0fab-296">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="b0fab-296">The client IP address.</span></span>

  - <span data-ttu-id="b0fab-297">ユーザーの Windows および web ブラウザーのバージョンに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="b0fab-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="b0fab-298">[**エクスポート**] をクリックすると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="b0fab-299">スピアーフィッシング (添付ファイル) のキャンペーン結果</span><span class="sxs-lookup"><span data-stu-id="b0fab-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="b0fab-300">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b0fab-301">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b0fab-302">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="b0fab-302">**Total users targeted**</span></span>

- <span data-ttu-id="b0fab-303">**成功**した試行回数: 添付ファイルを開いた、またはダウンロードしてから開いたユーザーの数 (プレビューではカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="b0fab-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="b0fab-304">**全体的な成功率**: 対象となるユーザーの**合計試行回数**で計算されたパーセンテージ  /  **Total users targeted**。</span><span class="sxs-lookup"><span data-stu-id="b0fab-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b0fab-305">**添付ファイルの最速開き時間**: キャンペーンの開始後、最初のユーザーが添付ファイルを開いたのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="b0fab-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="b0fab-306">**添付ファイルの平均開かれる時間**: 添付ファイルを開いたユーザーの数によって除算された、すべてのユーザーが添付ファイルを開くのにかかった時間の合計。</span><span class="sxs-lookup"><span data-stu-id="b0fab-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="b0fab-307">**添付ファイルオープン成功率**: 計算されるパーセンテージ (添付ファイルを開いたユーザーの数)/**対象ユーザー総数**。</span><span class="sxs-lookup"><span data-stu-id="b0fab-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="b0fab-308">ブルートフォースパスワード (辞書攻撃) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="b0fab-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="b0fab-309">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b0fab-310">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b0fab-311">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="b0fab-311">**Total users targeted**</span></span>

- <span data-ttu-id="b0fab-312">**成功**した試行: 指定されたパスワードの1つを使用していることが検出されたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b0fab-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="b0fab-313">**全体的な成功率**: 対象となるユーザーの**合計試行回数**で計算されたパーセンテージ  /  **Total users targeted**。</span><span class="sxs-lookup"><span data-stu-id="b0fab-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b0fab-314">[**侵害**されたユーザー] セクションに、影響を受けるユーザーの電子メールアドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="b0fab-315">[**エクスポート**] をクリックすると、結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="b0fab-316">パスワードスプレーアタックキャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="b0fab-316">Password spray attack campaign results</span></span>

<span data-ttu-id="b0fab-317">次の情報は、各キャンペーンの [**アタックの詳細**] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b0fab-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b0fab-318">キャンペーンの期間 (開始日時と終了日/時刻) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0fab-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b0fab-319">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="b0fab-319">**Total users targeted**</span></span>

- <span data-ttu-id="b0fab-320">**成功**した試行: 指定されたパスワードを使用していることが検出されたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b0fab-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="b0fab-321">**全体的な成功率**: 対象となるユーザーの**合計試行回数**で計算されたパーセンテージ  /  **Total users targeted**。</span><span class="sxs-lookup"><span data-stu-id="b0fab-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
