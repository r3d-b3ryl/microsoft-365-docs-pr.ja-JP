---
title: DLP ポリシーを作成、テスト、調整する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: この記事では、組織のニーズに応じて DLP ポリシーを作成、テスト、調整する方法について学習します。
ms.openlocfilehash: bd4857a2baefb22d789fc713a537d7e4a656718d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052085"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="ece38-103">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="ece38-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="ece38-104">データ損失防止 (DLP) は、機密情報の意図しない共有や偶発的な共有を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ece38-104">Data loss prevention (DLP) helps you prevent the unintentional or accidental sharing of sensitive information.</span></span>

<span data-ttu-id="ece38-105">DLP は、電子メール メッセージとファイルを調べて、クレジット カード番号などの機密情報を調べる。</span><span class="sxs-lookup"><span data-stu-id="ece38-105">DLP examines email messages and files for sensitive information, like a credit card number.</span></span> <span data-ttu-id="ece38-106">DLP を使用することで機密情報を検出し、次のようなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-106">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="ece38-107">監査目的でイベントを記録する</span><span class="sxs-lookup"><span data-stu-id="ece38-107">Log the event for auditing purposes</span></span>
- <span data-ttu-id="ece38-108">電子メールを送信またはファイルを共有しているエンド ユーザーに警告を表示する</span><span class="sxs-lookup"><span data-stu-id="ece38-108">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="ece38-109">メールまたはファイルの共有の実行を積極的にブロックする</span><span class="sxs-lookup"><span data-stu-id="ece38-109">Actively block the email or file sharing from taking place</span></span>

## <a name="permissions"></a><span data-ttu-id="ece38-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ece38-110">Permissions</span></span>

<span data-ttu-id="ece38-111">DLP ポリシーを作成するコンプライアンス チームのメンバーは、コンプライアンス センターへのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-111">Members of your compliance team who will create DLP policies need permissions to the Compliance Center.</span></span> <span data-ttu-id="ece38-112">既定では、テナント管理者はコンプライアンス担当者や他のユーザーにアクセス権を付与できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-112">By default, your tenant admin will have access can give compliance officers and other people access.</span></span> <span data-ttu-id="ece38-113">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ece38-113">Follow these steps:</span></span>
  
1. <span data-ttu-id="ece38-114">Microsoft 365 でグループを作成して、コンプライアンス責任者をグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="ece38-114">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="ece38-115">セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページで役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="ece38-115">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="ece38-116">役割グループの作成中に、[役割の選択] セクションを使用して、役割グループに次の役割を追加 **します**。</span><span class="sxs-lookup"><span data-stu-id="ece38-116">While creating the role group, use the **Choose Roles** section to add the following role to the role group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="ece38-117">**メンバーの選択** セクションを使用して、以前に作成した Microsoft 365 グループを役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="ece38-117">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="ece38-118">[表示のみ **] DLP コンプライアンス管理** 役割を使用して、DLP ポリシーおよび DLP レポートに対する表示専用の権限を持つ役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="ece38-118">Use the **View-Only DLP Compliance Management** role to create role group with view-only privileges to the DLP policies and DLP reports.</span></span>

