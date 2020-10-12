---
title: 秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する
f1.keywords:
- NOCSH
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
description: アクセスと使用を制限してデータを保護する暗号化のための秘密度ラベルを構成します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a734d6f71a943964775477199025180d1a41426e
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408627"
---
# <a name="restrict-access-to-content-by-using-sensitivity-labels-to-apply-encryption"></a><span data-ttu-id="f2c8d-103">秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="f2c8d-103">Restrict access to content by using sensitivity labels to apply encryption</span></span>

><span data-ttu-id="f2c8d-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="f2c8d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f2c8d-p101">機密ラベルを作成するときに、そのラベルが適用されるコンテンツへのアクセスを制限できます。たとえば、機密ラベルに対応する暗号化の設定によって、次のようにコンテンツを保護できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p101">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="f2c8d-107">組織内のユーザーのみが機密ドキュメントや電子メールを開けるようにする。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="f2c8d-108">宣伝広告用のドキュメントや電子メールは、マーケティング部門のユーザーのみが編集および印刷できるようにして、その他の組織内のユーザーは閲覧のみできるようにする。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="f2c8d-109">内部の再編成に関するニュースが含まれている電子メールは、ユーザーが転送や情報のコピーをできないようにする。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="f2c8d-110">ビジネス パートナーに送信する現行の価格リストは、指定した日付以降は開けないようにする。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="f2c8d-111">ドキュメントや電子メールを暗号化するときには、次のようにしてコンテンツへのアクセスが制限されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="f2c8d-112">暗号化の解除は、ラベルの暗号化設定で許可されているユーザーのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-112">Can be decrypted only by users authorized by the label's encryption settings.</span></span>
- <span data-ttu-id="f2c8d-113">暗号化は、ファイルの場所 (組織内外) を問わず、ファイル名が変更されていても維持されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file's renamed.</span></span>
- <span data-ttu-id="f2c8d-114">保存中 (OneDrive アカウントなど) と転送中 (インターネットを行き来するメールなど) の両方で暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, email as it traverses the internet).</span></span>

<span data-ttu-id="f2c8d-115">最後に、管理者は、暗号化に適用する秘密度ラベルを構成するときに、次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-115">Finally, as an admin, when you configure a sensitivity label to apply encryption, you can choose either to:</span></span>

- <span data-ttu-id="f2c8d-116">**アクセス許可を割り当てます**。これにより、どのユーザーがそのラベルのコンテンツにどのアクセス許可を取得するかを正確に決定します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-116">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="f2c8d-117">ラベルをコンテンツに適用するときに、**ユーザーがアクセス許可を割り当てる**ことができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-117">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="f2c8d-118">このようにして、組織内のユーザーに、共同作業を行って作業を完了するために必要な柔軟性を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-118">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="f2c8d-119">暗号化の設定は、Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、またはセキュリティ/コンプライアンス センターで[秘密度ラベルを作成](create-sensitivity-labels.md)するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-119">The encryption settings are available when you [create a sensitivity label](create-sensitivity-labels.md) in the Microsoft 365 compliance center, Microsoft 365 security center, or the Security & Compliance Center.</span></span>

## <a name="understand-how-the-encryption-works"></a><span data-ttu-id="f2c8d-120">暗号化のしくみを理解する</span><span class="sxs-lookup"><span data-stu-id="f2c8d-120">Understand how the encryption works</span></span>

