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
description: この記事では、組織のニーズに応じて DLP ポリシーを作成、テスト、および調整する方法について説明します。
ms.openlocfilehash: ef88da90d8e009d3ea634c9142d7d917fbfd288a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546937"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="5664f-103">DLP ポリシーを作成、テスト、調整する</span><span class="sxs-lookup"><span data-stu-id="5664f-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="5664f-104">データ損失防止 (DLP) は、組織が偶発的または偶発的で不要な機密情報を他者に公開しないようにするために設計されたコンプライアンス機能です。</span><span class="sxs-lookup"><span data-stu-id="5664f-104">Data loss prevention (DLP) is a compliance feature designed to help your organization prevent the unintentional or accidental exposure of sensitive information to unwanted parties.</span></span> <span data-ttu-id="5664f-105">DLP のルーツは Exchange Server および Exchange Online にあり、SharePoint Online および OneDrive for Business にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-105">DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="5664f-106">DLP は、コンテンツ分析エンジンを使用してメール メッセージおよびファイルのコンテンツを調べ、クレジット カード番号や個人を特定できる情報 (PII) などの機密情報を探します。</span><span class="sxs-lookup"><span data-stu-id="5664f-106">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII).</span></span> <span data-ttu-id="5664f-107">通常、機密情報はメール メッセージやファイルの暗号化などの追加の手順を実行せずにメールで送信したり、ドキュメントに含めたりするべきではありません。</span><span class="sxs-lookup"><span data-stu-id="5664f-107">Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files.</span></span> <span data-ttu-id="5664f-108">DLP を使用することで機密情報を検出し、次のようなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-108">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="5664f-109">監査目的でイベントを記録する</span><span class="sxs-lookup"><span data-stu-id="5664f-109">Log the event for auditing purposes</span></span>
- <span data-ttu-id="5664f-110">電子メールを送信またはファイルを共有しているエンド ユーザーに警告を表示する</span><span class="sxs-lookup"><span data-stu-id="5664f-110">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="5664f-111">メールまたはファイルの共有の実行を積極的にブロックする</span><span class="sxs-lookup"><span data-stu-id="5664f-111">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="5664f-112">保護が必要な種類のデータを持っていると自分が考えていないために、顧客が DLP を却下する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-112">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting.</span></span> <span data-ttu-id="5664f-113">医療記録や財務情報などの機密データは、ヘルスケアなどの業界またはオンライン ストアを運営する企業にのみ存在するという前提があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-113">The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores.</span></span> <span data-ttu-id="5664f-114">しかし、どんなビジネスでも、たとえ気付いていなくても定期的に機密情報を扱う場合があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-114">But any business can handle sensitive information on a regular basis, even if they don't realize it.</span></span> <span data-ttu-id="5664f-115">従業員の名前および生年月日のスプレッドシートは、顧客名およびクレジット カードの詳細情報のスプレッドシートと同じくらい重要です。</span><span class="sxs-lookup"><span data-stu-id="5664f-115">A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details.</span></span> <span data-ttu-id="5664f-116">そして、従業員は日々のタスクを静かに行っており、システムから CSV ファイルをエクスポートして誰かにメールで送信することに関して何も考えていないため、このタイプの情報は予想以上に多く出回っています。</span><span class="sxs-lookup"><span data-stu-id="5664f-116">And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone.</span></span> <span data-ttu-id="5664f-117">また、従業員がクレジット カードまたは銀行の詳細情報を含むメールを結果を考慮せずに送信する頻度にも驚かれるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="5664f-117">You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="permissions"></a><span data-ttu-id="5664f-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5664f-118">Permissions</span></span>

