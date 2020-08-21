---
title: ATP の攻撃シミュレータ
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
ms.custom:
- seo-marvel-apr2020
description: 管理者は、攻撃シミュレーターを使って Microsoft 365 E5 または ATP プラン 2 組織でシミュレートされたフィッシングやパスワード攻撃を実行する方法を学習できます。
ms.openlocfilehash: 017376d8002811398fe3ce2d94f7c207cd718a78
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825835"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="3b121-103">ATP の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="3b121-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="3b121-104">脅威の調査と対応の機能を含む Office 365 Advanced Threat Protection (ATP) プラン 2 を利用している [組織では、](office-365-ti.md)セキュリティ & コンプライアンス センターの攻撃シミュレータを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="3b121-105">これらのシミュレーションされた攻撃は、実際の攻撃が少なくとも行われる前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b121-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="3b121-106">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b121-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3b121-107">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="3b121-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3b121-108">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com/> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="3b121-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="3b121-109">攻撃シミュレータは、脅 **威管理攻** \> **撃シミュレータで利用できます**。</span><span class="sxs-lookup"><span data-stu-id="3b121-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="3b121-110">攻撃シミュレータに直接移動して、開きます <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="3b121-110">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="3b121-111">さまざまな Microsoft 365 サブスクリプションでの攻撃シミュレータの可用性について詳しくは [、「Office 365 Advanced Threat Protection サービスの説明」をご覧ください](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="3b121-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="3b121-112">組織の管理役割グループまたはセキュリティ管理者**役割グループの\*\*\*\*メンバーである**必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b121-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="3b121-113">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3b121-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="3b121-114">攻撃シミュレーターでキャンペーンを作成および管理するには、アカウントを多要素認証 (MFA) 用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b121-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="3b121-115">手順については、「多要素 [認証のセットアップ」をご覧ください](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="3b121-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="3b121-116">フィッシング キャンペーンは、30 日間、イベントを収集して処理します。</span><span class="sxs-lookup"><span data-stu-id="3b121-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="3b121-117">過去 90 日間キャンペーンの履歴データは、キャンペーンを起動した後 90 日間利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3b121-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="3b121-118">攻撃シミュレータに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="3b121-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="3b121-119">スペア フィッシング キャンペーン</span><span class="sxs-lookup"><span data-stu-id="3b121-119">Spear phishing campaigns</span></span>

<span data-ttu-id="3b121-120">*フィッシングは、* メール攻撃から、当人や信頼できる送信者から見えるメッセージ内の機密情報をやり取りしようとする、メール攻撃に対する一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="3b121-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="3b121-121">*スピア フィッシング* は、ターゲットとなる受信者に特にカスタマイズされたフォーカスされたカスタマイズされたコンテンツ (通常は、攻撃者による受信者の再調整後) を使用する、ターゲットとなるフィッシング攻撃です。</span><span class="sxs-lookup"><span data-stu-id="3b121-121">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="3b121-122">攻撃シミュレータでは、2 種類のスピア フィッシング キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-122">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="3b121-123">**スピア フィッシング (資格情報の取得)**: 攻撃では、受信者がメッセージ内の URL をクリックするために受信者を移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="3b121-123">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="3b121-124">ユーザーがリンクをクリックすると、資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="3b121-124">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="3b121-125">追加されている場合は、次の場所のいずれかに要求されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-125">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="3b121-126">これを説明する既定のページは単なるテストであり、フィッシング メッセージを認識するためのヒントが示されています。</span><span class="sxs-lookup"><span data-stu-id="3b121-126">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![フィッシング リンクをクリックして資格情報を入力したユーザーに対して表示される内容](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="3b121-128">指定したカスタム ページ (URL)。</span><span class="sxs-lookup"><span data-stu-id="3b121-128">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="3b121-129">**スピア フィッシング (添付ファイル):** 攻撃によって、受信者がメッセージ内の .docx または .pdf の添付ファイルを開くことを要求します。</span><span class="sxs-lookup"><span data-stu-id="3b121-129">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="3b121-130">添付ファイルには、既定のフィッシング リンクと同じコンテンツが含まれますが、最初の文は「」で始めたので、このメッセージが開いた最近の \<Display Name\> 電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-130">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="3b121-131">現在、攻撃シミュレーターのスピア フィッシング キャンペーンには有効期限がありません。</span><span class="sxs-lookup"><span data-stu-id="3b121-131">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="3b121-132">スピア フィッシング キャンペーンの作成</span><span class="sxs-lookup"><span data-stu-id="3b121-132">Create a spear phishing campaign</span></span>

<span data-ttu-id="3b121-133">スピア フィッシング キャンペーンでかかじの重要な部分は、対象となる受信者に送信されるメール メッセージのルック アンド フィールです。</span><span class="sxs-lookup"><span data-stu-id="3b121-133">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="3b121-134">メール メッセージを作成して構成するには、以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3b121-134">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="3b121-135">**組み込みの電子メール テンプレートを使用する**: 2 つの組み込みテンプレートが使用できる: **Prize Giveaway** and **Payroll Update**。</span><span class="sxs-lookup"><span data-stu-id="3b121-135">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="3b121-136">キャンペーンを作成して起動する場合、テンプレートからのメール プロパティの一部またはすべてをカスタマイズしたり、まったくカスタマイズしたり、まったくカスタマイズしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3b121-136">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="3b121-137">**再利用可能なメール テンプレートを作成します**。メール テンプレートを作成して保存した後、将来の速度で再び使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-137">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="3b121-138">キャンペーンを作成して起動する場合、テンプレートからのメール プロパティの一部またはすべてをカスタマイズしたり、まったくカスタマイズしたり、まったくカスタマイズしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3b121-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="3b121-139">**ウィザードでメール メッセージを作成:** ウィザードでは、スピア フィッシング キャンペーンを作成して起動すると、メール メッセージを直接作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3b121-139">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="3b121-140">手順 1 (省略可能): カスタム電子メール テンプレートの作成</span><span class="sxs-lookup"><span data-stu-id="3b121-140">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="3b121-141">組み込みのテンプレートのいずれかを使用するか、ウィザードで電子メール メッセージを直接作成する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-141">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="3b121-142">コンプライアンス センターからセキュリティ &シミ **ュレー** \> **ターに移動します**。</span><span class="sxs-lookup"><span data-stu-id="3b121-142">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="3b121-143">**[Simulate attacks]** ページの **[Simear Phishing (Credentials Harvest)]** セクションまたは **[Spear Phishing (添付ファイル)] セクション**で **、[Attack Details]**(攻撃の詳細) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-143">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="3b121-144">テンプレートを作成する場所は問題に含まれません。</span><span class="sxs-lookup"><span data-stu-id="3b121-144">It doesn't matter where you create the template.</span></span> <span data-ttu-id="3b121-145">テンプレートで使用できるオプションは、どちらの種類のフィッシング攻撃と同じです。</span><span class="sxs-lookup"><span data-stu-id="3b121-145">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="3b121-146">[攻 **撃の詳細]** ページが開いたら、[ **フィッシング テンプレート** ] セクションの [ **テンプレートの作成** ] 領域で、[新しいテンプレート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b121-146">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="3b121-147">フ **ィッシング テンプレートの構成ウィザード** は、新しいポップアップで開始されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-147">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="3b121-148">[スタート **] 操作リスト** で、テンプレート用の一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3b121-148">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="3b121-149">メールの **詳細を構成する手順** では、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3b121-149">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="3b121-150">**From (Name)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="3b121-150">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="3b121-151">**From (Email):** 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="3b121-151">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="3b121-152">**フィッシング ログイン サーバーの URL:** ドロップダウンをクリックし、一覧から利用可能な URL のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-152">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="3b121-153">これは、ユーザーがクリックするのを要求される URL です。</span><span class="sxs-lookup"><span data-stu-id="3b121-153">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="3b121-154">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="3b121-154">The choices are:</span></span>

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
     > - <span data-ttu-id="3b121-155">すべての URL は、https ではなく意図的に http です。</span><span class="sxs-lookup"><span data-stu-id="3b121-155">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="3b121-156">URL レピュの評価サービスにより、これらの URL の 1 つ以上が安全でないと識別される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b121-156">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="3b121-157">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL を利用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b121-157">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="3b121-158">**カスタム ランチ ページの URL:** フィッシング リンクをクリックしてユーザーの資格情報を入力した場合に、オプションのランフィング ページを入力します。</span><span class="sxs-lookup"><span data-stu-id="3b121-158">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="3b121-159">既定のランド ページは、このリンクに置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="3b121-159">This link replaces the default landing page.</span></span> <span data-ttu-id="3b121-160">たとえば、内部認識トレーニングを使用している場合、ここで URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-160">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="3b121-161">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span><span class="sxs-lookup"><span data-stu-id="3b121-161">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="3b121-162">**Subject**: **メール** メッセージの "件名" フィールド。</span><span class="sxs-lookup"><span data-stu-id="3b121-162">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="3b121-163">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-163">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="3b121-164">メールの **作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="3b121-164">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="3b121-165">[電子 **メール]** タブ (リッチ HTML エディター) または [ソース] **タブ** (元の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-165">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="3b121-166">HTML 形式は、必要に応じて複雑にしたり複雑にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="3b121-166">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="3b121-167">画像やテキストを挿入して、受信者の電子メール クライアントでメッセージの可能性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-167">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="3b121-168">`${username}` に指定された受信者の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b121-168">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="3b121-169">`${loginserverurl}` 前の手順 **のフィッシング ログイン サーバーの URL** 値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="3b121-169">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="3b121-170">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-170">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="3b121-171">[確認] **ステップで** 、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b121-171">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="3b121-172">手順 2: スピア フィッシング キャンペーンを作成して起動する</span><span class="sxs-lookup"><span data-stu-id="3b121-172">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="3b121-173">コンプライアンス センターからセキュリティ &シミ **ュレー** \> **ターに移動します**。</span><span class="sxs-lookup"><span data-stu-id="3b121-173">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="3b121-174">**[Simulate attacks] (** 攻撃のシミュレーション) ページで、作成するキャンペーンの種類に基づいて次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-174">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="3b121-175">**[Spear Phishing (Credentials Harvest)]** セクションで **、[Launch Attack] (攻撃の**起動) をクリックするか、[Launch Details Launch **Attack] (攻撃の詳細起動攻撃** \> **) をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b121-175">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="3b121-176">**[Spear Phishing (添付ファイル)] セクションで、[Launch Attack] (攻撃の起動)** **をクリックするか**、[Launch Details Launch **Attack] (攻撃の詳細起動攻撃)** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b121-176">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="3b121-177">フ **ィッシング攻撃の** 構成ウィザードは、新しいポップアップで開始されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-177">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="3b121-178">開始 **ステップで** 、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b121-178">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="3b121-179">[名前 **] ボックス** に、キャンペーンの一意の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b121-179">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="3b121-180">[テンプレートの **使用] をクリックしないでください**。ウィザードの後の手順で電子メール メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b121-180">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="3b121-181">[ **テンプレートの使用] を** クリックし、組み込みまたはカスタムの電子メール テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-181">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="3b121-182">テンプレートを選択すると **、[名前]** ボックスはテンプレートに基づいて自動的に設定されます。名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-182">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![フィッシングのスタート ページ](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="3b121-184">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-184">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3b121-185">ターゲット受信者 **の手順** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b121-185">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="3b121-186">[ **アドレス帳] を** クリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-186">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="3b121-187">対象となる各受信者には、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3b121-187">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="3b121-188">[フィルター] **をクリック** して **検索** 条件を入力しないで適用すると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-188">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="3b121-189">[ **インポート** ] **をクリック** して、コンマ区切り値 (CSV) またはメール アドレスの行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3b121-189">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="3b121-190">各行には、受信者のメール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b121-190">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="3b121-191">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-191">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3b121-192">メールの **詳細を構成する手順** では、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3b121-192">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="3b121-193">開始手順でテンプレートを選択 **した場合** 、これらの値の大部分は既に構成されていますが、値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-193">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="3b121-194">**From (Name)**: メッセージ送信者に使用される表示名。</span><span class="sxs-lookup"><span data-stu-id="3b121-194">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="3b121-195">**From (Email):** 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="3b121-195">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="3b121-196">組織のメール ドメインからの実際のまたはやらない電子メール アドレスを入力するか、実際または fake 外部のメール アドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-196">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="3b121-197">組織からの有効な送信者の電子メール アドレスは、実際には受信者の電子メール クライアントで解決されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-197">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="3b121-198">**フィッシング ログイン サーバーの URL:** ドロップダウンをクリックし、一覧から利用可能な URL のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-198">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="3b121-199">これは、ユーザーがクリックするのを要求される URL です。</span><span class="sxs-lookup"><span data-stu-id="3b121-199">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="3b121-200">3 つの選択肢は次のものです。</span><span class="sxs-lookup"><span data-stu-id="3b121-200">The choices are:</span></span>

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
     > - <span data-ttu-id="3b121-201">すべての URL は、https ではなく意図的に http です。</span><span class="sxs-lookup"><span data-stu-id="3b121-201">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="3b121-202">URL レピュの評価サービスにより、これらの URL の 1 つ以上が安全でないと識別される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b121-202">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="3b121-203">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL を利用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b121-203">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="3b121-204">URL の選択を要求されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-204">You are required to select a URL.</span></span> <span data-ttu-id="3b121-205">**スピア フィッシング (添付ファイル)** キャンペーンの場合、メッセージの本文から次の手順でリンクを削除することができます (そのリンクがない場合、メッセージにはリンクと添付**ファイルの両方**が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="3b121-205">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="3b121-206">**添付ファイル**の種類: この設定は **スピア フィッシング (添付ファイル)** キャンペーンでのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="3b121-206">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="3b121-207">ドロップダウンをクリックして、 **DOCX または** **.一覧の PDF。**</span><span class="sxs-lookup"><span data-stu-id="3b121-207">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="3b121-208">**添付ファイル**名: この設定は **スピア フィッシング (添付ファイル)** キャンペーンでのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="3b121-208">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="3b121-209">.docx 添付ファイルまたは .pdf 添付ファイルのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b121-209">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="3b121-210">**カスタム ランチ ページの URL:** フィッシング リンクをクリックしてユーザーの資格情報を入力した場合に、オプションのランフィング ページを入力します。</span><span class="sxs-lookup"><span data-stu-id="3b121-210">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="3b121-211">既定のランド ページは、このリンクに置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="3b121-211">This link replaces the default landing page.</span></span> <span data-ttu-id="3b121-212">たとえば、内部認識トレーニングを使用している場合、ここで URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-212">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="3b121-213">**Subject**: **メール** メッセージの "件名" フィールド。</span><span class="sxs-lookup"><span data-stu-id="3b121-213">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="3b121-214">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-214">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="3b121-215">メールの **作成手順** で、電子メール メッセージのメッセージ本文を作成します。</span><span class="sxs-lookup"><span data-stu-id="3b121-215">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="3b121-216">開始手順でテンプレートを選択 **した** 場合、メッセージ本文は既に構成されていますが、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3b121-216">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="3b121-217">[電子 **メール]** タブ (リッチ HTML エディター) または [ソース] **タブ** (元の HTML コード) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-217">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="3b121-218">HTML 形式は、必要に応じて複雑にしたり複雑にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="3b121-218">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="3b121-219">画像やテキストを挿入して、受信者の電子メール クライアントでメッセージの可能性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-219">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="3b121-220">`${username}` に指定された受信者の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b121-220">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="3b121-221">`${loginserverurl}` フィ **ッシング ログイン サーバーの URL 値を挿入** します。</span><span class="sxs-lookup"><span data-stu-id="3b121-221">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="3b121-222">**スピア フィッシング (添付ファイル)** キャンペーンの場合、メッセージの本文からリンクを削除する必要があります (リンクと添付ファイルの両方**and**が含まれ、リンクのクリックは添付ファイル キャンペーンで追跡されません)。</span><span class="sxs-lookup"><span data-stu-id="3b121-222">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![メールの作成本文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="3b121-224">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-224">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="3b121-225">確認手順 **の [** 完了] を **クリック** してキャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="3b121-225">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="3b121-226">フィッシング メッセージは、対象の受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-226">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="3b121-227">パスワード攻撃キャンペーン</span><span class="sxs-lookup"><span data-stu-id="3b121-227">Password attack campaigns</span></span>

<span data-ttu-id="3b121-228">パスワード *攻撃は* 、通常、攻撃者が 1 つ以上の有効なユーザー アカウントを識別した後、組織内のユーザー アカウントのパスワードを取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="3b121-228">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="3b121-229">攻撃シミュレータでは、ユーザーのパスワードの複雑さをテストするための、2 種類のパスワード攻撃キャンペーンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-229">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="3b121-230">\**ブルート フォース パスワード (ディクショナリ攻撃):\*\*\*ブルート*フォースや辞書攻撃は、1 つのアカウント (1 つのアカウントに対して多数のパスワード) を実行できるユーザー アカウントに大きなディクショナリ ファイルを使用します。 *dictionary*</span><span class="sxs-lookup"><span data-stu-id="3b121-230">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="3b121-231">パスワード ロックアウトが正しくないと、ブルート フォース パスワード攻撃を切り分けられます。</span><span class="sxs-lookup"><span data-stu-id="3b121-231">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="3b121-232">辞書攻撃には、(手動で入力する、またはアップロードしたファイル) 1 つまたは複数のパスワードを指定して、1 つまたは複数のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-232">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="3b121-233">**パスワード スプレー攻撃:** パスワード *スプレー攻撃* では、ユーザー アカウントの一覧 (多数のアカウントに対して 1 つのパスワード) に対して、注意して検討されたパスワードが、注意して使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-233">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="3b121-234">パスワード スプレー攻撃は、ブルート フォース パスワード攻撃よりも危険です (攻撃者が数数または数日のアカウントに対して 1 つのパスワードを試行すると、パスワードのロックアウトが正しくない可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="3b121-234">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="3b121-235">パスワード スプレー攻撃の場合、試用するパスワードを 1 つだけ指定できます。ユーザーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3b121-235">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="3b121-236">攻撃シミュレータのパスワード攻撃は、ユーザー名とパスワードの基本認証要求をエンドポイントに渡すため、他の認証方法 (AD FS、パスワード ハッシュ同期、パススルー、PingFederate など) でも動作します。</span><span class="sxs-lookup"><span data-stu-id="3b121-236">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="3b121-237">MFA が有効になっているユーザーの場合は、パスワード攻撃により実際のパスワードが試行されたとしても、必ず失敗として登録されます (つまり、MFA ユーザーはキャンペーンの **成功** 回数として表示されません)。</span><span class="sxs-lookup"><span data-stu-id="3b121-237">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="3b121-238">これは予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="3b121-238">This is the expected result.</span></span> <span data-ttu-id="3b121-239">MFA は、パスワード攻撃から保護するための主要な方法です。</span><span class="sxs-lookup"><span data-stu-id="3b121-239">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="3b121-240">パスワード攻撃キャンペーンを作成して立つ</span><span class="sxs-lookup"><span data-stu-id="3b121-240">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="3b121-241">コンプライアンス センターからセキュリティ &シミ **ュレー** \> **ターに移動します**。</span><span class="sxs-lookup"><span data-stu-id="3b121-241">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="3b121-242">**[Simulate attacks] (** 攻撃のシミュレーション) ページで、作成するキャンペーンの種類に基づいて次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-242">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="3b121-243">[ブ **ルート フォース パスワード (ディクシエーション攻撃)] セクション** で、[ **攻撃の起動** ] をクリックするか、[攻撃の **詳細起動攻撃]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b121-243">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="3b121-244">] の **[Password spray attack] セクションで、[Launch** **Attack] (攻撃の起動) をクリックするか** 、[攻撃の **詳細起動攻撃** \> **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b121-244">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="3b121-245">パスワード **攻撃の構成ウィザード** は、新しいポップアップで開始されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-245">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="3b121-246">[スタート **] ステップ** で、キャンペーンの一意の表示名を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3b121-246">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="3b121-247">[ターゲット **ユーザー] の** 手順で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b121-247">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="3b121-248">[ **アドレス帳] を** クリックして、キャンペーンの受信者 (ユーザーまたはグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-248">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="3b121-249">対象となる各受信者には、Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3b121-249">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="3b121-250">[フィルター] **をクリック** して **検索** 条件を入力しないで適用すると、すべての受信者が返され、キャンペーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-250">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="3b121-251">[ **インポート** ] **をクリック** して、コンマ区切り値 (CSV) またはメール アドレスの行区切りファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3b121-251">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="3b121-252">各行には、受信者のメール アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b121-252">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="3b121-253">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-253">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3b121-254">攻撃 **の設定を選択する** 手順では、キャンペーンの種類に基づいて行う処理を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b121-254">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="3b121-255">**ブルート フォース パスワード (辞書攻撃)**: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b121-255">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="3b121-256">**パスワードを手動で入力:** パスワードを追加 **するには、Enter キーを押** してパスワードを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3b121-256">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="3b121-257">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3b121-257">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="3b121-258">**辞書ファイルからパスワードをアップロードする**: [ **アップロード] を** クリックすると、各行に 1 つのパスワードが含まれている既存のテキスト ファイルと、最後の行が空白になっています。</span><span class="sxs-lookup"><span data-stu-id="3b121-258">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="3b121-259">テキスト ファイルのサイズは 10 MB 以下にする必要があります。30000 を超えるパスワードを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b121-259">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="3b121-260">**パスワード スプレー攻撃**: 攻 **撃ボックスで使用するパスワードに** 、1 つのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="3b121-260">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="3b121-261">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-261">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="3b121-262">確認手順 **の [** 完了] を **クリック** してキャンペーンを起動します。</span><span class="sxs-lookup"><span data-stu-id="3b121-262">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="3b121-263">指定したパスワードは、指定したユーザーに対して試行されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-263">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="3b121-264">キャンペーンの結果の表示</span><span class="sxs-lookup"><span data-stu-id="3b121-264">View campaign results</span></span>

<span data-ttu-id="3b121-265">キャンペーンを起動した後は、メインの [シミュレート攻撃] ページで進行 **状況と結果を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-265">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="3b121-266">アクティブ キャンペーンのステータス バー、完了したパーセンテージ値と "(ユーザーの合計数)" 数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-266">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="3b121-267">[ **更新] ボタン** をクリックすると、アクティブなキャンペーンの進行状況が更新されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-267">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="3b121-268">You can also click **Terminate** to stop an active campaign.</span><span class="sxs-lookup"><span data-stu-id="3b121-268">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="3b121-269">キャンペーンが完了したら、攻撃のステータスが **変更されます**。</span><span class="sxs-lookup"><span data-stu-id="3b121-269">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="3b121-270">次のいずれかの操作を実行すると、キャンペーンの結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-270">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="3b121-271">メインのシ **ミュレート攻撃のページで** 、キャン **ペ** ーンの名前の下の [レポートの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-271">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="3b121-272">[メインの **シミュレーション攻撃] ページで、** 攻撃 **の種類に** 関するセクションの [Attack Details] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b121-272">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="3b121-273">開いた **[攻撃** の詳細] ページで、[攻撃の履歴] セクションでキャンペーン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b121-273">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="3b121-274">前述のアクションのいずれかを行おり、Attack details という名前のページ **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3b121-274">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="3b121-275">このページでは、各種類のキャンペーンについてこのページで提供される情報について、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="3b121-275">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="3b121-276">スピア フィッシング (資格情報の取得) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="3b121-276">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="3b121-277">各キャンペーンの **[攻撃の** 詳細] ページでは、以下の情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-277">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="3b121-278">キャンペーンの期間 (開始日/時刻および終了日付/時刻)。</span><span class="sxs-lookup"><span data-stu-id="3b121-278">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="3b121-279">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="3b121-279">**Total users targeted**</span></span>

- <span data-ttu-id="3b121-280">**試行が成功**しました。リンクをクリックして資格情報 (**and**すべてのユーザー名とパスワード値)*を入力*したユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3b121-280">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="3b121-281">**全体の成功率**: 成功したユーザーの合計試行によって計算**された割**  /  **合の目標値**。</span><span class="sxs-lookup"><span data-stu-id="3b121-281">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="3b121-282">**最速のクリック**: キャンペーンを起動した後、最初のユーザーがリンクをクリックして、リンクをクリックした時間の長さ。</span><span class="sxs-lookup"><span data-stu-id="3b121-282">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="3b121-283">**平均クリック**: リンクをクリックしたユーザーの数でリンクをクリックしたすべてのユーザーに対して、リンクをクリックにかかった時間の合計。</span><span class="sxs-lookup"><span data-stu-id="3b121-283">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="3b121-284">**[成功率] を**クリックします。(リンクをクリックしたユーザーの数) によって計算された割 **合/ユーザーの合計**数。</span><span class="sxs-lookup"><span data-stu-id="3b121-284">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="3b121-285">**Credentials が最も**高速 : キャンペーンを起動した後に最初のユーザーが資格情報の入力に使用した時間。</span><span class="sxs-lookup"><span data-stu-id="3b121-285">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="3b121-286">**平均資格情報**: すべてのユーザーが資格情報を入力するために必要な時間の合計です。合計時間は、資格情報を入力したユーザーの数で除かれていません。</span><span class="sxs-lookup"><span data-stu-id="3b121-286">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="3b121-287">**Credentials Success Rate**( 資格情報の成功率) : (資格情報を入力したユーザーの数)、または対象 **ユーザーの合計**数が計算される割合。</span><span class="sxs-lookup"><span data-stu-id="3b121-287">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="3b121-288">リンククリックされた、および 1**日あたりに指定\*\*\*\*された番号を示**す棒グラフ。</span><span class="sxs-lookup"><span data-stu-id="3b121-288">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="3b121-289">キャンペーンのリンククリック、提供**された\*\*\*\*資格情報**、およびキャンペーン**の割合**なしを示す円グラフ。</span><span class="sxs-lookup"><span data-stu-id="3b121-289">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="3b121-290">侵 **害されたユーザー セクションには、** リンクをクリックしたユーザーの詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-290">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="3b121-291">ユーザーの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="3b121-291">The user's email address</span></span>

  - <span data-ttu-id="3b121-292">リンクをクリックした日時。</span><span class="sxs-lookup"><span data-stu-id="3b121-292">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="3b121-293">クライアント IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3b121-293">The client IP address.</span></span>

  - <span data-ttu-id="3b121-294">ユーザーの Windows と Web ブラウザーのバージョンに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="3b121-294">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="3b121-295">[エクスポート] **をクリック** すると、結果が CSV ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="3b121-295">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="3b121-296">スピア フィッシング (添付ファイル) キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="3b121-296">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="3b121-297">各キャンペーンの **[攻撃の** 詳細] ページでは、以下の情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-297">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="3b121-298">キャンペーンの期間 (開始日/時刻および終了日付/時刻)。</span><span class="sxs-lookup"><span data-stu-id="3b121-298">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="3b121-299">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="3b121-299">**Total users targeted**</span></span>

- <span data-ttu-id="3b121-300">**試行が成功**しました: 添付ファイルを開いたか、ダウンロードした (プレビューは表示されません) ユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3b121-300">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="3b121-301">**全体の成功率**: 成功したユーザーの合計試行によって計算**された割**  /  **合の目標値**。</span><span class="sxs-lookup"><span data-stu-id="3b121-301">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="3b121-302">**最速の添付ファイルの開く**時間: キャンペーンを起動した後に最初のユーザーが添付ファイルを開くのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="3b121-302">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="3b121-303">**Average attachment open time:** The sum of how long it to open the attachment divided by the number of users who opened the attachment.</span><span class="sxs-lookup"><span data-stu-id="3b121-303">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="3b121-304">**添付ファイルの開く成功**率: (添付ファイルを開いたユーザーの数) によって計算された割合/ **対象ユーザーの合計数**。</span><span class="sxs-lookup"><span data-stu-id="3b121-304">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="3b121-305">ブルート フォース パスワード (辞書攻撃) キャンペーン結果</span><span class="sxs-lookup"><span data-stu-id="3b121-305">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="3b121-306">各キャンペーンの **[攻撃の** 詳細] ページでは、以下の情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-306">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="3b121-307">キャンペーンの期間 (開始日/時刻および終了日付/時刻)。</span><span class="sxs-lookup"><span data-stu-id="3b121-307">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="3b121-308">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="3b121-308">**Total users targeted**</span></span>

- <span data-ttu-id="3b121-309">**試行が成功**しました: 指定されたパスワードのいずれかを使用していることの検出されたユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="3b121-309">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="3b121-310">**全体の成功率**: 成功したユーザーの合計試行によって計算**された割**  /  **合の目標値**。</span><span class="sxs-lookup"><span data-stu-id="3b121-310">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="3b121-311">侵 **害されたユーザー セクションには、影響** を受けるユーザーのメール アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b121-311">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="3b121-312">[エクスポート] **をクリック** すると、結果が CSV ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="3b121-312">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="3b121-313">パスワード スプレー攻撃キャンペーンの結果</span><span class="sxs-lookup"><span data-stu-id="3b121-313">Password spray attack campaign results</span></span>

<span data-ttu-id="3b121-314">各キャンペーンの **[攻撃の** 詳細] ページでは、以下の情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="3b121-314">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="3b121-315">キャンペーンの期間 (開始日/時刻および終了日付/時刻)。</span><span class="sxs-lookup"><span data-stu-id="3b121-315">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="3b121-316">**対象ユーザーの合計数**</span><span class="sxs-lookup"><span data-stu-id="3b121-316">**Total users targeted**</span></span>

- <span data-ttu-id="3b121-317">**試行が成功**しました: 指定されたパスワードを使用していると検出されたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3b121-317">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="3b121-318">**全体の成功率**: 成功したユーザーの合計試行によって計算**された割**  /  **合の目標値**。</span><span class="sxs-lookup"><span data-stu-id="3b121-318">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
