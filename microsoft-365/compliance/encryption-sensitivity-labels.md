---
title: 機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密ラベルを作成するときに、そのラベルが適用されるコンテンツへのアクセスを制限できます。機密ラベルでは、コンテンツの保護のために暗号化を使用できます。
ms.openlocfilehash: 55a4096fb802608ac8c0e9777dc20b1026ba6b60
ms.sourcegitcommit: 8ac1b6586678035050fc422e6fb503fa478be397
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962316"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a><span data-ttu-id="2e610-104">機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="2e610-104">Restrict access to content by using encryption in sensitivity labels</span></span>

<span data-ttu-id="2e610-p102">機密ラベルを作成するときに、そのラベルが適用されるコンテンツへのアクセスを制限できます。たとえば、機密ラベルに対応する暗号化の設定によって、次のようにコンテンツを保護できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="2e610-107">組織内のユーザーのみが機密ドキュメントや電子メールを開けるようにする。</span><span class="sxs-lookup"><span data-stu-id="2e610-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="2e610-108">宣伝広告用のドキュメントや電子メールは、マーケティング部門のユーザーのみが編集および印刷できるようにして、その他の組織内のユーザーは閲覧のみできるようにする。</span><span class="sxs-lookup"><span data-stu-id="2e610-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="2e610-109">内部の再編成に関するニュースが含まれている電子メールは、ユーザーが転送や情報のコピーをできないようにする。</span><span class="sxs-lookup"><span data-stu-id="2e610-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="2e610-110">ビジネス パートナーに送信する現行の価格リストは、指定した日付以降は開けないようにする。</span><span class="sxs-lookup"><span data-stu-id="2e610-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="2e610-111">ドキュメントや電子メールを暗号化するときには、次のようにしてコンテンツへのアクセスが制限されます。</span><span class="sxs-lookup"><span data-stu-id="2e610-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="2e610-112">暗号化の解除は、ラベルの暗号化設定で許可されているユーザーのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="2e610-112">Can be decrypted only by users authorized by the label’s encryption settings.</span></span>
- <span data-ttu-id="2e610-113">暗号化は、ファイルの場所 (組織内外) を問わず、ファイル名が変更されていても維持されます。</span><span class="sxs-lookup"><span data-stu-id="2e610-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file’s renamed.</span></span>
- <span data-ttu-id="2e610-114">保存中 (OneDrive アカウントなど) と転送中 (送信中の電子メールなど) の両方で暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="2e610-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="2e610-115">最後に、管理者として、秘密度ラベルを作成するときに、次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-115">Finally, as an admin, when you create a sensitivity label, you can choose either to:</span></span>

- <span data-ttu-id="2e610-116">**アクセス許可を割り当てます**。これにより、どのユーザーがそのラベルのコンテンツにどのアクセス許可を取得するかを正確に決定します。</span><span class="sxs-lookup"><span data-stu-id="2e610-116">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="2e610-117">ラベルをコンテンツに適用するときに、**ユーザーがアクセス許可を割り当てる**ことができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-117">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="2e610-118">このようにして、組織内のユーザーに、共同作業を行って作業を完了するために必要な柔軟性を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-118">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="2e610-119">暗号化の設定は、Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターで機密ラベルを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-119">The encryption settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="2e610-120">左側のナビゲーションで、[**分類**]  >  [**秘密度ラベル**]  >  [**ラベルの作成**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2e610-120">In the left nav, choose **Classification** > **Sensitivity label** > **Create a label**.</span></span>

## <a name="how-encryption-works"></a><span data-ttu-id="2e610-121">暗号化のしくみ</span><span class="sxs-lookup"><span data-stu-id="2e610-121">How encryption works</span></span>