<span data-ttu-id="5664f-119">DLP ポリシーを作成するコンプライアンス チームのメンバーは、セキュリティ &amp; コンプライアンス センターへのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-119">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="5664f-120">既定では、テナント管理者はこの場所へのアクセス許可を持ち、コンプライアンス責任者や他のユーザーに対し、テナント管理者のすべてのアクセス許可を付与せずに、セキュリティ &amp; コンプライアンス センターへのアクセスを許可できます。これを行うには、次の操作を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5664f-120">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="5664f-121">Microsoft 365 でグループを作成して、コンプライアンス責任者をグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="5664f-121">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="5664f-122">セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページで役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="5664f-122">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="5664f-123">役割グループの作成時に、 **[役割の選択** ] セクションを使用して、次の役割を役割グループに追加します。 **DLP コンプライアンス管理**。</span><span class="sxs-lookup"><span data-stu-id="5664f-123">While creating the role group, use the **Choose Roles** section to add the following role to the role group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="5664f-124">**メンバーの選択**セクションを使用して、以前に作成した Microsoft 365 グループを役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="5664f-124">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="5664f-125">また、**表示のみ DLP コンプライアンス管理** の役割を付与することで、DLP ポリシーと DLP レポートに表示のみの権限を持った役割グループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5664f-125">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="5664f-126">詳細については、「[Give users access to the Office 365 Security & Compliance Center (Office 365 セキュリティ/コンプライアンス センターへのアクセス権をユーザーに付与する)](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5664f-126">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="5664f-127">これらのアクセス許可は、DLP ポリシーを作成して適用するためにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="5664f-127">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="5664f-128">ポリシーの適用には、コンテンツへのアクセスは不要です。</span><span class="sxs-lookup"><span data-stu-id="5664f-128">Policy enforcement does not require access to the content.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="5664f-129">DLP による機密情報の検出方法</span><span class="sxs-lookup"><span data-stu-id="5664f-129">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="5664f-130">機密情報は、一致パターンに対する特定のキーワードの近接度など、他のインジケーターと組み合わせて、正規表現 (RegEx) パターンマッチングで識別されます。</span><span class="sxs-lookup"><span data-stu-id="5664f-130">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="5664f-131">この例として、クレジット カード番号が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="5664f-131">An example of this is credit card numbers.</span></span> <span data-ttu-id="5664f-132">VISA のクレジット カード番号は 16 桁です。</span><span class="sxs-lookup"><span data-stu-id="5664f-132">A VISA credit card number has 16 digits.</span></span> <span data-ttu-id="5664f-133">しかしながら、これらの数字は 1111-1111-1111-1111、1111 1111 1111 1111、または 1111111111111111 など、さまざまな方法で記述することができます。</span><span class="sxs-lookup"><span data-stu-id="5664f-133">However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="5664f-134">16 桁の数字列は必ずしもクレジット カード番号とは限らず、ヘルプ デスク システムのチケット番号、またはハードウェアのシリアル番号である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-134">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="5664f-135">クレジット カード番号と無害な 16 桁の数字列の違いを判断するために計算が実行され (チェックサム)、番号がさまざまなクレジット カード ブランドの既知のパターンに一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5664f-135">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="5664f-136">さらに、"VISA" や "AMEX" などのキーワードと、クレジットカードの有効期限が切れる日付の間の類似性は、データがクレジットカード番号であるかどうかを決定することも検討しています。</span><span class="sxs-lookup"><span data-stu-id="5664f-136">Furthermore, the proximity of keywords such as "VISA" or "AMEX", along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="5664f-137">言い換えれば、DLP は通常メール内のこれら 2 つのテキストの違いを認識するのに十分なほどスマートです。</span><span class="sxs-lookup"><span data-stu-id="5664f-137">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="5664f-138">"新しいラップトップをご注文いただくことができます。</span><span class="sxs-lookup"><span data-stu-id="5664f-138">"Can you order me a new laptop.</span></span> <span data-ttu-id="5664f-139">VISA カード1111-1111-1111-1111、有効期限11/22、および自分が所有しているときに送信する予定の日付を送信する</span><span class="sxs-lookup"><span data-stu-id="5664f-139">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it."</span></span>
- <span data-ttu-id="5664f-140">"My ラップトップのシリアル番号は2222-2222-2222-2222 で、11/2010 で購入されました。</span><span class="sxs-lookup"><span data-stu-id="5664f-140">"My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="5664f-141">ところで、旅行 visa は承認されていますか?</span><span class="sxs-lookup"><span data-stu-id="5664f-141">By the way, is my travel visa approved yet?"</span></span>

