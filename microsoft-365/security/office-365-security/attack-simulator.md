---
title: Office 365 の攻撃シミュレータ
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
description: Office 365 のグローバル管理者として、攻撃シミュレータを使用して、組織内で現実的な攻撃シナリオを実行できます。 これは、実際の攻撃によってビジネスに遭遇する前に、脆弱性のあるユーザーを特定して見つけるのに役立ちます。
ms.openlocfilehash: 6fb88e6b79c0949c7ddc26eabda2bb04ea1fa3bf
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957412"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="bfbb9-104">Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="bfbb9-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="bfbb9-105">**概要**Office 365 の全体管理者またはセキュリティ管理者で、組織に Office 365 Advanced Threat Protection プラン2があり、[脅威の調査および応答機能](office-365-ti.md)が含まれている場合は、攻撃シミュレータを使用して、組織内で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="bfbb9-106">これにより、実際の攻撃が収益に影響を与える前に、脆弱なユーザーを特定して検出することができます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="bfbb9-107">詳細については、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-107">Read this article to learn more.</span></span>

## <a name="the-attacks"></a><span data-ttu-id="bfbb9-108">攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-108">The Attacks</span></span>

<span data-ttu-id="bfbb9-109">現在、次に示す 3 種類の攻撃シミュレーションが利用できます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-109">Three kinds of attack simulations are currently available:</span></span>