<span data-ttu-id="2e610-p105">暗号化には、Azure Rights Management (Azure RMS) を使用します。Azure RMS は、暗号化ポリシー、ID ポリシー、および認証ポリシーを使用します。詳細については、「[Azure Rights Management とは](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-p105">Encryption uses Azure Rights Management (Azure RMS). Azure RMS uses encryption, identity, and authorization policies. To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)</span></span>

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a><span data-ttu-id="2e610-125">機密ラベルに対する暗号化を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2e610-125">How to turn on encryption for a sensitivity label</span></span>

<span data-ttu-id="2e610-126">開始するには、[**暗号化**] を [**オン**] に切り替えてから、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e610-126">To begin, simply toggle **Encryption** to **On**, and then choose whether to:</span></span>

- <span data-ttu-id="2e610-127">**アクセス許可を割り当てます**。これにより、どのユーザーがそのラベルのコンテンツにどのアクセス許可を取得するかを正確に決定することができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-127">**Assign permissions now**, so that you can determine exactly which users get which permissions to content with that label.</span></span> <span data-ttu-id="2e610-128">詳細については、次のセクション「[アクセス許可を割り当てる](#assign-permissions-now)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-128">For more information, see the next section [Assign permissions now](#assign-permissions-now).</span></span>
- <span data-ttu-id="2e610-129">ラベルをコンテンツに適用するときに、**ユーザーがアクセス許可を割り当てる**ことができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-129">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="2e610-130">このようにして、組織内のユーザーに、共同作業を行って作業を完了するために必要な柔軟性を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-130">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="2e610-131">詳細については、このページのセクション「[ユーザーがアクセス許可を割り当てる](#let-users-assign-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-131">For more information, see the below section [Let users assign permissions](#let-users-assign-permissions).</span></span>

<span data-ttu-id="2e610-132">たとえば、最も機密性の高いコンテンツに適用される「**極秘**」という名前の機密ラベルがある場合、そのコンテンツに対してどのタイプのアクセス許可を誰に付与するのかについて、この時点で決めることができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-132">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you may want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="2e610-133">一方、「**業務契約**」という名前の機密ラベルがあり、組織のワークフローの規定によりこのコンテンツに関して従業員と外部ユーザーの間でアドホック ベースで共同作業を行う必要がある場合は、従業員がラベルを割り当てる際に、アクセス許可を誰に付与するかを従業員が決定できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-133">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you may want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="2e610-134">この柔軟性により、ユーザーの生産性が向上し、特定のシナリオに対処するために管理者に新しい機密度ラベルを更新または作成を要求することを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-134">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

![ユーザーまたは管理者が定義したアクセス許可を追加するオプション](media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a><span data-ttu-id="2e610-136">アクセス許可を今すぐ割り当てる</span><span class="sxs-lookup"><span data-stu-id="2e610-136">Assign permissions now</span></span>

<span data-ttu-id="2e610-137">以下のオプションを使用して、このラベルが適用されるメールやドキュメントにアクセスできるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="2e610-137">Use the options below to control who can access email or documents to which this label is applied.</span></span> <span data-ttu-id="2e610-138">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-138">You can:</span></span>

1. <span data-ttu-id="2e610-p110">**ラベル付けされたコンテンツへのアクセスに有効期限を設定します。** 特定の日付または指定するラベル適用後の経過日数で有効期限が切れるようにします。期限が切れると、ユーザーはラベル付きのアイテムを開くことができなくなります。日付を指定した場合、現在のタイム ゾーンでその日付の午前 0 時に有効期限が切れます。(一部のメール クライアントでは、キャッシュの仕組みにより、有効期限が適用されず、有効期限を過ぎたメールが表示されることがある点に注意してください。)</span><span class="sxs-lookup"><span data-stu-id="2e610-p110">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won’t be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients may not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>

2. <span data-ttu-id="2e610-p111">**オフライン アクセス**を禁止、常に許可、または指定の日数 (ラベル適用後の経過日数) で許可します。オフライン アクセスを禁止または日数で制限すると、そのしきい値に達したときに、ユーザーは再認証される必要があり、ユーザーのアクセスがログに記録されます。詳細については、Rights Management 使用ライセンスに関する次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-p111">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

![管理者が定義したアクセス許可の設定](media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="2e610-147">オフライン アクセスのための Rights Management 使用ライセンス</span><span class="sxs-lookup"><span data-stu-id="2e610-147">Rights Management use license for offline access</span></span>

<span data-ttu-id="2e610-p112">ユーザーが機密ラベルで保護されているドキュメントや電子メールをオフラインで開くと、そのコンテンツの Azure Rights Management 使用ライセンスがユーザーに付与されます。この使用ライセンスは、ドキュメントまたは電子メールに対するユーザーの使用権とコンテンツの暗号化に使用された暗号化キーが含まれている証明書です。この使用ライセンスには、有効期限日 (設定されている場合) と使用ライセンスの有効期間も含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e610-p112">When a user opens a document or email offline that’s been protected by a sensitivity label, an Azure Rights Management use license for that content is granted to the user. This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content. The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="2e610-p113">有効期限日が設定されていない場合、テナントに対する使用ライセンスの既定の有効期間は 30 日間です。使用ライセンスの有効期間中は、そのコンテンツに対してユーザーが再認証または再承認されることはありません。このプロセスにより、インターネット接続がない場合でも保護されたドキュメントまたはメールをユーザーは引き続き開くことができます。使用ライセンスの有効期間が切れた場合、保護されたドキュメントまたはメールにユーザーが次回アクセスした際に、ユーザーの再認証または再承認が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2e610-p113">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This lets the user continue to open the protected document or email without an Internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="2e610-p114">再認証だけでなく、ポリシーとユーザー グループ メンバーシップの再評価も実行されます。そのため、ユーザーが最後にコンテンツにアクセスした後でポリシーやグループ メンバーシップに変更が加えられていると、同じドキュメントや電子メールに対して異なるアクセス結果がユーザーに示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e610-p114">In addition to reauthentication, the policy and user group membership is reevaluated. This means that users could experience different access results for the same document or email if there are changes in the policy or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="2e610-157">既定の 30 日の設定を変更する方法については、「[Rights Management 使用ライセンス](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-157">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="2e610-158">特定のユーザーまたはグループにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="2e610-158">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="2e610-159">特定のユーザーにアクセス許可を付与することで、ラベル付きコンテンツの操作を特定のユーザーにのみ許可することができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-159">You can grant permissions to specific people so that only they can interact with the labeled content.</span></span>

<span data-ttu-id="2e610-160">そのようにするには、次の簡単な 2 段階の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e610-160">Doing so is a straightforward two-step process:</span></span>

1. <span data-ttu-id="2e610-161">まず、ラベル付きコンテンツへのアクセス許可を割り当てるユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e610-161">First you add users or groups that will be assigned permissions to the labeled content.</span></span>
2. <span data-ttu-id="2e610-162">次に、該当するユーザーに付与するラベル付きコンテンツへのアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e610-162">Then you choose which permissions those users have for the labeled content.</span></span>

![ユーザーにアクセス許可を割り当てる際のオプション](media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="2e610-164">ユーザーまたはグループの追加</span><span class="sxs-lookup"><span data-stu-id="2e610-164">Add users or groups</span></span>

<span data-ttu-id="2e610-165">アクセス許可を割り当てるときには、次の選択が可能です。</span><span class="sxs-lookup"><span data-stu-id="2e610-165">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="2e610-p115">組織内のすべてのユーザー (すべてのテナント メンバー)。この設定ではゲスト アカウントが除外されます。</span><span class="sxs-lookup"><span data-stu-id="2e610-p115">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>
- <span data-ttu-id="2e610-168">特定のユーザーまたは電子メールが有効なセキュリティ グループ、配布グループ、Office 365 グループ、または動的配布グループ。</span><span class="sxs-lookup"><span data-stu-id="2e610-168">Any specific user or email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span> 
- <span data-ttu-id="2e610-169">組織外の電子メール アドレスまたはドメイン (gmail.com、hotmail.com、outlook.com など)。</span><span class="sxs-lookup"><span data-stu-id="2e610-169">Any email address or domain outside your organization, such as gmail.com, hotmail.com, or outlook.com.</span></span>

<span data-ttu-id="2e610-170">すべてのテナント メンバーを選択する場合やディレクトリを参照する場合は、ユーザーまたはグループに電子メール アドレスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="2e610-170">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="2e610-p116">ベスト プラクティスとして、ユーザーではなくグループを使用します。この方針により、シンプルな構成を維持できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-p116">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="2e610-173">アクセス許可の選択</span><span class="sxs-lookup"><span data-stu-id="2e610-173">Choose permissions</span></span>

<span data-ttu-id="2e610-174">該当するユーザーまたはグループに付与するアクセス許可を選択するときには、次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-174">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="2e610-175">既定の権限のグループ (「共同制作者」や「レビュー担当者」など) で[事前定義されたアクセス許可レベル](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)。</span><span class="sxs-lookup"><span data-stu-id="2e610-175">A [predefined permissions level](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="2e610-176">カスタムの権限のグループ。この場合は任意のアクセス許可を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-176">A Custom group of rights, where you choose whichever permissions you want.</span></span>

<span data-ttu-id="2e610-177">それぞれの具体的なアクセス許可に関する詳細については、「[使用権限と説明](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-177">For more information on each specific permission, see [Usage rights and descriptions](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![既定またはカスタムのアクセス許可を選択する際のオプション](media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="2e610-p117">同じラベルで異なるユーザーに異なるアクセス許可を付与できます。たとえば、次のスクリーンショットに示すように、単一のラベルで一部のユーザーを「レビュー担当者」として割り当てて、別のユーザーを「共同作成者」として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-p117">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown below.</span></span>

<span data-ttu-id="2e610-p118">これを行うには、ユーザーまたはグループを追加してアクセス許可を割り当て、その設定を保存します。その後で、この手順 (ユーザーの追加とアクセス許可の割り当て) を繰り返して、そのたびに保存します。この構成は、異なるユーザーに異なるアクセス許可を定義することが必要になるたびに実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-p118">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can do this as often as necessary, to define different permissions for different users.</span></span>

![異なるアクセス許可を持つ異なるユーザー](media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="2e610-185">常にフル コントロールを持つ Rights Management 発行者 (機密ラベルを適用するユーザー)</span><span class="sxs-lookup"><span data-stu-id="2e610-185">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="2e610-p119">機密ラベルに対する暗号化には Azure RMS が使用されます。ユーザーがドキュメントや電子メールを保護するために Azure RMS を使用して機密ラベルを適用すると、そのユーザーはそのコンテンツに対する Rights Management 発行者になります。</span><span class="sxs-lookup"><span data-stu-id="2e610-p119">Encryption for a sensitivity label uses Azure RMS. When a user applies a sensitivity label to protect a document or email by using Azure RMS, that user becomes the Rights Management issuers for that content.</span></span>

<span data-ttu-id="2e610-188">Rights Management 発行者には、常に、ドキュメントや電子メールに対するフル コントロールのアクセス許可が付与されます。さらに、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="2e610-188">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="2e610-189">保護設定に有効期限日が含まれている場合、Rights Management 発行者は、その期日が過ぎていてもドキュメントや電子メールを開いて編集できます。</span><span class="sxs-lookup"><span data-stu-id="2e610-189">If the protection settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="2e610-190">Rights Management 発行者は、常に、オフラインでドキュメントや電子メールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2e610-190">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="2e610-191">Rights Management 発行者は、失効後のドキュメントも開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-191">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="2e610-192">詳細については、「[Rights Management 発行者と Rights Management 所有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-192">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="2e610-193">ユーザーがアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="2e610-193">Let users assign permissions</span></span>

<span data-ttu-id="2e610-194">これらのオプションを使用すると、ユーザーがコンテンツに機密度ラベルを手動で適用するときにアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-194">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="2e610-195">Outlook では、ユーザーは [[転送不可](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails)] オプションと同等の制限を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-195">In Outlook, a user can enforce restrictions equivalent to the [Do Not Forward](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) option.</span></span> <span data-ttu-id="2e610-196">このオプションは Windows での Outlook でネイティブにサポートされており、Azure Information Protection 統合ラベル付けクライアントをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2e610-196">This option is supported natively in Outlook on Windows, and does not require you to install the Azure Information Protection unified labeling client.</span></span>
- <span data-ttu-id="2e610-197">Word、PowerPoint、Excel で、ユーザーは特定のユーザー、グループ、または組織のアクセス許可レベルを選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="2e610-197">In Word, PowerPoint, and Excel, a user is prompted to select a permission level for specific users, groups, or organizations.</span></span> <span data-ttu-id="2e610-198">このオプションはこれらの Office アプリではネイティブにサポートされていないため、ユーザーは Azure Information Protection 統合ラベル付けクライアントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e610-198">This option is not supported natively in these Office apps, so your users must install the Azure Information Protection unified labeling client.</span></span>

<span data-ttu-id="2e610-199">これらのオプションは、機密度ラベルが表示されるアプリを決定します。</span><span class="sxs-lookup"><span data-stu-id="2e610-199">These options determine in which apps the sensitivity label will appear:</span></span>

- <span data-ttu-id="2e610-200">機密度ラベルで Outlook オプションのみが有効になっている場合、ラベルは Outlook でのみユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e610-200">If the sensitivity label has only the Outlook option enabled, the label will appear to users only in Outlook.</span></span>
- <span data-ttu-id="2e610-201">機密度ラベルで Word、PowerPoint、Excel オプションのみが有効になっている場合、ラベルはこれらのアプリでのみユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e610-201">If the sensitivity label has only the Word, PowerPoint, and Excel option enabled, the label will appear to users only in those apps.</span></span>
- <span data-ttu-id="2e610-202">機密度ラベルの両方のオプションが有効になっている場合、利用可能なすべてのアプリ (Outlook、Word、PowerPoint、Excel) のユーザーにラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e610-202">If the sensitivity label has both options enabled, the label will appear to users in all of the available apps: Outlook, Word, PowerPoint, and Excel.</span></span>

<span data-ttu-id="2e610-203">ユーザーがアクセス許可を割り当てることができる機密度ラベルは、ユーザーが手動でのみコンテンツに適用できます。自動適用したり、推奨ラベルとして使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2e610-203">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

> [!NOTE]
> <span data-ttu-id="2e610-204">ユーザーがアクセス許可を割り当てることができるようになるには、Azure Information Protection サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e610-204">Letting users assign permissions requires an Azure Information Protection subscription.</span></span> <span data-ttu-id="2e610-205">この機能を Word、PowerPoint、Excel で使用するには、[Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)をダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e610-205">To use this feature in Word, PowerPoint, and Excel, you must download and install the [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> <span data-ttu-id="2e610-206">これらの Office アプリでは、Azure Information Protection クライアントを必要としないように、この機能のネイティブ サポートに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="2e610-206">We're working on native support for this feature in these Office apps, so that they won't require the Azure Information Protection client.</span></span> <span data-ttu-id="2e610-207">また、このクライアントは Windows でのみ実行されるため、この機能は Mac、iOS、Android、または Web 用 Office ではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2e610-207">Also, the client runs only on Windows, so this feature is not yet supported on Mac, iOS, Android, or Office for the web.</span></span>

![ユーザー定義のアクセス許可の暗号化設定](media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="2e610-209">Outlook の制限</span><span class="sxs-lookup"><span data-stu-id="2e610-209">Outlook restrictions</span></span>

<span data-ttu-id="2e610-210">Outlook では、ユーザーがメッセージにアクセス許可を割り当てることができる機密度ラベルを適用する場合、制限は [転送不可] オプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="2e610-210">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="2e610-211">メッセージの上部にラベル名と説明が表示されます。これは、コンテンツが保護されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="2e610-211">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="2e610-212">Word、PowerPoint、Excel ([次のセクション](#word-powerpoint-and-excel-permissions)参照) とは異なり、ユーザーは特定のアクセス許可を選択するよう求められません。</span><span class="sxs-lookup"><span data-stu-id="2e610-212">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![Outlook のメッセージに適用される機密度ラベル](media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="2e610-214">[転送不可] オプションがメールに適用されると、メールは暗号化され、受信者は認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e610-214">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="2e610-215">それにより、受信者はそれを転送したり、印刷したり、コピーしたりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="2e610-215">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="2e610-216">たとえば、Outlook クライアントでは、[転送] ボタン、[名前を付けて保存] および [印刷] メニュー オプションは使用できず、[宛先]、[CC]、または [BCC] ボックスで受信者を追加または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2e610-216">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="2e610-217">メールに添付されている保護されていない Office ドキュメントは、自動的に同じ制限を継承します。</span><span class="sxs-lookup"><span data-stu-id="2e610-217">Unprotected Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="2e610-218">これらのドキュメントに適用される使用権は、[コンテンツの編集]、[編集]、[保存]、[表示]、[開く]、[読み取り]、および [マクロの許可] です。</span><span class="sxs-lookup"><span data-stu-id="2e610-218">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="2e610-219">ユーザーが添付ファイルに別の使用権を要求する場合、または添付ファイルがこの継承された保護をサポートする Office ドキュメントでない場合は、メールに添付する前にファイルを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e610-219">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="2e610-220">Word、PowerPoint、および Excel のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2e610-220">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="2e610-221">Word、PowerPoint、および Excel では、ユーザーがドキュメントにアクセス許可を割り当てることができる機密度ラベルを適用すると、次のようにコンテンツを保護するように求められます。</span><span class="sxs-lookup"><span data-stu-id="2e610-221">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to protect the content as shown below.</span></span>

<span data-ttu-id="2e610-222">その場合、ユーザーは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2e610-222">The user can:</span></span>

- <span data-ttu-id="2e610-223">ビューアー ([表示のみ] アクセス許可を割り当てる) または共同作成者 ([表示]、[編集]、[コピー]、および [印刷] アクセス許可を割り当てる) などのアクセス許可レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e610-223">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="2e610-224">ユーザー、グループ、または組織を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e610-224">Select users, groups, or organizations.</span></span> <span data-ttu-id="2e610-225">これには、組織内外のユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e610-225">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="2e610-226">選択したユーザがコンテンツにアクセスできなくなる有効期限を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e610-226">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="2e610-227">詳細については、上記のセクション「[オフライン アクセスのための Rights Management 使用ライセンス](#rights-management-use-license-for-offline-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-227">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![ユーザーがカスタムのアクセス許可で保護するためのオプション](media/sensitivity-aip-custom-permissions-dialog.png)

## <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="2e610-229">ラベルが適用された場合の既存の暗号化</span><span class="sxs-lookup"><span data-stu-id="2e610-229">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="2e610-230">機密ラベルをコンテンツに適用する前に、ユーザーが他の保護設定を適用してコンテンツを既に暗号化している場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e610-230">Before a sensitivity label is applied to content, it's possible that a user already encrypted the content by applying some other protection setting.</span></span> <span data-ttu-id="2e610-231">たとえば、ユーザーが以下を適用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e610-231">For example, a user might have applied:</span></span>

- <span data-ttu-id="2e610-232">**転送不可**オプション。</span><span class="sxs-lookup"><span data-stu-id="2e610-232">The **Do Not Forward** option.</span></span>
- <span data-ttu-id="2e610-233">Azure Information Protection の統合ラベル付けクライアントを使用したカスタム保護。</span><span class="sxs-lookup"><span data-stu-id="2e610-233">Custom protection by using the Azure Information Protection unified labeling client.</span></span>
- <span data-ttu-id="2e610-234">ラベルには関連付けされずにコンテンツを暗号化する Azure Rights Management Service (RMS) テンプレート。</span><span class="sxs-lookup"><span data-stu-id="2e610-234">An Azure Rights Management Service (RMS) template that encrypts the content but is not associated with a label.</span></span>

<span data-ttu-id="2e610-235">次の表は、機密ラベルがコンテンツに適用されたときに既存の暗号化がどうなるかについての説明です。</span><span class="sxs-lookup"><span data-stu-id="2e610-235">This table describe what happens to existing encryption when a sensitivity label is applied to that content.</span></span>
<br/>
<br/>

| |<span data-ttu-id="2e610-236">**ユーザーが暗号化をオフにして機密ラベルを適用する**</span><span class="sxs-lookup"><span data-stu-id="2e610-236">**User applies a sensitivity label with encryption turned off**</span></span>|<span data-ttu-id="2e610-237">**ユーザーが暗号化をオンにして機密ラベルを適用する**</span><span class="sxs-lookup"><span data-stu-id="2e610-237">**User applies a sensitivity label with encryption turned on**</span></span>|<span data-ttu-id="2e610-238">**ユーザーが保護を解除してラベルを適用する**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2e610-238">**User applies a label with Remove Protection**<sup>1</sup></span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e610-239">**転送不可**</span><span class="sxs-lookup"><span data-stu-id="2e610-239">**Do Not Forward**</span></span>|<span data-ttu-id="2e610-240">メール - 保護が解除されます</span><span class="sxs-lookup"><span data-stu-id="2e610-240">Email - Protection is removed</span></span><br/><span data-ttu-id="2e610-241">ドキュメント - 保護が維持されます</span><span class="sxs-lookup"><span data-stu-id="2e610-241">Document - Protection is preserved</span></span>|<span data-ttu-id="2e610-242">ラベルの保護が適用されます</span><span class="sxs-lookup"><span data-stu-id="2e610-242">Label protection is applied</span></span>|<span data-ttu-id="2e610-243">**転送不可**が削除されます</span><span class="sxs-lookup"><span data-stu-id="2e610-243">**Do Not Forward** is removed</span></span>|
|<span data-ttu-id="2e610-244">**カスタム保護**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2e610-244">**Custom protection**<sup>1</sup></span></span>|<span data-ttu-id="2e610-245">保護が維持されます</span><span class="sxs-lookup"><span data-stu-id="2e610-245">Protection is preserved</span></span>|<span data-ttu-id="2e610-246">ラベルの保護が適用されます</span><span class="sxs-lookup"><span data-stu-id="2e610-246">Label protection is applied</span></span>|<span data-ttu-id="2e610-247">カスタム保護が解除されます</span><span class="sxs-lookup"><span data-stu-id="2e610-247">Custom protection is removed</span></span>|
|<span data-ttu-id="2e610-248">**Azure RMS テンプレート**</span><span class="sxs-lookup"><span data-stu-id="2e610-248">**Azure RMS template**</span></span>|<span data-ttu-id="2e610-249">保護が維持されます</span><span class="sxs-lookup"><span data-stu-id="2e610-249">Protection is preserved</span></span>|<span data-ttu-id="2e610-250">ラベルの保護が適用されます</span><span class="sxs-lookup"><span data-stu-id="2e610-250">Label protection is applied</span></span>|<span data-ttu-id="2e610-251">カスタム保護が解除されます</span><span class="sxs-lookup"><span data-stu-id="2e610-251">Custom protection is removed</span></span>|

<span data-ttu-id="2e610-252"><sup>1</sup>これらは、Azure Information Protection のラベル付けクライアントでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2e610-252"><sup>1</sup>This is supported only in the Azure Information Protection labeling client.</span></span>

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a><span data-ttu-id="2e610-253">OneDrive および SharePoint に暗号化されたコンテンツを保存する</span><span class="sxs-lookup"><span data-stu-id="2e610-253">Storing encrypted content in OneDrive and SharePoint</span></span>

<span data-ttu-id="2e610-p129">OneDrive および SharePoint に保存されているファイルに暗号化を適用すると、サービスは該当するファイルのコンテンツを処理できなくなります。そのため、共同編集、電子情報開示、検索、Delve などの共同作業機能が動作しなくなります。さらに、データ損失防止 (DLP) ポリシーはメタデータ (Office 365 のラベルを含む) にのみ作用し、暗号化されたファイルのコンテンツ (ファイル内のクレジット カード番号など) には作用しなくなります。</span><span class="sxs-lookup"><span data-stu-id="2e610-p129">Be aware that when encryption is applied to files stored in OneDrive and SharePoint, the service cannot process the contents of these files. This means that features such as co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Also, data loss prevention (DLP) policies can work only with the metadata (including Office 365 labels) but not the contents of encrypted files (such as credit card numbers within files).</span></span>

<span data-ttu-id="2e610-p130">これは、OneDrive および SharePoint に保存されているコンテンツにのみ当てはまります。Exchange Online では、メール フロー ルール (トランスポート ルールとも呼ばれる) で[スーパー ユーザー アカウント](https://docs.microsoft.com/azure/information-protection/configure-super-users)が使用されるため、暗号化されたコンテンツのスキャンと DLP ポリシーの強制適用が可能です。</span><span class="sxs-lookup"><span data-stu-id="2e610-p130">This applies only to content stored in OneDrive and SharePoint. In Exchange Online, mail flow rules (also known as transport rules) use the [super user account](https://docs.microsoft.com/azure/information-protection/configure-super-users) so that they can scan encrypted content and enforce DLP policies.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="2e610-259">重要な前提条件</span><span class="sxs-lookup"><span data-stu-id="2e610-259">Important prerequisites</span></span>

<span data-ttu-id="2e610-260">暗号化を使用する前に、次のタスクの実行が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e610-260">Before you can use encryption, you might need to perform these tasks.</span></span>

### <a name="activating-azure-rights-management"></a><span data-ttu-id="2e610-261">Azure Rights Management を有効化する</span><span class="sxs-lookup"><span data-stu-id="2e610-261">Activating Azure Rights Management</span></span>

<span data-ttu-id="2e610-p131">機密ラベルでの暗号化を使用する場合は、Azure Rights Management サービスがテナントで有効化されている必要があります。新しいテナントでは、このサービスが既定でオンになっていますが、手動で有効化することが必要になる場合もあります。詳細については、「[Rights Management をアクティブにする](https://docs.microsoft.com/azure/information-protection/activate-service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-p131">To use encryption in sensitivity labels, the Azure Rights Management service needs to be activated in your tenant. In newer tenants, the service is on by default, but you might need to manually activate the service. For more information, see [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="2e610-265">Azure Information Protection 用に Exchange を構成する</span><span class="sxs-lookup"><span data-stu-id="2e610-265">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="2e610-p132">ユーザーが Outlook で電子メールの保護のためにラベルを適用するまでは、Azure Information Protection 用に Exchange を構成する必要はありません。ただし、Exchange が Azure Information Protection 用に構成されるまで、Exchange には Azure Rights Management 保護の使用よる完全な機能が備わりません。</span><span class="sxs-lookup"><span data-stu-id="2e610-p132">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to protect their emails. However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="2e610-268">たとえば、ユーザーは保護された電子メールを携帯電話や Outlook on the web で表示できません。また、保護された電子メールは検索用のインデックスを作成できません。さらに、Rights Management 保護用に Exchange Online DLP を構成することもできません。</span><span class="sxs-lookup"><span data-stu-id="2e610-268">For example, users cannot view protected emails on mobile phones or with Outlook on the web, protected emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="2e610-269">このような追加のシナリオを Exchange でサポートする場合は、次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-269">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="2e610-270">Exchange Online の場合は、「[Exchange Online: IRM 構成](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration)」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e610-270">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration).</span></span>
- <span data-ttu-id="2e610-271">Exchange On-Premises の場合は、[RMS コネクタを展開して Exchange サーバーを構成する](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector)必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e610-271">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector).</span></span> 