<span data-ttu-id="5664f-142">ブックマークを保持するための適切な参照は、 [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md) で、各情報の種類が検出される方法を説明しています。</span><span class="sxs-lookup"><span data-stu-id="5664f-142">A good reference to keep bookmarked is [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="5664f-143">データ損失防止を開始する場所</span><span class="sxs-lookup"><span data-stu-id="5664f-143">Where to start with data loss prevention</span></span>

<span data-ttu-id="5664f-144">データ漏洩のリスクが完全に明らかではない場合、DLP の実装をどこから始めるべきかを正確に判断することは困難です。</span><span class="sxs-lookup"><span data-stu-id="5664f-144">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="5664f-145">さいわい、DLP ポリシーを "テストモード" で実行して、有効にする前に、その実効性と正確性を測定できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-145">Fortunately, DLP policies can be run in "test mode", allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="5664f-146">Exchange Online の DLP ポリシーは、Exchange 管理センターを介して管理できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-146">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="5664f-147">ただし、セキュリティ/コンプライアンス センターを介してすべてのワークロードの DLP ポリシーを構成できるため、この記事のデモではこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="5664f-147">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="5664f-148">セキュリティ/コンプライアンス センターでは、[**データ損失防止**] >  [**ポリシー**] の下に DLP ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="5664f-148">In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="5664f-149">[**ポリシーの作成**] をクリックして開始します。</span><span class="sxs-lookup"><span data-stu-id="5664f-149">Click on **Create a policy** to start.</span></span>

<span data-ttu-id="5664f-150">Microsoft 365 には、DLP ポリシーの作成に使用できる一連の [dlp ポリシーテンプレート](what-the-dlp-policy-templates-include.md) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5664f-150">Microsoft 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies.</span></span> <span data-ttu-id="5664f-151">例えば、ここがオーストラリアの企業だとしましょう。</span><span class="sxs-lookup"><span data-stu-id="5664f-151">Let's say that you're an Australian business.</span></span> <span data-ttu-id="5664f-152">ポリシー テンプレートをフィルター処理し、オーストラリアに関連するもののみを表示できます。これらは金融、医療、健康、プライバシーの一般カテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="5664f-152">You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![国または地域を選択するオプション](../media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="5664f-154">このデモンストレーションでは、オーストラリアの個人を特定できる情報 (PII) データを選択します。これには、オーストラリアのタックス ファイル ナンバー (TFN) および運転免許証番号の情報の種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5664f-154">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![ポリシー テンプレートを選択するオプション](../media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="5664f-156">新しい DLP ポリシーに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="5664f-156">Give your new DLP policy a name.</span></span> <span data-ttu-id="5664f-157">規定の名前は DLP ポリシー テンプレートと一致しますが、同じテンプレートから複数のポリシーを作成できるため、よりわかりやすい独自の名前を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-157">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![ポリシーに名前を付けるオプション](../media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="5664f-159">ポリシーを適用する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="5664f-159">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="5664f-160">DLP ポリシーは Exchange Online、SharePoint Online、および OneDrive for Business に適用できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-160">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="5664f-161">このポリシーは、すべての場所に適用されるように構成したまま残します。</span><span class="sxs-lookup"><span data-stu-id="5664f-161">I am going to leave this policy configured to apply to all locations.</span></span>

![すべての場所を選択するオプション](../media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="5664f-163">最初の**ポリシー設定**手順では、今のところは規定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="5664f-163">At the first **Policy Settings** step just accept the defaults for now.</span></span> <span data-ttu-id="5664f-164">DLP ポリシーでは行うことができるカスタマイズが非常に多くありますが、規定値は開始するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="5664f-164">There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![保護するコンテンツの種類をカスタマイズするオプション](../media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="5664f-166">[**次へ**] をクリックすると、カスタマイズ オプションが増えた追加の [**ポリシー設定**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5664f-166">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="5664f-167">テストしているポリシーの場合、ここから調整を開始できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-167">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="5664f-168">現時点ではポリシー ヒントをオフにしています。これは、テストを行っているだけであってまだユーザーに何も表示したくない場合に行う合理的な手順です。</span><span class="sxs-lookup"><span data-stu-id="5664f-168">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="5664f-169">ポリシー ヒントは、ユーザーに対して DLP ポリシーに違反しようとしているという警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="5664f-169">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="5664f-170">たとえば Outlook ユーザーには添付したファイルにクレジット カード番号が含まれているという警告が表示され、メールが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="5664f-170">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="5664f-171">ポリシー ヒントの目標は、非準拠の動作を発生前に停止することです。</span><span class="sxs-lookup"><span data-stu-id="5664f-171">The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="5664f-172">また、インスタンスの数を 10 から 1 に減らすことで、このポリシーがデータの一括共有だけでなくオーストラリアの PII データの共有を検出できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="5664f-172">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="5664f-173">また、インシデント レポートのメールに別の受信者を追加しました。</span><span class="sxs-lookup"><span data-stu-id="5664f-173">I've also added another recipient to the incident report email.</span></span>

![追加のポリシー設定](../media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="5664f-175">最後に、最初はテスト モードで実行するようにこのポリシーを構成しました。</span><span class="sxs-lookup"><span data-stu-id="5664f-175">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="5664f-176">ここには、テスト モード中にポリシー ヒントを無効にするオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="5664f-176">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="5664f-177">これにより、ポリシー内でポリシー ヒントを有効にする柔軟性が得られますが、それらを表示するか非表示にするかをテスト中に決定します。</span><span class="sxs-lookup"><span data-stu-id="5664f-177">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![最初にポリシーをテストするオプション](../media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="5664f-179">最終確認画面で [**作成**] をクリックして、ポリシーの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="5664f-179">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="5664f-180">DLP ポリシーをテストする</span><span class="sxs-lookup"><span data-stu-id="5664f-180">Test a DLP policy</span></span>

<span data-ttu-id="5664f-181">新しい DLP ポリシーは、約 1 時間以内に有効になります。</span><span class="sxs-lookup"><span data-stu-id="5664f-181">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="5664f-182">通常のユーザー アクティビティによってトリガーされるのを待つことも、試しに自分でトリガーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5664f-182">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="5664f-183">前述の [「機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」にリンクされており、DLP 一致をトリガーする方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5664f-183">Earlier I linked to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="5664f-184">例として、この記事のために作成した DLP ポリシーはオーストラリアのタックス ファイル ナンバー (TFN) を検出します。</span><span class="sxs-lookup"><span data-stu-id="5664f-184">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="5664f-185">ドキュメントによると、一致は以下の基準に基づいています。</span><span class="sxs-lookup"><span data-stu-id="5664f-185">According to the documentation, the match is based on the following criteria.</span></span>

![オーストラリアのタックス ファイル ナンバーに関するドキュメント](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="5664f-187">Blunt のように、TFN の検出をデモンストレーションするために、"税ファイル番号" という単語を持つ電子メールと、近接している9桁の文字列は、問題を発生させることなく sail ます。</span><span class="sxs-lookup"><span data-stu-id="5664f-187">To demonstrate TFN detection in a rather blunt manner, an email with the words "Tax file number" and a 9 digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="5664f-188">DLP ポリシーがトリガーされない理由は、9 桁の数字列が無害な数字の文字列ではなく有効な TFN であることを示すチェックサムに合格する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="5664f-188">The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![チェックサムに合格しないオーストラリアのタックス ファイル ナンバー](../media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="5664f-190">これに対して、"税ファイル番号" という語句を持つ電子メールと、チェックサムを渡す有効な TFN がポリシーをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="5664f-190">In comparison, an email with the words "Tax file number" and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="5664f-191">実際には、私が使用している TFN は有効ではあるものの本物ではない TFN を生成する Web サイトから取得したものです。</span><span class="sxs-lookup"><span data-stu-id="5664f-191">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="5664f-192">DLP ポリシーをテストする際の最も一般的な間違いの 1 つは、有効ではなくチェックサムを渡さない (したがってポリシーをトリガーしない) 偽の番号を使用することです。したがって、そういったサイトはとても便利です。</span><span class="sxs-lookup"><span data-stu-id="5664f-192">Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![チェックサムに合格したオーストラリアのタックス ファイル ナンバー](../media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="5664f-194">インシデント レポートのメールには、検出された機密情報の種類、検出されたインスタンスの数、および検出の信頼レベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5664f-194">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![検出されたタックス ファイル ナンバーを示すインシデント レポート](../media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="5664f-196">DLP ポリシーをテスト モードのままにしてインシデント レポートのメールを分析すると、DLP ポリシーの正確性およびそれが適用されたときの効果について感触をつかむことができます。</span><span class="sxs-lookup"><span data-stu-id="5664f-196">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="5664f-197">インシデント レポートに加えて、[DLP レポートを使用](view-the-dlp-reports.md)してテナント全体でのポリシーの一致の集計ビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-197">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="5664f-198">DLP ポリシーを調整する</span><span class="sxs-lookup"><span data-stu-id="5664f-198">Tune a DLP policy</span></span>

<span data-ttu-id="5664f-199">ポリシーのヒットを分析する際に、ポリシーの動作を調整する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="5664f-199">As you analyze your policy hits you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="5664f-200">簡単な例として、メール内に 1 つ TFN がある場合には問題がないと判断するとします (もちろん問題があるとは思いますが、デモのためにこの方法を使います)。しかし、問題は 2 つ以上のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="5664f-200">As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem.</span></span> <span data-ttu-id="5664f-201">複数のインスタンスは、従業員が HR データベースから外部パーティ (外部会計サービスなど) に CSV エクスポートをメールで送信するなどの危険性を持ったシナリオである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-201">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="5664f-202">間違いなく、検出してブロックしたいはずです。</span><span class="sxs-lookup"><span data-stu-id="5664f-202">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="5664f-203">セキュリティ/コンプライアンス センターでは、既存のポリシーを編集して動作を調整できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-203">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![ポリシーを編集するオプション](../media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="5664f-205">ポリシーが特定のワークロードまたは特定のサイトおよびアカウントにのみ適用されるように、場所の設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-205">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![特定の場所を選択するオプション](../media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="5664f-207">また、ポリシー設定を調整し、ニーズに合わせてルールを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="5664f-207">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![ルールを編集するオプション](../media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="5664f-209">DLP ポリシー内のルールを編集する際、以下を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-209">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="5664f-210">ルールをトリガーする機密データのインスタンスの種類および数を含む条件。</span><span class="sxs-lookup"><span data-stu-id="5664f-210">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="5664f-211">コンテンツへのアクセス制限などの、実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="5664f-211">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="5664f-212">ユーザー通知。メール クライアントまたは Web ブラウザーでユーザーに表示されるポリシー ヒントです。</span><span class="sxs-lookup"><span data-stu-id="5664f-212">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="5664f-213">ユーザーによる上書き。ユーザーがメールまたはファイル共有を続行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5664f-213">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="5664f-214">管理者に通知するためのインシデント レポート。</span><span class="sxs-lookup"><span data-stu-id="5664f-214">Incident reports, to notify administrators.</span></span>

![ルールの一部を編集するオプション](../media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="5664f-216">このデモンストレーションでは、ポリシーにユーザー通知を追加し (適切なユーザー認識トレーニングなしで行う場合には注意してください)、ユーザーがビジネス上の理由または誤検知としてフラグを立てることでポリシーを上書きすることを許可しました。</span><span class="sxs-lookup"><span data-stu-id="5664f-216">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="5664f-217">組織のポリシーに関する追加情報を含める場合にはメールおよびポリシー ヒントのテキストをカスタマイズしたり、質問がある場合にはサポートに連絡するようユーザーに促したりすることもできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5664f-217">Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![ユーザー通知および上書きのオプション](../media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="5664f-219">このポリシーには高ボリュームおよび低ボリュームの処理に関する 2 つのルールが含まれているため、必要なアクションでは必ず両方を編集してください。</span><span class="sxs-lookup"><span data-stu-id="5664f-219">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="5664f-220">これは、その特性に応じてケースを異なる方法で処理する機会となっています。</span><span class="sxs-lookup"><span data-stu-id="5664f-220">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="5664f-221">たとえば、低ボリューム違反への上書きは許可しても、高ボリューム違反への上書きは許可しない場合などです。</span><span class="sxs-lookup"><span data-stu-id="5664f-221">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![高ボリューム用の 1 つのルールおよび低ボリューム用の 1 つのルール](../media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="5664f-223">また、ポリシーに違反しているコンテンツへのアクセスを実際にブロックまたは制限したい場合には、そうするようにルールでアクションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-223">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![コンテンツへのアクセスを制限するオプション](../media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="5664f-225">ポリシー設定へのこれらの変更を保存した後、ポリシーのメイン設定ページに戻り、ポリシーがテスト モードのときにユーザーにポリシー ヒントを表示するオプションを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5664f-225">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="5664f-226">これは、エンド ユーザーに DLP ポリシーを紹介し、生産性に影響を与える多数の誤検知のリスクを負うことなくユーザーの意識向上トレーニングを行う効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="5664f-226">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![テスト モードでポリシー ヒントを表示するオプション](../media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="5664f-228">サーバー側 (または必要に応じてクラウド側) では、さまざまな処理間隔により、変更がすぐに有効にならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-228">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="5664f-229">ユーザーに新しいポリシー ヒントを表示する DLP ポリシーの変更を行っている場合、Outlook クライアントは 24 時間ごとにポリシーの変更をチェックするのでユーザーには変更がすぐに反映されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-229">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="5664f-230">テストのためにスピードを上げたい場合には、このレジストリ修正を使用して [PolicyNudges キーから最終ダウンロードのタイムスタンプをクリア](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-230">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="5664f-231">Outlook は次回再起動してメール メッセージの作成を開始する際に、最新のポリシー情報をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5664f-231">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="5664f-232">ポリシー ヒントを有効にしている場合、ユーザーは Outlook でヒントの表示を開始し、誤検知が発生した場合に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="5664f-232">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![誤検知を報告するオプションを備えたポリシー ヒント](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="5664f-234">誤検知を調査する</span><span class="sxs-lookup"><span data-stu-id="5664f-234">Investigate false positives</span></span>

<span data-ttu-id="5664f-235">DLP ポリシー テンプレートは、そのままでは完璧ではありません。</span><span class="sxs-lookup"><span data-stu-id="5664f-235">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="5664f-236">自身の環境で誤検出が発生する可能性は高いため、DLP 展開への道を容易にし、適切なポリシーのテストおよび調整に時間をかけることが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="5664f-236">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="5664f-237">これが誤検知の例です。</span><span class="sxs-lookup"><span data-stu-id="5664f-237">Here's an example of a false positive.</span></span> <span data-ttu-id="5664f-238">このメールは、まったくの無害です。</span><span class="sxs-lookup"><span data-stu-id="5664f-238">This email is quite harmless.</span></span> <span data-ttu-id="5664f-239">ユーザーは自分の携帯電話番号を誰かに提供し、メールに署名を含めています。</span><span class="sxs-lookup"><span data-stu-id="5664f-239">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![誤検知情報を示すメール](../media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="5664f-241">しかしユーザーには、メールに機密情報、具体的にはオーストラリアの運転免許証番号が含まれていることを警告するポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5664f-241">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![ポリシー ヒントで誤検知を報告するオプション](../media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="5664f-243">ユーザーは誤検知を報告でき、管理者はそれが発生した理由を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="5664f-243">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="5664f-244">インシデント レポートのメールには、誤検知のフラグが設定されています。</span><span class="sxs-lookup"><span data-stu-id="5664f-244">In the incident report email, the email is flagged as a false positive.</span></span>

![誤検知を示すインシデント レポート](../media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="5664f-246">この運転免許証のケースは、掘り下げるにはちょうど良い例です。</span><span class="sxs-lookup"><span data-stu-id="5664f-246">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="5664f-247">この誤検知が発生した理由は、"オーストラリアのドライバーのライセンス" の種類が、キーワード "シドニー nsw" (大文字と小文字を区別しない) の300文字以内の9桁の文字列でトリガーされるためです。</span><span class="sxs-lookup"><span data-stu-id="5664f-247">The reason this false positive has occurred is that the "Australian Driver's License" type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords "sydney nsw" (not case sensitive).</span></span> <span data-ttu-id="5664f-248">そのため、ユーザーがたまたまシドニーにいるという理由だけで、電話番号とメール署名によってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="5664f-248">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>


<span data-ttu-id="5664f-249">1 つのオプションは、オーストラリアの運転免許証の情報の種類をポリシーから削除することです。</span><span class="sxs-lookup"><span data-stu-id="5664f-249">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="5664f-250">DLP ポリシー テンプレートの一部なのでそこに含まれていますが、強制的に使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5664f-250">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="5664f-251">運転免許証ではなくタックス ファイル ナンバーのみに関心がある場合には、削除して構いません。</span><span class="sxs-lookup"><span data-stu-id="5664f-251">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="5664f-252">たとえば、ポリシーの低ボリューム ルールからそれを削除しながらも、複数の運転免許証のリストがまだ検出されるように高ボリューム ルールにはそのままそれを残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="5664f-252">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![機密情報の種類をルールから削除するオプション](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="5664f-254">別のオプションとしては、単純にインスタンス数を増やすことが挙げられます。これにより、複数のインスタンスがある場合にのみ少量の運転免許証が検出されます。</span><span class="sxs-lookup"><span data-stu-id="5664f-254">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![インスタンス数を編集するオプション](../media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="5664f-256">インスタンス数の変更に加えて、一致の精度 (または信頼レベル) を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="5664f-256">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="5664f-257">機密情報の種類に複数のパターンがある場合、ルールが特定のパターンのみに一致するように、ルールの一致の精度を調整できます。</span><span class="sxs-lookup"><span data-stu-id="5664f-257">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="5664f-258">たとえば、誤検出を減らすためにルールの一致の精度を設定して、最も高い信頼レベルを持つパターンのみと一致するようにできます。</span><span class="sxs-lookup"><span data-stu-id="5664f-258">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="5664f-259">信頼レベルの計算方法を理解することは少し難しい (そしてこの投稿の範囲を超えている) のですが、ここに[信頼レベルを使用してルールを調整する方法](data-loss-prevention-policies.md#match-accuracy)の良い説明があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-259">Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](data-loss-prevention-policies.md#match-accuracy).</span></span>

<span data-ttu-id="5664f-260">さらに高度な機能を利用する場合は、機密情報の種類をカスタマイズすることができます。たとえば、 [オーストラリアドライバーのライセンス番号](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)のキーワードの一覧から "シドニー NSW" を削除して、上記の誤検知を排除することができます。</span><span class="sxs-lookup"><span data-stu-id="5664f-260">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australia driver's license number](sensitive-information-type-entity-definitions.md#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="5664f-261">XML および PowerShell を使用してこれを行う方法については、[組み込みの機密情報の種類のカスタマイズ](customize-a-built-in-sensitive-information-type.md)に関するこのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5664f-261">To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-on-a-dlp-policy"></a><span data-ttu-id="5664f-262">DLP ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="5664f-262">Turn on a DLP policy</span></span>

<span data-ttu-id="5664f-263">DLP ポリシーが機密情報の種類を正確かつ効果的に検出し、エンド ユーザーが設定されたポリシーに対処する準備ができていることに満足したら、ポリシーを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5664f-263">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![ポリシーをオンにするオプション](../media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="5664f-265">ポリシーを有効にする時期を待っている場合には、[セキュリティ/コンプライアンス センターの PowerShell に接続し](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)、[Get-DlpCompliancePolicy コマンドレット](https://docs.microsoft.com/powershell/module/exchange/get-dlpcompliancepolicy)を実行して DistributionStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="5664f-265">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/powershell/module/exchange/get-dlpcompliancepolicy) to see the DistributionStatus.</span></span>

![PowerShell でコマンドレットを実行する](../media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="5664f-267">DLP ポリシーをオンにした後、独自の最終テストをいくつか実行し、予想されるポリシー アクションが発生していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5664f-267">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="5664f-268">クレジット カード データなどをテストしようとしている場合、チェックサムを通過しポリシーをトリガーするサンプルのクレジット カードやその他の個人情報を生成する方法についての情報を掲載した Web サイトがオンラインにあります。</span><span class="sxs-lookup"><span data-stu-id="5664f-268">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="5664f-269">ユーザーによる上書きを許可するポリシーは、ポリシー ヒントの一部としてユーザーにそのオプションを提示します。</span><span class="sxs-lookup"><span data-stu-id="5664f-269">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![ユーザーによる上書きを許可するポリシー ヒント](../media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="5664f-271">コンテンツを制限するポリシーは、ポリシー ヒントの一部としてユーザーに警告を表示しユーザーがメールを送信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="5664f-271">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![コンテンツが制限されているポリシー ヒント](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="5664f-273">概要</span><span class="sxs-lookup"><span data-stu-id="5664f-273">Summary</span></span>

<span data-ttu-id="5664f-274">データ損失防止ポリシーは、あらゆるタイプの組織に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5664f-274">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="5664f-275">一部の DLP ポリシーのテストは、ポリシー ヒント、エンド ユーザーによる上書き、インシデント レポートなどを制御できるため、リスクの低い演習です。</span><span class="sxs-lookup"><span data-stu-id="5664f-275">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports.</span></span> <span data-ttu-id="5664f-276">一部の DLP ポリシーを静かにテストし、組織で既に発生している違反の種類を確認し、誤検知率の低いポリシーを作成し、許可されているものと許可されていないものについてユーザーを教育し、DLP ポリシーを組織へとロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="5664f-276">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