<span data-ttu-id="f2c8d-121">暗号化では、Azure Information Protection の Azure Rights Management サービス (Azure RMS) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-121">Encryption uses the Azure Rights Management service (Azure RMS) from Azure Information Protection.</span></span> <span data-ttu-id="f2c8d-122">この保護ソリューションでは、暗号化ポリシー、ID ポリシー、および認識ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-122">This protection solution uses encryption, identity, and authorization policies.</span></span> <span data-ttu-id="f2c8d-123">詳細については、 Azure Information Protection ドキュメントの「[Azure Rights Management とは](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-123">To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) from the Azure Information Protection documentation.</span></span> 

<span data-ttu-id="f2c8d-124">暗号化ソリューションを使用すると、**スーパー ユーザー**機能により、認証されたユーザーとサービスが、組織のために暗号化されたデータの閲覧と検査を常に行えるようにできます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-124">When you use this encryption solution, the **super user** feature ensures that authorized people and services can always read and inspect the data that has been encrypted for your organization.</span></span> <span data-ttu-id="f2c8d-125">必要に応じて、暗号化を削除または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-125">If necessary, the encryption can then be removed or changed.</span></span> <span data-ttu-id="f2c8d-126">詳細については、「[Azure Information Protection および検索サービスまたはデータ回復用のスーパー ユーザーの構成](https://docs.microsoft.com/azure/information-protection/configure-super-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-126">For more information, see [Configuring super users for Azure Information Protection and discovery services or data recovery](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

## <a name="how-to-configure-a-label-for-encryption"></a><span data-ttu-id="f2c8d-127">暗号化のラベルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f2c8d-127">How to configure a label for encryption</span></span>

<span data-ttu-id="f2c8d-128">[秘密度ラベル を作成または編集](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)し、ウィザードの [**暗号化**] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-128">[Create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels), and on the **Encryption** page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="f2c8d-129">[**None**] (なし): 新しいラベルの既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-129">**None**: The default setting for a new label.</span></span> <span data-ttu-id="f2c8d-130">新規の暗号化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-130">No new encryption is applied.</span></span>
- <span data-ttu-id="f2c8d-131">[**Apply**] (適用): 暗号化が有効になります。管理者は暗号化の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-131">**Apply**: Turns on encryption, and you then specify encryption settings.</span></span>
- <span data-ttu-id="f2c8d-132">[**Remove**] (削除): ドキュメントまたはメールが暗号化されている場合は、暗号化が削除されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-132">**Remove**: Removes encryption if the document or email is encrypted.</span></span>

> [!NOTE]
> <span data-ttu-id="f2c8d-133">[**Remove**] (削除) オプションは、Azure Information Protection 統合ラベル付けクライアントでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-133">The **Remove** option is supported by the Azure Information Protection unified labeling client only.</span></span> <span data-ttu-id="f2c8d-134">組み込みのラベル付け機能を使用した場合、同オプションのラベルが Office アプリとサービスに表示されますが、これを選択した場合の暗号化の動作は、[**None**] (なし) の動作と同じになります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-134">When you use built-in labeling, a label with this option is visible in Office apps and services and if selected, the encryption behavior is the same as **None**.</span></span>

<span data-ttu-id="f2c8d-135">暗号化オプションの構成:</span><span class="sxs-lookup"><span data-stu-id="f2c8d-135">Configuring the encryption options:</span></span>

![暗号化用の秘密度ラベルのオプション](../media/encrytion-options-sensitivity-label.png)

### <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="f2c8d-137">ラベルが適用された場合の既存の暗号化への影響</span><span class="sxs-lookup"><span data-stu-id="f2c8d-137">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="f2c8d-138">暗号化されていないコンテンツに秘密度ラベルを適用する場合、選択可能な暗号化オプションを適用した場合の結果は、オプションの名前通りのものとなります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-138">If a sensitivity label is applied to unencrypted content, the outcome of the encryption options you can select is self-explanatory.</span></span> <span data-ttu-id="f2c8d-139">たとえば、暗号化を [**None**] (なし) に設定した場合、コンテンツでは暗号化されていない状態が続きます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-139">For example, if encryption is set to **None**, the content remains unencrypted.</span></span>

<span data-ttu-id="f2c8d-140">ただし、コンテンツが既に暗号化されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-140">However, the content might be already encrypted.</span></span> <span data-ttu-id="f2c8d-141">たとえば、別のユーザーにより次のようなアクセス許可などが適用されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-141">For example, another user might have applied:</span></span>

- <span data-ttu-id="f2c8d-142">ラベルにより求められた際にユーザーが定義したアクセス許可などのユーザー自身のアクセス許可、Azure Information Protection クライアントによるカスタムのアクセス許可、および Office アプリ内での**アクセス制限**によるドキュメントの保護。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-142">Their own permissions, which include user-defined permissions when prompted by a label, custom permissions by the Azure Information Protection client, and the **Restricted Access** document protection from within an Office app.</span></span>
- <span data-ttu-id="f2c8d-143">ラベルとは別にコンテンツの暗号化を行う、Azure Rights Management の保護テンプレート。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-143">An Azure Rights Management protection template that encrypts the content independently from a label.</span></span> <span data-ttu-id="f2c8d-144">このカテゴリには、権限の保護を使用して暗号化を適用する、メール フロー ルールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-144">This category includes mail flow rules that apply encryption by using rights protection.</span></span>
- <span data-ttu-id="f2c8d-145">管理者によって割り当てられているアクセス許可を使用して暗号化を適用するラベル。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-145">A label that applies encryption with permissions assigned by the administrator.</span></span>

<span data-ttu-id="f2c8d-146">そのようなコンテンツに秘密度ラベルが適用された際の既存の暗号化への影響を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-146">The following table identifies what happens to existing encryption when a sensitivity label is applied to that content:</span></span>

| |<span data-ttu-id="f2c8d-147">**暗号化: None (なし)**</span><span class="sxs-lookup"><span data-stu-id="f2c8d-147">**Encryption: None**</span></span>|<span data-ttu-id="f2c8d-148">**暗号化: Apply (適用)**</span><span class="sxs-lookup"><span data-stu-id="f2c8d-148">**Encryption: Apply**</span></span>|<span data-ttu-id="f2c8d-149">**暗号化: Remove (削除)**</span><span class="sxs-lookup"><span data-stu-id="f2c8d-149">**Encryption: Remove**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2c8d-150">**ユーザーによって指定されたアクセス許可**</span><span class="sxs-lookup"><span data-stu-id="f2c8d-150">**Permissions specified by a user**</span></span>|<span data-ttu-id="f2c8d-151">元の暗号化が維持されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-151">Original encryption is preserved</span></span>|<span data-ttu-id="f2c8d-152">新しいラベルの暗号化が適用されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-152">New label encryption is applied</span></span>|<span data-ttu-id="f2c8d-153">元の暗号化が削除されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-153">Original encryption is removed</span></span>|
|<span data-ttu-id="f2c8d-154">**保護テンプレート**</span><span class="sxs-lookup"><span data-stu-id="f2c8d-154">**Protection template**</span></span>|<span data-ttu-id="f2c8d-155">元の暗号化が維持されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-155">Original encryption is preserved</span></span>|<span data-ttu-id="f2c8d-156">新しいラベルの暗号化が適用されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-156">New label encryption is applied</span></span>|<span data-ttu-id="f2c8d-157">元の暗号化が削除されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-157">Original encryption is removed</span></span>|
|<span data-ttu-id="f2c8d-158">**管理者定義によるアクセス許可が適用されたラベル**</span><span class="sxs-lookup"><span data-stu-id="f2c8d-158">**Label with administator-defined permissions**</span></span>|<span data-ttu-id="f2c8d-159">元の暗号化が削除されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-159">Original encryption is removed</span></span>|<span data-ttu-id="f2c8d-160">新しいラベルの暗号化が適用されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-160">New label encryption is applied</span></span>|<span data-ttu-id="f2c8d-161">元の暗号化が削除されます</span><span class="sxs-lookup"><span data-stu-id="f2c8d-161">Original encryption is removed</span></span>|

<span data-ttu-id="f2c8d-162">新しいラベルの暗号化が適用された場合、または元の暗号化が削除された場合にそれが実際に実行されるのは、このアクションをサポートする次の使用権限または役割が、ラベルの適用を行うユーザーに付与されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-162">Note that in the cases where the new label encryption is applied or the original encryption is removed, this happens only if the user applying the label has a usage right or role that supports this action:</span></span>

- <span data-ttu-id="f2c8d-163">「エクスポート」または「フル コントロール」の[使用権限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-163">The [usage right](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Export or Full Control.</span></span>
- <span data-ttu-id="f2c8d-164">[Rights Management 発行者または Rights Management 所有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)の役割、または[スーパー ユーザー](https://docs.microsoft.com/azure/information-protection/configure-super-users)。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-164">The role of [Rights Management issuer or Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner), or [super user](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

<span data-ttu-id="f2c8d-165">ユーザーに上記のいずれかの権限または役割が付与されていない場合はラベルを適用することはできず、そのため元の暗号化が維持されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-165">If the user doesn't have one of these rights or roles, the label can't be applied and so the original encryption is preserved.</span></span> <span data-ttu-id="f2c8d-166">ユーザーには次のメッセージが表示されます: **You don't have permission to make this change to the sensitivity label. Please contact the content owner.** (秘密度ラベルを変更するためのアクセス許可がありません。コンテンツの所有者に連絡してください。)</span><span class="sxs-lookup"><span data-stu-id="f2c8d-166">The user sees the following message: **You don't have permission to make this change to the sensitivity label. Please contact the content owner.**</span></span>

<span data-ttu-id="f2c8d-167">たとえば、メール メッセージに「転送不可」を適用するユーザーは、スレッドのラベルを付け直して暗号化を置き換えたり削除したりできます。これらのユーザーはすべてのメールの Rights Management 所有者であるためです。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-167">For example, the person who applies Do Not Forward to an email message can relabel the thread to replace the encryption or remove it, because they are the Rights Management owner for the email.</span></span> <span data-ttu-id="f2c8d-168">ただし、スーパー ユーザーを除き、このメールの受信者はメールのラベルを付け直すことはできません。必要な使用権限が受信者に付与されていないためです。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-168">But with the exception of super users, recipients of this email can't relabel it because they don't have the required usage rights.</span></span>

#### <a name="email-attachments-for-encrypted-email-messages"></a><span data-ttu-id="f2c8d-169">暗号化されたメール メッセージの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="f2c8d-169">Email attachments for encrypted email messages</span></span>

<span data-ttu-id="f2c8d-170">メール メッセージが何らかの方法で暗号化されている場合、そのメールに添付されている暗号化されていないドキュメントでは、自動的に同じ暗号化設定が継承されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-170">When an email message is encrypted by any method, any unencrypted Office documents that are attached to the email automatically inherit the same encryption settings.</span></span>

<span data-ttu-id="f2c8d-171">既に暗号化されているドキュメントが添付ファイルとして追加された場合は常に、元の暗号化がそのドキュメントで維持されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-171">Documents that are already encrypted and then added as attachments always preserve their original encryption.</span></span>

## <a name="configure-encryption-settings"></a><span data-ttu-id="f2c8d-172">暗号化設定を構成する</span><span class="sxs-lookup"><span data-stu-id="f2c8d-172">Configure encryption settings</span></span>

<span data-ttu-id="f2c8d-173">秘密度ラベルを作成または編集するためにウィザードの [**Encryption**] (暗号化) ページで [**Apply**] (適用) を選択するときは、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-173">When you select **Apply** on the **Encryption** page of the wizard to create or edit a sensitivity label, choose whether to:</span></span>

- <span data-ttu-id="f2c8d-174">[**Assign permissions now**] (アクセス許可を今すぐ割り当てる): ラベルが適用されているコンテンツに対し、どのアクセス許可をどのユーザーに付与するかを正確に決められます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-174">**Assign permissions now**, so that you can determine exactly which users get which permissions to content that has the label applied.</span></span> <span data-ttu-id="f2c8d-175">詳細については、次のセクション「[アクセス許可を今すぐ割り当てる](#assign-permissions-now)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-175">For more information, see the next section [Assign permissions now](#assign-permissions-now).</span></span>
- <span data-ttu-id="f2c8d-176">[**Let users assign permissions**] (アクセス許可の割り当てをユーザーに許可する): ユーザーがラベルをコンテンツに適用するときに、ユーザーがアクセス許可を割り当てることを許可します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-176">**Let users assign permissions** when your users apply the label to content.</span></span> <span data-ttu-id="f2c8d-177">このオプションを使用した場合、共同作業や業務を行う上で必要な柔軟性を組織内のユーザーに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-177">With this option, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="f2c8d-178">詳細については、このページのセクション「[ユーザーがアクセス許可を割り当てる](#let-users-assign-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-178">For more information, see the [Let users assign permissions](#let-users-assign-permissions) section on this page.</span></span>

<span data-ttu-id="f2c8d-179">たとえば、最も機密性の高いコンテンツに適用される「**極秘**」という名前の機密ラベルがある場合、そのコンテンツに対してどのタイプのアクセス許可を誰に付与するのかについて、この時点で決めることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-179">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you might want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="f2c8d-180">一方、「**業務契約**」という名前の機密ラベルがあり、組織のワークフローの規定によりこのコンテンツに関して従業員と外部ユーザーの間でアドホック ベースで共同作業を行う必要がある場合は、従業員がラベルを割り当てる際に、アクセス許可を誰に付与するかを従業員が決定できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-180">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you might want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="f2c8d-181">この柔軟性により、ユーザーの生産性が向上し、特定のシナリオに対処するために管理者に新しい機密度ラベルを更新または作成を要求することを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-181">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

<span data-ttu-id="f2c8d-182">[Choosing whether to assign permissions now] (アクセス許可を今すぐ割り当てる) または [Let users assign permissions] (アクセス許可の割り当てをユーザーに許可する) の選択:</span><span class="sxs-lookup"><span data-stu-id="f2c8d-182">Choosing whether to assign permissions now or let users assign permissions:</span></span>

![ユーザーまたは管理者が定義したアクセス許可を追加するオプション](../media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a><span data-ttu-id="f2c8d-184">アクセス許可を今すぐ割り当てる</span><span class="sxs-lookup"><span data-stu-id="f2c8d-184">Assign permissions now</span></span>

<span data-ttu-id="f2c8d-185">以下のオプションを使用して、このラベルが適用されるメールやドキュメントにアクセスできるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-185">Use the following options to control who can access email or documents to which this label is applied.</span></span> <span data-ttu-id="f2c8d-186">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-186">You can:</span></span>

- <span data-ttu-id="f2c8d-p116">**ラベル付けされたコンテンツへのアクセスに有効期限を設定します。** 特定の日付または指定するラベル適用後の経過日数で有効期限が切れるようにします。期限が切れると、ユーザーはラベル付きのアイテムを開くことができなくなります。日付を指定した場合、現在のタイム ゾーンでその日付の午前 0 時に有効期限が切れます。(一部のメール クライアントでは、キャッシュの仕組みにより、有効期限が適用されず、有効期限を過ぎたメールが表示されることがある点に注意してください。)</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p116">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won't be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients might not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>

- <span data-ttu-id="f2c8d-p117">**オフライン アクセス**を禁止、常に許可、または指定の日数 (ラベル適用後の経過日数) で許可します。オフライン アクセスを禁止または日数で制限すると、そのしきい値に達したときに、ユーザーは再認証される必要があり、ユーザーのアクセスがログに記録されます。詳細については、Rights Management 使用ライセンスに関する次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p117">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

<span data-ttu-id="f2c8d-194">暗号化されたコンテンツに対するアクセス制御の設定:</span><span class="sxs-lookup"><span data-stu-id="f2c8d-194">Settings for access control for encrypted content:</span></span>

![管理者が定義したアクセス許可の設定](../media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="f2c8d-196">オフライン アクセスのための Rights Management 使用ライセンス</span><span class="sxs-lookup"><span data-stu-id="f2c8d-196">Rights Management use license for offline access</span></span>

<span data-ttu-id="f2c8d-197">Azure Rights Management サービスの暗号化で保護されたドキュメントまたはメールをユーザーが開くと、そのコンテンツの Azure Rights Management の使用ライセンスがユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-197">When a user opens a document or email that's been protected by encryption from the Azure Rights Management service, an Azure Rights Management use license for that content is granted to the user.</span></span> <span data-ttu-id="f2c8d-198">使用ライセンスは、ドキュメントまたはメールに対するユーザーの使用権限およびコンテンツの暗号化に使用された暗号化キーが含まれている証明書です。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-198">This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content.</span></span> <span data-ttu-id="f2c8d-199">使用ライセンスに有効期限日が設定されている場合は、期限日と期間も使用ライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-199">The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="f2c8d-p119">有効期限日が設定されていない場合、テナントに対する使用ライセンスの既定の有効期間は 30 日間です。使用ライセンスの有効期間中は、そのコンテンツに対してユーザーが再認証または再承認されることはありません。このプロセスにより、インターネット接続がない場合でも保護されたドキュメントまたはメールをユーザーは引き続き開くことができます。使用ライセンスの有効期間が切れた場合、保護されたドキュメントまたはメールにユーザーが次回アクセスした際に、ユーザーの再認証または再承認が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p119">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This process lets the user continue to open the protected document or email without an internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="f2c8d-204">再認証に加え、暗号化設定とユーザー グループのメンバーシップが再評価を受けます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-204">In addition to reauthentication, the encryption settings and user group membership is reevaluated.</span></span> <span data-ttu-id="f2c8d-205">そのため、ユーザーが最後にコンテンツにアクセスした後に暗号化設定またはグループ メンバーシップに変更が加えられた場合、同じドキュメントやメールに対してのアクセス性が変化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-205">This means that users could experience different access results for the same document or email if there are changes in the encryption settings or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="f2c8d-206">既定の 30 日の設定を変更する方法については、「[Rights Management 使用ライセンス](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-206">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="f2c8d-207">特定のユーザーまたはグループにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="f2c8d-207">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="f2c8d-208">特定のユーザーのみがラベル付きのコンテンツを操作できるよう、特定のユーザーのみにアクセス許可を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-208">You can grant permissions to specific people so that only they can interact with the labeled content:</span></span>

1. <span data-ttu-id="f2c8d-209">最初に、ラベル付きコンテンツへのアクセス許可を割り当てるユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-209">First, add users or groups that will be assigned permissions to the labeled content.</span></span>

2. <span data-ttu-id="f2c8d-210">次に、これらのユーザーに付与するラベル付きコンテンツへのアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-210">Then, choose which permissions those users should have for the labeled content.</span></span>

<span data-ttu-id="f2c8d-211">アクセス許可の割り当て:</span><span class="sxs-lookup"><span data-stu-id="f2c8d-211">Assigning permissions:</span></span>

![ユーザーにアクセス許可を割り当てる際のオプション](../media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="f2c8d-213">ユーザーまたはグループの追加</span><span class="sxs-lookup"><span data-stu-id="f2c8d-213">Add users or groups</span></span>

<span data-ttu-id="f2c8d-214">アクセス許可を割り当てるときには、次の選択が可能です。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-214">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="f2c8d-p121">組織内のすべてのユーザー (すべてのテナント メンバー)。この設定ではゲスト アカウントが除外されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p121">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>

- <span data-ttu-id="f2c8d-217">すべての認証されたユーザー。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-217">Any authenticated users.</span></span> <span data-ttu-id="f2c8d-218">選択する前に、この設定の[要件と制限事項](#requirements-and-limitations-for-add-any-authenticated-users)を理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-218">Make sure you understand the [requirements and limitations](#requirements-and-limitations-for-add-any-authenticated-users) of this setting before selecting it.</span></span>

- <span data-ttu-id="f2c8d-219">Azure AD で、特定のユーザーまたは電子メールが有効なセキュリティ グループ、配布グループ、または Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-219">Any specific user or email-enabled security group, distribution group, or Microsoft 365 group ([formerly Office 365 group](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) in Azure AD.</span></span> <span data-ttu-id="f2c8d-220">Microsoft 365 グループは、静的メンバーシップまたは[動的メンバーシップ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-220">The Microsoft 365 group can have static or [dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="f2c8d-221">このグループの種類は Azure AD に同期されていないため、また、メールが有効になっていないセキュリティグループを使用できないため、[Exchange からの動的配布グループ](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-221">Note that you can't use a [dynamic distribution group from Exchange](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups) because this group type isn't synchronized to Azure AD, and you can't use a security group that isn't email-enabled.</span></span>

- <span data-ttu-id="f2c8d-222">任意のメール アドレスまたはドメイン。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-222">Any email address or domain.</span></span> <span data-ttu-id="f2c8d-223">この組織の任意のドメイン名を入力して、Azure AD を使用する別の組織のすべてのユーザーを指定するには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-223">Use this option to specify all users in another organization who uses Azure AD, by entering any domain name from that organization.</span></span> <span data-ttu-id="f2c8d-224">**gmail.com**、**hotmail.com**、**outlook.com** などのドメイン名を入力することにより、ソーシャル プロバイダーに対してこのオプションを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-224">You can also use this option for social providers, by entering their domain name such as **gmail.com**, **hotmail.com**, or **outlook.com**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2c8d-225">Azure AD を使用する組織のドメインを指定した場合、その特定のドメインへのアクセスを制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-225">If you specify a domain from an organization that uses Azure AD, you can't restrict access to that specific domain.</span></span> <span data-ttu-id="f2c8d-226">代わりに、Azure AD の検証済みドメインはすべて、指定したドメイン名を所有するテナントに自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-226">Instead, all verified domains in Azure AD are automatically included for the tenant that owns the domain name you specify.</span></span>

<span data-ttu-id="f2c8d-227">組織内のすべてのユーザーとグループを選択するか、ディレクトリを参照する場合、ユーザーまたはグループにはメール アドレスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-227">When you choose all users and groups in your organization or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="f2c8d-p126">ベスト プラクティスとして、ユーザーではなくグループを使用します。この方針により、シンプルな構成を維持できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p126">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

##### <a name="requirements-and-limitations-for-add-any-authenticated-users"></a><span data-ttu-id="f2c8d-230">[Add any authenticated users] (すべての認証されたユーザーを追加) の要件と制限事項</span><span class="sxs-lookup"><span data-stu-id="f2c8d-230">Requirements and limitations for "Add any authenticated users"</span></span>

<span data-ttu-id="f2c8d-231">この設定では、ラベルによって暗号化されているコンテンツにアクセスできるユーザーは制限されませんが、コンテンツの暗号化は実行され、コンテンツの使用 (アクセス許可) およびコンテンツへのアクセス (有効期限とオフライン アクセス) を制限するオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-231">This setting doesn't restrict who can access the content that the label encrypts, while still encrypting the content and providing you with options to restrict how the content can be used (permissions), and accessed (expiry and offline access).</span></span> <span data-ttu-id="f2c8d-232">ただし、暗号化されたコンテンツを開くために使用するアプリケーションでは、使用する認証方法がサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-232">However, the application opening the encrypted content must be able to support the authentication being used.</span></span> <span data-ttu-id="f2c8d-233">このため、Google などのフェデレーションされたソーシャル プロバイダーやワンタイム パスコード認証はメールに対してのみ動作し、動作するのは Exchange Online を使用した場合のみになります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-233">For this reason, federated social providers such as Google, and onetime passcode authentication work for email only, and only when you use Exchange Online.</span></span> <span data-ttu-id="f2c8d-234">Microsoft アカウントは、Office 365 アプリおよび [Azure Information Protection ビューアー](https://portal.azurerms.com/#/download)で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-234">Microsoft accounts can be used with Office 365 apps and the [Azure Information Protection viewer](https://portal.azurerms.com/#/download).</span></span>

<span data-ttu-id="f2c8d-235">いずれの認証ユーザー設定の場合も、一般的なシナリオとして次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-235">Some typical scenarios for any authenticated users setting:</span></span>

- <span data-ttu-id="f2c8d-236">コンテンツの閲覧者は制限しないが、コンテンツの使用方法を制限したい。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-236">You don't mind who views the content, but you want to restrict how it is used.</span></span> <span data-ttu-id="f2c8d-237">たとえば、コンテンツの編集、コピー、または印刷を制限したい場合がこれに該当します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-237">For example, you don't want the content to be edited, copied, or printed.</span></span>
- <span data-ttu-id="f2c8d-238">コンテンツにアクセスするユーザーは制限しないが、コンテンツを開くユーザーを確認したい。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-238">You don't need to restrict who accesses the content, but you want to be able to confirm who opens it.</span></span>
- <span data-ttu-id="f2c8d-239">コンテンツの保存時と送信時の暗号化を要求する要件があるが、コンテンツに対するアクセス制御が必要ない場合。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-239">You have a requirement that the content must be encrypted at rest and in transit, but it doesn't require access controls.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="f2c8d-240">アクセス許可の選択</span><span class="sxs-lookup"><span data-stu-id="f2c8d-240">Choose permissions</span></span>

<span data-ttu-id="f2c8d-241">該当するユーザーまたはグループに付与するアクセス許可を選択するときには、次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-241">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="f2c8d-242">既定の権限のグループ (「共同制作者」や「レビュー担当者」など) で[事前定義されたアクセス許可レベル](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-242">A [predefined permissions level](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="f2c8d-243">カスタムのアクセス許可。1 つ以上の使用権限を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-243">Custom permissions, where you choose one or more usage rights.</span></span>

<span data-ttu-id="f2c8d-244">適切な許可の選択に役立つ詳細については、「[使用権限と説明](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-244">For more information to help you select the appropriate permissions, see [Usage rights and descriptions](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![既定またはカスタムのアクセス許可を選択する際のオプション](../media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="f2c8d-p129">同じラベルで異なるユーザーに異なるアクセス許可を付与できます。たとえば、次のスクリーンショットに示すように、単一のラベルで一部のユーザーを「レビュー担当者」として割り当てて、別のユーザーを「共同作成者」として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p129">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown in the following screenshot.</span></span>

<span data-ttu-id="f2c8d-p130">これを行うには、ユーザーまたはグループを追加してアクセス許可を割り当て、その設定を保存します。その後で、この手順 (ユーザーの追加とアクセス許可の割り当て) を繰り返して、そのたびに保存します。この構成は、異なるユーザーに異なるアクセス許可を定義することが必要になるたびに実行できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-p130">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can repeat this configuration as often as necessary, to define different permissions for different users.</span></span>

![異なるアクセス許可を持つ異なるユーザー](../media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="f2c8d-252">常にフル コントロールを持つ Rights Management 発行者 (機密ラベルを適用するユーザー)</span><span class="sxs-lookup"><span data-stu-id="f2c8d-252">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="f2c8d-253">秘密度ラベルの暗号化では、Azure Information Protection の Azure Rights Management サービスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-253">Encryption for a sensitivity label uses the Azure Rights Management service from Azure Information Protection.</span></span> <span data-ttu-id="f2c8d-254">ドキュメントやメールを保護するためにユーザーが暗号化を使用して秘密度ラベルを適用すると、そのユーザーはそのコンテンツに対する Rights Management 発行者になります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-254">When a user applies a sensitivity label to protect a document or email by using encryption, that user becomes the Rights Management issuer for that content.</span></span>

<span data-ttu-id="f2c8d-255">Rights Management 発行者には、ドキュメントまたはメールに対するフル コントロールのアクセス許可が必ず付与されます。これに加え、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-255">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="f2c8d-256">暗号化設定に有効期が含まれている場合、Rights Management 発行者は期限を過ぎても引き続きドキュメントまたはメールを開いて編集できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-256">If the encryption settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="f2c8d-257">Rights Management 発行者は、常に、オフラインでドキュメントや電子メールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-257">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="f2c8d-258">Rights Management 発行者は、失効後のドキュメントも開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-258">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="f2c8d-259">詳細については、「[Rights Management 発行者と Rights Management 所有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-259">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

### <a name="double-key-encryption"></a><span data-ttu-id="f2c8d-260">二重キー暗号化</span><span class="sxs-lookup"><span data-stu-id="f2c8d-260">Double Key Encryption</span></span>

> [!NOTE]
> <span data-ttu-id="f2c8d-261">この機能は現在、Azure Information Protection 統合ラベル付けクライアントでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-261">This feature is currently supported only by the Azure Information Protection unified labeling client.</span></span>

<span data-ttu-id="f2c8d-262">このオプションは、二重キー暗号化サービスを構成していて、このラベルを適用するファイルにこの二重キー暗号化を使用する必要がある場合にのみ選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-262">Select this option only after you have configured the Double Key Encryption service and you need to use this double key encryption for files that will have this label applied.</span></span>

<span data-ttu-id="f2c8d-263">詳細、前提条件、構成手順については、「[二重キー暗号化 (DKE)](double-key-encryption.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-263">For more information, prerequisites, and configuration instructions, see [Double Key Encryption (DKE)](double-key-encryption.md).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="f2c8d-264">ユーザーがアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="f2c8d-264">Let users assign permissions</span></span>

<span data-ttu-id="f2c8d-265">これらのオプションを使用すると、ユーザーがコンテンツに機密度ラベルを手動で適用するときにアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-265">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="f2c8d-266">Outlook では、ユーザーは選択した受信者に対して [[転送不可](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails)] オプションと同等の制限を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-266">In Outlook, a user can select restrictions equivalent to the [Do Not Forward](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) option for their chosen recipients.</span></span>

- <span data-ttu-id="f2c8d-267">Word、PowerPoint、Excel で、ユーザーは特定のユーザー、グループ、または組織に対して任意のアクセス許可を選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-267">In Word, PowerPoint, and Excel, a user is prompted to select their own permissions for specific users, groups, or organizations.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2c8d-268">Word、PowerPoint、Excel 用のこのオプションは、Azure Information Protection 統合ラベル付けクライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-268">This option for Word, PowerPoint, and Excel is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="f2c8d-269">組み込みのラベル付けを使用するアプリの場合は、[どのアプリがそれをサポートしているかを確認します](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-269">For apps that use built-in labeling, [check which apps support it](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint).</span></span>
    >
    > <span data-ttu-id="f2c8d-270">このオプションが選択されているもののユーザーのアプリでサポートされていない場合、そのラベルはユーザーに表示されないか、または一貫性のためにラベルは表示されますが、ユーザーへの説明メッセージとともに適用はされません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-270">If this option is selected but isn't supported for a user's app, either that label doesn't display to the user, or the label displays for consistency, but it can't be applied with an explanation message to users.</span></span>

<span data-ttu-id="f2c8d-271">選択するオプションがサポートされている場合に、秘密度ラベルがユーザーに表示されるどうかについて、次の表で確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-271">When the options are supported, use the following table to identify when users see the sensitivity label:</span></span>

|<span data-ttu-id="f2c8d-272">設定</span><span class="sxs-lookup"><span data-stu-id="f2c8d-272">Setting</span></span> |<span data-ttu-id="f2c8d-273">ラベルを Outlook で表示</span><span class="sxs-lookup"><span data-stu-id="f2c8d-273">Label visible in Outlook</span></span>|<span data-ttu-id="f2c8d-274">ラベルを Word、PowerPoint、Excel で表示</span><span class="sxs-lookup"><span data-stu-id="f2c8d-274">Label visible in Word, Excel, PowerPoint</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2c8d-275">**In Outlook, enforce restrictions equivalent to the Do Not Forward option** (Outlook で、[転送不可] オプションと同等の制限を適用する)</span><span class="sxs-lookup"><span data-stu-id="f2c8d-275">**In Outlook, enforce restrictions equivalent to the Do Not Forward option**</span></span>|<span data-ttu-id="f2c8d-276">はい</span><span class="sxs-lookup"><span data-stu-id="f2c8d-276">Yes</span></span> |<span data-ttu-id="f2c8d-277">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2c8d-277">No</span></span> |
|<span data-ttu-id="f2c8d-278">**In Word, PowerPoint, and Excel, prompt users to specify permissions** (Word、PowerPoint、Excel で、アクセス許可の指定をユーザーに求める) </span><span class="sxs-lookup"><span data-stu-id="f2c8d-278">**In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>|<span data-ttu-id="f2c8d-279">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2c8d-279">No</span></span> |<span data-ttu-id="f2c8d-280">はい</span><span class="sxs-lookup"><span data-stu-id="f2c8d-280">Yes</span></span>|

<span data-ttu-id="f2c8d-281">両方の設定を選択すると、ラベルは Outlook と Word、Excel、PowerPoint の両方で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-281">When both settings are selected, the label is therefore visible in both Outlook and in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="f2c8d-282">ユーザーがアクセス許可を割り当てることができる機密度ラベルは、ユーザーが手動でのみコンテンツに適用できます。自動適用したり、推奨ラベルとして使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-282">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

<span data-ttu-id="f2c8d-283">ユーザーが割り当てるアクセス許可の構成:</span><span class="sxs-lookup"><span data-stu-id="f2c8d-283">Configuring the user-assigned permissions:</span></span>

![ユーザー定義のアクセス許可の暗号化設定](../media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="f2c8d-285">Outlook の制限</span><span class="sxs-lookup"><span data-stu-id="f2c8d-285">Outlook restrictions</span></span>

<span data-ttu-id="f2c8d-286">Outlook では、ユーザーがメッセージにアクセス許可を割り当てることができる機密度ラベルを適用する場合、制限は [転送不可] オプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-286">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="f2c8d-287">メッセージの上部にラベル名と説明が表示されます。これは、コンテンツが保護されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-287">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="f2c8d-288">Word、PowerPoint、Excel ([次のセクション](#word-powerpoint-and-excel-permissions)参照) とは異なり、ユーザーは特定のアクセス許可を選択するよう求められません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-288">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![Outlook のメッセージに適用される機密度ラベル](../media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="f2c8d-290">[転送不可] オプションがメールに適用されると、メールは暗号化され、受信者は認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-290">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="f2c8d-291">それにより、受信者はそれを転送したり、印刷したり、コピーしたりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-291">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="f2c8d-292">たとえば、Outlook クライアントでは、[転送] ボタン、[名前を付けて保存] および [印刷] メニュー オプションは使用できず、[宛先]、[CC]、または [BCC] ボックスで受信者を追加または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-292">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="f2c8d-293">メールに添付されている暗号化されていない Office ドキュメントでは、自動的に同じ制限が継承されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-293">Unencrypted Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="f2c8d-294">これらのドキュメントに適用される使用権は、[コンテンツの編集]、[編集]、[保存]、[表示]、[開く]、[読み取り]、および [マクロの許可] です。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-294">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="f2c8d-295">ユーザーが添付ファイルに別の使用権を要求する場合、または添付ファイルがこの継承された保護をサポートする Office ドキュメントでない場合は、メールに添付する前にファイルを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-295">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="f2c8d-296">Word、PowerPoint、および Excel のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f2c8d-296">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="f2c8d-297">Word、PowerPoint、および Excel では、ドキュメントにアクセス許可を割り当てることをユーザーに許可する秘密度ラベルをユーザーが適用しようとすると、暗号化に際しての対象ユーザーとアクセス許可を指定するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-297">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to specify their choice of users and permissions when the encryption is applied.</span></span>

<span data-ttu-id="f2c8d-298">たとえば、Azure Information Protection の統合ラベル付けクライアントでは次のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-298">For example, with the Azure Information Protection unified labeling client, users can:</span></span>

- <span data-ttu-id="f2c8d-299">ビューアー ([表示のみ] アクセス許可を割り当てる) または共同作成者 ([表示]、[編集]、[コピー]、および [印刷] アクセス許可を割り当てる) などのアクセス許可レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-299">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="f2c8d-300">ユーザー、グループ、または組織を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-300">Select users, groups, or organizations.</span></span> <span data-ttu-id="f2c8d-301">これには、組織内外のユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-301">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="f2c8d-302">選択したユーザがコンテンツにアクセスできなくなる有効期限を設定します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-302">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="f2c8d-303">詳細については、上記のセクション「[オフライン アクセスのための Rights Management 使用ライセンス](#rights-management-use-license-for-offline-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-303">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![ユーザーがカスタムのアクセス許可で保護するためのオプション](../media/sensitivity-aip-custom-permissions-dialog.png)

<span data-ttu-id="f2c8d-305">組み込みのラベルの場合、ユーザーが次のオプションを選択すると同様のダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-305">For built-in labeling, users see the same dialog box if they select the following:</span></span>

- <span data-ttu-id="f2c8d-306">Windows: [**ファイル**] タブ > [**情報**] > [**文書の保護**] > [**アクセスの制限**] > [**制限アクセス**]</span><span class="sxs-lookup"><span data-stu-id="f2c8d-306">Windows: **File** tab > **Info** > **Protect Document** > **Restrict Access** > **Restricted Access**</span></span>

- <span data-ttu-id="f2c8d-307">MacOS: [**校閲**] タブ > [**保護**] > [**アクセス許可**] > [**制限アクセス**]</span><span class="sxs-lookup"><span data-stu-id="f2c8d-307">MacOS: **Review** tab > **Protection** > **Permissions** > **Restricted Access**</span></span>

## <a name="example-configurations-for-the-encryption-settings"></a><span data-ttu-id="f2c8d-308">暗号化の設定の構成例</span><span class="sxs-lookup"><span data-stu-id="f2c8d-308">Example configurations for the encryption settings</span></span>

<span data-ttu-id="f2c8d-309">以下の各例では、[機密ラベルを作成または編集する](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)ときに、ウィザードの **[暗号化]** ページから構成を行います。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-309">For each example that follows, do the configuration from the **Encryption** page of the wizard when you [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span> <span data-ttu-id="f2c8d-310">最初に、**[暗号化]** が **[適用]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-310">First make sure that the **Encryption** is set to **Apply**:</span></span>

![機密ラベル ウィザードで暗号化オプションを適用する](../media/apply-encryption-option.png)

### <a name="example-1-label-that-applies-do-not-forward-to-send-an-encrypted-email-to-a-gmail-account"></a><span data-ttu-id="f2c8d-312">例 1: 暗号化されたメールを Gmail アカウントに送信するために [転送不可] を適用するラベル</span><span class="sxs-lookup"><span data-stu-id="f2c8d-312">Example 1: Label that applies Do Not Forward to send an encrypted email to a Gmail account</span></span>

<span data-ttu-id="f2c8d-313">このラベルは Outlook および Outlook on the web でのみ表示され、Exchange Online を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-313">This label displays only in Outlook and Outlook on the web, and you must use Exchange Online.</span></span> <span data-ttu-id="f2c8d-314">Gmail アカウント (または組織外の他のメール アカウント) を使用しているユーザーに暗号化されたメールを送信する必要がある場合、このラベルを選択するようユーザーに指示します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-314">Instruct users to select this label when they need to send an encrypted email to people using a Gmail account (or any other email account outside your organization).</span></span>

<span data-ttu-id="f2c8d-315">ユーザーは、**[宛先]** ボックスに Gmail のメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-315">Your users type the Gmail email address in the **To** box.</span></span>  <span data-ttu-id="f2c8d-316">次に、ラベルを選択すると、メールに [転送不可] オプションが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-316">Then, they select the label and the Do Not Forward option is automatically added to the email.</span></span> <span data-ttu-id="f2c8d-317">その結果、受信者は、**[名前を付けて保存]** オプションを使用してメールを転送、印刷、コピー、またはメールボックス外に保存することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-317">The result is that recipients cannot forward the email, or print it, copy from it, or save the email outside their mailbox by using the **Save As** option.</span></span>

1. <span data-ttu-id="f2c8d-318">**[暗号化]** ページで: **[アクセス許可を今すぐ割り当てるか、それともユーザーに決定させますか?]** で、**[ラベルを適用するときに、ユーザーがアクセス許可を割り当てることができる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-318">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Let users assign permissions when they apply the label**.</span></span>

2. <span data-ttu-id="f2c8d-319">**[Outlook で、[転送不可] オプションと同等の制限を適用する]** チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-319">Select the checkbox: **In Outlook, enforce restrictions equivalent to the Do Not Forward option**.</span></span>

3. <span data-ttu-id="f2c8d-320">**[Word、PowerPoint、Excel で、ユーザーにアクセス許可を指定するように求める]** が選択されている場合、チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-320">If selected, clear the checkbox: **In Word, PowerPoint, and Excel, prompt users to specify permissions**.</span></span>

4. <span data-ttu-id="f2c8d-321">**[次へ]** を選択してウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-321">Select **Next** and complete the wizard.</span></span>

### <a name="example-2-label-that-restricts-read-only-permission-to-all-users-in-another-organization"></a><span data-ttu-id="f2c8d-322">例 2: 別の組織のすべてのユーザーを読み取り専用アクセス許可に制限するラベル</span><span class="sxs-lookup"><span data-stu-id="f2c8d-322">Example 2: Label that restricts read-only permission to all users in another organization</span></span>

<span data-ttu-id="f2c8d-323">このラベルは、非常に機密性の高いドキュメントを読み取り専用として共有するのに適しており、ドキュメントを表示するには常にインターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-323">This label is suitable for sharing very sensitive documents as read-only, and the documents always require an internet connection to view them.</span></span>

<span data-ttu-id="f2c8d-324">このラベルはメールには適していません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-324">This label is not suitable for emails.</span></span>

1. <span data-ttu-id="f2c8d-325">**[暗号化]** ページで: **[アクセス許可を今すぐ割り当てるか、それともユーザーに決定させますか?]** で、**[アクセス許可を今すぐ割り当てる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-325">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Assign permissions now**.</span></span>

2. <span data-ttu-id="f2c8d-326">**[オフライン アクセスの許可]** で、**[使用しない]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-326">For **Allow offline access**, select **Never**.</span></span>

3. <span data-ttu-id="f2c8d-327">**[アクセス許可の割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-327">Select **Assign permissions**.</span></span>

4. <span data-ttu-id="f2c8d-328">**[アクセス許可の割り当て]** ウィンドウで、**[特定のメール アドレスまたはドメインを追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-328">On the **Assign permissions** pane, select **Add specific email addresses or domains**.</span></span>

5. <span data-ttu-id="f2c8d-329">テキスト ボックスに、他の組織のドメイン名を入力します (例: **fabrikam.com**)。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-329">In the text box, enter the name of a domain from the other organization, for example, **fabrikam.com**.</span></span> <span data-ttu-id="f2c8d-330">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-330">Then select **Add**.</span></span>

6. <span data-ttu-id="f2c8d-331">**[アクセス許可の選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-331">Select **Choose permissions**.</span></span>

7. <span data-ttu-id="f2c8d-332">**[アクセス許可の選択]** ウィンドウで、ドロップダウン ボックスを選択し、**[ビューアー]** を選択し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-332">On the **Choose permissions** pane, select the dropdown box, select **Viewer**, and then select **Save**.</span></span>

8. <span data-ttu-id="f2c8d-333">**[アクセス許可の割り当て]** ウィンドウに戻り、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-333">Back on the **Assign Permissions** pane, select **Save**.</span></span>

9. <span data-ttu-id="f2c8d-334">**[暗号化]** ページで、**[次へ]** を選択してウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-334">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

### <a name="example-3-add-external-users-to-an-existing-label-that-encrypts-content"></a><span data-ttu-id="f2c8d-335">例 3: コンテンツを暗号化する既存のラベルに外部ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="f2c8d-335">Example 3: Add external users to an existing label that encrypts content</span></span>

<span data-ttu-id="f2c8d-336">追加した新しいユーザーは、このラベルで既に保護されているドキュメントとメールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-336">The new users that you add will be able open documents and emails that have already been protected with this label.</span></span> <span data-ttu-id="f2c8d-337">これらのユーザーに付与するアクセス許可は、既存のユーザーが持つアクセス許可とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-337">The permissions that you grant these users can be different from the permissions that the existing users have.</span></span>

1. <span data-ttu-id="f2c8d-338">**[暗号化]** ページで: **[アクセス許可を今すぐ割り当てるか、それともユーザーに決定させますか?]** で、**[アクセス許可を今すぐ割り当てる]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-338">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="f2c8d-339">**[アクセス許可の割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-339">Select **Assign permissions**.</span></span>

3. <span data-ttu-id="f2c8d-340">**[アクセス許可の割り当て]** ウィンドウで、**[特定のメール アドレスまたはドメインを追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-340">On the **Assign permissions** pane, select **Add specific email addresses or domains**.</span></span>

4. <span data-ttu-id="f2c8d-341">テキスト ボックスに、追加する最初のユーザー (またはグループ) のメール アドレスを入力し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-341">In the text box, enter the email address of the first user (or group) to add, and then select **Add**.</span></span>

5. <span data-ttu-id="f2c8d-342">**[アクセス許可の選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-342">Select **Choose permissions**.</span></span>

6. <span data-ttu-id="f2c8d-343">**[アクセス許可の選択]** ウィンドウで、このユーザー (またはグループ) のアクセス許可の選択し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-343">On the **Choose permissions** pane, select the permissions for this user (or group), and then select **Save**.</span></span>

7. <span data-ttu-id="f2c8d-344">**[アクセス許可の割り当て]** ウィンドウに戻り、このラベルに追加するユーザー (またはグループ) ごとに手順 3 から 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-344">Back on the **Assign Permissions** pane, repeat steps 3 through 6 for each user (or group) that you want to add to this label.</span></span> <span data-ttu-id="f2c8d-345">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-345">Then click **Save**.</span></span>

8. <span data-ttu-id="f2c8d-346">**[暗号化]** ページで、**[次へ]** を選択してウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-346">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

### <a name="example-4-label-that-encrypts-content-but-doesnt-restrict-who-can-access-it"></a><span data-ttu-id="f2c8d-347">例 4: コンテンツを暗号化するが、誰がアクセスできるかについては制限をしないラベル</span><span class="sxs-lookup"><span data-stu-id="f2c8d-347">Example 4: Label that encrypts content but doesn't restrict who can access it</span></span>

<span data-ttu-id="f2c8d-348">この構成には、メールまたはドキュメントを暗号化するためにユーザー、グループ、またはドメインを指定する必要がないという利点があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-348">This configuration has the advantage that you don't need to specify users, groups, or domains to encrypt an email or document.</span></span> <span data-ttu-id="f2c8d-349">コンテンツは引き続き暗号化され、使用権限、有効期限、オフライン アクセスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-349">The content will still be encrypted and you can still specify usage rights, an expiry date, and offline access.</span></span>

<span data-ttu-id="f2c8d-350">保護されたドキュメントまたはメールを開くことができるユーザーを制限する必要がない場合にのみ、この構成を使用してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-350">Use this configuration only when you do not need to restrict who can open the protected document or email.</span></span> [<span data-ttu-id="f2c8d-351">この設定の詳細情報</span><span class="sxs-lookup"><span data-stu-id="f2c8d-351">More information about this setting</span></span>](#requirements-and-limitations-for-add-any-authenticated-users)

1. <span data-ttu-id="f2c8d-352">**[暗号化]** ページで: **[アクセス許可を今すぐ割り当てるか、それともユーザーに決定させますか?]** で、**[アクセス許可を今すぐ割り当てる]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-352">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="f2c8d-353">必要に応じて、**[コンテンツへのユーザー アクセスの有効期限]** および **[オフライン アクセスの許可]** の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-353">Configure settings for **User access to content expires** and **Allow offline access** as required.</span></span>

3. <span data-ttu-id="f2c8d-354">**[アクセス許可の割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-354">Select **Assign permissions**.</span></span>

4. <span data-ttu-id="f2c8d-355">**[アクセス許可の割り当て]** ウィンドウで、**[すべての認証されたユーザーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-355">On the **Assign permissions** pane, select **Add any authenticated users**.</span></span>

    <span data-ttu-id="f2c8d-356">**[ユーザーとグループ]** については、自動的に追加された **Authenticated Users** を確認します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-356">For **Users and groups**, you see **Authenticated users** automatically added.</span></span> <span data-ttu-id="f2c8d-357">この値を削除することはできますが、変更はできません。削除すると、**[すべての認証されたユーザーの追加]** の選択がキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-357">You can't change this value, only delete it, which cancels the **Add any authenticated users** selection.</span></span>

5. <span data-ttu-id="f2c8d-358">**[アクセス許可の選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-358">Select **Choose permissions**.</span></span>

6. <span data-ttu-id="f2c8d-359">[**アクセス許可の選択**] ウィンドウで、ドロップダウン ボックスを選択し、必要なアクセス許可の選択して [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-359">On the **Choose permissions** pane, select the dropdown box, select the permissions you want, and then select **Save**.</span></span>

7. <span data-ttu-id="f2c8d-360">**[アクセス許可の割り当て]** ウィンドウに戻り、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-360">Back on the **Assign Permissions** pane, select **Save**.</span></span>

8. <span data-ttu-id="f2c8d-361">**[暗号化]** ページで、**[次へ]** を選択してウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-361">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

## <a name="considerations-for-encrypted-content"></a><span data-ttu-id="f2c8d-362">暗号化されたコンテンツに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f2c8d-362">Considerations for encrypted content</span></span>

<span data-ttu-id="f2c8d-363">重要なドキュメントやメールを暗号化することにより、許可されたユーザーのみがそのデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-363">Encrypting your most sensitive documents and emails helps to ensure that only authorized people can access this data.</span></span> <span data-ttu-id="f2c8d-364">ただし、考慮すべき点がいつくかあります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-364">However, there are some considerations to take into account:</span></span>

- <span data-ttu-id="f2c8d-365">[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md) 機能が組織でまだ有効になっていない場合:</span><span class="sxs-lookup"><span data-stu-id="f2c8d-365">If your organization hasn't [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>

  - <span data-ttu-id="f2c8d-366">暗号化されたファイルに対して、検索、電子情報開示、Delve は動作しません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-366">Search, eDiscovery, and Delve will not work for encrypted files.</span></span>
  - <span data-ttu-id="f2c8d-367">DLP ポリシーは、これらの暗号化されたファイルのメタデータ (保持ラベルの情報など) に対しては機能しますが、これらのファイルのコンテンツ (ファイル内のクレジット カード番号など) に対しては機能しません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-367">DLP policies work for the metadata of these encrypted files (including retention label information) but not the content of these files (such as credit card numbers within files).</span></span>
  - <span data-ttu-id="f2c8d-368">ユーザーは、暗号化されたファイルを Web 用 Office で開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-368">Users can't open encrypted files using Office on the web.</span></span> <span data-ttu-id="f2c8d-369">SharePoint および OneDrive 内の Office ファイルの秘密度ラベルが有効化されている場合、ユーザーは有効化されたファイルを Web 用 Office で開くことができますが、次のようないつくつかの[制限](sensitivity-labels-sharepoint-onedrive-files.md#limitations)があります: オンプレミス キー ("Hold Your Own Key" または HYOK と呼ばれます)を使用して適用された暗号化、[二重キー暗号化](#double-key-encryption)、秘密度ラベルとは別に適用された暗号化。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-369">When sensitivity labels for Office files in SharePoint and OneDrive are enabled, users can use Office on the web to open encrypted files, with some [limitations](sensitivity-labels-sharepoint-onedrive-files.md#limitations) that include encryption that has been applied with an on-premises key (known as "hold your own key", or HYOK), [double key encryption](#double-key-encryption), and encryption that has been applied independently from a sensitivity label.</span></span>

- <span data-ttu-id="f2c8d-370">暗号化されたファイルを複数のユーザーが同時に編集するには、全員が Web 用 Office を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-370">For multiple users to edit an encrypted file at the same time, they must all be using Office for the web.</span></span> <span data-ttu-id="f2c8d-371">この状況が当てはまらず、ファイルが既に開かれている場合、次のことが起こります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-371">If this isn't the case, and the file is already open:</span></span>

  - <span data-ttu-id="f2c8d-372">Office アプリ (Windows、Mac、Android、iOS)で、[**使用中のファイル**] メッセージがファイルをチェック アウトしているユーザーの名前とともにユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-372">In Office apps (Windows, Mac, Android, and iOS), users see a **File In Use** message with the name of the person who has checked out the file.</span></span> <span data-ttu-id="f2c8d-373">その場合、ユーザーは読み取り専用コピーの閲覧またはそのコピーの保存と編集を行うことが可能で、他のユーザーによるファイルの使用が終了したときに通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-373">They can then view a read-only copy or save and edit a copy of the file, and receive notification when the file is available.</span></span>
  - <span data-ttu-id="f2c8d-374">Web 用 Office では、他のユーザーと同時にドキュメントを編集することはできないというメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-374">In Office for the web, users see an error message that they can't edit the document with other people.</span></span> <span data-ttu-id="f2c8d-375">その場合は、[**閲覧表示で開く**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-375">They can then select **Open in Reading View**.</span></span>

- <span data-ttu-id="f2c8d-376">Office アプリ (Windows、Mac、Android、iOS) の[自動保存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)機能は、暗号化されたファイルに対しては無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-376">The [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality in Office apps (Windows, Mac, Android, and iOS) is disabled for encrypted files.</span></span> <span data-ttu-id="f2c8d-377">自動保存を有効にする前に削除する必要があるアクセスの制限がファイルに適用されているというメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-377">Users see a message that the file has restricted permissions that must be removed before AutoSave can be turned on.</span></span>

- <span data-ttu-id="f2c8d-378">暗号化されたファイルは、Office アプリ (Windows、Mac、Android、iOS) で開くのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-378">Encrypted files might take longer to open in Office apps (Windows, Mac, Android, and iOS).</span></span>

- <span data-ttu-id="f2c8d-379">暗号化されたファイルに対する次の操作は Office アプリ (Windows、Mac、Android、iOS) ではサポートされておらず、問題が発生したことを示すエラー メッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-379">The following actions for encrypted files aren't supported from Office apps (Windows, Mac, Android, and iOS), and users see an error message that something went wrong.</span></span> <span data-ttu-id="f2c8d-380">ただし、代替手段として SharePoint 機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-380">However, SharePoint functionality can be used as an alternative:</span></span>

  - <span data-ttu-id="f2c8d-381">以前のバージョンのコピーの表示、復元、および保存。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-381">View, restore, and save copies of previous versions.</span></span> <span data-ttu-id="f2c8d-382">代替方法として、[リストまたはライブラリのバージョン管理を有効にして構成する](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37)と、Web 用 Office でこれらの操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-382">As an alternative, users can do these actions using Office on the web when you [enable and configure versioning for a list or library](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).</span></span>
  - <span data-ttu-id="f2c8d-383">ファイルの名前または場所の変更。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-383">Change the name or location of files.</span></span> <span data-ttu-id="f2c8d-384">代替方法として、[ドキュメント ライブラリ内のファイル、フォルダー、またはリンクの名前を SharePoint で変更](https://support.microsoft.com/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185)することができます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-384">As an alternative, users can [rename a file, folder, or link in a document library](https://support.microsoft.com/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185) in SharePoint.</span></span>

<span data-ttu-id="f2c8d-385">秘密度ラベルを使用して暗号化されたファイルでの共同作業環境を最適化するには、[SharePoint および OndeDrive 内の Office ファイル用秘密度ラベル](sensitivity-labels-sharepoint-onedrive-files.md)および Web 用 Office を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-385">For the best collaboration experience for files that are encrypted by a sensitivity label, we recommend you use [sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) and Office for the web.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="f2c8d-386">重要な前提条件</span><span class="sxs-lookup"><span data-stu-id="f2c8d-386">Important prerequisites</span></span>

<span data-ttu-id="f2c8d-387">暗号化を使用するには、構成作業をいくつか行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-387">Before you can use encryption, you might need to do some configuration tasks.</span></span>

### <a name="activate-protection-from-azure-information-protection"></a><span data-ttu-id="f2c8d-388">Azure Information Protection の保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="f2c8d-388">Activate protection from Azure Information Protection</span></span>

<span data-ttu-id="f2c8d-389">秘密度ラベルが暗号化を適用するには、Azure Information Protection の保護サービス (Azure Rights Management) をテナントに対して有効にする必要があります。 </span><span class="sxs-lookup"><span data-stu-id="f2c8d-389">For sensitivity labels to apply encryption, the protection service (Azure Rights Management) from Azure Information Protection must be activated for your tenant.</span></span> <span data-ttu-id="f2c8d-390">新しいテナントの場合はこれが既定の設定になっていますが、サービスを手動で有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-390">In newer tenants, this is the default setting, but you might need to manually activate the service.</span></span> <span data-ttu-id="f2c8d-391">詳細については、「[Azure Information Protection の保護サービスのアクティブ化](https://docs.microsoft.com/azure/information-protection/activate-service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-391">For more information, see [Activating the protection service from Azure Information Protection](https://docs.microsoft.com/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="f2c8d-392">Azure Information Protection 用に Exchange を構成する</span><span class="sxs-lookup"><span data-stu-id="f2c8d-392">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="f2c8d-393">ユーザーは、Azure Information Protection 用に Exchange を構成していなくても、Outlook でラベルを適用してメールを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-393">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to encrypt their emails.</span></span> <span data-ttu-id="f2c8d-394">ただし、Exchange が Azure Information Protection 用に構成されるまで、Azure Rights Management 保護を使用する機能の一部を Exchange で利用できません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-394">However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>

<span data-ttu-id="f2c8d-395">たとえば、暗号化された電子メールを携帯電話や Outlook on the web で表示すること、暗号化された電子メールの検索用インデックスの作成、Rights Management 保護用に Exchange Online DLP を構成することなどは行えません。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-395">For example, users cannot view encrypted emails on mobile phones or with Outlook on the web, encrypted emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span>

<span data-ttu-id="f2c8d-396">このような追加のシナリオを Exchange でサポートする場合は、次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-396">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="f2c8d-397">Exchange Online の場合は、「[Exchange Online: IRM 構成](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration)」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-397">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration).</span></span>
- <span data-ttu-id="f2c8d-398">Exchange On-Premises の場合は、[RMS コネクタを展開して Exchange サーバーを構成する](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector)必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2c8d-398">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector).</span></span>