- [<span data-ttu-id="bfbb9-110">資格情報ハーベストのスピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-110">Credential harvest spear-phishing attack</span></span>](#credential-harvest-spear-phishing-attack)

- [<span data-ttu-id="bfbb9-111">添付ファイルのスピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-111">Attachment spear-phishing attack</span></span>](#attachment-spear-phishing-attack)

- [<span data-ttu-id="bfbb9-112">パスワードスプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-112">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="bfbb9-113">ブルートフォース パスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-113">Brute-force password attack</span></span>](#brute-force-password-attack)

<span data-ttu-id="bfbb9-114">攻撃が正常に開始されるようにするには、シミュレートされた攻撃の実行に使用しているアカウントが多要素認証を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-114">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="bfbb9-115">さらに、Office 365 の全体管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-115">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="bfbb9-116">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-116">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="bfbb9-117">アタックシミュレータにアクセスするには、 &amp;セキュリティ/コンプライアンスセンターで、[ **Threat management** \> **アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-117">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bfbb9-118">開始する前に</span><span class="sxs-lookup"><span data-stu-id="bfbb9-118">Before you begin...</span></span>

<span data-ttu-id="bfbb9-119">自分と組織が、次のアタックシミュレータの要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-119">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>

- <span data-ttu-id="bfbb9-120">組織の電子メールは Exchange Online でホストされています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-120">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="bfbb9-121">(アタックシミュレータは、オンプレミスの電子メールサーバーでは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-121">(Attack Simulator is not available for on-premises email servers.)</span></span>

- <span data-ttu-id="bfbb9-122">Office 365 の全体管理者またはセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="bfbb9-122">You are an Office 365 global administrator or security administrator</span></span>

- <span data-ttu-id="bfbb9-123">フィッシングキャンペーンは、30日間の間イベントを収集して処理します。過去のキャンペーンデータは、キャンペーンが開始されてから90日以内に利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-123">Phishing campaigns will collect and process events for a period of 30 days, historical campaign data will be available for up to 90 days after the campaign is launched.</span></span>

- <span data-ttu-id="bfbb9-124">少なくとも1人の Office 365 グローバル管理者アカウントおよびセキュリティ管理者がアタックシミュレータを使用する場合は、[多要素認証/条件付きアクセス](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-124">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="bfbb9-125">(理想的には、組織内のすべてのユーザーに対して多要素認証/条件付きアクセスが有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-125">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

- <span data-ttu-id="bfbb9-126">組織に[Office 365 Advanced Threat Protection プラン 2](office-365-atp.md)があり、セキュリティ&amp;コンプライアンスセンターでアタックシミュレータが表示されている (**脅威管理** \>の**アタックシミュレータ**に移動)</span><span class="sxs-lookup"><span data-stu-id="bfbb9-126">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![脅威管理-アタックシミュレータ](../media/ThreatMgmt-AttackSimulator.png)

## <a name="credential-harvest-spear-phishing-attack"></a><span data-ttu-id="bfbb9-128">資格情報ハーベストのスピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-128">Credential harvest spear-phishing attack</span></span>

<span data-ttu-id="bfbb9-129">フィッシングとは、ソーシャルエンジニアリングスタイルの攻撃として分類された広範な攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-129">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="bfbb9-130">この攻撃は、スピアーフィッシングに重点を置いており、特定の個人または組織のグループを対象とした、より標的とされた攻撃に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-130">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="bfbb9-131">通常、一部の偵察を実行し、組織内の役員からのメールメッセージなど、受信者の信頼を生成する表示名を使用して、カスタマイズされた攻撃を行います。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-131">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="bfbb9-132">この攻撃は、表示名と送信元アドレスを変更することによって、メッセージの発信元の表示者を操作することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-132">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="bfbb9-133">スピアーフィッシング攻撃が成功すると、cyberattackers はユーザーの資格情報にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-133">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>

### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="bfbb9-134">スピアーフィッシング攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="bfbb9-134">To simulate a spear-phishing attack</span></span>

![電子メール本文の作成](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

<span data-ttu-id="bfbb9-136">リッチ HTML エディターは、**電子メール本文**フィールド自体で直接作成することも、html ソースで操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-136">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>

1. <span data-ttu-id="bfbb9-137">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-137">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="bfbb9-138">攻撃に対して適切なキャンペーン名を指定するか、テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-138">Specify a meaningful campaign name for the attack or select a template.</span></span>

   ![フィッシング開始ページ](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. <span data-ttu-id="bfbb9-140">対象の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-140">Specify the target recipients.</span></span> <span data-ttu-id="bfbb9-141">これは、組織内の個人またはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-141">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="bfbb9-142">攻撃を成功させるには、各対象となる受信者に Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-142">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>

   ![受信者の選択](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. <span data-ttu-id="bfbb9-144">フィッシング電子メールの詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-144">Configure the Phishing email details.</span></span>

   ![電子メールの詳細を構成する](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   <span data-ttu-id="bfbb9-146">HTML 形式は、キャンペーンのニーズに合わせて複雑な書式にすることも、基本的なものにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-146">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="bfbb9-147">電子メール形式は HTML であるため、画像とテキストを挿入して believability を強化できます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-147">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="bfbb9-148">受信したメッセージが受信側の電子メールクライアントでどのように表示されるかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-148">You have control on what the received message will look like in the receiving email client.</span></span>

5. <span data-ttu-id="bfbb9-149">[**差出人 (名前)** ] フィールドにテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-149">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="bfbb9-150">これは、受信側の電子メールクライアントの**表示名**に表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-150">This is the field that shows in the **Display Name** in the receiving email client.</span></span>

6. <span data-ttu-id="bfbb9-151">Text または**From**フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-151">Specify text or the **From** field.</span></span> <span data-ttu-id="bfbb9-152">これは、受信側の電子メールクライアントの送信者の電子メールアドレスとして表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-152">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

   <span data-ttu-id="bfbb9-153">組織内に既存の電子メール名前空間を入力できます (これにより、受信側クライアントで電子メールアドレスが実際に解決されるようになり、非常に高い信頼モデルを使用できるようになります)。または、外部電子メールアドレスを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-153">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="bfbb9-154">指定した電子メールアドレスは、実際に存在する必要はありませんが、などの有効な SMTP アドレスの形式に従う`user@domainname.extension`必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-154">The email address that you specify does not have to actually exist, but it does need to follow the format of a valid SMTP address, such as `user@domainname.extension`.</span></span>

7. <span data-ttu-id="bfbb9-155">ドロップダウンセレクターを使用して、攻撃の対象となるコンテンツの種類を反映するフィッシングのログインサーバーの URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-155">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="bfbb9-156">文書の配信、技術、給与など、さまざまなテーマを選択できるようにするための Url が用意されています。これは事実上、対象ユーザーがクリックするよう求められる URL です。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-156">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>

8. <span data-ttu-id="bfbb9-157">カスタムのランディングページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-157">Specify a custom landing page URL.</span></span> <span data-ttu-id="bfbb9-158">これを使用すると、成功した攻撃の終了時に指定した URL にユーザーがリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-158">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="bfbb9-159">たとえば、内部の認識トレーニングがある場合は、ここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-159">If you have internal awareness training, for example, you can specify that here.</span></span>

9. <span data-ttu-id="bfbb9-160">[**件名**] フィールドのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-160">Specify text for the **Subject** field.</span></span> <span data-ttu-id="bfbb9-161">これは、受信側の電子メールクライアントで**サブジェクト名**として表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-161">This is the field that shows as the **Subject Name** in the receiving email client.</span></span>

10. <span data-ttu-id="bfbb9-162">ターゲットが受け取る**電子メール本文**を作成します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-162">Compose the **Email body** that the target will receive.</span></span>

    <span data-ttu-id="bfbb9-163">`${username}`ターゲット名を電子メール本文に挿入します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-163">`${username}` inserts the targets name into the Email body.</span></span>

    <span data-ttu-id="bfbb9-164">`${loginserverurl}`ターゲットユーザーがクリックする URL を挿入します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-164">`${loginserverurl}` inserts the URL we want target users to click</span></span>

11. <span data-ttu-id="bfbb9-165">[**次へ**] を選択し、[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-165">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="bfbb9-166">スピアーフィッシングの電子メールメッセージは、移動先の受信者のメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-166">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span>

## <a name="attachment-spear-phishing-attack"></a><span data-ttu-id="bfbb9-167">添付ファイルのスピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-167">Attachment spear-phishing attack</span></span>

<span data-ttu-id="bfbb9-168">フィッシングとは、ソーシャルエンジニアリングスタイルの攻撃として分類された広範な攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-168">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="bfbb9-169">この攻撃は、添付ファイルのスピアーフィッシングに重点を置いており、特定の個人または組織の特定のグループを対象とした、より標的とされた攻撃に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-169">This attack is focused on attachment spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="bfbb9-170">通常、一部の偵察を実行し、組織内の役員からのメールメッセージなど、受信者の信頼を生成する表示名を使用して、カスタマイズされた攻撃を行います。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-170">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="bfbb9-171">この攻撃は、表示名と送信元アドレスを変更することによって、メッセージの発信元の人物を操作することに重点を置いていますが、今回は、ユーザーがクリックするための URL を提供するのではなく、t を取得しようとしている添付ファイルを提供しています。エンドユーザーがを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-171">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address, but this time as opposed to offering a URL to try and lure the end user to click, we offer an attachment that we are trying to get the end user to open.</span></span> 

### <a name="to-simulate-a-attachment-spear-phishing-attack"></a><span data-ttu-id="bfbb9-172">添付ファイルのスピアーフィッシング攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="bfbb9-172">To simulate a Attachment spear-phishing attack</span></span>

1. <span data-ttu-id="bfbb9-173">前述の手順を実行します。この時間は、ランディングページで**添付ファイル攻撃**をクリックしたことになります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-173">Follow the steps from above, having this time clicked on **Attachment Attack** on the landing page.</span></span>

2. <span data-ttu-id="bfbb9-174">ウィザードを実行すると、2つの構成オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-174">As you progress through the wizard, you see two options to configure.</span></span> <span data-ttu-id="bfbb9-175">**添付ファイルの種類**は、 **.docx**または **.pdf**の2種類の添付ファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-175">The **Attachment Type**, we support two attachment types, **.docx** or **.pdf**.</span></span> <span data-ttu-id="bfbb9-176">**添付ファイル名**。このフィールドを使用して、キャンペーンにわかりやすい添付ファイル名を作成します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-176">The **Attachment Name**, use this field to create a meaningful attachment name for the campaign.</span></span>

## <a name="password-spray-attack"></a><span data-ttu-id="bfbb9-177">パスワードスプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-177">Password-spray attack</span></span>

<span data-ttu-id="bfbb9-178">組織に対するパスワードスプレー攻撃は、通常、誤ったアクターがテナントから有効なユーザーの一覧を正常に取得した後に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-178">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="bfbb9-179">誤ったアクターは、ユーザーが使用する共通のパスワードを知っています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-179">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="bfbb9-180">これは、実行される安価な攻撃であり、ブルートフォースアプローチよりも検出が困難なため、広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-180">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>

<span data-ttu-id="bfbb9-181">この攻撃は、ユーザーの大規模なターゲットベースに対して共通のパスワードを指定することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-181">This attack focuses on letting you specify a common password against a large target base of users.</span></span>

<span data-ttu-id="bfbb9-182">**重要メモ**既に多要素認証が設定されているエンドユーザーアカウントに対してパスワードのスプレー攻撃を実行すると、レポート内のそれらのアカウントに対して失敗が発生します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-182">**Important Note** running the password spray attack against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="bfbb9-183">これは、パスワードのスプレー攻撃から保護するために、複数要素認証がプライマリ mechanims の1つになるためです。そのため、これが予想されます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-183">This is due to multi-factor authentication being one of the primary mechanims to help protect against password spray attacks, so is expected.</span></span>

### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="bfbb9-184">パスワードスプレー攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="bfbb9-184">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="bfbb9-185">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="bfbb9-186">攻撃に対して適切なキャンペーン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-186">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="bfbb9-187">対象の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-187">Specify the target recipients.</span></span> <span data-ttu-id="bfbb9-188">これは、組織内の個人またはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-188">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="bfbb9-189">攻撃を成功させるには、対象の受信者が Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-189">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="bfbb9-190">攻撃に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-190">Specify a password to use for the attack.</span></span> <span data-ttu-id="bfbb9-191">たとえば、よく使用される1つの関連パスワードと`Summer2019`して、を試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-191">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="bfbb9-192">別の方法`Fall2019`とし`Password1`て、またはの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-192">Another might be `Fall2019`, or `Password1`.</span></span>

5. <span data-ttu-id="bfbb9-193">[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-193">Choose **Finish** to launch the attack.</span></span>

## <a name="brute-force-password-attack"></a><span data-ttu-id="bfbb9-194">ブルートフォース パスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="bfbb9-194">Brute-force password attack</span></span>

<span data-ttu-id="bfbb9-195">通常、組織に対するブルートフォースパスワード攻撃は、誤ったアクターがテナントからキーユーザーの一覧を正常に取得した後に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-195">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="bfbb9-196">この攻撃は、1人のユーザーのアカウントで一連のパスワードを試行することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-196">This attack focuses on trying a set of passwords on a single user's account.</span></span>

<span data-ttu-id="bfbb9-197">**重要メモ**既に多要素認証が設定されているエンドユーザーアカウントに対してブルートフォースパスワード攻撃を実行すると、レポート内のそれらのアカウントに対する失敗が発生します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-197">**Important Note** running the brute-force password attacks against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="bfbb9-198">これは、多要素認証が、ブルートフォースパスワード攻撃から保護するために重要な mechanims の1つであるためです。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-198">This is due to multi-factor authentication being one of the primary mechanims to help protect against brute-force password attacks, so is expected.</span></span>

### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="bfbb9-199">ブルートフォースパスワード攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="bfbb9-199">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="bfbb9-200">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-200">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="bfbb9-201">攻撃に対して適切なキャンペーン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-201">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="bfbb9-202">ターゲットの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-202">Specify the target recipient.</span></span> <span data-ttu-id="bfbb9-203">攻撃を成功させるには、対象の受信者が Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-203">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="bfbb9-204">攻撃に使用するパスワードのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-204">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="bfbb9-205">これを行うには、パスワードの一覧にテキスト (.txt) ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-205">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="bfbb9-206">このテキストファイルは、ファイルサイズが 10 MB を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-206">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="bfbb9-207">1行に1つのパスワードを使用し、リスト内の最後のパスワードの後にハードリターンを含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-207">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>

5. <span data-ttu-id="bfbb9-208">[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-208">Choose **Finish** to launch the attack.</span></span>



<span data-ttu-id="bfbb9-209">[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照して、開発中のもの、ロールアウトされているもの、および既に起動しているものを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-209">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfbb9-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfbb9-210">See also</span></span>

[<span data-ttu-id="bfbb9-211">Office 365 Advanced Threat Protection サービスの説明</span><span class="sxs-lookup"><span data-stu-id="bfbb9-211">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="bfbb9-212">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bfbb9-212">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