<span data-ttu-id="ece38-119">詳細については、「[Give users access to the Office 365 Security & Compliance Center (Office 365 セキュリティ/コンプライアンス センターへのアクセス権をユーザーに付与する)](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ece38-119">For more information, see [Give users access to the Office 365 Compliance Center](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="ece38-120">ポリシーを適用しない DLP ポリシーを作成して適用するには、これらのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ece38-120">These permissions are required to create and apply a DLP policy not to enforce policies.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="ece38-121">DLP による機密情報の検出方法</span><span class="sxs-lookup"><span data-stu-id="ece38-121">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="ece38-122">DLP は、正規表現 (RegEx) パターンマッチングによって、特定のキーワードと一致するパターンとの近接性などの他のインジケーターと組み合わせて機密情報を検索します。</span><span class="sxs-lookup"><span data-stu-id="ece38-122">DLP finds sensitive information by regular expression (RegEx) pattern matching, in combination with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="ece38-123">たとえば、VISA クレジット カード番号の桁数は 16 桁です。</span><span class="sxs-lookup"><span data-stu-id="ece38-123">For example, a VISA credit card number has 16 digits.</span></span> <span data-ttu-id="ece38-124">ただし、これらの数字は、1111-1111-1111-1111、1111 1111 1111 1111、または 1111111111 など、さまざまな方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-124">But, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="ece38-125">16 桁の文字列は、必ずしもクレジット カード番号ではなく、ヘルプ デスク システムからのチケット番号、またはハードウェアのシリアル番号である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-125">Any 16-digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="ece38-126">クレジット カード番号と無害な 16 桁の数字列の違いを判断するために計算が実行され (チェックサム)、番号がさまざまなクレジット カード ブランドの既知のパターンに一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ece38-126">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="ece38-127">DLP が"VISA" や "AMEX" などのキーワード (クレジット カードの有効期限になる可能性のある近日の値) を検出した場合、DLP は、そのデータを使用して、文字列がクレジット カード番号であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ece38-127">If DLP finds keywords such as "VISA" or "AMEX", near date values that might be the credit card expiry date, DLP also uses that data to help it decide whether the string is a credit card number or not.</span></span>

<span data-ttu-id="ece38-128">つまり、DLP は、電子メール内の次の 2 つの文字列の違いを認識するのに十分スマートです。</span><span class="sxs-lookup"><span data-stu-id="ece38-128">In other words, DLP is smart enough to recognize the difference between these two strings of text in an email:</span></span>

- <span data-ttu-id="ece38-129">「新しいノート PC を注文できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-129">"Can you order me a new laptop.</span></span> <span data-ttu-id="ece38-130">自分の VISA 番号 1111-1111-1111-1111、有効期限 11/22 を使用し、お持ちになったときに推定配信日を送信してください。</span><span class="sxs-lookup"><span data-stu-id="ece38-130">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it."</span></span>
- <span data-ttu-id="ece38-131">「ノート PC のシリアル番号は 2222-2222-2222-2222 で、2010 年 11 月 11 日に購入されました。</span><span class="sxs-lookup"><span data-stu-id="ece38-131">"My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="ece38-132">ところで、私の旅行ビザはまだ承認されていますか?</span><span class="sxs-lookup"><span data-stu-id="ece38-132">By the way, is my travel visa approved yet?"</span></span>

<span data-ttu-id="ece38-133">各 [情報の種類が検出される方法](sensitive-information-type-entity-definitions.md) については、「機密情報の種類エンティティ定義」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ece38-133">See [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="ece38-134">データ損失防止を開始する場所</span><span class="sxs-lookup"><span data-stu-id="ece38-134">Where to start with data loss prevention</span></span>

<span data-ttu-id="ece38-135">データ漏洩のリスクが完全に明らかではない場合、DLP の実装をどこから始めるべきかを正確に判断することは困難です。</span><span class="sxs-lookup"><span data-stu-id="ece38-135">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="ece38-136">幸い、DLP ポリシーは "テスト モード" で実行でき、有効にする前に効果と精度を測定できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-136">Fortunately, DLP policies can be run in "test mode", allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="ece38-137">Exchange Online の DLP ポリシーは、Exchange 管理センターを介して管理できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-137">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="ece38-138">ただし、セキュリティ/コンプライアンス センターを介してすべてのワークロードの DLP ポリシーを構成できるため、この記事のデモではこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="ece38-138">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="ece38-139">セキュリティ セキュリティ & コンプライアンス センターには、[データ損失防止ポリシー] の下に DLP **ポリシーがあります**  >  。</span><span class="sxs-lookup"><span data-stu-id="ece38-139">In the Security & Compliance Center, you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="ece38-140">[開始 **するポリシーの作成** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ece38-140">Choose **Create a policy** to start.</span></span>

<span data-ttu-id="ece38-141">Microsoft 365 には、ポリシーの作成に使用できる [さまざまな DLP](what-the-dlp-policy-templates-include.md) ポリシー テンプレートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="ece38-141">Microsoft 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create policies.</span></span> <span data-ttu-id="ece38-142">例えば、ここがオーストラリアの企業だとしましょう。</span><span class="sxs-lookup"><span data-stu-id="ece38-142">Let's say that you're an Australian business.</span></span> <span data-ttu-id="ece38-143">オーストラリアのテンプレートをフィルター処理し、[財務]、[医療と健康]、および [プライバシー] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-143">You can filter the templates on Australia, and choose Financial, Medical and Health, and Privacy.</span></span>

![国または地域を選択するオプション](../media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="ece38-145">このデモンストレーションでは、オーストラリアの個人を特定できる情報 (PII) データを選択します。これには、オーストラリアのタックス ファイル ナンバー (TFN) および運転免許証番号の情報の種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ece38-145">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![ポリシー テンプレートを選択するオプション](../media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="ece38-147">新しい DLP ポリシーに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="ece38-147">Give your new DLP policy a name.</span></span> <span data-ttu-id="ece38-148">規定の名前は DLP ポリシー テンプレートと一致しますが、同じテンプレートから複数のポリシーを作成できるため、よりわかりやすい独自の名前を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-148">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![ポリシーに名前を付けるオプション](../media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="ece38-150">ポリシーを適用する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ece38-150">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="ece38-151">DLP ポリシーは Exchange Online、SharePoint Online、および OneDrive for Business に適用できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-151">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="ece38-152">このポリシーは、すべての場所に適用されるように構成したまま残します。</span><span class="sxs-lookup"><span data-stu-id="ece38-152">I am going to leave this policy configured to apply to all locations.</span></span>

![すべての場所を選択するオプション](../media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="ece38-154">最初のポリシー **設定手順** で、今のところ既定値を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-154">At the first **Policy Settings** step, just accept the defaults for now.</span></span> <span data-ttu-id="ece38-155">DLP ポリシーをカスタマイズできますが、既定の設定は開始する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ece38-155">You can customize DLP policies, but the defaults are a fine place to start.</span></span>

![保護するコンテンツの種類をカスタマイズするオプション](../media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="ece38-157">[次へ] をクリックすると、追加の [ポリシー設定] ページが表示され、カスタマイズ オプションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ece38-157">After clicking Next,\*\* you'll be presented with an additional **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="ece38-158">テストしているポリシーの場合、ここから調整を開始できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-158">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="ece38-159">現時点ではポリシー ヒントをオフにしています。これは、テストを行っているだけであってまだユーザーに何も表示したくない場合に行う合理的な手順です。</span><span class="sxs-lookup"><span data-stu-id="ece38-159">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="ece38-160">ポリシー ヒントは、ユーザーに対して DLP ポリシーに違反しようとしているという警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="ece38-160">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="ece38-161">たとえば Outlook ユーザーには添付したファイルにクレジット カード番号が含まれているという警告が表示され、メールが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="ece38-161">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="ece38-162">ポリシー ヒントの目標は、非準拠の動作を発生前に停止することです。</span><span class="sxs-lookup"><span data-stu-id="ece38-162">The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="ece38-163">また、インスタンスの数を 10 から 1 に減らすことで、このポリシーがデータの一括共有だけでなくオーストラリアの PII データの共有を検出できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="ece38-163">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="ece38-164">また、インシデント レポートのメールに別の受信者を追加しました。</span><span class="sxs-lookup"><span data-stu-id="ece38-164">I've also added another recipient to the incident report email.</span></span>

![追加のポリシー設定](../media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="ece38-166">最後に、最初はテスト モードで実行するようにこのポリシーを構成しました。</span><span class="sxs-lookup"><span data-stu-id="ece38-166">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="ece38-167">ここには、テスト モード中にポリシー ヒントを無効にするオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="ece38-167">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="ece38-168">これにより、ポリシー内でポリシー ヒントを有効にする柔軟性が得られますが、それらを表示するか非表示にするかをテスト中に決定します。</span><span class="sxs-lookup"><span data-stu-id="ece38-168">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![最初にポリシーをテストするオプション](../media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="ece38-170">最終確認画面で [**作成**] をクリックして、ポリシーの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="ece38-170">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="ece38-171">DLP ポリシーをテストする</span><span class="sxs-lookup"><span data-stu-id="ece38-171">Test a DLP policy</span></span>

<span data-ttu-id="ece38-172">新しい DLP ポリシーは、約 1 時間以内に有効になります。</span><span class="sxs-lookup"><span data-stu-id="ece38-172">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="ece38-173">通常のユーザー アクティビティによってトリガーされるのを待つことも、試しに自分でトリガーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ece38-173">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="ece38-174">以前は、DLP 一致 [をトリガーする](sensitive-information-type-entity-definitions.md)方法に関する情報を提供する機密情報の種類エンティティ定義にリンクしました。</span><span class="sxs-lookup"><span data-stu-id="ece38-174">Earlier I linked to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="ece38-175">例として、この記事のために作成した DLP ポリシーはオーストラリアのタックス ファイル ナンバー (TFN) を検出します。</span><span class="sxs-lookup"><span data-stu-id="ece38-175">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="ece38-176">ドキュメントによると、一致は以下の基準に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ece38-176">According to the documentation, the match is based on the following criteria.</span></span>

![オーストラリアのタックス ファイル ナンバーに関するドキュメント](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="ece38-178">TFN 検出をかなり鈍い方法で示す場合、"Tax file number" という単語と近接する 9 桁の文字列を含む電子メールは問題なく送信されます。</span><span class="sxs-lookup"><span data-stu-id="ece38-178">To demonstrate TFN detection in a rather blunt manner, an email with the words "Tax file number" and a 9 digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="ece38-179">DLP ポリシーがトリガーされない理由は、9 桁の数字列が無害な数字の文字列ではなく有効な TFN であることを示すチェックサムに合格する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="ece38-179">The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![チェックサムに合格しないオーストラリアのタックス ファイル ナンバー](../media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="ece38-181">一方、"Tax file number" という単語と、チェックサムを渡す有効な TFN を含むメールがポリシーをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ece38-181">In comparison, an email with the words "Tax file number" and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="ece38-182">実際には、私が使用している TFN は有効ではあるものの本物ではない TFN を生成する Web サイトから取得したものです。</span><span class="sxs-lookup"><span data-stu-id="ece38-182">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="ece38-183">DLP ポリシーをテストする際の最も一般的な間違いの 1 つは、有効ではなくチェックサムを渡さない (したがってポリシーをトリガーしない) 偽の番号を使用することです。したがって、そういったサイトはとても便利です。</span><span class="sxs-lookup"><span data-stu-id="ece38-183">Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![チェックサムに合格したオーストラリアのタックス ファイル ナンバー](../media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="ece38-185">インシデント レポートのメールには、検出された機密情報の種類、検出されたインスタンスの数、および検出の信頼レベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ece38-185">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![検出されたタックス ファイル ナンバーを示すインシデント レポート](../media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="ece38-187">DLP ポリシーをテスト モードのままにしてインシデント レポートのメールを分析すると、DLP ポリシーの正確性およびそれが適用されたときの効果について感触をつかむことができます。</span><span class="sxs-lookup"><span data-stu-id="ece38-187">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="ece38-188">インシデント レポートに加えて、[DLP レポートを使用](view-the-dlp-reports.md)してテナント全体でのポリシーの一致の集計ビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-188">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="ece38-189">DLP ポリシーを調整する</span><span class="sxs-lookup"><span data-stu-id="ece38-189">Tune a DLP policy</span></span>

<span data-ttu-id="ece38-190">ポリシーのヒットを分析する際に、ポリシーの動作を調整する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="ece38-190">As you analyze your policy hits you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="ece38-191">簡単な例として、メール内に 1 つ TFN がある場合には問題がないと判断するとします (もちろん問題があるとは思いますが、デモのためにこの方法を使います)。しかし、問題は 2 つ以上のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="ece38-191">As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem.</span></span> <span data-ttu-id="ece38-192">複数のインスタンスは、従業員が HR データベースから外部パーティ (外部会計サービスなど) に CSV エクスポートをメールで送信するなどの危険性を持ったシナリオである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-192">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="ece38-193">間違いなく、検出してブロックしたいはずです。</span><span class="sxs-lookup"><span data-stu-id="ece38-193">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="ece38-194">セキュリティ/コンプライアンス センターでは、既存のポリシーを編集して動作を調整できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-194">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![ポリシーを編集するオプション](../media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="ece38-196">ポリシーが特定のワークロードまたは特定のサイトおよびアカウントにのみ適用されるように、場所の設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-196">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![特定の場所を選択するオプション](../media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="ece38-198">また、ポリシー設定を調整し、ニーズに合わせてルールを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="ece38-198">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![ルールを編集するオプション](../media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="ece38-200">DLP ポリシー内のルールを編集する際、以下を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-200">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="ece38-201">ルールをトリガーする機密データのインスタンスの種類および数を含む条件。</span><span class="sxs-lookup"><span data-stu-id="ece38-201">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="ece38-202">コンテンツへのアクセス制限などの、実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="ece38-202">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="ece38-203">ユーザー通知。メール クライアントまたは Web ブラウザーでユーザーに表示されるポリシー ヒントです。</span><span class="sxs-lookup"><span data-stu-id="ece38-203">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="ece38-204">ユーザーによる上書き。ユーザーがメールまたはファイル共有を続行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ece38-204">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="ece38-205">管理者に通知するためのインシデント レポート。</span><span class="sxs-lookup"><span data-stu-id="ece38-205">Incident reports, to notify administrators.</span></span>

![ルールの一部を編集するオプション](../media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="ece38-207">このデモンストレーションでは、ポリシーにユーザー通知を追加し (適切なユーザー認識トレーニングなしで行う場合には注意してください)、ユーザーがビジネス上の理由または誤検知としてフラグを立てることでポリシーを上書きすることを許可しました。</span><span class="sxs-lookup"><span data-stu-id="ece38-207">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="ece38-208">組織のポリシーに関する追加情報を含める場合にはメールおよびポリシー ヒントのテキストをカスタマイズしたり、質問がある場合にはサポートに連絡するようユーザーに促したりすることもできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ece38-208">Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![ユーザー通知および上書きのオプション](../media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="ece38-210">このポリシーには高ボリュームおよび低ボリュームの処理に関する 2 つのルールが含まれているため、必要なアクションでは必ず両方を編集してください。</span><span class="sxs-lookup"><span data-stu-id="ece38-210">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="ece38-211">これは、その特性に応じてケースを異なる方法で処理する機会となっています。</span><span class="sxs-lookup"><span data-stu-id="ece38-211">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="ece38-212">たとえば、低ボリューム違反への上書きは許可しても、高ボリューム違反への上書きは許可しない場合などです。</span><span class="sxs-lookup"><span data-stu-id="ece38-212">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![高ボリューム用の 1 つのルールおよび低ボリューム用の 1 つのルール](../media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="ece38-214">また、ポリシーに違反しているコンテンツへのアクセスを実際にブロックまたは制限したい場合には、そうするようにルールでアクションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-214">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![コンテンツへのアクセスを制限するオプション](../media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="ece38-216">ポリシー設定へのこれらの変更を保存した後、ポリシーのメイン設定ページに戻り、ポリシーがテスト モードのときにユーザーにポリシー ヒントを表示するオプションを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ece38-216">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="ece38-217">これは、エンド ユーザーに DLP ポリシーを紹介し、生産性に影響を与える多数の誤検知のリスクを負うことなくユーザーの意識向上トレーニングを行う効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="ece38-217">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![テスト モードでポリシー ヒントを表示するオプション](../media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="ece38-219">サーバー側 (または必要に応じてクラウド側) では、さまざまな処理間隔により、変更がすぐに有効にならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-219">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="ece38-220">ユーザーに新しいポリシー ヒントを表示する DLP ポリシーの変更を行っている場合、Outlook クライアントは 24 時間ごとにポリシーの変更をチェックするのでユーザーには変更がすぐに反映されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-220">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="ece38-221">テストのためにスピードを上げたい場合には、このレジストリ修正を使用して [PolicyNudges キーから最終ダウンロードのタイムスタンプをクリア](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-221">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="ece38-222">Outlook は次回再起動してメール メッセージの作成を開始する際に、最新のポリシー情報をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ece38-222">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="ece38-223">ポリシー ヒントを有効にしている場合、ユーザーは Outlook でヒントの表示を開始し、誤検知が発生した場合に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="ece38-223">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![誤検知を報告するオプションを備えたポリシー ヒント](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="ece38-225">誤検知を調査する</span><span class="sxs-lookup"><span data-stu-id="ece38-225">Investigate false positives</span></span>

<span data-ttu-id="ece38-226">DLP ポリシー テンプレートは、そのままでは完璧ではありません。</span><span class="sxs-lookup"><span data-stu-id="ece38-226">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="ece38-227">自身の環境で誤検出が発生する可能性は高いため、DLP 展開への道を容易にし、適切なポリシーのテストおよび調整に時間をかけることが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="ece38-227">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="ece38-228">これが誤検知の例です。</span><span class="sxs-lookup"><span data-stu-id="ece38-228">Here's an example of a false positive.</span></span> <span data-ttu-id="ece38-229">このメールは、まったくの無害です。</span><span class="sxs-lookup"><span data-stu-id="ece38-229">This email is quite harmless.</span></span> <span data-ttu-id="ece38-230">ユーザーは自分の携帯電話番号を誰かに提供し、メールに署名を含めています。</span><span class="sxs-lookup"><span data-stu-id="ece38-230">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![誤検知情報を示すメール](../media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="ece38-232">しかしユーザーには、メールに機密情報、具体的にはオーストラリアの運転免許証番号が含まれていることを警告するポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ece38-232">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![ポリシー ヒントで誤検知を報告するオプション](../media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="ece38-234">ユーザーは誤検知を報告でき、管理者はそれが発生した理由を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="ece38-234">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="ece38-235">インシデント レポートのメールには、誤検知のフラグが設定されています。</span><span class="sxs-lookup"><span data-stu-id="ece38-235">In the incident report email, the email is flagged as a false positive.</span></span>

![誤検知を示すインシデント レポート](../media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="ece38-237">この運転免許証のケースは、掘り下げるにはちょうど良い例です。</span><span class="sxs-lookup"><span data-stu-id="ece38-237">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="ece38-238">この誤検知が発生した理由は、"sydney nsw" というキーワードに 300 文字近い任意の 9 桁の文字列 (10 桁の文字列に含まれる文字列でも) によって "オーストラリアの運転免許証" タイプがトリガーされる(大文字と小文字は区別されません)。</span><span class="sxs-lookup"><span data-stu-id="ece38-238">The reason this false positive has occurred is that the "Australian Driver's License" type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords "sydney nsw" (not case sensitive).</span></span> <span data-ttu-id="ece38-239">そのため、ユーザーがたまたまシドニーにいるという理由だけで、電話番号とメール署名によってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="ece38-239">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>


<span data-ttu-id="ece38-240">1 つのオプションは、オーストラリアの運転免許証の情報の種類をポリシーから削除することです。</span><span class="sxs-lookup"><span data-stu-id="ece38-240">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="ece38-241">DLP ポリシー テンプレートの一部なのでそこに含まれていますが、強制的に使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ece38-241">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="ece38-242">運転免許証ではなくタックス ファイル ナンバーのみに関心がある場合には、削除して構いません。</span><span class="sxs-lookup"><span data-stu-id="ece38-242">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="ece38-243">たとえば、ポリシーの低ボリューム ルールからそれを削除しながらも、複数の運転免許証のリストがまだ検出されるように高ボリューム ルールにはそのままそれを残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="ece38-243">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![機密情報の種類をルールから削除するオプション](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="ece38-245">別のオプションとしては、単純にインスタンス数を増やすことが挙げられます。これにより、複数のインスタンスがある場合にのみ少量の運転免許証が検出されます。</span><span class="sxs-lookup"><span data-stu-id="ece38-245">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![インスタンス数を編集するオプション](../media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="ece38-247">インスタンス数の変更に加えて、一致の精度 (または信頼レベル) を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="ece38-247">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="ece38-248">機密情報の種類に複数のパターンがある場合、ルールが特定のパターンのみに一致するように、ルールの一致の精度を調整できます。</span><span class="sxs-lookup"><span data-stu-id="ece38-248">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="ece38-249">たとえば、誤検出を減らすためにルールの一致の精度を設定して、最も高い信頼レベルを持つパターンのみと一致するようにできます。</span><span class="sxs-lookup"><span data-stu-id="ece38-249">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="ece38-250">信頼レベルの計算方法を理解することは少し難しい (そしてこの投稿の範囲を超えている) のですが、ここに[信頼レベルを使用してルールを調整する方法](data-loss-prevention-policies.md#match-accuracy)の良い説明があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-250">Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](data-loss-prevention-policies.md#match-accuracy).</span></span>

<span data-ttu-id="ece38-251">最後に、もう少し高度な情報を取得する場合は、機密情報の種類をカスタマイズできます 。たとえば、オーストラリアの運転免許証番号のキーワードのリストから "Sydney NSW" を削除して、上記でトリガーされた誤検知を排除できます。 [](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)</span><span class="sxs-lookup"><span data-stu-id="ece38-251">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australia driver's license number](sensitive-information-type-entity-definitions.md#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="ece38-252">XML と PowerShell を使用してこれを行う方法については、「組み込みの機密情報の種類をカスタマイズする [」を参照してください](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="ece38-252">To learn how to do this by using XML and PowerShell, see [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-on-a-dlp-policy"></a><span data-ttu-id="ece38-253">DLP ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="ece38-253">Turn on a DLP policy</span></span>

<span data-ttu-id="ece38-254">DLP ポリシーが機密情報の種類を正確かつ効果的に検出し、エンド ユーザーが設定されたポリシーに対処する準備ができていることに満足したら、ポリシーを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ece38-254">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![ポリシーをオンにするオプション](../media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="ece38-256">ポリシーを有効にする時期を待っている場合には、[セキュリティ/コンプライアンス センターの PowerShell に接続し](/powershell/exchange/connect-to-scc-powershell)、[Get-DlpCompliancePolicy コマンドレット](/powershell/module/exchange/get-dlpcompliancepolicy)を実行して DistributionStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="ece38-256">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the [Get-DlpCompliancePolicy cmdlet](/powershell/module/exchange/get-dlpcompliancepolicy) to see the DistributionStatus.</span></span>

![PowerShell でコマンドレットを実行する](../media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="ece38-258">DLP ポリシーをオンにした後、独自の最終テストをいくつか実行し、予想されるポリシー アクションが発生していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ece38-258">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="ece38-259">クレジット カード データなどをテストしようとしている場合、チェックサムを通過しポリシーをトリガーするサンプルのクレジット カードやその他の個人情報を生成する方法についての情報を掲載した Web サイトがオンラインにあります。</span><span class="sxs-lookup"><span data-stu-id="ece38-259">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="ece38-260">ユーザーによる上書きを許可するポリシーは、ポリシー ヒントの一部としてユーザーにそのオプションを提示します。</span><span class="sxs-lookup"><span data-stu-id="ece38-260">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![ユーザーによる上書きを許可するポリシー ヒント](../media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="ece38-262">コンテンツを制限するポリシーは、ポリシー ヒントの一部としてユーザーに警告を表示しユーザーがメールを送信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="ece38-262">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![コンテンツが制限されているポリシー ヒント](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="ece38-264">概要</span><span class="sxs-lookup"><span data-stu-id="ece38-264">Summary</span></span>

<span data-ttu-id="ece38-265">データ損失防止ポリシーは、あらゆるタイプの組織に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ece38-265">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="ece38-266">一部の DLP ポリシーのテストは、ポリシー ヒント、エンド ユーザーによる上書き、インシデント レポートなどを制御できるため、リスクの低い演習です。</span><span class="sxs-lookup"><span data-stu-id="ece38-266">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports.</span></span> <span data-ttu-id="ece38-267">一部の DLP ポリシーを静かにテストし、組織で既に発生している違反の種類を確認し、誤検知率の低いポリシーを作成し、許可されているものと許可されていないものについてユーザーを教育し、DLP ポリシーを組織へとロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="ece38-267">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>